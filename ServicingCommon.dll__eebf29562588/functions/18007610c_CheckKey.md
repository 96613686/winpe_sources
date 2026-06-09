# CheckKey

- ea: `0x18007610c`
- end: `0x1800762f9`
- name: `CheckKey`
- size: `493`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180076b90`

## callees

- `0x180075cac`
- `0x18007610c`
- `0x180076398`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007624a`
- `KERNEL32!GetLastError` at `0x18007624a`
- `ADVAPI32!RegOpenKeyExW` at `0x18007616c`
- `ADVAPI32!RegOpenKeyExW` at `0x18007616c`
- `ADVAPI32!RegCloseKey` at `0x1800761ad`
- `ADVAPI32!RegCloseKey` at `0x1800761ad`
- `ADVAPI32!RegEnumKeyExW` at `0x18007629f`
- `ADVAPI32!RegEnumKeyExW` at `0x18007629f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076203`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076203`

## string_xrefs

- `0x180076181`: `Error %d opening [%s]\n`

## pseudocode

```c
__int64 __fastcall CheckKey(WCHAR *Src, int a2)
{
  REGSAM v3; // r9d
  const wchar_t *v4; // r9
  int v5; // r8d
  __int64 KeyInfo; // rax
  __int64 v8; // rbx
  DWORD cSubKeys; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( a2 == 13 )
  {
    v3 = 983359;
  }
  else
  {
    v3 = 983103;
    if ( a2 == 12 )
      v3 = 983615;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Src + 8, 0, v3, &hKey) )
  {
    v4 = L"Error %d opening [%s]\n";
    v5 = 953;
LABEL_7:
    dprintf(5, (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c", v5, (_DWORD)v4);
    goto LABEL_8;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    v4 = L"Error %d querying key [%s]\n";
    v5 = 971;
    goto LABEL_7;
  }
  if ( !cSubKeys )
    goto LABEL_8;
  KeyInfo = AllocateKeyInfo(Src);
  v8 = KeyInfo;
  if ( !KeyInfo )
  {
    GetLastError();
    v4 = L"Error [%d] not enough memory [%s]\n";
    v5 = 984;
    goto LABEL_7;
  }
  cbMaxSubKeyLen = *(_DWORD *)(KeyInfo + 40) - *(_DWORD *)(KeyInfo + 32);
  if ( !RegEnumKeyExW(
          hKey,
          0,
          (LPWSTR)(*(_QWORD *)(KeyInfo + 24) + 2LL * *(unsigned int *)(KeyInfo + 32)),
          &cbMaxSubKeyLen,
          0,
          0,
          0,
          0) )
  {
    *(_DWORD *)(v8 + 36) = cbMaxSubKeyLen;
    *(_QWORD *)(v8 + 16) = hKey;
    return v8;
  }
  dprintf(
    5,
    (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
    1001,
    (unsigned int)L"Error %d enumerating [%s]\n");
  FreeKeyInfo((HLOCAL)v8);
LABEL_8:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18007610c  push    rbp
0x18007610e  push    rbx
0x18007610f  push    rsi
0x180076110  push    rdi
0x180076111  push    r14
0x180076113  mov     rbp, rsp
0x180076116  sub     rsp, 60h
0x18007611a  xor     r14d, r14d
0x18007611d  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180076125  mov     [rbp+cSubKeys], r14d
0x180076129  mov     rsi, r8
0x18007612c  mov     [rbp+cbMaxSubKeyLen], r14d
0x180076130  mov     rdi, rcx
0x180076133  cmp     edx, 0Dh
0x180076136  jnz     short loc_180076140
0x180076138  mov     r9d, 0F013Fh
0x18007613e  jmp     short loc_180076152
0x180076140  cmp     edx, 0Ch
0x180076143  mov     eax, 0F023Fh
0x180076148  mov     r9d, 0F003Fh
0x18007614e  cmovz   r9d, eax; samDesired
0x180076152  lea     rbx, [rcx+10h]
0x180076156  xor     r8d, r8d; ulOptions
0x180076159  lea     rax, [rbp+hKey]
0x18007615d  mov     rdx, rbx; lpSubKey
0x180076160  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076167  mov     [rsp+60h+phkResult], rax; phkResult
0x18007616c  call    cs:__imp_RegOpenKeyExW
0x180076173  nop     dword ptr [rax+rax+00h]
0x180076178  test    eax, eax
0x18007617a  jz      short loc_1800761C7
0x18007617c  mov     [rsp+60h+lpcbMaxSubKeyLen], rbx
0x180076181  lea     r9, aErrorDOpeningS; "Error %d opening [%s]\n"
0x180076188  mov     r8d, 3B9h
0x18007618e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076195  mov     dword ptr [rsp+60h+phkResult], eax
0x180076199  mov     ecx, 5
0x18007619e  call    dprintf
0x1800761a3  mov     rcx, [rbp+hKey]; hKey
0x1800761a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800761ab  jz      short loc_1800761B9
0x1800761ad  call    cs:__imp_RegCloseKey
0x1800761b4  nop     dword ptr [rax+rax+00h]
0x1800761b9  xor     eax, eax
0x1800761bb  add     rsp, 60h
0x1800761bf  pop     r14
0x1800761c1  pop     rdi
0x1800761c2  pop     rsi
0x1800761c3  pop     rbx
0x1800761c4  pop     rbp
0x1800761c5  retn
0x1800761c7  mov     rcx, [rbp+hKey]; hKey
0x1800761cb  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800761cf  mov     [rsp+60h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800761d4  xor     r9d, r9d; lpReserved
0x1800761d7  mov     [rsp+60h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800761dc  xor     r8d, r8d; lpcchClass
0x1800761df  mov     [rsp+60h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800761e4  xor     edx, edx; lpClass
0x1800761e6  mov     [rsp+60h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800761eb  mov     [rsp+60h+lpcValues], r14; lpcValues
0x1800761f0  mov     [rsp+60h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800761f5  mov     [rsp+60h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800761fa  lea     rax, [rbp+cSubKeys]
0x1800761fe  mov     [rsp+60h+phkResult], rax; lpcSubKeys
0x180076203  call    cs:__imp_RegQueryInfoKeyW
0x18007620a  nop     dword ptr [rax+rax+00h]
0x18007620f  test    eax, eax
0x180076211  jz      short loc_18007622A
0x180076213  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x180076218  lea     r9, aErrorDQuerying; "Error %d querying key [%s]\n"
0x18007621f  mov     r8d, 3CBh
0x180076225  jmp     loc_18007618E
0x18007622a  cmp     [rbp+cSubKeys], r14d
0x18007622e  jz      loc_1800761A3
0x180076234  mov     edx, [rbp+cbMaxSubKeyLen]
0x180076237  mov     r8, rsi
0x18007623a  mov     rcx, rdi; Src
0x18007623d  call    AllocateKeyInfo
0x180076242  mov     rbx, rax
0x180076245  test    rax, rax
0x180076248  jnz     short loc_18007626D
0x18007624a  call    cs:__imp_GetLastError
0x180076251  nop     dword ptr [rax+rax+00h]
0x180076256  lea     r9, aErrorDNotEnoug; "Error [%d] not enough memory [%s]\n"
0x18007625d  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x180076262  mov     r8d, 3D8h
0x180076268  jmp     loc_18007618E
0x18007626d  mov     eax, [rax+28h]
0x180076270  lea     r9, [rbp+cbMaxSubKeyLen]; lpcchName
0x180076274  sub     eax, [rbx+20h]
0x180076277  xor     edx, edx; dwIndex
0x180076279  mov     [rbp+cbMaxSubKeyLen], eax
0x18007627c  mov     ecx, [rbx+20h]
0x18007627f  mov     rax, [rbx+18h]
0x180076283  mov     [rsp+60h+lpcValues], r14; lpftLastWriteTime
0x180076288  mov     [rsp+60h+lpcbMaxClassLen], r14; lpcchClass
0x18007628d  mov     [rsp+60h+lpcbMaxSubKeyLen], r14; lpClass
0x180076292  lea     r8, [rax+rcx*2]; lpName
0x180076296  mov     [rsp+60h+phkResult], r14; lpReserved
0x18007629b  mov     rcx, [rbp+hKey]; hKey
0x18007629f  call    cs:__imp_RegEnumKeyExW
0x1800762a6  nop     dword ptr [rax+rax+00h]
0x1800762ab  test    eax, eax
0x1800762ad  jz      short loc_1800762E3
0x1800762af  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x1800762b4  lea     r9, aErrorDEnumerat_0; "Error %d enumerating [%s]\n"
0x1800762bb  mov     r8d, 3E9h
0x1800762c1  mov     dword ptr [rsp+60h+phkResult], eax
0x1800762c5  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800762cc  mov     ecx, 5
0x1800762d1  call    dprintf
0x1800762d6  mov     rcx, rbx; hMem
0x1800762d9  call    FreeKeyInfo
0x1800762de  jmp     loc_1800761A3
0x1800762e3  mov     eax, [rbp+cbMaxSubKeyLen]
0x1800762e6  mov     [rbx+24h], eax
0x1800762e9  mov     rax, [rbp+hKey]
0x1800762ed  mov     [rbx+10h], rax
0x1800762f1  mov     rax, rbx
0x1800762f4  jmp     loc_1800761BB
```
