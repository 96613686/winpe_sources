# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::get_marshaler(void)

- ea: `0x18001ee7c`
- end: `0x18001ef5a`
- name: `?get_marshaler@marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@34@PEAPEAX@Z@CA?AU?$com_ptr@UIMarshal@impl@winrt@@@4@XZ`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f560`

## callees

- `0x180003405`
- `0x18001ee7c`
- `0x1800215e8`
- `0x180024010`

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
0x18001ee7c  push    rbp
0x18001ee7e  push    rbx
0x18001ee7f  push    rsi
0x18001ee80  push    rdi
0x18001ee81  mov     rbp, rsp
0x18001ee84  sub     rsp, 28h
0x18001ee88  mov     rsi, rcx
0x18001ee8b  mov     dword ptr [rbp+ppunkMarshal], 0
0x18001ee92  xor     ecx, ecx; punkOuter
0x18001ee94  mov     [rbp+ppunkMarshal], 0
0x18001ee9c  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18001eea0  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x18001eea5  mov     rcx, [rbp+ppunkMarshal]
0x18001eea9  test    rcx, rcx
0x18001eeac  jz      short loc_18001EEDF
0x18001eeae  mov     rax, [rcx]
0x18001eeb1  lea     r8, [rbp+arg_8]
0x18001eeb5  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18001eebc  mov     [rbp+arg_8], 0
0x18001eec4  mov     rax, [rax]
0x18001eec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eecc  mov     rax, [rbp+arg_8]
0x18001eed0  lea     rcx, [rbp+arg_18]
0x18001eed4  mov     rbx, [rbp+arg_10]
0x18001eed8  mov     edi, 1
0x18001eedd  jmp     short loc_18001EEEE
0x18001eedf  xor     ebx, ebx
0x18001eee1  lea     rcx, [rbp+arg_8]
0x18001eee5  mov     [rbp+arg_10], rbx
0x18001eee9  xor     eax, eax
0x18001eeeb  lea     edi, [rbx+6]
0x18001eeee  mov     qword ptr [rcx], 0
0x18001eef5  mov     [rsi], rax
0x18001eef8  test    dil, 4
0x18001eefc  jz      short loc_18001EF11
0x18001eefe  and     edi, 0FFFFFFFBh
0x18001ef01  cmp     [rbp+arg_8], 0
0x18001ef06  jz      short loc_18001EF11
0x18001ef08  lea     rcx, [rbp+arg_8]
0x18001ef0c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ef11  test    dil, 2
0x18001ef15  jz      short loc_18001EF28
0x18001ef17  and     edi, 0FFFFFFFDh
0x18001ef1a  test    rbx, rbx
0x18001ef1d  jz      short loc_18001EF28
0x18001ef1f  lea     rcx, [rbp+arg_10]
0x18001ef23  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ef28  test    dil, 1
0x18001ef2c  jz      short loc_18001EF3E
0x18001ef2e  cmp     [rbp+arg_18], 0
0x18001ef33  jz      short loc_18001EF3E
0x18001ef35  lea     rcx, [rbp+arg_18]
0x18001ef39  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ef3e  cmp     [rbp+ppunkMarshal], 0
0x18001ef43  jz      short loc_18001EF4E
0x18001ef45  lea     rcx, [rbp+ppunkMarshal]
0x18001ef49  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ef4e  mov     rax, rsi
0x18001ef51  add     rsp, 28h
0x18001ef55  pop     rdi
0x18001ef56  pop     rsi
0x18001ef57  pop     rbx
0x18001ef58  pop     rbp
0x18001ef59  retn
```
