# CInputDllRegKey::RecurseDeleteKey(ushort const *,int)

- ea: `0x180002820`
- end: `0x180002ad3`
- name: `?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z`
- size: `691`
- prototype: `__int64 __fastcall(CInputDllRegKey *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180002344`
- `0x180002820`
- `0x1800040e0`

## callees

- `0x180002820`
- `0x180007fc0`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800028a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800028a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002973`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002973`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800029aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002aa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002aa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002ac0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002ac0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800029c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800029c2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000291c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000291c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800029d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800029d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000295a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180002a15`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000295a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180002a15`

## pseudocode

```c
__int64 __fastcall CInputDllRegKey::RecurseDeleteKey(CInputDllRegKey *this, const unsigned __int16 *a2, int a3)
{
  HKEY v3; // rdi
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  void **v11; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h]
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  HKEY v15; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[256]; // [rsp+90h] [rbp-70h] BYREF

  v3 = (HKEY)*((_QWORD *)this + 1);
  v11 = &CInputDllRegKey::`vftable';
  hKey = 0;
  phkResult = 0;
  v15 = 0;
  if ( v3 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x2001Fu, &v15) )
    v3 = v15;
  v7 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v8 = v7;
  if ( !v7
    || v7 == 5
    && (dwDisposition = 0, (v8 = RegCreateKeyExW(v3, a2, 0, 0, 4u, 0x2001Fu, 0, &phkResult, &dwDisposition)) == 0) )
  {
    v8 = 0;
    hKey = phkResult;
  }
  if ( v15 )
    RegCloseKey(v15);
  if ( v8 )
  {
LABEL_21:
    v11 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v11);
  }
  else
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      SubKey[255] = 0;
      v8 = CInputDllRegKey::RecurseDeleteKey((CInputDllRegKey *)&v11, SubKey, 1);
      if ( v8 )
        goto LABEL_21;
    }
    if ( a3 )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v8 = RegDeleteKeyExW(*((HKEY *)this + 1), a2, 0, 0);
    }
    else
    {
      for ( cchName = 256; !RegEnumValueW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0); cchName = 256 )
      {
        v8 = RegDeleteValueW(hKey, SubKey);
        if ( v8 )
          break;
      }
    }
    v11 = &CInputDllRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v8;
}

```

## disassembly

```asm
0x180002820  mov     [rsp-8+arg_10], rbx
0x180002825  push    rbp
0x180002826  push    rsi
0x180002827  push    rdi
0x180002828  push    r12
0x18000282a  push    r13
0x18000282c  push    r14
0x18000282e  push    r15
0x180002830  lea     rbp, [rsp-1A0h]
0x180002838  sub     rsp, 2A0h
0x18000283f  mov     rax, cs:__security_cookie
0x180002846  xor     rax, rsp
0x180002849  mov     [rbp+1D0h+var_40], rax
0x180002850  mov     rdi, [rcx+8]
0x180002854  lea     r13, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x18000285b  xor     r12d, r12d
0x18000285e  mov     [rsp+2D0h+var_278], r13
0x180002863  mov     [rsp+2D0h+hKey], r12
0x180002868  mov     esi, r8d
0x18000286b  mov     [rsp+2D0h+var_268], r12
0x180002870  mov     r14, rdx
0x180002873  mov     [rsp+2D0h+var_258], r12
0x180002878  mov     r15, rcx
0x18000287b  cmp     rdi, 0FFFFFFFF80000001h
0x180002882  jz      loc_180002AB6
0x180002888  lea     rax, [rsp+2D0h+var_268]
0x18000288d  mov     r9d, 2001Fh; samDesired
0x180002893  xor     r8d, r8d; ulOptions
0x180002896  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18000289b  mov     rdx, r14; lpSubKey
0x18000289e  mov     rcx, rdi; hKey
0x1800028a1  call    cs:__imp_RegOpenKeyExW
0x1800028a7  mov     ebx, eax
0x1800028a9  test    eax, eax
0x1800028ab  jnz     loc_180002A5E
0x1800028b1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800028b6  mov     ebx, r12d
0x1800028b9  test    rcx, rcx
0x1800028bc  jz      short loc_1800028C6
0x1800028be  call    cs:__imp_RegCloseKey
0x1800028c4  mov     ebx, eax
0x1800028c6  mov     rax, [rsp+2D0h+var_268]
0x1800028cb  mov     [rsp+2D0h+hKey], rax
0x1800028d0  mov     rcx, [rsp+2D0h+var_258]; hKey
0x1800028d5  test    rcx, rcx
0x1800028d8  jz      short loc_1800028E0
0x1800028da  call    cs:__imp_RegCloseKey
0x1800028e0  test    ebx, ebx
0x1800028e2  jnz     loc_180002A4A
0x1800028e8  mov     qword ptr [rbp+1D0h+ftLastWriteTime.dwLowDateTime], r12
0x1800028ec  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800028f1  lea     rax, [rbp+1D0h+ftLastWriteTime]
0x1800028f5  mov     [rsp+2D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800028fa  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800028ff  mov     [rsp+2D0h+lpcchClass], r12; lpcchClass
0x180002904  lea     r8, [rbp+1D0h+SubKey]; lpName
0x180002908  mov     [rsp+2D0h+lpClass], r12; lpClass
0x18000290d  xor     edx, edx; dwIndex
0x18000290f  mov     [rsp+2D0h+phkResult], r12; lpReserved
0x180002914  mov     [rsp+2D0h+cchName], 100h
0x18000291c  call    cs:__imp_RegEnumKeyExW
0x180002922  test    eax, eax
0x180002924  jz      loc_180002A24
0x18000292a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18000292f  test    esi, esi
0x180002931  jnz     short loc_1800029A5
0x180002933  mov     [rsp+2D0h+lpftLastWriteTime], r12; lpcbData
0x180002938  lea     r9, [rsp+2D0h+cchName]; lpcchValueName
0x18000293d  mov     [rsp+2D0h+lpcchClass], r12; lpData
0x180002942  lea     r8, [rbp+1D0h+SubKey]; lpValueName
0x180002946  mov     [rsp+2D0h+lpClass], r12; lpType
0x18000294b  xor     edx, edx; dwIndex
0x18000294d  mov     [rsp+2D0h+phkResult], r12; lpReserved
0x180002952  mov     [rsp+2D0h+cchName], 100h
0x18000295a  call    cs:__imp_RegEnumValueW
0x180002960  test    eax, eax
0x180002962  jz      short loc_1800029D0
0x180002964  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180002969  mov     [rsp+2D0h+var_278], r13
0x18000296e  test    rcx, rcx
0x180002971  jz      short loc_180002979
0x180002973  call    cs:__imp_RegCloseKey
0x180002979  mov     eax, ebx
0x18000297b  mov     rcx, [rbp+1D0h+var_40]
0x180002982  xor     rcx, rsp; StackCookie
0x180002985  call    __security_check_cookie
0x18000298a  mov     rbx, [rsp+2D0h+arg_10]
0x180002992  add     rsp, 2A0h
0x180002999  pop     r15
0x18000299b  pop     r14
0x18000299d  pop     r13
0x18000299f  pop     r12
0x1800029a1  pop     rdi
0x1800029a2  pop     rsi
0x1800029a3  pop     rbp
0x1800029a4  retn
0x1800029a5  test    rcx, rcx
0x1800029a8  jz      short loc_1800029B5
0x1800029aa  call    cs:__imp_RegCloseKey
0x1800029b0  mov     [rsp+2D0h+hKey], r12
0x1800029b5  mov     rcx, [r15+8]; hKey
0x1800029b9  xor     r9d, r9d; Reserved
0x1800029bc  xor     r8d, r8d; samDesired
0x1800029bf  mov     rdx, r14; lpSubKey
0x1800029c2  call    cs:__imp_RegDeleteKeyExW
0x1800029c8  mov     ebx, eax
0x1800029ca  jmp     short loc_180002964
0x1800029d0  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800029d5  lea     rdx, [rbp+1D0h+SubKey]; lpValueName
0x1800029d9  call    cs:__imp_RegDeleteValueW
0x1800029df  mov     ebx, eax
0x1800029e1  test    eax, eax
0x1800029e3  jnz     loc_180002964
0x1800029e9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800029ee  lea     r9, [rsp+2D0h+cchName]; lpcchValueName
0x1800029f3  mov     [rsp+2D0h+lpftLastWriteTime], r12; lpcbData
0x1800029f8  lea     r8, [rbp+1D0h+SubKey]; lpValueName
0x1800029fc  mov     [rsp+2D0h+lpcchClass], r12; lpData
0x180002a01  xor     edx, edx; dwIndex
0x180002a03  mov     [rsp+2D0h+lpClass], r12; lpType
0x180002a08  mov     [rsp+2D0h+phkResult], r12; lpReserved
0x180002a0d  mov     [rsp+2D0h+cchName], 100h
0x180002a15  call    cs:__imp_RegEnumValueW
0x180002a1b  test    eax, eax
0x180002a1d  jz      short loc_1800029D0
0x180002a1f  jmp     loc_180002964
0x180002a24  mov     r8d, 1; int
0x180002a2a  mov     [rbp+1D0h+var_42], r12w
0x180002a32  lea     rdx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x180002a36  lea     rcx, [rsp+2D0h+var_278]; this
0x180002a3b  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x180002a40  mov     ebx, eax
0x180002a42  test    eax, eax
0x180002a44  jz      loc_1800028EC
0x180002a4a  lea     rcx, [rsp+2D0h+var_278]; this
0x180002a4f  mov     [rsp+2D0h+var_278], r13
0x180002a54  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180002a59  jmp     loc_180002979
0x180002a5e  cmp     eax, 5
0x180002a61  jnz     loc_1800028D0
0x180002a67  lea     rax, [rsp+2D0h+dwDisposition]
0x180002a6c  mov     [rsp+2D0h+dwDisposition], r12d
0x180002a71  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x180002a76  xor     r9d, r9d; lpClass
0x180002a79  lea     rax, [rsp+2D0h+var_268]
0x180002a7e  xor     r8d, r8d; Reserved
0x180002a81  mov     [rsp+2D0h+lpftLastWriteTime], rax; phkResult
0x180002a86  mov     rdx, r14; lpSubKey
0x180002a89  mov     [rsp+2D0h+lpcchClass], r12; lpSecurityAttributes
0x180002a8e  mov     rcx, rdi; hKey
0x180002a91  mov     dword ptr [rsp+2D0h+lpClass], 2001Fh; samDesired
0x180002a99  mov     dword ptr [rsp+2D0h+phkResult], 4; dwOptions
0x180002aa1  call    cs:__imp_RegCreateKeyExW
0x180002aa7  mov     ebx, eax
0x180002aa9  test    eax, eax
0x180002aab  jz      loc_1800028B1
0x180002ab1  jmp     loc_1800028D0
0x180002ab6  lea     rdx, [rsp+2D0h+var_258]; phkResult
0x180002abb  mov     ecx, 2001Fh; samDesired
0x180002ac0  call    cs:__imp_RegOpenCurrentUser
0x180002ac6  test    eax, eax
0x180002ac8  cmovz   rdi, [rsp+2D0h+var_258]
0x180002ace  jmp     loc_180002888
```
