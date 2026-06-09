# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke

- ea: `0x180017310`
- end: `0x18001741c`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017310`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800173da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800173da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke(
        __int64 a1,
        __int64 *a2,
        int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64 *, __int64 *); // rbp
  __int64 *v9; // rdi
  __int64 v10; // rcx
  int (__fastcall *v11)(__int64 *, GUID *, __int64 *); // rdi
  __int64 v12; // rcx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  v14 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64 *))(*a2 + 8))(a2);
    v6 = v14;
  }
  v7 = *a2;
  if ( a3 == 1 )
  {
    v8 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 64);
    v9 = *(__int64 **)(a1 + 24);
    v10 = *v9;
    if ( *v9 )
    {
      *v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    **(_DWORD **)(a1 + 32) = v8(a2, v9);
  }
  else
  {
    v11 = *(int (__fastcall **)(__int64 *, GUID *, __int64 *))v7;
    if ( v6 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    if ( v11(a2, &GUID_00000036_0000_0000_c000_000000000046, &v14) >= 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, *(_QWORD *)(a1 + 32));
  }
  SetEvent(**(HANDLE **)(a1 + 16));
  (*(void (__fastcall **)(__int64 *))(*a2 + 16))(a2);
  v12 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180017310  push    rbx
0x180017312  push    rbp
0x180017313  push    rsi
0x180017314  push    rdi
0x180017315  sub     rsp, 28h
0x180017319  mov     edi, r8d
0x18001731c  mov     rbx, rdx
0x18001731f  mov     rsi, rcx
0x180017322  xor     ecx, ecx
0x180017324  mov     [rsp+48h+arg_0], rcx
0x180017329  test    rdx, rdx
0x18001732c  jz      short loc_180017342
0x18001732e  mov     rax, [rdx]
0x180017331  mov     rcx, rdx
0x180017334  mov     rax, [rax+8]
0x180017338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001733d  mov     rcx, [rsp+48h+arg_0]
0x180017342  mov     rax, [rbx]
0x180017345  cmp     edi, 1
0x180017348  jnz     short loc_180017384
0x18001734a  mov     rbp, [rax+40h]
0x18001734e  mov     rdi, [rsi+18h]
0x180017352  mov     rcx, [rdi]
0x180017355  test    rcx, rcx
0x180017358  jz      short loc_18001736E
0x18001735a  mov     qword ptr [rdi], 0
0x180017361  mov     r8, [rcx]
0x180017364  mov     rax, [r8+10h]
0x180017368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001736d  nop
0x18001736e  mov     rdx, rdi
0x180017371  mov     rcx, rbx
0x180017374  mov     rax, rbp
0x180017377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001737c  mov     rcx, [rsi+20h]
0x180017380  mov     [rcx], eax
0x180017382  jmp     short loc_1800173D3
0x180017384  mov     rdi, [rax]
0x180017387  test    rcx, rcx
0x18001738a  jz      short loc_1800173A2
0x18001738c  mov     [rsp+48h+arg_0], 0
0x180017395  mov     rdx, [rcx]
0x180017398  mov     rax, [rdx+10h]
0x18001739c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173a1  nop
0x1800173a2  lea     r8, [rsp+48h+arg_0]
0x1800173a7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800173ae  mov     rcx, rbx
0x1800173b1  mov     rax, rdi
0x1800173b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b9  nop
0x1800173ba  test    eax, eax
0x1800173bc  js      short loc_1800173D3
0x1800173be  mov     rcx, [rsp+48h+arg_0]
0x1800173c3  mov     rax, [rcx]
0x1800173c6  mov     rdx, [rsi+20h]
0x1800173ca  mov     rax, [rax+40h]
0x1800173ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173d3  mov     rcx, [rsi+10h]
0x1800173d7  mov     rcx, [rcx]; hEvent
0x1800173da  call    cs:__imp_SetEvent
0x1800173e0  nop
0x1800173e1  mov     rax, [rbx]
0x1800173e4  mov     rcx, rbx
0x1800173e7  mov     rax, [rax+10h]
0x1800173eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173f0  nop
0x1800173f1  mov     rcx, [rsp+48h+arg_0]
0x1800173f6  test    rcx, rcx
0x1800173f9  jz      short loc_180017411
0x1800173fb  mov     [rsp+48h+arg_0], 0
0x180017404  mov     rax, [rcx]
0x180017407  mov     rax, [rax+10h]
0x18001740b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017410  nop
0x180017411  xor     eax, eax
0x180017413  add     rsp, 28h
0x180017417  pop     rdi
0x180017418  pop     rsi
0x180017419  pop     rbp
0x18001741a  pop     rbx
0x18001741b  retn
```
