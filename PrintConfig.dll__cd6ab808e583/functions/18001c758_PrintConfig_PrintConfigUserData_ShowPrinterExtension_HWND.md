# PrintConfig::PrintConfigUserData::ShowPrinterExtension(HWND__ *)

- ea: `0x18001c758`
- end: `0x18001cda2`
- name: `?ShowPrinterExtension@PrintConfigUserData@PrintConfig@@QEAAJPEAUHWND__@@@Z`
- size: `1610`
- prototype: `__int64 __fastcall(PrintConfig::PrintConfigUserData *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180019fc4`
- `0x18001c4b0`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000f380`
- `0x180014a48`
- `0x180018bbc`
- `0x18001c6d4`
- `0x18001c758`
- `0x18001ce80`
- `0x1800e59d8`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001c7e3`
- `KERNEL32!GetProcAddress` at `0x18001c7e3`
- `KERNEL32!FreeLibrary` at `0x18001c859`
- `KERNEL32!FreeLibrary` at `0x18001c859`
- `KERNEL32!CloseHandle` at `0x18001cba0`
- `KERNEL32!CloseHandle` at `0x18001ccef`
- `KERNEL32!CloseHandle` at `0x18001cba0`
- `KERNEL32!CloseHandle` at `0x18001ccef`
- `KERNEL32!GetLastError` at `0x18001cd34`
- `KERNEL32!GetLastError` at `0x18001cd34`
- `KERNEL32!CreateEventW` at `0x18001cb80`
- `KERNEL32!CreateEventW` at `0x18001cb80`
- `KERNEL32!QueueUserWorkItem` at `0x18001cbc3`
- `KERNEL32!QueueUserWorkItem` at `0x18001cbc3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001c841`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001c841`
- `USER32!PeekMessageW` at `0x18001cc17`
- `USER32!PeekMessageW` at `0x18001cc17`
- `USER32!TranslateMessage` at `0x18001cbf5`
- `USER32!TranslateMessage` at `0x18001cbf5`
- `USER32!IsGUIThread` at `0x18001c9f0`
- `USER32!IsGUIThread` at `0x18001c9f0`
- `USER32!GetActiveWindow` at `0x18001c9bd`
- `USER32!GetActiveWindow` at `0x18001c9bd`
- `USER32!GetFocus` at `0x18001c9d0`
- `USER32!GetFocus` at `0x18001c9d0`
- `USER32!EnableWindow` at `0x18001c9e7`
- `USER32!EnableWindow` at `0x18001cc50`
- `USER32!EnableWindow` at `0x18001c9e7`
- `USER32!EnableWindow` at `0x18001cc50`
- `USER32!SetActiveWindow` at `0x18001cc59`
- `USER32!SetActiveWindow` at `0x18001cc59`
- `USER32!SetForegroundWindow` at `0x18001cc62`
- `USER32!SetForegroundWindow` at `0x18001cc62`
- `USER32!SetFocus` at `0x18001cc70`
- `USER32!SetFocus` at `0x18001cc70`
- `USER32!GetAncestor` at `0x18001c86d`
- `USER32!GetAncestor` at `0x18001c86d`
- `USER32!DispatchMessageW` at `0x18001cc00`
- `USER32!DispatchMessageW` at `0x18001cc00`
- `USER32!MsgWaitForMultipleObjects` at `0x18001cc37`
- `USER32!MsgWaitForMultipleObjects` at `0x18001cc37`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrintConfig::PrintConfigUserData::ShowPrinterExtension(
        PrintConfig::PrintConfigUserData *this,
        HWND a2)
{
  HMODULE v3; // rdi
  int v4; // esi
  FARPROC ProcAddress; // rax
  _BYTE *v6; // rax
  _BYTE *v7; // rcx
  _BYTE *v8; // rdx
  _QWORD *v9; // rdx
  int v10; // esi
  bool v11; // r15
  HWND ActiveWindow; // rdi
  HWND Focus; // r14
  _BYTE *v14; // rdx
  _BYTE *v15; // rdx
  _BYTE *v16; // rdx
  HANDLE EventW; // rsi
  unsigned __int16 *const *v18; // rdi
  _DWORD *v19; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v20; // rcx
  unsigned int v21; // edi
  _BYTE *v22; // rdx
  signed int LastError; // eax
  unsigned int v25; // edi
  int v26; // [rsp+30h] [rbp-258h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-250h] BYREF
  HWND hwnd; // [rsp+40h] [rbp-248h] BYREF
  int v29; // [rsp+48h] [rbp-240h] BYREF
  void **v30; // [rsp+50h] [rbp-238h]
  HMODULE v31; // [rsp+58h] [rbp-230h]
  bool v32; // [rsp+60h] [rbp-228h]
  HWND v33; // [rsp+68h] [rbp-220h]
  HWND v34; // [rsp+70h] [rbp-218h]
  MSG Msg; // [rsp+78h] [rbp-210h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-1E0h]
  const PrintCore::WindowsError *v37; // [rsp+B0h] [rbp-1D8h] BYREF
  const hr_error *v38; // [rsp+B8h] [rbp-1D0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+C0h] [rbp-1C8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+E0h] [rbp-1A8h] BYREF
  char v41[56]; // [rsp+E8h] [rbp-1A0h] BYREF
  int v42; // [rsp+120h] [rbp-168h]
  HANDLE hObject; // [rsp+150h] [rbp-138h] BYREF
  _BYTE v44[56]; // [rsp+158h] [rbp-130h] BYREF
  _BYTE *v45; // [rsp+190h] [rbp-F8h]
  _BYTE v46[56]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE *v47; // [rsp+1D8h] [rbp-B0h]
  _QWORD v48[7]; // [rsp+1E0h] [rbp-A8h] BYREF
  _QWORD *v49; // [rsp+218h] [rbp-70h]
  _BYTE v50[56]; // [rsp+220h] [rbp-68h] BYREF
  _BYTE *v51; // [rsp+258h] [rbp-30h]

  v36 = -2;
  hwnd = a2;
  v26 = -2147467259;
  v30 = &ModuleRAII::`vftable';
  v3 = v31;
  if ( (int)LoadLibraryFromSystemDirectory(L"winspool.drv") < 0 )
    v3 = 0;
  v31 = v3;
  if ( v3 )
  {
    v4 = 0;
    ProcAddress = GetProcAddress(v3, "GetPrintExecutionData");
    if ( ProcAddress )
    {
      pHandles = 0;
      if ( ((unsigned int (__fastcall *)(HANDLE *))ProcAddress)(&pHandles) && (_DWORD)pHandles == 4 )
        v4 = HIDWORD(pHandles);
    }
    else
    {
      memset_0(v41, 0, 0x68u);
      RpcCallAttributes[0] = 2;
      RpcCallAttributes[1] = 16;
      if ( !RpcServerInqCallAttributesW(0, RpcCallAttributes) )
        v4 = v42;
    }
    FreeLibrary(v3);
  }
  else
  {
    v4 = 0;
  }
  v29 = v4;
  hwnd = GetAncestor(hwnd, 2u);
  v48[0] = &std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::`vftable';
  v48[1] = &v26;
  v48[2] = this;
  v48[3] = &hwnd;
  v48[4] = &v29;
  v49 = v48;
  hObject = 0;
  v45 = 0;
  v47 = 0;
  v6 = (_BYTE *)std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::_Move(v48, v46);
  try
  {
    v7 = v6;
    v47 = v6;
    if ( v6 != v46 && v45 != v44 )
    {
      v47 = v45;
      goto LABEL_16;
    }
    v51 = 0;
    if ( v6 )
    {
      if ( v6 == v46 )
      {
        v51 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v50);
        if ( !v47 )
          goto LABEL_34;
        v14 = v46;
        LOBYTE(v14) = v47 != v46;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v14);
      }
      else
      {
        v51 = v6;
      }
      v47 = 0;
    }
LABEL_34:
    if ( v45 )
    {
      if ( v45 != v44 )
      {
        v47 = v45;
        goto LABEL_39;
      }
      v47 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v45 + 8LL))(v45, v46);
      if ( v45 )
      {
        v15 = v44;
        LOBYTE(v15) = v45 != v44;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v45 + 32LL))(v45, v15);
LABEL_39:
        v45 = 0;
      }
    }
    v7 = v51;
    if ( !v51 )
      goto LABEL_17;
    if ( v51 == v50 )
    {
      v45 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v51 + 8LL))(v51, v44);
      if ( v51 )
      {
        v16 = v50;
        LOBYTE(v16) = v51 != v50;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v51 + 32LL))(v51, v16);
      }
      goto LABEL_17;
    }
LABEL_16:
    v45 = v7;
LABEL_17:
    if ( v47 )
    {
      v8 = v46;
      LOBYTE(v8) = v47 != v46;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v8);
    }
    if ( v49 )
    {
      v9 = v48;
      LOBYTE(v9) = v49 != v48;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v49 + 32LL))(v49, v9);
    }
    v30 = (void **)((char *)this + 24);
    v10 = *(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 0x40000000;
    v11 = v10 == 0;
    v32 = v10 == 0;
    ActiveWindow = hwnd;
    v33 = hwnd;
    Focus = 0;
    v34 = 0;
    if ( hwnd || (ActiveWindow = GetActiveWindow(), (v33 = ActiveWindow) != 0) )
    {
      Focus = GetFocus();
      v34 = Focus;
      if ( !v10 )
        EnableWindow(ActiveWindow, 0);
    }
    if ( IsGUIThread(0) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      pHandles = EventW;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      hObject = EventW;
      if ( !QueueUserWorkItem(PrintConfig::UserWorkItem::ThreadProc, &hObject, 0x110u) )
      {
        LastError = GetLastError();
        v25 = LastError;
        if ( LastError > 0 )
          v25 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids, v25);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v25);
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
      if ( !v45 )
        std::_Xbad_function_call();
      (*(void (**)(void))(*(_QWORD *)v45 + 16LL))();
    }
    if ( ActiveWindow )
    {
      if ( v11 )
        EnableWindow(ActiveWindow, 1);
      SetActiveWindow(ActiveWindow);
      SetForegroundWindow(ActiveWindow);
    }
    if ( Focus )
      SetFocus(Focus);
  }
  catch ( std::bad_alloc )
  {
    v26 = -2147024882;
  }
  catch ( const hr_error *v38 )
  {
    v26 = *((_DWORD *)v38 + 6);
  }
  catch ( const PrintCore::WindowsError *v37 )
  {
    v26 = *((_DWORD *)v37 + 6);
  }
  catch ( std::exception )
  {
    v26 = -2147467259;
  }
  catch ( ... )
  {
    v26 = -2147418113;
  }
  v18 = (unsigned __int16 *const *)*v30;
  v19 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
  if ( v19 && *v19 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
    Print::Driver::Telemetry::PrintConfigTelemetry::PrinterExtensionPrintPreferencesAttempt_(v20, v18[2], v26);
  }
  v21 = v26;
  if ( v45 )
  {
    v22 = v44;
    LOBYTE(v22) = v45 != v44;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v45 + 32LL))(v45, v22);
    v45 = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v21;
}

```

## disassembly

```asm
0x18001c758  mov     rax, rsp
0x18001c75b  push    rdi
0x18001c75c  push    r14
0x18001c75e  push    r15
0x18001c760  sub     rsp, 270h
0x18001c767  mov     qword ptr [rax-1E0h], 0FFFFFFFFFFFFFFFEh
0x18001c772  mov     [rax+18h], rbx
0x18001c776  mov     [rax+20h], rsi
0x18001c77a  mov     rax, cs:__security_cookie
0x18001c781  xor     rax, rsp
0x18001c784  mov     [rsp+288h+var_28], rax
0x18001c78c  mov     r14, rcx
0x18001c78f  mov     [rsp+288h+hwnd], rdx
0x18001c794  mov     [rsp+288h+var_258], 80004005h
0x18001c79c  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x18001c7a3  mov     [rsp+288h+var_238], rax
0x18001c7a8  lea     rdx, [rsp+288h+var_230]
0x18001c7ad  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18001c7b4  call    LoadLibraryFromSystemDirectory
0x18001c7b9  mov     rdi, [rsp+288h+var_230]
0x18001c7be  xor     ebx, ebx
0x18001c7c0  test    eax, eax
0x18001c7c2  cmovs   rdi, rbx
0x18001c7c6  mov     [rsp+288h+var_230], rdi
0x18001c7cb  test    rdi, rdi
0x18001c7ce  jnz     short loc_18001C7D7
0x18001c7d0  mov     esi, ebx
0x18001c7d2  jmp     loc_18001C85F
0x18001c7d7  mov     esi, ebx
0x18001c7d9  lea     rdx, aGetprintexecut; "GetPrintExecutionData"
0x18001c7e0  mov     rcx, rdi; hModule
0x18001c7e3  call    cs:__imp_GetProcAddress
0x18001c7e9  test    rax, rax
0x18001c7ec  jz      short loc_18001C80E
0x18001c7ee  mov     [rsp+288h+pHandles], rbx
0x18001c7f3  lea     rcx, [rsp+288h+pHandles]
0x18001c7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7fd  test    eax, eax
0x18001c7ff  jz      short loc_18001C851
0x18001c801  cmp     dword ptr [rsp+288h+pHandles], 4
0x18001c806  jnz     short loc_18001C851
0x18001c808  mov     esi, dword ptr [rsp+288h+pHandles+4]
0x18001c80c  jmp     short loc_18001C851
0x18001c80e  xor     edx, edx; Val
0x18001c810  lea     r8d, [rdx+68h]; Size
0x18001c814  lea     rcx, [rsp+288h+var_1A0]; void *
0x18001c81c  call    memset_0
0x18001c821  mov     [rsp+288h+RpcCallAttributes], 2
0x18001c82c  mov     [rsp+288h+var_1A4], 10h
0x18001c837  lea     rdx, [rsp+288h+RpcCallAttributes]; RpcCallAttributes
0x18001c83f  xor     ecx, ecx; ClientBinding
0x18001c841  call    cs:__imp_RpcServerInqCallAttributesW
0x18001c847  test    eax, eax
0x18001c849  cmovz   esi, [rsp+288h+var_168]
0x18001c851  test    rdi, rdi
0x18001c854  jz      short loc_18001C85F
0x18001c856  mov     rcx, rdi; hLibModule
0x18001c859  call    cs:__imp_FreeLibrary
0x18001c85f  mov     [rsp+288h+var_240], esi
0x18001c863  mov     edx, 2; gaFlags
0x18001c868  mov     rcx, [rsp+288h+hwnd]; hwnd
0x18001c86d  call    cs:__imp_GetAncestor
0x18001c873  mov     [rsp+288h+hwnd], rax
0x18001c878  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d422c950f2f909e47ca6180ffad9d988_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::`vftable'
0x18001c87f  mov     [rsp+288h+var_A8], rax
0x18001c887  lea     rax, [rsp+288h+var_258]
0x18001c88c  mov     [rsp+288h+var_A0], rax
0x18001c894  mov     [rsp+288h+var_98], r14
0x18001c89c  lea     rax, [rsp+288h+hwnd]
0x18001c8a1  mov     [rsp+288h+var_90], rax
0x18001c8a9  lea     rax, [rsp+288h+var_240]
0x18001c8ae  mov     [rsp+288h+var_88], rax
0x18001c8b6  lea     rax, [rsp+288h+var_A8]
0x18001c8be  mov     [rsp+288h+var_70], rax
0x18001c8c6  mov     [rsp+288h+hObject], rbx
0x18001c8ce  mov     [rsp+288h+var_F8], rbx
0x18001c8d6  mov     [rsp+288h+var_B0], rbx
0x18001c8de  lea     rdx, [rsp+288h+var_E8]
0x18001c8e6  lea     rcx, [rsp+288h+var_A8]
0x18001c8ee  call    ?_Move@?$_Func_impl_no_alloc@V_lambda_d422c950f2f909e47ca6180ffad9d988_@@X$$V@std@@EEAAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<_lambda_d422c950f2f909e47ca6180ffad9d988_,void,>::_Move(void *)
0x18001c8f3  mov     rcx, rax
0x18001c8f6  mov     [rsp+288h+var_B0], rax
0x18001c8fe  lea     rax, [rsp+288h+var_E8]
0x18001c906  cmp     rcx, rax
0x18001c909  jz      loc_18001CA14
0x18001c90f  mov     rax, [rsp+288h+var_F8]
0x18001c917  lea     rdx, [rsp+288h+var_130]
0x18001c91f  cmp     rax, rdx
0x18001c922  jz      loc_18001CA14
0x18001c928  mov     [rsp+288h+var_B0], rax
0x18001c930  mov     [rsp+288h+var_F8], rcx
0x18001c938  mov     rcx, [rsp+288h+var_B0]
0x18001c940  test    rcx, rcx
0x18001c943  jz      short loc_18001C960
0x18001c945  mov     rax, [rcx]
0x18001c948  lea     rdx, [rsp+288h+var_E8]
0x18001c950  cmp     rcx, rdx
0x18001c953  setnz   dl
0x18001c956  mov     rax, [rax+20h]
0x18001c95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c95f  nop
0x18001c960  mov     rcx, [rsp+288h+var_70]
0x18001c968  test    rcx, rcx
0x18001c96b  jz      short loc_18001C988
0x18001c96d  mov     rax, [rcx]
0x18001c970  lea     rdx, [rsp+288h+var_A8]
0x18001c978  cmp     rcx, rdx
0x18001c97b  setnz   dl
0x18001c97e  mov     rax, [rax+20h]
0x18001c982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c987  nop
0x18001c988  lea     rax, [r14+18h]
0x18001c98c  mov     [rsp+288h+var_238], rax
0x18001c991  mov     rax, [rax]
0x18001c994  mov     esi, [rax+2Ch]
0x18001c997  and     esi, 40000000h
0x18001c99d  setz    r15b
0x18001c9a1  mov     [rsp+288h+var_228], r15b
0x18001c9a6  mov     rdi, [rsp+288h+hwnd]
0x18001c9ab  mov     [rsp+288h+var_220], rdi
0x18001c9b0  mov     r14, rbx
0x18001c9b3  mov     [rsp+288h+var_218], rbx
0x18001c9b8  test    rdi, rdi
0x18001c9bb  jnz     short loc_18001C9D0
0x18001c9bd  call    cs:__imp_GetActiveWindow
0x18001c9c3  mov     rdi, rax
0x18001c9c6  mov     [rsp+288h+var_220], rax
0x18001c9cb  test    rax, rax
0x18001c9ce  jz      short loc_18001C9EE
0x18001c9d0  call    cs:__imp_GetFocus
0x18001c9d6  mov     r14, rax
0x18001c9d9  mov     [rsp+288h+var_218], rax
0x18001c9de  test    esi, esi
0x18001c9e0  jnz     short loc_18001C9EE
0x18001c9e2  xor     edx, edx; bEnable
0x18001c9e4  mov     rcx, rdi; hWnd
0x18001c9e7  call    cs:__imp_EnableWindow
0x18001c9ed  nop
0x18001c9ee  xor     ecx, ecx; bConvert
0x18001c9f0  call    cs:__imp_IsGUIThread
0x18001c9f6  test    eax, eax
0x18001c9f8  jnz     loc_18001CB76
0x18001c9fe  mov     rcx, [rsp+288h+var_F8]
0x18001ca06  test    rcx, rcx
0x18001ca09  jz      loc_18001CD2F
0x18001ca0f  jmp     loc_18001CB60
0x18001ca14  mov     [rsp+288h+var_30], rbx
0x18001ca1c  test    rcx, rcx
0x18001ca1f  jz      short loc_18001CA83
0x18001ca21  lea     rax, [rsp+288h+var_E8]
0x18001ca29  cmp     rcx, rax
0x18001ca2c  jnz     short loc_18001CA73
0x18001ca2e  mov     rax, [rcx]
0x18001ca31  lea     rdx, [rsp+288h+var_68]
0x18001ca39  mov     rax, [rax+8]
0x18001ca3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca42  mov     [rsp+288h+var_30], rax
0x18001ca4a  mov     rcx, [rsp+288h+var_B0]
0x18001ca52  test    rcx, rcx
0x18001ca55  jz      short loc_18001CA83
0x18001ca57  mov     rax, [rcx]
0x18001ca5a  lea     rdx, [rsp+288h+var_E8]
0x18001ca62  cmp     rcx, rdx
0x18001ca65  setnz   dl
0x18001ca68  mov     rax, [rax+20h]
0x18001ca6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca71  jmp     short loc_18001CA7B
0x18001ca73  mov     [rsp+288h+var_30], rcx
0x18001ca7b  mov     [rsp+288h+var_B0], rbx
0x18001ca83  mov     rcx, [rsp+288h+var_F8]
0x18001ca8b  test    rcx, rcx
0x18001ca8e  jz      short loc_18001CAF2
0x18001ca90  lea     rax, [rsp+288h+var_130]
0x18001ca98  cmp     rcx, rax
0x18001ca9b  jnz     short loc_18001CAE2
0x18001ca9d  mov     rax, [rcx]
0x18001caa0  lea     rdx, [rsp+288h+var_E8]
0x18001caa8  mov     rax, [rax+8]
0x18001caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cab1  mov     [rsp+288h+var_B0], rax
0x18001cab9  mov     rcx, [rsp+288h+var_F8]
0x18001cac1  test    rcx, rcx
0x18001cac4  jz      short loc_18001CAF2
0x18001cac6  mov     rax, [rcx]
0x18001cac9  lea     rdx, [rsp+288h+var_130]
0x18001cad1  cmp     rcx, rdx
0x18001cad4  setnz   dl
0x18001cad7  mov     rax, [rax+20h]
0x18001cadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cae0  jmp     short loc_18001CAEA
0x18001cae2  mov     [rsp+288h+var_B0], rcx
0x18001caea  mov     [rsp+288h+var_F8], rbx
0x18001caf2  mov     rcx, [rsp+288h+var_30]
0x18001cafa  test    rcx, rcx
0x18001cafd  jz      loc_18001C938
0x18001cb03  lea     rax, [rsp+288h+var_68]
0x18001cb0b  cmp     rcx, rax
0x18001cb0e  jnz     loc_18001C930
0x18001cb14  mov     rax, [rcx]
0x18001cb17  lea     rdx, [rsp+288h+var_130]
0x18001cb1f  mov     rax, [rax+8]
0x18001cb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb28  mov     [rsp+288h+var_F8], rax
0x18001cb30  mov     rcx, [rsp+288h+var_30]
0x18001cb38  test    rcx, rcx
0x18001cb3b  jz      loc_18001C938
0x18001cb41  mov     rax, [rcx]
0x18001cb44  lea     rdx, [rsp+288h+var_68]
0x18001cb4c  cmp     rcx, rdx
0x18001cb4f  setnz   dl
0x18001cb52  mov     rax, [rax+20h]
0x18001cb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb5b  jmp     loc_18001C938
0x18001cb60  mov     rax, [rcx]
0x18001cb63  mov     rax, [rax+10h]
0x18001cb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb6c  mov     esi, 1
0x18001cb71  jmp     loc_18001CC41
0x18001cb76  xor     r9d, r9d; lpName
0x18001cb79  xor     r8d, r8d; bInitialState
0x18001cb7c  xor     edx, edx; bManualReset
0x18001cb7e  xor     ecx, ecx; lpEventAttributes
0x18001cb80  call    cs:__imp_CreateEventW
0x18001cb86  mov     rsi, rax
0x18001cb89  mov     [rsp+288h+pHandles], rax
0x18001cb8e  mov     rcx, [rsp+288h+hObject]; hObject
0x18001cb96  lea     rdx, [rcx-1]
0x18001cb9a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001cb9e  ja      short loc_18001CBA6
0x18001cba0  call    cs:__imp_CloseHandle
0x18001cba6  mov     [rsp+288h+hObject], rsi
0x18001cbae  mov     r8d, 110h; Flags
0x18001cbb4  lea     rdx, [rsp+288h+hObject]; Context
0x18001cbbc  lea     rcx, ?ThreadProc@UserWorkItem@PrintConfig@@CAKPEAX@Z; Function
0x18001cbc3  call    cs:__imp_QueueUserWorkItem
0x18001cbc9  test    eax, eax
0x18001cbcb  jz      loc_18001CD34
0x18001cbd1  xorps   xmm0, xmm0
0x18001cbd4  movups  xmmword ptr [rsp+288h+Msg.hwnd], xmm0
0x18001cbd9  movups  xmmword ptr [rsp+288h+Msg.wParam], xmm0
0x18001cbe1  movups  xmmword ptr [rsp+288h+Msg.time], xmm0
0x18001cbe9  mov     esi, 1
0x18001cbee  jmp     short loc_18001CC21
0x18001cbf0  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001cbf5  call    cs:__imp_TranslateMessage
0x18001cbfb  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001cc00  call    cs:__imp_DispatchMessageW
0x18001cc06  mov     [rsp+288h+wRemoveMsg], esi; wRemoveMsg
0x18001cc0a  xor     r9d, r9d; wMsgFilterMax
0x18001cc0d  xor     r8d, r8d; wMsgFilterMin
0x18001cc10  xor     edx, edx; hWnd
0x18001cc12  lea     rcx, [rsp+288h+Msg]; lpMsg
0x18001cc17  call    cs:__imp_PeekMessageW
0x18001cc1d  test    eax, eax
0x18001cc1f  jnz     short loc_18001CBF0
0x18001cc21  mov     [rsp+288h+wRemoveMsg], 1C7Fh; dwWakeMask
0x18001cc29  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001cc2d  xor     r8d, r8d; fWaitAll
0x18001cc30  lea     rdx, [rsp+288h+pHandles]; pHandles
0x18001cc35  mov     ecx, esi; nCount
0x18001cc37  call    cs:__imp_MsgWaitForMultipleObjects
0x18001cc3d  cmp     eax, esi
0x18001cc3f  jz      short loc_18001CC06
0x18001cc41  test    rdi, rdi
0x18001cc44  jz      short loc_18001CC68
0x18001cc46  test    r15b, r15b
0x18001cc49  jz      short loc_18001CC56
0x18001cc4b  mov     edx, esi; bEnable
0x18001cc4d  mov     rcx, rdi; hWnd
0x18001cc50  call    cs:__imp_EnableWindow
0x18001cc56  mov     rcx, rdi; hWnd
0x18001cc59  call    cs:__imp_SetActiveWindow
0x18001cc5f  mov     rcx, rdi; hWnd
0x18001cc62  call    cs:__imp_SetForegroundWindow
0x18001cc68  test    r14, r14
0x18001cc6b  jz      short loc_18001CC77
0x18001cc6d  mov     rcx, r14; hWnd
0x18001cc70  call    cs:__imp_SetFocus
0x18001cc76  nop
0x18001cc77  jmp     short loc_18001CC7B
0x18001cc79  xor     ebx, ebx
0x18001cc7b  mov     rax, [rsp+288h+var_238]
0x18001cc80  mov     rdi, [rax]
0x18001cc83  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x18001cc88  mov     rax, [rax+8]
0x18001cc8c  test    rax, rax
0x18001cc8f  jz      short loc_18001CCAA
0x18001cc91  mov     eax, [rax]
0x18001cc93  test    eax, eax
0x18001cc95  jz      short loc_18001CCAA
0x18001cc97  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x18001cc9c  mov     r8d, [rsp+288h+var_258]; int
0x18001cca1  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18001cca5  call    ?PrinterExtensionPrintPreferencesAttempt_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEAGJ@Z; Print::Driver::Telemetry::PrintConfigTelemetry::PrinterExtensionPrintPreferencesAttempt_(ushort * const,long)
0x18001ccaa  mov     edi, [rsp+288h+var_258]
0x18001ccae  mov     rcx, [rsp+288h+var_F8]
0x18001ccb6  test    rcx, rcx
0x18001ccb9  jz      short loc_18001CCDD
0x18001ccbb  mov     rax, [rcx]
0x18001ccbe  lea     rdx, [rsp+288h+var_130]
  ... truncated ...
```
