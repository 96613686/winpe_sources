# `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)

- ea: `0x18000ce6c`
- end: `0x18000cf9d`
- name: `??0marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@QEAA@0@Z`
- size: `305`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010120`
- `0x18001176c`
- `0x1800118bc`

## callees

- `0x180003b91`
- `0x18000ce6c`
- `0x180011e0c`
- `0x180013010`

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
0x18000ce6c  push    rbp
0x18000ce6e  push    rbx
0x18000ce6f  push    rsi
0x18000ce70  push    rdi
0x18000ce71  push    r14
0x18000ce73  push    r15
0x18000ce75  mov     rbp, rsp
0x18000ce78  sub     rsp, 28h
0x18000ce7c  mov     dword ptr [rbp+ppunkMarshal], 0
0x18000ce83  lea     r15, [rcx+8]
0x18000ce87  lea     rax, ??_7marshaler@?1??make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@PEAPEAX@Z@6B@; const `winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)'::`2'::marshaler::`vftable'
0x18000ce8e  mov     [rbp+ppunkMarshal], 0
0x18000ce96  mov     [rcx], rax
0x18000ce99  mov     rsi, rdx
0x18000ce9c  mov     r14, rcx
0x18000ce9f  mov     qword ptr [r15], 0
0x18000cea6  xor     ecx, ecx; punkOuter
0x18000cea8  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18000ceac  call    WINRT_IMPL_CoCreateFreeThreadedMarshaler
0x18000ceb1  mov     rcx, [rbp+ppunkMarshal]
0x18000ceb5  test    rcx, rcx
0x18000ceb8  jz      short loc_18000CEEB
0x18000ceba  mov     rax, [rcx]
0x18000cebd  lea     r8, [rbp+arg_8]
0x18000cec1  lea     rdx, ??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18000cec8  mov     [rbp+arg_8], 0
0x18000ced0  mov     rax, [rax]
0x18000ced3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced8  mov     rax, [rbp+arg_8]
0x18000cedc  lea     rcx, [rbp+arg_18]
0x18000cee0  mov     rbx, [rbp+arg_10]
0x18000cee4  mov     edi, 1
0x18000cee9  jmp     short loc_18000CEFA
0x18000ceeb  xor     ebx, ebx
0x18000ceed  lea     rcx, [rbp+arg_8]
0x18000cef1  mov     [rbp+arg_10], rbx
0x18000cef5  xor     eax, eax
0x18000cef7  lea     edi, [rbx+6]
0x18000cefa  mov     qword ptr [rcx], 0
0x18000cf01  mov     [r14+10h], rax
0x18000cf05  test    dil, 4
0x18000cf09  jz      short loc_18000CF1E
0x18000cf0b  and     edi, 0FFFFFFFBh
0x18000cf0e  cmp     [rbp+arg_8], 0
0x18000cf13  jz      short loc_18000CF1E
0x18000cf15  lea     rcx, [rbp+arg_8]
0x18000cf19  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cf1e  test    dil, 2
0x18000cf22  jz      short loc_18000CF35
0x18000cf24  and     edi, 0FFFFFFFDh
0x18000cf27  test    rbx, rbx
0x18000cf2a  jz      short loc_18000CF35
0x18000cf2c  lea     rcx, [rbp+arg_10]
0x18000cf30  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cf35  test    dil, 1
0x18000cf39  jz      short loc_18000CF4B
0x18000cf3b  cmp     [rbp+arg_18], 0
0x18000cf40  jz      short loc_18000CF4B
0x18000cf42  lea     rcx, [rbp+arg_18]
0x18000cf46  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cf4b  cmp     [rbp+ppunkMarshal], 0
0x18000cf50  jz      short loc_18000CF5B
0x18000cf52  lea     rcx, [rbp+ppunkMarshal]
0x18000cf56  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cf5b  mov     dword ptr [r14+18h], 1
0x18000cf63  cmp     [r15], rsi
0x18000cf66  jz      short loc_18000CF8D
0x18000cf68  cmp     qword ptr [r15], 0
0x18000cf6c  jz      short loc_18000CF76
0x18000cf6e  mov     rcx, r15
0x18000cf71  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000cf76  mov     [r15], rsi
0x18000cf79  test    rsi, rsi
0x18000cf7c  jz      short loc_18000CF8D
0x18000cf7e  mov     rax, [rsi]
0x18000cf81  mov     rcx, rsi
0x18000cf84  mov     rax, [rax+8]
0x18000cf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf8d  mov     rax, r14
0x18000cf90  add     rsp, 28h
0x18000cf94  pop     r15
0x18000cf96  pop     r14
0x18000cf98  pop     rdi
0x18000cf99  pop     rsi
0x18000cf9a  pop     rbx
0x18000cf9b  pop     rbp
0x18000cf9c  retn
```
