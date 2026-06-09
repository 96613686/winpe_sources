# UserOOBEController::s_PrepareForBootWinREOnReboot(void)

- ea: `0x180028f50`
- end: `0x180029257`
- name: `?s_PrepareForBootWinREOnReboot@UserOOBEController@@CAJXZ`
- size: `775`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x180007114`
- `0x180007134`
- `0x180022fb0`
- `0x180028f50`
- `0x180047e1c`
- `0x1800488e0`
- `0x180048afc`
- `0x180048b30`
- `0x18004afa8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028f69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800290ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002919a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800290ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002919a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002907b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002915b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002907b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002915b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029186`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800290b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029192`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800290b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029192`

## string_xrefs

- `0x180028fb6`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029231`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002917b`: `SetupFinalTasks`
- `0x180028f62`: `ReAgent.dll`
- `0x18002906d`: `System\Setup\Status\ChildCompletion`
- `0x18002914d`: `System\Setup\Status\ChildCompletion`

## pseudocode

```c
__int64 UserOOBEController::s_PrepareForBootWinREOnReboot(void)
{
  HMODULE Library; // rax
  const char *v1; // r9
  HMODULE v2; // rbx
  __int64 v3; // rdx
  FARPROC ProcAddress; // rdi
  FARPROC v5; // rax
  unsigned int (*v6)(void); // rbx
  signed int updated; // ebx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  LSTATUS v11; // ebx
  HKEY v12; // rdx
  HKEY v13; // rcx
  const unsigned __int16 *v14; // r8
  signed int LastError; // eax
  bool v16; // sf
  signed int v17; // eax
  LSTATUS v18; // ebx
  HKEY v19; // rdx
  HKEY v20; // rcx
  const unsigned __int16 *v21; // r8
  signed int v22; // eax
  bool v23; // sf
  signed int v24; // eax
  int v25; // eax
  int v26; // eax
  const unsigned __int16 *v27; // rcx
  int v28; // eax
  int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  DWORD dwDisposition; // [rsp+80h] [rbp+28h] BYREF
  int Data; // [rsp+88h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+38h] BYREF
  HMODULE v35; // [rsp+98h] [rbp+40h] BYREF

  Library = LoadLibraryExW(L"ReAgent.dll", 0, 0);
  v2 = Library;
  v35 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WinReSetRecoveryAction");
    v5 = GetProcAddress(v2, "WinReQueueRecoveryBoot");
    v6 = (unsigned int (*)(void))v5;
    if ( !ProcAddress )
    {
      v3 = 526;
      goto LABEL_5;
    }
    if ( !v5 )
    {
      v3 = 527;
      goto LABEL_5;
    }
    if ( !((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(4, 0, 0) )
    {
      v3 = 528;
      goto LABEL_5;
    }
    if ( !v6() )
    {
      v3 = 529;
      goto LABEL_5;
    }
    v8 = OrchestrateBootCommand();
    updated = v8;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v10 = 530;
      goto LABEL_46;
    }
    Data = 0;
    hKey = 0;
    dwDisposition = 0;
    v11 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\Setup\\Status\\ChildCompletion",
            0,
            (LPWSTR)&Class,
            0,
            0x20006u,
            0,
            &hKey,
            &dwDisposition);
    if ( !v11 )
    {
      v11 = RegSetValueExW(hKey, L"oobeldr.exe", 0, 4u, (const BYTE *)&Data, 4u);
      RegCloseKey(hKey);
    }
    SetLastError(v11);
    if ( v11 )
    {
      LastError = GetLastError();
      v16 = LastError < 0;
      if ( LastError > 0 )
        v16 = 1;
      if ( !v16 )
      {
        updated = -2147467259;
        goto LABEL_44;
      }
      v17 = GetLastError();
      updated = v17;
      if ( v17 > 0 )
        updated = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
      updated = OrchestrateUpdateImageState(v13, v12, v14);
    }
    if ( updated >= 0 )
    {
      Data = 0;
      hKey = 0;
      dwDisposition = 0;
      v18 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\Setup\\Status\\ChildCompletion",
              0,
              (LPWSTR)&Class,
              0,
              0x20006u,
              0,
              &hKey,
              &dwDisposition);
      if ( !v18 )
      {
        v18 = RegSetValueExW(hKey, L"SetupFinalTasks", 0, 4u, (const BYTE *)&Data, 4u);
        RegCloseKey(hKey);
      }
      SetLastError(v18);
      if ( v18 )
      {
        v22 = GetLastError();
        v23 = v22 < 0;
        if ( v22 > 0 )
          v23 = 1;
        if ( !v23 )
        {
          updated = -2147467259;
LABEL_42:
          v10 = 532;
LABEL_45:
          v9 = (unsigned int)updated;
          goto LABEL_46;
        }
        v24 = GetLastError();
        updated = v24;
        if ( v24 > 0 )
          updated = (unsigned __int16)v24 | 0x80070000;
      }
      else
      {
        updated = OrchestrateUpdateImageState(v20, v19, v21);
      }
      if ( updated >= 0 )
      {
        v25 = OrchestratePublishWnfOobeCompletion();
        updated = v25;
        if ( v25 >= 0 )
        {
          v26 = OrchestratePublishWnfOobeUserLogonCompletion();
          updated = v26;
          if ( v26 >= 0 )
          {
            v28 = OrchestrateResetPantherState(v27);
            updated = v28;
            if ( v28 >= 0 )
            {
              updated = 0;
              goto LABEL_47;
            }
            v9 = (unsigned int)v28;
            v10 = 535;
          }
          else
          {
            v9 = (unsigned int)v26;
            v10 = 534;
          }
        }
        else
        {
          v9 = (unsigned int)v25;
          v10 = 533;
        }
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
          (const char *)v9,
          dwOptions);
        goto LABEL_47;
      }
      goto LABEL_42;
    }
LABEL_44:
    v10 = 531;
    goto LABEL_45;
  }
  v3 = 523;
LABEL_5:
  updated = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)v3,
              (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
              v1);
LABEL_47:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v35);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180028f50  push    rbp
0x180028f52  push    rbx
0x180028f53  push    rdi
0x180028f54  push    r14
0x180028f56  mov     rbp, rsp
0x180028f59  sub     rsp, 58h
0x180028f5d  xor     r8d, r8d; dwFlags
0x180028f60  xor     edx, edx; hFile
0x180028f62  lea     rcx, LibFileName; "ReAgent.dll"
0x180028f69  call    cs:__imp_LoadLibraryExW
0x180028f6f  mov     rbx, rax
0x180028f72  mov     [rbp+arg_18], rax
0x180028f76  test    rax, rax
0x180028f79  jnz     short loc_180028F82
0x180028f7b  mov     edx, 20Bh
0x180028f80  jmp     short loc_180028FB2
0x180028f82  lea     rdx, aWinresetrecove; "WinReSetRecoveryAction"
0x180028f89  mov     rcx, rbx; hModule
0x180028f8c  call    cs:__imp_GetProcAddress
0x180028f92  mov     rdi, rax
0x180028f95  lea     rdx, aWinrequeuereco; "WinReQueueRecoveryBoot"
0x180028f9c  mov     rcx, rbx; hModule
0x180028f9f  call    cs:__imp_GetProcAddress
0x180028fa5  mov     rbx, rax
0x180028fa8  test    rdi, rdi
0x180028fab  jnz     short loc_180028FC9
0x180028fad  mov     edx, 20Eh; void *
0x180028fb2  mov     rcx, [rbp+20h]; this
0x180028fb6  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028fbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028fc2  mov     ebx, eax
0x180028fc4  jmp     loc_180029242
0x180028fc9  test    rbx, rbx
0x180028fcc  jnz     short loc_180028FD5
0x180028fce  mov     edx, 20Fh
0x180028fd3  jmp     short loc_180028FB2
0x180028fd5  xor     r9d, r9d
0x180028fd8  xor     r8d, r8d
0x180028fdb  xor     edx, edx
0x180028fdd  lea     r14d, [r9+4]
0x180028fe1  mov     ecx, r14d
0x180028fe4  mov     rax, rdi
0x180028fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fec  test    eax, eax
0x180028fee  jnz     short loc_180028FF7
0x180028ff0  mov     edx, 210h
0x180028ff5  jmp     short loc_180028FB2
0x180028ff7  mov     rax, rbx
0x180028ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fff  test    eax, eax
0x180029001  jnz     short loc_18002900A
0x180029003  mov     edx, 211h
0x180029008  jmp     short loc_180028FB2
0x18002900a  call    OrchestrateBootCommand
0x18002900f  mov     ebx, eax
0x180029011  test    eax, eax
0x180029013  jns     short loc_180029022
0x180029015  mov     r9d, eax
0x180029018  mov     edx, 212h
0x18002901d  jmp     loc_180029231
0x180029022  mov     [rbp+Data], 0
0x180029029  mov     [rbp+hKey], 0
0x180029031  mov     [rbp+dwDisposition], 0
0x180029038  lea     rax, [rbp+dwDisposition]
0x18002903c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180029041  lea     rax, [rbp+hKey]
0x180029045  mov     [rsp+58h+phkResult], rax; phkResult
0x18002904a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029053  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18002905b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180029063  lea     r9, Class; lpClass
0x18002906a  xor     r8d, r8d; Reserved
0x18002906d  lea     rdx, aSystemSetupSta_1; "System\\Setup\\Status\\ChildCompletion"
0x180029074  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002907b  call    cs:__imp_RegCreateKeyExW
0x180029081  mov     ebx, eax
0x180029083  test    eax, eax
0x180029085  jnz     short loc_1800290B8
0x180029087  mov     [rsp+58h+samDesired], r14d; cbData
0x18002908c  lea     rax, [rbp+Data]
0x180029090  mov     qword ptr [rsp+58h+dwOptions], rax; int
0x180029095  mov     r9d, r14d; dwType
0x180029098  xor     r8d, r8d; Reserved
0x18002909b  lea     rdx, aOobeldrExe; "oobeldr.exe"
0x1800290a2  mov     rcx, [rbp+hKey]; hKey
0x1800290a6  call    cs:__imp_RegSetValueExW
0x1800290ac  mov     ebx, eax
0x1800290ae  mov     rcx, [rbp+hKey]; hKey
0x1800290b2  call    cs:__imp_RegCloseKey
0x1800290b8  mov     ecx, ebx; dwErrCode
0x1800290ba  call    cs:__imp_SetLastError
0x1800290c0  mov     edi, 80070000h
0x1800290c5  test    ebx, ebx
0x1800290c7  jnz     short loc_1800290D2
0x1800290c9  call    ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x1800290ce  mov     ebx, eax
0x1800290d0  jmp     short loc_1800290FA
0x1800290d2  call    cs:__imp_GetLastError
0x1800290d8  test    eax, eax
0x1800290da  jle     short loc_1800290E3
0x1800290dc  movzx   eax, ax
0x1800290df  or      eax, edi
0x1800290e1  test    eax, eax
0x1800290e3  jns     loc_180029224
0x1800290e9  call    cs:__imp_GetLastError
0x1800290ef  mov     ebx, eax
0x1800290f1  test    eax, eax
0x1800290f3  jle     short loc_1800290FA
0x1800290f5  movzx   ebx, ax
0x1800290f8  or      ebx, edi
0x1800290fa  test    ebx, ebx
0x1800290fc  js      loc_180029229
0x180029102  mov     [rbp+Data], 0
0x180029109  mov     [rbp+hKey], 0
0x180029111  mov     [rbp+dwDisposition], 0
0x180029118  lea     rax, [rbp+dwDisposition]
0x18002911c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180029121  lea     rax, [rbp+hKey]
0x180029125  mov     [rsp+58h+phkResult], rax; phkResult
0x18002912a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029133  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18002913b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180029143  lea     r9, Class; lpClass
0x18002914a  xor     r8d, r8d; Reserved
0x18002914d  lea     rdx, aSystemSetupSta_1; "System\\Setup\\Status\\ChildCompletion"
0x180029154  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002915b  call    cs:__imp_RegCreateKeyExW
0x180029161  mov     ebx, eax
0x180029163  test    eax, eax
0x180029165  jnz     short loc_180029198
0x180029167  mov     [rsp+58h+samDesired], r14d; cbData
0x18002916c  lea     rax, [rbp+Data]
0x180029170  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180029175  mov     r9d, r14d; dwType
0x180029178  xor     r8d, r8d; Reserved
0x18002917b  lea     rdx, aSetupfinaltask; "SetupFinalTasks"
0x180029182  mov     rcx, [rbp+hKey]; hKey
0x180029186  call    cs:__imp_RegSetValueExW
0x18002918c  mov     ebx, eax
0x18002918e  mov     rcx, [rbp+hKey]; hKey
0x180029192  call    cs:__imp_RegCloseKey
0x180029198  mov     ecx, ebx; dwErrCode
0x18002919a  call    cs:__imp_SetLastError
0x1800291a0  test    ebx, ebx
0x1800291a2  jnz     short loc_1800291AD
0x1800291a4  call    ?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z; OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)
0x1800291a9  mov     ebx, eax
0x1800291ab  jmp     short loc_1800291D1
0x1800291ad  call    cs:__imp_GetLastError
0x1800291b3  test    eax, eax
0x1800291b5  jle     short loc_1800291BE
0x1800291b7  movzx   eax, ax
0x1800291ba  or      eax, edi
0x1800291bc  test    eax, eax
0x1800291be  jns     short loc_180029218
0x1800291c0  call    cs:__imp_GetLastError
0x1800291c6  mov     ebx, eax
0x1800291c8  test    eax, eax
0x1800291ca  jle     short loc_1800291D1
0x1800291cc  movzx   ebx, ax
0x1800291cf  or      ebx, edi
0x1800291d1  test    ebx, ebx
0x1800291d3  js      short loc_18002921D
0x1800291d5  call    OrchestratePublishWnfOobeCompletion
0x1800291da  mov     ebx, eax
0x1800291dc  test    eax, eax
0x1800291de  jns     short loc_1800291EA
0x1800291e0  mov     r9d, eax
0x1800291e3  mov     edx, 215h
0x1800291e8  jmp     short loc_180029231
0x1800291ea  call    OrchestratePublishWnfOobeUserLogonCompletion
0x1800291ef  mov     ebx, eax
0x1800291f1  test    eax, eax
0x1800291f3  jns     short loc_1800291FF
0x1800291f5  mov     r9d, eax
0x1800291f8  mov     edx, 216h
0x1800291fd  jmp     short loc_180029231
0x1800291ff  call    ?OrchestrateResetPantherState@@YAJPEBG@Z; OrchestrateResetPantherState(ushort const *)
0x180029204  mov     ebx, eax
0x180029206  test    eax, eax
0x180029208  jns     short loc_180029214
0x18002920a  mov     r9d, eax
0x18002920d  mov     edx, 217h
0x180029212  jmp     short loc_180029231
0x180029214  xor     ebx, ebx
0x180029216  jmp     short loc_180029242
0x180029218  mov     ebx, 80004005h
0x18002921d  mov     edx, 214h
0x180029222  jmp     short loc_18002922E
0x180029224  mov     ebx, 80004005h
0x180029229  mov     edx, 213h; void *
0x18002922e  mov     r9d, ebx; char *
0x180029231  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029238  mov     rcx, [rbp+20h]; this
0x18002923c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029241  nop
0x180029242  lea     rcx, [rbp+arg_18]
0x180029246  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002924b  mov     eax, ebx
0x18002924d  add     rsp, 58h
0x180029251  pop     r14
0x180029253  pop     rdi
0x180029254  pop     rbx
0x180029255  pop     rbp
0x180029256  retn
```
