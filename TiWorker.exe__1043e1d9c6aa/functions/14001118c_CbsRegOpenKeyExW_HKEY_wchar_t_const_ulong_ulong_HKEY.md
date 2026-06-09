# CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x14001118c`
- end: `0x140011216`
- name: `?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `138`
- prototype: `LSTATUS __fastcall(HKEY, const wchar_t *, __int64, REGSAM, PHKEY)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010fe0`
- `0x14001121c`
- `0x140011550`
- `0x140011a30`

## callees

- `0x14001118c`
- `0x140024efc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011200`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011200`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x1400111f3`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x1400111f3`

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
0x14001118c  mov     [rsp+arg_8], rbx
0x140011191  mov     [rsp+arg_10], rsi
0x140011196  mov     [rsp+arg_0], rcx
0x14001119b  push    rdi
0x14001119c  sub     rsp, 40h
0x1400111a0  mov     rbx, [rsp+48h+arg_20]
0x1400111a5  mov     edi, r9d
0x1400111a8  mov     rsi, rdx
0x1400111ab  test    rbx, rbx
0x1400111ae  jnz     short loc_1400111B7
0x1400111b0  mov     eax, 80004003h
0x1400111b5  jmp     short loc_140011206
0x1400111b7  lea     rcx, [rsp+48h+arg_0]; void **
0x1400111bc  mov     [rsp+48h+arg_0], 0
0x1400111c5  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x1400111ca  mov     rax, [rsp+48h+arg_0]
0x1400111cf  xor     r8d, r8d; ulOptions
0x1400111d2  mov     r9d, edi; samDesired
0x1400111d5  mov     rdx, rsi; lpSubKey
0x1400111d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400111df  test    rax, rax
0x1400111e2  jz      short loc_1400111FB
0x1400111e4  mov     [rsp+48h+pExtendedParemeter], r8; pExtendedParemeter
0x1400111e9  mov     [rsp+48h+hTransaction], rax; hTransaction
0x1400111ee  mov     [rsp+48h+phkResult], rbx; phkResult
0x1400111f3  call    cs:__imp_RegOpenKeyTransactedW
0x1400111f9  jmp     short loc_140011206
0x1400111fb  mov     [rsp+48h+phkResult], rbx; phkResult
0x140011200  call    cs:__imp_RegOpenKeyExW
0x140011206  mov     rbx, [rsp+48h+arg_8]
0x14001120b  mov     rsi, [rsp+48h+arg_10]
0x140011210  add     rsp, 40h
0x140011214  pop     rdi
0x140011215  retn
```
