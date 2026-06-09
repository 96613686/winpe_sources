# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::get_marshaler(void)

- ea: `0x18000f77c`
- end: `0x18000f85a`
- name: `?get_marshaler@marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@34@PEAPEAX@Z@CA?AU?$com_ptr@UIMarshal@impl@winrt@@@4@XZ`
- size: `222`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f8bc`

## callees

- `0x1800034c5`
- `0x18000750c`
- `0x18000f77c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall `winrt::impl::make_marshaler'::`2'::marshaler::get_marshaler(_QWORD *a1)
{
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v3; // rax
  __int64 *v4; // rcx
  __int64 v5; // rbx
  char v6; // di
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+28h] BYREF
  __int64 v9; // [rsp+58h] [rbp+30h] BYREF
  __int64 v10; // [rsp+60h] [rbp+38h] BYREF
  __int64 v11; // [rsp+68h] [rbp+40h] BYREF

  ppunkMarshal = 0;
  WINRT_IMPL_CoCreateFreeThreadedMarshaler(0, &ppunkMarshal);
  if ( ppunkMarshal )
  {
    lpVtbl = ppunkMarshal->lpVtbl;
    v9 = 0;
    ((void (__fastcall *)(LPUNKNOWN, __int64 *, __int64 *))lpVtbl->QueryInterface)(
      ppunkMarshal,
      &winrt::impl::guid_v<winrt::impl::IMarshal>,
      &v9);
    v3 = v9;
    v4 = &v11;
    v5 = v10;
    v6 = 1;
  }
  else
  {
    v5 = 0;
    v4 = &v9;
    v10 = 0;
    v3 = 0;
    v6 = 6;
  }
  *v4 = 0;
  *a1 = v3;
  if ( (v6 & 4) != 0 )
  {
    v6 &= ~4u;
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  }
  if ( (v6 & 1) != 0 && v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  if ( ppunkMarshal )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x18000f77c  push    rbp
0x18000f77e  push    rbx
0x18000f77f  push    rsi
0x18000f780  push    rdi
0x18000f781  mov     rbp, rsp
0x18000f784  sub     rsp, 28h
0x18000f788  mov     rsi, rcx
0x18000f78b  mov     dword ptr [rbp+ppunkMarshal], 0
0x18000f792  xor     ecx, ecx; punkOuter
0x18000f794  mov     [rbp+ppunkMarshal], 0
0x18000f79c  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18000f7a0  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x18000f7a5  mov     rcx, [rbp+ppunkMarshal]
0x18000f7a9  test    rcx, rcx
0x18000f7ac  jz      short loc_18000F7DF
0x18000f7ae  mov     rax, [rcx]
0x18000f7b1  lea     r8, [rbp+arg_8]
0x18000f7b5  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000f7bc  mov     [rbp+arg_8], 0
0x18000f7c4  mov     rax, [rax]
0x18000f7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7cc  mov     rax, [rbp+arg_8]
0x18000f7d0  lea     rcx, [rbp+arg_18]
0x18000f7d4  mov     rbx, [rbp+arg_10]
0x18000f7d8  mov     edi, 1
0x18000f7dd  jmp     short loc_18000F7EE
0x18000f7df  xor     ebx, ebx
0x18000f7e1  lea     rcx, [rbp+arg_8]
0x18000f7e5  mov     [rbp+arg_10], rbx
0x18000f7e9  xor     eax, eax
0x18000f7eb  lea     edi, [rbx+6]
0x18000f7ee  mov     qword ptr [rcx], 0
0x18000f7f5  mov     [rsi], rax
0x18000f7f8  test    dil, 4
0x18000f7fc  jz      short loc_18000F811
0x18000f7fe  and     edi, 0FFFFFFFBh
0x18000f801  cmp     [rbp+arg_8], 0
0x18000f806  jz      short loc_18000F811
0x18000f808  lea     rcx, [rbp+arg_8]
0x18000f80c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f811  test    dil, 2
0x18000f815  jz      short loc_18000F828
0x18000f817  and     edi, 0FFFFFFFDh
0x18000f81a  test    rbx, rbx
0x18000f81d  jz      short loc_18000F828
0x18000f81f  lea     rcx, [rbp+arg_10]
0x18000f823  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f828  test    dil, 1
0x18000f82c  jz      short loc_18000F83E
0x18000f82e  cmp     [rbp+arg_18], 0
0x18000f833  jz      short loc_18000F83E
0x18000f835  lea     rcx, [rbp+arg_18]
0x18000f839  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f83e  cmp     [rbp+ppunkMarshal], 0
0x18000f843  jz      short loc_18000F84E
0x18000f845  lea     rcx, [rbp+ppunkMarshal]
0x18000f849  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f84e  mov     rax, rsi
0x18000f851  add     rsp, 28h
0x18000f855  pop     rdi
0x18000f856  pop     rsi
0x18000f857  pop     rbx
0x18000f858  pop     rbp
0x18000f859  retn
```
