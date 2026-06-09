# PaymentSelection::Store(PaymentSelection const &)

- ea: `0x18003c484`
- end: `0x18003c5a3`
- name: `?Store@PaymentSelection@@SAJAEBU1@@Z`
- size: `287`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fed4`
- `0x18003004c`
- `0x180031a94`
- `0x180031ff0`
- `0x18003226c`
- `0x1800341b0`
- `0x180034554`
- `0x180040f40`

## callees

- `0x18003c484`
- `0x18007d504`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003c531`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003c531`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c58b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c58b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c510`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c568`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c510`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c568`

## pseudocode

```c
__int64 __fastcall PaymentSelection::Store(BYTE *lpData, unsigned int a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  const wchar_t *v4; // rdi
  signed int v6; // ebx
  int v7; // eax
  LSTATUS v8; // eax
  int v9; // eax
  int v10; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v4 = (const wchar_t *)(lpData + 16);
  if ( lpData == (BYTE *)-16LL )
  {
    return (unsigned int)-2147467261;
  }
  else
  {
    hKey = 0;
    v7 = NfcRegCreateKeyEx((const struct NfcRegistryLocation *)&qword_1800A1C18, a2, 0x20006u, a4, &hKey, 0);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      v8 = RegSetValueExW(hKey, L"PaymentSelectionGuid", 0, 3u, lpData, 0x10u);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
      {
        v9 = wcsnlen(v4, 0x41u);
        if ( v9 == 65 )
        {
          v6 = -2147024809;
        }
        else
        {
          v10 = RegSetValueExW(hKey, L"PaymentSelectionPackage", 0, 1u, (const BYTE *)v4, 2 * v9 + 2);
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          v6 = 0;
          if ( v10 < 0 )
            v6 = v10;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c484  mov     [rsp+arg_8], rbx
0x18003c489  mov     [rsp+arg_10], rsi
0x18003c48e  push    rdi
0x18003c48f  sub     rsp, 30h
0x18003c493  lea     rdi, [rcx+10h]
0x18003c497  mov     rsi, rcx
0x18003c49a  test    rdi, rdi
0x18003c49d  jnz     short loc_18003C4A9
0x18003c49f  mov     ebx, 80004003h
0x18003c4a4  jmp     loc_18003C591
0x18003c4a9  lea     rax, [rsp+38h+hKey]
0x18003c4ae  mov     qword ptr [rsp+38h+cbData], 0; unsigned int *
0x18003c4b7  mov     r8d, 20006h; unsigned int
0x18003c4bd  mov     [rsp+38h+lpData], rax; HKEY *
0x18003c4c2  lea     rcx, qword_1800A1C18; struct NfcRegistryLocation *
0x18003c4c9  mov     [rsp+38h+hKey], 0
0x18003c4d2  call    ?NfcRegCreateKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; NfcRegCreateKeyEx(NfcRegistryLocation const &,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18003c4d7  mov     ebx, eax
0x18003c4d9  test    eax, eax
0x18003c4db  jle     short loc_18003C4E6
0x18003c4dd  movzx   ebx, ax
0x18003c4e0  or      ebx, 80070000h
0x18003c4e6  test    ebx, ebx
0x18003c4e8  js      loc_18003C581
0x18003c4ee  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c4f3  lea     rdx, aPaymentselecti_0; "PaymentSelectionGuid"
0x18003c4fa  mov     [rsp+38h+cbData], 10h; cbData
0x18003c502  mov     r9d, 3; dwType
0x18003c508  xor     r8d, r8d; Reserved
0x18003c50b  mov     [rsp+38h+lpData], rsi; lpData
0x18003c510  call    cs:__imp_RegSetValueExW
0x18003c516  mov     ebx, eax
0x18003c518  test    eax, eax
0x18003c51a  jle     short loc_18003C525
0x18003c51c  movzx   ebx, ax
0x18003c51f  or      ebx, 80070000h
0x18003c525  test    ebx, ebx
0x18003c527  js      short loc_18003C581
0x18003c529  mov     edx, 41h ; 'A'; MaxCount
0x18003c52e  mov     rcx, rdi; Source
0x18003c531  call    cs:__imp_wcsnlen
0x18003c537  cmp     eax, 41h ; 'A'
0x18003c53a  jnz     short loc_18003C543
0x18003c53c  mov     ebx, 80070057h
0x18003c541  jmp     short loc_18003C581
0x18003c543  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c548  lea     eax, ds:2[rax*2]
0x18003c54f  mov     [rsp+38h+cbData], eax; cbData
0x18003c553  lea     rdx, aPaymentselecti; "PaymentSelectionPackage"
0x18003c55a  mov     r9d, 1; dwType
0x18003c560  mov     [rsp+38h+lpData], rdi; lpData
0x18003c565  xor     r8d, r8d; Reserved
0x18003c568  call    cs:__imp_RegSetValueExW
0x18003c56e  test    eax, eax
0x18003c570  jle     short loc_18003C57A
0x18003c572  movzx   eax, ax
0x18003c575  or      eax, 80070000h
0x18003c57a  xor     ebx, ebx
0x18003c57c  test    eax, eax
0x18003c57e  cmovs   ebx, eax
0x18003c581  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c586  test    rcx, rcx
0x18003c589  jz      short loc_18003C591
0x18003c58b  call    cs:__imp_RegCloseKey
0x18003c591  mov     rsi, [rsp+38h+arg_10]
0x18003c596  mov     eax, ebx
0x18003c598  mov     rbx, [rsp+38h+arg_8]
0x18003c59d  add     rsp, 30h
0x18003c5a1  pop     rdi
0x18003c5a2  retn
```
