# CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x18005126c`
- end: `0x180051303`
- name: `?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `151`
- prototype: `unsigned int(HKEY, const wchar_t *, unsigned int, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800242d0`
- `0x18005130c`
- `0x1800517e8`

## callees

- `0x18005126c`
- `0x180052590`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800512e6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800512e6`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800512d3`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800512d3`

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
0x18005126c  mov     [rsp+arg_8], rbx
0x180051271  mov     [rsp+arg_10], rsi
0x180051276  mov     [rsp+arg_0], rcx
0x18005127b  push    rdi
0x18005127c  sub     rsp, 40h
0x180051280  mov     rbx, [rsp+48h+arg_20]
0x180051285  mov     edi, r9d
0x180051288  mov     rsi, rdx
0x18005128b  test    rbx, rbx
0x18005128e  jnz     short loc_180051297
0x180051290  mov     eax, 80004003h
0x180051295  jmp     short loc_1800512F2
0x180051297  lea     rcx, [rsp+48h+arg_0]
0x18005129c  mov     [rsp+48h+arg_0], 0
0x1800512a5  call    CbsGetCurrentTransaction
0x1800512aa  mov     rax, [rsp+48h+arg_0]
0x1800512af  xor     r8d, r8d; ulOptions
0x1800512b2  mov     r9d, edi; samDesired
0x1800512b5  mov     rdx, rsi; lpSubKey
0x1800512b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800512bf  test    rax, rax
0x1800512c2  jz      short loc_1800512E1
0x1800512c4  mov     [rsp+48h+pExtendedParemeter], r8; pExtendedParemeter
0x1800512c9  mov     [rsp+48h+hTransaction], rax; hTransaction
0x1800512ce  mov     [rsp+48h+phkResult], rbx; phkResult
0x1800512d3  call    cs:__imp_RegOpenKeyTransactedW
0x1800512da  nop     dword ptr [rax+rax+00h]
0x1800512df  jmp     short loc_1800512F2
0x1800512e1  mov     [rsp+48h+phkResult], rbx; phkResult
0x1800512e6  call    cs:__imp_RegOpenKeyExW
0x1800512ed  nop     dword ptr [rax+rax+00h]
0x1800512f2  mov     rbx, [rsp+48h+arg_8]
0x1800512f7  mov     rsi, [rsp+48h+arg_10]
0x1800512fc  add     rsp, 40h
0x180051300  pop     rdi
0x180051301  retn
```
