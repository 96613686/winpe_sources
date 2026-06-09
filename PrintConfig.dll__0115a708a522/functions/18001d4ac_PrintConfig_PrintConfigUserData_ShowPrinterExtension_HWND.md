# PrintConfig::PrintConfigUserData::ShowPrinterExtension(HWND__ *)

- ea: `0x18001d4ac`
- end: `0x18001db1d`
- name: `?ShowPrinterExtension@PrintConfigUserData@PrintConfig@@QEAAJPEAUHWND__@@@Z`
- size: `1649`
- prototype: `__int64 __fastcall(PrintConfig::PrintConfigUserData *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001ac24`
- `0x18001d1b0`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000f830`
- `0x18001535c`
- `0x1800197b4`
- `0x18001a144`
- `0x18001d428`
- `0x18001d4ac`
- `0x18001dc10`
- `0x1800ea130`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001d532`
- `KERNEL32!GetProcAddress` at `0x18001d532`
- `KERNEL32!FreeLibrary` at `0x18001d5b4`
- `KERNEL32!FreeLibrary` at `0x18001d5b4`
- `KERNEL32!CloseHandle` at `0x18001d916`
- `KERNEL32!CloseHandle` at `0x18001da62`
- `KERNEL32!CloseHandle` at `0x18001d916`
- `KERNEL32!CloseHandle` at `0x18001da62`
- `KERNEL32!GetLastError` at `0x18001daa9`
- `KERNEL32!GetLastError` at `0x18001daa9`
- `KERNEL32!CreateEventW` at `0x18001d8f0`
- `KERNEL32!CreateEventW` at `0x18001d8f0`
- `KERNEL32!QueueUserWorkItem` at `0x18001d93f`
- `KERNEL32!QueueUserWorkItem` at `0x18001d93f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001d596`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001d596`
- `USER32!PeekMessageW` at `0x18001d9ae`
- `USER32!PeekMessageW` at `0x18001d9ae`
- `USER32!TranslateMessage` at `0x18001d980`
- `USER32!TranslateMessage` at `0x18001d980`
- `USER32!IsGUIThread` at `0x18001d75f`
- `USER32!IsGUIThread` at `0x18001d75f`
- `USER32!GetActiveWindow` at `0x18001d71d`
- `USER32!GetActiveWindow` at `0x18001d71d`
- `USER32!GetFocus` at `0x18001d736`
- `USER32!GetFocus` at `0x18001d736`
- `USER32!EnableWindow` at `0x18001d750`
- `USER32!EnableWindow` at `0x18001d750`
- `USER32!GetAncestor` at `0x18001d5ce`
- `USER32!GetAncestor` at `0x18001d5ce`
- `USER32!DispatchMessageW` at `0x18001d991`
- `USER32!DispatchMessageW` at `0x18001d991`
- `USER32!MsgWaitForMultipleObjects` at `0x18001d9cf`
- `USER32!MsgWaitForMultipleObjects` at `0x18001d9cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrintConfig::PrintConfigUserData::ShowPrinterExtension(
        PrintConfig::PrintConfigUserData *this,
        HWND a2)
{
  int v3; // eax
  HMODULE v4; // rdi
  int v5; // esi
  FARPROC ProcAddress; // rax
  _BYTE *v7; // rax
  _BYTE *v8; // rcx
  _BYTE *v9; // rdx
  _QWORD *v10; // rdx
  int v11; // esi
  HWND ActiveWindow; // rdi
  _BYTE *v13; // rdx
  _BYTE *v14; // rdx
  _BYTE *v15; // rdx
  HANDLE EventW; // rdi
  unsigned __int16 *const *v17; // rdi
  _DWORD *v18; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v19; // rcx
  unsigned int v20; // edi
  _BYTE *v21; // rdx
  signed int LastError; // eax
  unsigned int v24; // edi
  int v25; // [rsp+30h] [rbp-258h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-250h] BYREF
  HWND hwnd; // [rsp+40h] [rbp-248h] BYREF
  int v28; // [rsp+48h] [rbp-240h] BYREF
  void **v29; // [rsp+50h] [rbp-238h]
  HMODULE v30; // [rsp+58h] [rbp-230h] BYREF
  bool v31[8]; // [rsp+60h] [rbp-228h] BYREF
  HWND v32; // [rsp+68h] [rbp-220h]
  HWND Focus; // [rsp+70h] [rbp-218h]
  MSG Msg; // [rsp+78h] [rbp-210h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-1E0h]
  const PrintCore::WindowsError *v36; // [rsp+B0h] [rbp-1D8h] BYREF
  const hr_error *v37; // [rsp+B8h] [rbp-1D0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+C0h] [rbp-1C8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+E0h] [rbp-1A8h] BYREF
  char v40[56]; // [rsp+E8h] [rbp-1A0h] BYREF
  int v41; // [rsp+120h] [rbp-168h]
  HANDLE hObject; // [rsp+150h] [rbp-138h] BYREF
  _BYTE v43[56]; // [rsp+158h] [rbp-130h] BYREF
  _BYTE *v44; // [rsp+190h] [rbp-F8h]
  _BYTE v45[56]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE *v46; // [rsp+1D8h] [rbp-B0h]
  _QWORD v47[7]; // [rsp+1E0h] [rbp-A8h] BYREF
  _QWORD *v48; // [rsp+218h] [rbp-70h]
  _BYTE v49[56]; // [rsp+220h] [rbp-68h] BYREF
  _BYTE *v50; // [rsp+258h] [rbp-30h]

  v35 = -2;
  hwnd = a2;
  v25 = -2147467259;
  v29 = &ModuleRAII::`vftable';
  v3 = LoadLibraryFromSystemDirectory(L"winspool.drv", &v30);
  v4 = v30;
  if ( v3 < 0 )
    v4 = 0;
  v30 = v4;
  if ( v4 )
  {
    v5 = 0;
    ProcAddress = GetProcAddress(v4, "GetPrintExecutionData");
    if ( ProcAddress )
    {
      pHandles = 0;
      if ( ((unsigned int (__fastcall *)(HANDLE *))ProcAddress)(&pHandles) && (_DWORD)pHandles == 4 )
        v5 = HIDWORD(pHandles);
    }
    else
    {
      memset_0(v40, 0, 0x68u);
      RpcCallAttributes[0] = 2;
      RpcCallAttributes[1] = 16;
      if ( !RpcServerInqCallAttributesW(0, RpcCallAttributes) )
        v5 = v41;
    }
    FreeLibrary(v4);
  }
  else
  {
    v5 = 0;
  }
  v28 = v5;
  hwnd = GetAncestor(hwnd, 2u);
  v47[0] = &std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::`vftable';
  v47[1] = &v25;
  v47[2] = this;
  v47[3] = &hwnd;
  v47[4] = &v28;
  v48 = v47;
  hObject = 0;
  v44 = 0;
  v46 = 0;
  v7 = (_BYTE *)std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::_Move(
                  (__int64)v47,
                  (__int64)v45);
  try
  {
    v8 = v7;
    v46 = v7;
    if ( v7 != v45 && v44 != v43 )
    {
      v46 = v44;
      goto LABEL_16;
    }
    v50 = 0;
    if ( v7 )
    {
      if ( v7 == v45 )
      {
        v50 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v7 + 8LL))(v7, v49);
        if ( !v46 )
          goto LABEL_34;
        v13 = v45;
        LOBYTE(v13) = v46 != v45;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v46 + 32LL))(v46, v13);
      }
      else
      {
        v50 = v7;
      }
      v46 = 0;
    }
LABEL_34:
    if ( v44 )
    {
      if ( v44 != v43 )
      {
        v46 = v44;
        goto LABEL_39;
      }
      v46 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v44 + 8LL))(v44, v45);
      if ( v44 )
      {
        v14 = v43;
        LOBYTE(v14) = v44 != v43;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v44 + 32LL))(v44, v14);
LABEL_39:
        v44 = 0;
      }
    }
    v8 = v50;
    if ( !v50 )
      goto LABEL_17;
    if ( v50 == v49 )
    {
      v44 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v50 + 8LL))(v50, v43);
      if ( v50 )
      {
        v15 = v49;
        LOBYTE(v15) = v50 != v49;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v50 + 32LL))(v50, v15);
      }
      goto LABEL_17;
    }
LABEL_16:
    v44 = v8;
LABEL_17:
    if ( v46 )
    {
      v9 = v45;
      LOBYTE(v9) = v46 != v45;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v46 + 32LL))(v46, v9);
    }
    if ( v48 )
    {
      v10 = v47;
      LOBYTE(v10) = v48 != v47;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v48 + 32LL))(v48, v10);
    }
    v29 = (void **)((char *)this + 24);
    v11 = *(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 0x40000000;
    v31[0] = v11 == 0;
    ActiveWindow = hwnd;
    v32 = hwnd;
    Focus = 0;
    if ( hwnd || (ActiveWindow = GetActiveWindow(), (v32 = ActiveWindow) != 0) )
    {
      Focus = GetFocus();
      if ( !v11 )
        EnableWindow(ActiveWindow, 0);
    }
    if ( IsGUIThread(0) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      pHandles = EventW;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      hObject = EventW;
      if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)PrintConfig::UserWorkItem::ThreadProc, &hObject, 0x110u) )
      {
        LastError = GetLastError();
        v24 = LastError;
        if ( LastError > 0 )
          v24 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0xAu,
            (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
            v24);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v24);
        throw (hr_error *)pExceptionObject;
      }
      memset(&Msg, 0, sizeof(Msg));
      while ( MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1C7Fu) == 1 )
      {
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
    }
    else
    {
      if ( !v44 )
        std::_Xbad_function_call();
      (*(void (**)(void))(*(_QWORD *)v44 + 16LL))();
    }
    PrintConfig::OutOfProcessDialogStateScope::~OutOfProcessDialogStateScope((PrintConfig::OutOfProcessDialogStateScope *)v31);
  }
  catch ( std::bad_alloc )
  {
    v25 = -2147024882;
  }
  catch ( const hr_error *v37 )
  {
    v25 = *((_DWORD *)v37 + 6);
  }
  catch ( const PrintCore::WindowsError *v36 )
  {
    v25 = *((_DWORD *)v36 + 6);
  }
  catch ( std::exception )
  {
    v25 = -2147467259;
  }
  catch ( ... )
  {
    v25 = -2147418113;
  }
  v17 = (unsigned __int16 *const *)*v29;
  v18 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
  if ( v18 && *v18 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
    Print::Driver::Telemetry::PrintConfigTelemetry::PrinterExtensionPrintPreferencesAttempt_(v19, v17[2], v25);
  }
  v20 = v25;
  if ( v44 )
  {
    v21 = v43;
    LOBYTE(v21) = v44 != v43;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v44 + 32LL))(v44, v21);
    v44 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v20;
}

```

## disassembly

```asm
0x18001d4ac  mov     rax, rsp
0x18001d4af  push    rsi
0x18001d4b0  push    rdi
0x18001d4b1  push    r14
0x18001d4b3  sub     rsp, 270h
0x18001d4ba  mov     qword ptr [rax-1E0h], 0FFFFFFFFFFFFFFFEh
0x18001d4c5  mov     [rax+18h], rbx
0x18001d4c9  mov     rax, cs:__security_cookie
0x18001d4d0  xor     rax, rsp
0x18001d4d3  mov     [rsp+288h+var_28], rax
0x18001d4db  mov     r14, rcx
0x18001d4de  mov     [rsp+288h+hwnd], rdx
0x18001d4e3  mov     [rsp+288h+var_258], 80004005h
0x18001d4eb  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x18001d4f2  mov     [rsp+288h+var_238], rax
0x18001d4f7  lea     rdx, [rsp+288h+var_230]
0x18001d4fc  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18001d503  call    LoadLibraryFromSystemDirectory
0x18001d508  mov     rdi, [rsp+288h+var_230]
0x18001d50d  xor     ebx, ebx
0x18001d50f  test    eax, eax
0x18001d511  cmovs   rdi, rbx
0x18001d515  mov     [rsp+288h+var_230], rdi
0x18001d51a  test    rdi, rdi
0x18001d51d  jnz     short loc_18001D526
0x18001d51f  mov     esi, ebx
0x18001d521  jmp     loc_18001D5C0
0x18001d526  mov     esi, ebx
0x18001d528  lea     rdx, aGetprintexecut; "GetPrintExecutionData"
0x18001d52f  mov     rcx, rdi; hModule
0x18001d532  call    cs:__imp_GetProcAddress
0x18001d539  nop     dword ptr [rax+rax+00h]
0x18001d53e  test    rax, rax
0x18001d541  jz      short loc_18001D563
0x18001d543  mov     [rsp+288h+pHandles], rbx
0x18001d548  lea     rcx, [rsp+288h+pHandles]
0x18001d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d552  test    eax, eax
0x18001d554  jz      short loc_18001D5AC
0x18001d556  cmp     dword ptr [rsp+288h+pHandles], 4
0x18001d55b  jnz     short loc_18001D5AC
0x18001d55d  mov     esi, dword ptr [rsp+288h+pHandles+4]
0x18001d561  jmp     short loc_18001D5AC
0x18001d563  xor     edx, edx; Val
0x18001d565  lea     r8d, [rdx+68h]; Size
0x18001d569  lea     rcx, [rsp+288h+var_1A0]; void *
0x18001d571  call    memset_0
0x18001d576  mov     [rsp+288h+RpcCallAttributes], 2
0x18001d581  mov     [rsp+288h+var_1A4], 10h
0x18001d58c  lea     rdx, [rsp+288h+RpcCallAttributes]; RpcCallAttributes
0x18001d594  xor     ecx, ecx; ClientBinding
0x18001d596  call    cs:__imp_RpcServerInqCallAttributesW
0x18001d59d  nop     dword ptr [rax+rax+00h]
0x18001d5a2  test    eax, eax
0x18001d5a4  cmovz   esi, [rsp+288h+var_168]
0x18001d5ac  test    rdi, rdi
0x18001d5af  jz      short loc_18001D5C0
0x18001d5b1  mov     rcx, rdi; hLibModule
0x18001d5b4  call    cs:__imp_FreeLibrary
0x18001d5bb  nop     dword ptr [rax+rax+00h]
0x18001d5c0  mov     [rsp+288h+var_240], esi
0x18001d5c4  mov     edx, 2; gaFlags
0x18001d5c9  mov     rcx, [rsp+288h+hwnd]; hwnd
0x18001d5ce  call    cs:__imp_GetAncestor
0x18001d5d5  nop     dword ptr [rax+rax+00h]
0x18001d5da  mov     [rsp+288h+hwnd], rax
0x18001d5df  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d422c950f2f909e47ca6180ffad9d988_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::`vftable'
0x18001d5e6  mov     [rsp+288h+var_A8], rax
0x18001d5ee  lea     rax, [rsp+288h+var_258]
0x18001d5f3  mov     [rsp+288h+var_A0], rax
0x18001d5fb  mov     [rsp+288h+var_98], r14
0x18001d603  lea     rax, [rsp+288h+hwnd]
0x18001d608  mov     [rsp+288h+var_90], rax
0x18001d610  lea     rax, [rsp+288h+var_240]
0x18001d615  mov     [rsp+288h+var_88], rax
0x18001d61d  lea     rax, [rsp+288h+var_A8]
0x18001d625  mov     [rsp+288h+var_70], rax
0x18001d62d  mov     [rsp+288h+hObject], rbx
0x18001d635  mov     [rsp+288h+var_F8], rbx
0x18001d63d  mov     [rsp+288h+var_B0], rbx
0x18001d645  lea     rdx, [rsp+288h+var_E8]
0x18001d64d  lea     rcx, [rsp+288h+var_A8]
0x18001d655  call    ?_Move@?$_Func_impl_no_alloc@V_lambda_d422c950f2f909e47ca6180ffad9d988_@@X$$V@std@@EEAAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::_Move(void *)
0x18001d65a  mov     rcx, rax
0x18001d65d  mov     [rsp+288h+var_B0], rax
0x18001d665  lea     rax, [rsp+288h+var_E8]
0x18001d66d  cmp     rcx, rax
0x18001d670  jz      loc_18001D789
0x18001d676  mov     rax, [rsp+288h+var_F8]
0x18001d67e  lea     rdx, [rsp+288h+var_130]
0x18001d686  cmp     rax, rdx
0x18001d689  jz      loc_18001D789
0x18001d68f  mov     [rsp+288h+var_B0], rax
0x18001d697  mov     [rsp+288h+var_F8], rcx
0x18001d69f  mov     rcx, [rsp+288h+var_B0]
0x18001d6a7  test    rcx, rcx
0x18001d6aa  jz      short loc_18001D6C7
0x18001d6ac  mov     rax, [rcx]
0x18001d6af  lea     rdx, [rsp+288h+var_E8]
0x18001d6b7  cmp     rcx, rdx
0x18001d6ba  setnz   dl
0x18001d6bd  mov     rax, [rax+20h]
0x18001d6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c6  nop
0x18001d6c7  mov     rcx, [rsp+288h+var_70]
0x18001d6cf  test    rcx, rcx
0x18001d6d2  jz      short loc_18001D6EF
0x18001d6d4  mov     rax, [rcx]
0x18001d6d7  lea     rdx, [rsp+288h+var_A8]
0x18001d6df  cmp     rcx, rdx
0x18001d6e2  setnz   dl
0x18001d6e5  mov     rax, [rax+20h]
0x18001d6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6ee  nop
0x18001d6ef  lea     rax, [r14+18h]
0x18001d6f3  mov     [rsp+288h+var_238], rax
0x18001d6f8  mov     rax, [rax]
0x18001d6fb  mov     esi, [rax+2Ch]
0x18001d6fe  and     esi, 40000000h
0x18001d704  setz    [rsp+288h+var_228]
0x18001d709  mov     rdi, [rsp+288h+hwnd]
0x18001d70e  mov     [rsp+288h+var_220], rdi
0x18001d713  mov     [rsp+288h+var_218], rbx
0x18001d718  test    rdi, rdi
0x18001d71b  jnz     short loc_18001D736
0x18001d71d  call    cs:__imp_GetActiveWindow
0x18001d724  nop     dword ptr [rax+rax+00h]
0x18001d729  mov     rdi, rax
0x18001d72c  mov     [rsp+288h+var_220], rax
0x18001d731  test    rax, rax
0x18001d734  jz      short loc_18001D75D
0x18001d736  call    cs:__imp_GetFocus
0x18001d73d  nop     dword ptr [rax+rax+00h]
0x18001d742  mov     [rsp+288h+var_218], rax
0x18001d747  test    esi, esi
0x18001d749  jnz     short loc_18001D75D
0x18001d74b  xor     edx, edx; bEnable
0x18001d74d  mov     rcx, rdi; hWnd
0x18001d750  call    cs:__imp_EnableWindow
0x18001d757  nop     dword ptr [rax+rax+00h]
0x18001d75c  nop
0x18001d75d  xor     ecx, ecx; bConvert
0x18001d75f  call    cs:__imp_IsGUIThread
0x18001d766  nop     dword ptr [rax+rax+00h]
0x18001d76b  test    eax, eax
0x18001d76d  jnz     loc_18001D8E6
0x18001d773  mov     rcx, [rsp+288h+var_F8]
0x18001d77b  test    rcx, rcx
0x18001d77e  jz      loc_18001DAA4
0x18001d784  jmp     loc_18001D8D5
0x18001d789  mov     [rsp+288h+var_30], rbx
0x18001d791  test    rcx, rcx
0x18001d794  jz      short loc_18001D7F8
0x18001d796  lea     rax, [rsp+288h+var_E8]
0x18001d79e  cmp     rcx, rax
0x18001d7a1  jnz     short loc_18001D7E8
0x18001d7a3  mov     rax, [rcx]
0x18001d7a6  lea     rdx, [rsp+288h+var_68]
0x18001d7ae  mov     rax, [rax+8]
0x18001d7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b7  mov     [rsp+288h+var_30], rax
0x18001d7bf  mov     rcx, [rsp+288h+var_B0]
0x18001d7c7  test    rcx, rcx
0x18001d7ca  jz      short loc_18001D7F8
0x18001d7cc  mov     rax, [rcx]
0x18001d7cf  lea     rdx, [rsp+288h+var_E8]
0x18001d7d7  cmp     rcx, rdx
0x18001d7da  setnz   dl
0x18001d7dd  mov     rax, [rax+20h]
0x18001d7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7e6  jmp     short loc_18001D7F0
0x18001d7e8  mov     [rsp+288h+var_30], rcx
0x18001d7f0  mov     [rsp+288h+var_B0], rbx
0x18001d7f8  mov     rcx, [rsp+288h+var_F8]
0x18001d800  test    rcx, rcx
0x18001d803  jz      short loc_18001D867
0x18001d805  lea     rax, [rsp+288h+var_130]
0x18001d80d  cmp     rcx, rax
0x18001d810  jnz     short loc_18001D857
0x18001d812  mov     rax, [rcx]
0x18001d815  lea     rdx, [rsp+288h+var_E8]
0x18001d81d  mov     rax, [rax+8]
0x18001d821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d826  mov     [rsp+288h+var_B0], rax
0x18001d82e  mov     rcx, [rsp+288h+var_F8]
0x18001d836  test    rcx, rcx
0x18001d839  jz      short loc_18001D867
0x18001d83b  mov     rax, [rcx]
0x18001d83e  lea     rdx, [rsp+288h+var_130]
0x18001d846  cmp     rcx, rdx
0x18001d849  setnz   dl
0x18001d84c  mov     rax, [rax+20h]
0x18001d850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d855  jmp     short loc_18001D85F
0x18001d857  mov     [rsp+288h+var_B0], rcx
0x18001d85f  mov     [rsp+288h+var_F8], rbx
0x18001d867  mov     rcx, [rsp+288h+var_30]
0x18001d86f  test    rcx, rcx
0x18001d872  jz      loc_18001D69F
0x18001d878  lea     rax, [rsp+288h+var_68]
0x18001d880  cmp     rcx, rax
0x18001d883  jnz     loc_18001D697
0x18001d889  mov     rax, [rcx]
0x18001d88c  lea     rdx, [rsp+288h+var_130]
0x18001d894  mov     rax, [rax+8]
0x18001d898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d89d  mov     [rsp+288h+var_F8], rax
0x18001d8a5  mov     rcx, [rsp+288h+var_30]
0x18001d8ad  test    rcx, rcx
0x18001d8b0  jz      loc_18001D69F
0x18001d8b6  mov     rax, [rcx]
0x18001d8b9  lea     rdx, [rsp+288h+var_68]
0x18001d8c1  cmp     rcx, rdx
0x18001d8c4  setnz   dl
0x18001d8c7  mov     rax, [rax+20h]
0x18001d8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d0  jmp     loc_18001D69F
0x18001d8d5  mov     rax, [rcx]
0x18001d8d8  mov     rax, [rax+10h]
0x18001d8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e1  jmp     loc_18001D9DF
0x18001d8e6  xor     r9d, r9d; lpName
0x18001d8e9  xor     r8d, r8d; bInitialState
0x18001d8ec  xor     edx, edx; bManualReset
0x18001d8ee  xor     ecx, ecx; lpEventAttributes
0x18001d8f0  call    cs:__imp_CreateEventW
0x18001d8f7  nop     dword ptr [rax+rax+00h]
0x18001d8fc  mov     rdi, rax
0x18001d8ff  mov     [rsp+288h+pHandles], rax
0x18001d904  mov     rcx, [rsp+288h+hObject]; hObject
0x18001d90c  lea     rdx, [rcx-1]
0x18001d910  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001d914  ja      short loc_18001D922
0x18001d916  call    cs:__imp_CloseHandle
0x18001d91d  nop     dword ptr [rax+rax+00h]
0x18001d922  mov     [rsp+288h+hObject], rdi
0x18001d92a  mov     r8d, 110h; Flags
0x18001d930  lea     rdx, [rsp+288h+hObject]; Context
0x18001d938  lea     rcx, ?ThreadProc@UserWorkItem@PrintConfig@@CAKPEAX@Z; Function
0x18001d93f  call    cs:__imp_QueueUserWorkItem
0x18001d946  nop     dword ptr [rax+rax+00h]
0x18001d94b  test    eax, eax
0x18001d94d  jz      loc_18001DAA9
0x18001d953  xorps   xmm0, xmm0
0x18001d956  movups  xmmword ptr [rsp+288h+Msg.hwnd], xmm0
0x18001d95b  movups  xmmword ptr [rsp+288h+Msg.wParam], xmm0
0x18001d963  movups  xmmword ptr [rsp+288h+Msg.time], xmm0
0x18001d96b  mov     edi, 1C7Fh
0x18001d970  or      r14d, 0FFFFFFFFh
0x18001d974  mov     esi, 1
0x18001d979  jmp     short loc_18001D9BE
0x18001d97b  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001d980  call    cs:__imp_TranslateMessage
0x18001d987  nop     dword ptr [rax+rax+00h]
0x18001d98c  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001d991  call    cs:__imp_DispatchMessageW
0x18001d998  nop     dword ptr [rax+rax+00h]
0x18001d99d  mov     [rsp+288h+wRemoveMsg], esi; wRemoveMsg
0x18001d9a1  xor     r9d, r9d; wMsgFilterMax
0x18001d9a4  xor     r8d, r8d; wMsgFilterMin
0x18001d9a7  xor     edx, edx; hWnd
0x18001d9a9  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001d9ae  call    cs:__imp_PeekMessageW
0x18001d9b5  nop     dword ptr [rax+rax+00h]
0x18001d9ba  test    eax, eax
0x18001d9bc  jnz     short loc_18001D97B
0x18001d9be  mov     [rsp+288h+wRemoveMsg], edi; dwWakeMask
0x18001d9c2  mov     r9d, r14d; dwMilliseconds
0x18001d9c5  xor     r8d, r8d; fWaitAll
0x18001d9c8  lea     rdx, [rsp+288h+pHandles]; pHandles
0x18001d9cd  mov     ecx, esi; nCount
0x18001d9cf  call    cs:__imp_MsgWaitForMultipleObjects
0x18001d9d6  nop     dword ptr [rax+rax+00h]
0x18001d9db  cmp     eax, esi
0x18001d9dd  jz      short loc_18001D99D
0x18001d9df  lea     rcx, [rsp+288h+var_228]; this
0x18001d9e4  call    ??1OutOfProcessDialogStateScope@PrintConfig@@QEAA@XZ; PrintConfig::OutOfProcessDialogStateScope::~OutOfProcessDialogStateScope(void)
0x18001d9e9  nop
0x18001d9ea  jmp     short loc_18001D9EE
0x18001d9ec  xor     ebx, ebx
0x18001d9ee  mov     rax, [rsp+288h+var_238]
0x18001d9f3  mov     rdi, [rax]
0x18001d9f6  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x18001d9fb  mov     rax, [rax+8]
0x18001d9ff  test    rax, rax
0x18001da02  jz      short loc_18001DA1D
0x18001da04  mov     eax, [rax]
0x18001da06  test    eax, eax
0x18001da08  jz      short loc_18001DA1D
0x18001da0a  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x18001da0f  mov     r8d, [rsp+288h+var_258]; int
0x18001da14  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18001da18  call    ?PrinterExtensionPrintPreferencesAttempt_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEAGJ@Z; Print::Driver::Telemetry::PrintConfigTelemetry::PrinterExtensionPrintPreferencesAttempt_(ushort * const,long)
0x18001da1d  mov     edi, [rsp+288h+var_258]
0x18001da21  mov     rcx, [rsp+288h+var_F8]
0x18001da29  test    rcx, rcx
0x18001da2c  jz      short loc_18001DA50
0x18001da2e  mov     rax, [rcx]
0x18001da31  lea     rdx, [rsp+288h+var_130]
0x18001da39  cmp     rcx, rdx
  ... truncated ...
```
