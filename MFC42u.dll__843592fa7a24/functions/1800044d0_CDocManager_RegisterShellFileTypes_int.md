# CDocManager::RegisterShellFileTypes(int)

- ea: `0x1800044d0`
- end: `0x1800049c2`
- name: `?RegisterShellFileTypes@CDocManager@@UEAAXH@Z`
- size: `1266`
- prototype: `void __fastcall(CDocManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800044d0`
- `0x1800049c8`
- `0x18000b9e0`
- `0x18000bf30`
- `0x18000c0a0`
- `0x18000c590`
- `0x18000c860`
- `0x18000ceb0`
- `0x18000d960`
- `0x180013330`
- `0x180019290`
- `0x180020220`
- `0x180038490`
- `0x1800d7010`

## import_xrefs

- `USER32!DestroyIcon` at `0x1800045ae`
- `USER32!DestroyIcon` at `0x1800045ae`
- `SHELL32!ExtractIconW` at `0x18000458a`
- `SHELL32!ExtractIconW` at `0x18000458a`
- `ADVAPI32!RegQueryValueW` at `0x1800048c2`
- `ADVAPI32!RegQueryValueW` at `0x1800048c2`

## string_xrefs

- `0x1800047d4`: `command`
- `0x18000480b`: `command`
- `0x18000483e`: `command`
- `0x1800046f9`: `%s\shell\open\%s`
- `0x1800047df`: `%s\shell\open\%s`
- `0x18000470c`: `[open("%1")]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CDocManager::RegisterShellFileTypes(CDocManager *this, int a2)
{
  struct AFX_MODULE_STATE *ModuleState; // rax
  UINT v5; // r14d
  CObList *v6; // r15
  __int64 v7; // rsi
  struct AFX_MODULE_STATE *v8; // rax
  HICON IconW; // rbx
  const unsigned __int16 *v10; // rdx
  BYTE **v11; // rcx
  WCHAR *Buffer; // rax
  LSTATUS ValueW; // ebx
  LPCWSTR v14; // rax
  int v15; // ecx
  int v16; // r8d
  LPCWSTR lpSubKey; // [rsp+20h] [rbp-40h] BYREF
  LPCWSTR pszExeFileName; // [rsp+28h] [rbp-38h] BYREF
  BYTE *v19; // [rsp+30h] [rbp-30h] BYREF
  BYTE *lpData; // [rsp+38h] [rbp-28h] BYREF
  BYTE *v21; // [rsp+40h] [rbp-20h] BYREF
  BYTE *v22; // [rsp+48h] [rbp-18h] BYREF
  BYTE *v23; // [rsp+50h] [rbp-10h] BYREF
  struct __POSITION *v24; // [rsp+58h] [rbp-8h] BYREF
  LPCWSTR cbData; // [rsp+90h] [rbp+30h] BYREF
  LPCWSTR v26; // [rsp+A0h] [rbp+40h] BYREF
  LPCWSTR v27; // [rsp+A8h] [rbp+48h] BYREF

  pszExeFileName = _afxPchNil;
  v26 = _afxPchNil;
  ModuleState = AfxGetModuleState();
  AfxGetModuleShortFileName(*((HINSTANCE *)ModuleState + 2), (struct CString *)&pszExeFileName);
  v24 = (struct __POSITION *)*((_QWORD *)this + 2);
  v5 = 1;
  if ( v24 )
  {
    v6 = (CDocManager *)((char *)this + 8);
    while ( 1 )
    {
      v7 = (__int64)*CObList::GetNext(v6, &v24);
      CString::CString((CString *)&v19, (const struct CString *)&pszExeFileName);
      CString::CString((CString *)&v22, (const struct CString *)&pszExeFileName);
      CString::CString((CString *)&v21, (const struct CString *)&pszExeFileName);
      CString::CString((CString *)&v23, (const struct CString *)&pszExeFileName);
      if ( a2 )
      {
        cbData = _afxPchNil;
        v8 = AfxGetModuleState();
        IconW = ExtractIconW(*((HINSTANCE *)v8 + 2), pszExeFileName, v5);
        if ( IconW )
        {
          CString::Format((CString *)&cbData, (wchar_t *)L",%d", v5);
          DestroyIcon(IconW);
        }
        else
        {
          CString::Format((CString *)&cbData, (wchar_t *)L",%d", 0);
        }
        CString::operator+=(&v23, &cbData);
        CString::~CString((CString *)&cbData);
      }
      lpSubKey = _afxPchNil;
      v27 = _afxPchNil;
      lpData = (BYTE *)_afxPchNil;
      if ( !(*(unsigned int (__fastcall **)(__int64, LPCWSTR *, __int64))(*(_QWORD *)v7 + 216LL))(v7, &v27, 5)
        || !*((_DWORD *)v27 - 2) )
      {
        goto LABEL_40;
      }
      if ( !(*(unsigned int (__fastcall **)(__int64, BYTE **, __int64))(*(_QWORD *)v7 + 216LL))(v7, &lpData, 6) )
        CString::operator=(&lpData, &v27);
      if ( !_AfxSetRegKey(v27, lpData, 0) )
        goto LABEL_40;
      if ( a2 )
      {
        CString::Format((CString *)&v26, (wchar_t *)L"%s\\DefaultIcon", v27);
        if ( !_AfxSetRegKey(v26, v23, 0) )
          goto LABEL_40;
      }
      if ( (*(unsigned int (__fastcall **)(__int64, LPCWSTR *, _QWORD))(*(_QWORD *)v7 + 216LL))(v7, &v26, 0)
        && *((_DWORD *)v26 - 2) )
      {
        break;
      }
      CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\open\\%s", v27, L"ddeexec");
      if ( _AfxSetRegKey(v26, (BYTE *)L"[open(\"%1\")]", 0) )
      {
        if ( !a2 )
        {
          v10 = L" \"%1\"";
          v11 = &v19;
          goto LABEL_26;
        }
        CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\print\\%s", v27, L"ddeexec");
        if ( _AfxSetRegKey(v26, (BYTE *)L"[print(\"%1\")]", 0) )
        {
          CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\printto\\%s", v27, L"ddeexec");
          if ( _AfxSetRegKey(v26, (BYTE *)L"[printto(\"%1\",\"%2\",\"%3\",\"%4\")]", 0) )
          {
            CString::operator+=(&v19, L" /dde");
            CString::operator+=(&v22, L" /dde");
            v10 = L" /dde";
LABEL_19:
            v11 = &v21;
LABEL_26:
            CString::operator+=(v11, v10);
LABEL_27:
            CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\open\\%s", v27, L"command");
            if ( _AfxSetRegKey(v26, v19, 0) )
            {
              if ( !a2
                || (CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\print\\%s", v27, L"command"),
                    _AfxSetRegKey(v26, v22, 0))
                && (CString::Format((CString *)&v26, (wchar_t *)L"%s\\shell\\printto\\%s", v27, L"command"),
                    _AfxSetRegKey(v26, v21, 0)) )
              {
                (*(void (__fastcall **)(__int64, LPCWSTR *, __int64))(*(_QWORD *)v7 + 216LL))(v7, &lpSubKey, 4);
                if ( *((_DWORD *)lpSubKey - 2) )
                {
                  LODWORD(cbData) = 520;
                  Buffer = CString::GetBuffer((CString *)&v26, 520);
                  ValueW = RegQueryValueW(HKEY_CLASSES_ROOT, lpSubKey, Buffer, (PLONG)&cbData);
                  CString::ReleaseBuffer((CString *)&v26, -1);
                  if ( ValueW )
                    goto LABEL_38;
                  v14 = v26;
                  if ( !*((_DWORD *)v26 - 2) )
                    goto LABEL_38;
                  do
                  {
                    v15 = *(LPCWSTR)((char *)v14 + (char *)v27 - (char *)v26);
                    v16 = *v14 - v15;
                    if ( v16 )
                      break;
                    ++v14;
                  }
                  while ( v15 );
                  if ( !v16 )
                  {
LABEL_38:
                    if ( _AfxSetRegKey(lpSubKey, (BYTE *)v27, 0) && a2 )
                    {
                      CString::Format((CString *)&v26, (wchar_t *)L"%s\\ShellNew", lpSubKey);
                      _AfxSetRegKey(v26, (BYTE *)&_afxShellNewValue, L"NullFile");
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_40:
      CString::~CString((CString *)&lpData);
      CString::~CString((CString *)&v27);
      CString::~CString((CString *)&lpSubKey);
      CString::~CString((CString *)&v23);
      CString::~CString((CString *)&v21);
      CString::~CString((CString *)&v22);
      CString::~CString((CString *)&v19);
      ++v5;
      if ( !v24 )
        goto LABEL_41;
    }
    CString::operator+=(&v19, L" \"%1\"");
    if ( a2 )
    {
      CString::operator+=(&v22, L" /p \"%1\"");
      v10 = L" /pt \"%1\" \"%2\" \"%3\" \"%4\"";
      goto LABEL_19;
    }
    goto LABEL_27;
  }
LABEL_41:
  CString::~CString((CString *)&v26);
  CString::~CString((CString *)&pszExeFileName);
}

```

## disassembly

```asm
0x1800044d0  mov     [rsp-28h+arg_8], rbx
0x1800044d5  push    rbp
0x1800044d6  push    rsi
0x1800044d7  push    rdi
0x1800044d8  push    r14
0x1800044da  push    r15
0x1800044dc  mov     rbp, rsp
0x1800044df  sub     rsp, 60h
0x1800044e3  mov     edi, edx
0x1800044e5  mov     rbx, rcx
0x1800044e8  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800044ef  mov     [rbp+pszExeFileName], rax
0x1800044f3  mov     [rbp+arg_10], rax
0x1800044f7  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800044fc  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x180004500  mov     rcx, [rax+10h]; HINSTANCE
0x180004504  call    ?AfxGetModuleShortFileName@@YAXPEAUHINSTANCE__@@AEAVCString@@@Z; AfxGetModuleShortFileName(HINSTANCE__ *,CString &)
0x180004509  mov     rax, [rbx+10h]
0x18000450d  mov     [rbp+var_8], rax
0x180004511  mov     r14d, 1
0x180004517  test    rax, rax
0x18000451a  jz      loc_18000499B
0x180004520  lea     r15, [rbx+8]
0x180004524  lea     rdx, [rbp+var_8]; struct __POSITION **
0x180004528  mov     rcx, r15; this
0x18000452b  call    ?GetNext@CObList@@QEAAAEAPEAVCObject@@AEAPEAU__POSITION@@@Z; CObList::GetNext(__POSITION * &)
0x180004530  mov     rsi, [rax]
0x180004533  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x180004537  lea     rcx, [rbp+var_30]; this
0x18000453b  call    ??0CString@@QEAA@AEBV0@@Z; CString::CString(CString const &)
0x180004540  nop
0x180004541  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x180004545  lea     rcx, [rbp+var_18]; this
0x180004549  call    ??0CString@@QEAA@AEBV0@@Z; CString::CString(CString const &)
0x18000454e  nop
0x18000454f  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x180004553  lea     rcx, [rbp+var_20]; this
0x180004557  call    ??0CString@@QEAA@AEBV0@@Z; CString::CString(CString const &)
0x18000455c  nop
0x18000455d  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x180004561  lea     rcx, [rbp+var_10]; this
0x180004565  call    ??0CString@@QEAA@AEBV0@@Z; CString::CString(CString const &)
0x18000456a  nop
0x18000456b  test    edi, edi
0x18000456d  jz      short loc_1800045D5
0x18000456f  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180004576  mov     [rbp+cbData], rax
0x18000457a  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18000457f  mov     r8d, r14d; nIconIndex
0x180004582  mov     rdx, [rbp+pszExeFileName]; pszExeFileName
0x180004586  mov     rcx, [rax+10h]; hInst
0x18000458a  call    cs:__imp_ExtractIconW
0x180004590  mov     rbx, rax
0x180004593  lea     rdx, ?_afxIconIndexFmt@@3QBGB; ",%d"
0x18000459a  lea     rcx, [rbp+cbData]; this
0x18000459e  test    rax, rax
0x1800045a1  jz      short loc_1800045B6
0x1800045a3  mov     r8d, r14d
0x1800045a6  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x1800045ab  mov     rcx, rbx; hIcon
0x1800045ae  call    cs:__imp_DestroyIcon
0x1800045b4  jmp     short loc_1800045BE
0x1800045b6  xor     r8d, r8d
0x1800045b9  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x1800045be  lea     rdx, [rbp+cbData]
0x1800045c2  lea     rcx, [rbp+var_10]
0x1800045c6  call    ??YCString@@QEAAAEBV0@AEBV0@@Z; CString::operator+=(CString const &)
0x1800045cb  nop
0x1800045cc  lea     rcx, [rbp+cbData]; this
0x1800045d0  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800045d5  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800045dc  mov     [rbp+lpSubKey], rax
0x1800045e0  mov     [rbp+arg_18], rax
0x1800045e4  mov     [rbp+lpData], rax
0x1800045e8  mov     rax, [rsi]
0x1800045eb  mov     r8d, 5
0x1800045f1  lea     rdx, [rbp+arg_18]
0x1800045f5  mov     rcx, rsi
0x1800045f8  mov     rax, [rax+0D8h]
0x1800045ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004604  test    eax, eax
0x180004606  jz      loc_180004948
0x18000460c  mov     rax, [rbp+arg_18]
0x180004610  cmp     dword ptr [rax-8], 0
0x180004614  jz      loc_180004948
0x18000461a  mov     rax, [rsi]
0x18000461d  mov     r8d, 6
0x180004623  lea     rdx, [rbp+lpData]
0x180004627  mov     rcx, rsi
0x18000462a  mov     rax, [rax+0D8h]
0x180004631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004636  test    eax, eax
0x180004638  jnz     short loc_180004647
0x18000463a  lea     rdx, [rbp+arg_18]
0x18000463e  lea     rcx, [rbp+lpData]
0x180004642  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x180004647  xor     r8d, r8d; lpValueName
0x18000464a  mov     rdx, [rbp+lpData]; lpData
0x18000464e  mov     rcx, [rbp+arg_18]; lpSubKey
0x180004652  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004657  test    eax, eax
0x180004659  jz      loc_180004948
0x18000465f  test    edi, edi
0x180004661  jz      short loc_18000468F
0x180004663  mov     r8, [rbp+arg_18]
0x180004667  lea     rdx, ?_afxDefaultIconFmt@@3QBGB; "%s\\DefaultIcon"
0x18000466e  lea     rcx, [rbp+arg_10]; this
0x180004672  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004677  xor     r8d, r8d; lpValueName
0x18000467a  mov     rdx, [rbp+var_10]; lpData
0x18000467e  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004682  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004687  test    eax, eax
0x180004689  jz      loc_180004948
0x18000468f  mov     rax, [rsi]
0x180004692  xor     r8d, r8d
0x180004695  lea     rdx, [rbp+arg_10]
0x180004699  mov     rcx, rsi
0x18000469c  mov     rax, [rax+0D8h]
0x1800046a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a8  test    eax, eax
0x1800046aa  jz      short loc_1800046EE
0x1800046ac  mov     rax, [rbp+arg_10]
0x1800046b0  cmp     dword ptr [rax-8], 0
0x1800046b4  jz      short loc_1800046EE
0x1800046b6  lea     rdx, ?_afxOpenArg@@3QBGB; " \"%1\""
0x1800046bd  lea     rcx, [rbp+var_30]
0x1800046c1  call    ??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x1800046c6  test    edi, edi
0x1800046c8  jz      loc_1800047D4
0x1800046ce  lea     rdx, ?_afxPrintArg@@3QBGB; " /p \"%1\""
0x1800046d5  lea     rcx, [rbp+var_18]
0x1800046d9  call    ??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x1800046de  lea     rdx, ?_afxPrintToArg@@3QBGB; " /pt \"%1\" \"%2\" \"%3\" \"%4\""
0x1800046e5  lea     rcx, [rbp+var_20]
0x1800046e9  jmp     loc_1800047CF
0x1800046ee  lea     r9, ?_afxDDEExec@@3QBGB; "ddeexec"
0x1800046f5  mov     r8, [rbp+arg_18]
0x1800046f9  lea     rdx, ?_afxShellOpenFmt@@3QBGB; "%s\\shell\\open\\%s"
0x180004700  lea     rcx, [rbp+arg_10]; this
0x180004704  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004709  xor     r8d, r8d; lpValueName
0x18000470c  lea     rdx, ?_afxDDEOpen@@3QBGB; "[open(\"%1\")]"
0x180004713  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004717  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x18000471c  test    eax, eax
0x18000471e  jz      loc_180004948
0x180004724  test    edi, edi
0x180004726  jz      loc_1800047C4
0x18000472c  lea     r9, ?_afxDDEExec@@3QBGB; "ddeexec"
0x180004733  mov     r8, [rbp+arg_18]
0x180004737  lea     rdx, ?_afxShellPrintFmt@@3QBGB; "%s\\shell\\print\\%s"
0x18000473e  lea     rcx, [rbp+arg_10]; this
0x180004742  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004747  xor     r8d, r8d; lpValueName
0x18000474a  lea     rdx, ?_afxDDEPrint@@3QBGB; "[print(\"%1\")]"
0x180004751  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004755  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x18000475a  test    eax, eax
0x18000475c  jz      loc_180004948
0x180004762  lea     r9, ?_afxDDEExec@@3QBGB; "ddeexec"
0x180004769  mov     r8, [rbp+arg_18]
0x18000476d  lea     rdx, ?_afxShellPrintToFmt@@3QBGB; "%s\\shell\\printto\\%s"
0x180004774  lea     rcx, [rbp+arg_10]; this
0x180004778  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x18000477d  xor     r8d, r8d; lpValueName
0x180004780  lea     rdx, ?_afxDDEPrintTo@@3QBGB; "[printto(\"%1\",\"%2\",\"%3\",\"%4\")]"
0x180004787  mov     rcx, [rbp+arg_10]; lpSubKey
0x18000478b  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004790  test    eax, eax
0x180004792  jz      loc_180004948
0x180004798  lea     rdx, ?_afxDDEArg@@3QBGB; " /dde"
0x18000479f  lea     rcx, [rbp+var_30]
0x1800047a3  call    ??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x1800047a8  lea     rdx, ?_afxDDEArg@@3QBGB; " /dde"
0x1800047af  lea     rcx, [rbp+var_18]
0x1800047b3  call    ??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x1800047b8  lea     rdx, ?_afxDDEArg@@3QBGB; " /dde"
0x1800047bf  jmp     loc_1800046E5
0x1800047c4  lea     rdx, ?_afxOpenArg@@3QBGB; " \"%1\""
0x1800047cb  lea     rcx, [rbp+var_30]
0x1800047cf  call    ??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x1800047d4  lea     r9, ?_afxCommand@@3QBGB; "command"
0x1800047db  mov     r8, [rbp+arg_18]
0x1800047df  lea     rdx, ?_afxShellOpenFmt@@3QBGB; "%s\\shell\\open\\%s"
0x1800047e6  lea     rcx, [rbp+arg_10]; this
0x1800047ea  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x1800047ef  xor     r8d, r8d; lpValueName
0x1800047f2  mov     rdx, [rbp+var_30]; lpData
0x1800047f6  mov     rcx, [rbp+arg_10]; lpSubKey
0x1800047fa  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x1800047ff  test    eax, eax
0x180004801  jz      loc_180004948
0x180004807  test    edi, edi
0x180004809  jz      short loc_180004871
0x18000480b  lea     r9, ?_afxCommand@@3QBGB; "command"
0x180004812  mov     r8, [rbp+arg_18]
0x180004816  lea     rdx, ?_afxShellPrintFmt@@3QBGB; "%s\\shell\\print\\%s"
0x18000481d  lea     rcx, [rbp+arg_10]; this
0x180004821  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004826  xor     r8d, r8d; lpValueName
0x180004829  mov     rdx, [rbp+var_18]; lpData
0x18000482d  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004831  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004836  test    eax, eax
0x180004838  jz      loc_180004948
0x18000483e  lea     r9, ?_afxCommand@@3QBGB; "command"
0x180004845  mov     r8, [rbp+arg_18]
0x180004849  lea     rdx, ?_afxShellPrintToFmt@@3QBGB; "%s\\shell\\printto\\%s"
0x180004850  lea     rcx, [rbp+arg_10]; this
0x180004854  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004859  xor     r8d, r8d; lpValueName
0x18000485c  mov     rdx, [rbp+var_20]; lpData
0x180004860  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004864  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004869  test    eax, eax
0x18000486b  jz      loc_180004948
0x180004871  mov     rax, [rsi]
0x180004874  mov     r8d, 4
0x18000487a  lea     rdx, [rbp+lpSubKey]
0x18000487e  mov     rcx, rsi
0x180004881  mov     rax, [rax+0D8h]
0x180004888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488d  mov     rax, [rbp+lpSubKey]
0x180004891  cmp     dword ptr [rax-8], 0
0x180004895  jz      loc_180004948
0x18000489b  mov     dword ptr [rbp+cbData], 208h
0x1800048a2  mov     edx, 208h; int
0x1800048a7  lea     rcx, [rbp+arg_10]; this
0x1800048ab  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x1800048b0  lea     r9, [rbp+cbData]; lpcbData
0x1800048b4  mov     r8, rax; lpData
0x1800048b7  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800048bb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800048c2  call    cs:__imp_RegQueryValueW
0x1800048c8  mov     ebx, eax
0x1800048ca  or      edx, 0FFFFFFFFh; int
0x1800048cd  lea     rcx, [rbp+arg_10]; this
0x1800048d1  call    ?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x1800048d6  mov     rdx, [rbp+arg_18]; lpData
0x1800048da  test    ebx, ebx
0x1800048dc  jnz     short loc_180004908
0x1800048de  mov     rax, [rbp+arg_10]
0x1800048e2  cmp     [rax-8], ebx
0x1800048e5  jz      short loc_180004908
0x1800048e7  mov     r9, rdx
0x1800048ea  sub     r9, rax
0x1800048ed  movzx   r8d, word ptr [rax]
0x1800048f1  movzx   ecx, word ptr [rax+r9]
0x1800048f6  sub     r8d, ecx
0x1800048f9  jnz     short loc_180004903
0x1800048fb  add     rax, 2
0x1800048ff  test    ecx, ecx
0x180004901  jnz     short loc_1800048ED
0x180004903  test    r8d, r8d
0x180004906  jnz     short loc_180004948
0x180004908  xor     r8d, r8d; lpValueName
0x18000490b  mov     rcx, [rbp+lpSubKey]; lpSubKey
0x18000490f  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004914  test    eax, eax
0x180004916  jz      short loc_180004948
0x180004918  test    edi, edi
0x18000491a  jz      short loc_180004948
0x18000491c  mov     r8, [rbp+lpSubKey]
0x180004920  lea     rdx, ?_afxShellNewFmt@@3QBGB; "%s\\ShellNew"
0x180004927  lea     rcx, [rbp+arg_10]; this
0x18000492b  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180004930  lea     r8, ?_afxShellNewValueName@@3QBGB; "NullFile"
0x180004937  lea     rdx, ?_afxShellNewValue@@3QBGB; lpData
0x18000493e  mov     rcx, [rbp+arg_10]; lpSubKey
0x180004942  call    ?_AfxSetRegKey@@YAHPEBG00@Z; _AfxSetRegKey(ushort const *,ushort const *,ushort const *)
0x180004947  nop
0x180004948  lea     rcx, [rbp+lpData]; this
0x18000494c  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180004951  nop
0x180004952  lea     rcx, [rbp+arg_18]; this
0x180004956  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18000495b  nop
0x18000495c  lea     rcx, [rbp+lpSubKey]; this
0x180004960  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180004965  nop
0x180004966  lea     rcx, [rbp+var_10]; this
0x18000496a  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18000496f  nop
0x180004970  lea     rcx, [rbp+var_20]; this
0x180004974  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180004979  nop
0x18000497a  lea     rcx, [rbp+var_18]; this
0x18000497e  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180004983  nop
0x180004984  lea     rcx, [rbp+var_30]; this
0x180004988  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18000498d  inc     r14d
0x180004990  cmp     [rbp+var_8], 0
0x180004995  jnz     loc_180004524
0x18000499b  lea     rcx, [rbp+arg_10]; this
0x18000499f  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800049a4  nop
0x1800049a5  lea     rcx, [rbp+pszExeFileName]; this
0x1800049a9  call    ??1CString@@QEAA@XZ; CString::~CString(void)
  ... truncated ...
```
