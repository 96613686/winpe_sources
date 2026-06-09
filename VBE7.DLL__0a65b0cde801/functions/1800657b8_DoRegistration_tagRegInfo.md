# _DoRegistration(tagRegInfo *)

- ea: `0x1800657b8`
- end: `0x180065df9`
- name: `?_DoRegistration@@YAIPEAUtagRegInfo@@@Z`
- size: `1601`
- prototype: `unsigned int __fastcall(struct tagRegInfo *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180062670`
- `0x1800640c8`

## callees

- `0x180016790`
- `0x180059120`
- `0x18005b0d4`
- `0x180060ed4`
- `0x180061268`
- `0x180065244`
- `0x18006556c`
- `0x1800657b8`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800658ed`
- `KERNEL32!lstrlenA` at `0x18006592e`
- `KERNEL32!lstrlenA` at `0x180065970`
- `KERNEL32!lstrlenA` at `0x1800659d5`
- `KERNEL32!lstrlenA` at `0x180065a14`
- `KERNEL32!lstrlenA` at `0x180065ada`
- `KERNEL32!lstrlenA` at `0x180065b0b`
- `KERNEL32!lstrlenA` at `0x180065bb6`
- `KERNEL32!lstrlenA` at `0x180065be1`
- `KERNEL32!lstrlenA` at `0x180065c9d`
- `KERNEL32!lstrlenA` at `0x1800658ed`
- `KERNEL32!lstrlenA` at `0x18006592e`
- `KERNEL32!lstrlenA` at `0x180065970`
- `KERNEL32!lstrlenA` at `0x1800659d5`
- `KERNEL32!lstrlenA` at `0x180065a14`
- `KERNEL32!lstrlenA` at `0x180065ada`
- `KERNEL32!lstrlenA` at `0x180065b0b`
- `KERNEL32!lstrlenA` at `0x180065bb6`
- `KERNEL32!lstrlenA` at `0x180065be1`
- `KERNEL32!lstrlenA` at `0x180065c9d`
- `USER32!wsprintfA` at `0x180065814`
- `USER32!wsprintfA` at `0x180065854`
- `USER32!wsprintfA` at `0x18006586c`
- `USER32!wsprintfA` at `0x180065c53`
- `USER32!wsprintfA` at `0x180065814`
- `USER32!wsprintfA` at `0x180065854`
- `USER32!wsprintfA` at `0x18006586c`
- `USER32!wsprintfA` at `0x180065c53`
- `ADVAPI32!RegSetValueA` at `0x18006590a`
- `ADVAPI32!RegSetValueA` at `0x18006598d`
- `ADVAPI32!RegSetValueA` at `0x1800659ec`
- `ADVAPI32!RegSetValueA` at `0x180065af7`
- `ADVAPI32!RegSetValueA` at `0x180065b28`
- `ADVAPI32!RegSetValueA` at `0x180065bcd`
- `ADVAPI32!RegSetValueA` at `0x180065bfe`
- `ADVAPI32!RegSetValueA` at `0x18006590a`
- `ADVAPI32!RegSetValueA` at `0x18006598d`
- `ADVAPI32!RegSetValueA` at `0x1800659ec`
- `ADVAPI32!RegSetValueA` at `0x180065af7`
- `ADVAPI32!RegSetValueA` at `0x180065b28`
- `ADVAPI32!RegSetValueA` at `0x180065bcd`
- `ADVAPI32!RegSetValueA` at `0x180065bfe`
- `ADVAPI32!RegDeleteValueA` at `0x180065aaa`
- `ADVAPI32!RegDeleteValueA` at `0x180065aaa`
- `ADVAPI32!RegSetValueExA` at `0x180065956`
- `ADVAPI32!RegSetValueExA` at `0x180065a38`
- `ADVAPI32!RegSetValueExA` at `0x180065cc5`
- `ADVAPI32!RegSetValueExA` at `0x180065cfb`
- `ADVAPI32!RegSetValueExA` at `0x180065956`
- `ADVAPI32!RegSetValueExA` at `0x180065a38`
- `ADVAPI32!RegSetValueExA` at `0x180065cc5`
- `ADVAPI32!RegSetValueExA` at `0x180065cfb`
- `ADVAPI32!RegCloseKey` at `0x180065a4f`
- `ADVAPI32!RegCloseKey` at `0x180065a60`
- `ADVAPI32!RegCloseKey` at `0x180065ab5`
- `ADVAPI32!RegCloseKey` at `0x180065b3d`
- `ADVAPI32!RegCloseKey` at `0x180065c13`
- `ADVAPI32!RegCloseKey` at `0x180065d10`
- `ADVAPI32!RegCloseKey` at `0x180065a4f`
- `ADVAPI32!RegCloseKey` at `0x180065a60`
- `ADVAPI32!RegCloseKey` at `0x180065ab5`
- `ADVAPI32!RegCloseKey` at `0x180065b3d`
- `ADVAPI32!RegCloseKey` at `0x180065c13`
- `ADVAPI32!RegCloseKey` at `0x180065d10`

## string_xrefs

- `0x18006585e`: `CLSID\%s`
- `0x180065aa3`: `ThreadingModel`
- `0x180065bf0`: `Clsid`
- `0x180065a1f`: `ThreadingModel`

## pseudocode

```c
unsigned int __fastcall _DoRegistration(struct tagRegInfo *a1)
{
  const char *v1; // r9
  const char *v2; // r8
  char *v4; // r14
  HKEY v5; // rbx
  LSTATUS v6; // edi
  HKEY v7; // rax
  CHAR *v8; // rcx
  CHAR *v9; // rbx
  DWORD cbData; // eax
  int v11; // eax
  DWORD v12; // eax
  HKEY v13; // rbx
  HKEY v14; // rax
  DWORD v15; // eax
  int v16; // eax
  LSTATUS v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  LSTATUS v21; // eax
  HKEY v22; // rbx
  HKEY v23; // rax
  CHAR *v24; // rcx
  CHAR *v25; // rbx
  DWORD v26; // eax
  DWORD v27; // eax
  LSTATUS v28; // eax
  HKEY v29; // rbx
  HKEY v30; // rax
  int v31; // eax
  LSTATUS v32; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v34; // [rsp+38h] [rbp-C8h] BYREF
  void *v35; // [rsp+40h] [rbp-C0h] BYREF
  CATID v36; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Data[40]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR String[40]; // [rsp+108h] [rbp+8h] BYREF
  CHAR v39[40]; // [rsp+130h] [rbp+30h] BYREF
  CHAR v40[40]; // [rsp+158h] [rbp+58h] BYREF
  CHAR v41[256]; // [rsp+180h] [rbp+80h] BYREF
  CHAR v42[256]; // [rsp+280h] [rbp+180h] BYREF

  v1 = (const char *)*((_QWORD *)a1 + 2);
  v2 = (const char *)*((_QWORD *)a1 + 1);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v34 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  wsprintfA(Data, "%s.%s", v2, v1);
  StringFromGUID2Ansi((const struct _GUID *)a1 + 2, String, 39);
  StringFromGUID2Ansi((const struct _GUID *)a1 + 5, v39, 39);
  wsprintfA(v40, "%d.%d", *((unsigned __int16 *)a1 + 60), *((unsigned __int16 *)a1 + 61));
  wsprintfA(v41, "CLSID\\%s", String);
  v4 = (char *)&szLocalServer32;
  if ( *((_DWORD *)a1 + 26) )
    v4 = szInprocServer32;
  if ( *((_DWORD *)a1 + 28) )
    RegDeleteSubKeys(HKEY_CLASSES_ROOT, v41);
  v5 = hKey;
  v6 = FastRegCreateKey(HKEY_CLASSES_ROOT, v41, &hKey);
  v7 = hKey;
  if ( v6 )
    v7 = v5;
  hKey = v7;
  if ( v6 )
    goto LABEL_24;
  v8 = Data;
  v9 = Data;
  if ( **((_BYTE **)a1 + 3) )
  {
    v8 = (CHAR *)*((_QWORD *)a1 + 3);
    v9 = v8;
  }
  cbData = lstrlenA(v8);
  v6 = RegSetValueA(hKey, 0, 1u, v9, cbData);
  if ( v6 )
    goto LABEL_24;
  if ( (*((_WORD *)a1 + 62) & 0x1200) != 0 )
  {
    if ( *((_DWORD *)a1 + 26) )
    {
      v11 = lstrlenA(String);
      v6 = RegSetValueExA(hKey, "AppID", 0, 1u, (const BYTE *)String, v11 + 1);
      if ( v6 )
        goto LABEL_24;
    }
    if ( (*((_WORD *)a1 + 62) & 0x1200) != 0 )
    {
      v12 = lstrlenA(Data);
      v6 = RegSetValueA(hKey, szPROGID, 1u, Data, v12);
      if ( v6 )
        goto LABEL_24;
    }
  }
  if ( *((_DWORD *)a1 + 25) )
  {
    v13 = v34;
    v6 = FastRegCreateKey(hKey, v4, &v34);
    v14 = v34;
    if ( v6 )
      v14 = v13;
    v34 = v14;
    if ( v6 )
      goto LABEL_24;
    v15 = lstrlenA(*(LPCSTR *)a1);
    v6 = RegSetValueA(v34, 0, 1u, *(LPCSTR *)a1, v15);
    if ( v6 )
      goto LABEL_24;
    if ( !*((_DWORD *)a1 + 26) || *((_DWORD *)a1 + 27) )
    {
      if ( !*((_DWORD *)a1 + 28) )
        RegDeleteValueA(v34, "ThreadingModel");
    }
    else
    {
      v16 = lstrlenA((LPCSTR)szApartmentModel);
      v6 = RegSetValueExA(v34, szThreadingModel, 0, 1u, szApartmentModel, v16 + 1);
      if ( v6 )
        goto LABEL_24;
    }
    v18 = RegCloseKey(v34);
    v34 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v6 = v18;
    if ( v18 )
      goto LABEL_24;
  }
  else
  {
    RegDeleteSubKeys(hKey, v4);
  }
  if ( (*((_WORD *)a1 + 62) & 0x1200) != 0 )
  {
    v19 = lstrlenA(v39);
    v6 = RegSetValueA(hKey, szTypeLib, 1u, v39, v19);
    if ( v6 )
      goto LABEL_24;
    v20 = lstrlenA(v40);
    v6 = RegSetValueA(hKey, szVersion, 1u, v40, v20);
    if ( v6 )
      goto LABEL_24;
  }
  v21 = RegCloseKey(hKey);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = v21;
  if ( v21 )
    goto LABEL_26;
  if ( (*((_WORD *)a1 + 62) & 0x1200) == 0 )
    goto LABEL_59;
  RegDeleteSubKeys(HKEY_CLASSES_ROOT, Data);
  v22 = hKey;
  v6 = FastRegCreateKey(HKEY_CLASSES_ROOT, Data, &hKey);
  v23 = hKey;
  if ( v6 )
    v23 = v22;
  hKey = v23;
  if ( v6 )
    goto LABEL_24;
  v24 = Data;
  v25 = Data;
  if ( **((_BYTE **)a1 + 3) )
  {
    v24 = (CHAR *)*((_QWORD *)a1 + 3);
    v25 = v24;
  }
  v26 = lstrlenA(v24);
  v6 = RegSetValueA(hKey, 0, 1u, v25, v26);
  if ( v6 )
    goto LABEL_24;
  v27 = lstrlenA(String);
  v6 = RegSetValueA(hKey, szCLSID, 1u, String, v27);
  if ( v6 )
    goto LABEL_24;
  v28 = RegCloseKey(hKey);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = v28;
  if ( v28 )
    goto LABEL_26;
  if ( (*((_WORD *)a1 + 62) & 0x1200) == 0 )
    goto LABEL_59;
  if ( *((_DWORD *)a1 + 26) )
  {
    wsprintfA(v42, "AppID\\%s", String);
    RegDeleteSubKeys(HKEY_CLASSES_ROOT, v42);
    v29 = hKey;
    v6 = FastRegCreateKey(HKEY_CLASSES_ROOT, v42, &hKey);
    v30 = hKey;
    if ( v6 )
      v30 = v29;
    hKey = v30;
    if ( v6 )
      goto LABEL_24;
    v31 = lstrlenA(String);
    v6 = RegSetValueExA(hKey, "AppID", 0, 1u, (const BYTE *)String, v31 + 1);
    if ( v6 )
      goto LABEL_24;
    v6 = RegSetValueExA(hKey, "RunAs", 0, 1u, "Interactive User", 0x11u);
    if ( v6 )
      goto LABEL_24;
    v32 = RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v6 = v32;
    if ( v32 )
    {
LABEL_26:
      if ( v34 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(v34);
      return ErrFromRegError(v6);
    }
  }
  if ( (*((_WORD *)a1 + 62) & 0x1200) != 0 )
  {
    v6 = _RegisterInterfaces(
           *((_DWORD *)a1 + 12),
           *((struct _GUID **)a1 + 7),
           a1,
           v39,
           "{00020424-0000-0000-C000-000000000046}");
    if ( !v6 )
    {
      v6 = _RegisterInterfaces(
             *((_DWORD *)a1 + 16),
             *((struct _GUID **)a1 + 9),
             a1,
             v39,
             "{00020420-0000-0000-C000-000000000046}");
      if ( !v6 )
      {
        if ( (*((_WORD *)a1 + 62) & 0x1200) != 0 )
        {
          v36 = CATID_Programmable;
          if ( (int)GetComponentCategoryManagerPointer(&IID_ICatRegister, &v35) >= 0 )
            (*(void (__fastcall **)(void *, char *, __int64, CATID *))(*(_QWORD *)v35 + 40LL))(
              v35,
              (char *)a1 + 32,
              1,
              &v36);
        }
        goto LABEL_59;
      }
    }
LABEL_24:
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
LABEL_59:
  if ( (*((_BYTE *)a1 + 130) & 1) == 0 )
    return ErrFromRegError(v6);
  return _RegisterBaseDesigner(a1, Data, 1);
}

```

## disassembly

```asm
0x1800657b8  mov     [rsp-8+arg_8], rbx
0x1800657bd  mov     [rsp-8+arg_10], rsi
0x1800657c2  push    rbp
0x1800657c3  push    rdi
0x1800657c4  push    r13
0x1800657c6  push    r14
0x1800657c8  push    r15
0x1800657ca  lea     rbp, [rsp-290h]
0x1800657d2  mov     eax, 390h
0x1800657d7  call    _alloca_probe
0x1800657dc  sub     rsp, rax
0x1800657df  mov     rax, cs:__security_cookie
0x1800657e6  xor     rax, rsp
0x1800657e9  mov     [rbp+2B0h+var_30], rax
0x1800657f0  mov     r9, [rcx+10h]
0x1800657f4  mov     r8, [rcx+8]
0x1800657f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800657fc  mov     rsi, rcx
0x1800657ff  lea     rdx, aSS_6; "%s.%s"
0x180065806  lea     rcx, [rbp+2B0h+Data]; LPSTR
0x18006580a  mov     [rsp+3B0h+hKey], rax
0x18006580f  mov     [rsp+3B0h+var_378], rax
0x180065814  call    cs:__imp_wsprintfA
0x18006581a  mov     ebx, 27h ; '''
0x18006581f  lea     rdx, [rbp+2B0h+String]; char *
0x180065823  lea     rcx, [rsi+20h]; struct _GUID *
0x180065827  mov     r8d, ebx; int
0x18006582a  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18006582f  lea     rcx, [rsi+50h]; struct _GUID *
0x180065833  lea     rdx, [rbp+2B0h+var_280]; char *
0x180065837  mov     r8d, ebx; int
0x18006583a  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18006583f  movzx   r9d, word ptr [rsi+7Ah]
0x180065844  movzx   r8d, word ptr [rsi+78h]
0x180065849  lea     rdx, aDD; "%d.%d"
0x180065850  lea     rcx, [rbp+2B0h+var_258]; LPSTR
0x180065854  call    cs:__imp_wsprintfA
0x18006585a  lea     r8, [rbp+2B0h+String]
0x18006585e  lea     rdx, aClsidS; "CLSID\\%s"
0x180065865  lea     rcx, [rbp+2B0h+var_230]; LPSTR
0x18006586c  call    cs:__imp_wsprintfA
0x180065872  cmp     dword ptr [rsi+68h], 0
0x180065876  lea     rax, ?szInprocServer32@@3PADA; "InprocServer32"
0x18006587d  lea     r14, ?szLocalServer32@@3PADA; "LocalServer32"
0x180065884  mov     rdi, 0FFFFFFFF80000000h
0x18006588b  cmovnz  r14, rax
0x18006588f  cmp     dword ptr [rsi+70h], 0
0x180065893  jz      short loc_1800658A4
0x180065895  lea     rdx, [rbp+2B0h+var_230]; char *
0x18006589c  mov     rcx, rdi; HKEY
0x18006589f  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x1800658a4  mov     rbx, [rsp+3B0h+hKey]
0x1800658a9  lea     r8, [rsp+3B0h+hKey]; HKEY *
0x1800658ae  lea     rdx, [rbp+2B0h+var_230]; char *
0x1800658b5  mov     rcx, rdi; HKEY
0x1800658b8  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x1800658bd  mov     edi, eax
0x1800658bf  mov     rax, [rsp+3B0h+hKey]
0x1800658c4  test    edi, edi
0x1800658c6  cmovnz  rax, rbx
0x1800658ca  mov     [rsp+3B0h+hKey], rax
0x1800658cf  jnz     loc_180065A44
0x1800658d5  mov     rdx, [rsi+18h]
0x1800658d9  lea     rcx, [rbp+2B0h+Data]
0x1800658dd  lea     rbx, [rbp+2B0h+Data]
0x1800658e1  mov     al, [rdx]
0x1800658e3  test    al, al
0x1800658e5  cmovnz  rcx, rdx; lpString
0x1800658e9  cmovnz  rbx, rdx
0x1800658ed  call    cs:__imp_lstrlenA
0x1800658f3  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800658f8  mov     r13d, 1
0x1800658fe  mov     r8d, r13d; dwType
0x180065901  mov     r9, rbx; lpData
0x180065904  xor     edx, edx; lpSubKey
0x180065906  mov     [rsp+3B0h+cbData], eax; cbData
0x18006590a  call    cs:__imp_RegSetValueA
0x180065910  mov     edi, eax
0x180065912  test    eax, eax
0x180065914  jnz     loc_180065A44
0x18006591a  mov     ebx, 1200h
0x18006591f  test    [rsi+7Ch], bx
0x180065923  jz      short loc_18006599D
0x180065925  cmp     [rsi+68h], eax
0x180065928  jz      short loc_180065966
0x18006592a  lea     rcx, [rbp+2B0h+String]; lpString
0x18006592e  call    cs:__imp_lstrlenA
0x180065934  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065939  lea     rdx, aAppid; "AppID"
0x180065940  add     eax, r13d
0x180065943  mov     r9d, r13d; dwType
0x180065946  xor     r8d, r8d; Reserved
0x180065949  mov     [rsp+3B0h+var_388], eax; cbData
0x18006594d  lea     rax, [rbp+2B0h+String]
0x180065951  mov     qword ptr [rsp+3B0h+cbData], rax; lpData
0x180065956  call    cs:__imp_RegSetValueExA
0x18006595c  mov     edi, eax
0x18006595e  test    eax, eax
0x180065960  jnz     loc_180065A44
0x180065966  test    [rsi+7Ch], bx
0x18006596a  jz      short loc_18006599D
0x18006596c  lea     rcx, [rbp+2B0h+Data]; lpString
0x180065970  call    cs:__imp_lstrlenA
0x180065976  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18006597b  lea     r9, [rbp+2B0h+Data]; lpData
0x18006597f  lea     rdx, ?szPROGID@@3PADA; "ProgID"
0x180065986  mov     r8d, r13d; dwType
0x180065989  mov     [rsp+3B0h+cbData], eax; cbData
0x18006598d  call    cs:__imp_RegSetValueA
0x180065993  mov     edi, eax
0x180065995  test    eax, eax
0x180065997  jnz     loc_180065A44
0x18006599d  cmp     dword ptr [rsi+64h], 0
0x1800659a1  mov     rcx, [rsp+3B0h+hKey]; HKEY
0x1800659a6  mov     rdx, r14; char *
0x1800659a9  jz      loc_180065DEF
0x1800659af  mov     rbx, [rsp+3B0h+var_378]
0x1800659b4  lea     r8, [rsp+3B0h+var_378]; HKEY *
0x1800659b9  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x1800659be  mov     edi, eax
0x1800659c0  mov     rax, [rsp+3B0h+var_378]
0x1800659c5  test    edi, edi
0x1800659c7  cmovnz  rax, rbx
0x1800659cb  mov     [rsp+3B0h+var_378], rax
0x1800659d0  jnz     short loc_180065A44
0x1800659d2  mov     rcx, [rsi]; lpString
0x1800659d5  call    cs:__imp_lstrlenA
0x1800659db  mov     r9, [rsi]; lpData
0x1800659de  mov     rcx, [rsp+3B0h+var_378]; hKey
0x1800659e3  mov     r8d, r13d; dwType
0x1800659e6  xor     edx, edx; lpSubKey
0x1800659e8  mov     [rsp+3B0h+cbData], eax; cbData
0x1800659ec  call    cs:__imp_RegSetValueA
0x1800659f2  mov     edi, eax
0x1800659f4  test    eax, eax
0x1800659f6  jnz     short loc_180065A44
0x1800659f8  cmp     [rsi+68h], eax
0x1800659fb  jz      loc_180065A98
0x180065a01  cmp     [rsi+6Ch], eax
0x180065a04  jnz     loc_180065A98
0x180065a0a  lea     rbx, ?szApartmentModel@@3PADA; "Apartment"
0x180065a11  mov     rcx, rbx; lpString
0x180065a14  call    cs:__imp_lstrlenA
0x180065a1a  mov     rcx, [rsp+3B0h+var_378]; hKey
0x180065a1f  lea     rdx, ?szThreadingModel@@3PADA; "ThreadingModel"
0x180065a26  add     eax, r13d
0x180065a29  mov     r9d, r13d; dwType
0x180065a2c  xor     r8d, r8d; Reserved
0x180065a2f  mov     [rsp+3B0h+var_388], eax; cbData
0x180065a33  mov     qword ptr [rsp+3B0h+cbData], rbx; lpData
0x180065a38  call    cs:__imp_RegSetValueExA
0x180065a3e  mov     edi, eax
0x180065a40  test    eax, eax
0x180065a42  jz      short loc_180065AB0
0x180065a44  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065a49  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180065a4d  jz      short loc_180065A55
0x180065a4f  call    cs:__imp_RegCloseKey
0x180065a55  mov     rcx, [rsp+3B0h+var_378]; hKey
0x180065a5a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180065a5e  jz      short loc_180065A66
0x180065a60  call    cs:__imp_RegCloseKey
0x180065a66  mov     ecx, edi; int
0x180065a68  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x180065a6d  mov     rcx, [rbp+2B0h+var_30]
0x180065a74  xor     rcx, rsp; StackCookie
0x180065a77  call    __security_check_cookie
0x180065a7c  lea     r11, [rsp+3B0h+var_20]
0x180065a84  mov     rbx, [r11+38h]
0x180065a88  mov     rsi, [r11+40h]
0x180065a8c  mov     rsp, r11
0x180065a8f  pop     r15
0x180065a91  pop     r14
0x180065a93  pop     r13
0x180065a95  pop     rdi
0x180065a96  pop     rbp
0x180065a97  retn
0x180065a98  cmp     dword ptr [rsi+70h], 0
0x180065a9c  jnz     short loc_180065AB0
0x180065a9e  mov     rcx, [rsp+3B0h+var_378]; hKey
0x180065aa3  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180065aaa  call    cs:__imp_RegDeleteValueA
0x180065ab0  mov     rcx, [rsp+3B0h+var_378]; hKey
0x180065ab5  call    cs:__imp_RegCloseKey
0x180065abb  or      [rsp+3B0h+var_378], 0FFFFFFFFFFFFFFFFh
0x180065ac1  mov     edi, eax
0x180065ac3  test    eax, eax
0x180065ac5  jnz     loc_180065A44
0x180065acb  mov     ebx, 1200h
0x180065ad0  test    [rsi+7Ch], bx
0x180065ad4  jz      short loc_180065B38
0x180065ad6  lea     rcx, [rbp+2B0h+var_280]; lpString
0x180065ada  call    cs:__imp_lstrlenA
0x180065ae0  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065ae5  lea     r9, [rbp+2B0h+var_280]; lpData
0x180065ae9  lea     rdx, ?szTypeLib@@3PADA; "TypeLib"
0x180065af0  mov     r8d, r13d; dwType
0x180065af3  mov     [rsp+3B0h+cbData], eax; cbData
0x180065af7  call    cs:__imp_RegSetValueA
0x180065afd  mov     edi, eax
0x180065aff  test    eax, eax
0x180065b01  jnz     loc_180065A44
0x180065b07  lea     rcx, [rbp+2B0h+var_258]; lpString
0x180065b0b  call    cs:__imp_lstrlenA
0x180065b11  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065b16  lea     r9, [rbp+2B0h+var_258]; lpData
0x180065b1a  lea     rdx, ?szVersion@@3PADA; "VERSION"
0x180065b21  mov     r8d, r13d; dwType
0x180065b24  mov     [rsp+3B0h+cbData], eax; cbData
0x180065b28  call    cs:__imp_RegSetValueA
0x180065b2e  mov     edi, eax
0x180065b30  test    eax, eax
0x180065b32  jnz     loc_180065A44
0x180065b38  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065b3d  call    cs:__imp_RegCloseKey
0x180065b43  or      [rsp+3B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180065b49  mov     edi, eax
0x180065b4b  test    eax, eax
0x180065b4d  jnz     loc_180065A55
0x180065b53  mov     r14, 0FFFFFFFF80000000h
0x180065b5a  test    [rsi+7Ch], bx
0x180065b5e  jz      loc_180065DC6
0x180065b64  lea     rdx, [rbp+2B0h+Data]; char *
0x180065b68  mov     rcx, r14; HKEY
0x180065b6b  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180065b70  mov     rbx, [rsp+3B0h+hKey]
0x180065b75  lea     r8, [rsp+3B0h+hKey]; HKEY *
0x180065b7a  lea     rdx, [rbp+2B0h+Data]; char *
0x180065b7e  mov     rcx, r14; HKEY
0x180065b81  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180065b86  mov     edi, eax
0x180065b88  mov     rax, [rsp+3B0h+hKey]
0x180065b8d  test    edi, edi
0x180065b8f  cmovnz  rax, rbx
0x180065b93  mov     [rsp+3B0h+hKey], rax
0x180065b98  jnz     loc_180065A44
0x180065b9e  mov     rdx, [rsi+18h]
0x180065ba2  lea     rcx, [rbp+2B0h+Data]
0x180065ba6  lea     rbx, [rbp+2B0h+Data]
0x180065baa  mov     al, [rdx]
0x180065bac  test    al, al
0x180065bae  cmovnz  rcx, rdx; lpString
0x180065bb2  cmovnz  rbx, rdx
0x180065bb6  call    cs:__imp_lstrlenA
0x180065bbc  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065bc1  mov     r9, rbx; lpData
0x180065bc4  mov     r8d, r13d; dwType
0x180065bc7  xor     edx, edx; lpSubKey
0x180065bc9  mov     [rsp+3B0h+cbData], eax; cbData
0x180065bcd  call    cs:__imp_RegSetValueA
0x180065bd3  mov     edi, eax
0x180065bd5  test    eax, eax
0x180065bd7  jnz     loc_180065A44
0x180065bdd  lea     rcx, [rbp+2B0h+String]; lpString
0x180065be1  call    cs:__imp_lstrlenA
0x180065be7  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065bec  lea     r9, [rbp+2B0h+String]; lpData
0x180065bf0  lea     rdx, ?szCLSID@@3PADA; "Clsid"
0x180065bf7  mov     r8d, r13d; dwType
0x180065bfa  mov     [rsp+3B0h+cbData], eax; cbData
0x180065bfe  call    cs:__imp_RegSetValueA
0x180065c04  mov     edi, eax
0x180065c06  test    eax, eax
0x180065c08  jnz     loc_180065A44
0x180065c0e  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065c13  call    cs:__imp_RegCloseKey
0x180065c19  or      [rsp+3B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180065c1f  mov     edi, eax
0x180065c21  test    eax, eax
0x180065c23  jnz     loc_180065A55
0x180065c29  mov     ebx, 1200h
0x180065c2e  test    [rsi+7Ch], bx
0x180065c32  jz      loc_180065DC6
0x180065c38  cmp     [rsi+68h], eax
0x180065c3b  jz      loc_180065D2B
0x180065c41  lea     r8, [rbp+2B0h+String]
0x180065c45  lea     rdx, aAppidS; "AppID\\%s"
0x180065c4c  lea     rcx, [rbp+2B0h+var_130]; LPSTR
0x180065c53  call    cs:__imp_wsprintfA
0x180065c59  lea     rdx, [rbp+2B0h+var_130]; char *
0x180065c60  mov     rcx, r14; HKEY
0x180065c63  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180065c68  mov     rbx, [rsp+3B0h+hKey]
0x180065c6d  lea     r8, [rsp+3B0h+hKey]; HKEY *
0x180065c72  lea     rdx, [rbp+2B0h+var_130]; char *
0x180065c79  mov     rcx, r14; HKEY
0x180065c7c  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180065c81  mov     edi, eax
0x180065c83  mov     rax, [rsp+3B0h+hKey]
0x180065c88  test    edi, edi
0x180065c8a  cmovnz  rax, rbx
0x180065c8e  mov     [rsp+3B0h+hKey], rax
0x180065c93  jnz     loc_180065A44
0x180065c99  lea     rcx, [rbp+2B0h+String]; lpString
0x180065c9d  call    cs:__imp_lstrlenA
0x180065ca3  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180065ca8  lea     rdx, aAppid; "AppID"
0x180065caf  add     eax, r13d
0x180065cb2  mov     r9d, r13d; dwType
0x180065cb5  xor     r8d, r8d; Reserved
  ... truncated ...
```
