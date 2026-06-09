# CVBServer::ErrExitDesignMode(void)

- ea: `0x180063450`
- end: `0x180063862`
- name: `?ErrExitDesignMode@CVBServer@@QEAAIXZ`
- size: `1042`
- prototype: `unsigned int __fastcall(CVBServer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x180044b6c`

## callees

- `0x180015ae8`
- `0x180015b08`
- `0x180016790`
- `0x180026838`
- `0x180059120`
- `0x180060ed4`
- `0x180061f68`
- `0x180062518`
- `0x180062670`
- `0x180062920`
- `0x1800630d4`
- `0x18006310c`
- `0x180063450`
- `0x180063868`
- `0x1800639cc`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x180063514`
- `MSVCR100!strcpy_s` at `0x180063514`
- `KERNEL32!lstrlenA` at `0x1800635ac`
- `KERNEL32!lstrlenA` at `0x1800635ac`
- `KERNEL32!GetModuleFileNameA` at `0x1800634c5`
- `KERNEL32!GetModuleFileNameA` at `0x1800634c5`
- `USER32!wsprintfA` at `0x1800635ec`
- `USER32!wsprintfA` at `0x1800635ec`
- `ADVAPI32!RegSetValueA` at `0x1800635cd`
- `ADVAPI32!RegSetValueA` at `0x1800635cd`
- `ADVAPI32!RegEnumKeyA` at `0x1800636c0`
- `ADVAPI32!RegEnumKeyA` at `0x1800636c0`
- `ADVAPI32!RegDeleteKeyA` at `0x1800636e9`
- `ADVAPI32!RegDeleteKeyA` at `0x1800636e9`
- `ADVAPI32!RegCloseKey` at `0x180063691`
- `ADVAPI32!RegCloseKey` at `0x1800636cd`
- `ADVAPI32!RegCloseKey` at `0x1800637b0`
- `ADVAPI32!RegCloseKey` at `0x1800637bb`
- `ADVAPI32!RegCloseKey` at `0x180063691`
- `ADVAPI32!RegCloseKey` at `0x1800636cd`
- `ADVAPI32!RegCloseKey` at `0x1800637b0`
- `ADVAPI32!RegCloseKey` at `0x1800637bb`
- `ole32!CoGetCurrentProcess` at `0x1800635d3`
- `ole32!CoGetCurrentProcess` at `0x1800635d3`
- `ole32!CoFreeUnusedLibraries` at `0x180063817`
- `ole32!CoFreeUnusedLibraries` at `0x180063817`

## string_xrefs

- `0x18006350d`: `VB6DEBUG.DLL`

## pseudocode

```c
__int64 __fastcall CVBServer::ErrExitDesignMode(CVBServer *this)
{
  unsigned int v1; // esi
  __int64 v4; // rax
  rsize_t v5; // rdx
  char *i; // rcx
  COAServer *v7; // r14
  HKEY v8; // rbx
  int v9; // eax
  HKEY v10; // rcx
  const CHAR *v11; // rax
  DWORD cbData; // ebx
  const CHAR *v13; // rax
  DWORD CurrentProcess; // eax
  HKEY v15; // rcx
  HKEY v16; // rbx
  int v17; // eax
  HKEY v18; // rcx
  LSTATUS v19; // ebx
  unsigned int v20; // eax
  struct ITypeLib *v21; // rsi
  unsigned int v22; // ebx
  int v23; // eax
  struct ITypeLibVtbl *lpVtbl; // rax
  unsigned __int16 v25; // r15
  unsigned __int16 v26; // r12
  COAServer *v27; // rcx
  __int64 v28; // rax
  COAServer *v29; // rax
  COAServer *v30; // r14
  COAServer *v31; // r14
  int v32; // eax
  unsigned __int16 v33; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v35; // [rsp+40h] [rbp-C0h] BYREF
  struct ITypeLib *v36; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v37; // [rsp+50h] [rbp-B0h] BYREF
  CHAR v38[32]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR Filename[4096]; // [rsp+80h] [rbp-80h] BYREF

  v1 = 0;
  v36 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v35 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( *((_DWORD *)this + 12) )
    return 0;
  v38[0] = 0;
  if ( !GetModuleFileNameA(Rby_hinstExe, Filename, 0x1000u) )
    return 50253;
  v4 = -1;
  do
    ++v4;
  while ( Filename[v4] );
  v5 = 4096 - v4;
  for ( i = &Filename[v4]; i > Filename && *(i - 1) != 92; --i )
    ++v5;
  strcpy_s(i, v5, "VB6DEBUG.DLL");
  *(_DWORD *)(*((_QWORD *)this + 5) + 120LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 5) + 32LL) = 0;
  v7 = (COAServer *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 5) + 400LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 5) + 400LL));
  if ( !v7 )
    return 0;
  do
  {
    if ( (unsigned int)COAServer::FPutInRegistryForRunMode(v7) )
    {
      if ( !*((_DWORD *)this + 12) )
      {
        v8 = hKey;
        v9 = FastRegCreateKey(HKEY_CLASSES_ROOT, aVbkeysave5, &hKey);
        v10 = hKey;
        if ( v9 )
          v10 = v8;
        hKey = v10;
        v1 = ErrFromRegError(v9);
        if ( v1 )
          break;
        v11 = IntlLpstrStringOfID(270);
        cbData = lstrlenA(v11);
        v13 = IntlLpstrStringOfID(270);
        RegSetValueA(hKey, 0, 1u, v13, cbData);
        CurrentProcess = CoGetCurrentProcess();
        wsprintfA(v38, "%08lx.S%p", CurrentProcess, *((const void **)this + 5));
        RegDeleteSubKeys(hKey, v38);
        v15 = hKey;
        v16 = v35;
        *((_DWORD *)this + 12) = 1;
        v17 = FastRegCreateKey(v15, v38, &v35);
        v18 = v35;
        if ( v17 )
          v18 = v16;
        v35 = v18;
        v1 = ErrFromRegError(v17);
        if ( v1 )
          break;
      }
      v1 = COAServer::ErrVerifyNames(v7, 0);
      if ( v1 )
        break;
      v1 = COAServer::ErrSaveKeys(v7, v35);
      if ( v1 )
        break;
    }
    v7 = (COAServer *)(*(__int64 (__fastcall **)(COAServer *))(*(_QWORD *)v7 + 32LL))(v7);
  }
  while ( v7 );
  if ( !*((_DWORD *)this + 12) )
    return v1;
  if ( v1 )
  {
    if ( v35 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(v35);
    if ( v38[0] )
      RegDeleteSubKeys(hKey, v38);
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v19 = RegEnumKeyA(hKey, 0, Filename, 0x1000u);
      RegCloseKey(hKey);
      if ( v19 == 259 )
        RegDeleteKeyA(HKEY_CLASSES_ROOT, aVbkeysave5);
    }
    *((_DWORD *)this + 12) = 0;
    return v1;
  }
  v20 = CVBServer::_ErrRegisterTl(this, &v36);
  v21 = v36;
  v22 = v20;
  if ( v20 )
    goto LABEL_38;
  v23 = ((__int64 (__fastcall *)(struct ITypeLib *, struct ITypeLib **))v36->lpVtbl->GetLibAttr)(v36, &v36);
  if ( v23 < 0 )
  {
    v22 = _ErrFromHr(v23, 0xC44Du);
LABEL_38:
    v26 = v33;
    v25 = v33;
    goto LABEL_39;
  }
  lpVtbl = v21->lpVtbl;
  v25 = (unsigned __int16)v36[3].lpVtbl;
  v26 = WORD1(v36[3].lpVtbl);
  v37 = *(struct _GUID *)&v36->lpVtbl;
  ((void (__fastcall *)(struct ITypeLib *))lpVtbl->ReleaseTLibAttr)(v21);
LABEL_39:
  v27 = *(COAServer **)(*((_QWORD *)this + 5) + 400LL);
  v28 = *(_QWORD *)v27;
  while ( 1 )
  {
    v29 = (COAServer *)(*(__int64 (__fastcall **)(COAServer *))(v28 + 32))(v27);
    v30 = v29;
    if ( v22 || !v29 )
      break;
    if ( (unsigned int)COAServer::FPutInRegistryForRunMode(v29) )
      v22 = COAServer::ErrRegister(v30, Filename, &v37, v25, v26);
    v28 = *(_QWORD *)v30;
    v27 = v30;
  }
  RegCloseKey(v35);
  RegCloseKey(hKey);
  v31 = (COAServer *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 5) + 400LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 5) + 400LL));
  if ( v22 )
    goto LABEL_54;
  do
  {
    if ( !v31 )
      break;
    if ( (unsigned int)COAServer::FRegisterFactoryForRunMode(v31) )
    {
      v32 = COAServer::CFRegisterRun(v31);
      if ( v32 < 0 )
        v22 = _ErrFromHrDefault(v32);
      else
        v22 = 0;
    }
    v31 = (COAServer *)(*(__int64 (__fastcall **)(COAServer *))(*(_QWORD *)v31 + 32LL))(v31);
  }
  while ( !v22 );
  if ( v22 )
LABEL_54:
    CVBServer::EnterDesignMode(this);
  else
    CoFreeUnusedLibraries();
  if ( v21 )
    ((void (__fastcall *)(struct ITypeLib *))v21->lpVtbl->Release)(v21);
  return v22;
}

```

## disassembly

```asm
0x180063450  mov     [rsp-8+arg_8], rbx
0x180063455  mov     [rsp-8+arg_10], rsi
0x18006345a  push    rbp
0x18006345b  push    rdi
0x18006345c  push    r12
0x18006345e  push    r14
0x180063460  push    r15
0x180063462  lea     rbp, [rsp-0F90h]
0x18006346a  mov     eax, 1090h
0x18006346f  call    _alloca_probe
0x180063474  sub     rsp, rax
0x180063477  mov     rax, cs:__security_cookie
0x18006347e  xor     rax, rsp
0x180063481  mov     [rbp+0FB0h+var_30], rax
0x180063488  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006348c  xor     esi, esi
0x18006348e  mov     rdi, rcx
0x180063491  and     [rsp+10B0h+var_1068], rsi
0x180063496  mov     [rsp+10B0h+hKey], r15
0x18006349b  mov     [rsp+10B0h+var_1070], r15
0x1800634a0  cmp     [rcx+30h], esi
0x1800634a3  jz      short loc_1800634AC
0x1800634a5  xor     eax, eax
0x1800634a7  jmp     loc_180063837
0x1800634ac  mov     rcx, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; hModule
0x1800634b3  mov     r12d, 1000h
0x1800634b9  lea     rdx, [rbp+0FB0h+Filename]; lpFilename
0x1800634bd  mov     r8d, r12d; nSize
0x1800634c0  mov     [rsp+10B0h+var_1050], sil
0x1800634c5  call    cs:__imp_GetModuleFileNameA
0x1800634cb  test    eax, eax
0x1800634cd  jnz     short loc_1800634D9
0x1800634cf  mov     eax, 0C44Dh
0x1800634d4  jmp     loc_180063837
0x1800634d9  lea     rcx, [rbp+0FB0h+Filename]
0x1800634dd  mov     rax, r15
0x1800634e0  inc     rax
0x1800634e3  cmp     [rcx+rax], sil
0x1800634e7  jnz     short loc_1800634E0
0x1800634e9  lea     rcx, [rbp+0FB0h+Filename]
0x1800634ed  mov     rdx, r12
0x1800634f0  sub     rdx, rax
0x1800634f3  add     rcx, rax
0x1800634f6  jmp     short loc_180063504
0x1800634f8  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x1800634fc  jz      short loc_18006350D
0x1800634fe  dec     rcx; Destination
0x180063501  inc     rdx; SizeInBytes
0x180063504  lea     rax, [rbp+0FB0h+Filename]
0x180063508  cmp     rcx, rax
0x18006350b  ja      short loc_1800634F8
0x18006350d  lea     r8, aVb6debugDll; "VB6DEBUG.DLL"
0x180063514  call    cs:__imp_strcpy_s
0x18006351a  mov     rax, [rdi+28h]
0x18006351e  and     [rax+78h], esi
0x180063521  mov     rax, [rdi+28h]
0x180063525  and     [rax+20h], esi
0x180063528  mov     rax, [rdi+28h]
0x18006352c  mov     rcx, [rax+190h]
0x180063533  mov     rax, [rcx]
0x180063536  call    qword ptr [rax+20h]
0x180063539  mov     r14, rax
0x18006353c  test    rax, rax
0x18006353f  jz      loc_1800634A5
0x180063545  mov     rcx, r14; this
0x180063548  call    ?FPutInRegistryForRunMode@COAServer@@QEAAHXZ; COAServer::FPutInRegistryForRunMode(void)
0x18006354d  test    eax, eax
0x18006354f  jz      loc_180063661
0x180063555  cmp     dword ptr [rdi+30h], 0
0x180063559  jnz     loc_18006363E
0x18006355f  mov     rbx, [rsp+10B0h+hKey]
0x180063564  lea     r8, [rsp+10B0h+hKey]; HKEY *
0x180063569  lea     rdx, aVbkeysave5; "VBKeySave5"
0x180063570  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180063577  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x18006357c  mov     rcx, [rsp+10B0h+hKey]
0x180063581  test    eax, eax
0x180063583  cmovnz  rcx, rbx
0x180063587  mov     [rsp+10B0h+hKey], rcx
0x18006358c  mov     ecx, eax; int
0x18006358e  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x180063593  mov     esi, eax
0x180063595  test    eax, eax
0x180063597  jnz     loc_180063676
0x18006359d  mov     esi, 10Eh
0x1800635a2  mov     ecx, esi; int
0x1800635a4  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800635a9  mov     rcx, rax; lpString
0x1800635ac  call    cs:__imp_lstrlenA
0x1800635b2  mov     ecx, esi; int
0x1800635b4  mov     ebx, eax
0x1800635b6  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800635bb  mov     rcx, [rsp+10B0h+hKey]; hKey
0x1800635c0  xor     edx, edx; lpSubKey
0x1800635c2  mov     r9, rax; lpData
0x1800635c5  mov     [rsp+10B0h+cbData], ebx; cbData
0x1800635c9  lea     r8d, [rdx+1]; dwType
0x1800635cd  call    cs:__imp_RegSetValueA
0x1800635d3  call    cs:__imp_CoGetCurrentProcess
0x1800635d9  mov     r9, [rdi+28h]
0x1800635dd  lea     rdx, a08lxSP; "%08lx.S%p"
0x1800635e4  lea     rcx, [rsp+10B0h+var_1050]; LPSTR
0x1800635e9  mov     r8d, eax
0x1800635ec  call    cs:__imp_wsprintfA
0x1800635f2  mov     rcx, [rsp+10B0h+hKey]; HKEY
0x1800635f7  lea     rdx, [rsp+10B0h+var_1050]; char *
0x1800635fc  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180063601  mov     rcx, [rsp+10B0h+hKey]; HKEY
0x180063606  mov     rbx, [rsp+10B0h+var_1070]
0x18006360b  lea     r8, [rsp+10B0h+var_1070]; HKEY *
0x180063610  lea     rdx, [rsp+10B0h+var_1050]; char *
0x180063615  mov     dword ptr [rdi+30h], 1
0x18006361c  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180063621  mov     rcx, [rsp+10B0h+var_1070]
0x180063626  test    eax, eax
0x180063628  cmovnz  rcx, rbx
0x18006362c  mov     [rsp+10B0h+var_1070], rcx
0x180063631  mov     ecx, eax; int
0x180063633  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x180063638  mov     esi, eax
0x18006363a  test    eax, eax
0x18006363c  jnz     short loc_180063676
0x18006363e  xor     edx, edx; int
0x180063640  mov     rcx, r14; this
0x180063643  call    ?ErrVerifyNames@COAServer@@QEAAIH@Z; COAServer::ErrVerifyNames(int)
0x180063648  mov     esi, eax
0x18006364a  test    eax, eax
0x18006364c  jnz     short loc_180063676
0x18006364e  mov     rdx, [rsp+10B0h+var_1070]; HKEY
0x180063653  mov     rcx, r14; this
0x180063656  call    ?ErrSaveKeys@COAServer@@QEAAIPEAUHKEY__@@@Z; COAServer::ErrSaveKeys(HKEY__ *)
0x18006365b  mov     esi, eax
0x18006365d  test    eax, eax
0x18006365f  jnz     short loc_180063676
0x180063661  mov     rax, [r14]
0x180063664  mov     rcx, r14
0x180063667  call    qword ptr [rax+20h]
0x18006366a  mov     r14, rax
0x18006366d  test    rax, rax
0x180063670  jnz     loc_180063545
0x180063676  cmp     dword ptr [rdi+30h], 0
0x18006367a  jnz     short loc_180063683
0x18006367c  mov     eax, esi
0x18006367e  jmp     loc_180063837
0x180063683  test    esi, esi
0x180063685  jz      short loc_1800636F5
0x180063687  mov     rcx, [rsp+10B0h+var_1070]; hKey
0x18006368c  cmp     rcx, r15
0x18006368f  jz      short loc_180063697
0x180063691  call    cs:__imp_RegCloseKey
0x180063697  cmp     [rsp+10B0h+var_1050], 0
0x18006369c  jz      short loc_1800636AD
0x18006369e  mov     rcx, [rsp+10B0h+hKey]; HKEY
0x1800636a3  lea     rdx, [rsp+10B0h+var_1050]; char *
0x1800636a8  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x1800636ad  mov     rcx, [rsp+10B0h+hKey]; hKey
0x1800636b2  cmp     rcx, r15
0x1800636b5  jz      short loc_1800636EF
0x1800636b7  lea     r8, [rbp+0FB0h+Filename]; lpName
0x1800636bb  mov     r9d, r12d; cchName
0x1800636be  xor     edx, edx; dwIndex
0x1800636c0  call    cs:__imp_RegEnumKeyA
0x1800636c6  mov     rcx, [rsp+10B0h+hKey]; hKey
0x1800636cb  mov     ebx, eax
0x1800636cd  call    cs:__imp_RegCloseKey
0x1800636d3  cmp     ebx, 103h
0x1800636d9  jnz     short loc_1800636EF
0x1800636db  lea     rdx, aVbkeysave5; "VBKeySave5"
0x1800636e2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800636e9  call    cs:__imp_RegDeleteKeyA
0x1800636ef  and     dword ptr [rdi+30h], 0
0x1800636f3  jmp     short loc_18006367C
0x1800636f5  lea     rdx, [rsp+10B0h+var_1068]; struct ITypeLib **
0x1800636fa  mov     rcx, rdi; this
0x1800636fd  call    ?_ErrRegisterTl@CVBServer@@AEAAIPEAPEAUITypeLib@@@Z; CVBServer::_ErrRegisterTl(ITypeLib * *)
0x180063702  mov     rsi, [rsp+10B0h+var_1068]
0x180063707  mov     ebx, eax
0x180063709  test    eax, eax
0x18006370b  jnz     short loc_180063751
0x18006370d  mov     r8, [rsi]
0x180063710  lea     rdx, [rsp+10B0h+var_1068]
0x180063715  mov     rcx, rsi
0x180063718  call    qword ptr [r8+38h]
0x18006371c  test    eax, eax
0x18006371e  js      short loc_180063743
0x180063720  mov     rdx, [rsp+10B0h+var_1068]
0x180063725  mov     rax, [rsi]
0x180063728  mov     rcx, rsi
0x18006372b  movzx   r15d, word ptr [rdx+18h]
0x180063730  movzx   r12d, word ptr [rdx+1Ah]
0x180063735  movups  xmm0, xmmword ptr [rdx]
0x180063738  movdqu  xmmword ptr [rsp+10B0h+var_1060.Data1], xmm0
0x18006373e  call    qword ptr [rax+60h]
0x180063741  jmp     short loc_18006375D
0x180063743  mov     edx, 0C44Dh; unsigned int
0x180063748  mov     ecx, eax; int
0x18006374a  call    ?_ErrFromHr@@YAIJI@Z; _ErrFromHr(long,uint)
0x18006374f  mov     ebx, eax
0x180063751  movzx   r12d, [rsp+10B0h+var_1080]
0x180063757  movzx   r15d, [rsp+10B0h+var_1080]
0x18006375d  mov     rax, [rdi+28h]
0x180063761  mov     rcx, [rax+190h]
0x180063768  mov     rax, [rcx]
0x18006376b  jmp     short loc_1800637A1
0x18006376d  test    r14, r14
0x180063770  jz      short loc_1800637AB
0x180063772  mov     rcx, r14; this
0x180063775  call    ?FPutInRegistryForRunMode@COAServer@@QEAAHXZ; COAServer::FPutInRegistryForRunMode(void)
0x18006377a  test    eax, eax
0x18006377c  jz      short loc_18006379B
0x18006377e  lea     r8, [rsp+10B0h+var_1060]; struct _GUID *
0x180063783  lea     rdx, [rbp+0FB0h+Filename]; char *
0x180063787  movzx   r9d, r15w; unsigned __int16
0x18006378b  mov     rcx, r14; this
0x18006378e  mov     word ptr [rsp+10B0h+cbData], r12w; unsigned __int16
0x180063794  call    ?ErrRegister@COAServer@@QEAAIPEADAEBU_GUID@@GG@Z; COAServer::ErrRegister(char *,_GUID const &,ushort,ushort)
0x180063799  mov     ebx, eax
0x18006379b  mov     rax, [r14]
0x18006379e  mov     rcx, r14
0x1800637a1  call    qword ptr [rax+20h]
0x1800637a4  mov     r14, rax
0x1800637a7  test    ebx, ebx
0x1800637a9  jz      short loc_18006376D
0x1800637ab  mov     rcx, [rsp+10B0h+var_1070]; hKey
0x1800637b0  call    cs:__imp_RegCloseKey
0x1800637b6  mov     rcx, [rsp+10B0h+hKey]; hKey
0x1800637bb  call    cs:__imp_RegCloseKey
0x1800637c1  mov     r11, [rdi+28h]
0x1800637c5  mov     rcx, [r11+190h]
0x1800637cc  mov     rax, [rcx]
0x1800637cf  call    qword ptr [rax+20h]
0x1800637d2  mov     r14, rax
0x1800637d5  test    ebx, ebx
0x1800637d7  jnz     short loc_18006381F
0x1800637d9  test    r14, r14
0x1800637dc  jz      short loc_180063813
0x1800637de  mov     rcx, r14; this
0x1800637e1  call    ?FRegisterFactoryForRunMode@COAServer@@QEAAHXZ; COAServer::FRegisterFactoryForRunMode(void)
0x1800637e6  test    eax, eax
0x1800637e8  jz      short loc_180063803
0x1800637ea  mov     rcx, r14; this
0x1800637ed  call    ?CFRegisterRun@COAServer@@QEAAJXZ; COAServer::CFRegisterRun(void)
0x1800637f2  test    eax, eax
0x1800637f4  js      short loc_1800637FA
0x1800637f6  xor     ebx, ebx
0x1800637f8  jmp     short loc_180063803
0x1800637fa  mov     ecx, eax; int
0x1800637fc  call    ?_ErrFromHrDefault@@YAIJ@Z; _ErrFromHrDefault(long)
0x180063801  mov     ebx, eax
0x180063803  mov     rax, [r14]
0x180063806  mov     rcx, r14
0x180063809  call    qword ptr [rax+20h]
0x18006380c  mov     r14, rax
0x18006380f  test    ebx, ebx
0x180063811  jz      short loc_1800637D9
0x180063813  test    ebx, ebx
0x180063815  jnz     short loc_18006381F
0x180063817  call    cs:__imp_CoFreeUnusedLibraries
0x18006381d  jmp     short loc_180063827
0x18006381f  mov     rcx, rdi; this
0x180063822  call    ?EnterDesignMode@CVBServer@@QEAAXXZ; CVBServer::EnterDesignMode(void)
0x180063827  test    rsi, rsi
0x18006382a  jz      short loc_180063835
0x18006382c  mov     rax, [rsi]
0x18006382f  mov     rcx, rsi
0x180063832  call    qword ptr [rax+10h]
0x180063835  mov     eax, ebx
0x180063837  mov     rcx, [rbp+0FB0h+var_30]
0x18006383e  xor     rcx, rsp; StackCookie
0x180063841  call    __security_check_cookie
0x180063846  lea     r11, [rsp+10B0h+var_20]
0x18006384e  mov     rbx, [r11+38h]
0x180063852  mov     rsi, [r11+40h]
0x180063856  mov     rsp, r11
0x180063859  pop     r15
0x18006385b  pop     r14
0x18006385d  pop     r12
0x18006385f  pop     rdi
0x180063860  pop     rbp
0x180063861  retn
```
