# Microsoft::WRL::Details::ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_::_ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_

- ea: `0x180007264`
- end: `0x1800072e2`
- name: `Microsoft::WRL::Details::ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_::_ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007438`
- `0x180007900`

## callees

- `0x180007264`
- `0x18000f588`
- `0x180019010`

## pseudocode

```c
_UNKNOWN **__fastcall Microsoft::WRL::Details::ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_::_ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_(
        __int64 a1)
{
  __int64 v2; // rcx
  bool v3; // zf
  _UNKNOWN **result; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *(_QWORD *)(a1 + 104);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 104) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *(_DWORD *)(a1 + 16) == 0;
  result = &off_18001B648;
  *(_QWORD *)a1 = &off_18001B648;
  if ( v3 )
    result = (_UNKNOWN **)Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete(a1);
  v5 = *(_QWORD *)(a1 + 48);
  if ( v5 )
  {
    *(_QWORD *)(a1 + 48) = 0;
    result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    return (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180007264  push    rbx
0x180007266  sub     rsp, 20h
0x18000726a  mov     rbx, rcx
0x18000726d  mov     rcx, [rcx+68h]
0x180007271  test    rcx, rcx
0x180007274  jz      short loc_18000728A
0x180007276  mov     qword ptr [rbx+68h], 0
0x18000727e  mov     rax, [rcx]
0x180007281  mov     rax, [rax+10h]
0x180007285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728a  cmp     dword ptr [rbx+10h], 0
0x18000728e  lea     rax, off_18001B648
0x180007295  mov     [rbx], rax
0x180007298  jnz     short loc_1800072A2
0x18000729a  mov     rcx, rbx
0x18000729d  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TraceOperationComplete
0x1800072a2  mov     rcx, [rbx+30h]
0x1800072a6  test    rcx, rcx
0x1800072a9  jz      short loc_1800072BF
0x1800072ab  mov     qword ptr [rbx+30h], 0
0x1800072b3  mov     rax, [rcx]
0x1800072b6  mov     rax, [rax+10h]
0x1800072ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072bf  mov     rcx, [rbx+18h]
0x1800072c3  test    rcx, rcx
0x1800072c6  jz      short loc_1800072DC
0x1800072c8  mov     qword ptr [rbx+18h], 0
0x1800072d0  mov     rax, [rcx]
0x1800072d3  mov     rax, [rax+10h]
0x1800072d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072dc  add     rsp, 20h
0x1800072e0  pop     rbx
0x1800072e1  retn
```
