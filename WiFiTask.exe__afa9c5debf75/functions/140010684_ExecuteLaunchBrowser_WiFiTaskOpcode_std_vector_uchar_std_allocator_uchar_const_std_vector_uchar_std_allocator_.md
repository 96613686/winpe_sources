# ExecuteLaunchBrowser(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x140010684`
- end: `0x14001094e`
- name: `?ExecuteLaunchBrowser@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `714`
- prototype: `__int64 __fastcall(__int64, const WCHAR **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x1400016a0`
- `0x14000bf20`
- `0x1400100ec`
- `0x1400101f8`
- `0x140010684`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400106d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140010771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400107b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400106d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140010771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400107b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001070e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400107ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001070e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400107ef`

## string_xrefs

- `0x1400106cd`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ExecuteLaunchBrowser(__int64 a1, const WCHAR **a2)
{
  const WCHAR *v2; // rdi
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // ebx
  unsigned int v7; // r8d
  _QWORD *v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v22; // [rsp+20h] [rbp-50h] BYREF
  __int64 v23; // [rsp+28h] [rbp-48h] BYREF
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v25; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF

  v2 = *a2;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v25);
  if ( ActivationFactory >= 0 )
  {
    v8 = v25;
    v9 = *v25;
    v10 = -1;
    do
      ++v10;
    while ( v2[v10] );
    if ( v10 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v7);
      __debugbreak();
    }
    if ( (int)v10 + 1 < (unsigned int)v10 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v7);
      __debugbreak();
    }
    v11 = WindowsCreateStringReference(v2, v10, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v9 + 48))(v8, string, &v24);
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v14 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &string);
      if ( v14 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
        JUMPOUT(0x14001094DLL);
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v23);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 64LL))(
                              v23,
                              v24,
                              &v22);
        if ( ActivationFactory >= 0 )
          ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v22);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_003c317278e1391f2cb4b3afb958f2ba_Traceguids,
      (unsigned int)ActivationFactory);
  }
  if ( ActivationFactory < 0 )
  {
    if ( (ActivationFactory & 0x1FFF0000) == 0x70000 )
      ActivationFactory = (unsigned __int16)ActivationFactory;
  }
  else
  {
    ActivationFactory = 0;
  }
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x140010684  mov     [rsp-18h+arg_0], rbx
0x140010689  mov     [rsp-18h+arg_10], rsi
0x14001068e  push    rbp
0x14001068f  push    rdi
0x140010690  push    r14
0x140010692  mov     rbp, rsp
0x140010695  sub     rsp, 70h
0x140010699  mov     rax, cs:__security_cookie
0x1400106a0  xor     rax, rsp
0x1400106a3  mov     [rbp+var_10], rax
0x1400106a7  mov     rdi, [rdx]
0x1400106aa  xor     r14d, r14d
0x1400106ad  mov     [rbp+var_38], r14
0x1400106b1  mov     [rbp+var_40], r14
0x1400106b5  mov     [rbp+var_48], r14
0x1400106b9  mov     [rbp+var_50], r14
0x1400106bd  mov     [rbp+string], r14
0x1400106c1  lea     r9, [rbp+string]; string
0x1400106c5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400106c9  lea     edx, [r14+16h]; length
0x1400106cd  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1400106d4  call    cs:__imp_WindowsCreateStringReference
0x1400106da  test    eax, eax
0x1400106dc  js      loc_14001092B
0x1400106e2  mov     rbx, [rbp+string]
0x1400106e6  mov     rcx, [rbp+var_38]
0x1400106ea  test    rcx, rcx
0x1400106ed  jz      short loc_140010700
0x1400106ef  mov     [rbp+var_38], r14
0x1400106f3  mov     rax, [rcx]
0x1400106f6  mov     rax, [rax+10h]
0x1400106fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106ff  nop
0x140010700  lea     r8, [rbp+var_38]
0x140010704  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x14001070b  mov     rcx, rbx
0x14001070e  call    cs:__imp_RoGetActivationFactory
0x140010714  mov     ebx, eax
0x140010716  test    eax, eax
0x140010718  js      loc_140010844
0x14001071e  mov     rbx, [rbp+var_38]
0x140010722  mov     rsi, [rbx]
0x140010725  mov     rcx, [rbp+var_40]
0x140010729  test    rcx, rcx
0x14001072c  jz      short loc_14001073F
0x14001072e  mov     [rbp+var_40], r14
0x140010732  mov     rax, [rcx]
0x140010735  mov     rax, [rax+10h]
0x140010739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001073e  nop
0x14001073f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140010743  inc     rdx; int
0x140010746  cmp     [rdi+rdx*2], r14w
0x14001074b  jnz     short loc_140010743
0x14001074d  mov     eax, 0FFFFFFFFh
0x140010752  cmp     rdx, rax
0x140010755  ja      loc_140010920
0x14001075b  lea     eax, [rdx+1]
0x14001075e  cmp     eax, edx
0x140010760  jb      loc_140010933
0x140010766  lea     r9, [rbp+string]; string
0x14001076a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14001076e  mov     rcx, rdi; sourceString
0x140010771  call    cs:__imp_WindowsCreateStringReference
0x140010777  test    eax, eax
0x140010779  js      loc_14001093E
0x14001077f  lea     r8, [rbp+var_40]
0x140010783  mov     rdx, [rbp+string]
0x140010787  mov     rcx, rbx
0x14001078a  mov     rax, [rsi+30h]
0x14001078e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010793  mov     ebx, eax
0x140010795  test    eax, eax
0x140010797  js      loc_140010844
0x14001079d  mov     [rbp+string], r14
0x1400107a1  lea     r9, [rbp+string]; string
0x1400107a5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400107a9  mov     edx, 17h; length
0x1400107ae  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1400107b5  call    cs:__imp_WindowsCreateStringReference
0x1400107bb  test    eax, eax
0x1400107bd  js      loc_140010946
0x1400107c3  mov     rbx, [rbp+string]
0x1400107c7  mov     rcx, [rbp+var_48]
0x1400107cb  test    rcx, rcx
0x1400107ce  jz      short loc_1400107E1
0x1400107d0  mov     [rbp+var_48], r14
0x1400107d4  mov     rax, [rcx]
0x1400107d7  mov     rax, [rax+10h]
0x1400107db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107e0  nop
0x1400107e1  lea     r8, [rbp+var_48]
0x1400107e5  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x1400107ec  mov     rcx, rbx
0x1400107ef  call    cs:__imp_RoGetActivationFactory
0x1400107f5  mov     ebx, eax
0x1400107f7  test    eax, eax
0x1400107f9  js      short loc_140010844
0x1400107fb  mov     rbx, [rbp+var_48]
0x1400107ff  mov     rax, [rbx]
0x140010802  mov     rdi, [rax+40h]
0x140010806  mov     rcx, [rbp+var_50]
0x14001080a  test    rcx, rcx
0x14001080d  jz      short loc_140010820
0x14001080f  mov     [rbp+var_50], r14
0x140010813  mov     rdx, [rcx]
0x140010816  mov     rax, [rdx+10h]
0x14001081a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001081f  nop
0x140010820  lea     r8, [rbp+var_50]
0x140010824  mov     rdx, [rbp+var_40]
0x140010828  mov     rcx, rbx
0x14001082b  mov     rax, rdi
0x14001082e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010833  mov     ebx, eax
0x140010835  test    eax, eax
0x140010837  js      short loc_140010844
0x140010839  mov     rcx, [rbp+var_50]
0x14001083d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)
0x140010842  mov     ebx, eax
0x140010844  lea     rax, WPP_GLOBAL_Control
0x14001084b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010852  cmp     rcx, rax
0x140010855  jz      short loc_14001087B
0x140010857  cmp     byte ptr [rcx+19h], 4
0x14001085b  jb      short loc_14001087B
0x14001085d  test    byte ptr [rcx+1Ch], 1
0x140010861  jz      short loc_14001087B
0x140010863  mov     edx, 0Ah
0x140010868  mov     r9d, ebx
0x14001086b  lea     r8, WPP_003c317278e1391f2cb4b3afb958f2ba_Traceguids
0x140010872  mov     rcx, [rcx+10h]
0x140010876  call    WPP_SF_d
0x14001087b  test    ebx, ebx
0x14001087d  js      short loc_140010884
0x14001087f  mov     ebx, r14d
0x140010882  jmp     short loc_140010895
0x140010884  mov     eax, ebx
0x140010886  and     eax, 1FFF0000h
0x14001088b  cmp     eax, 70000h
0x140010890  jnz     short loc_140010895
0x140010892  movzx   ebx, bx
0x140010895  mov     rcx, [rbp+var_50]
0x140010899  test    rcx, rcx
0x14001089c  jz      short loc_1400108AF
0x14001089e  mov     [rbp+var_50], r14
0x1400108a2  mov     rax, [rcx]
0x1400108a5  mov     rax, [rax+10h]
0x1400108a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108ae  nop
0x1400108af  mov     rcx, [rbp+var_48]
0x1400108b3  test    rcx, rcx
0x1400108b6  jz      short loc_1400108C9
0x1400108b8  mov     [rbp+var_48], r14
0x1400108bc  mov     rax, [rcx]
0x1400108bf  mov     rax, [rax+10h]
0x1400108c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108c8  nop
0x1400108c9  mov     rcx, [rbp+var_40]
0x1400108cd  test    rcx, rcx
0x1400108d0  jz      short loc_1400108E3
0x1400108d2  mov     [rbp+var_40], r14
0x1400108d6  mov     rax, [rcx]
0x1400108d9  mov     rax, [rax+10h]
0x1400108dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108e2  nop
0x1400108e3  mov     rcx, [rbp+var_38]
0x1400108e7  test    rcx, rcx
0x1400108ea  jz      short loc_1400108FD
0x1400108ec  mov     [rbp+var_38], r14
0x1400108f0  mov     rdx, [rcx]
0x1400108f3  mov     rax, [rdx+10h]
0x1400108f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108fc  nop
0x1400108fd  mov     eax, ebx
0x1400108ff  mov     rcx, [rbp+var_10]
0x140010903  xor     rcx, rsp; StackCookie
0x140010906  call    __security_check_cookie
0x14001090b  lea     r11, [rsp+70h+var_s0]
0x140010910  mov     rbx, [r11+20h]
0x140010914  mov     rsi, [r11+30h]
0x140010918  mov     rsp, r11
0x14001091b  pop     r14
0x14001091d  pop     rdi
0x14001091e  pop     rbp
0x14001091f  retn
0x140010920  mov     ecx, 80070216h; this
0x140010925  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001092a  int     3; Trap to Debugger
0x14001092b  mov     ecx, eax; this
0x14001092d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140010932  int     3; Trap to Debugger
0x140010933  mov     ecx, 80070216h; this
0x140010938  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001093d  int     3; Trap to Debugger
0x14001093e  mov     ecx, eax; this
0x140010940  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140010945  int     3; Trap to Debugger
0x140010946  mov     ecx, eax; this
0x140010948  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
