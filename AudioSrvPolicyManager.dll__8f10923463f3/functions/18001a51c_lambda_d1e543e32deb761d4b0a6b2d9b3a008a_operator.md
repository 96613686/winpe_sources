# _lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()

- ea: `0x18001a51c`
- end: `0x18001a72e`
- name: `_lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a4d0`

## callees

- `0x18001a51c`
- `0x18001ab34`
- `0x180025db0`
- `0x1800272f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a68f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a68f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a5ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a62f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a5ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a62f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a66f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a70b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a5ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a66f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a70b`

## string_xrefs

- `0x18001a551`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_d1e543e32deb761d4b0a6b2d9b3a008a_::operator()(__int64 a1)
{
  int v2; // ebx
  HKEY v3; // rbx
  WCHAR *v4; // rbx
  LSTATUS v5; // eax
  unsigned int v6; // edi
  HKEY v7; // rcx
  LSTATUS v9; // eax
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  char v13; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         L"Configs");
  if ( v2 < 0 )
  {
    if ( lpSubKey[0] )
      CoTaskMemFree((LPVOID)lpSubKey[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v2;
  }
  else
  {
    v3 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
      RegCloseKey(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
    }
    hKey = 0;
    v4 = (WCHAR *)lpSubKey[0];
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 )
        CoTaskMemFree(v4);
      v7 = hKey;
      if ( !hKey )
        return v6;
      goto LABEL_10;
    }
    phkResult = 0;
    v9 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, &phkResult);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v4 )
        CoTaskMemFree(v4);
      v7 = hKey;
      if ( !hKey )
        return v6;
LABEL_10:
      RegCloseKey(v7);
      return v6;
    }
    **(_BYTE **)(a1 + 16) = 1;
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v4 )
      CoTaskMemFree(v4);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x18001a51c  mov     [rsp-18h+arg_18], rbx
0x18001a521  push    rbp
0x18001a522  push    rsi
0x18001a523  push    rdi
0x18001a524  mov     rbp, rsp
0x18001a527  sub     rsp, 50h
0x18001a52b  mov     rsi, rcx
0x18001a52e  mov     [rbp+hKey], 0
0x18001a536  mov     [rbp+lpSubKey], 0
0x18001a53e  mov     [rbp+var_18], 0
0x18001a546  mov     [rbp+var_10], 0
0x18001a54e  mov     r8, [rcx]
0x18001a551  lea     r9, aConfigs; "Configs"
0x18001a558  mov     r8, [r8+8]
0x18001a55c  lea     rdx, aSS; "%s\\%s"
0x18001a563  lea     rcx, [rbp+lpSubKey]
0x18001a567  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a56c  mov     ebx, eax
0x18001a56e  test    eax, eax
0x18001a570  js      loc_18001A6A6
0x18001a576  mov     rbx, [rbp+hKey]
0x18001a57a  test    rbx, rbx
0x18001a57d  jnz     loc_18001A6DE
0x18001a583  mov     [rbp+hKey], 0
0x18001a58b  lea     rax, [rbp+hKey]
0x18001a58f  mov     [rsp+50h+phkResult], rax; phkResult
0x18001a594  mov     r9d, 20019h; samDesired
0x18001a59a  xor     r8d, r8d; ulOptions
0x18001a59d  mov     rbx, [rbp+lpSubKey]
0x18001a5a1  mov     rdx, rbx; lpSubKey
0x18001a5a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a5ab  call    cs:__imp_RegOpenKeyExW
0x18001a5b1  mov     edi, eax
0x18001a5b3  test    eax, eax
0x18001a5b5  jz      short loc_18001A5F5
0x18001a5b7  jle     short loc_18001A5C2
0x18001a5b9  movzx   edi, ax
0x18001a5bc  or      edi, 80070000h
0x18001a5c2  test    rbx, rbx
0x18001a5c5  jz      short loc_18001A5D1
0x18001a5c7  mov     rcx, rbx; pv
0x18001a5ca  call    cs:__imp_CoTaskMemFree
0x18001a5d0  nop
0x18001a5d1  mov     rcx, [rbp+hKey]; hKey
0x18001a5d5  test    rcx, rcx
0x18001a5d8  jnz     short loc_18001A5EC
0x18001a5da  mov     eax, edi
0x18001a5dc  mov     rbx, [rsp+50h+arg_18]
0x18001a5e4  add     rsp, 50h
0x18001a5e8  pop     rdi
0x18001a5e9  pop     rsi
0x18001a5ea  pop     rbp
0x18001a5eb  retn
0x18001a5ec  call    cs:__imp_RegCloseKey
0x18001a5f2  nop
0x18001a5f3  jmp     short loc_18001A5DA
0x18001a5f5  mov     [rbp+arg_8], 0
0x18001a5fd  mov     rdi, [rbp+arg_8]
0x18001a601  test    rdi, rdi
0x18001a604  jnz     loc_18001A6FF
0x18001a60a  mov     [rbp+arg_8], 0
0x18001a612  mov     rdx, [rsi+8]
0x18001a616  lea     rax, [rbp+arg_8]
0x18001a61a  mov     [rsp+50h+phkResult], rax; phkResult
0x18001a61f  mov     r9d, 20019h; samDesired
0x18001a625  xor     r8d, r8d; ulOptions
0x18001a628  mov     rdx, [rdx]; lpSubKey
0x18001a62b  mov     rcx, [rbp+hKey]; hKey
0x18001a62f  call    cs:__imp_RegOpenKeyExW
0x18001a635  mov     edi, eax
0x18001a637  test    eax, eax
0x18001a639  jz      short loc_18001A677
0x18001a63b  jg      loc_18001A720
0x18001a641  mov     rcx, [rbp+arg_8]; hKey
0x18001a645  test    rcx, rcx
0x18001a648  jnz     short loc_18001A667
0x18001a64a  test    rbx, rbx
0x18001a64d  jz      short loc_18001A659
0x18001a64f  mov     rcx, rbx; pv
0x18001a652  call    cs:__imp_CoTaskMemFree
0x18001a658  nop
0x18001a659  mov     rcx, [rbp+hKey]; hKey
0x18001a65d  test    rcx, rcx
0x18001a660  jnz     short loc_18001A66F
0x18001a662  jmp     loc_18001A5DA
0x18001a667  call    cs:__imp_RegCloseKey
0x18001a66d  jmp     short loc_18001A64A
0x18001a66f  call    cs:__imp_RegCloseKey
0x18001a675  jmp     short loc_18001A662
0x18001a677  mov     rax, [rsi+10h]
0x18001a67b  mov     byte ptr [rax], 1
0x18001a67e  mov     rcx, [rbp+arg_8]; hKey
0x18001a682  test    rcx, rcx
0x18001a685  jnz     short loc_18001A6C6
0x18001a687  test    rbx, rbx
0x18001a68a  jz      short loc_18001A696
0x18001a68c  mov     rcx, rbx; pv
0x18001a68f  call    cs:__imp_CoTaskMemFree
0x18001a695  nop
0x18001a696  mov     rcx, [rbp+hKey]; hKey
0x18001a69a  test    rcx, rcx
0x18001a69d  jnz     short loc_18001A6CE
0x18001a69f  xor     eax, eax
0x18001a6a1  jmp     loc_18001A5DC
0x18001a6a6  mov     rcx, [rbp+lpSubKey]; pv
0x18001a6aa  test    rcx, rcx
0x18001a6ad  jz      short loc_18001A6B6
0x18001a6af  call    cs:__imp_CoTaskMemFree
0x18001a6b5  nop
0x18001a6b6  mov     rcx, [rbp+hKey]; hKey
0x18001a6ba  test    rcx, rcx
0x18001a6bd  jnz     short loc_18001A6D6
0x18001a6bf  mov     eax, ebx
0x18001a6c1  jmp     loc_18001A5DC
0x18001a6c6  call    cs:__imp_RegCloseKey
0x18001a6cc  jmp     short loc_18001A687
0x18001a6ce  call    cs:__imp_RegCloseKey
0x18001a6d4  jmp     short loc_18001A69F
0x18001a6d6  call    cs:__imp_RegCloseKey
0x18001a6dc  jmp     short loc_18001A6BF
0x18001a6de  lea     rcx, [rbp+arg_10]; this
0x18001a6e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a6e7  mov     rcx, rbx; hKey
0x18001a6ea  call    cs:__imp_RegCloseKey
0x18001a6f0  lea     rcx, [rbp+arg_10]; this
0x18001a6f4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a6f9  nop
0x18001a6fa  jmp     loc_18001A583
0x18001a6ff  lea     rcx, [rbp+arg_10]; this
0x18001a703  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a708  mov     rcx, rdi; hKey
0x18001a70b  call    cs:__imp_RegCloseKey
0x18001a711  lea     rcx, [rbp+arg_10]; this
0x18001a715  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a71a  nop
0x18001a71b  jmp     loc_18001A60A
0x18001a720  movzx   edi, ax
0x18001a723  or      edi, 80070000h
0x18001a729  jmp     loc_18001A641
```
