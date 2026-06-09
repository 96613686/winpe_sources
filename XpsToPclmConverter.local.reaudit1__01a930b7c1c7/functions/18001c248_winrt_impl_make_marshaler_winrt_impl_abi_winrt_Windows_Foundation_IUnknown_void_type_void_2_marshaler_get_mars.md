# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::get_marshaler(void)

- ea: `0x18001c248`
- end: `0x18001c326`
- name: `?get_marshaler@marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@34@PEAPEAX@Z@CA?AU?$com_ptr@UIMarshal@impl@winrt@@@4@XZ`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c354`

## callees

- `0x180007769`
- `0x18001c248`
- `0x18001c790`
- `0x18001f010`

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
0x18001c248  push    rbp
0x18001c24a  push    rbx
0x18001c24b  push    rsi
0x18001c24c  push    rdi
0x18001c24d  mov     rbp, rsp
0x18001c250  sub     rsp, 28h
0x18001c254  mov     rsi, rcx
0x18001c257  mov     dword ptr [rbp+ppunkMarshal], 0
0x18001c25e  xor     ecx, ecx; punkOuter
0x18001c260  mov     [rbp+ppunkMarshal], 0
0x18001c268  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18001c26c  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x18001c271  mov     rcx, [rbp+ppunkMarshal]
0x18001c275  test    rcx, rcx
0x18001c278  jz      short loc_18001C2AB
0x18001c27a  mov     rax, [rcx]
0x18001c27d  lea     r8, [rbp+arg_8]
0x18001c281  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18001c288  mov     [rbp+arg_8], 0
0x18001c290  mov     rax, [rax]
0x18001c293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c298  mov     rax, [rbp+arg_8]
0x18001c29c  lea     rcx, [rbp+arg_18]
0x18001c2a0  mov     rbx, [rbp+arg_10]
0x18001c2a4  mov     edi, 1
0x18001c2a9  jmp     short loc_18001C2BA
0x18001c2ab  xor     ebx, ebx
0x18001c2ad  lea     rcx, [rbp+arg_8]
0x18001c2b1  mov     [rbp+arg_10], rbx
0x18001c2b5  xor     eax, eax
0x18001c2b7  lea     edi, [rbx+6]
0x18001c2ba  mov     qword ptr [rcx], 0
0x18001c2c1  mov     [rsi], rax
0x18001c2c4  test    dil, 4
0x18001c2c8  jz      short loc_18001C2DD
0x18001c2ca  and     edi, 0FFFFFFFBh
0x18001c2cd  cmp     [rbp+arg_8], 0
0x18001c2d2  jz      short loc_18001C2DD
0x18001c2d4  lea     rcx, [rbp+arg_8]
0x18001c2d8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c2dd  test    dil, 2
0x18001c2e1  jz      short loc_18001C2F4
0x18001c2e3  and     edi, 0FFFFFFFDh
0x18001c2e6  test    rbx, rbx
0x18001c2e9  jz      short loc_18001C2F4
0x18001c2eb  lea     rcx, [rbp+arg_10]
0x18001c2ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c2f4  test    dil, 1
0x18001c2f8  jz      short loc_18001C30A
0x18001c2fa  cmp     [rbp+arg_18], 0
0x18001c2ff  jz      short loc_18001C30A
0x18001c301  lea     rcx, [rbp+arg_18]
0x18001c305  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c30a  cmp     [rbp+ppunkMarshal], 0
0x18001c30f  jz      short loc_18001C31A
0x18001c311  lea     rcx, [rbp+ppunkMarshal]
0x18001c315  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c31a  mov     rax, rsi
0x18001c31d  add     rsp, 28h
0x18001c321  pop     rdi
0x18001c322  pop     rsi
0x18001c323  pop     rbx
0x18001c324  pop     rbp
0x18001c325  retn
```
