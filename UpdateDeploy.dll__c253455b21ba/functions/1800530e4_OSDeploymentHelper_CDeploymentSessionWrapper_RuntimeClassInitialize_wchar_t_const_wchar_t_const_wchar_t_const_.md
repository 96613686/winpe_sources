# OSDeploymentHelper::CDeploymentSessionWrapper::RuntimeClassInitialize(wchar_t const *,wchar_t const *,wchar_t const *,ulong,tagDSFile * *,_GUID,ulong,void *,bool *)

- ea: `0x1800530e4`
- end: `0x180053ae6`
- name: `?RuntimeClassInitialize@CDeploymentSessionWrapper@OSDeploymentHelper@@QEAAJPEB_W00KPEAPEAUtagDSFile@@U_GUID@@KPEAXPEA_N@Z`
- size: `2562`
- prototype: `__int64 __fastcall(OSDeploymentHelper::CDeploymentSessionWrapper *this, wchar_t *, const wchar_t *, wchar_t *, unsigned int, struct tagDSFile **, struct _GUID *, unsigned int, char *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180042a70`
- `0x180042e50`

## callees

- `0x180003180`
- `0x180008b30`
- `0x18000dce4`
- `0x18000e8f4`
- `0x1800110fc`
- `0x180012014`
- `0x18001a930`
- `0x180048ba0`
- `0x180048bf0`
- `0x180049130`
- `0x1800498a0`
- `0x180049ce8`
- `0x180049ff8`
- `0x18004a234`
- `0x18004d204`
- `0x1800530e4`
- `0x180053aec`
- `0x1800553c4`
- `0x180059fc8`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800534ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800534ce`

## string_xrefs

- `0x180053553`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1800535db`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1800533f1`: `Failed to find the service stack cab file '%ws'`
- `0x180053387`: `Using the inbox service stack dll file '%ws' `
- `0x1800535d4`: `AlternateServiceStackDLLPath`
- `0x1800534f5`: `Using the update's service stack dll file '%ws' `
- `0x18005362d`: `Using test service stack dll file '%ws' for Update ID '%ws'`
- `0x180053679`: `Failed to find the service stack dll file '%ws'`

## pseudocode

```c
__int64 __fastcall OSDeploymentHelper::CDeploymentSessionWrapper::RuntimeClassInitialize(
        OSDeploymentHelper::CDeploymentSessionWrapper *this,
        wchar_t *a2,
        const wchar_t *a3,
        wchar_t *a4,
        unsigned int a5,
        struct tagDSFile **a6,
        struct _GUID *a7,
        unsigned int a8,
        char *a9)
{
  wchar_t *v10; // rbx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int128 v15; // xmm0
  wchar_t *v16; // rcx
  int CombinedPath; // eax
  unsigned __int64 v18; // rdx
  int SystemFilePath; // r15d
  WCHAR *v20; // r14
  WCHAR *v21; // rbx
  char v22; // si
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  bool v25; // cl
  int v26; // eax
  WCHAR *v27; // rdi
  __int64 v28; // rdx
  int v29; // eax
  int v30; // eax
  void *v31; // r8
  const wchar_t *v32; // r9
  int v33; // eax
  int v34; // eax
  unsigned __int64 v35; // r9
  const wchar_t *v36; // r15
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  const wchar_t *v39; // r8
  wchar_t v40; // ax
  wchar_t *v41; // rax
  void *v42; // rdi
  unsigned int v43; // edx
  void *v44; // r8
  int DirectoryW; // eax
  struct tagDSFile **v46; // rcx
  WCHAR *v47; // rsi
  __int64 v48; // rdx
  __int64 v49; // rdx
  struct IDeploymentSession *v50; // rdi
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  void (__fastcall ***v54)(_QWORD, GUID *, char *); // rsi
  __int64 v55; // rcx
  void (__fastcall ***v56)(_QWORD, GUID *, char *); // rsi
  __int64 v57; // rcx
  void (__fastcall ***v58)(_QWORD, GUID *, char *); // rsi
  __int64 v59; // rcx
  void (__fastcall ***v60)(_QWORD, GUID *, char *); // rsi
  __int64 v61; // rcx
  void (__fastcall ***v62)(_QWORD, GUID *, char *); // rsi
  __int64 v63; // rcx
  void (__fastcall ***v64)(_QWORD, GUID *, char *); // rdi
  __int64 v65; // rcx
  void *v66; // [rsp+20h] [rbp-E0h]
  void *v67; // [rsp+20h] [rbp-E0h]
  struct tagOptionalSessionInfo6 *v68; // [rsp+28h] [rbp-D8h]
  void *lpMem; // [rsp+40h] [rbp-C0h] BYREF
  PCNZWCH v70; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-B0h] BYREF
  struct tagDSFile **v72; // [rsp+58h] [rbp-A8h]
  wchar_t *v73; // [rsp+60h] [rbp-A0h]
  PCNZWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v75; // [rsp+70h] [rbp-90h]
  struct _GUID *v76; // [rsp+78h] [rbp-88h]
  _QWORD v77[14]; // [rsp+80h] [rbp-80h] BYREF
  struct IDeploymentSession *v78; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v79[3]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v80[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v75 = a4;
  lpExistingFileName = a3;
  v10 = a2;
  v73 = a2;
  v72 = a6;
  v76 = a7;
  if ( !a2 )
  {
    v12 = 26;
LABEL_3:
    v13 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)v13,
      (int)v66);
    return v13;
  }
  if ( !a4 )
  {
    v12 = 27;
    goto LABEL_3;
  }
  memset(v77, 0, sizeof(v77));
  if ( a9 )
  {
    if ( a8 < 6 )
    {
      if ( a8 != 5 )
      {
        LODWORD(v68) = a8;
        v13 = -2145124297;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2FD,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
          (const char *)0x80240037LL,
          (int)"WU does NOT support OptionalSession version %lu",
          (const char *)v68);
        v12 = 39;
        goto LABEL_4;
      }
      v77[0] = *(_QWORD *)a9;
      v77[1] = *((_QWORD *)a9 + 1);
      v77[2] = *((_QWORD *)a9 + 2);
      v77[3] = *((_QWORD *)a9 + 3);
      v77[4] = *((_QWORD *)a9 + 4);
      v77[5] = *((_QWORD *)a9 + 5);
      v77[7] = *((_QWORD *)a9 + 7);
      LODWORD(v77[8]) = *((_DWORD *)a9 + 16);
      HIDWORD(v77[12]) = *((_DWORD *)a9 + 25);
    }
    else
    {
      v77[0] = *(_QWORD *)a9;
      v77[1] = *((_QWORD *)a9 + 1);
      v77[2] = *((_QWORD *)a9 + 2);
      v77[3] = *((_QWORD *)a9 + 3);
      v77[4] = *((_QWORD *)a9 + 4);
      v77[5] = *((_QWORD *)a9 + 5);
      v77[7] = *((_QWORD *)a9 + 7);
      LODWORD(v77[8]) = *((_DWORD *)a9 + 16);
      HIDWORD(v77[12]) = *((_DWORD *)a9 + 25);
      LODWORD(v77[13]) = *((_DWORD *)a9 + 26);
    }
    v15 = *(_OWORD *)(a9 + 68);
    v16 = (wchar_t *)*((_QWORD *)a9 + 6);
    *(_OWORD *)((char *)&v77[10] + 4) = *(_OWORD *)(a9 + 84);
    *(_OWORD *)((char *)&v77[8] + 4) = v15;
    v77[6] = v16;
    if ( v16 )
      v10 = v16;
    v73 = v10;
  }
  lpString1 = 0;
  CombinedPath = CreateCombinedPath(v10, L"Metadata", (wchar_t **)&lpString1);
  SystemFilePath = CombinedPath;
  v20 = (WCHAR *)lpString1;
  if ( CombinedPath >= 0 )
  {
    v21 = 0;
    v70 = 0;
    memset(v79, 0, sizeof(v79));
    v22 = 1;
    if ( !lpExistingFileName )
    {
      SystemFilePath = GetSystemFilePath(v80, v18, a4);
      if ( SystemFilePath < 0 )
      {
        v23 = 152;
LABEL_23:
        v24 = (unsigned int)SystemFilePath;
LABEL_71:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
          (const char *)v24,
          (int)v66);
LABEL_118:
        SsShimInterface::~SsShimInterface((SsShimInterface *)v79);
        if ( v21 )
          SusFree(v21);
        goto LABEL_120;
      }
      SystemFilePath = DuplicateString<wchar_t *,wchar_t *>(v80, &v70);
      v21 = (WCHAR *)v70;
      if ( SystemFilePath < 0 )
      {
        v23 = 154;
        goto LABEL_23;
      }
      WUTrace(0, 0, 4096, 4, 0, L"Using the inbox service stack dll file '%ws' ");
LABEL_44:
      if ( (unsigned int)AreTestKeysAllowed(v25) )
      {
        v36 = L"Global";
        if ( a9 && v77[1] )
          v36 = (const wchar_t *)v77[1];
        v37 = 260;
        v38 = v80;
        v39 = (const wchar_t *)((char *)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test"
                              - (char *)v80);
        do
        {
          if ( v37 == -2147483386 )
            break;
          v40 = *(const wchar_t *)((char *)v39 + (_QWORD)v38);
          if ( !v40 )
            break;
          *v38++ = v40;
          --v37;
        }
        while ( v37 );
        v41 = v38 - 1;
        if ( v37 )
          v41 = v38;
        *v41 = 0;
        WUPathCchAppend(v80, v37, v39);
        lpMem = 0;
        if ( (int)RegQueryStringValue(-2147483646, v80, v36, &lpMem) >= 0 )
          goto LABEL_59;
        if ( lpMem )
        {
          SusFree(lpMem);
          lpMem = 0;
        }
        if ( (int)RegQueryStringValue(
                    -2147483646,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                    L"AlternateServiceStackDLLPath",
                    &lpMem) >= 0 )
        {
LABEL_59:
          if ( v21 )
          {
            SusFree(v21);
            v70 = 0;
          }
          v42 = lpMem;
          if ( (int)DuplicateString<wchar_t *,wchar_t *>(lpMem, &v70) >= 0 )
            WUTrace(0, 0, 4096, 4, 0, L"Using test service stack dll file '%ws' for Update ID '%ws'");
          v21 = (WCHAR *)v70;
        }
        else
        {
          v42 = lpMem;
        }
        if ( v42 )
          SusFree(v42);
      }
      SystemFilePath = CheckIfFileExists(v21);
      if ( SystemFilePath < 0 )
      {
        LODWORD(v66) = SystemFilePath;
        WUTrace(0, 0, 4096, 1, v66, L"Failed to find the service stack dll file '%ws'");
        v24 = (unsigned int)SystemFilePath;
        v23 = 280;
        goto LABEL_71;
      }
      if ( a5 )
      {
        DirectoryW = SusMakeDirectoryW(v20, v43, v44);
        SystemFilePath = DirectoryW;
        if ( DirectoryW < 0 )
        {
          v24 = (unsigned int)DirectoryW;
          v23 = 286;
          goto LABEL_71;
        }
        LODWORD(lpMem) = 0;
        v46 = v72;
        while ( 1 )
        {
          lpExistingFileName = 0;
          v26 = CreateCombinedPath(v73, *((const wchar_t **)*v46 + 9), (wchar_t **)&lpExistingFileName);
          SystemFilePath = v26;
          v27 = (WCHAR *)lpExistingFileName;
          if ( v26 < 0 )
          {
            v28 = 294;
            goto LABEL_88;
          }
          lpExistingFileName = 0;
          SystemFilePath = CreateCombinedPath(v20, *((const wchar_t **)*v72 + 9), (wchar_t **)&lpExistingFileName);
          v47 = (WCHAR *)lpExistingFileName;
          if ( SystemFilePath < 0 )
            break;
          SystemFilePath = SusCopyFileRetryIfSharingViolation(v27, lpExistingFileName, 0, 0xAu, v66);
          if ( SystemFilePath < 0 )
          {
            v49 = 304;
            goto LABEL_85;
          }
          if ( v47 )
            SusFree(v47);
          if ( v27 )
            SusFree(v27);
          v22 = 1;
          LODWORD(lpMem) = (_DWORD)lpMem + 1;
          v46 = ++v72;
          if ( (unsigned int)lpMem >= a5 )
            goto LABEL_81;
        }
        v49 = 299;
LABEL_85:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v49,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
          (const char *)(unsigned int)SystemFilePath,
          (int)v66);
        if ( v47 )
          SusFree(v47);
LABEL_90:
        if ( v27 )
          SusFree(v27);
        goto LABEL_118;
      }
LABEL_81:
      v78 = 0;
      SystemFilePath = OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(
                         this,
                         v21,
                         v73,
                         v76,
                         a8,
                         (struct tagOptionalSessionInfo6 *)v77,
                         a9,
                         &v78);
      if ( SystemFilePath >= 0 )
      {
        v50 = v78;
        if ( v78 )
        {
          v78 = 0;
          v51 = *((_QWORD *)this + 11);
          if ( v51 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          *((_QWORD *)this + 11) = v50;
          v52 = *((_QWORD *)this + 13);
          if ( v52 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            *((_QWORD *)this + 13) = 0;
          }
          v53 = (**(__int64 (__fastcall ***)(struct IDeploymentSession *, GUID *, char *))v50)(
                  v50,
                  &GUID_3e309b3c_494d_4429_a607_fd4098ae813f,
                  (char *)this + 104);
          SystemFilePath = v53;
          if ( v53 < 0 )
          {
            if ( (unsigned int)(v53 + 2147467263) > 1 )
            {
              LODWORD(v67) = v53;
              WUTrace(0, 0, 4096, 1, v67, L"Query IDeploymentSession2");
              v48 = 332;
              goto LABEL_101;
            }
            v22 = 0;
          }
          *((_BYTE *)this + 96) = v22;
          v54 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v55 = *((_QWORD *)this + 14);
          SystemFilePath = 0;
          if ( v55 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
            *((_QWORD *)this + 14) = 0;
          }
          (**v54)(v54, &GUID_36fb071a_6dc5_48bf_a6f3_d4f6751d39dc, (char *)this + 112);
          v56 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v57 = *((_QWORD *)this + 15);
          if ( v57 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
            *((_QWORD *)this + 15) = 0;
          }
          (**v56)(v56, &GUID_09110432_1aee_49f8_9c1c_0f7d203777bf, (char *)this + 120);
          v58 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v59 = *((_QWORD *)this + 16);
          if ( v59 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
            *((_QWORD *)this + 16) = 0;
          }
          (**v58)(v58, &GUID_347c6b31_7d10_4ada_9ede_ae9288f35f47, (char *)this + 128);
          v60 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v61 = *((_QWORD *)this + 17);
          if ( v61 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
            *((_QWORD *)this + 17) = 0;
          }
          (**v60)(v60, &GUID_7d79e71d_36c6_4a20_bab0_0e44763c8ba9, (char *)this + 136);
          v62 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v63 = *((_QWORD *)this + 18);
          if ( v63 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
            *((_QWORD *)this + 18) = 0;
          }
          (**v62)(v62, &GUID_68aaa5b1_d95c_482d_8967_41c07caa2adc, (char *)this + 144);
          v64 = (void (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 11);
          v65 = *((_QWORD *)this + 19);
          if ( v65 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            *((_QWORD *)this + 19) = 0;
          }
          (**v64)(v64, &GUID_57816c47_d685_423a_89c6_feefbd90ed47, (char *)this + 152);
          goto LABEL_116;
        }
        SystemFilePath = -2145112065;
        v48 = 317;
      }
      else
      {
        v48 = 315;
      }
LABEL_101:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v48,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)SystemFilePath,
        (int)v67);
LABEL_116:
      if ( v78 )
      {
        (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      goto LABEL_118;
    }
    lpMem = 0;
    v26 = CreateCombinedPath(v73, lpExistingFileName, (wchar_t **)&lpMem);
    SystemFilePath = v26;
    v27 = (WCHAR *)lpMem;
    if ( v26 >= 0 )
    {
      SystemFilePath = CheckIfFileExists((const wchar_t *)lpMem);
      if ( SystemFilePath >= 0 )
      {
        v29 = CreateCombinedPath(v20, v75, (wchar_t **)&v70);
        SystemFilePath = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB7,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
            (const char *)(unsigned int)v29,
            (int)v66);
          v21 = (WCHAR *)v70;
          goto LABEL_90;
        }
        v30 = CheckIfDirExists(v20);
        v21 = (WCHAR *)v70;
        if ( v30 < 0
          || (v33 = SusDeleteFileRetryIfSharingViolation(v70, 6u, v31), SystemFilePath = v33, v33 > -2147024895)
          && (unsigned int)(v33 + 2147024892) > 0x7FF8FFFB )
        {
          LODWORD(lpMem) = 0;
          while ( 1 )
          {
            v34 = DecompressCabFile(v27, v20, (unsigned int)v31, v32, v66);
            SystemFilePath = v34;
            if ( v34 >= 0 )
              break;
            if ( v34 == -2147024864 )
            {
              Sleep(0x2710u);
              LODWORD(lpMem) = (_DWORD)lpMem + 1;
              if ( (unsigned int)lpMem < 6 )
                continue;
            }
            v28 = 223;
            goto LABEL_41;
          }
          WUTrace(0, 0, 4096, 4, 0, L"Using the update's service stack dll file '%ws' ");
          if ( v27 )
            SusFree(v27);
          goto LABEL_44;
        }
        v28 = 197;
      }
      else
      {
        LODWORD(v66) = SystemFilePath;
        WUTrace(0, 0, 4096, 1, v66, L"Failed to find the service stack cab file '%ws'");
        if ( (unsigned int)(SystemFilePath + 2147024894) <= 1 )
          goto LABEL_90;
        v28 = 179;
      }
LABEL_41:
      v35 = (unsigned int)SystemFilePath;
    }
    else
    {
      v28 = 165;
LABEL_88:
      v35 = (unsigned int)v26;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)v35,
      (int)v66);
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
    (const char *)(unsigned int)CombinedPath,
    (int)v66);
LABEL_120:
  if ( v20 )
    SusFree(v20);
  return (unsigned int)SystemFilePath;
}

```

## disassembly

```asm
0x1800530e4  push    rbp
0x1800530e6  push    rbx
0x1800530e7  push    rsi
0x1800530e8  push    rdi
0x1800530e9  push    r12
0x1800530eb  push    r13
0x1800530ed  push    r14
0x1800530ef  push    r15
0x1800530f1  lea     rbp, [rsp-258h]
0x1800530f9  sub     rsp, 358h
0x180053100  mov     rax, cs:__security_cookie
0x180053107  xor     rax, rsp
0x18005310a  mov     [rbp+290h+var_50], rax
0x180053111  mov     rdi, r9
0x180053114  mov     [rsp+390h+var_320], r9
0x180053119  mov     [rsp+390h+lpExistingFileName], r8
0x18005311e  mov     rbx, rdx
0x180053121  mov     [rsp+390h+var_330], rdx
0x180053126  mov     r13, rcx
0x180053129  mov     r12, [rbp+290h+arg_40]
0x180053130  mov     rax, [rbp+290h+arg_28]
0x180053137  mov     [rsp+390h+var_338], rax
0x18005313c  mov     rax, [rbp+290h+arg_30]
0x180053143  mov     [rsp+390h+var_318], rax
0x180053148  xor     esi, esi
0x18005314a  test    rdx, rdx
0x18005314d  jnz     short loc_180053174
0x18005314f  lea     edx, [rbx+1Ah]; void *
0x180053152  mov     ebx, 80004003h
0x180053157  mov     rcx, [rbp+298h]; this
0x18005315e  mov     r9d, ebx; char *
0x180053161  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180053168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005316d  mov     eax, ebx
0x18005316f  jmp     loc_180053AC3
0x180053174  test    rdi, rdi
0x180053177  jnz     short loc_18005317E
0x180053179  lea     edx, [rdi+1Bh]
0x18005317c  jmp     short loc_180053152
0x18005317e  xor     edx, edx; Val
0x180053180  lea     r8d, [rdx+70h]; Size
0x180053184  lea     rcx, [rbp+290h+var_310]; void *
0x180053188  call    memset
0x18005318d  mov     rcx, rsi
0x180053190  mov     rax, rsi
0x180053193  test    r12, r12
0x180053196  jz      loc_180053287
0x18005319c  mov     eax, dword ptr [rbp+290h+arg_38]
0x1800531a2  cmp     eax, 6
0x1800531a5  jb      short loc_1800531FF
0x1800531a7  mov     rax, [r12]
0x1800531ab  mov     [rbp+290h+var_310], rax
0x1800531af  mov     rax, [r12+8]
0x1800531b4  mov     [rbp+290h+var_308], rax
0x1800531b8  mov     rax, [r12+10h]
0x1800531bd  mov     [rbp+290h+var_300], rax
0x1800531c1  mov     rax, [r12+18h]
0x1800531c6  mov     [rbp+290h+var_2F8], rax
0x1800531ca  mov     rax, [r12+20h]
0x1800531cf  mov     [rbp+290h+var_2F0], rax
0x1800531d3  mov     rax, [r12+28h]
0x1800531d8  mov     [rbp+290h+var_2E8], rax
0x1800531dc  mov     rax, [r12+38h]
0x1800531e1  mov     [rbp+290h+var_2D8], rax
0x1800531e5  mov     eax, [r12+40h]
0x1800531ea  mov     [rbp+290h+var_2D0], eax
0x1800531ed  mov     eax, [r12+64h]
0x1800531f2  mov     [rbp+290h+var_2AC], eax
0x1800531f5  mov     eax, [r12+68h]
0x1800531fa  mov     [rbp+290h+var_2A8], eax
0x1800531fd  jmp     short loc_180053256
0x1800531ff  cmp     eax, 5
0x180053202  jnz     loc_1800532CC
0x180053208  mov     rax, [r12]
0x18005320c  mov     [rbp+290h+var_310], rax
0x180053210  mov     rax, [r12+8]
0x180053215  mov     [rbp+290h+var_308], rax
0x180053219  mov     rax, [r12+10h]
0x18005321e  mov     [rbp+290h+var_300], rax
0x180053222  mov     rax, [r12+18h]
0x180053227  mov     [rbp+290h+var_2F8], rax
0x18005322b  mov     rax, [r12+20h]
0x180053230  mov     [rbp+290h+var_2F0], rax
0x180053234  mov     rax, [r12+28h]
0x180053239  mov     [rbp+290h+var_2E8], rax
0x18005323d  mov     rax, [r12+38h]
0x180053242  mov     [rbp+290h+var_2D8], rax
0x180053246  mov     eax, [r12+40h]
0x18005324b  mov     [rbp+290h+var_2D0], eax
0x18005324e  mov     eax, [r12+64h]
0x180053253  mov     [rbp+290h+var_2AC], eax
0x180053256  movups  xmm1, xmmword ptr [r12+54h]
0x18005325c  movups  xmm0, xmmword ptr [r12+44h]
0x180053262  mov     rcx, [r12+30h]
0x180053267  movups  [rbp+290h+var_2BC], xmm1
0x18005326b  movups  [rbp+290h+var_2CC], xmm0
0x18005326f  mov     [rbp+290h+var_2E0], rcx
0x180053273  mov     rax, rcx
0x180053276  test    r12, r12
0x180053279  jz      short loc_180053287
0x18005327b  test    rcx, rcx
0x18005327e  cmovnz  rbx, rcx
0x180053282  mov     [rsp+390h+var_330], rbx
0x180053287  mov     [rsp+390h+lpString1], rsi
0x18005328c  lea     r8, [rsp+390h+lpString1]; wchar_t **
0x180053291  lea     rdx, ?c_szUUPMetaDataSubFolder@CDeploymentSessionWrapper@OSDeploymentHelper@@2QB_WB; "Metadata"
0x180053298  mov     rcx, rbx; wchar_t *
0x18005329b  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800532a0  mov     r15d, eax
0x1800532a3  mov     r14, [rsp+390h+lpString1]
0x1800532a8  test    eax, eax
0x1800532aa  jns     short loc_180053306
0x1800532ac  mov     rcx, [rbp+298h]; this
0x1800532b3  mov     r9d, eax; char *
0x1800532b6  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800532bd  mov     edx, 33h ; '3'; void *
0x1800532c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532c7  jmp     loc_180053AB3
0x1800532cc  mov     rcx, [rbp+298h]; this
0x1800532d3  mov     dword ptr [rsp+390h+var_368], eax; char *
0x1800532d7  lea     rax, aWuDoesNotSuppo; "WU does NOT support OptionalSession ver"...
0x1800532de  mov     [rsp+390h+var_370], rax; int
0x1800532e3  mov     ebx, 80240037h
0x1800532e8  mov     r9d, ebx; char *
0x1800532eb  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800532f2  mov     edx, 2FDh; void *
0x1800532f7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800532fc  mov     edx, 27h ; '''
0x180053301  jmp     loc_180053157
0x180053306  mov     rbx, rsi
0x180053309  mov     [rsp+390h+var_348], rbx
0x18005330e  xorps   xmm0, xmm0
0x180053311  movups  [rbp+290h+var_288], xmm0
0x180053315  movups  [rbp+290h+var_278], xmm0
0x180053319  movdqu  [rbp+290h+var_298], xmm0
0x18005331e  mov     word ptr [rbp+290h+var_288], si
0x180053322  mov     qword ptr [rbp+290h+var_288+8], rsi
0x180053326  mov     qword ptr [rbp+290h+var_278], rsi
0x18005332a  mov     qword ptr [rbp+290h+var_278+8], rsi
0x18005332e  mov     esi, 1
0x180053333  mov     rax, [rsp+390h+lpExistingFileName]
0x180053338  xor     ecx, ecx
0x18005333a  test    rax, rax
0x18005333d  jnz     short loc_1800533B0
0x18005333f  mov     r8, rdi; wchar_t *
0x180053342  lea     rcx, [rbp+290h+var_260]; wchar_t *
0x180053346  call    ?GetSystemFilePath@@YAJPEA_W_KPEB_W@Z; GetSystemFilePath(wchar_t *,unsigned __int64,wchar_t const *)
0x18005334b  mov     r15d, eax
0x18005334e  xor     edi, edi
0x180053350  test    eax, eax
0x180053352  jns     short loc_18005335B
0x180053354  mov     edx, 98h
0x180053359  jmp     short loc_18005337A
0x18005335b  lea     rdx, [rsp+390h+var_348]
0x180053360  lea     rcx, [rbp+290h+var_260]
0x180053364  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180053369  mov     r15d, eax
0x18005336c  mov     rbx, [rsp+390h+var_348]
0x180053371  test    eax, eax
0x180053373  jns     short loc_180053382
0x180053375  mov     edx, 9Ah
0x18005337a  mov     r9d, r15d
0x18005337d  jmp     loc_1800536C9
0x180053382  mov     [rsp+390h+var_360], rbx
0x180053387  lea     rax, aUsingTheInboxS; "Using the inbox service stack dll file "...
0x18005338e  mov     [rsp+390h+var_368], rax
0x180053393  mov     [rsp+390h+var_370], rdi
0x180053398  xor     edx, edx
0x18005339a  xor     ecx, ecx
0x18005339c  lea     r9d, [rdx+4]
0x1800533a0  mov     r8d, 1000h
0x1800533a6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800533ab  jmp     loc_180053526
0x1800533b0  mov     [rsp+390h+lpMem], rcx
0x1800533b5  lea     r8, [rsp+390h+lpMem]; wchar_t **
0x1800533ba  mov     rdx, rax; wchar_t *
0x1800533bd  mov     rcx, [rsp+390h+var_330]; wchar_t *
0x1800533c2  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800533c7  mov     r15d, eax
0x1800533ca  mov     rdi, [rsp+390h+lpMem]
0x1800533cf  test    eax, eax
0x1800533d1  jns     short loc_1800533DD
0x1800533d3  mov     edx, 0A5h
0x1800533d8  jmp     loc_18005382B
0x1800533dd  mov     rcx, rdi; wchar_t *
0x1800533e0  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x1800533e5  mov     r15d, eax
0x1800533e8  test    eax, eax
0x1800533ea  jns     short loc_18005342D
0x1800533ec  mov     [rsp+390h+var_360], rdi
0x1800533f1  lea     rax, aFailedToFindTh_0; "Failed to find the service stack cab fi"...
0x1800533f8  mov     [rsp+390h+var_368], rax
0x1800533fd  mov     dword ptr [rsp+390h+var_370], r15d
0x180053402  mov     r9d, esi
0x180053405  xor     edx, edx
0x180053407  xor     ecx, ecx
0x180053409  mov     r8d, 1000h
0x18005340f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180053414  lea     eax, [r15+7FF8FFFEh]
0x18005341b  cmp     eax, esi
0x18005341d  jbe     loc_180053841
0x180053423  mov     edx, 0B3h
0x180053428  jmp     loc_1800534E8
0x18005342d  lea     r8, [rsp+390h+var_348]; wchar_t **
0x180053432  mov     rdx, [rsp+390h+var_320]; wchar_t *
0x180053437  mov     rcx, r14; wchar_t *
0x18005343a  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18005343f  mov     r15d, eax
0x180053442  test    eax, eax
0x180053444  jns     short loc_18005346B
0x180053446  mov     rcx, [rbp+298h]; this
0x18005344d  mov     r9d, eax; char *
0x180053450  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180053457  mov     edx, 0B7h; void *
0x18005345c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053461  mov     rbx, [rsp+390h+var_348]
0x180053466  jmp     loc_180053841
0x18005346b  mov     rcx, r14; wchar_t *
0x18005346e  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x180053473  mov     rbx, [rsp+390h+var_348]
0x180053478  test    eax, eax
0x18005347a  js      short loc_1800534A6
0x18005347c  mov     edx, 6; unsigned int
0x180053481  mov     rcx, rbx; lpString1
0x180053484  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x180053489  mov     r15d, eax
0x18005348c  cmp     eax, 80070001h
0x180053491  jle     short loc_18005349F
0x180053493  add     eax, 7FF8FFFCh
0x180053498  cmp     eax, 7FF8FFFBh
0x18005349d  ja      short loc_1800534A6
0x18005349f  mov     edx, 0C5h
0x1800534a4  jmp     short loc_1800534E8
0x1800534a6  mov     dword ptr [rsp+390h+lpMem], 0
0x1800534ae  mov     rdx, r14; wchar_t *
0x1800534b1  mov     rcx, rdi; wchar_t *
0x1800534b4  call    ?DecompressCabFile@@YAJPEB_W0K0PEAX@Z; DecompressCabFile(wchar_t const *,wchar_t const *,ulong,wchar_t const *,void *)
0x1800534b9  mov     r15d, eax
0x1800534bc  xor     ecx, ecx
0x1800534be  test    eax, eax
0x1800534c0  jns     short loc_1800534F0
0x1800534c2  cmp     eax, 80070020h
0x1800534c7  jnz     short loc_1800534E3
0x1800534c9  mov     ecx, 2710h; dwMilliseconds
0x1800534ce  call    cs:__imp_Sleep
0x1800534d4  mov     eax, dword ptr [rsp+390h+lpMem]
0x1800534d8  add     eax, esi
0x1800534da  mov     dword ptr [rsp+390h+lpMem], eax
0x1800534de  cmp     eax, 6
0x1800534e1  jb      short loc_1800534AE
0x1800534e3  mov     edx, 0DFh
0x1800534e8  mov     r9d, r15d
0x1800534eb  jmp     loc_18005382E
0x1800534f0  mov     [rsp+390h+var_360], rbx
0x1800534f5  lea     rax, aUsingTheUpdate; "Using the update's service stack dll fi"...
0x1800534fc  mov     [rsp+390h+var_368], rax
0x180053501  mov     [rsp+390h+var_370], rcx
0x180053506  xor     edx, edx
0x180053508  lea     r9d, [rdx+4]
0x18005350c  mov     r8d, 1000h
0x180053512  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180053517  test    rdi, rdi
0x18005351a  jz      short loc_180053524
0x18005351c  mov     rcx, rdi; lpMem
0x18005351f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180053524  xor     edi, edi
0x180053526  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18005352b  test    eax, eax
0x18005352d  jz      loc_180053665
0x180053533  lea     r15, aGlobal; "Global"
0x18005353a  test    r12, r12
0x18005353d  jz      short loc_18005354A
0x18005353f  mov     rax, [rbp+290h+var_308]
0x180053543  test    rax, rax
0x180053546  cmovnz  r15, rax
0x18005354a  mov     edx, 104h
0x18005354f  lea     rcx, [rbp+290h+var_260]
0x180053553  lea     r8, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005355a  lea     rax, [rbp+290h+var_260]
0x18005355e  sub     r8, rax; wchar_t *
0x180053561  lea     rax, [rdx+7FFFFEFAh]
0x180053568  test    rax, rax
0x18005356b  jz      short loc_180053583
0x18005356d  movzx   eax, word ptr [rcx+r8]
0x180053572  test    ax, ax
0x180053575  jz      short loc_180053583
0x180053577  mov     [rcx], ax
0x18005357a  add     rcx, 2
0x18005357e  sub     rdx, rsi; unsigned int
0x180053581  jnz     short loc_180053561
0x180053583  lea     rax, [rcx-2]
0x180053587  test    rdx, rdx
0x18005358a  cmovnz  rax, rcx
0x18005358e  mov     [rax], di
0x180053591  lea     rcx, [rbp+290h+var_260]; wchar_t *
0x180053595  call    ?WUPathCchAppend@@YAJPEA_WKPEB_W@Z; WUPathCchAppend(wchar_t *,ulong,wchar_t const *)
0x18005359a  mov     [rsp+390h+lpMem], rdi
0x18005359f  lea     r9, [rsp+390h+lpMem]
0x1800535a4  mov     r8, r15
0x1800535a7  lea     rdx, [rbp+290h+var_260]
  ... truncated ...
```
