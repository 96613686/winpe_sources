# CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x14001a0e0`
- end: `0x14001a163`
- name: `?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `131`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpSubKey, __int64, REGSAM, PHKEY hTransaction)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001a16c`
- `0x14001a4c0`
- `0x14001a7e4`
- `0x14001acbc`
- `0x14001afa4`

## callees

- `0x14001a0e0`
- `0x140022498`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a154`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a154`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14001a147`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14001a147`

## pseudocode

```c
LSTATUS __fastcall CbsRegOpenKeyExW(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, REGSAM a4, PHKEY hTransaction)
{
  HKEY *phkResult; // rbx

  phkResult = hTransaction;
  if ( !hTransaction )
    return -2147467261;
  hTransaction = 0;
  CbsGetCurrentTransaction((void **)&hTransaction);
  if ( hTransaction )
    return RegOpenKeyTransactedW(hKey, lpSubKey, 0, a4, phkResult, hTransaction, 0);
  else
    return RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
}

```

## disassembly

```asm
0x14001a0e0  push    rbx
0x14001a0e2  push    rbp
0x14001a0e3  push    rsi
0x14001a0e4  push    rdi
0x14001a0e5  sub     rsp, 48h
0x14001a0e9  mov     rbx, [rsp+68h+arg_20]
0x14001a0f1  mov     edi, r9d
0x14001a0f4  mov     rsi, rdx
0x14001a0f7  mov     rbp, rcx
0x14001a0fa  test    rbx, rbx
0x14001a0fd  jnz     short loc_14001A106
0x14001a0ff  mov     eax, 80004003h
0x14001a104  jmp     short loc_14001A15A
0x14001a106  lea     rcx, [rsp+68h+arg_20]; void **
0x14001a10e  mov     [rsp+68h+arg_20], 0
0x14001a11a  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x14001a11f  mov     rax, [rsp+68h+arg_20]
0x14001a127  xor     r8d, r8d; ulOptions
0x14001a12a  mov     r9d, edi; samDesired
0x14001a12d  mov     rdx, rsi; lpSubKey
0x14001a130  mov     rcx, rbp; hKey
0x14001a133  test    rax, rax
0x14001a136  jz      short loc_14001A14F
0x14001a138  mov     [rsp+68h+pExtendedParemeter], r8; pExtendedParemeter
0x14001a13d  mov     [rsp+68h+hTransaction], rax; hTransaction
0x14001a142  mov     [rsp+68h+phkResult], rbx; phkResult
0x14001a147  call    cs:__imp_RegOpenKeyTransactedW
0x14001a14d  jmp     short loc_14001A15A
0x14001a14f  mov     [rsp+68h+phkResult], rbx; phkResult
0x14001a154  call    cs:__imp_RegOpenKeyExW
0x14001a15a  add     rsp, 48h
0x14001a15e  pop     rdi
0x14001a15f  pop     rsi
0x14001a160  pop     rbp
0x14001a161  pop     rbx
0x14001a162  retn
```
