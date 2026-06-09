# CWinSATTaskMangerTask::Stop(long *)

- ea: `0x180021330`
- end: `0x18002139e`
- name: `?Stop@CWinSATTaskMangerTask@@UEAAJPEAJ@Z`
- size: `110`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000f0e8`
- `0x180021330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021381`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021381`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002135c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002135c`

## string_xrefs

- `0x18002134c`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::Stop(CWinSATTaskMangerTask *this, int *a2)
{
  __int64 result; // rax
  void *v5; // rcx

  Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 646, "Received STOP signal");
  if ( SetEvent(*((HANDLE *)this + 14)) )
  {
    v5 = (void *)*((_QWORD *)this + 11);
    if ( v5 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    *a2 = 0;
    return 0;
  }
  else
  {
    result = 2147500037LL;
    *a2 = -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180021330  mov     [rsp+arg_0], rbx
0x180021335  push    rdi
0x180021336  sub     rsp, 20h
0x18002133a  mov     rbx, rdx
0x18002133d  lea     r8, aReceivedStopSi; "Received STOP signal"
0x180021344  mov     rdi, rcx
0x180021347  mov     edx, 286h
0x18002134c  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021353  call    Log_Text_F
0x180021358  mov     rcx, [rdi+70h]; hEvent
0x18002135c  call    cs:__imp_SetEvent
0x180021363  nop     dword ptr [rax+rax+00h]
0x180021368  test    eax, eax
0x18002136a  jnz     short loc_180021375
0x18002136c  mov     eax, 80004005h
0x180021371  mov     [rbx], eax
0x180021373  jmp     short loc_180021392
0x180021375  mov     rcx, [rdi+58h]; hHandle
0x180021379  test    rcx, rcx
0x18002137c  jz      short loc_18002138D
0x18002137e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021381  call    cs:__imp_WaitForSingleObject
0x180021388  nop     dword ptr [rax+rax+00h]
0x18002138d  and     dword ptr [rbx], 0
0x180021390  xor     eax, eax
0x180021392  mov     rbx, [rsp+28h+arg_0]
0x180021397  add     rsp, 20h
0x18002139b  pop     rdi
0x18002139c  retn
```
