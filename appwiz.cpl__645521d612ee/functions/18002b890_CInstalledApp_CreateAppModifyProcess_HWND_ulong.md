# CInstalledApp::_CreateAppModifyProcess(HWND__ *,ulong)

- ea: `0x18002b890`
- end: `0x18002bdd1`
- name: `?_CreateAppModifyProcess@CInstalledApp@@AEAAJPEAUHWND__@@K@Z`
- size: `1345`
- prototype: `__int64 __fastcall(CInstalledApp *this, HWND, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b050`
- `0x18002c528`

## callees

- `0x180008cf8`
- `0x18002a2f0`
- `0x18002a8c0`
- `0x18002b2b0`
- `0x18002b890`
- `0x18002c148`
- `0x180050c74`
- `0x1800568b4`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18002b9d6`
- `SHELL32!ShellExecuteExW` at `0x18002b9d6`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002b91b`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002bd7b`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002b91b`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002bd7b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002bd2b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18002bd2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b9e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b9e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bcce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bcce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd95`
- `USER32!AllowSetForegroundWindow` at `0x18002ba91`
- `USER32!AllowSetForegroundWindow` at `0x18002bb10`
- `USER32!AllowSetForegroundWindow` at `0x18002ba91`
- `USER32!AllowSetForegroundWindow` at `0x18002bb10`

## pseudocode

```c
__int64 __fastcall CInstalledApp::_CreateAppModifyProcess(CInstalledApp *this, HWND a2, int a3)
{
  char v4; // si
  unsigned int v5; // esi
  int v7; // r14d
  const WCHAR *v8; // r12
  int IsNetAndCreatable; // r13d
  int NewUninstallProgram; // ebx
  unsigned int v11; // r8d
  signed int LastError; // eax
  unsigned int UninstallClassContext; // eax
  const struct _GUID *v14; // r8
  const struct _GUID *v15; // r9
  HRESULT v16; // eax
  DWORD v17; // eax
  int v18; // r14d
  LPVOID v19; // rcx
  unsigned int v20; // eax
  const struct _GUID *v21; // r8
  const struct _GUID *v22; // r9
  bool v23; // cf
  LPVOID v24; // rcx
  unsigned int v25; // eax
  const struct _GUID *v26; // r8
  const struct _GUID *v27; // r9
  HRESULT v28; // eax
  DWORD v29; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  PWSTR *v32; // [rsp+28h] [rbp-D8h]
  int pnButton; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v34; // [rsp+38h] [rbp-C8h] BYREF
  __int128 ppszApplication; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  TASKDIALOGCONFIG pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v38[264]; // [rsp+100h] [rbp+0h] BYREF

  v4 = ~(unsigned __int8)*((_DWORD *)this + 7);
  pnButton = a3;
  v5 = v4 & 1;
  if ( a3 == 1 )
  {
    v7 = *((_DWORD *)this + 1332);
    v8 = (const WCHAR *)((char *)this + 556);
  }
  else
  {
    v8 = (const WCHAR *)((char *)this + 2116);
    v7 = v5;
  }
  ppszApplication = 0u;
  IsNetAndCreatable = 1;
  NewUninstallProgram = SHEvaluateSystemCommandTemplate(v8, (PWSTR *)&ppszApplication, 0, (PWSTR *)&ppszApplication + 1);
  if ( NewUninstallProgram < 0 )
  {
    IsNetAndCreatable = PathIsNetAndCreatable(v8, v38, v11);
    if ( IsNetAndCreatable )
    {
      NewUninstallProgram = 0;
    }
    else
    {
      NewUninstallProgram = GetNewUninstallProgram(
                              a2,
                              (*((_DWORD *)this + 7) & 1) == 0,
                              v38,
                              (unsigned __int16 *)this + 18,
                              (PWSTR *)&ppszApplication,
                              (PWSTR *)&ppszApplication + 1);
      if ( NewUninstallProgram >= 0 )
      {
        pExecInfo.cbSize = 112;
        memset_0(&pExecInfo.hwndParent, 0, 0x6Cu);
        *(_OWORD *)&pExecInfo.dwCommonButtons = ppszApplication;
        LODWORD(pExecInfo.hwndParent) = 33555264;
        HIDWORD(pExecInfo.pszMainInstruction) = 1;
        *(HWND *)((char *)&pExecInfo.hwndParent + 4) = a2;
        *(HINSTANCE *)((char *)&pExecInfo.hInstance + 4) = (HINSTANCE)((unsigned __int64)L"RunAs" & -(__int64)(v7 != 0));
        if ( ShellExecuteExW((SHELLEXECUTEINFOW *)&pExecInfo) )
        {
          WaitForSingleObject(*(HANDLE *)((char *)&pExecInfo.pszExpandedInformation + 4), 0xFFFFFFFF);
        }
        else
        {
          LastError = GetLastError();
          NewUninstallProgram = LastError;
          if ( LastError > 0 )
            NewUninstallProgram = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  CoTaskMemFree((LPVOID)ppszApplication);
  CoTaskMemFree(*((LPVOID *)&ppszApplication + 1));
  v34 = 0;
  if ( NewUninstallProgram < 0 )
    goto LABEL_25;
  if ( !IsNetAndCreatable )
    goto LABEL_52;
  if ( v7 )
  {
    UninstallClassContext = CInstalledApp::_GetUninstallClassContext(this, v7);
    v16 = CoCreateInstanceAsAdminWithCorrectBitness(a2, UninstallClassContext, v14, v15, &v34);
  }
  else
  {
    v17 = CInstalledApp::_GetUninstallClassContext(this, 0);
    v16 = CoCreateInstance(
            &GUID_fcc74b77_ec3e_4dd8_a80b_008a702075a9,
            0,
            v17,
            &GUID_f885120e_3789_4fd9_865e_dc9b4a6412d2,
            &v34);
  }
  NewUninstallProgram = v16;
  if ( v16 < 0 )
  {
LABEL_25:
    v18 = pnButton;
    goto LABEL_26;
  }
  AllowSetForegroundWindow(0xFFFFFFFF);
  v18 = pnButton;
  ppv = (LPVOID *)a2;
  NewUninstallProgram = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *, _QWORD))(*(_QWORD *)v34 + 24LL))(
                          v34,
                          v5,
                          (char *)this + 4288,
                          (unsigned int)pnButton);
  if ( NewUninstallProgram == -2147024156 )
  {
    v19 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = CInstalledApp::_GetUninstallClassContext(this, 1);
    NewUninstallProgram = CoCreateInstanceAsAdminWithCorrectBitness(a2, v20, v21, v22, &v34);
    if ( NewUninstallProgram < 0 )
      goto LABEL_26;
    AllowSetForegroundWindow(0xFFFFFFFF);
    ppv = (LPVOID *)a2;
    NewUninstallProgram = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *, _QWORD))(*(_QWORD *)v34 + 24LL))(
                            v34,
                            v5,
                            (char *)this + 4288,
                            (unsigned int)pnButton);
  }
  if ( NewUninstallProgram >= 0 )
  {
LABEL_46:
    if ( !v18
      && NewUninstallProgram != -2147023673
      && NewUninstallProgram != -2147023436
      && !(*(unsigned int (__fastcall **)(CInstalledApp *))(*(_QWORD *)this + 56LL))(this)
      && SHEvaluateSystemCommandTemplate(v8, (PWSTR *)&ppszApplication, 0, (PWSTR *)&ppszApplication + 1) >= 0 )
    {
      CoTaskMemFree((LPVOID)ppszApplication);
      CoTaskMemFree(*((LPVOID *)&ppszApplication + 1));
    }
    goto LABEL_52;
  }
LABEL_26:
  if ( NewUninstallProgram == -2147023673
    || NewUninstallProgram == -2147023436
    || NewUninstallProgram == -2147023636
    || NewUninstallProgram == -2147024156
    || NewUninstallProgram == -2147024891 )
  {
    if ( !IsNetAndCreatable )
      goto LABEL_52;
    goto LABEL_46;
  }
  v23 = *((_WORD *)this + 2666) != 0;
  hMem[0] = 0;
  NewUninstallProgram = SHFormatResMessageArgAlloc(g_hinst, (unsigned int)v23 + 2031, hMem, (char *)this + 36, ppv, v32);
  if ( NewUninstallProgram >= 0 )
  {
    pExecInfo.cbSize = 160;
    memset_0(&pExecInfo.hwndParent, 0, 0x9Cu);
    pExecInfo.hInstance = g_hinst;
    v23 = *((_WORD *)this + 2666) != 0;
    pExecInfo.hwndParent = a2;
    pExecInfo.pszContent = (PCWSTR)hMem[0];
    pExecInfo.dwFlags = 8;
    pExecInfo.dwCommonButtons = 6;
    pExecInfo.nDefaultButton = 7;
    pExecInfo.pszWindowTitle = (PCWSTR)((-(__int64)v23 & 0xFFFFFFFFFFFFFFFEuLL) + 159);
    pExecInfo.hMainIcon = (HICON)0xFFFF;
    pExecInfo.pfCallback = (PFTASKDIALOGCALLBACK)TaskDialogCallbackProc;
    if ( !v5 || (pExecInfo.lpCallbackData = 1, v34) )
      pExecInfo.lpCallbackData = 0;
    pnButton = 0;
    TaskDialogIndirect(&pExecInfo, &pnButton, 0, 0);
    if ( pnButton != 6 )
      goto LABEL_44;
    v24 = v34;
    if ( !v34 )
    {
      if ( v5 )
      {
        v25 = CInstalledApp::_GetUninstallClassContext(this, v5);
        v28 = CoCreateInstanceAsAdminWithCorrectBitness(a2, v25, v26, v27, &v34);
      }
      else
      {
        v29 = CInstalledApp::_GetUninstallClassContext(this, 0);
        v28 = CoCreateInstance(
                &GUID_fcc74b77_ec3e_4dd8_a80b_008a702075a9,
                0,
                v29,
                &GUID_f885120e_3789_4fd9_865e_dc9b4a6412d2,
                &v34);
      }
      NewUninstallProgram = v28;
      if ( v28 < 0 )
        goto LABEL_44;
      v24 = v34;
    }
    NewUninstallProgram = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v24 + 32LL))(
                            v24,
                            v5,
                            (char *)this + 4288);
    if ( NewUninstallProgram < 0 )
      ShellMessageBoxW(
        g_hinst,
        a2,
        (LPCWSTR)0x7FC,
        (LPCWSTR)((-(__int64)(*((_WORD *)this + 2666) != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 159),
        0x30u,
        (char *)this + 36);
LABEL_44:
    LocalFree(hMem[0]);
  }
LABEL_52:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  return (unsigned int)NewUninstallProgram;
}

```

## disassembly

```asm
0x18002b890  mov     [rsp-8+arg_18], rbx
0x18002b895  push    rbp
0x18002b896  push    rsi
0x18002b897  push    rdi
0x18002b898  push    r12
0x18002b89a  push    r13
0x18002b89c  push    r14
0x18002b89e  push    r15
0x18002b8a0  lea     rbp, [rsp-220h]
0x18002b8a8  sub     rsp, 320h
0x18002b8af  mov     rax, cs:__security_cookie
0x18002b8b6  xor     rax, rsp
0x18002b8b9  mov     [rbp+250h+var_40], rax
0x18002b8c0  mov     esi, [rcx+1Ch]
0x18002b8c3  mov     r15, rdx
0x18002b8c6  not     esi
0x18002b8c8  mov     [rsp+350h+pnButton], r8d
0x18002b8cd  and     esi, 1
0x18002b8d0  mov     rdi, rcx
0x18002b8d3  cmp     r8d, 1
0x18002b8d7  jnz     short loc_18002B8E9
0x18002b8d9  mov     r14d, [rcx+14D0h]
0x18002b8e0  lea     r12, [rcx+22Ch]
0x18002b8e7  jmp     short loc_18002B8F3
0x18002b8e9  lea     r12, [rcx+844h]
0x18002b8f0  mov     r14d, esi
0x18002b8f3  lea     r9, [rsp+350h+ppszParameters]; ppszParameters
0x18002b8f8  mov     [rsp+350h+ppszApplication], 0
0x18002b901  xor     r8d, r8d; ppszCommandLine
0x18002b904  mov     [rsp+350h+ppszParameters], 0
0x18002b90d  lea     rdx, [rsp+350h+ppszApplication]; ppszApplication
0x18002b912  mov     rcx, r12; pszCmdTemplate
0x18002b915  mov     r13d, 1
0x18002b91b  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18002b921  mov     ebx, eax
0x18002b923  test    eax, eax
0x18002b925  jns     loc_18002BA04
0x18002b92b  lea     rdx, [rbp+250h+var_250]; unsigned __int16 *
0x18002b92f  mov     rcx, r12; unsigned __int16 *
0x18002b932  call    ?PathIsNetAndCreatable@@YAHPEBGPEAGI@Z; PathIsNetAndCreatable(ushort const *,ushort *,uint)
0x18002b937  mov     r13d, eax
0x18002b93a  test    eax, eax
0x18002b93c  jz      short loc_18002B945
0x18002b93e  xor     ebx, ebx
0x18002b940  jmp     loc_18002BA04
0x18002b945  mov     edx, [rdi+1Ch]
0x18002b948  lea     rax, [rsp+350h+ppszParameters]
0x18002b94d  mov     [rsp+350h+var_328], rax; ppszParameters
0x18002b952  lea     r9, [rdi+24h]; unsigned __int16 *
0x18002b956  not     edx
0x18002b958  lea     rax, [rsp+350h+ppszApplication]
0x18002b95d  and     edx, 1; int
0x18002b960  mov     [rsp+350h+ppv], rax; ppszApplication
0x18002b965  lea     r8, [rbp+250h+var_250]; unsigned __int16 *
0x18002b969  mov     rcx, r15; HWND
0x18002b96c  call    ?GetNewUninstallProgram@@YAJPEAUHWND__@@HPEAG1PEAPEAG2@Z; GetNewUninstallProgram(HWND__ *,int,ushort *,ushort *,ushort * *,ushort * *)
0x18002b971  mov     ebx, eax
0x18002b973  test    eax, eax
0x18002b975  js      loc_18002BA04
0x18002b97b  xor     edx, edx; Val
0x18002b97d  mov     [rsp+350h+pExecInfo.cbSize], 70h ; 'p'
0x18002b985  lea     rcx, [rsp+350h+pExecInfo.fMask]; void *
0x18002b98a  lea     r8d, [rdx+6Ch]; Size
0x18002b98e  call    memset_0
0x18002b993  mov     rax, [rsp+350h+ppszApplication]
0x18002b998  mov     [rsp+350h+pExecInfo.lpFile], rax
0x18002b99d  mov     rax, [rsp+350h+ppszParameters]
0x18002b9a2  mov     [rbp+250h+pExecInfo.lpParameters], rax
0x18002b9a6  mov     eax, r14d
0x18002b9a9  neg     eax
0x18002b9ab  mov     [rsp+350h+pExecInfo.fMask], 2000340h
0x18002b9b3  lea     rax, aRunas; "RunAs"
0x18002b9ba  mov     [rbp+250h+pExecInfo.nShow], 1
0x18002b9c1  sbb     rcx, rcx
0x18002b9c4  mov     [rsp+350h+pExecInfo.hwnd], r15
0x18002b9c9  and     rcx, rax
0x18002b9cc  mov     [rsp+350h+pExecInfo.lpVerb], rcx
0x18002b9d1  lea     rcx, [rsp+350h+pExecInfo]; pExecInfo
0x18002b9d6  call    cs:__imp_ShellExecuteExW
0x18002b9dc  test    eax, eax
0x18002b9de  jz      short loc_18002B9EF
0x18002b9e0  mov     rcx, [rbp+250h+pExecInfo.hProcess]; hHandle
0x18002b9e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b9e7  call    cs:__imp_WaitForSingleObject
0x18002b9ed  jmp     short loc_18002BA04
0x18002b9ef  call    cs:__imp_GetLastError
0x18002b9f5  mov     ebx, eax
0x18002b9f7  test    eax, eax
0x18002b9f9  jle     short loc_18002BA04
0x18002b9fb  movzx   ebx, ax
0x18002b9fe  or      ebx, 80070000h
0x18002ba04  mov     rcx, [rsp+350h+ppszApplication]; pv
0x18002ba09  call    cs:__imp_CoTaskMemFree
0x18002ba0f  mov     rcx, [rsp+350h+ppszParameters]; pv
0x18002ba14  call    cs:__imp_CoTaskMemFree
0x18002ba1a  mov     [rsp+350h+var_318], 0
0x18002ba23  test    ebx, ebx
0x18002ba25  js      loc_18002BB44
0x18002ba2b  test    r13d, r13d
0x18002ba2e  jz      loc_18002BD9B
0x18002ba34  mov     rcx, rdi; this
0x18002ba37  test    r14d, r14d
0x18002ba3a  jz      short loc_18002BA5A
0x18002ba3c  mov     edx, r14d; int
0x18002ba3f  call    ?_GetUninstallClassContext@CInstalledApp@@AEAAKH@Z; CInstalledApp::_GetUninstallClassContext(int)
0x18002ba44  lea     rcx, [rsp+350h+var_318]
0x18002ba49  mov     edx, eax; unsigned int
0x18002ba4b  mov     [rsp+350h+ppv], rcx; ppv
0x18002ba50  mov     rcx, r15; HWND
0x18002ba53  call    ?CoCreateInstanceAsAdminWithCorrectBitness@@YAJPEAUHWND__@@KAEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdminWithCorrectBitness(HWND__ *,ulong,_GUID const &,_GUID const &,void * *)
0x18002ba58  jmp     short loc_18002BA84
0x18002ba5a  xor     edx, edx; int
0x18002ba5c  call    ?_GetUninstallClassContext@CInstalledApp@@AEAAKH@Z; CInstalledApp::_GetUninstallClassContext(int)
0x18002ba61  lea     rcx, [rsp+350h+var_318]
0x18002ba66  mov     r8d, eax; dwClsContext
0x18002ba69  mov     [rsp+350h+ppv], rcx; ppv
0x18002ba6e  lea     r9, _GUID_f885120e_3789_4fd9_865e_dc9b4a6412d2; riid
0x18002ba75  lea     rcx, _GUID_fcc74b77_ec3e_4dd8_a80b_008a702075a9; rclsid
0x18002ba7c  xor     edx, edx; pUnkOuter
0x18002ba7e  call    cs:__imp_CoCreateInstance
0x18002ba84  mov     ebx, eax
0x18002ba86  test    eax, eax
0x18002ba88  js      loc_18002BB44
0x18002ba8e  or      ecx, 0FFFFFFFFh; dwProcessId
0x18002ba91  call    cs:__imp_AllowSetForegroundWindow
0x18002ba97  mov     rcx, [rsp+350h+var_318]
0x18002ba9c  lea     r8, [rdi+10C0h]
0x18002baa3  mov     r14d, [rsp+350h+pnButton]
0x18002baa8  mov     edx, esi
0x18002baaa  mov     r9d, r14d
0x18002baad  mov     [rsp+350h+ppv], r15
0x18002bab2  mov     rax, [rcx]
0x18002bab5  mov     rax, [rax+18h]
0x18002bab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002babe  mov     ebx, eax
0x18002bac0  cmp     eax, 800702E4h
0x18002bac5  jnz     short loc_18002BB3A
0x18002bac7  mov     rcx, [rsp+350h+var_318]
0x18002bacc  test    rcx, rcx
0x18002bacf  jz      short loc_18002BAE6
0x18002bad1  mov     [rsp+350h+var_318], 0
0x18002bada  mov     rax, [rcx]
0x18002badd  mov     rax, [rax+10h]
0x18002bae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae6  mov     edx, 1; int
0x18002baeb  mov     rcx, rdi; this
0x18002baee  call    ?_GetUninstallClassContext@CInstalledApp@@AEAAKH@Z; CInstalledApp::_GetUninstallClassContext(int)
0x18002baf3  lea     rcx, [rsp+350h+var_318]
0x18002baf8  mov     edx, eax; unsigned int
0x18002bafa  mov     [rsp+350h+ppv], rcx; ppv
0x18002baff  mov     rcx, r15; HWND
0x18002bb02  call    ?CoCreateInstanceAsAdminWithCorrectBitness@@YAJPEAUHWND__@@KAEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdminWithCorrectBitness(HWND__ *,ulong,_GUID const &,_GUID const &,void * *)
0x18002bb07  mov     ebx, eax
0x18002bb09  test    eax, eax
0x18002bb0b  js      short loc_18002BB49
0x18002bb0d  or      ecx, 0FFFFFFFFh; dwProcessId
0x18002bb10  call    cs:__imp_AllowSetForegroundWindow
0x18002bb16  mov     rcx, [rsp+350h+var_318]
0x18002bb1b  lea     r8, [rdi+10C0h]
0x18002bb22  mov     r9d, r14d
0x18002bb25  mov     [rsp+350h+ppv], r15
0x18002bb2a  mov     edx, esi
0x18002bb2c  mov     rax, [rcx]
0x18002bb2f  mov     rax, [rax+18h]
0x18002bb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb38  mov     ebx, eax
0x18002bb3a  test    ebx, ebx
0x18002bb3c  jns     loc_18002BD43
0x18002bb42  jmp     short loc_18002BB49
0x18002bb44  mov     r14d, [rsp+350h+pnButton]
0x18002bb49  cmp     ebx, 800704C7h
0x18002bb4f  jz      loc_18002BD3E
0x18002bb55  cmp     ebx, 800705B4h
0x18002bb5b  jz      loc_18002BD3E
0x18002bb61  cmp     ebx, 800704ECh
0x18002bb67  jz      loc_18002BD3E
0x18002bb6d  cmp     ebx, 800702E4h
0x18002bb73  jz      loc_18002BD3E
0x18002bb79  cmp     ebx, 80070005h
0x18002bb7f  jz      loc_18002BD3E
0x18002bb85  movzx   eax, word ptr [rdi+14D4h]
0x18002bb8c  lea     r14, [rdi+24h]
0x18002bb90  mov     rcx, cs:g_hinst
0x18002bb97  lea     r8, [rsp+350h+hMem]
0x18002bb9c  xor     r12d, r12d
0x18002bb9f  mov     r9, r14
0x18002bba2  neg     ax
0x18002bba5  mov     [rsp+350h+hMem], r12
0x18002bbaa  sbb     edx, edx
0x18002bbac  neg     edx
0x18002bbae  add     edx, 7EFh
0x18002bbb4  call    SHFormatResMessageArgAlloc
0x18002bbb9  mov     ebx, eax
0x18002bbbb  test    eax, eax
0x18002bbbd  js      loc_18002BD9B
0x18002bbc3  xor     edx, edx; Val
0x18002bbc5  mov     [rsp+350h+pExecInfo.cbSize], 0A0h
0x18002bbcd  mov     r8d, 9Ch; Size
0x18002bbd3  lea     rcx, [rsp+350h+pExecInfo.fMask]; void *
0x18002bbd8  call    memset_0
0x18002bbdd  mov     rax, cs:g_hinst
0x18002bbe4  mov     r13d, 9Fh
0x18002bbea  mov     [rsp+350h+pExecInfo.hwnd+4], rax
0x18002bbef  movzx   eax, word ptr [rdi+14D4h]
0x18002bbf6  neg     ax
0x18002bbf9  mov     qword ptr [rsp+350h+pExecInfo.fMask], r15
0x18002bbfe  mov     rax, [rsp+350h+hMem]
0x18002bc03  sbb     rcx, rcx
0x18002bc06  mov     qword ptr [rbp+250h+pExecInfo+34h], rax
0x18002bc0a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002bc0e  mov     dword ptr [rsp+350h+pExecInfo.lpVerb+4], 8
0x18002bc16  add     rcx, r13
0x18002bc19  mov     dword ptr [rsp+350h+pExecInfo.lpFile], 6
0x18002bc21  mov     dword ptr [rbp+250h+pExecInfo.lpClass], 7
0x18002bc28  lea     rax, ?TaskDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18002bc2f  mov     [rsp+350h+pExecInfo.lpFile+4], rcx
0x18002bc34  mov     [rbp+250h+pExecInfo.lpParameters+4], 0FFFFh
0x18002bc3c  mov     [rbp+250h+var_264], rax
0x18002bc40  test    esi, esi
0x18002bc42  jz      short loc_18002BC53
0x18002bc44  mov     [rbp+250h+var_25C], 1
0x18002bc4c  cmp     [rsp+350h+var_318], r12
0x18002bc51  jz      short loc_18002BC57
0x18002bc53  mov     [rbp+250h+var_25C], r12
0x18002bc57  xor     r9d, r9d; pfVerificationFlagChecked
0x18002bc5a  mov     [rsp+350h+pnButton], r12d
0x18002bc5f  xor     r8d, r8d; pnRadioButton
0x18002bc62  lea     rdx, [rsp+350h+pnButton]; pnButton
0x18002bc67  lea     rcx, [rsp+350h+pExecInfo]; pTaskConfig
0x18002bc6c  call    TaskDialogIndirect
0x18002bc71  cmp     [rsp+350h+pnButton], 6
0x18002bc76  jnz     loc_18002BD31
0x18002bc7c  mov     rcx, [rsp+350h+var_318]
0x18002bc81  test    rcx, rcx
0x18002bc84  jnz     short loc_18002BCDF
0x18002bc86  mov     rcx, rdi; this
0x18002bc89  test    esi, esi
0x18002bc8b  jz      short loc_18002BCAA
0x18002bc8d  mov     edx, esi; int
0x18002bc8f  call    ?_GetUninstallClassContext@CInstalledApp@@AEAAKH@Z; CInstalledApp::_GetUninstallClassContext(int)
0x18002bc94  lea     rcx, [rsp+350h+var_318]
0x18002bc99  mov     edx, eax; unsigned int
0x18002bc9b  mov     [rsp+350h+ppv], rcx; ppv
0x18002bca0  mov     rcx, r15; HWND
0x18002bca3  call    ?CoCreateInstanceAsAdminWithCorrectBitness@@YAJPEAUHWND__@@KAEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdminWithCorrectBitness(HWND__ *,ulong,_GUID const &,_GUID const &,void * *)
0x18002bca8  jmp     short loc_18002BCD4
0x18002bcaa  xor     edx, edx; int
0x18002bcac  call    ?_GetUninstallClassContext@CInstalledApp@@AEAAKH@Z; CInstalledApp::_GetUninstallClassContext(int)
0x18002bcb1  lea     rcx, [rsp+350h+var_318]
0x18002bcb6  mov     r8d, eax; dwClsContext
0x18002bcb9  mov     [rsp+350h+ppv], rcx; ppv
0x18002bcbe  lea     r9, _GUID_f885120e_3789_4fd9_865e_dc9b4a6412d2; riid
0x18002bcc5  lea     rcx, _GUID_fcc74b77_ec3e_4dd8_a80b_008a702075a9; rclsid
0x18002bccc  xor     edx, edx; pUnkOuter
0x18002bcce  call    cs:__imp_CoCreateInstance
0x18002bcd4  mov     ebx, eax
0x18002bcd6  test    eax, eax
0x18002bcd8  js      short loc_18002BD31
0x18002bcda  mov     rcx, [rsp+350h+var_318]
0x18002bcdf  mov     rax, [rcx]
0x18002bce2  lea     r8, [rdi+10C0h]
0x18002bce9  mov     edx, esi
0x18002bceb  mov     rax, [rax+20h]
0x18002bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcf4  mov     ebx, eax
0x18002bcf6  test    eax, eax
0x18002bcf8  jns     short loc_18002BD31
0x18002bcfa  movzx   eax, word ptr [rdi+14D4h]
0x18002bd01  mov     r8d, 7FCh; lpcText
0x18002bd07  mov     rcx, cs:g_hinst; hAppInst
0x18002bd0e  neg     ax
0x18002bd11  mov     [rsp+350h+var_328], r14
0x18002bd16  mov     rdx, r15; hWnd
0x18002bd19  sbb     r9, r9
0x18002bd1c  mov     dword ptr [rsp+350h+ppv], 30h ; '0'; fuStyle
0x18002bd24  and     r9, 0FFFFFFFFFFFFFFFEh
0x18002bd28  add     r9, r13; lpcTitle
0x18002bd2b  call    cs:__imp_ShellMessageBoxW
0x18002bd31  mov     rcx, [rsp+350h+hMem]; hMem
0x18002bd36  call    cs:__imp_LocalFree
0x18002bd3c  jmp     short loc_18002BD9B
0x18002bd3e  test    r13d, r13d
0x18002bd41  jz      short loc_18002BD9B
0x18002bd43  test    r14d, r14d
0x18002bd46  jnz     short loc_18002BD9B
0x18002bd48  cmp     ebx, 800704C7h
0x18002bd4e  jz      short loc_18002BD9B
0x18002bd50  cmp     ebx, 800705B4h
0x18002bd56  jz      short loc_18002BD9B
0x18002bd58  mov     rax, [rdi]
0x18002bd5b  mov     rcx, rdi
0x18002bd5e  mov     rax, [rax+38h]
0x18002bd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd67  test    eax, eax
0x18002bd69  jnz     short loc_18002BD9B
0x18002bd6b  lea     r9, [rsp+350h+ppszParameters]; ppszParameters
0x18002bd70  xor     r8d, r8d; ppszCommandLine
0x18002bd73  lea     rdx, [rsp+350h+ppszApplication]; ppszApplication
0x18002bd78  mov     rcx, r12; pszCmdTemplate
0x18002bd7b  call    cs:__imp_SHEvaluateSystemCommandTemplate
  ... truncated ...
```
