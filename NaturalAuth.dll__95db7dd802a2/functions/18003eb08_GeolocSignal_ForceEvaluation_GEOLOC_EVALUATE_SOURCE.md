# GeolocSignal::ForceEvaluation(_GEOLOC_EVALUATE_SOURCE)

- ea: `0x18003eb08`
- end: `0x18003ec32`
- name: `?ForceEvaluation@GeolocSignal@@QEAAXW4_GEOLOC_EVALUATE_SOURCE@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e118`
- `0x18003eac4`

## callees

- `0x18000a7d0`
- `0x180014e7c`
- `0x18003dcd0`
- `0x18003e060`
- `0x18003e39c`
- `0x18003eb08`
- `0x18003f210`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003eb7b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003eb7b`

## string_xrefs

- `0x18003ebd7`: `asyncOperation->put_Completed(completionHandler.Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GeolocSignal::ForceEvaluation(__int64 a1, int a2)
{
  _lambda_31049d99e5e4b12cd8f83d421dddc1a7_ *v3; // rax
  signed __int8 v4; // al
  char v5; // tt
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64, __int64); // rbx
  int v8; // eax
  const char *v9; // rcx
  _BYTE v11[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v12[48]; // [rsp+50h] [rbp-30h] BYREF
  bool v13; // [rsp+B0h] [rbp+30h] BYREF
  int v14; // [rsp+B8h] [rbp+38h] BYREF
  int v15; // [rsp+C0h] [rbp+40h] BYREF

  v14 = a2;
  v15 = 0;
  v13 = 0;
  v3 = _lambda_31049d99e5e4b12cd8f83d421dddc1a7_::_lambda_31049d99e5e4b12cd8f83d421dddc1a7_(
         (_lambda_31049d99e5e4b12cd8f83d421dddc1a7_ *)v11,
         &v15,
         (enum _GEOLOC_EVALUATE_SOURCE *)&v14,
         (struct GeolocSignal *)a1,
         &v13);
  wil::ScopeExit<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(v12, v3);
  v5 = v13;
  v4 = _InterlockedCompareExchange8((volatile signed __int8 *)(a1 + 80), 1, v13);
  if ( v5 != v4 )
  {
    v13 = v4;
    return wil::details::ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>::~ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(v12);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 88);
  ResetEvent(*(HANDLE *)(a1 + 48));
  v6 = *(_QWORD *)(a1 + 72);
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v6 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 88);
  v8 = v7(v6, 3000000000LL, 600000000, a1 + 88);
  v15 = v8;
  if ( v8 < 0 )
  {
    v9 = "locator->GetGeopositionAsyncWithAgeAndTimeout(GeolocationMaximumAge, GeolocationTimeout, &asyncOperation)";
LABEL_7:
    LogError(v9, (unsigned int)v8);
    *(_BYTE *)(a1 + 80) = 0;
    return wil::details::ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>::~ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(v12);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 88) + 48LL))(
         *(_QWORD *)(a1 + 88),
         *(_QWORD *)(a1 + 96));
  v15 = v8;
  if ( v8 < 0 )
  {
    v9 = "asyncOperation->put_Completed(completionHandler.Get())";
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d7a34c12d6d033c41d405f6d74c18c9b_Traceguids);
  return wil::details::ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>::~ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(v12);
}

```

## disassembly

```asm
0x18003eb08  mov     [rsp-28h+arg_8], edx
0x18003eb0c  push    rbp
0x18003eb0d  push    rbx
0x18003eb0e  push    rsi
0x18003eb0f  push    rdi
0x18003eb10  push    r14
0x18003eb12  mov     rbp, rsp
0x18003eb15  sub     rsp, 80h
0x18003eb1c  mov     rsi, rcx
0x18003eb1f  mov     [rbp+arg_10], 0
0x18003eb26  mov     [rbp+arg_0], 0
0x18003eb2a  lea     rax, [rbp+arg_0]
0x18003eb2e  mov     [rsp+80h+var_60], rax; bool *
0x18003eb33  mov     r9, rcx; struct GeolocSignal *
0x18003eb36  lea     r8, [rbp+arg_8]; enum _GEOLOC_EVALUATE_SOURCE *
0x18003eb3a  lea     rdx, [rbp+arg_10]; int *
0x18003eb3e  lea     rcx, [rbp+var_50]; this
0x18003eb42  call    ??0_lambda_31049d99e5e4b12cd8f83d421dddc1a7_@@QEAA@AEAJAEAW4_GEOLOC_EVALUATE_SOURCE@@PEAVGeolocSignal@@AEA_N@Z; _lambda_31049d99e5e4b12cd8f83d421dddc1a7_::_lambda_31049d99e5e4b12cd8f83d421dddc1a7_(long &,_GEOLOC_EVALUATE_SOURCE &,GeolocSignal *,bool &)
0x18003eb47  mov     rdx, rax
0x18003eb4a  lea     rcx, [rbp+var_30]
0x18003eb4e  call    ??$ScopeExit@V_lambda_31049d99e5e4b12cd8f83d421dddc1a7_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_31049d99e5e4b12cd8f83d421dddc1a7_@@@details@0@$$QEAV_lambda_31049d99e5e4b12cd8f83d421dddc1a7_@@@Z; wil::ScopeExit<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(_lambda_31049d99e5e4b12cd8f83d421dddc1a7_ &&)
0x18003eb53  nop
0x18003eb54  mov     ecx, 1
0x18003eb59  mov     al, [rbp+arg_0]
0x18003eb5c  lock cmpxchg [rsi+50h], cl
0x18003eb61  jz      short loc_18003EB6B
0x18003eb63  mov     [rbp+arg_0], al
0x18003eb66  jmp     loc_18003EC1B
0x18003eb6b  lea     r14, [rsi+58h]
0x18003eb6f  mov     rcx, r14
0x18003eb72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eb77  mov     rcx, [rsi+30h]; hEvent
0x18003eb7b  call    cs:__imp_ResetEvent
0x18003eb81  mov     rdi, [rsi+48h]
0x18003eb85  mov     rax, [rdi]
0x18003eb88  mov     rbx, [rax+70h]
0x18003eb8c  mov     rcx, r14
0x18003eb8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eb94  mov     edx, 0B2D05E00h
0x18003eb99  mov     r9, r14
0x18003eb9c  mov     r8d, 23C34600h
0x18003eba2  mov     rcx, rdi
0x18003eba5  mov     rax, rbx
0x18003eba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebad  mov     [rbp+arg_10], eax
0x18003ebb0  test    eax, eax
0x18003ebb2  jns     short loc_18003EBBD
0x18003ebb4  lea     rcx, aLocatorGetgeop; "locator->GetGeopositionAsyncWithAgeAndT"...
0x18003ebbb  jmp     short loc_18003EBDE
0x18003ebbd  mov     rcx, [r14]
0x18003ebc0  mov     rax, [rcx]
0x18003ebc3  mov     rdx, [rsi+60h]
0x18003ebc7  mov     rax, [rax+30h]
0x18003ebcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebd0  mov     [rbp+arg_10], eax
0x18003ebd3  test    eax, eax
0x18003ebd5  jns     short loc_18003EBEC
0x18003ebd7  lea     rcx, aAsyncoperation_0; "asyncOperation->put_Completed(completio"...
0x18003ebde  mov     edx, eax
0x18003ebe0  call    LogError
0x18003ebe5  xor     eax, eax
0x18003ebe7  xchg    al, [rsi+50h]
0x18003ebea  jmp     short loc_18003EC1B
0x18003ebec  lea     rax, WPP_GLOBAL_Control
0x18003ebf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ebfa  cmp     rcx, rax
0x18003ebfd  jz      short loc_18003EC1B
0x18003ebff  test    byte ptr [rcx+1Ch], 4
0x18003ec03  jz      short loc_18003EC1B
0x18003ec05  mov     edx, 0Ch
0x18003ec0a  lea     r8, WPP_d7a34c12d6d033c41d405f6d74c18c9b_Traceguids
0x18003ec11  mov     rcx, [rcx+10h]
0x18003ec15  call    WPP_SF_
0x18003ec1a  nop
0x18003ec1b  lea     rcx, [rbp+var_30]
0x18003ec1f  call    ??1?$ScopeExitFn@V_lambda_31049d99e5e4b12cd8f83d421dddc1a7_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>::~ScopeExitFn<_lambda_31049d99e5e4b12cd8f83d421dddc1a7_>(void)
0x18003ec24  add     rsp, 80h
0x18003ec2b  pop     r14
0x18003ec2d  pop     rdi
0x18003ec2e  pop     rsi
0x18003ec2f  pop     rbx
0x18003ec30  pop     rbp
0x18003ec31  retn
```
