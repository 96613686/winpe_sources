# CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x18004e134`
- end: `0x18004e1cb`
- name: `?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `151`
- prototype: `unsigned int(HKEY, const wchar_t *, unsigned int, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021300`
- `0x18004e1d4`
- `0x18004e6b4`

## callees

- `0x18004e134`
- `0x18004f460`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004e1ae`
- `ADVAPI32!RegOpenKeyExW` at `0x18004e1ae`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x18004e19b`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x18004e19b`

## pseudocode

```c
LSTATUS __fastcall CbsRegOpenKeyExW(HKEY a1, const wchar_t *a2, __int64 a3, REGSAM a4, PHKEY a5)
{
  HKEY *phkResult; // rbx
  HANDLE hTransaction; // [rsp+50h] [rbp+8h] BYREF

  hTransaction = a1;
  phkResult = a5;
  if ( !a5 )
    return -2147467261;
  hTransaction = 0;
  CbsGetCurrentTransaction(&hTransaction);
  if ( hTransaction )
    return RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, a2, 0, a4, phkResult, hTransaction, 0);
  else
    return RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, a4, phkResult);
}

```

## disassembly

```asm
0x18004e134  mov     [rsp+arg_8], rbx
0x18004e139  mov     [rsp+arg_10], rsi
0x18004e13e  mov     [rsp+arg_0], rcx
0x18004e143  push    rdi
0x18004e144  sub     rsp, 40h
0x18004e148  mov     rbx, [rsp+48h+arg_20]
0x18004e14d  mov     edi, r9d
0x18004e150  mov     rsi, rdx
0x18004e153  test    rbx, rbx
0x18004e156  jnz     short loc_18004E15F
0x18004e158  mov     eax, 80004003h
0x18004e15d  jmp     short loc_18004E1BA
0x18004e15f  lea     rcx, [rsp+48h+arg_0]; void **
0x18004e164  mov     [rsp+48h+arg_0], 0
0x18004e16d  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x18004e172  mov     rax, [rsp+48h+arg_0]
0x18004e177  xor     r8d, r8d; ulOptions
0x18004e17a  mov     r9d, edi; samDesired
0x18004e17d  mov     rdx, rsi; lpSubKey
0x18004e180  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004e187  test    rax, rax
0x18004e18a  jz      short loc_18004E1A9
0x18004e18c  mov     [rsp+48h+pExtendedParemeter], r8; pExtendedParemeter
0x18004e191  mov     [rsp+48h+hTransaction], rax; hTransaction
0x18004e196  mov     [rsp+48h+phkResult], rbx; phkResult
0x18004e19b  call    cs:__imp_RegOpenKeyTransactedW
0x18004e1a2  nop     dword ptr [rax+rax+00h]
0x18004e1a7  jmp     short loc_18004E1BA
0x18004e1a9  mov     [rsp+48h+phkResult], rbx; phkResult
0x18004e1ae  call    cs:__imp_RegOpenKeyExW
0x18004e1b5  nop     dword ptr [rax+rax+00h]
0x18004e1ba  mov     rbx, [rsp+48h+arg_8]
0x18004e1bf  mov     rsi, [rsp+48h+arg_10]
0x18004e1c4  add     rsp, 40h
0x18004e1c8  pop     rdi
0x18004e1c9  retn
```
