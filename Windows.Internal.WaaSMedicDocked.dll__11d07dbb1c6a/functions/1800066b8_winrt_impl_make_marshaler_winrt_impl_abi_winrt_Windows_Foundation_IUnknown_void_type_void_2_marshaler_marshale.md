# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)

- ea: `0x1800066b8`
- end: `0x1800067e9`
- name: `??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z`
- size: `305`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008bf0`
- `0x1800098e8`
- `0x1800099b8`

## callees

- `0x180002115`
- `0x1800066b8`
- `0x18000a014`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall `winrt::impl::make_marshaler'::`2'::marshaler::marshaler(__int64 a1, __int64 a2)
{
  __int64 *v2; // r15
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rbx
  char v9; // di
  LPUNKNOWN ppunkMarshal; // [rsp+60h] [rbp+38h] BYREF
  __int64 v12; // [rsp+68h] [rbp+40h] BYREF
  __int64 v13; // [rsp+70h] [rbp+48h] BYREF
  __int64 v14; // [rsp+78h] [rbp+50h] BYREF

  v2 = (__int64 *)(a1 + 8);
  ppunkMarshal = 0;
  *(_QWORD *)a1 = `winrt::impl::make_marshaler'::`2'::marshaler::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  WINRT_IMPL_CoCreateFreeThreadedMarshaler(0, &ppunkMarshal);
  if ( ppunkMarshal )
  {
    lpVtbl = ppunkMarshal->lpVtbl;
    v12 = 0;
    ((void (__fastcall *)(LPUNKNOWN, __int64 *, __int64 *))lpVtbl->QueryInterface)(
      ppunkMarshal,
      &winrt::impl::guid_v<winrt::impl::IMarshal>,
      &v12);
    v6 = v12;
    v7 = &v14;
    v8 = v13;
    v9 = 1;
  }
  else
  {
    v8 = 0;
    v7 = &v12;
    v13 = 0;
    v6 = 0;
    v9 = 6;
  }
  *v7 = 0;
  *(_QWORD *)(a1 + 16) = v6;
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    if ( v12 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  }
  if ( (v9 & 1) != 0 && v14 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  if ( ppunkMarshal )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&ppunkMarshal);
  *(_DWORD *)(a1 + 24) = 1;
  if ( *v2 != a2 )
  {
    if ( *v2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
    *v2 = a2;
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  }
  return a1;
}

```

## disassembly

```asm
0x1800066b8  push    rbp
0x1800066ba  push    rbx
0x1800066bb  push    rsi
0x1800066bc  push    rdi
0x1800066bd  push    r14
0x1800066bf  push    r15
0x1800066c1  mov     rbp, rsp
0x1800066c4  sub     rsp, 28h
0x1800066c8  mov     dword ptr [rbp+ppunkMarshal], 0
0x1800066cf  lea     r15, [rcx+8]
0x1800066d3  lea     rax, ??_7marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@6B@; const `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::`vftable'
0x1800066da  mov     [rbp+ppunkMarshal], 0
0x1800066e2  mov     [rcx], rax
0x1800066e5  mov     rsi, rdx
0x1800066e8  mov     r14, rcx
0x1800066eb  mov     qword ptr [r15], 0
0x1800066f2  xor     ecx, ecx; punkOuter
0x1800066f4  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x1800066f8  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x1800066fd  mov     rcx, [rbp+ppunkMarshal]
0x180006701  test    rcx, rcx
0x180006704  jz      short loc_180006737
0x180006706  mov     rax, [rcx]
0x180006709  lea     r8, [rbp+arg_8]
0x18000670d  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x180006714  mov     [rbp+arg_8], 0
0x18000671c  mov     rax, [rax]
0x18000671f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006724  mov     rax, [rbp+arg_8]
0x180006728  lea     rcx, [rbp+arg_18]
0x18000672c  mov     rbx, [rbp+arg_10]
0x180006730  mov     edi, 1
0x180006735  jmp     short loc_180006746
0x180006737  xor     ebx, ebx
0x180006739  lea     rcx, [rbp+arg_8]
0x18000673d  mov     [rbp+arg_10], rbx
0x180006741  xor     eax, eax
0x180006743  lea     edi, [rbx+6]
0x180006746  mov     qword ptr [rcx], 0
0x18000674d  mov     [r14+10h], rax
0x180006751  test    dil, 4
0x180006755  jz      short loc_18000676A
0x180006757  and     edi, 0FFFFFFFBh
0x18000675a  cmp     [rbp+arg_8], 0
0x18000675f  jz      short loc_18000676A
0x180006761  lea     rcx, [rbp+arg_8]
0x180006765  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000676a  test    dil, 2
0x18000676e  jz      short loc_180006781
0x180006770  and     edi, 0FFFFFFFDh
0x180006773  test    rbx, rbx
0x180006776  jz      short loc_180006781
0x180006778  lea     rcx, [rbp+arg_10]
0x18000677c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006781  test    dil, 1
0x180006785  jz      short loc_180006797
0x180006787  cmp     [rbp+arg_18], 0
0x18000678c  jz      short loc_180006797
0x18000678e  lea     rcx, [rbp+arg_18]
0x180006792  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006797  cmp     [rbp+ppunkMarshal], 0
0x18000679c  jz      short loc_1800067A7
0x18000679e  lea     rcx, [rbp+ppunkMarshal]
0x1800067a2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800067a7  mov     dword ptr [r14+18h], 1
0x1800067af  cmp     [r15], rsi
0x1800067b2  jz      short loc_1800067D9
0x1800067b4  cmp     qword ptr [r15], 0
0x1800067b8  jz      short loc_1800067C2
0x1800067ba  mov     rcx, r15
0x1800067bd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800067c2  mov     [r15], rsi
0x1800067c5  test    rsi, rsi
0x1800067c8  jz      short loc_1800067D9
0x1800067ca  mov     rax, [rsi]
0x1800067cd  mov     rcx, rsi
0x1800067d0  mov     rax, [rax+8]
0x1800067d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d9  mov     rax, r14
0x1800067dc  add     rsp, 28h
0x1800067e0  pop     r15
0x1800067e2  pop     r14
0x1800067e4  pop     rdi
0x1800067e5  pop     rsi
0x1800067e6  pop     rbx
0x1800067e7  pop     rbp
0x1800067e8  retn
```
