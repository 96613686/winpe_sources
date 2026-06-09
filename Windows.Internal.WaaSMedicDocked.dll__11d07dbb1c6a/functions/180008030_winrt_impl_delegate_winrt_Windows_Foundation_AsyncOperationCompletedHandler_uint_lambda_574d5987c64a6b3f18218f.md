# winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::Invoke(void *,int)

- ea: `0x180008030`
- end: `0x1800080c4`
- name: `?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@V_lambda_574d5987c64a6b3f18218f4a51f47ca3_@@@impl@winrt@@UEAAHPEAXH@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008030`
- `0x180009c90`
- `0x18000a014`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::Invoke(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v6; // rdx
  int v7; // [rsp+20h] [rbp-28h]
  __int128 v8; // [rsp+28h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = 0;
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 16) + 24LL))(
    *(_QWORD *)(a1 + 16),
    a1 + 24,
    &v9);
  v7 = 0;
  v8 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, a2, a3) < 0 )
  {
    try
    {
      winrt::throw_hresult();
    }
    catch ( ... )
    {
      *(_DWORD *)(v6 + 80) = *(_DWORD *)winrt::to_hresult(&v9);
      return (unsigned int)v9;
    }
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return 0;
}

```

## disassembly

```asm
0x180008030  mov     [rsp+arg_8], rbx
0x180008035  push    rdi
0x180008036  sub     rsp, 40h
0x18000803a  mov     ebx, r8d
0x18000803d  mov     rdi, rdx
0x180008040  mov     rdx, rcx
0x180008043  mov     [rsp+48h+arg_0], 0
0x18000804c  mov     rcx, [rcx+10h]
0x180008050  mov     rax, [rcx]
0x180008053  add     rdx, 18h
0x180008057  lea     r8, [rsp+48h+arg_0]
0x18000805c  mov     rax, [rax+18h]
0x180008060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008065  mov     [rsp+48h+var_28], 0
0x18000806d  xorps   xmm0, xmm0
0x180008070  movdqu  [rsp+48h+var_20], xmm0
0x180008076  mov     rcx, [rsp+48h+arg_0]
0x18000807b  mov     rax, [rcx]
0x18000807e  mov     r8d, ebx
0x180008081  mov     rdx, rdi
0x180008084  mov     rax, [rax+18h]
0x180008088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808d  test    eax, eax
0x18000808f  js      short loc_1800080B6
0x180008091  cmp     [rsp+48h+arg_0], 0
0x180008097  jz      short loc_1800080A3
0x180008099  lea     rcx, [rsp+48h+arg_0]
0x18000809e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800080a3  xor     eax, eax
0x1800080a5  jmp     short loc_1800080AB
0x1800080a7  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800080ab  mov     rbx, [rsp+48h+arg_8]
0x1800080b0  add     rsp, 40h
0x1800080b4  pop     rdi
0x1800080b5  retn
0x1800080b6  lea     rdx, [rsp+48h+var_28]
0x1800080bb  mov     ecx, eax
0x1800080bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
