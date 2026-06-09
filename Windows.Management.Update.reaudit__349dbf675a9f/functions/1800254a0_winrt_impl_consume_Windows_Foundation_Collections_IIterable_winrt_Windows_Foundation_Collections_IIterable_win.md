# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)

- ea: `0x1800254a0`
- end: `0x180025546`
- name: `?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024e9c`
- `0x1800250f0`

## callees

- `0x180017c3c`
- `0x18001e7a4`
- `0x1800254a0`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v3; // rcx
  signed int v4; // eax
  __int64 v5; // r8
  __int64 v6; // rdi
  signed int v7; // eax
  __int64 v8; // r8
  unsigned int v10; // [rsp+28h] [rbp-18h] BYREF
  __int128 v11; // [rsp+30h] [rbp-10h]
  char v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v3 = *a1;
  v10 = 0;
  v11 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v13);
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v10, v5);
  v6 = v13;
  v14 = v13;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 56LL))(v13, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult(v7, &v10, v8);
  if ( v12 )
  {
    *a2 = v6;
  }
  else
  {
    *a2 = 0;
    if ( v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  }
  return a2;
}

```

## disassembly

```asm
0x1800254a0  push    rbp
0x1800254a2  push    rbx
0x1800254a3  push    rdi
0x1800254a4  mov     rbp, rsp
0x1800254a7  sub     rsp, 40h
0x1800254ab  mov     rbx, rdx
0x1800254ae  and     [rbp+arg_10], 0
0x1800254b3  mov     rcx, [rcx]
0x1800254b6  and     [rbp+var_18], 0
0x1800254ba  xorps   xmm0, xmm0
0x1800254bd  movdqu  [rbp+var_10], xmm0
0x1800254c2  mov     rax, [rcx]
0x1800254c5  lea     rdx, [rbp+arg_10]
0x1800254c9  mov     rax, [rax+30h]
0x1800254cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d2  test    eax, eax
0x1800254d4  js      short loc_18002553A
0x1800254d6  mov     rdi, [rbp+arg_10]
0x1800254da  mov     [rbp+arg_18], rdi
0x1800254de  mov     [rbp+arg_0], 0
0x1800254e2  and     [rbp+var_18], 0
0x1800254e6  xorps   xmm0, xmm0
0x1800254e9  movdqu  [rbp+var_10], xmm0
0x1800254ee  mov     rax, [rdi]
0x1800254f1  lea     rdx, [rbp+arg_0]
0x1800254f5  mov     rcx, rdi
0x1800254f8  mov     rax, [rax+38h]
0x1800254fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025501  test    eax, eax
0x180025503  js      short loc_18002552E
0x180025505  cmp     [rbp+arg_0], 0
0x180025509  jnz     short loc_18002551F
0x18002550b  and     qword ptr [rbx], 0
0x18002550f  test    rdi, rdi
0x180025512  jz      short loc_180025522
0x180025514  lea     rcx, [rbp+arg_18]
0x180025518  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002551d  jmp     short loc_180025522
0x18002551f  mov     [rbx], rdi
0x180025522  mov     rax, rbx
0x180025525  add     rsp, 40h
0x180025529  pop     rdi
0x18002552a  pop     rbx
0x18002552b  pop     rbp
0x18002552c  retn
0x18002552e  lea     rdx, [rbp+var_18]
0x180025532  mov     ecx, eax
0x180025534  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002553a  lea     rdx, [rbp+var_18]
0x18002553e  mov     ecx, eax
0x180025540  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
