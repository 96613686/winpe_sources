# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke

- ea: `0x180017830`
- end: `0x180017943`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_80fc5ebc6c75ae438d12ab94b57c3bb1___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017830`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800178fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800178fa`

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
0x180017830  push    rbx
0x180017832  push    rbp
0x180017833  push    rsi
0x180017834  push    rdi
0x180017835  sub     rsp, 28h
0x180017839  mov     edi, r8d
0x18001783c  mov     rbx, rdx
0x18001783f  mov     rsi, rcx
0x180017842  xor     ecx, ecx
0x180017844  mov     [rsp+48h+arg_0], rcx
0x180017849  test    rdx, rdx
0x18001784c  jz      short loc_180017862
0x18001784e  mov     rax, [rdx]
0x180017851  mov     rcx, rdx
0x180017854  mov     rax, [rax+8]
0x180017858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785d  mov     rcx, [rsp+48h+arg_0]
0x180017862  mov     rax, [rbx]
0x180017865  cmp     edi, 1
0x180017868  jnz     short loc_1800178A4
0x18001786a  mov     rbp, [rax+40h]
0x18001786e  mov     rdi, [rsi+18h]
0x180017872  mov     rcx, [rdi]
0x180017875  test    rcx, rcx
0x180017878  jz      short loc_18001788E
0x18001787a  mov     qword ptr [rdi], 0
0x180017881  mov     r8, [rcx]
0x180017884  mov     rax, [r8+10h]
0x180017888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001788d  nop
0x18001788e  mov     rdx, rdi
0x180017891  mov     rcx, rbx
0x180017894  mov     rax, rbp
0x180017897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001789c  mov     rcx, [rsi+20h]
0x1800178a0  mov     [rcx], eax
0x1800178a2  jmp     short loc_1800178F3
0x1800178a4  mov     rdi, [rax]
0x1800178a7  test    rcx, rcx
0x1800178aa  jz      short loc_1800178C2
0x1800178ac  mov     [rsp+48h+arg_0], 0
0x1800178b5  mov     rdx, [rcx]
0x1800178b8  mov     rax, [rdx+10h]
0x1800178bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178c1  nop
0x1800178c2  lea     r8, [rsp+48h+arg_0]
0x1800178c7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800178ce  mov     rcx, rbx
0x1800178d1  mov     rax, rdi
0x1800178d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178d9  nop
0x1800178da  test    eax, eax
0x1800178dc  js      short loc_1800178F3
0x1800178de  mov     rcx, [rsp+48h+arg_0]
0x1800178e3  mov     rax, [rcx]
0x1800178e6  mov     rdx, [rsi+20h]
0x1800178ea  mov     rax, [rax+40h]
0x1800178ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f3  mov     rcx, [rsi+10h]
0x1800178f7  mov     rcx, [rcx]; hEvent
0x1800178fa  call    cs:__imp_SetEvent
0x180017901  nop     dword ptr [rax+rax+00h]
0x180017906  nop
0x180017907  mov     rax, [rbx]
0x18001790a  mov     rcx, rbx
0x18001790d  mov     rax, [rax+10h]
0x180017911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017916  nop
0x180017917  mov     rcx, [rsp+48h+arg_0]
0x18001791c  test    rcx, rcx
0x18001791f  jz      short loc_180017937
0x180017921  mov     [rsp+48h+arg_0], 0
0x18001792a  mov     rax, [rcx]
0x18001792d  mov     rax, [rax+10h]
0x180017931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017936  nop
0x180017937  xor     eax, eax
0x180017939  add     rsp, 28h
0x18001793d  pop     rdi
0x18001793e  pop     rsi
0x18001793f  pop     rbp
0x180017940  pop     rbx
0x180017941  retn
```
