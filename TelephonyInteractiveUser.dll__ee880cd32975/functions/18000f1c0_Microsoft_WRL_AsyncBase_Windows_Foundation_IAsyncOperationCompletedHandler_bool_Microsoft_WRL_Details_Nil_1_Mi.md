# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Start

- ea: `0x18000f1c0`
- end: `0x18000f2e9`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Start`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f6c`

## callees

- `0x18000e284`
- `0x18000f1c0`
- `0x18000f698`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f210`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f269`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f2b8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f2b8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Start(
        unsigned int *a1)
{
  int v2; // ebx
  unsigned int v3; // r8d
  __int64 v4; // rbp
  unsigned __int64 v5; // rdx
  __int64 v6; // rsi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  void (__fastcall *v10)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, unsigned int *, HSTRING, __int64); // rax
  GUID v12; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+68h] [rbp-30h] BYREF

  if ( (unsigned __int8)Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
                          a1,
                          0) )
  {
    v2 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v2 >= 0
      && InitOnceExecuteOnce(
           &Microsoft::WRL::gCausalityInitOnce,
           Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::InitCausality,
           0,
           0)
      && Microsoft::WRL::gCausality )
    {
      v4 = *(_QWORD *)Microsoft::WRL::gCausality;
      string = 0;
      v5 = -1;
      do
        ++v5;
      while ( sourceString[v5] );
      if ( v5 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, v3);
        __debugbreak();
      }
      if ( (int)v5 + 1 < (unsigned int)v5 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, v3);
        __debugbreak();
      }
      v6 = a1[16];
      v7 = WindowsCreateStringReference(
             L"Windows.Foundation.IAsyncOperation WindowsInternal.ApplicationModel.Calls.AppLauncher.LaunchForActiveCallAsync",
             v5,
             &hstringHeader,
             &string);
      if ( v7 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
        JUMPOUT(0x18000F2E8LL);
      }
      v10 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, unsigned int *, HSTRING, __int64))(v4 + 48);
      v12 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v10(Microsoft::WRL::gCausality, 0, 2, &v12, a1, string, v6);
    }
  }
  else
  {
    v2 = -2147483635;
    RoOriginateError(2147483661LL);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f1c0  push    rbx
0x18000f1c2  push    rbp
0x18000f1c3  push    rsi
0x18000f1c4  push    rdi
0x18000f1c5  push    r14
0x18000f1c7  sub     rsp, 70h
0x18000f1cb  xor     edx, edx
0x18000f1cd  mov     rdi, rcx
0x18000f1d0  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TransitionToState
0x18000f1d5  xor     r14d, r14d
0x18000f1d8  test    al, al
0x18000f1da  jz      loc_18000F2B1
0x18000f1e0  mov     rax, [rdi]
0x18000f1e3  mov     rcx, rdi
0x18000f1e6  mov     rax, [rax+88h]
0x18000f1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1f2  mov     ebx, eax
0x18000f1f4  test    eax, eax
0x18000f1f6  js      loc_18000F2BE
0x18000f1fc  xor     r9d, r9d; Context
0x18000f1ff  lea     rdx, Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____InitCausality; InitFn
0x18000f206  xor     r8d, r8d; Parameter
0x18000f209  lea     rcx, ?gCausalityInitOnce@WRL@Microsoft@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000f210  call    cs:__imp_InitOnceExecuteOnce
0x18000f216  test    eax, eax
0x18000f218  jz      loc_18000F2BE
0x18000f21e  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f225  test    rax, rax
0x18000f228  jz      loc_18000F2BE
0x18000f22e  mov     rbp, [rax]
0x18000f231  lea     rcx, sourceString; "Windows.Foundation.IAsyncOperation Wind"...
0x18000f238  mov     [rsp+98h+string], r14
0x18000f23d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f241  inc     rdx; int
0x18000f244  cmp     [rcx+rdx*2], r14w
0x18000f249  jnz     short loc_18000F241
0x18000f24b  mov     eax, 0FFFFFFFFh
0x18000f250  cmp     rdx, rax
0x18000f253  ja      short loc_18000F2CB
0x18000f255  lea     eax, [rdx+1]
0x18000f258  cmp     eax, edx
0x18000f25a  jb      short loc_18000F2D6
0x18000f25c  mov     esi, [rdi+40h]
0x18000f25f  lea     r9, [rsp+98h+string]; string
0x18000f264  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18000f269  call    cs:__imp_WindowsCreateStringReference
0x18000f26f  test    eax, eax
0x18000f271  js      short loc_18000F2E1
0x18000f273  mov     rcx, [rsp+98h+string]
0x18000f278  lea     r9, [rsp+98h+var_58]
0x18000f27d  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000f284  mov     rax, [rbp+30h]
0x18000f288  xor     edx, edx
0x18000f28a  mov     [rsp+98h+var_68], rsi
0x18000f28f  mov     [rsp+98h+var_70], rcx
0x18000f294  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f29b  lea     r8d, [rdx+2]
0x18000f29f  mov     [rsp+98h+var_78], rdi
0x18000f2a4  movdqu  [rsp+98h+var_58], xmm0
0x18000f2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2af  jmp     short loc_18000F2BE
0x18000f2b1  mov     ebx, 8000000Dh
0x18000f2b6  mov     ecx, ebx
0x18000f2b8  call    cs:__imp_RoOriginateError
0x18000f2be  mov     eax, ebx
0x18000f2c0  add     rsp, 70h
0x18000f2c4  pop     r14
0x18000f2c6  pop     rdi
0x18000f2c7  pop     rsi
0x18000f2c8  pop     rbp
0x18000f2c9  pop     rbx
0x18000f2ca  retn
0x18000f2cb  mov     ecx, 80070216h; this
0x18000f2d0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000f2d5  int     3; Trap to Debugger
0x18000f2d6  mov     ecx, 80070216h; this
0x18000f2db  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000f2e0  int     3; Trap to Debugger
0x18000f2e1  mov     ecx, eax; this
0x18000f2e3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
