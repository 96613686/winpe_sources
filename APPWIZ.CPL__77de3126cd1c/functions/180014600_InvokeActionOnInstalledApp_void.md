# InvokeActionOnInstalledApp(void *)

- ea: `0x180014600`
- end: `0x180014bac`
- name: `?InvokeActionOnInstalledApp@@YAKPEAX@Z`
- size: `1452`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180010904`
- `0x1800109a4`
- `0x180011e78`
- `0x180013490`
- `0x180014600`
- `0x180014d90`
- `0x180016ad0`
- `0x18001732c`
- `0x180017a64`
- `0x180017e58`
- `0x180017f10`
- `0x18001b5b8`
- `0x180044d5c`
- `0x180050078`
- `0x1800569c4`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180014b35`
- `SHELL32!SHChangeNotify` at `0x180014b35`
- `SHELL32!ShellExecuteW` at `0x180014806`
- `SHELL32!ShellExecuteW` at `0x180014806`
- `SHELL32!__imp_ILFree` at `0x180014b5e`
- `SHELL32!__imp_ILFree` at `0x180014b5e`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180014713`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180014af4`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180014713`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180014af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001471e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001471e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aff`
- `ntdll!NtSetInformationProcess` at `0x180014947`
- `ntdll!NtSetInformationProcess` at `0x18001499c`
- `ntdll!NtSetInformationProcess` at `0x1800149f8`
- `ntdll!NtSetInformationProcess` at `0x180014947`
- `ntdll!NtSetInformationProcess` at `0x18001499c`
- `ntdll!NtSetInformationProcess` at `0x1800149f8`
- `ntdll!EtwCheckCoverage` at `0x18001492d`
- `ntdll!EtwCheckCoverage` at `0x180014982`
- `ntdll!EtwCheckCoverage` at `0x1800149de`
- `ntdll!EtwCheckCoverage` at `0x18001492d`
- `ntdll!EtwCheckCoverage` at `0x180014982`
- `ntdll!EtwCheckCoverage` at `0x1800149de`
- `USER32!GetCursorPos` at `0x180014666`
- `USER32!GetCursorPos` at `0x180014666`

## pseudocode

```c
__int64 __fastcall InvokeActionOnInstalledApp(_DWORD *Parameter, __int64 a2, int *a3, int *a4)
{
  _DWORD *v4; // rdi
  int v5; // esi
  unsigned int v6; // eax
  BOOL v7; // ebx
  HWND v8; // rcx
  HINSTANCE v9; // rdx
  HWND v10; // rbx
  struct _ITEMID_CHILD *v11; // rdx
  struct _ITEMIDLIST_ABSOLUTE *v12; // rcx
  BOOL v13; // r14d
  const WCHAR *pszHelpLink; // r8
  int v15; // eax
  int v16; // eax
  unsigned __int64 v17; // rdx
  unsigned __int8 v18; // cl
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  struct _ITEMID_CHILD *v21; // rdx
  struct _ITEMIDLIST_ABSOLUTE *v22; // rcx
  const struct _ITEMIDLIST_RELATIVE *v23; // rdx
  const struct _ITEMIDLIST_ABSOLUTE *v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  HWND v30; // [rsp+38h] [rbp-C8h] BYREF
  struct tagPOINT Point; // [rsp+40h] [rbp-C0h] BYREF
  _AppInfoData v32; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+F0h] [rbp-10h] BYREF
  const WCHAR *v34; // [rsp+100h] [rbp+0h]
  const WCHAR *v35; // [rsp+108h] [rbp+8h]
  _BYTE v36[96]; // [rsp+110h] [rbp+10h] BYREF

  v4 = Parameter;
  v5 = 0;
  if ( !Parameter )
    goto LABEL_75;
  v6 = Parameter[4] - 1;
  v30 = 0;
  v7 = v6 <= 3;
  Point.y = 0x80000000;
  Point.x = 0x80000000;
  GetCursorPos(&Point);
  if ( v7 && !Stub_EnsureUniqueStubWithParent(v8, *(const struct _ITEMIDLIST_ABSOLUTE **)v4, (int)a3, Point, &v30) )
  {
    TaskDialog_CantRemoveMulti(*((HWND *)v4 + 3), v9, a3, a4);
    goto LABEL_75;
  }
  v10 = 0;
  v30 = 0;
  if ( !v4[5] )
  {
    v5 = RecreateInstalledApp((struct tagAppRecreateInfo *)(v4 + 9), (struct IInstalledApp **)&v30);
    if ( v5 < 0 )
    {
      v11 = (struct _ITEMID_CHILD *)*((_QWORD *)v4 + 1);
      v12 = *(struct _ITEMIDLIST_ABSOLUTE **)v4;
      pv = 0;
      if ( GetDisplayName(v12, v11, (unsigned __int16 **)&pv) >= 0 )
      {
        ShellMessageBoxW(
          g_hinst,
          *((HWND *)v4 + 3),
          (LPCWSTR)0x90,
          (LPCWSTR)((-(__int64)(v4[8] != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 159),
          0x40u,
          pv);
        CoTaskMemFree(pv);
      }
LABEL_71:
      v23 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)v4 + 1);
      v24 = *(const struct _ITEMIDLIST_ABSOLUTE **)v4;
      pv = 0;
      if ( (int)SHILCombine(v24, v23, (struct _ITEMIDLIST_ABSOLUTE **)&pv) >= 0 )
      {
        SHChangeNotify(4, 0x3000u, pv, 0);
        if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            v25,
            (int)&AppWizCpl_SoftwareExplorer_InstalledProgramsChangeNotify_Info,
            v26,
            v27,
            &v33);
        ILFree((LPITEMIDLIST)pv);
      }
      goto LABEL_75;
    }
    v10 = v30;
  }
  v13 = 0;
  LODWORD(Parameter) = v4[4] - 1;
  if ( v4[4] == 1 )
    goto LABEL_34;
  LODWORD(Parameter) = v4[4] - 2;
  if ( v4[4] == 2 )
  {
    if ( !v10 )
      goto LABEL_61;
    v15 = (*(__int64 (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, *((_QWORD *)v4 + 3));
    goto LABEL_31;
  }
  LODWORD(Parameter) = v4[4] - 3;
  if ( v4[4] == 3 )
  {
    if ( !v10 )
      goto LABEL_61;
    v15 = (*(__int64 (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v10 + 80LL))(v10, *((_QWORD *)v4 + 3));
LABEL_31:
    v5 = v15;
    goto LABEL_60;
  }
  LODWORD(Parameter) = v4[4] - 4;
  if ( v4[4] == 4 )
  {
LABEL_34:
    if ( v4[5] == 2 )
    {
      v16 = UninstallVUEPackage((struct tagInstalledAppData *)v4);
    }
    else
    {
      if ( v4[5] != 1 )
      {
        if ( !v10 )
          goto LABEL_61;
        memset_0(&v32, 0, sizeof(v32));
        memset_0(v36, 0, 0x5Au);
        if ( AppWizLogging::IsEnabled(v18, v17) )
        {
          v32.cbSize = 152;
          v32.dwMask = 5;
          if ( (*(int (__fastcall **)(HWND, _AppInfoData *))(*(_QWORD *)v30 + 24LL))(v30, &v32) >= 0 )
          {
            v33.Ptr = (ULONGLONG)v32.pszDisplayName;
            *(_QWORD *)&v33.Size = v32.pszPublisher;
            v34 = &WindowName;
            v35 = &WindowName;
            AeComputeProgramIdentityHash(&v33, v36);
          }
        }
        if ( (unsigned int)dword_1800771FC < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_1800771F0) )
          NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessAffinityMask|0x40, &off_1800771F0, 0x18u);
        LODWORD(pv) = (*(__int64 (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v30 + 64LL))(v30, *((_QWORD *)v4 + 3));
        v5 = (int)pv;
        if ( (int)pv < 0 )
        {
          if ( (unsigned int)dword_1800771CC < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_1800771C0) )
            NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessAffinityMask|0x40, &off_1800771C0, 0x18u);
          v13 = 0;
          if ( AppWizLogging::IsEnabled(v20, v19) )
            AppWizLoggingTelemetry::UninstallAppFailed<unsigned short * &,unsigned short * &,unsigned short (&)[45],long &>(
              &v32.pszDisplayName,
              &v32.pszPublisher,
              v36,
              &pv);
        }
        else
        {
          if ( (unsigned int)dword_1800771E4 < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_1800771D8) )
            NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessAffinityMask|0x40, &off_1800771D8, 0x18u);
          v13 = 1;
          if ( AppWizLogging::IsEnabled(v20, v19) )
            AppWizLoggingTelemetry::UninstallAppSucceeded<unsigned short * &,unsigned short * &,unsigned short (&)[45],long &>(
              &v32.pszDisplayName,
              &v32.pszPublisher,
              v36,
              &pv);
        }
        ClearAppInfoData(&v32);
        Parameter = v4 + 9;
        if ( !v4[9] )
        {
          pv = 0;
          if ( (int)RecreateInstalledApp((struct tagAppRecreateInfo *)Parameter, (struct IInstalledApp **)&pv) >= 0 )
          {
            v13 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
        }
        goto LABEL_60;
      }
      v16 = UninstallCBSPackage((struct tagInstalledAppData *)v4);
    }
    v5 = v16;
    v13 = v16 >= 0;
LABEL_60:
    v10 = v30;
    goto LABEL_61;
  }
  LODWORD(Parameter) = v4[4] - 5;
  if ( v4[4] == 5
    || (LODWORD(Parameter) = v4[4] - 6, v4[4] == 6)
    || (LODWORD(Parameter) = v4[4] - 7, (unsigned int)Parameter <= 1) )
  {
    if ( v10 )
    {
      memset_0(&v32.pszDisplayName, 0, 0x90u);
      v32.cbSize = 152;
      v32.dwMask = 787072;
      v5 = (*(__int64 (__fastcall **)(HWND, _AppInfoData *))(*(_QWORD *)v10 + 24LL))(v10, &v32);
      if ( v5 >= 0 )
      {
        pszHelpLink = v32.pszHelpLink;
        if ( v32.pszHelpLink && v4[4] == 5
          || (pszHelpLink = v32.pszUpdateInfoUrl) != 0 && v4[4] == 8
          || (pszHelpLink = v32.pszReadmeUrl) != 0 && v4[4] == 7
          || (pszHelpLink = v32.pszSupportUrl) != 0 && v4[4] == 6 )
        {
          ShellExecuteW(0, 0, pszHelpLink, 0, 0, 1);
        }
        ClearAppInfoData(&v32);
      }
      goto LABEL_60;
    }
  }
LABEL_61:
  v30 = 0;
  if ( v10 )
    (*(void (__fastcall **)(HWND))(*(_QWORD *)v10 + 16LL))(v10);
  if ( !v4[5] && (v5 == -2147023636 || v5 == -2147024156 || v5 == -2147023271 || v5 == -2147024891) )
  {
    v21 = (struct _ITEMID_CHILD *)*((_QWORD *)v4 + 1);
    v22 = *(struct _ITEMIDLIST_ABSOLUTE **)v4;
    pv = 0;
    if ( GetDisplayName(v22, v21, (unsigned __int16 **)&pv) >= 0 )
    {
      ShellMessageBoxW(
        g_hinst,
        *((HWND *)v4 + 3),
        (LPCWSTR)0x7FD,
        (LPCWSTR)((-(__int64)(v4[8] != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 159),
        0x30u,
        pv);
      CoTaskMemFree(pv);
    }
  }
  if ( v13 )
    goto LABEL_71;
LABEL_75:
  if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (int)Parameter,
      (int)&AppWizCpl_SoftwareExplorer_RemoveApplicationLaunch_Stop,
      (int)a3,
      (int)a4,
      &v33);
  FreePublishedAppDataParam(v4);
  return 0;
}

```

## disassembly

```asm
0x180014600  push    rbp
0x180014602  push    rbx
0x180014603  push    rsi
0x180014604  push    rdi
0x180014605  push    r12
0x180014607  push    r13
0x180014609  push    r14
0x18001460b  push    r15
0x18001460d  lea     rbp, [rsp-88h]
0x180014615  sub     rsp, 188h
0x18001461c  mov     rax, cs:__security_cookie
0x180014623  xor     rax, rsp
0x180014626  mov     [rbp+0C0h+var_50], rax
0x18001462a  xor     r15d, r15d
0x18001462d  mov     rdi, rcx
0x180014630  mov     esi, r15d
0x180014633  lea     r12d, [r15+1]
0x180014637  test    rcx, rcx
0x18001463a  jz      loc_180014B64
0x180014640  mov     eax, [rcx+10h]
0x180014643  mov     ebx, r15d
0x180014646  sub     eax, r12d
0x180014649  mov     [rsp+1C0h+var_188], r15
0x18001464e  cmp     eax, 3
0x180014651  lea     rcx, [rsp+1C0h+Point]; lpPoint
0x180014656  mov     eax, 80000000h
0x18001465b  setbe   bl
0x18001465e  mov     [rsp+1C0h+Point.y], eax
0x180014662  mov     [rsp+1C0h+Point.x], eax
0x180014666  call    cs:__imp_GetCursorPos
0x18001466c  test    ebx, ebx
0x18001466e  jz      short loc_180014699
0x180014670  mov     r9, qword ptr [rsp+1C0h+Point.x]; struct tagPOINT
0x180014675  lea     rax, [rsp+1C0h+var_188]
0x18001467a  mov     rdx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x18001467d  mov     qword ptr [rsp+1C0h+fuStyle], rax; HWND *
0x180014682  call    ?Stub_EnsureUniqueStubWithParent@@YAHPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@HUtagPOINT@@PEAPEAU1@@Z; Stub_EnsureUniqueStubWithParent(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,int,tagPOINT,HWND__ * *)
0x180014687  test    eax, eax
0x180014689  jnz     short loc_180014699
0x18001468b  mov     rcx, [rdi+18h]; HWND
0x18001468f  call    ?TaskDialog_CantRemoveMulti@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEAH2@Z; TaskDialog_CantRemoveMulti(HWND__ *,HINSTANCE__ *,int *,int *)
0x180014694  jmp     loc_180014B64
0x180014699  mov     rbx, r15
0x18001469c  mov     [rsp+1C0h+var_188], rbx
0x1800146a1  cmp     [rdi+14h], r15d
0x1800146a5  jnz     loc_18001472E
0x1800146ab  lea     rcx, [rdi+24h]; struct tagAppRecreateInfo *
0x1800146af  lea     rdx, [rsp+1C0h+var_188]; struct IInstalledApp **
0x1800146b4  call    ?RecreateInstalledApp@@YAJPEAUtagAppRecreateInfo@@PEAPEAUIInstalledApp@@@Z; RecreateInstalledApp(tagAppRecreateInfo *,IInstalledApp * *)
0x1800146b9  mov     esi, eax
0x1800146bb  test    eax, eax
0x1800146bd  jns     short loc_180014729
0x1800146bf  mov     rdx, [rdi+8]; struct _ITEMID_CHILD *
0x1800146c3  lea     r8, [rsp+1C0h+pv]; unsigned __int16 **
0x1800146c8  mov     rcx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x1800146cb  mov     [rsp+1C0h+pv], r15
0x1800146d0  call    ?GetDisplayName@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAU_ITEMID_CHILD@@PEAPEAG@Z; GetDisplayName(_ITEMIDLIST_ABSOLUTE *,_ITEMID_CHILD *,ushort * *)
0x1800146d5  test    eax, eax
0x1800146d7  js      loc_180014B0A
0x1800146dd  mov     eax, [rdi+20h]
0x1800146e0  mov     r8d, 90h; lpcText
0x1800146e6  mov     rdx, [rdi+18h]; hWnd
0x1800146ea  neg     eax
0x1800146ec  mov     rax, [rsp+1C0h+pv]
0x1800146f1  mov     rcx, cs:g_hinst; hAppInst
0x1800146f8  sbb     r9, r9
0x1800146fb  and     r9, 0FFFFFFFFFFFFFFFEh
0x1800146ff  mov     qword ptr [rsp+1C0h+nShowCmd], rax
0x180014704  add     r9, 9Fh; lpcTitle
0x18001470b  mov     [rsp+1C0h+fuStyle], 40h ; '@'; fuStyle
0x180014713  call    cs:__imp_ShellMessageBoxW
0x180014719  mov     rcx, [rsp+1C0h+pv]; pv
0x18001471e  call    cs:__imp_CoTaskMemFree
0x180014724  jmp     loc_180014B0A
0x180014729  mov     rbx, [rsp+1C0h+var_188]
0x18001472e  mov     ecx, [rdi+10h]
0x180014731  mov     r14d, r15d
0x180014734  sub     ecx, r12d
0x180014737  jz      loc_180014850
0x18001473d  sub     ecx, r12d
0x180014740  jz      loc_18001483E
0x180014746  sub     ecx, r12d
0x180014749  jz      loc_18001481B
0x18001474f  sub     ecx, r12d
0x180014752  jz      loc_180014850
0x180014758  sub     ecx, r12d
0x18001475b  jz      short loc_180014770
0x18001475d  sub     ecx, r12d
0x180014760  jz      short loc_180014770
0x180014762  sub     ecx, r12d
0x180014765  jz      short loc_180014770
0x180014767  cmp     ecx, r12d
0x18001476a  jnz     loc_180014A61
0x180014770  test    rbx, rbx
0x180014773  jz      loc_180014A61
0x180014779  xor     edx, edx; Val
0x18001477b  lea     rcx, [rsp+1C0h+var_170.pszDisplayName]; void *
0x180014780  mov     r8d, 90h; Size
0x180014786  call    memset_0
0x18001478b  mov     [rsp+1C0h+var_170.cbSize], 98h
0x180014793  lea     rdx, [rsp+1C0h+var_170]
0x180014798  mov     [rsp+1C0h+var_170.dwMask], 0C0280h
0x1800147a0  mov     rcx, rbx
0x1800147a3  mov     rax, [rbx]
0x1800147a6  mov     rax, [rax+18h]
0x1800147aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147af  mov     esi, eax
0x1800147b1  test    eax, eax
0x1800147b3  js      loc_180014A5C
0x1800147b9  mov     r8, [rbp+0C0h+var_170.pszHelpLink]
0x1800147bd  test    r8, r8
0x1800147c0  jz      short loc_1800147C8
0x1800147c2  cmp     dword ptr [rdi+10h], 5
0x1800147c6  jz      short loc_1800147F5
0x1800147c8  mov     r8, [rbp+0C0h+var_170.pszUpdateInfoUrl]
0x1800147cc  test    r8, r8
0x1800147cf  jz      short loc_1800147D7
0x1800147d1  cmp     dword ptr [rdi+10h], 8
0x1800147d5  jz      short loc_1800147F5
0x1800147d7  mov     r8, [rbp+0C0h+var_170.pszReadmeUrl]
0x1800147db  test    r8, r8
0x1800147de  jz      short loc_1800147E6
0x1800147e0  cmp     dword ptr [rdi+10h], 7
0x1800147e4  jz      short loc_1800147F5
0x1800147e6  mov     r8, [rbp+0C0h+var_170.pszSupportUrl]; lpFile
0x1800147ea  test    r8, r8
0x1800147ed  jz      short loc_18001480C
0x1800147ef  cmp     dword ptr [rdi+10h], 6
0x1800147f3  jnz     short loc_18001480C
0x1800147f5  mov     [rsp+1C0h+nShowCmd], r12d; nShowCmd
0x1800147fa  xor     r9d, r9d; lpParameters
0x1800147fd  xor     edx, edx; lpOperation
0x1800147ff  mov     qword ptr [rsp+1C0h+fuStyle], r15; lpDirectory
0x180014804  xor     ecx, ecx; hwnd
0x180014806  call    cs:__imp_ShellExecuteW
0x18001480c  lea     rcx, [rsp+1C0h+var_170]; struct _AppInfoData *
0x180014811  call    ?ClearAppInfoData@@YAXPEAU_AppInfoData@@@Z; ClearAppInfoData(_AppInfoData *)
0x180014816  jmp     loc_180014A5C
0x18001481b  test    rbx, rbx
0x18001481e  jz      loc_180014A61
0x180014824  mov     rax, [rbx]
0x180014827  mov     rax, [rax+50h]
0x18001482b  mov     rdx, [rdi+18h]
0x18001482f  mov     rcx, rbx
0x180014832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014837  mov     esi, eax
0x180014839  jmp     loc_180014A5C
0x18001483e  test    rbx, rbx
0x180014841  jz      loc_180014A61
0x180014847  mov     rax, [rbx]
0x18001484a  mov     rax, [rax+48h]
0x18001484e  jmp     short loc_18001482B
0x180014850  cmp     dword ptr [rdi+14h], 2
0x180014854  jnz     short loc_18001486F
0x180014856  mov     rcx, rdi; struct tagInstalledAppData *
0x180014859  call    ?UninstallVUEPackage@@YAJPEAUtagInstalledAppData@@@Z; UninstallVUEPackage(tagInstalledAppData *)
0x18001485e  mov     r14d, eax
0x180014861  mov     esi, eax
0x180014863  not     r14d
0x180014866  shr     r14d, 1Fh
0x18001486a  jmp     loc_180014A5C
0x18001486f  cmp     [rdi+14h], r12d
0x180014873  jnz     short loc_18001487F
0x180014875  mov     rcx, rdi; struct tagInstalledAppData *
0x180014878  call    ?UninstallCBSPackage@@YAJPEAUtagInstalledAppData@@@Z; UninstallCBSPackage(tagInstalledAppData *)
0x18001487d  jmp     short loc_18001485E
0x18001487f  test    rbx, rbx
0x180014882  jz      loc_180014A61
0x180014888  xor     edx, edx; Val
0x18001488a  lea     rcx, [rsp+1C0h+var_170]; void *
0x18001488f  mov     r8d, 98h; Size
0x180014895  call    memset_0
0x18001489a  xor     edx, edx; Val
0x18001489c  lea     rcx, [rbp+0C0h+var_B0]; void *
0x1800148a0  lea     r8d, [rdx+5Ah]; Size
0x1800148a4  call    memset_0
0x1800148a9  call    ?IsEnabled@AppWizLogging@@SA_NE_K@Z; AppWizLogging::IsEnabled(uchar,unsigned __int64)
0x1800148ae  test    al, al
0x1800148b0  jz      short loc_18001490A
0x1800148b2  mov     rcx, [rsp+1C0h+var_188]
0x1800148b7  lea     rdx, [rsp+1C0h+var_170]
0x1800148bc  mov     [rsp+1C0h+var_170.cbSize], 98h
0x1800148c4  mov     [rsp+1C0h+var_170.dwMask], 5
0x1800148cc  mov     rax, [rcx]
0x1800148cf  mov     rax, [rax+18h]
0x1800148d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d8  test    eax, eax
0x1800148da  js      short loc_18001490A
0x1800148dc  mov     rax, [rsp+1C0h+var_170.pszDisplayName]
0x1800148e1  lea     rdx, [rbp+0C0h+var_B0]
0x1800148e5  mov     [rbp+0C0h+var_D0.Ptr], rax
0x1800148e9  lea     rcx, [rbp+0C0h+var_D0]
0x1800148ed  mov     rax, [rsp+1C0h+var_170.pszPublisher]
0x1800148f2  mov     qword ptr [rbp+0C0h+var_D0.Size], rax
0x1800148f6  lea     rax, WindowName
0x1800148fd  mov     [rbp+0C0h+var_C0], rax
0x180014901  mov     [rbp+0C0h+var_B8], rax
0x180014905  call    AeComputeProgramIdentityHash
0x18001490a  mov     eax, ds:7FFE037Ch
0x180014911  mov     ebx, 18h
0x180014916  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001491a  cmp     cs:dword_1800771FC, eax
0x180014920  lea     r14d, [rbx+3Dh]
0x180014924  jnb     short loc_18001494D
0x180014926  lea     rcx, off_1800771F0; "Shell_ARP_UninstallApp"
0x18001492d  call    cs:__imp_EtwCheckCoverage
0x180014933  test    al, al
0x180014935  jnz     short loc_18001494D
0x180014937  mov     r9d, ebx; ProcessInformationLength
0x18001493a  lea     r8, off_1800771F0; ProcessInformation
0x180014941  mov     edx, r14d; ProcessInformationClass
0x180014944  mov     rcx, r13; ProcessHandle
0x180014947  call    cs:__imp_NtSetInformationProcess
0x18001494d  mov     rcx, [rsp+1C0h+var_188]
0x180014952  mov     rdx, [rdi+18h]
0x180014956  mov     rax, [rcx]
0x180014959  mov     rax, [rax+40h]
0x18001495d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014962  mov     dword ptr [rsp+1C0h+pv], eax
0x180014966  mov     esi, eax
0x180014968  test    eax, eax
0x18001496a  js      short loc_1800149C8
0x18001496c  mov     eax, ds:7FFE037Ch
0x180014973  cmp     cs:dword_1800771E4, eax
0x180014979  jnb     short loc_1800149A2
0x18001497b  lea     rcx, off_1800771D8; "Shell_ARP_UninstallApp_Success"
0x180014982  call    cs:__imp_EtwCheckCoverage
0x180014988  test    al, al
0x18001498a  jnz     short loc_1800149A2
0x18001498c  mov     r9d, ebx; ProcessInformationLength
0x18001498f  lea     r8, off_1800771D8; ProcessInformation
0x180014996  mov     edx, r14d; ProcessInformationClass
0x180014999  mov     rcx, r13; ProcessHandle
0x18001499c  call    cs:__imp_NtSetInformationProcess
0x1800149a2  mov     r14d, r12d
0x1800149a5  call    ?IsEnabled@AppWizLogging@@SA_NE_K@Z; AppWizLogging::IsEnabled(uchar,unsigned __int64)
0x1800149aa  test    al, al
0x1800149ac  jz      short loc_180014A22
0x1800149ae  lea     r9, [rsp+1C0h+pv]
0x1800149b3  lea     r8, [rbp+0C0h+var_B0]
0x1800149b7  lea     rdx, [rsp+1C0h+var_170.pszPublisher]
0x1800149bc  lea     rcx, [rsp+1C0h+var_170.pszDisplayName]
0x1800149c1  call    ??$UninstallAppSucceeded@AEAPEAGAEAPEAGAEAY0CN@GAEAJ@AppWizLoggingTelemetry@@SAXAEAPEAG0AEAY0CN@GAEAJ@Z; AppWizLoggingTelemetry::UninstallAppSucceeded<ushort * &,ushort * &,ushort (&)[45],long &>(ushort * &,ushort * &,ushort (&)[45],long &)
0x1800149c6  jmp     short loc_180014A22
0x1800149c8  mov     eax, ds:7FFE037Ch
0x1800149cf  cmp     cs:dword_1800771CC, eax
0x1800149d5  jnb     short loc_1800149FE
0x1800149d7  lea     rcx, off_1800771C0; "Shell_ARP_UninstallApp_Failure"
0x1800149de  call    cs:__imp_EtwCheckCoverage
0x1800149e4  test    al, al
0x1800149e6  jnz     short loc_1800149FE
0x1800149e8  mov     r9d, ebx; ProcessInformationLength
0x1800149eb  lea     r8, off_1800771C0; ProcessInformation
0x1800149f2  mov     edx, r14d; ProcessInformationClass
0x1800149f5  mov     rcx, r13; ProcessHandle
0x1800149f8  call    cs:__imp_NtSetInformationProcess
0x1800149fe  mov     r14d, r15d
0x180014a01  call    ?IsEnabled@AppWizLogging@@SA_NE_K@Z; AppWizLogging::IsEnabled(uchar,unsigned __int64)
0x180014a06  test    al, al
0x180014a08  jz      short loc_180014A22
0x180014a0a  lea     r9, [rsp+1C0h+pv]
0x180014a0f  lea     r8, [rbp+0C0h+var_B0]
0x180014a13  lea     rdx, [rsp+1C0h+var_170.pszPublisher]
0x180014a18  lea     rcx, [rsp+1C0h+var_170.pszDisplayName]
0x180014a1d  call    ??$UninstallAppFailed@AEAPEAGAEAPEAGAEAY0CN@GAEAJ@AppWizLoggingTelemetry@@SAXAEAPEAG0AEAY0CN@GAEAJ@Z; AppWizLoggingTelemetry::UninstallAppFailed<ushort * &,ushort * &,ushort (&)[45],long &>(ushort * &,ushort * &,ushort (&)[45],long &)
0x180014a22  lea     rcx, [rsp+1C0h+var_170]; struct _AppInfoData *
0x180014a27  call    ?ClearAppInfoData@@YAXPEAU_AppInfoData@@@Z; ClearAppInfoData(_AppInfoData *)
0x180014a2c  lea     rcx, [rdi+24h]; struct tagAppRecreateInfo *
0x180014a30  cmp     [rcx], r15d
0x180014a33  jnz     short loc_180014A5C
0x180014a35  lea     rdx, [rsp+1C0h+pv]; struct IInstalledApp **
0x180014a3a  mov     [rsp+1C0h+pv], r15
0x180014a3f  call    ?RecreateInstalledApp@@YAJPEAUtagAppRecreateInfo@@PEAPEAUIInstalledApp@@@Z; RecreateInstalledApp(tagAppRecreateInfo *,IInstalledApp * *)
0x180014a44  test    eax, eax
0x180014a46  js      short loc_180014A5C
0x180014a48  mov     rcx, [rsp+1C0h+pv]
0x180014a4d  mov     r14d, r15d
0x180014a50  mov     rax, [rcx]
0x180014a53  mov     rax, [rax+10h]
0x180014a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a5c  mov     rbx, [rsp+1C0h+var_188]
0x180014a61  mov     [rsp+1C0h+var_188], r15
0x180014a66  test    rbx, rbx
0x180014a69  jz      short loc_180014A7A
0x180014a6b  mov     rax, [rbx]
0x180014a6e  mov     rcx, rbx
0x180014a71  mov     rax, [rax+10h]
0x180014a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a7a  cmp     [rdi+14h], r15d
0x180014a7e  jnz     loc_180014B05
0x180014a84  cmp     esi, 800704ECh
0x180014a8a  jz      short loc_180014AA4
0x180014a8c  cmp     esi, 800702E4h
0x180014a92  jz      short loc_180014AA4
0x180014a94  cmp     esi, 80070659h
0x180014a9a  jz      short loc_180014AA4
0x180014a9c  cmp     esi, 80070005h
0x180014aa2  jnz     short loc_180014B05
0x180014aa4  mov     rdx, [rdi+8]; struct _ITEMID_CHILD *
0x180014aa8  lea     r8, [rsp+1C0h+pv]; unsigned __int16 **
  ... truncated ...
```
