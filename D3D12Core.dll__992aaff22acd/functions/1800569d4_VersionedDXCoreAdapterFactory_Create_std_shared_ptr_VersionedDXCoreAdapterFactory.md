# VersionedDXCoreAdapterFactory::Create(std::shared_ptr<VersionedDXCoreAdapterFactory> &)

- ea: `0x1800569d4`
- end: `0x180056ac7`
- name: `?Create@VersionedDXCoreAdapterFactory@@SAJAEAV?$shared_ptr@VVersionedDXCoreAdapterFactory@@@std@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800567c8`

## callees

- `0x180003c84`
- `0x18000ab50`
- `0x18000b920`
- `0x1800569d4`
- `0x180056ad0`
- `0x1800bde58`
- `0x180262020`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x1800569fd`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180056aa4`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x1800569fd`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180056aa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VersionedDXCoreAdapterFactory::Create(_QWORD *a1)
{
  int v2; // ebx
  void *v3; // rax
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rax
  void *v7; // [rsp+48h] [rbp+28h] BYREF
  __int64 v8; // [rsp+50h] [rbp+30h] BYREF
  __int64 v9; // [rsp+58h] [rbp+38h] BYREF

  v9 = 0;
  v8 = 0;
  v2 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v9);
  if ( v2 == -2147467262 )
  {
    v7 = 0;
    v2 = DXCoreCreateAdapterFactory(&GUID_e4212a94_d660_480e_82b3_006e050a44c0, &v7);
    if ( v2 >= 0 )
      ATL::CComPtr<Redist_19H1::IDXCoreAdapterFactory>::operator=<Redist_19H1::IDXCoreAdapterFactory_Internal>(&v8, &v7);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v7);
  }
  if ( v2 >= 0 )
  {
    v3 = operator new(0x20u);
    v7 = v3;
    v4 = v3
       ? std::_Ref_count_obj2<VersionedDXCoreAdapterFactory>::_Ref_count_obj2<VersionedDXCoreAdapterFactory>(
           v3,
           &v9,
           &v8)
       : 0LL;
    *a1 = v4 + 16;
    v5 = (std::_Ref_count_base *)a1[1];
    a1[1] = v4;
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800569d4  push    rbp
0x1800569d6  push    rbx
0x1800569d7  push    rdi
0x1800569d8  mov     rbp, rsp
0x1800569db  sub     rsp, 20h
0x1800569df  mov     rdi, rcx
0x1800569e2  mov     [rbp+arg_18], 0
0x1800569ea  mov     [rbp+arg_10], 0
0x1800569f2  lea     rdx, [rbp+arg_18]
0x1800569f6  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x1800569fd  call    cs:__imp_DXCoreCreateAdapterFactory
0x180056a03  mov     ebx, eax
0x180056a05  cmp     eax, 80004002h
0x180056a0a  jz      loc_180056A91
0x180056a10  test    ebx, ebx
0x180056a12  js      short loc_180056A57
0x180056a14  mov     ecx, 20h ; ' '; dwBytes
0x180056a19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056a1e  mov     [rbp+arg_8], rax
0x180056a22  test    rax, rax
0x180056a25  jz      short loc_180056A8D
0x180056a27  lea     r8, [rbp+arg_10]
0x180056a2b  lea     rdx, [rbp+arg_18]
0x180056a2f  mov     rcx, rax
0x180056a32  call    ??$?0AEAV?$CComPtr@UIDXCoreAdapterFactory@@@ATL@@AEAV?$CComPtr@UIDXCoreAdapterFactory@Redist_19H1@@@1@@?$_Ref_count_obj2@VVersionedDXCoreAdapterFactory@@@std@@QEAA@AEAV?$CComPtr@UIDXCoreAdapterFactory@@@ATL@@AEAV?$CComPtr@UIDXCoreAdapterFactory@Redist_19H1@@@3@@Z; std::_Ref_count_obj2<VersionedDXCoreAdapterFactory>::_Ref_count_obj2<VersionedDXCoreAdapterFactory>(ATL::CComPtr<IDXCoreAdapterFactory> &,ATL::CComPtr<Redist_19H1::IDXCoreAdapterFactory> &)
0x180056a37  mov     rcx, rax
0x180056a3a  lea     rax, [rcx+10h]
0x180056a3e  mov     [rdi], rax
0x180056a41  mov     rax, [rdi+8]
0x180056a45  mov     [rdi+8], rcx
0x180056a49  test    rax, rax
0x180056a4c  jz      short loc_180056A57
0x180056a4e  mov     rcx, rax; this
0x180056a51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056a56  nop
0x180056a57  mov     rcx, [rbp+arg_10]
0x180056a5b  test    rcx, rcx
0x180056a5e  jz      short loc_180056A6D
0x180056a60  mov     rax, [rcx]
0x180056a63  mov     rax, [rax+10h]
0x180056a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a6c  nop
0x180056a6d  mov     rcx, [rbp+arg_18]
0x180056a71  test    rcx, rcx
0x180056a74  jz      short loc_180056A83
0x180056a76  mov     rax, [rcx]
0x180056a79  mov     rax, [rax+10h]
0x180056a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a82  nop
0x180056a83  mov     eax, ebx
0x180056a85  add     rsp, 20h
0x180056a89  pop     rdi
0x180056a8a  pop     rbx
0x180056a8b  pop     rbp
0x180056a8c  retn
0x180056a8d  xor     ecx, ecx
0x180056a8f  jmp     short loc_180056A3A
0x180056a91  mov     [rbp+arg_8], 0
0x180056a99  lea     rdx, [rbp+arg_8]
0x180056a9d  lea     rcx, _GUID_e4212a94_d660_480e_82b3_006e050a44c0
0x180056aa4  call    cs:__imp_DXCoreCreateAdapterFactory
0x180056aaa  mov     ebx, eax
0x180056aac  test    eax, eax
0x180056aae  js      loc_1802354C6
0x180056ab4  lea     rdx, [rbp+arg_8]
0x180056ab8  lea     rcx, [rbp+arg_10]
0x180056abc  call    ??$?4UIDXCoreAdapterFactory_Internal@Redist_19H1@@@?$CComPtr@UIDXCoreAdapterFactory@Redist_19H1@@@ATL@@QEAAPEAUIDXCoreAdapterFactory@Redist_19H1@@AEBV?$CComPtr@UIDXCoreAdapterFactory_Internal@Redist_19H1@@@1@@Z; ATL::CComPtr<Redist_19H1::IDXCoreAdapterFactory>::operator=<Redist_19H1::IDXCoreAdapterFactory_Internal>(ATL::CComPtr<Redist_19H1::IDXCoreAdapterFactory_Internal> const &)
0x180056ac1  nop
0x180056ac2  jmp     loc_1802354C6
0x1802354c6  lea     rcx, [rbp+arg_8]
0x1802354ca  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1802354cf  nop
0x1802354d0  jmp     loc_180056A10
```
