# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::get_marshaler(void)

- ea: `0x180021c9c`
- end: `0x180021d7a`
- name: `?get_marshaler@marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@34@PEAPEAX@Z@CA?AU?$com_ptr@UIMarshal@impl@winrt@@@4@XZ`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021ddc`

## callees

- `0x180004b65`
- `0x180021c9c`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 *__fastcall `winrt::impl::make_marshaler'::`2'::marshaler::get_marshaler(__int64 *a1)
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
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x180021c9c  push    rbp
0x180021c9e  push    rbx
0x180021c9f  push    rsi
0x180021ca0  push    rdi
0x180021ca1  mov     rbp, rsp
0x180021ca4  sub     rsp, 28h
0x180021ca8  mov     rsi, rcx
0x180021cab  mov     dword ptr [rbp+ppunkMarshal], 0
0x180021cb2  xor     ecx, ecx; punkOuter
0x180021cb4  mov     [rbp+ppunkMarshal], 0
0x180021cbc  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x180021cc0  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x180021cc5  mov     rcx, [rbp+ppunkMarshal]
0x180021cc9  test    rcx, rcx
0x180021ccc  jz      short loc_180021CFF
0x180021cce  mov     rax, [rcx]
0x180021cd1  lea     r8, [rbp+arg_8]
0x180021cd5  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180021cdc  mov     [rbp+arg_8], 0
0x180021ce4  mov     rax, [rax]
0x180021ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cec  mov     rax, [rbp+arg_8]
0x180021cf0  lea     rcx, [rbp+arg_18]
0x180021cf4  mov     rbx, [rbp+arg_10]
0x180021cf8  mov     edi, 1
0x180021cfd  jmp     short loc_180021D0E
0x180021cff  xor     ebx, ebx
0x180021d01  lea     rcx, [rbp+arg_8]
0x180021d05  mov     [rbp+arg_10], rbx
0x180021d09  xor     eax, eax
0x180021d0b  lea     edi, [rbx+6]
0x180021d0e  mov     qword ptr [rcx], 0
0x180021d15  mov     [rsi], rax
0x180021d18  test    dil, 4
0x180021d1c  jz      short loc_180021D31
0x180021d1e  and     edi, 0FFFFFFFBh
0x180021d21  cmp     [rbp+arg_8], 0
0x180021d26  jz      short loc_180021D31
0x180021d28  lea     rcx, [rbp+arg_8]
0x180021d2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021d31  test    dil, 2
0x180021d35  jz      short loc_180021D48
0x180021d37  and     edi, 0FFFFFFFDh
0x180021d3a  test    rbx, rbx
0x180021d3d  jz      short loc_180021D48
0x180021d3f  lea     rcx, [rbp+arg_10]
0x180021d43  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021d48  test    dil, 1
0x180021d4c  jz      short loc_180021D5E
0x180021d4e  cmp     [rbp+arg_18], 0
0x180021d53  jz      short loc_180021D5E
0x180021d55  lea     rcx, [rbp+arg_18]
0x180021d59  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021d5e  cmp     [rbp+ppunkMarshal], 0
0x180021d63  jz      short loc_180021D6E
0x180021d65  lea     rcx, [rbp+ppunkMarshal]
0x180021d69  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021d6e  mov     rax, rsi
0x180021d71  add     rsp, 28h
0x180021d75  pop     rdi
0x180021d76  pop     rsi
0x180021d77  pop     rbx
0x180021d78  pop     rbp
0x180021d79  retn
```
