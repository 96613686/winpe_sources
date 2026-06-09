# `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::RunInContext<`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)'::`2'::_lambda_1_>(`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::operator()(tagComCallData *)

- ea: `0x1800114e4`
- end: `0x18001165f`
- name: `??R_lambda_1_@?1???$RunInContext@V_lambda_1_@?1???0?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ@@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAX$$QEAV0?1???0123@QEAA@XZ@@Z@QEBAJPEAUtagComCallData@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ff60`

## callees

- `0x180002250`
- `0x180002274`
- `0x180002d60`
- `0x180002e00`
- `0x180007a54`
- `0x180007d44`
- `0x180010300`
- `0x1800114e4`
- `0x180011c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011609`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115c0`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800115f5`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800115f5`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x1800115cb`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x1800115cb`

## string_xrefs

- `0x18001159f`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
__int64 __fastcall __R_lambda_1___1____RunInContext_V_lambda_1___1___0__svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__QEAA_XZ____svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAX__QEAV0_1___0123_QEAA_XZ__Z_QEBAJPEAUtagComCallData___Z(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v3; // edx
  struct winrt::impl::shared_hstring_header *v4; // rbx
  void *v5; // rdi
  int v6; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rdi
  __int64 v9; // rsi
  DWORD LastError; // ebx
  int v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 result; // rax
  __int64 v15; // [rsp+0h] [rbp-68h] BYREF
  __int64 (__fastcall *v16)(); // [rsp+20h] [rbp-48h] BYREF
  struct winrt::impl::shared_hstring_header *v17; // [rsp+28h] [rbp-40h] BYREF
  int v18; // [rsp+30h] [rbp-38h] BYREF
  const char *v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h]
  LPVOID lpMem; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v2 = **(_QWORD **)(a2 + 8);
    lpMem = 0;
    __builtin_array_init_helper_eh<winrt::hstring>(&lpMem);
    v17 = 0;
    v16 = 0;
    v4 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x3E, v3);
    memcpy_s((char *)v4 + 28, 0x7Cu, L"Windows.Internal.AggregatedDataPlatform.AggregatedDataPlatform", 0x7Cu);
    v5 = lpMem;
    if ( lpMem )
    {
      v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v6 )
      {
        if ( v6 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v5);
      }
    }
    lpMem = v4;
    v17 = v4;
    v16 = `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::populate_winrt_runtime_classes_helper<0>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    v18 = 310;
    v19 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
    v20 = 0;
    v8 = (_QWORD *)(v2 + 8);
    v9 = *(_QWORD *)(v2 + 8);
    if ( v9 )
    {
      LastError = GetLastError();
      RoRevokeActivationFactories(v9);
      SetLastError(LastError);
    }
    *v8 = 0;
    v11 = ((__int64 (__fastcall *)(struct winrt::impl::shared_hstring_header **, __int64 (__fastcall **)(), __int64, _QWORD *))RoRegisterActivationFactories)(
            &v17,
            &v16,
            1,
            v8);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, &v18);
    `eh vector destructor iterator'(&lpMem, 8u, 1u, (void (*)(void *))winrt::hstring::~hstring);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v15, v12, v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800114e4  mov     r11, rsp
0x1800114e7  mov     [r11+8], rbx
0x1800114eb  mov     [r11+18h], rsi
0x1800114ef  push    rdi
0x1800114f0  sub     rsp, 60h
0x1800114f4  mov     rax, cs:__security_cookie
0x1800114fb  xor     rax, rsp
0x1800114fe  mov     [rsp+68h+var_18], rax
0x180011503  mov     rax, [rdx+8]
0x180011507  mov     rsi, [rax]
0x18001150a  mov     qword ptr [r11-20h], 0
0x180011512  lea     rcx, [r11-20h]
0x180011516  call    ??$__builtin_array_init_helper_eh@Uhstring@winrt@@@@YAXPEAUhstring@winrt@@_KP6AXPEAX@Z@Z; __builtin_array_init_helper_eh<winrt::hstring>(winrt::hstring *,unsigned __int64,void (*)(void *))
0x18001151b  nop
0x18001151c  mov     [rsp+68h+var_40], 0
0x180011525  mov     [rsp+68h+var_48], 0
0x18001152e  mov     ecx, 3Eh ; '>'; this
0x180011533  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180011538  mov     rbx, rax
0x18001153b  lea     rcx, [rax+1Ch]; Destination
0x18001153f  mov     edx, 7Ch ; '|'; DestinationSize
0x180011544  mov     r9d, edx; SourceSize
0x180011547  lea     r8, aWindowsInterna_1; "Windows.Internal.AggregatedDataPlatform"...
0x18001154e  call    memcpy_s
0x180011553  mov     rdi, [rsp+68h+lpMem]
0x180011558  test    rdi, rdi
0x18001155b  jz      short loc_180011581
0x18001155d  or      eax, 0FFFFFFFFh
0x180011560  lock xadd [rdi+18h], eax
0x180011565  sub     eax, 1
0x180011568  jnz     loc_180011601
0x18001156e  nop
0x18001156f  call    WINRT_IMPL_GetProcessHeap
0x180011574  mov     rcx, rax; hHeap
0x180011577  mov     r8, rdi; lpMem
0x18001157a  xor     edx, edx; dwFlags
0x18001157c  call    WINRT_IMPL_HeapFree
0x180011581  mov     [rsp+68h+lpMem], rbx
0x180011586  mov     [rsp+68h+var_40], rbx
0x18001158b  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$populate_winrt_runtime_classes_helper@$0A@@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAXAEAV?$array@Uhstring@winrt@@$00@std@@AEAV?$array@PEAUHSTRING__@@$00@6@AEAV?$array@P6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z$00@6@@Z@SAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::populate_winrt_runtime_classes_helper<0>(std::array<winrt::hstring,1> &,std::array<HSTRING__ *,1> &,std::array<long (*)(HSTRING__ *,IActivationFactory * *),1> &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(HSTRING__ *,IActivationFactory * *)
0x180011592  mov     [rsp+68h+var_48], rax
0x180011597  mov     [rsp+68h+var_38], 136h
0x18001159f  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x1800115a6  mov     [rsp+68h+var_30], rax
0x1800115ab  mov     [rsp+68h+var_28], 0
0x1800115b4  lea     rdi, [rsi+8]
0x1800115b8  mov     rsi, [rdi]
0x1800115bb  test    rsi, rsi
0x1800115be  jz      short loc_1800115D9
0x1800115c0  call    cs:__imp_GetLastError
0x1800115c6  mov     ebx, eax
0x1800115c8  mov     rcx, rsi
0x1800115cb  call    cs:__imp_RoRevokeActivationFactories
0x1800115d1  mov     ecx, ebx; dwErrCode
0x1800115d3  call    cs:__imp_SetLastError
0x1800115d9  mov     qword ptr [rdi], 0
0x1800115e0  mov     r9, rdi
0x1800115e3  mov     ebx, 1
0x1800115e8  mov     r8d, ebx
0x1800115eb  lea     rdx, [rsp+68h+var_48]
0x1800115f0  lea     rcx, [rsp+68h+var_40]
0x1800115f5  call    cs:__imp_RoRegisterActivationFactories
0x1800115fb  test    eax, eax
0x1800115fd  js      short loc_180011651
0x1800115ff  jmp     short loc_180011610
0x180011601  test    eax, eax
0x180011603  jns     loc_180011581
0x180011609  call    cs:__imp_abort
0x180011610  lea     r9, ??1hstring@winrt@@QEAA@XZ; void (*)(void *)
0x180011617  mov     r8, rbx; unsigned __int64
0x18001161a  mov     edx, 8; unsigned __int64
0x18001161f  lea     rcx, [rsp+68h+lpMem]; void *
0x180011624  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011629  nop
0x18001162a  xor     eax, eax
0x18001162c  jmp     short loc_180011632
0x18001162e  mov     eax, dword ptr [rsp+68h+lpMem]
0x180011632  mov     rcx, [rsp+68h+var_18]
0x180011637  xor     rcx, rsp; StackCookie
0x18001163a  call    __security_check_cookie
0x18001163f  lea     r11, [rsp+68h+var_8]
0x180011644  mov     rbx, [r11+10h]
0x180011648  mov     rsi, [r11+20h]
0x18001164c  mov     rsp, r11
0x18001164f  pop     rdi
0x180011650  retn
0x180011651  lea     rdx, [rsp+68h+var_38]
0x180011656  mov     ecx, eax
0x180011658  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
