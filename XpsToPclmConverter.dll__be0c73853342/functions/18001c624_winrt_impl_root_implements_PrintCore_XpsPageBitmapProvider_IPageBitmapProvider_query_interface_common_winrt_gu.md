# winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::query_interface_common(winrt::guid const &,void * *)

- ea: `0x18001c624`
- end: `0x18001c6fb`
- name: `?query_interface_common@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c5bc`

## callees

- `0x18001b580`
- `0x18001c354`
- `0x18001c3f4`
- `0x18001c624`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::query_interface_common(
        __int64 (***a1)(void),
        _QWORD *a2,
        __int64 *a3)
{
  __int64 weak_ref; // rax
  __int64 v7; // rax
  __int64 (**v8)(void); // r9
  __int64 v9; // rax

  if ( *a2 == winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown> && a2[1] == 0x46000000000000C0LL )
    goto LABEL_3;
  if ( *a2 == winrt::impl::guid_v<winrt::impl::IWeakReferenceSource> && a2[1] == 0x46000000000000C0LL )
  {
    weak_ref = winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::make_weak_ref();
    *a3 = weak_ref;
    return weak_ref == 0 ? 0x8007000E : 0;
  }
  else
  {
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IAgileObject> && a2[1] == 0x905B8FCA64EEFFC0uLL )
    {
LABEL_3:
      *a3 = ((__int64 (__fastcall *)(__int64 (***)(void)))(*a1)[3])(a1);
      winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::AddRef(a1);
      return 0;
    }
    v7 = *a2 - winrt::impl::guid_v<winrt::impl::IMarshal>;
    if ( *a2 == winrt::impl::guid_v<winrt::impl::IMarshal> )
      v7 = a2[1] - 0x46000000000000C0LL;
    v8 = *a1;
    if ( v7 )
    {
      return (*v8)();
    }
    else
    {
      v9 = v8[3]();
      return winrt::impl::make_marshaler(v9, a3);
    }
  }
}

```

## disassembly

```asm
0x18001c624  mov     [rsp+arg_0], rbx
0x18001c629  push    rdi
0x18001c62a  sub     rsp, 20h
0x18001c62e  mov     rax, [rdx]
0x18001c631  mov     rdi, r8
0x18001c634  cmp     rax, cs:??$guid_v@UIUnknown@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUnknown>
0x18001c63b  mov     rbx, rcx
0x18001c63e  jnz     short loc_18001C66B
0x18001c640  mov     rax, [rdx+8]
0x18001c644  cmp     rax, cs:qword_180025C58
0x18001c64b  jnz     short loc_18001C66B
0x18001c64d  mov     rax, [rcx]
0x18001c650  mov     rax, [rax+18h]
0x18001c654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c659  mov     rcx, rbx
0x18001c65c  mov     [rdi], rax
0x18001c65f  call    ?AddRef@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::AddRef(void)
0x18001c664  xor     eax, eax
0x18001c666  jmp     loc_18001C6F0
0x18001c66b  mov     rax, [rdx]
0x18001c66e  cmp     rax, cs:??$guid_v@UIWeakReferenceSource@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IWeakReferenceSource>
0x18001c675  jnz     short loc_18001C69A
0x18001c677  mov     rax, [rdx+8]
0x18001c67b  cmp     rax, cs:qword_180025C28
0x18001c682  jnz     short loc_18001C69A
0x18001c684  call    ?make_weak_ref@?$root_implements@VXpsPageBitmapProvider@PrintCore@@UIPageBitmapProvider@@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<PrintCore::XpsPageBitmapProvider,IPageBitmapProvider>::make_weak_ref(void)
0x18001c689  mov     [rdi], rax
0x18001c68c  neg     rax
0x18001c68f  sbb     eax, eax
0x18001c691  not     eax
0x18001c693  and     eax, 8007000Eh
0x18001c698  jmp     short loc_18001C6F0
0x18001c69a  mov     rax, [rdx]
0x18001c69d  cmp     rax, cs:??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c6a4  jnz     short loc_18001C6B3
0x18001c6a6  mov     rax, [rdx+8]
0x18001c6aa  cmp     rax, cs:qword_180025C48
0x18001c6b1  jz      short loc_18001C64D
0x18001c6b3  mov     rax, [rdx]
0x18001c6b6  sub     rax, cs:??$guid_v@UIMarshal@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMarshal>
0x18001c6bd  jnz     short loc_18001C6CA
0x18001c6bf  mov     rax, [rdx+8]
0x18001c6c3  sub     rax, cs:qword_180025C38
0x18001c6ca  mov     r9, [rcx]
0x18001c6cd  test    rax, rax
0x18001c6d0  jnz     short loc_18001C6E8
0x18001c6d2  mov     rax, [r9+18h]
0x18001c6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6db  mov     rcx, rax
0x18001c6de  mov     rdx, rdi
0x18001c6e1  call    ?make_marshaler@impl@winrt@@YAHPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@12@PEAPEAX@Z; winrt::impl::make_marshaler(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,void * *)
0x18001c6e6  jmp     short loc_18001C6F0
0x18001c6e8  mov     rax, [r9]
0x18001c6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6f0  mov     rbx, [rsp+28h+arg_0]
0x18001c6f5  add     rsp, 20h
0x18001c6f9  pop     rdi
0x18001c6fa  retn
```
