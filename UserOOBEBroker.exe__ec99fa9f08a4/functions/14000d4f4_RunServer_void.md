# _RunServer(void)

- ea: `0x14000d4f4`
- end: `0x14000d786`
- name: `?_RunServer@@YAJXZ`
- size: `658`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000daf0`

## callees

- `0x140005474`
- `0x14000731c`
- `0x1400082d4`
- `0x14000d4b8`
- `0x14000d4f4`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000d64a`
- `KERNEL32!GetCurrentThreadId` at `0x14000d64a`
- `KERNEL32!InitOnceExecuteOnce` at `0x14000d666`
- `KERNEL32!InitOnceExecuteOnce` at `0x14000d666`
- `USER32!TranslateMessage` at `0x14000d717`
- `USER32!TranslateMessage` at `0x14000d717`
- `USER32!DispatchMessageW` at `0x14000d721`
- `USER32!DispatchMessageW` at `0x14000d721`
- `USER32!GetMessageW` at `0x14000d733`
- `USER32!GetMessageW` at `0x14000d733`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000d602`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000d602`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000d74a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000d74a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000d50f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000d50f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d563`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d563`

## string_xrefs

- `0x14000d522`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000d576`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000d615`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000d6c9`: `shell\oobe\user\exe\useroobebroker.cpp`

## pseudocode

```c
__int64 _RunServer(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HRESULT v3; // eax
  LPVOID v4; // rcx
  int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  HRESULT v8; // eax
  LPVOID v9; // rcx
  DWORD CurrentThreadId; // ebx
  int v11; // eax
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  int ppv; // [rsp+20h] [rbp-19h]
  int ppva; // [rsp+20h] [rbp-19h]
  int ppvb; // [rsp+20h] [rbp-19h]
  __int64 *v17; // [rsp+50h] [rbp+17h] BYREF
  char v18; // [rsp+58h] [rbp+1Fh]
  MSG Msg; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  LPVOID v21; // [rsp+A0h] [rbp+67h] BYREF

  v0 = CoInitializeEx(0, 0);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
      (const char *)(unsigned int)v0,
      ppv);
    return v1;
  }
  v21 = 0;
  v3 = CoCreateInstance(&CLSID_GlobalOptions, 0, 3u, &GUID_0000015b_0000_0000_c000_000000000046, &v21);
  v1 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
      (const char *)(unsigned int)v3,
      ppva);
    v4 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v1;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, 4, 8);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, v6, v7, (const char *)(unsigned int)v5, ppva);
  v8 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0x20u, 0);
  v1 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
      (const char *)(unsigned int)v8,
      ppvb);
    v9 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v1;
  }
  CurrentThreadId = GetCurrentThreadId();
  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::initOnceOutOfProc_,
    _lambda_7cb3f1da0a0e9a3a23678494bd451f36_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_140017D68 = 1;
  if ( !qword_140017D60 )
  {
    byte_140017D50 = 1;
    byte_140017D40 = 0;
    qword_140017D38 = (__int64)off_140011E38;
    dword_140017D48 = CurrentThreadId;
    qword_140017D60 = (__int64)&qword_140017D38;
  }
  v11 = Microsoft::WRL::Details::RegisterObjects<2>(&Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int>::instance_);
  v1 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
      (const char *)(unsigned int)v11,
      ppvb);
    v12 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v1;
  }
  v17 = &Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int>::instance_;
  memset(&Msg, 0, sizeof(Msg));
  while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
  {
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  v18 = 0;
  lambda_5f86a55444b1e573aae144ba352139f0_::operator()(&v17);
  CoUninitialize();
  v13 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d4f4  mov     [rsp-8+arg_8], rbx
0x14000d4f9  mov     [rsp-8+arg_10], rsi
0x14000d4fe  push    rbp
0x14000d4ff  lea     rbp, [rsp-57h]
0x14000d504  sub     rsp, 90h
0x14000d50b  xor     edx, edx; dwCoInit
0x14000d50d  xor     ecx, ecx; pvReserved
0x14000d50f  call    cs:__imp_CoInitializeEx
0x14000d515  mov     ebx, eax
0x14000d517  test    eax, eax
0x14000d519  jns     short loc_14000D53A
0x14000d51b  mov     rcx, [rbp+5Fh]; this
0x14000d51f  mov     r9d, eax; char *
0x14000d522  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000d529  mov     edx, 85h; void *
0x14000d52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d533  mov     eax, ebx
0x14000d535  jmp     loc_14000D771
0x14000d53a  mov     [rbp+57h+arg_0], 0
0x14000d542  lea     rax, [rbp+57h+arg_0]
0x14000d546  mov     [rsp+90h+ppv], rax; int
0x14000d54b  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000d552  mov     esi, 3
0x14000d557  mov     r8d, esi; dwClsContext
0x14000d55a  xor     edx, edx; pUnkOuter
0x14000d55c  lea     rcx, CLSID_GlobalOptions; rclsid
0x14000d563  call    cs:__imp_CoCreateInstance
0x14000d569  mov     ebx, eax
0x14000d56b  test    eax, eax
0x14000d56d  jns     short loc_14000D5A8
0x14000d56f  mov     rcx, [rbp+5Fh]; this
0x14000d573  mov     r9d, eax; char *
0x14000d576  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000d57d  mov     edx, 89h; void *
0x14000d582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d587  nop
0x14000d588  mov     rcx, [rbp+57h+arg_0]
0x14000d58c  test    rcx, rcx
0x14000d58f  jz      short loc_14000D5A6
0x14000d591  mov     [rbp+57h+arg_0], 0
0x14000d599  mov     rax, [rcx]
0x14000d59c  mov     rax, [rax+10h]
0x14000d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5a5  nop
0x14000d5a6  jmp     short loc_14000D533
0x14000d5a8  mov     rcx, [rbp+57h+arg_0]
0x14000d5ac  mov     rax, [rcx]
0x14000d5af  mov     edx, 4
0x14000d5b4  lea     r8d, [rdx+4]
0x14000d5b8  mov     rax, [rax+18h]
0x14000d5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5c1  mov     rcx, [rbp+5Fh]; this
0x14000d5c5  test    eax, eax
0x14000d5c7  jns     short loc_14000D5D1
0x14000d5c9  mov     r9d, eax; char *
0x14000d5cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000d5d1  mov     [rsp+90h+pReserved3], 0; pReserved3
0x14000d5da  mov     [rsp+90h+dwCapabilities], 20h ; ' '; dwCapabilities
0x14000d5e2  mov     [rsp+90h+pAuthList], 0; pAuthList
0x14000d5eb  mov     [rsp+90h+dwImpLevel], esi; dwImpLevel
0x14000d5ef  mov     dword ptr [rsp+90h+ppv], 0; int
0x14000d5f7  xor     r9d, r9d; pReserved1
0x14000d5fa  xor     r8d, r8d; asAuthSvc
0x14000d5fd  or      edx, 0FFFFFFFFh; cAuthSvc
0x14000d600  xor     ecx, ecx; pSecDesc
0x14000d602  call    cs:__imp_CoInitializeSecurity
0x14000d608  mov     ebx, eax
0x14000d60a  test    eax, eax
0x14000d60c  jns     short loc_14000D64A
0x14000d60e  mov     rcx, [rbp+5Fh]; this
0x14000d612  mov     r9d, eax; char *
0x14000d615  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000d61c  mov     edx, 8Dh; void *
0x14000d621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d626  nop
0x14000d627  mov     rcx, [rbp+57h+arg_0]
0x14000d62b  test    rcx, rcx
0x14000d62e  jz      short loc_14000D645
0x14000d630  mov     [rbp+57h+arg_0], 0
0x14000d638  mov     rax, [rcx]
0x14000d63b  mov     rax, [rax+10h]
0x14000d63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d644  nop
0x14000d645  jmp     loc_14000D533
0x14000d64a  call    cs:__imp_GetCurrentThreadId
0x14000d650  mov     ebx, eax
0x14000d652  xor     r9d, r9d; Context
0x14000d655  xor     r8d, r8d; Parameter
0x14000d658  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_7cb3f1da0a0e9a3a23678494bd451f36_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x14000d65f  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VMultipleUseOutOfProcModule@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x14000d666  call    cs:__imp_InitOnceExecuteOnce
0x14000d66c  mov     cs:byte_140017D68, 1
0x14000d673  cmp     cs:qword_140017D60, 0
0x14000d67b  jnz     short loc_14000D6AD
0x14000d67d  mov     cs:byte_140017D50, 1
0x14000d684  mov     cs:byte_140017D40, 0
0x14000d68b  lea     rax, off_140011E38
0x14000d692  mov     cs:qword_140017D38, rax
0x14000d699  mov     cs:dword_140017D48, ebx
0x14000d69f  lea     rax, qword_140017D38
0x14000d6a6  mov     cs:qword_140017D60, rax
0x14000d6ad  lea     rsi, ?instance_@?$StaticStorage@VMultipleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int> Microsoft::WRL::Details::StaticStorage<MultipleUseOutOfProcModule,1,int>::instance_
0x14000d6b4  mov     rcx, rsi
0x14000d6b7  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x14000d6bc  mov     ebx, eax
0x14000d6be  test    eax, eax
0x14000d6c0  jns     short loc_14000D6FE
0x14000d6c2  mov     rcx, [rbp+5Fh]; this
0x14000d6c6  mov     r9d, eax; char *
0x14000d6c9  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000d6d0  mov     edx, 93h; void *
0x14000d6d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d6da  nop
0x14000d6db  mov     rcx, [rbp+57h+arg_0]
0x14000d6df  test    rcx, rcx
0x14000d6e2  jz      short loc_14000D6F9
0x14000d6e4  mov     [rbp+57h+arg_0], 0
0x14000d6ec  mov     rax, [rcx]
0x14000d6ef  mov     rax, [rax+10h]
0x14000d6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6f8  nop
0x14000d6f9  jmp     loc_14000D533
0x14000d6fe  mov     [rbp+57h+var_40], rsi
0x14000d702  xorps   xmm0, xmm0
0x14000d705  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000d709  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000d70d  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000d711  jmp     short loc_14000D727
0x14000d713  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000d717  call    cs:__imp_TranslateMessage
0x14000d71d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000d721  call    cs:__imp_DispatchMessageW
0x14000d727  xor     r9d, r9d; wMsgFilterMax
0x14000d72a  xor     r8d, r8d; wMsgFilterMin
0x14000d72d  xor     edx, edx; hWnd
0x14000d72f  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000d733  call    cs:__imp_GetMessageW
0x14000d739  test    eax, eax
0x14000d73b  jg      short loc_14000D713
0x14000d73d  mov     [rbp+57h+var_38], 0
0x14000d741  lea     rcx, [rbp+57h+var_40]
0x14000d745  call    _lambda_5f86a55444b1e573aae144ba352139f0___operator__
0x14000d74a  call    cs:__imp_CoUninitialize
0x14000d750  nop
0x14000d751  mov     rcx, [rbp+57h+arg_0]
0x14000d755  test    rcx, rcx
0x14000d758  jz      short loc_14000D76F
0x14000d75a  mov     [rbp+57h+arg_0], 0
0x14000d762  mov     rax, [rcx]
0x14000d765  mov     rax, [rax+10h]
0x14000d769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d76e  nop
0x14000d76f  xor     eax, eax
0x14000d771  lea     r11, [rsp+90h+var_s0]
0x14000d779  mov     rbx, [r11+18h]
0x14000d77d  mov     rsi, [r11+20h]
0x14000d781  mov     rsp, r11
0x14000d784  pop     rbp
0x14000d785  retn
```
