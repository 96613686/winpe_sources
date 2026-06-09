# IMTLRegister(Project *,ITypeLib *,tagIMTLREG *,char *,ulong)

- ea: `0x180063ad4`
- end: `0x180063f83`
- name: `?IMTLRegister@@YAJPEAVProject@@PEAUITypeLib@@PEAUtagIMTLREG@@PEADK@Z`
- size: `1199`
- prototype: `__int64 __fastcall(struct Project *, struct ITypeLib *, struct tagIMTLREG *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1800639cc`

## callees

- `0x18001606c`
- `0x18001b8b0`
- `0x18001b8c8`
- `0x18001bf20`
- `0x18001c1b0`
- `0x180026838`
- `0x180041bf0`
- `0x180059120`
- `0x18005aa78`
- `0x18005acac`
- `0x180063ad4`
- `0x180063f8c`
- `0x180064558`
- `0x180064cf0`
- `0x180064db0`
- `0x180064f44`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180063db2`
- `KERNEL32!lstrlenA` at `0x180063db2`
- `KERNEL32!GetModuleFileNameA` at `0x180063eb4`
- `KERNEL32!GetModuleFileNameA` at `0x180063eb4`
- `USER32!wsprintfA` at `0x180063e08`
- `USER32!wsprintfA` at `0x180063e08`
- `ADVAPI32!RegSetValueA` at `0x180063dd3`
- `ADVAPI32!RegSetValueA` at `0x180063dd3`
- `ADVAPI32!RegOpenKeyA` at `0x180063e21`
- `ADVAPI32!RegOpenKeyA` at `0x180063e21`
- `ADVAPI32!RegCloseKey` at `0x180063e2f`
- `ADVAPI32!RegCloseKey` at `0x180063f11`
- `ADVAPI32!RegCloseKey` at `0x180063f21`
- `ADVAPI32!RegCloseKey` at `0x180063e2f`
- `ADVAPI32!RegCloseKey` at `0x180063f11`
- `ADVAPI32!RegCloseKey` at `0x180063f21`
- `ole32!CoGetCurrentProcess` at `0x180063ded`
- `ole32!CoGetCurrentProcess` at `0x180063ded`
- `OLEAUT32!__imp_SysFreeString` at `0x180063cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180063f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180063f35`
- `OLEAUT32!__imp_SysFreeString` at `0x180063cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180063f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180063f35`

## pseudocode

```c
__int64 __fastcall IMTLRegister(
        struct Project *a1,
        struct ITypeLib *a2,
        struct tagIMTLREG *a3,
        char *a4,
        unsigned int a5)
{
  LSTATUS TempFile; // ebx
  unsigned int v10; // r14d
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  OLECHAR *v23; // rcx
  wchar_t *v24; // rax
  const char *v25; // rdx
  __int64 v26; // rax
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  HKEY v32; // rbx
  LSTATUS v33; // eax
  HKEY v34; // rcx
  const CHAR *v35; // rax
  DWORD cbData; // ebx
  const CHAR *v37; // rax
  int v38; // eax
  DWORD CurrentProcess; // eax
  HKEY v40; // rbx
  LSTATUS v41; // eax
  HKEY v42; // rcx
  HKEY v43; // rdx
  int ProjPathname; // eax
  HKEY phkResult; // [rsp+30h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp+10h] BYREF
  BSTR v49; // [rsp+48h] [rbp+18h] BYREF
  __int64 v50; // [rsp+50h] [rbp+20h] BYREF
  _BYTE v51[24]; // [rsp+58h] [rbp+28h] BYREF
  _QWORD v52[2]; // [rsp+70h] [rbp+40h] BYREF
  CHAR *NonPrintDriveDir; // [rsp+80h] [rbp+50h]
  _BYTE v54[24]; // [rsp+88h] [rbp+58h] BYREF
  struct _GUID v55; // [rsp+A0h] [rbp+70h] BYREF
  int v56; // [rsp+B0h] [rbp+80h]
  __int16 v57; // [rsp+B4h] [rbp+84h]
  __int16 v58; // [rsp+B6h] [rbp+86h]
  __int16 v59; // [rsp+B8h] [rbp+88h]
  CHAR SubKey[32]; // [rsp+C0h] [rbp+90h] BYREF
  CHAR Filename[2048]; // [rsp+E0h] [rbp+B0h] BYREF

  TempFile = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v49 = 0;
  bstrString = 0;
  CFileRep::CFileRep((CFileRep *)v51);
  CFileRep::CFileRep((CFileRep *)v54);
  v10 = *(_DWORD *)a3 ^ a5;
  *(_DWORD *)a3 |= v10;
  if ( (v10 & 3) != 0 )
  {
    if ( (v10 & 4) != 0 )
    {
      TempFile = _MakeTempFile((wchar_t **)a3 + 1);
      if ( TempFile < 0 )
        goto LABEL_54;
      a4 = (char *)*((_QWORD *)a3 + 1);
      if ( ((unsigned __int64)a4 & 0xFFFFFFFFFFFF0000uLL) != 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&a4[2 * v11] );
        v12 = 2 * v11 + 1;
        v13 = v12 + 15;
        if ( v12 + 15 < v12 )
          v13 = 0xFFFFFFFFFFFFFF0LL;
        v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
        v15 = alloca(v14);
        v16 = alloca(v14);
        a4 = strcpyAfromW((char *)&phkResult, *((const wchar_t **)a3 + 1));
      }
    }
    else
    {
      v23 = (OLECHAR *)*((_QWORD *)a3 + 1);
      if ( v23 )
        SysFreeString(v23);
      v24 = AllocBstrWfromA(a4);
      *((_QWORD *)a3 + 1) = v24;
      if ( !v24 )
        goto LABEL_23;
    }
  }
  if ( (v10 & 1) == 0 )
    goto LABEL_51;
  TempFile = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))a2->lpVtbl->GetLibAttr)(a2, &v50);
  if ( TempFile >= 0 )
  {
    v57 = *(_WORD *)(v50 + 24);
    v58 = *(_WORD *)(v50 + 26);
    v56 = *(_DWORD *)(v50 + 16);
    v55 = *(struct _GUID *)v50;
    v59 = *(_WORD *)(v50 + 28);
    ((void (__fastcall *)(struct ITypeLib *))a2->lpVtbl->ReleaseTLibAttr)(a2);
    TempFile = ((__int64 (__fastcall *)(struct ITypeLib *, __int64, _QWORD, BSTR *, _QWORD, BSTR *))a2->lpVtbl->GetDocumentation)(
                 a2,
                 0xFFFFFFFFLL,
                 0,
                 &bstrString,
                 0,
                 &v49);
    if ( TempFile >= 0 )
    {
      if ( bstrString )
      {
        if ( ((unsigned __int64)bstrString & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          v17 = -1;
          do
            ++v17;
          while ( bstrString[v17] );
          v18 = 2 * v17 + 1;
          v19 = v18 + 15;
          if ( v18 + 15 < v18 )
            v19 = 0xFFFFFFFFFFFFFF0LL;
          v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
          v21 = alloca(v20);
          v22 = alloca(v20);
          v52[0] = strcpyAfromW((char *)&phkResult, bstrString);
        }
        else
        {
          v52[0] = bstrString;
        }
      }
      else
      {
        v52[0] = Rby_szNull;
      }
      v25 = (const char *)v49;
      if ( v49 )
      {
        if ( ((unsigned __int64)v49 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v49[v26] );
          v27 = 2 * v26 + 1;
          v28 = v27 + 15;
          if ( v27 + 15 < v27 )
            v28 = 0xFFFFFFFFFFFFFF0LL;
          v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
          v30 = alloca(v29);
          v31 = alloca(v29);
          v25 = strcpyAfromW((char *)&phkResult, v49);
        }
        if ( !(unsigned int)CFileRep::SetFullPath((CFileRep *)v51, v25) )
          goto LABEL_23;
        NonPrintDriveDir = (CHAR *)CFileRep::GetNonPrintDriveDir((CFileRep *)v51);
      }
      else
      {
        NonPrintDriveDir = Rby_szNull;
      }
      v32 = hKey;
      v33 = FastRegCreateKey(HKEY_CLASSES_ROOT, aVbkeysave5, &hKey);
      v34 = hKey;
      if ( v33 )
        v34 = v32;
      hKey = v34;
      TempFile = HrFromRegError(v33);
      if ( TempFile < 0 )
        goto LABEL_54;
      v35 = IntlLpstrStringOfID(270);
      cbData = lstrlenA(v35);
      v37 = IntlLpstrStringOfID(270);
      RegSetValueA(hKey, 0, 1u, v37, cbData);
      while ( 1 )
      {
        v38 = dword_1803FA610;
        *((_DWORD *)a3 + 5) = dword_1803FA610;
        dword_1803FA610 = v38 + 1;
        CurrentProcess = CoGetCurrentProcess();
        wsprintfA(SubKey, "%08lx.T%08lx", CurrentProcess, *((_DWORD *)a3 + 5));
        v40 = phkResult;
        if ( RegOpenKeyA(hKey, SubKey, &phkResult) )
          break;
        RegCloseKey(phkResult);
      }
      phkResult = v40;
      v41 = FastRegCreateKey(hKey, SubKey, &phkResult);
      v42 = phkResult;
      if ( v41 )
        v42 = v40;
      phkResult = v42;
      TempFile = HrFromRegError(v41);
      if ( TempFile < 0 )
      {
        phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        goto LABEL_53;
      }
      v43 = phkResult;
      *((_DWORD *)a3 + 6) = 1;
      TempFile = _SaveTlKeys(&v55, v43);
      if ( TempFile < 0 )
        goto LABEL_54;
      v52[1] = a4;
      if ( *((_QWORD *)a1 + 56) )
      {
        ProjPathname = Project::GetProjPathname(a1, (struct CFileRep *)v54);
      }
      else
      {
        GetModuleFileNameA(Rby_hinstExe, Filename, 0x800u);
        ProjPathname = CFileRep::SetFullPath((CFileRep *)v54, Filename);
      }
      if ( ProjPathname )
      {
        TempFile = _DoTlRegistration((struct tagtlRegInfo *)v52);
        if ( TempFile >= 0 )
        {
LABEL_51:
          if ( (v10 & 2) != 0 )
            TempFile = _IMTLRegisterROT(a2, a4, (unsigned int *)a3 + 4);
LABEL_53:
          if ( TempFile >= 0 )
            goto LABEL_55;
          goto LABEL_54;
        }
        goto LABEL_54;
      }
LABEL_23:
      TempFile = -2147024882;
    }
  }
LABEL_54:
  IMTLUnRegister(a3, v10);
LABEL_55:
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(phkResult);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  SysFreeString(bstrString);
  SysFreeString(v49);
  CFileRep::~CFileRep((CFileRep *)v54);
  CFileRep::~CFileRep((CFileRep *)v51);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x180063ad4  push    rbp
0x180063ad6  push    rbx
0x180063ad7  push    rsi
0x180063ad8  push    rdi
0x180063ad9  push    r12
0x180063adb  push    r13
0x180063add  push    r14
0x180063adf  push    r15
0x180063ae1  mov     eax, 8F8h
0x180063ae6  call    _alloca_probe
0x180063aeb  sub     rsp, rax
0x180063aee  lea     rbp, [rsp+30h]
0x180063af3  mov     rax, cs:__security_cookie
0x180063afa  xor     rax, rbp
0x180063afd  mov     [rbp+900h+var_50], rax
0x180063b04  xor     r13d, r13d
0x180063b07  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063b0b  mov     r12, rcx
0x180063b0e  lea     rcx, [rbp+900h+var_8D8]; this
0x180063b12  mov     rsi, r9
0x180063b15  mov     rdi, r8
0x180063b18  mov     r15, rdx
0x180063b1b  mov     ebx, r13d
0x180063b1e  mov     [rbp+900h+phkResult], rax
0x180063b22  mov     [rbp+900h+hKey], rax
0x180063b26  mov     [rbp+900h+var_8E8], r13
0x180063b2a  mov     [rbp+900h+bstrString], r13
0x180063b2e  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x180063b33  lea     rcx, [rbp+900h+var_8A8]; this
0x180063b37  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x180063b3c  mov     r11d, [rdi]
0x180063b3f  mov     r14d, [rbp+900h+arg_20]
0x180063b46  xor     r14d, r11d
0x180063b49  or      r11d, r14d
0x180063b4c  mov     [rdi], r11d
0x180063b4f  test    r14b, 3
0x180063b53  jz      short loc_180063BC7
0x180063b55  test    r14b, 4
0x180063b59  jz      loc_180063CB8
0x180063b5f  lea     rcx, [rdi+8]; wchar_t **
0x180063b63  call    ?_MakeTempFile@@YAJPEAPEA_W@Z; _MakeTempFile(wchar_t * *)
0x180063b68  mov     ebx, eax
0x180063b6a  test    eax, eax
0x180063b6c  js      loc_180063EFC
0x180063b72  mov     rsi, [rdi+8]
0x180063b76  test    rsi, 0FFFFFFFFFFFF0000h
0x180063b7d  jz      short loc_180063BC7
0x180063b7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063b83  inc     rax
0x180063b86  cmp     [rsi+rax*2], r13w
0x180063b8b  jnz     short loc_180063B83
0x180063b8d  lea     rax, ds:1[rax*2]
0x180063b95  lea     rcx, [rax+0Fh]
0x180063b99  cmp     rcx, rax
0x180063b9c  ja      short loc_180063BA8
0x180063b9e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180063ba8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180063bac  mov     rax, rcx
0x180063baf  call    _alloca_probe
0x180063bb4  sub     rsp, rcx
0x180063bb7  mov     rdx, rsi; wchar_t *
0x180063bba  lea     rcx, [rsp+930h+phkResult]; char *
0x180063bbf  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x180063bc4  mov     rsi, rax
0x180063bc7  test    r14b, 1
0x180063bcb  jz      loc_180063EE1
0x180063bd1  mov     rax, [r15]
0x180063bd4  lea     rdx, [rbp+900h+var_8E0]
0x180063bd8  mov     rcx, r15
0x180063bdb  call    qword ptr [rax+38h]
0x180063bde  mov     ebx, eax
0x180063be0  test    eax, eax
0x180063be2  js      loc_180063EFC
0x180063be8  mov     rdx, [rbp+900h+var_8E0]
0x180063bec  mov     rcx, r15
0x180063bef  movzx   eax, word ptr [rdx+18h]
0x180063bf3  mov     [rbp+900h+var_87C], ax
0x180063bfa  movzx   eax, word ptr [rdx+1Ah]
0x180063bfe  mov     [rbp+900h+var_87A], ax
0x180063c05  mov     eax, [rdx+10h]
0x180063c08  mov     [rbp+900h+var_880], eax
0x180063c0e  movups  xmm0, xmmword ptr [rdx]
0x180063c11  movdqu  xmmword ptr [rbp+900h+var_890.Data1], xmm0
0x180063c16  movzx   eax, word ptr [rdx+1Ch]
0x180063c1a  mov     [rbp+900h+var_878], ax
0x180063c21  mov     rax, [r15]
0x180063c24  call    qword ptr [rax+60h]
0x180063c27  mov     r11, [r15]
0x180063c2a  lea     rax, [rbp+900h+var_8E8]
0x180063c2e  mov     [rsp+930h+var_908], rax
0x180063c33  lea     r9, [rbp+900h+bstrString]
0x180063c37  xor     r8d, r8d
0x180063c3a  or      edx, 0FFFFFFFFh
0x180063c3d  mov     rcx, r15
0x180063c40  mov     qword ptr [rsp+930h+cbData], r13
0x180063c45  call    qword ptr [r11+48h]
0x180063c49  mov     ebx, eax
0x180063c4b  test    eax, eax
0x180063c4d  js      loc_180063EFC
0x180063c53  mov     rdx, [rbp+900h+bstrString]
0x180063c57  lea     rbx, ?Rby_szNull@@3PADA; char near * Rby_szNull
0x180063c5e  test    rdx, rdx
0x180063c61  jz      loc_180063CEC
0x180063c67  test    rdx, 0FFFFFFFFFFFF0000h
0x180063c6e  jz      short loc_180063CE6
0x180063c70  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063c74  inc     rax
0x180063c77  cmp     [rdx+rax*2], r13w
0x180063c7c  jnz     short loc_180063C74
0x180063c7e  lea     rax, ds:1[rax*2]
0x180063c86  lea     rcx, [rax+0Fh]
0x180063c8a  cmp     rcx, rax
0x180063c8d  ja      short loc_180063C99
0x180063c8f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180063c99  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180063c9d  mov     rax, rcx
0x180063ca0  call    _alloca_probe
0x180063ca5  sub     rsp, rcx
0x180063ca8  lea     rcx, [rsp+930h+phkResult]; char *
0x180063cad  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x180063cb2  mov     [rbp+900h+var_8C0], rax
0x180063cb6  jmp     short loc_180063CF0
0x180063cb8  mov     rcx, [rdi+8]; bstrString
0x180063cbc  test    rcx, rcx
0x180063cbf  jz      short loc_180063CC7
0x180063cc1  call    cs:__imp_SysFreeString
0x180063cc7  mov     rcx, rsi; char *
0x180063cca  call    ?AllocBstrWfromA@@YAPEA_WPEBD@Z; AllocBstrWfromA(char const *)
0x180063ccf  mov     [rdi+8], rax
0x180063cd3  test    rax, rax
0x180063cd6  jnz     loc_180063BC7
0x180063cdc  mov     ebx, 8007000Eh
0x180063ce1  jmp     loc_180063EFC
0x180063ce6  mov     [rbp+900h+var_8C0], rdx
0x180063cea  jmp     short loc_180063CF0
0x180063cec  mov     [rbp+900h+var_8C0], rbx
0x180063cf0  mov     rdx, [rbp+900h+var_8E8]
0x180063cf4  test    rdx, rdx
0x180063cf7  jnz     short loc_180063CFF
0x180063cf9  mov     [rbp+900h+var_8B0], rbx
0x180063cfd  jmp     short loc_180063D67
0x180063cff  test    rdx, 0FFFFFFFFFFFF0000h
0x180063d06  jz      short loc_180063D4D
0x180063d08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180063d0c  inc     rax
0x180063d0f  cmp     [rdx+rax*2], r13w
0x180063d14  jnz     short loc_180063D0C
0x180063d16  lea     rax, ds:1[rax*2]
0x180063d1e  lea     rcx, [rax+0Fh]
0x180063d22  cmp     rcx, rax
0x180063d25  ja      short loc_180063D31
0x180063d27  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180063d31  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180063d35  mov     rax, rcx
0x180063d38  call    _alloca_probe
0x180063d3d  sub     rsp, rcx
0x180063d40  lea     rcx, [rsp+930h+phkResult]; char *
0x180063d45  call    ?strcpyAfromW@@YAPEADPEADPEB_W@Z; strcpyAfromW(char *,wchar_t const *)
0x180063d4a  mov     rdx, rax; char *
0x180063d4d  lea     rcx, [rbp+900h+var_8D8]; this
0x180063d51  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x180063d56  test    eax, eax
0x180063d58  jz      short loc_180063CDC
0x180063d5a  lea     rcx, [rbp+900h+var_8D8]; this
0x180063d5e  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x180063d63  mov     [rbp+900h+var_8B0], rax
0x180063d67  mov     rbx, [rbp+900h+hKey]
0x180063d6b  lea     r8, [rbp+900h+hKey]; HKEY *
0x180063d6f  lea     rdx, aVbkeysave5; "VBKeySave5"
0x180063d76  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x180063d7d  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180063d82  mov     rcx, [rbp+900h+hKey]
0x180063d86  test    eax, eax
0x180063d88  cmovnz  rcx, rbx
0x180063d8c  mov     [rbp+900h+hKey], rcx
0x180063d90  mov     ecx, eax; int
0x180063d92  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x180063d97  mov     ebx, eax
0x180063d99  test    eax, eax
0x180063d9b  js      loc_180063EFC
0x180063da1  mov     r13d, 10Eh
0x180063da7  mov     ecx, r13d; int
0x180063daa  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180063daf  mov     rcx, rax; lpString
0x180063db2  call    cs:__imp_lstrlenA
0x180063db8  mov     ecx, r13d; int
0x180063dbb  mov     ebx, eax
0x180063dbd  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180063dc2  mov     rcx, [rbp+900h+hKey]; hKey
0x180063dc6  xor     edx, edx; lpSubKey
0x180063dc8  mov     r9, rax; lpData
0x180063dcb  mov     [rsp+930h+cbData], ebx; cbData
0x180063dcf  lea     r8d, [rdx+1]; dwType
0x180063dd3  call    cs:__imp_RegSetValueA
0x180063dd9  xor     r13d, r13d
0x180063ddc  mov     eax, cs:dword_1803FA610
0x180063de2  mov     [rdi+14h], eax
0x180063de5  inc     eax
0x180063de7  mov     cs:dword_1803FA610, eax
0x180063ded  call    cs:__imp_CoGetCurrentProcess
0x180063df3  mov     r9d, [rdi+14h]
0x180063df7  lea     rdx, a08lxT08lx; "%08lx.T%08lx"
0x180063dfe  lea     rcx, [rbp+900h+SubKey]; LPSTR
0x180063e05  mov     r8d, eax
0x180063e08  call    cs:__imp_wsprintfA
0x180063e0e  mov     rcx, [rbp+900h+hKey]; hKey
0x180063e12  mov     rbx, [rbp+900h+phkResult]
0x180063e16  lea     r8, [rbp+900h+phkResult]; phkResult
0x180063e1a  lea     rdx, [rbp+900h+SubKey]; lpSubKey
0x180063e21  call    cs:__imp_RegOpenKeyA
0x180063e27  test    eax, eax
0x180063e29  jnz     short loc_180063E37
0x180063e2b  mov     rcx, [rbp+900h+phkResult]; hKey
0x180063e2f  call    cs:__imp_RegCloseKey
0x180063e35  jmp     short loc_180063DDC
0x180063e37  mov     rcx, [rbp+900h+hKey]; HKEY
0x180063e3b  lea     r8, [rbp+900h+phkResult]; HKEY *
0x180063e3f  lea     rdx, [rbp+900h+SubKey]; char *
0x180063e46  mov     [rbp+900h+phkResult], rbx
0x180063e4a  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180063e4f  mov     rcx, [rbp+900h+phkResult]
0x180063e53  test    eax, eax
0x180063e55  cmovnz  rcx, rbx
0x180063e59  mov     [rbp+900h+phkResult], rcx
0x180063e5d  mov     ecx, eax; int
0x180063e5f  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x180063e64  mov     ebx, eax
0x180063e66  test    eax, eax
0x180063e68  jns     short loc_180063E74
0x180063e6a  or      [rbp+900h+phkResult], 0FFFFFFFFFFFFFFFFh
0x180063e6f  jmp     loc_180063EF8
0x180063e74  mov     rdx, [rbp+900h+phkResult]; HKEY
0x180063e78  lea     rcx, [rbp+900h+var_890]; struct _GUID *
0x180063e7c  mov     dword ptr [rdi+18h], 1
0x180063e83  call    ?_SaveTlKeys@@YAJAEAU_GUID@@PEAUHKEY__@@@Z; _SaveTlKeys(_GUID &,HKEY__ *)
0x180063e88  mov     ebx, eax
0x180063e8a  test    eax, eax
0x180063e8c  js      short loc_180063EFC
0x180063e8e  mov     [rbp+900h+var_8B8], rsi
0x180063e92  cmp     [r12+1C0h], r13
0x180063e9a  jnz     loc_180063F72
0x180063ea0  mov     rcx, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; hModule
0x180063ea7  lea     rdx, [rbp+900h+Filename]; lpFilename
0x180063eae  mov     r8d, 800h; nSize
0x180063eb4  call    cs:__imp_GetModuleFileNameA
0x180063eba  lea     rdx, [rbp+900h+Filename]; char *
0x180063ec1  lea     rcx, [rbp+900h+var_8A8]; this
0x180063ec5  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x180063eca  test    eax, eax
0x180063ecc  jz      loc_180063CDC
0x180063ed2  lea     rcx, [rbp+900h+var_8C0]; struct tagtlRegInfo *
0x180063ed6  call    ?_DoTlRegistration@@YAJPEAUtagtlRegInfo@@@Z; _DoTlRegistration(tagtlRegInfo *)
0x180063edb  mov     ebx, eax
0x180063edd  test    eax, eax
0x180063edf  js      short loc_180063EFC
0x180063ee1  test    r14b, 2
0x180063ee5  jz      short loc_180063EF8
0x180063ee7  lea     r8, [rdi+10h]; unsigned int *
0x180063eeb  mov     rdx, rsi; char *
0x180063eee  mov     rcx, r15; struct ITypeLib *
0x180063ef1  call    ?_IMTLRegisterROT@@YAJPEAUITypeLib@@PEADPEAK@Z; _IMTLRegisterROT(ITypeLib *,char *,ulong *)
0x180063ef6  mov     ebx, eax
0x180063ef8  test    ebx, ebx
0x180063efa  jns     short loc_180063F07
0x180063efc  mov     edx, r14d; unsigned int
0x180063eff  mov     rcx, rdi; struct tagIMTLREG *
0x180063f02  call    ?IMTLUnRegister@@YAKPEAUtagIMTLREG@@K@Z; IMTLUnRegister(tagIMTLREG *,ulong)
0x180063f07  mov     rcx, [rbp+900h+phkResult]; hKey
0x180063f0b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180063f0f  jz      short loc_180063F17
0x180063f11  call    cs:__imp_RegCloseKey
0x180063f17  mov     rcx, [rbp+900h+hKey]; hKey
0x180063f1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180063f1f  jz      short loc_180063F27
0x180063f21  call    cs:__imp_RegCloseKey
0x180063f27  mov     rcx, [rbp+900h+bstrString]; bstrString
0x180063f2b  call    cs:__imp_SysFreeString
0x180063f31  mov     rcx, [rbp+900h+var_8E8]; bstrString
0x180063f35  call    cs:__imp_SysFreeString
0x180063f3b  lea     rcx, [rbp+900h+var_8A8]; this
0x180063f3f  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x180063f44  lea     rcx, [rbp+900h+var_8D8]; this
0x180063f48  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x180063f4d  mov     eax, ebx
0x180063f4f  mov     rcx, [rbp+900h+var_50]
0x180063f56  xor     rcx, rbp; StackCookie
0x180063f59  call    __security_check_cookie
0x180063f5e  lea     rsp, [rbp+8C8h]
0x180063f65  pop     r15
0x180063f67  pop     r14
0x180063f69  pop     r13
0x180063f6b  pop     r12
0x180063f6d  pop     rdi
0x180063f6e  pop     rsi
0x180063f6f  pop     rbx
0x180063f70  pop     rbp
0x180063f71  retn
0x180063f72  lea     rdx, [rbp+900h+var_8A8]; struct CFileRep *
0x180063f76  mov     rcx, r12; this
0x180063f79  call    ?GetProjPathname@Project@@QEAAHPEAVCFileRep@@@Z; Project::GetProjPathname(CFileRep *)
  ... truncated ...
```
