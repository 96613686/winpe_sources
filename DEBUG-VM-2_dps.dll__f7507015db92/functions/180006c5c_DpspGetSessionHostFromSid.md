# DpspGetSessionHostFromSid

- ea: `0x180006c5c`
- end: `0x180006d01`
- name: `DpspGetSessionHostFromSid`
- size: `165`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003020`
- `0x180006d08`

## callees

- `0x180006c5c`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ced`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ced`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cb1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006cbe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006cbe`

## string_xrefs

- `0x180006c8c`: `DpspGetSessionHostFromSid`

## pseudocode

```c
__int64 __fastcall DpspGetSessionHostFromSid(PSID pSid1, int a2, int a3)
{
  __int64 i; // rbx

  if ( pSid1 )
  {
    for ( i = g_pHostHead; i; i = *(_QWORD *)(i + 136) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 72));
      if ( EqualSid(pSid1, *(PSID *)(i + 32)) && *(_DWORD *)(i + 40) == a2 && *(_DWORD *)(i + 120) == a3 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(i + 72));
        return i;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 72));
    }
  }
  else
  {
    i = 0;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspGetSessionHostFromSid",
      576,
      (int)L"Error = %d",
      87);
  }
  return i;
}

```

## disassembly

```asm
0x180006c5c  push    rbx
0x180006c5e  push    rbp
0x180006c5f  push    rsi
0x180006c60  push    rdi
0x180006c61  push    r14
0x180006c63  sub     rsp, 30h
0x180006c67  mov     ebp, r8d
0x180006c6a  mov     r14d, edx
0x180006c6d  mov     rsi, rcx
0x180006c70  test    rcx, rcx
0x180006c73  jnz     short loc_180006CA1
0x180006c75  xor     ebx, ebx
0x180006c77  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180006c7f  lea     r9, aErrorD; "Error = %d"
0x180006c86  mov     r8d, 240h; int
0x180006c8c  lea     rdx, aDpspgetsession_0; "DpspGetSessionHostFromSid"
0x180006c93  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006c9a  call    WdipTraceError
0x180006c9f  jmp     short loc_180006CF3
0x180006ca1  mov     rbx, cs:g_pHostHead
0x180006ca8  jmp     short loc_180006CE3
0x180006caa  lea     rdi, [rbx+48h]
0x180006cae  mov     rcx, rdi; lpCriticalSection
0x180006cb1  call    cs:__imp_EnterCriticalSection
0x180006cb7  mov     rdx, [rbx+20h]; pSid2
0x180006cbb  mov     rcx, rsi; pSid1
0x180006cbe  call    cs:__imp_EqualSid
0x180006cc4  test    eax, eax
0x180006cc6  jz      short loc_180006CD3
0x180006cc8  cmp     [rbx+28h], r14d
0x180006ccc  jnz     short loc_180006CD3
0x180006cce  cmp     [rbx+78h], ebp
0x180006cd1  jz      short loc_180006CEA
0x180006cd3  mov     rcx, rdi; lpCriticalSection
0x180006cd6  call    cs:__imp_LeaveCriticalSection
0x180006cdc  mov     rbx, [rbx+88h]
0x180006ce3  test    rbx, rbx
0x180006ce6  jnz     short loc_180006CAA
0x180006ce8  jmp     short loc_180006CF3
0x180006cea  mov     rcx, rdi; lpCriticalSection
0x180006ced  call    cs:__imp_LeaveCriticalSection
0x180006cf3  mov     rax, rbx
0x180006cf6  add     rsp, 30h
0x180006cfa  pop     r14
0x180006cfc  pop     rdi
0x180006cfd  pop     rsi
0x180006cfe  pop     rbp
0x180006cff  pop     rbx
0x180006d00  retn
```
