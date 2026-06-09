# CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)

- ea: `0x180021ebc`
- end: `0x180021ef7`
- name: `?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z`
- size: `59`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned __int64, unsigned __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021898`
- `0x1800219d4`

## callees

- `0x18001b5d8`
- `0x180021ebc`

## string_xrefs

- `0x180021ecd`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`
- `0x180021ec1`: `First idle run time is is greater than first sucesfully completion time`
- `0x180021ee5`: `Completion to first run time difference is greater than 32 bits can hold`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::SQMFirstCompletionDuration(
        CWinSATTaskMangerTask *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int *a4)
{
  wchar_t *v4; // r8
  unsigned int v5; // edx
  unsigned __int64 v6; // r8

  if ( a2 >= a3 )
  {
    v4 = (wchar_t *)L"First idle run time is is greater than first sucesfully completion time";
    v5 = 141;
LABEL_3:
    Record_InternalError_w("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp", v5, v4);
    return;
  }
  v6 = a3 - a2;
  if ( v6 > 0xFFFF )
  {
    v4 = L"Completion to first run time difference is greater than 32 bits can hold";
    v5 = 154;
    goto LABEL_3;
  }
  *a4 = v6;
}

```

## disassembly

```asm
0x180021ebc  cmp     rdx, r8
0x180021ebf  jb      short loc_180021ED9
0x180021ec1  lea     r8, aFirstIdleRunTi; "First idle run time is is greater than "...
0x180021ec8  mov     edx, 8Dh; unsigned int
0x180021ecd  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021ed4  jmp     Record_InternalError_w
0x180021ed9  sub     r8, rdx
0x180021edc  cmp     r8, 0FFFFh
0x180021ee3  jbe     short loc_180021EF3
0x180021ee5  lea     r8, aCompletionToFi; "Completion to first run time difference"...
0x180021eec  mov     edx, 9Ah
0x180021ef1  jmp     short loc_180021ECD
0x180021ef3  mov     [r9], r8d
0x180021ef6  retn
```
