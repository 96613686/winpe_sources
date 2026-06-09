# DpspDeleteSecurityAttributes

- ea: `0x1800062a8`
- end: `0x18000635a`
- name: `DpspDeleteSecurityAttributes`
- size: `178`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004864`
- `0x180004de4`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011fd4`

## callees

- `0x1800062a8`
- `0x180008ea0`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006344`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006344`
- `ntdll!AlpcGetMessageAttribute` at `0x18000630a`
- `ntdll!AlpcGetMessageAttribute` at `0x18000630a`
- `ntdll!NtAlpcDeleteSecurityContext` at `0x18000631e`
- `ntdll!NtAlpcDeleteSecurityContext` at `0x18000631e`

## string_xrefs

- `0x1800062e4`: `DpspDeleteSecurityAttributes`

## pseudocode

```c
void __fastcall DpspDeleteSecurityAttributes(__int64 a1, RTL_SRWLOCK *a2)
{
  PVOID Ptr; // rcx
  __int64 MessageAttribute; // rax

  if ( a2 )
    AcquireSRWLockExclusive(a2 + 2);
  if ( a1 )
  {
    Ptr = a2[94].Ptr;
    if ( Ptr )
    {
      MessageAttribute = AlpcGetMessageAttribute(Ptr, 0x80000000LL);
      if ( MessageAttribute )
        NtAlpcDeleteSecurityContext(a1, 0, *(_QWORD *)(MessageAttribute + 16));
      WdipFree(a2[94].Ptr);
      a2[94].Ptr = 0;
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspDeleteSecurityAttributes",
      114,
      (int)L"Error = %d",
      87);
  }
  if ( a2 )
    ReleaseSRWLockExclusive(a2 + 2);
}

```

## disassembly

```asm
0x1800062a8  mov     [rsp+arg_0], rbx
0x1800062ad  mov     [rsp+arg_8], rsi
0x1800062b2  push    rdi
0x1800062b3  sub     rsp, 30h
0x1800062b7  mov     rbx, rdx
0x1800062ba  mov     rsi, rcx
0x1800062bd  test    rdx, rdx
0x1800062c0  jz      short loc_1800062CC
0x1800062c2  lea     rcx, [rdx+10h]; SRWLock
0x1800062c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800062cc  test    rsi, rsi
0x1800062cf  jnz     short loc_1800062F9
0x1800062d1  lea     r9, aErrorD; "Error = %d"
0x1800062d8  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x1800062e0  lea     r8d, [rsi+72h]; int
0x1800062e4  lea     rdx, aDpspdeletesecu; "DpspDeleteSecurityAttributes"
0x1800062eb  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800062f2  call    WdipTraceError
0x1800062f7  jmp     short loc_18000633B
0x1800062f9  mov     rcx, [rbx+2F0h]
0x180006300  test    rcx, rcx
0x180006303  jz      short loc_18000633B
0x180006305  mov     edx, 80000000h
0x18000630a  call    cs:__imp_AlpcGetMessageAttribute
0x180006310  test    rax, rax
0x180006313  jz      short loc_180006324
0x180006315  mov     r8, [rax+10h]
0x180006319  xor     edx, edx
0x18000631b  mov     rcx, rsi
0x18000631e  call    cs:__imp_NtAlpcDeleteSecurityContext
0x180006324  mov     rcx, [rbx+2F0h]
0x18000632b  call    WdipFree
0x180006330  mov     qword ptr [rbx+2F0h], 0
0x18000633b  test    rbx, rbx
0x18000633e  jz      short loc_18000634A
0x180006340  lea     rcx, [rbx+10h]; SRWLock
0x180006344  call    cs:__imp_ReleaseSRWLockExclusive
0x18000634a  mov     rbx, [rsp+38h+arg_0]
0x18000634f  mov     rsi, [rsp+38h+arg_8]
0x180006354  add     rsp, 30h
0x180006358  pop     rdi
0x180006359  retn
```
