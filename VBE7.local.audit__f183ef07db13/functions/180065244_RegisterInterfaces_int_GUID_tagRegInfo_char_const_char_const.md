# _RegisterInterfaces(int,_GUID *,tagRegInfo *,char const *,char const *)

- ea: `0x180065244`
- end: `0x180065566`
- name: `?_RegisterInterfaces@@YAJHPEAU_GUID@@PEAUtagRegInfo@@PEBD2@Z`
- size: `802`
- prototype: `__int64 __fastcall(int, struct _GUID *, struct tagRegInfo *, const char *, LPCSTR lpString)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800657b8`

## callees

- `0x180059120`
- `0x18005b0d4`
- `0x180060ed4`
- `0x180065244`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800652db`
- `KERNEL32!lstrlenA` at `0x1800652ef`
- `KERNEL32!lstrlenA` at `0x180065360`
- `KERNEL32!lstrlenA` at `0x180065390`
- `KERNEL32!lstrlenA` at `0x1800653bf`
- `KERNEL32!lstrlenA` at `0x180065437`
- `KERNEL32!lstrlenA` at `0x180065468`
- `KERNEL32!lstrlenA` at `0x1800654d2`
- `KERNEL32!lstrlenA` at `0x1800652db`
- `KERNEL32!lstrlenA` at `0x1800652ef`
- `KERNEL32!lstrlenA` at `0x180065360`
- `KERNEL32!lstrlenA` at `0x180065390`
- `KERNEL32!lstrlenA` at `0x1800653bf`
- `KERNEL32!lstrlenA` at `0x180065437`
- `KERNEL32!lstrlenA` at `0x180065468`
- `KERNEL32!lstrlenA` at `0x1800654d2`
- `KERNEL32!lstrcpyA` at `0x1800652c3`
- `KERNEL32!lstrcpyA` at `0x1800652c3`
- `USER32!wsprintfA` at `0x1800652b2`
- `USER32!wsprintfA` at `0x1800652b2`
- `ADVAPI32!RegSetValueA` at `0x18006537d`
- `ADVAPI32!RegSetValueA` at `0x1800653ac`
- `ADVAPI32!RegSetValueA` at `0x1800653db`
- `ADVAPI32!RegSetValueA` at `0x180065453`
- `ADVAPI32!RegSetValueA` at `0x1800654f0`
- `ADVAPI32!RegSetValueA` at `0x18006537d`
- `ADVAPI32!RegSetValueA` at `0x1800653ac`
- `ADVAPI32!RegSetValueA` at `0x1800653db`
- `ADVAPI32!RegSetValueA` at `0x180065453`
- `ADVAPI32!RegSetValueA` at `0x1800654f0`
- `ADVAPI32!RegSetValueExA` at `0x18006548e`
- `ADVAPI32!RegSetValueExA` at `0x18006548e`
- `ADVAPI32!RegCloseKey` at `0x1800654a3`
- `ADVAPI32!RegCloseKey` at `0x180065501`
- `ADVAPI32!RegCloseKey` at `0x18006552a`
- `ADVAPI32!RegCloseKey` at `0x18006553b`
- `ADVAPI32!RegCloseKey` at `0x1800654a3`
- `ADVAPI32!RegCloseKey` at `0x180065501`
- `ADVAPI32!RegCloseKey` at `0x18006552a`
- `ADVAPI32!RegCloseKey` at `0x18006553b`

## string_xrefs

- `0x18006539b`: `ProxyStubClsid`
- `0x1800653ca`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall _RegisterInterfaces(
        int a1,
        struct _GUID *a2,
        struct tagRegInfo *a3,
        const char *a4,
        LPCSTR lpString)
{
  int v6; // r9d
  int v8; // r8d
  unsigned int v10; // edi
  int v11; // esi
  int v12; // ebx
  int v13; // eax
  HKEY v14; // rbx
  HKEY v15; // rax
  DWORD cbData; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  HKEY v19; // rbx
  HKEY v20; // rax
  DWORD v21; // eax
  DWORD v22; // eax
  LSTATUS v23; // eax
  DWORD v24; // eax
  LSTATUS v25; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v28; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID *v29; // [rsp+40h] [rbp-C0h]
  CHAR String[32]; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Data[40]; // [rsp+68h] [rbp-98h] BYREF
  CHAR String1[256]; // [rsp+90h] [rbp-70h] BYREF

  v6 = *((unsigned __int16 *)a3 + 61);
  v8 = *((unsigned __int16 *)a3 + 60);
  v29 = a2;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v28 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v10 = 0;
  wsprintfA(String, "%x.%x", v8, v6);
  lstrcpyA(String1, szInterfaceSep);
  v11 = 0;
  if ( a1 <= 0 )
    return v10;
  while ( 1 )
  {
    v12 = 256 - lstrlenA(szInterfaceSep);
    v13 = lstrlenA(szInterfaceSep);
    StringFromGUID2Ansi(&v29[v11], &String1[v13], v12);
    if ( *((_DWORD *)a3 + 28) )
      RegDeleteSubKeys(HKEY_CLASSES_ROOT, String1);
    v14 = hKey;
    v10 = FastRegCreateKey(HKEY_CLASSES_ROOT, String1, &hKey);
    v15 = hKey;
    if ( v10 )
      v15 = v14;
    hKey = v15;
    if ( v10 )
      break;
    cbData = lstrlenA(*((LPCSTR *)a3 + 2));
    v10 = RegSetValueA(hKey, 0, 1u, *((LPCSTR *)a3 + 2), cbData);
    if ( v10 )
      break;
    v17 = lstrlenA(lpString);
    v10 = RegSetValueA(hKey, aProxystubclsid, 1u, lpString, v17);
    if ( v10 )
      break;
    v18 = lstrlenA(lpString);
    v10 = RegSetValueA(hKey, aProxystubclsid_0, 1u, lpString, v18);
    if ( v10 )
      break;
    if ( v11 == a1 - 1 )
    {
      if ( !*((_DWORD *)a3 + 29) )
        goto LABEL_20;
      v19 = v28;
      v10 = FastRegCreateKey(hKey, szTypeLib, &v28);
      v20 = v28;
      if ( v10 )
        v20 = v19;
      v28 = v20;
      if ( v10 )
        break;
      v21 = lstrlenA(a4);
      v10 = RegSetValueA(v28, 0, 1u, a4, v21);
      if ( v10 )
        break;
      v22 = lstrlenA(String);
      v10 = RegSetValueExA(v28, "Version", 0, 1u, (const BYTE *)String, v22);
      if ( v10 )
        break;
      v23 = RegCloseKey(v28);
      v28 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    else
    {
      StringFromGUID2Ansi(&v29[a1 - 1], Data, 39);
      v24 = lstrlenA(Data);
      v23 = RegSetValueA(hKey, aForward, 1u, Data, v24);
    }
    v10 = v23;
    if ( v23 )
      break;
LABEL_20:
    v25 = RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v10 = v25;
    if ( v25 )
      goto LABEL_25;
    if ( ++v11 >= a1 )
      return v10;
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
LABEL_25:
  if ( v28 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v28);
  return v10;
}

```

## disassembly

```asm
0x180065244  push    rbp
0x180065246  push    rbx
0x180065247  push    rsi
0x180065248  push    rdi
0x180065249  push    r12
0x18006524b  push    r13
0x18006524d  push    r14
0x18006524f  push    r15
0x180065251  lea     rbp, [rsp-0A8h]
0x180065259  mov     eax, 1A8h
0x18006525e  call    _alloca_probe
0x180065263  sub     rsp, rax
0x180065266  mov     rax, cs:__security_cookie
0x18006526d  xor     rax, rsp
0x180065270  mov     [rbp+0E0h+var_50], rax
0x180065277  mov     r12, [rbp+0E0h+lpString]
0x18006527e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065282  mov     r13, r9
0x180065285  movzx   r9d, word ptr [r8+7Ah]
0x18006528a  mov     r14, r8
0x18006528d  movzx   r8d, word ptr [r8+78h]
0x180065292  mov     [rsp+1E0h+var_1A0], rdx
0x180065297  mov     r15d, ecx
0x18006529a  lea     rdx, aXX; "%x.%x"
0x1800652a1  lea     rcx, [rsp+1E0h+String]; LPSTR
0x1800652a6  mov     [rsp+1E0h+hKey], rax
0x1800652ab  mov     [rsp+1E0h+var_1A8], rax
0x1800652b0  xor     edi, edi
0x1800652b2  call    cs:__imp_wsprintfA
0x1800652b8  lea     rdx, ?szInterfaceSep@@3PADA; "Interface\\"
0x1800652bf  lea     rcx, [rbp+0E0h+String1]; lpString1
0x1800652c3  call    cs:__imp_lstrcpyA
0x1800652c9  xor     esi, esi
0x1800652cb  test    r15d, r15d
0x1800652ce  jle     loc_180065541
0x1800652d4  lea     rcx, ?szInterfaceSep@@3PADA; "Interface\\"
0x1800652db  call    cs:__imp_lstrlenA
0x1800652e1  lea     rcx, ?szInterfaceSep@@3PADA; "Interface\\"
0x1800652e8  mov     ebx, 100h
0x1800652ed  sub     ebx, eax
0x1800652ef  call    cs:__imp_lstrlenA
0x1800652f5  lea     rdx, [rbp+0E0h+String1]
0x1800652f9  movsxd  rcx, eax
0x1800652fc  mov     r8d, ebx; int
0x1800652ff  add     rdx, rcx; char *
0x180065302  movsxd  rcx, esi
0x180065305  shl     rcx, 4
0x180065309  add     rcx, [rsp+1E0h+var_1A0]; struct _GUID *
0x18006530e  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180065313  cmp     dword ptr [r14+70h], 0
0x180065318  jz      short loc_18006532A
0x18006531a  lea     rdx, [rbp+0E0h+String1]; char *
0x18006531e  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180065325  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x18006532a  mov     rbx, [rsp+1E0h+hKey]
0x18006532f  lea     r8, [rsp+1E0h+hKey]; HKEY *
0x180065334  lea     rdx, [rbp+0E0h+String1]; char *
0x180065338  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x18006533f  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180065344  mov     edi, eax
0x180065346  mov     rax, [rsp+1E0h+hKey]
0x18006534b  test    edi, edi
0x18006534d  cmovnz  rax, rbx
0x180065351  mov     [rsp+1E0h+hKey], rax
0x180065356  jnz     loc_18006551F
0x18006535c  mov     rcx, [r14+10h]; lpString
0x180065360  call    cs:__imp_lstrlenA
0x180065366  mov     r9, [r14+10h]; lpData
0x18006536a  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006536f  mov     ebx, 1
0x180065374  xor     edx, edx; lpSubKey
0x180065376  mov     [rsp+1E0h+cbData], eax; cbData
0x18006537a  mov     r8d, ebx; dwType
0x18006537d  call    cs:__imp_RegSetValueA
0x180065383  mov     edi, eax
0x180065385  test    eax, eax
0x180065387  jnz     loc_18006551F
0x18006538d  mov     rcx, r12; lpString
0x180065390  call    cs:__imp_lstrlenA
0x180065396  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006539b  lea     rdx, aProxystubclsid; "ProxyStubClsid"
0x1800653a2  mov     r9, r12; lpData
0x1800653a5  mov     r8d, ebx; dwType
0x1800653a8  mov     [rsp+1E0h+cbData], eax; cbData
0x1800653ac  call    cs:__imp_RegSetValueA
0x1800653b2  mov     edi, eax
0x1800653b4  test    eax, eax
0x1800653b6  jnz     loc_18006551F
0x1800653bc  mov     rcx, r12; lpString
0x1800653bf  call    cs:__imp_lstrlenA
0x1800653c5  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800653ca  lea     rdx, aProxystubclsid_0; "ProxyStubClsid32"
0x1800653d1  mov     r9, r12; lpData
0x1800653d4  mov     r8d, ebx; dwType
0x1800653d7  mov     [rsp+1E0h+cbData], eax; cbData
0x1800653db  call    cs:__imp_RegSetValueA
0x1800653e1  mov     edi, eax
0x1800653e3  test    eax, eax
0x1800653e5  jnz     loc_18006551F
0x1800653eb  lea     eax, [r15-1]
0x1800653ef  cmp     esi, eax
0x1800653f1  jnz     loc_1800654B1
0x1800653f7  cmp     [r14+74h], edi
0x1800653fb  jz      loc_1800654FC
0x180065401  mov     rcx, [rsp+1E0h+hKey]; HKEY
0x180065406  mov     rbx, [rsp+1E0h+var_1A8]
0x18006540b  lea     r8, [rsp+1E0h+var_1A8]; HKEY *
0x180065410  lea     rdx, ?szTypeLib@@3PADA; "TypeLib"
0x180065417  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x18006541c  mov     edi, eax
0x18006541e  mov     rax, [rsp+1E0h+var_1A8]
0x180065423  test    edi, edi
0x180065425  cmovnz  rax, rbx
0x180065429  mov     [rsp+1E0h+var_1A8], rax
0x18006542e  jnz     loc_18006551F
0x180065434  mov     rcx, r13; lpString
0x180065437  call    cs:__imp_lstrlenA
0x18006543d  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x180065442  mov     ebx, 1
0x180065447  mov     r8d, ebx; dwType
0x18006544a  mov     r9, r13; lpData
0x18006544d  xor     edx, edx; lpSubKey
0x18006544f  mov     [rsp+1E0h+cbData], eax; cbData
0x180065453  call    cs:__imp_RegSetValueA
0x180065459  mov     edi, eax
0x18006545b  test    eax, eax
0x18006545d  jnz     loc_18006551F
0x180065463  lea     rcx, [rsp+1E0h+String]; lpString
0x180065468  call    cs:__imp_lstrlenA
0x18006546e  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x180065473  lea     rdx, aVersion; "Version"
0x18006547a  mov     [rsp+1E0h+var_1B8], eax; cbData
0x18006547e  lea     rax, [rsp+1E0h+String]
0x180065483  mov     r9d, ebx; dwType
0x180065486  xor     r8d, r8d; Reserved
0x180065489  mov     qword ptr [rsp+1E0h+cbData], rax; lpData
0x18006548e  call    cs:__imp_RegSetValueExA
0x180065494  mov     edi, eax
0x180065496  test    eax, eax
0x180065498  jnz     loc_18006551F
0x18006549e  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x1800654a3  call    cs:__imp_RegCloseKey
0x1800654a9  or      [rsp+1E0h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x1800654af  jmp     short loc_1800654F6
0x1800654b1  movsxd  rcx, eax
0x1800654b4  lea     rdx, [rsp+1E0h+Data]; char *
0x1800654b9  mov     r8d, 27h ; '''; int
0x1800654bf  shl     rcx, 4
0x1800654c3  add     rcx, [rsp+1E0h+var_1A0]; struct _GUID *
0x1800654c8  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x1800654cd  lea     rcx, [rsp+1E0h+Data]; lpString
0x1800654d2  call    cs:__imp_lstrlenA
0x1800654d8  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800654dd  lea     r9, [rsp+1E0h+Data]; lpData
0x1800654e2  lea     rdx, aForward; "Forward"
0x1800654e9  mov     r8d, ebx; dwType
0x1800654ec  mov     [rsp+1E0h+cbData], eax; cbData
0x1800654f0  call    cs:__imp_RegSetValueA
0x1800654f6  mov     edi, eax
0x1800654f8  test    eax, eax
0x1800654fa  jnz     short loc_18006551F
0x1800654fc  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180065501  call    cs:__imp_RegCloseKey
0x180065507  or      [rsp+1E0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18006550d  mov     edi, eax
0x18006550f  test    eax, eax
0x180065511  jnz     short loc_180065530
0x180065513  add     esi, ebx
0x180065515  cmp     esi, r15d
0x180065518  jge     short loc_180065541
0x18006551a  jmp     loc_1800652D4
0x18006551f  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180065524  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180065528  jz      short loc_180065530
0x18006552a  call    cs:__imp_RegCloseKey
0x180065530  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x180065535  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180065539  jz      short loc_180065541
0x18006553b  call    cs:__imp_RegCloseKey
0x180065541  mov     eax, edi
0x180065543  mov     rcx, [rbp+0E0h+var_50]
0x18006554a  xor     rcx, rsp; StackCookie
0x18006554d  call    __security_check_cookie
0x180065552  add     rsp, 1A8h
0x180065559  pop     r15
0x18006555b  pop     r14
0x18006555d  pop     r13
0x18006555f  pop     r12
0x180065561  pop     rdi
0x180065562  pop     rsi
0x180065563  pop     rbx
0x180065564  pop     rbp
0x180065565  retn
```
