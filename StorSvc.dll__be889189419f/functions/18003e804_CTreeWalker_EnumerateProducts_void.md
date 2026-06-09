# CTreeWalker::EnumerateProducts(void)

- ea: `0x18003e804`
- end: `0x18003e953`
- name: `?EnumerateProducts@CTreeWalker@@AEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(CTreeWalker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003e090`

## callees

- `0x18000d030`
- `0x18003e804`
- `0x18003ecc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e90c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e90c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e873`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e873`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003e8c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003e8c9`

## pseudocode

```c
LSTATUS __fastcall CTreeWalker::EnumerateProducts(CTreeWalker *this)
{
  int v1; // ebx
  unsigned int i; // edi
  LSTATUS result; // eax
  DWORD j; // esi
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+40h] [rbp-248h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  v1 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return v1;
    hKey = 0;
    result = RegOpenKeyExW((HKEY)qword_1800BFA30[66 * i], (LPCWSTR)&qword_1800BFA30[66 * i + 1], 0, 0x20019u, &hKey);
    if ( result != 2 )
      break;
LABEL_14:
    ;
  }
  if ( !result )
  {
    for ( j = 0; ; ++j )
    {
      cchName = 260;
      v6 = RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0);
      if ( v6 )
        break;
      v1 = CTreeWalker::PrepareProductInfo(this, hKey, Name);
      if ( v1 < 0 )
        goto LABEL_13;
    }
    if ( v6 != 259 )
    {
      if ( v6 > 0 )
        v1 = (unsigned __int16)v6 | 0x80070000;
      else
        v1 = v6;
    }
LABEL_13:
    RegCloseKey(hKey);
    if ( v1 < 0 )
      return v1;
    goto LABEL_14;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003e804  mov     [rsp+arg_8], rbx
0x18003e809  mov     [rsp+arg_10], rbp
0x18003e80e  push    rsi
0x18003e80f  push    rdi
0x18003e810  push    r12
0x18003e812  sub     rsp, 270h
0x18003e819  mov     rax, cs:__security_cookie
0x18003e820  xor     rax, rsp
0x18003e823  mov     [rsp+288h+var_28], rax
0x18003e82b  xor     ebx, ebx
0x18003e82d  lea     r12, qword_1800BFA30
0x18003e834  xor     edi, edi
0x18003e836  mov     rbp, rcx
0x18003e839  cmp     edi, 4
0x18003e83c  jnb     loc_18003E929
0x18003e842  mov     eax, edi
0x18003e844  lea     rdx, [r12+8]
0x18003e849  imul    rcx, rax, 210h
0x18003e850  lea     rax, [rsp+288h+hKey]
0x18003e855  mov     [rsp+288h+hKey], 0
0x18003e85e  add     rdx, rcx; lpSubKey
0x18003e861  mov     [rsp+288h+phkResult], rax; phkResult
0x18003e866  mov     r9d, 20019h; samDesired
0x18003e86c  xor     r8d, r8d; ulOptions
0x18003e86f  mov     rcx, [rcx+r12]; hKey
0x18003e873  call    cs:__imp_RegOpenKeyExW
0x18003e879  cmp     eax, 2
0x18003e87c  jz      loc_18003E916
0x18003e882  test    eax, eax
0x18003e884  jnz     loc_18003E91D
0x18003e88a  xor     esi, esi
0x18003e88c  mov     rcx, [rsp+288h+hKey]; hKey
0x18003e891  lea     r9, [rsp+288h+cchName]; lpcchName
0x18003e896  mov     [rsp+288h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003e89f  lea     r8, [rsp+288h+Name]; lpName
0x18003e8a4  mov     [rsp+288h+lpcchClass], 0; lpcchClass
0x18003e8ad  mov     edx, esi; dwIndex
0x18003e8af  mov     [rsp+288h+lpClass], 0; lpClass
0x18003e8b8  mov     [rsp+288h+phkResult], 0; lpReserved
0x18003e8c1  mov     [rsp+288h+cchName], 104h
0x18003e8c9  call    cs:__imp_RegEnumKeyExW
0x18003e8cf  test    eax, eax
0x18003e8d1  jnz     short loc_18003E8EF
0x18003e8d3  mov     rdx, [rsp+288h+hKey]; HKEY
0x18003e8d8  lea     r8, [rsp+288h+Name]; unsigned __int16 *
0x18003e8dd  mov     rcx, rbp; this
0x18003e8e0  call    ?PrepareProductInfo@CTreeWalker@@AEAAJPEAUHKEY__@@PEBG@Z; CTreeWalker::PrepareProductInfo(HKEY__ *,ushort const *)
0x18003e8e5  mov     ebx, eax
0x18003e8e7  test    eax, eax
0x18003e8e9  js      short loc_18003E907
0x18003e8eb  inc     esi
0x18003e8ed  jmp     short loc_18003E88C
0x18003e8ef  cmp     eax, 103h
0x18003e8f4  jz      short loc_18003E907
0x18003e8f6  test    eax, eax
0x18003e8f8  jg      short loc_18003E8FE
0x18003e8fa  mov     ebx, eax
0x18003e8fc  jmp     short loc_18003E907
0x18003e8fe  movzx   ebx, ax
0x18003e901  or      ebx, 80070000h
0x18003e907  mov     rcx, [rsp+288h+hKey]; hKey
0x18003e90c  call    cs:__imp_RegCloseKey
0x18003e912  test    ebx, ebx
0x18003e914  js      short loc_18003E929
0x18003e916  inc     edi
0x18003e918  jmp     loc_18003E839
0x18003e91d  jle     short loc_18003E92B
0x18003e91f  movzx   eax, ax
0x18003e922  or      eax, 80070000h
0x18003e927  jmp     short loc_18003E92B
0x18003e929  mov     eax, ebx
0x18003e92b  mov     rcx, [rsp+288h+var_28]
0x18003e933  xor     rcx, rsp; StackCookie
0x18003e936  call    __security_check_cookie
0x18003e93b  lea     r11, [rsp+288h+var_18]
0x18003e943  mov     rbx, [r11+28h]
0x18003e947  mov     rbp, [r11+30h]
0x18003e94b  mov     rsp, r11
0x18003e94e  pop     r12
0x18003e950  pop     rdi
0x18003e951  pop     rsi
0x18003e952  retn
```
