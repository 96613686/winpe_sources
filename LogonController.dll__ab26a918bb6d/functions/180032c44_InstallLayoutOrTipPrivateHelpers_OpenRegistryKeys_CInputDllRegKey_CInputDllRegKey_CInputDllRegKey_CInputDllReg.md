# InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,bool)

- ea: `0x180032c44`
- end: `0x18003316d`
- name: `?OpenRegistryKeys@InstallLayoutOrTipPrivateHelpers@@SA_NAEAVCInputDllRegKey@@00000000_N@Z`
- size: `1321`
- prototype: `bool __fastcall(struct CInputDllRegKey *this, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *, HKEY *, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *, DWORD lpdwDisposition)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180096a78`

## callees

- `0x180007fc0`
- `0x180032c44`
- `0x180033180`
- `0x1800332d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032cea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032d55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032f6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033074`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032cea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032d55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032f6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033074`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800330df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032cd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032dde`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032e3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032efa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032fb5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033059`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800330b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032cd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032dde`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032e3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032efa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032fb5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033059`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800330b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032c92`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032d98`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003300f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032c92`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032d98`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003300f`

## pseudocode

```c
bool __fastcall InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(
        struct CInputDllRegKey *this,
        struct CInputDllRegKey *a2,
        struct CInputDllRegKey *a3,
        struct CInputDllRegKey *a4,
        HKEY *a5,
        struct CInputDllRegKey *a6,
        struct CInputDllRegKey *a7,
        struct CInputDllRegKey *a8,
        struct CInputDllRegKey *a9,
        DWORD lpdwDisposition)
{
  const WCHAR *v10; // r12
  HKEY v15; // r13
  LSTATUS v16; // eax
  LSTATUS v17; // ebx
  HKEY v18; // rcx
  LSTATUS v19; // eax
  char v20; // r13
  const WCHAR *v21; // rdi
  bool v22; // zf
  HKEY v23; // r12
  LSTATUS v24; // eax
  LSTATUS v25; // ebx
  HKEY v26; // rcx
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  HKEY v29; // rcx
  LSTATUS v30; // edx
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  HKEY v33; // rcx
  LSTATUS v34; // edx
  LSTATUS v35; // eax
  HKEY v36; // rbx
  LSTATUS v37; // eax
  unsigned __int16 *v38; // r9
  LSTATUS v39; // edi
  struct CInputDllRegKey *v40; // rbx
  HKEY v41; // rcx
  LSTATUS v42; // eax
  unsigned __int16 *v43; // r9
  unsigned __int16 *v44; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-58h]
  REGSAM samDesired; // [rsp+28h] [rbp-50h]
  REGSAM samDesireda; // [rsp+28h] [rbp-50h]
  REGSAM samDesiredb; // [rsp+28h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // [rsp+30h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributesa; // [rsp+30h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributesb; // [rsp+30h] [rbp-48h]
  unsigned int *v55; // [rsp+38h] [rbp-40h]
  unsigned int *v56; // [rsp+38h] [rbp-40h]
  unsigned int *v57; // [rsp+38h] [rbp-40h]
  DWORD dwDisposition; // [rsp+50h] [rbp-28h] BYREF
  HKEY v59; // [rsp+58h] [rbp-20h] BYREF
  HKEY phkResult[3]; // [rsp+60h] [rbp-18h] BYREF

  v10 = L"TextInputDrt\\Keyboard Layout\\Preload";
  dwDisposition = 0;
  v59 = 0;
  phkResult[0] = 0;
  if ( !(_BYTE)lpdwDisposition )
    v10 = L"Keyboard Layout\\Preload";
  v15 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, phkResult) )
    v15 = phkResult[0];
  v16 = RegCreateKeyExW(v15, v10, 0, 0, 0, 0x2001Fu, 0, &v59, &dwDisposition);
  v17 = v16;
  if ( !v16 )
  {
    v18 = (HKEY)*((_QWORD *)this + 1);
    if ( !v18 )
    {
LABEL_12:
      *((_QWORD *)this + 1) = v59;
      goto LABEL_13;
    }
    v19 = RegCloseKey(v18);
LABEL_11:
    v17 = v19;
    goto LABEL_12;
  }
  if ( v16 == 5 )
  {
    v17 = RegCreateKeyExW(v15, v10, 0, 0, 4u, 0x2001Fu, 0, &v59, &dwDisposition);
    if ( !v17 )
    {
      v19 = CInputDllRegKey::Close(this);
      goto LABEL_11;
    }
  }
LABEL_13:
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  if ( v17 )
    return 0;
  v20 = lpdwDisposition;
  v21 = L"TextInputDrt\\Keyboard Layout\\Substitutes";
  v22 = (_BYTE)lpdwDisposition == 0;
  lpdwDisposition = 0;
  v59 = 0;
  phkResult[0] = 0;
  if ( v22 )
    v21 = L"Keyboard Layout\\Substitutes";
  v23 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, phkResult) )
    v23 = phkResult[0];
  v24 = RegCreateKeyExW(v23, v21, 0, 0, 0, 0x2001Fu, 0, &v59, &lpdwDisposition);
  v25 = v24;
  if ( !v24 )
  {
    v26 = (HKEY)*((_QWORD *)a2 + 1);
    if ( !v26 )
    {
LABEL_27:
      *((_QWORD *)a2 + 1) = v59;
      goto LABEL_28;
    }
    v27 = RegCloseKey(v26);
LABEL_26:
    v25 = v27;
    goto LABEL_27;
  }
  if ( v24 == 5 )
  {
    v25 = RegCreateKeyExW(v23, v21, 0, 0, 4u, 0x2001Fu, 0, &v59, &lpdwDisposition);
    if ( !v25 )
    {
      v27 = CInputDllRegKey::Close(a2);
      goto LABEL_26;
    }
  }
LABEL_28:
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  if ( v25 )
    return 0;
  v59 = 0;
  v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Keyboard Layouts", 0, 0x20019u, &v59);
  if ( !v28 )
  {
    v29 = (HKEY)*((_QWORD *)a3 + 1);
    v30 = 0;
    if ( !v29 )
    {
LABEL_38:
      *((_QWORD *)a3 + 1) = v59;
LABEL_39:
      if ( !v30 )
        goto LABEL_41;
      goto LABEL_40;
    }
    v31 = RegCloseKey(v29);
LABEL_37:
    v30 = v31;
    goto LABEL_38;
  }
  if ( v28 == 5 )
  {
    lpdwDisposition = 0;
    v30 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Keyboard Layouts",
            0,
            0,
            4u,
            0x20019u,
            0,
            &v59,
            &lpdwDisposition);
    if ( v30 )
      goto LABEL_39;
    v31 = CInputDllRegKey::Close(a3);
    goto LABEL_37;
  }
LABEL_40:
  if ( CInputDllRegKey::Open(a3, HKEY_LOCAL_MACHINE, L"System\\ControlSet001\\Control\\Keyboard Layouts", 0x20019u) )
    return 0;
LABEL_41:
  v59 = 0;
  v32 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Nls\\Locale", 0, 0x20019u, &v59);
  if ( !v32 )
  {
    v33 = (HKEY)*((_QWORD *)a4 + 1);
    v34 = 0;
    if ( !v33 )
    {
LABEL_48:
      *((_QWORD *)a4 + 1) = v59;
LABEL_49:
      if ( !v34 )
        goto LABEL_51;
      goto LABEL_50;
    }
    v35 = RegCloseKey(v33);
LABEL_47:
    v34 = v35;
    goto LABEL_48;
  }
  if ( v32 == 5 )
  {
    lpdwDisposition = 0;
    v34 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Nls\\Locale",
            0,
            0,
            4u,
            0x20019u,
            0,
            &v59,
            &lpdwDisposition);
    if ( v34 )
      goto LABEL_49;
    v35 = CInputDllRegKey::Close(a4);
    goto LABEL_47;
  }
LABEL_50:
  if ( CInputDllRegKey::Open(a4, HKEY_LOCAL_MACHINE, L"System\\ControlSet001\\Control\\Nls\\Locale", 0x20019u) )
    return 0;
LABEL_51:
  lpdwDisposition = 0;
  v59 = 0;
  phkResult[0] = 0;
  v36 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, phkResult) )
    v36 = phkResult[0];
  v37 = RegCreateKeyExW(v36, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 0, 0x2001Fu, 0, &v59, &lpdwDisposition);
  v39 = v37;
  if ( !v37 )
  {
    v40 = (struct CInputDllRegKey *)a5;
    v39 = 0;
    v41 = a5[1];
    if ( !v41 )
    {
LABEL_60:
      *((_QWORD *)v40 + 1) = v59;
      goto LABEL_61;
    }
    v42 = RegCloseKey(v41);
LABEL_59:
    v39 = v42;
    goto LABEL_60;
  }
  if ( v37 == 5 )
  {
    v39 = RegCreateKeyExW(v36, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 4u, 0x2001Fu, 0, &v59, &lpdwDisposition);
    if ( !v39 )
    {
      v40 = (struct CInputDllRegKey *)a5;
      v42 = CInputDllRegKey::Close((CInputDllRegKey *)a5);
      goto LABEL_59;
    }
  }
LABEL_61:
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  if ( !v39
    && !(unsigned int)CInputDllRegKey::Create(
                        a6,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\CTF\\HiddenDummyLayouts",
                        v38,
                        dwOptions,
                        samDesired,
                        lpSecurityAttributes,
                        v55)
    && (!CInputDllRegKey::Open(a7, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\CTF\\TIP", 0x20019u) || v20)
    && !(unsigned int)CInputDllRegKey::Create(
                        a8,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\CTF\\SortOrder\\Language",
                        v43,
                        dwOptionsa,
                        samDesireda,
                        lpSecurityAttributesa,
                        v56) )
  {
    return (unsigned int)CInputDllRegKey::Create(
                           a9,
                           HKEY_CURRENT_USER,
                           L"Software\\Microsoft\\CTF\\SortOrder\\AssemblyItem",
                           v44,
                           dwOptionsb,
                           samDesiredb,
                           lpSecurityAttributesb,
                           v57) == 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180032c44  push    rbp
0x180032c46  push    rbx
0x180032c47  push    rsi
0x180032c48  push    rdi
0x180032c49  push    r12
0x180032c4b  push    r13
0x180032c4d  push    r14
0x180032c4f  push    r15
0x180032c51  mov     rbp, rsp
0x180032c54  sub     rsp, 78h
0x180032c58  xor     ebx, ebx
0x180032c5a  lea     rax, ?c_szPreload@@3QBGB; "Keyboard Layout\\Preload"
0x180032c61  cmp     byte ptr [rbp+arg_48], bl
0x180032c67  lea     r12, ?c_szPreloadTest@@3QBGB; "TextInputDrt\\Keyboard Layout\\Preload"
0x180032c6e  mov     rsi, rdx
0x180032c71  mov     [rbp+dwDisposition], ebx
0x180032c74  mov     rdi, rcx
0x180032c77  mov     [rbp+var_20], rbx
0x180032c7b  lea     rdx, [rbp+phkResult]; phkResult
0x180032c7f  mov     [rbp+phkResult], rbx
0x180032c83  mov     ecx, 2001Fh; samDesired
0x180032c88  cmovz   r12, rax
0x180032c8c  mov     r15, r9
0x180032c8f  mov     r14, r8
0x180032c92  call    cs:__imp_RegOpenCurrentUser
0x180032c98  mov     r13, 0FFFFFFFF80000001h
0x180032c9f  mov     rdx, r12; lpSubKey
0x180032ca2  test    eax, eax
0x180032ca4  lea     rax, [rbp+dwDisposition]
0x180032ca8  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032cad  lea     rax, [rbp+var_20]
0x180032cb1  cmovz   r13, [rbp+phkResult]
0x180032cb6  xor     r9d, r9d; lpClass
0x180032cb9  mov     [rsp+78h+var_40], rax; phkResult
0x180032cbe  xor     r8d, r8d; Reserved
0x180032cc1  mov     [rsp+78h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180032cc6  mov     rcx, r13; hKey
0x180032cc9  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180032cd1  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x180032cd5  call    cs:__imp_RegCreateKeyExW
0x180032cdb  mov     ebx, eax
0x180032cdd  test    eax, eax
0x180032cdf  jnz     short loc_180032CF2
0x180032ce1  mov     rcx, [rdi+8]; hKey
0x180032ce5  test    rcx, rcx
0x180032ce8  jz      short loc_180032D44
0x180032cea  call    cs:__imp_RegCloseKey
0x180032cf0  jmp     short loc_180032D42
0x180032cf2  cmp     eax, 5
0x180032cf5  jnz     short loc_180032D4C
0x180032cf7  lea     rax, [rbp+dwDisposition]
0x180032cfb  xor     r9d, r9d; lpClass
0x180032cfe  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032d03  xor     r8d, r8d; Reserved
0x180032d06  lea     rax, [rbp+var_20]
0x180032d0a  mov     rdx, r12; lpSubKey
0x180032d0d  mov     [rsp+78h+var_40], rax; phkResult
0x180032d12  mov     rcx, r13; hKey
0x180032d15  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032d1e  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180032d26  mov     [rsp+78h+dwOptions], 4; dwOptions
0x180032d2e  call    cs:__imp_RegCreateKeyExW
0x180032d34  mov     ebx, eax
0x180032d36  test    eax, eax
0x180032d38  jnz     short loc_180032D4C
0x180032d3a  mov     rcx, rdi; this
0x180032d3d  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180032d42  mov     ebx, eax
0x180032d44  mov     rax, [rbp+var_20]
0x180032d48  mov     [rdi+8], rax
0x180032d4c  mov     rcx, [rbp+phkResult]; hKey
0x180032d50  test    rcx, rcx
0x180032d53  jz      short loc_180032D5B
0x180032d55  call    cs:__imp_RegCloseKey
0x180032d5b  test    ebx, ebx
0x180032d5d  jnz     loc_18003315A
0x180032d63  mov     r13b, byte ptr [rbp+arg_48]
0x180032d6a  lea     rax, ?c_szSubstitutes@@3QBGB; "Keyboard Layout\\Substitutes"
0x180032d71  xor     ebx, ebx
0x180032d73  lea     rdi, ?c_szSubstitutesTest@@3QBGB; "TextInputDrt\\Keyboard Layout\\Substitu"...
0x180032d7a  test    r13b, r13b
0x180032d7d  mov     [rbp+arg_48], ebx
0x180032d83  lea     rdx, [rbp+phkResult]; phkResult
0x180032d87  mov     [rbp+var_20], rbx
0x180032d8b  mov     ecx, 2001Fh; samDesired
0x180032d90  mov     [rbp+phkResult], rbx
0x180032d94  cmovz   rdi, rax
0x180032d98  call    cs:__imp_RegOpenCurrentUser
0x180032d9e  mov     r12, 0FFFFFFFF80000001h
0x180032da5  mov     rdx, rdi; lpSubKey
0x180032da8  test    eax, eax
0x180032daa  lea     rax, [rbp+arg_48]
0x180032db1  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032db6  lea     rax, [rbp+var_20]
0x180032dba  cmovz   r12, [rbp+phkResult]
0x180032dbf  xor     r9d, r9d; lpClass
0x180032dc2  mov     [rsp+78h+var_40], rax; phkResult
0x180032dc7  xor     r8d, r8d; Reserved
0x180032dca  mov     [rsp+78h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180032dcf  mov     rcx, r12; hKey
0x180032dd2  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180032dda  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x180032dde  call    cs:__imp_RegCreateKeyExW
0x180032de4  mov     ebx, eax
0x180032de6  test    eax, eax
0x180032de8  jnz     short loc_180032DFB
0x180032dea  mov     rcx, [rsi+8]; hKey
0x180032dee  test    rcx, rcx
0x180032df1  jz      short loc_180032E50
0x180032df3  call    cs:__imp_RegCloseKey
0x180032df9  jmp     short loc_180032E4E
0x180032dfb  cmp     eax, 5
0x180032dfe  jnz     short loc_180032E58
0x180032e00  lea     rax, [rbp+arg_48]
0x180032e07  xor     r9d, r9d; lpClass
0x180032e0a  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032e0f  xor     r8d, r8d; Reserved
0x180032e12  lea     rax, [rbp+var_20]
0x180032e16  mov     rdx, rdi; lpSubKey
0x180032e19  mov     [rsp+78h+var_40], rax; phkResult
0x180032e1e  mov     rcx, r12; hKey
0x180032e21  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032e2a  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180032e32  mov     [rsp+78h+dwOptions], 4; dwOptions
0x180032e3a  call    cs:__imp_RegCreateKeyExW
0x180032e40  mov     ebx, eax
0x180032e42  test    eax, eax
0x180032e44  jnz     short loc_180032E58
0x180032e46  mov     rcx, rsi; this
0x180032e49  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180032e4e  mov     ebx, eax
0x180032e50  mov     rax, [rbp+var_20]
0x180032e54  mov     [rsi+8], rax
0x180032e58  mov     rcx, [rbp+phkResult]; hKey
0x180032e5c  xor     esi, esi
0x180032e5e  test    rcx, rcx
0x180032e61  jz      short loc_180032E69
0x180032e63  call    cs:__imp_RegCloseKey
0x180032e69  test    ebx, ebx
0x180032e6b  jnz     loc_18003315A
0x180032e71  lea     rax, [rbp+var_20]
0x180032e75  mov     [rbp+var_20], rsi
0x180032e79  mov     r12d, 20019h
0x180032e7f  mov     qword ptr [rsp+78h+dwOptions], rax; phkResult
0x180032e84  mov     rbx, 0FFFFFFFF80000002h
0x180032e8b  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Key"...
0x180032e92  mov     r9d, r12d; samDesired
0x180032e95  mov     rcx, rbx; hKey
0x180032e98  xor     r8d, r8d; ulOptions
0x180032e9b  call    cs:__imp_RegOpenKeyExW
0x180032ea1  test    eax, eax
0x180032ea3  jnz     short loc_180032EB8
0x180032ea5  mov     rcx, [r14+8]; hKey
0x180032ea9  mov     edx, esi
0x180032eab  test    rcx, rcx
0x180032eae  jz      short loc_180032F10
0x180032eb0  call    cs:__imp_RegCloseKey
0x180032eb6  jmp     short loc_180032F0E
0x180032eb8  cmp     eax, 5
0x180032ebb  jnz     short loc_180032F1C
0x180032ebd  lea     rax, [rbp+arg_48]
0x180032ec4  mov     [rbp+arg_48], esi
0x180032eca  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032ecf  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Key"...
0x180032ed6  lea     rax, [rbp+var_20]
0x180032eda  xor     r9d, r9d; lpClass
0x180032edd  mov     [rsp+78h+var_40], rax; phkResult
0x180032ee2  xor     r8d, r8d; Reserved
0x180032ee5  mov     [rsp+78h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180032eea  mov     rcx, rbx; hKey
0x180032eed  mov     [rsp+78h+samDesired], r12d; samDesired
0x180032ef2  mov     [rsp+78h+dwOptions], 4; dwOptions
0x180032efa  call    cs:__imp_RegCreateKeyExW
0x180032f00  mov     edx, eax
0x180032f02  test    eax, eax
0x180032f04  jnz     short loc_180032F18
0x180032f06  mov     rcx, r14; this
0x180032f09  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180032f0e  mov     edx, eax
0x180032f10  mov     rax, [rbp+var_20]
0x180032f14  mov     [r14+8], rax
0x180032f18  test    edx, edx
0x180032f1a  jz      short loc_180032F39
0x180032f1c  mov     r9d, r12d; unsigned int
0x180032f1f  lea     r8, aSystemControls; "System\\ControlSet001\\Control\\Keyboar"...
0x180032f26  mov     rdx, rbx; HKEY
0x180032f29  mov     rcx, r14; this
0x180032f2c  call    ?Open@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CInputDllRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180032f31  test    eax, eax
0x180032f33  jnz     loc_18003315A
0x180032f39  lea     rax, [rbp+var_20]
0x180032f3d  mov     [rbp+var_20], rsi
0x180032f41  mov     r9d, r12d; samDesired
0x180032f44  mov     qword ptr [rsp+78h+dwOptions], rax; phkResult
0x180032f49  xor     r8d, r8d; ulOptions
0x180032f4c  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Nls"...
0x180032f53  mov     rcx, rbx; hKey
0x180032f56  call    cs:__imp_RegOpenKeyExW
0x180032f5c  test    eax, eax
0x180032f5e  jnz     short loc_180032F73
0x180032f60  mov     rcx, [r15+8]; hKey
0x180032f64  mov     edx, esi
0x180032f66  test    rcx, rcx
0x180032f69  jz      short loc_180032FCB
0x180032f6b  call    cs:__imp_RegCloseKey
0x180032f71  jmp     short loc_180032FC9
0x180032f73  cmp     eax, 5
0x180032f76  jnz     short loc_180032FD7
0x180032f78  lea     rax, [rbp+arg_48]
0x180032f7f  mov     [rbp+arg_48], esi
0x180032f85  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180032f8a  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Nls"...
0x180032f91  lea     rax, [rbp+var_20]
0x180032f95  xor     r9d, r9d; lpClass
0x180032f98  mov     [rsp+78h+var_40], rax; phkResult
0x180032f9d  xor     r8d, r8d; Reserved
0x180032fa0  mov     [rsp+78h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180032fa5  mov     rcx, rbx; hKey
0x180032fa8  mov     [rsp+78h+samDesired], r12d; samDesired
0x180032fad  mov     [rsp+78h+dwOptions], 4; dwOptions
0x180032fb5  call    cs:__imp_RegCreateKeyExW
0x180032fbb  mov     edx, eax
0x180032fbd  test    eax, eax
0x180032fbf  jnz     short loc_180032FD3
0x180032fc1  mov     rcx, r15; this
0x180032fc4  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180032fc9  mov     edx, eax
0x180032fcb  mov     rax, [rbp+var_20]
0x180032fcf  mov     [r15+8], rax
0x180032fd3  test    edx, edx
0x180032fd5  jz      short loc_180032FF4
0x180032fd7  mov     r9d, r12d; unsigned int
0x180032fda  lea     r8, aSystemControls_0; "System\\ControlSet001\\Control\\Nls\\Lo"...
0x180032fe1  mov     rdx, rbx; HKEY
0x180032fe4  mov     rcx, r15; this
0x180032fe7  call    ?Open@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CInputDllRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180032fec  test    eax, eax
0x180032fee  jnz     loc_18003315A
0x180032ff4  mov     r15d, 2001Fh
0x180032ffa  mov     [rbp+arg_48], esi
0x180033000  mov     ecx, r15d; samDesired
0x180033003  mov     [rbp+var_20], rsi
0x180033007  lea     rdx, [rbp+phkResult]; phkResult
0x18003300b  mov     [rbp+phkResult], rsi
0x18003300f  call    cs:__imp_RegOpenCurrentUser
0x180033015  mov     rbx, 0FFFFFFFF80000001h
0x18003301c  lea     r14, ?c_szCtfTip@@3QBGB; "Software\\Microsoft\\CTF\\TIP"
0x180033023  test    eax, eax
0x180033025  mov     rdx, r14; lpSubKey
0x180033028  lea     rax, [rbp+arg_48]
0x18003302f  cmovz   rbx, [rbp+phkResult]
0x180033034  xor     r9d, r9d; lpClass
0x180033037  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18003303c  xor     r8d, r8d; Reserved
0x18003303f  lea     rax, [rbp+var_20]
0x180033043  mov     rcx, rbx; hKey
0x180033046  mov     [rsp+78h+var_40], rax; phkResult
0x18003304b  mov     [rsp+78h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180033050  mov     [rsp+78h+samDesired], r15d; samDesired
0x180033055  mov     [rsp+78h+dwOptions], esi; dwOptions
0x180033059  call    cs:__imp_RegCreateKeyExW
0x18003305f  mov     edi, eax
0x180033061  test    eax, eax
0x180033063  jnz     short loc_18003307C
0x180033065  mov     rbx, [rbp+arg_20]
0x180033069  mov     edi, esi
0x18003306b  mov     rcx, [rbx+8]; hKey
0x18003306f  test    rcx, rcx
0x180033072  jz      short loc_1800330CE
0x180033074  call    cs:__imp_RegCloseKey
0x18003307a  jmp     short loc_1800330CC
0x18003307c  cmp     eax, 5
0x18003307f  jnz     short loc_1800330D6
0x180033081  lea     rax, [rbp+arg_48]
0x180033088  xor     r9d, r9d; lpClass
0x18003308b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180033090  xor     r8d, r8d; Reserved
0x180033093  lea     rax, [rbp+var_20]
0x180033097  mov     rdx, r14; lpSubKey
0x18003309a  mov     [rsp+78h+var_40], rax; unsigned int *
0x18003309f  mov     rcx, rbx; hKey
0x1800330a2  mov     [rsp+78h+lpSecurityAttributes], rsi; struct _SECURITY_ATTRIBUTES *
0x1800330a7  mov     [rsp+78h+samDesired], r15d; unsigned int
0x1800330ac  mov     [rsp+78h+dwOptions], 4; unsigned int
0x1800330b4  call    cs:__imp_RegCreateKeyExW
0x1800330ba  mov     edi, eax
0x1800330bc  test    eax, eax
0x1800330be  jnz     short loc_1800330D6
0x1800330c0  mov     rbx, [rbp+arg_20]
0x1800330c4  mov     rcx, rbx; this
0x1800330c7  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800330cc  mov     edi, eax
0x1800330ce  mov     rax, [rbp+var_20]
0x1800330d2  mov     [rbx+8], rax
0x1800330d6  mov     rcx, [rbp+phkResult]; hKey
0x1800330da  test    rcx, rcx
0x1800330dd  jz      short loc_1800330E5
0x1800330df  call    cs:__imp_RegCloseKey
0x1800330e5  test    edi, edi
0x1800330e7  jnz     short loc_18003315A
  ... truncated ...
```
