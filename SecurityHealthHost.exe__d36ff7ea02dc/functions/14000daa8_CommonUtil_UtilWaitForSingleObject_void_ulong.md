# CommonUtil::UtilWaitForSingleObject(void *,ulong)

- ea: `0x14000daa8`
- end: `0x14000db22`
- name: `?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z`
- size: `122`
- prototype: `bool __fastcall(CommonUtil *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002a94`

## callees

- `0x14000d068`
- `0x14000daa8`
- `0x14000f7c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000dab0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000dab0`

## pseudocode

```c
bool __fastcall CommonUtil::UtilWaitForSingleObject(CommonUtil *this, void *a2)
{
  unsigned int v2; // ebx
  DWORD v3; // eax
  __int64 v4; // rdx
  bool v5; // zf
  int LastFailure; // r8d

  v2 = (unsigned int)a2;
  v3 = WaitForSingleObject(this, (DWORD)a2);
  if ( !v3 || v3 == 128 )
    return v3 == 258;
  v5 = v3 == 258;
  if ( v3 == 258 )
    return v5;
  LastFailure = -2147024890;
  if ( v3 == -1 )
    LastFailure = HrGetLastFailure(258, v4, 2147942406LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, v2, LastFailure);
  return 0;
}

```

## disassembly

```asm
0x14000daa8  push    rbx
0x14000daaa  sub     rsp, 30h
0x14000daae  mov     ebx, edx
0x14000dab0  call    cs:__imp_WaitForSingleObject
0x14000dab6  mov     ecx, 102h
0x14000dabb  test    eax, eax
0x14000dabd  jz      short loc_14000DB17
0x14000dabf  cmp     eax, 80h
0x14000dac4  jz      short loc_14000DB17
0x14000dac6  cmp     eax, ecx
0x14000dac8  jz      short loc_14000DB19
0x14000daca  mov     r8d, 80070006h
0x14000dad0  cmp     eax, 0FFFFFFFFh
0x14000dad3  jnz     short loc_14000DADD
0x14000dad5  call    HrGetLastFailure
0x14000dada  mov     r8d, eax
0x14000dadd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dae4  lea     rax, WPP_GLOBAL_Control
0x14000daeb  cmp     rcx, rax
0x14000daee  jz      short loc_14000DB13
0x14000daf0  test    byte ptr [rcx+1Ch], 1
0x14000daf4  jz      short loc_14000DB13
0x14000daf6  mov     rcx, [rcx+10h]
0x14000dafa  mov     edx, 12h
0x14000daff  mov     [rsp+38h+var_18], r8d
0x14000db04  mov     r9d, ebx
0x14000db07  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000db0e  call    WPP_SF_Dd
0x14000db13  xor     al, al
0x14000db15  jmp     short loc_14000DB1C
0x14000db17  cmp     eax, ecx
0x14000db19  setz    al
0x14000db1c  add     rsp, 30h
0x14000db20  pop     rbx
0x14000db21  retn
```
