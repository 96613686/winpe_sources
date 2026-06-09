# SystemSettings::WorkAccess::ExecuteAdminComObject(HWND__ *,ushort const *,_GUID const &,_GUID const &,void * *)

- ea: `0x18003c804`
- end: `0x18003ca7c`
- name: `?ExecuteAdminComObject@WorkAccess@SystemSettings@@YAJPEAUHWND__@@PEBGAEBU_GUID@@2PEAPEAX@Z`
- size: `632`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess *this, IRunningObjectTable *, const unsigned __int16 *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bbf8`

## callees

- `0x180003534`
- `0x1800076ac`
- `0x1800096cc`
- `0x18002ecf8`
- `0x18003c804`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c867`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c867`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c841`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c841`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ca11`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ca11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9a9`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18003c995`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18003c995`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18003c8b6`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18003c8b6`

## string_xrefs

- `0x18003c970`: `%systemroot%\system32\SystemSettingsAdminFlows.exe`
- `0x18003c880`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003c83a`: `ole32.dll`
- `0x18003c85d`: `CreateClassMoniker`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::ExecuteAdminComObject(
        SystemSettings::WorkAccess *this,
        IRunningObjectTable *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        const struct _GUID *a5)
{
  const struct _GUID *v6; // r14
  HMODULE Library; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  FARPROC ProcAddress; // rdi
  int RunningObjectTable; // ebx
  LPRUNNINGOBJECTTABLE v12; // rdi
  HRESULT (__stdcall *GetObjectA)(IRunningObjectTable *, IMoniker *, IUnknown **); // rbx
  signed int LastError; // eax
  int i; // esi
  LPRUNNINGOBJECTTABLE v16; // rdi
  HRESULT (__stdcall *v17)(IRunningObjectTable *, IMoniker *, IUnknown **); // rbx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+28h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+57h]
  LPRUNNINGOBJECTTABLE pprot; // [rsp+D0h] [rbp+67h] BYREF
  const unsigned __int16 *v22; // [rsp+D8h] [rbp+6Fh] BYREF
  const struct _GUID *v23; // [rsp+E0h] [rbp+77h] BYREF

  v23 = a4;
  v22 = a3;
  pprot = a2;
  v6 = a5;
  *(_QWORD *)&a5->Data1 = 0;
  Library = LoadLibraryExW(L"ole32.dll", 0, 0x800u);
  a5 = (const struct _GUID *)Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CreateClassMoniker");
    if ( !ProcAddress )
    {
      v9 = 632;
      goto LABEL_5;
    }
    pprot = 0;
    v22 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pprot);
    RunningObjectTable = GetRunningObjectTable(0, &pprot);
    if ( RunningObjectTable >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      RunningObjectTable = ((__int64 (__fastcall *)(GUID *, const unsigned __int16 **))ProcAddress)(
                             &GUID_e0ba3bf5_25ef_459f_9ee0_855fd3666692,
                             &v22);
      if ( RunningObjectTable >= 0 )
      {
        v23 = 0;
        v12 = pprot;
        GetObjectA = pprot->lpVtbl->GetObjectA;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, const unsigned __int16 *, const struct _GUID **))GetObjectA)(
                               v12,
                               v22,
                               &v23);
        if ( RunningObjectTable >= 0 )
          RunningObjectTable = (**(__int64 (__fastcall ***)(const struct _GUID *, GUID *, const struct _GUID *))&v23->Data1)(
                                 v23,
                                 &GUID_6c69a927_921c_4d37_a8cb_9f1d8dbdbab2,
                                 v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      }
    }
    if ( RunningObjectTable == -2147221021 )
    {
      pExecInfo.cbSize = 112;
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.lpVerb = L"runas";
      pExecInfo.lpFile = L"%systemroot%\\system32\\SystemSettingsAdminFlows.exe";
      pExecInfo.fMask = 768;
      pExecInfo.lpParameters = L"CorpDeviceAdminHelper";
      pExecInfo.hwnd = (HWND)this;
      if ( ShellExecuteExW(&pExecInfo) )
      {
        RunningObjectTable = 0;
        goto LABEL_17;
      }
      LastError = GetLastError();
      RunningObjectTable = LastError;
      if ( LastError > 0 )
        RunningObjectTable = (unsigned __int16)LastError | 0x80070000;
      if ( RunningObjectTable >= 0 )
      {
LABEL_17:
        for ( i = 12000; i; --i )
        {
          v23 = 0;
          v16 = pprot;
          v17 = pprot->lpVtbl->GetObjectA;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, const unsigned __int16 *, const struct _GUID **))v17)(
                                 v16,
                                 v22,
                                 &v23);
          if ( RunningObjectTable >= 0 )
          {
            RunningObjectTable = (**(__int64 (__fastcall ***)(const struct _GUID *, GUID *, const struct _GUID *))&v23->Data1)(
                                   v23,
                                   &GUID_6c69a927_921c_4d37_a8cb_9f1d8dbdbab2,
                                   v6);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
            break;
          }
          Sleep(0xAu);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pprot);
    goto LABEL_23;
  }
  v9 = 630;
LABEL_5:
  RunningObjectTable = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)v9,
                         (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
                         v8);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&a5);
  return (unsigned int)RunningObjectTable;
}

```

## disassembly

```asm
0x18003c804  mov     rax, rsp
0x18003c807  mov     [rax+20h], r9
0x18003c80b  mov     [rax+18h], r8
0x18003c80f  mov     [rax+10h], rdx
0x18003c813  push    rbp
0x18003c814  push    rbx
0x18003c815  push    rsi
0x18003c816  push    rdi
0x18003c817  push    r14
0x18003c819  lea     rbp, [rax-57h]
0x18003c81d  sub     rsp, 90h
0x18003c824  mov     rsi, rcx
0x18003c827  mov     r14, [rbp+4Fh+arg_20]
0x18003c82b  mov     qword ptr [r14], 0
0x18003c832  xor     edx, edx; hFile
0x18003c834  mov     r8d, 800h; dwFlags
0x18003c83a  lea     rcx, LibFileName; "ole32.dll"
0x18003c841  call    cs:__imp_LoadLibraryExW
0x18003c848  nop     dword ptr [rax+rax+00h]
0x18003c84d  mov     [rbp+4Fh+arg_20], rax
0x18003c851  test    rax, rax
0x18003c854  jnz     short loc_18003C85D
0x18003c856  mov     edx, 276h
0x18003c85b  jmp     short loc_18003C880
0x18003c85d  lea     rdx, ProcName; "CreateClassMoniker"
0x18003c864  mov     rcx, rax; hModule
0x18003c867  call    cs:__imp_GetProcAddress
0x18003c86e  nop     dword ptr [rax+rax+00h]
0x18003c873  mov     rdi, rax
0x18003c876  test    rax, rax
0x18003c879  jnz     short loc_18003C897
0x18003c87b  mov     edx, 278h; void *
0x18003c880  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003c887  mov     rcx, [rbp+57h]; this
0x18003c88b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c890  mov     ebx, eax
0x18003c892  jmp     loc_18003CA62
0x18003c897  mov     [rbp+4Fh+pprot], 0
0x18003c89f  mov     [rbp+4Fh+arg_10], 0
0x18003c8a7  lea     rcx, [rbp+4Fh+pprot]
0x18003c8ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c8b0  lea     rdx, [rbp+4Fh+pprot]; pprot
0x18003c8b4  xor     ecx, ecx; reserved
0x18003c8b6  call    cs:__imp_GetRunningObjectTable
0x18003c8bd  nop     dword ptr [rax+rax+00h]
0x18003c8c2  mov     ebx, eax
0x18003c8c4  test    eax, eax
0x18003c8c6  js      short loc_18003C943
0x18003c8c8  lea     rcx, [rbp+4Fh+arg_10]
0x18003c8cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c8d1  lea     rdx, [rbp+4Fh+arg_10]
0x18003c8d5  lea     rcx, _GUID_e0ba3bf5_25ef_459f_9ee0_855fd3666692
0x18003c8dc  mov     rax, rdi
0x18003c8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8e4  mov     ebx, eax
0x18003c8e6  test    eax, eax
0x18003c8e8  js      short loc_18003C943
0x18003c8ea  mov     [rbp+4Fh+arg_18], 0
0x18003c8f2  mov     rdi, [rbp+4Fh+pprot]
0x18003c8f6  mov     rax, [rdi]
0x18003c8f9  mov     rbx, [rax+30h]
0x18003c8fd  lea     rcx, [rbp+4Fh+arg_18]
0x18003c901  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c906  lea     r8, [rbp+4Fh+arg_18]
0x18003c90a  mov     rdx, [rbp+4Fh+arg_10]
0x18003c90e  mov     rcx, rdi
0x18003c911  mov     rax, rbx
0x18003c914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c919  mov     ebx, eax
0x18003c91b  test    eax, eax
0x18003c91d  js      short loc_18003C93A
0x18003c91f  mov     rcx, [rbp+4Fh+arg_18]
0x18003c923  mov     rax, [rcx]
0x18003c926  mov     r8, r14
0x18003c929  lea     rdx, _GUID_6c69a927_921c_4d37_a8cb_9f1d8dbdbab2
0x18003c930  mov     rax, [rax]
0x18003c933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c938  mov     ebx, eax
0x18003c93a  lea     rcx, [rbp+4Fh+arg_18]
0x18003c93e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c943  cmp     ebx, 800401E3h
0x18003c949  jnz     loc_18003CA4E
0x18003c94f  mov     [rbp+4Fh+pExecInfo.cbSize], 70h ; 'p'
0x18003c956  xor     edx, edx; Val
0x18003c958  lea     r8d, [rdx+6Ch]; Size
0x18003c95c  lea     rcx, [rbp+4Fh+pExecInfo.fMask]; void *
0x18003c960  call    memset_0
0x18003c965  lea     rax, aRunas; "runas"
0x18003c96c  mov     [rbp+4Fh+pExecInfo.lpVerb], rax
0x18003c970  lea     rax, aSystemrootSyst; "%systemroot%\\system32\\SystemSettingsA"...
0x18003c977  mov     [rbp+4Fh+pExecInfo.lpFile], rax
0x18003c97b  mov     [rbp+4Fh+pExecInfo.fMask], 300h
0x18003c982  lea     rax, aCorpdeviceadmi_0; "CorpDeviceAdminHelper"
0x18003c989  mov     [rbp+4Fh+pExecInfo.lpParameters], rax
0x18003c98d  mov     [rbp+4Fh+pExecInfo.hwnd], rsi
0x18003c991  lea     rcx, [rbp+4Fh+pExecInfo]; pExecInfo
0x18003c995  call    cs:__imp_ShellExecuteExW
0x18003c99c  nop     dword ptr [rax+rax+00h]
0x18003c9a1  test    eax, eax
0x18003c9a3  jz      short loc_18003C9A9
0x18003c9a5  xor     ebx, ebx
0x18003c9a7  jmp     short loc_18003C9CC
0x18003c9a9  call    cs:__imp_GetLastError
0x18003c9b0  nop     dword ptr [rax+rax+00h]
0x18003c9b5  mov     ebx, eax
0x18003c9b7  test    eax, eax
0x18003c9b9  jle     short loc_18003C9C4
0x18003c9bb  movzx   ebx, ax
0x18003c9be  or      ebx, 80070000h
0x18003c9c4  test    ebx, ebx
0x18003c9c6  js      loc_18003CA4E
0x18003c9cc  mov     esi, 2EE0h
0x18003c9d1  test    esi, esi
0x18003c9d3  jz      short loc_18003CA4E
0x18003c9d5  mov     [rbp+4Fh+arg_18], 0
0x18003c9dd  mov     rdi, [rbp+4Fh+pprot]
0x18003c9e1  mov     rax, [rdi]
0x18003c9e4  mov     rbx, [rax+30h]
0x18003c9e8  lea     rcx, [rbp+4Fh+arg_18]
0x18003c9ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c9f1  lea     r8, [rbp+4Fh+arg_18]
0x18003c9f5  mov     rdx, [rbp+4Fh+arg_10]
0x18003c9f9  mov     rcx, rdi
0x18003c9fc  mov     rax, rbx
0x18003c9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca04  mov     ebx, eax
0x18003ca06  test    eax, eax
0x18003ca08  jns     short loc_18003CA29
0x18003ca0a  dec     esi
0x18003ca0c  mov     ecx, 0Ah; dwMilliseconds
0x18003ca11  call    cs:__imp_Sleep
0x18003ca18  nop     dword ptr [rax+rax+00h]
0x18003ca1d  nop
0x18003ca1e  lea     rcx, [rbp+4Fh+arg_18]
0x18003ca22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca27  jmp     short loc_18003C9D1
0x18003ca29  mov     rcx, [rbp+4Fh+arg_18]
0x18003ca2d  mov     rax, [rcx]
0x18003ca30  mov     r8, r14
0x18003ca33  lea     rdx, _GUID_6c69a927_921c_4d37_a8cb_9f1d8dbdbab2
0x18003ca3a  mov     rax, [rax]
0x18003ca3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca42  mov     ebx, eax
0x18003ca44  lea     rcx, [rbp+4Fh+arg_18]
0x18003ca48  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca4d  nop
0x18003ca4e  lea     rcx, [rbp+4Fh+arg_10]
0x18003ca52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca57  nop
0x18003ca58  lea     rcx, [rbp+4Fh+pprot]
0x18003ca5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca61  nop
0x18003ca62  lea     rcx, [rbp+4Fh+arg_20]
0x18003ca66  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003ca6b  mov     eax, ebx
0x18003ca6d  add     rsp, 90h
0x18003ca74  pop     r14
0x18003ca76  pop     rdi
0x18003ca77  pop     rsi
0x18003ca78  pop     rbx
0x18003ca79  pop     rbp
0x18003ca7a  retn
```
