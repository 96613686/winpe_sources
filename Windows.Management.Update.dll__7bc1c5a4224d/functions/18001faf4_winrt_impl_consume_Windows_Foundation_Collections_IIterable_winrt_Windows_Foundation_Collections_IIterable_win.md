# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(void)

- ea: `0x18001faf4`
- end: `0x18001fbb4`
- name: `?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UWindowsSoftwareUpdate@Update@Management@45@@impl@winrt@@QEBA@XZ`
- size: `192`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e414`
- `0x180023c04`
- `0x180023e54`

## callees

- `0x180016fe4`
- `0x18001d50c`
- `0x18001faf4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Management::Update::WindowsSoftwareUpdate>::begin(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rdi
  int v6; // eax
  int v8; // [rsp+28h] [rbp-18h] BYREF
  __int128 v9; // [rsp+30h] [rbp-10h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v10 = 0;
  v3 = *a1;
  v8 = 0;
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v10);
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v8);
  v5 = v10;
  v11 = v10;
  LOBYTE(v10) = 0;
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 56LL))(v11, &v10);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v8);
  if ( (_BYTE)v10 )
  {
    *a2 = v5;
  }
  else
  {
    *a2 = 0;
    if ( v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  }
  return a2;
}

```

## disassembly

```asm
0x18001faf4  mov     [rsp-8+arg_8], rbx
0x18001faf9  mov     [rsp-8+arg_18], rdi
0x18001fafe  push    rbp
0x18001faff  mov     rbp, rsp
0x18001fb02  sub     rsp, 40h
0x18001fb06  mov     rbx, rdx
0x18001fb09  mov     [rbp+arg_0], 0
0x18001fb11  mov     rcx, [rcx]
0x18001fb14  mov     [rbp+var_18], 0
0x18001fb1b  xorps   xmm0, xmm0
0x18001fb1e  movdqu  [rbp+var_10], xmm0
0x18001fb23  mov     rax, [rcx]
0x18001fb26  lea     rdx, [rbp+arg_0]
0x18001fb2a  mov     rax, [rax+30h]
0x18001fb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb33  test    eax, eax
0x18001fb35  js      short loc_18001FBA8
0x18001fb37  mov     rdi, [rbp+arg_0]
0x18001fb3b  mov     [rbp+arg_10], rdi
0x18001fb3f  mov     byte ptr [rbp+arg_0], 0
0x18001fb43  mov     [rbp+var_18], 0
0x18001fb4a  xorps   xmm0, xmm0
0x18001fb4d  movdqu  [rbp+var_10], xmm0
0x18001fb52  mov     rax, [rdi]
0x18001fb55  lea     rdx, [rbp+arg_0]
0x18001fb59  mov     rcx, rdi
0x18001fb5c  mov     rax, [rax+38h]
0x18001fb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb65  test    eax, eax
0x18001fb67  js      short loc_18001FB9C
0x18001fb69  cmp     byte ptr [rbp+arg_0], 0
0x18001fb6d  jnz     short loc_18001FB86
0x18001fb6f  mov     qword ptr [rbx], 0
0x18001fb76  test    rdi, rdi
0x18001fb79  jz      short loc_18001FB89
0x18001fb7b  lea     rcx, [rbp+arg_10]
0x18001fb7f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fb84  jmp     short loc_18001FB89
0x18001fb86  mov     [rbx], rdi
0x18001fb89  mov     rax, rbx
0x18001fb8c  mov     rbx, [rsp+40h+arg_8]
0x18001fb91  mov     rdi, [rsp+40h+arg_18]
0x18001fb96  add     rsp, 40h
0x18001fb9a  pop     rbp
0x18001fb9b  retn
0x18001fb9c  lea     rdx, [rbp+var_18]
0x18001fba0  mov     ecx, eax
0x18001fba2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001fba8  lea     rdx, [rbp+var_18]
0x18001fbac  mov     ecx, eax
0x18001fbae  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
