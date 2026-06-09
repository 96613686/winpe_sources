# CloudStoreItemName_CreateInstance(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180057f20`
- end: `0x1800580ea`
- name: `?CloudStoreItemName_CreateInstance@@YA?AV?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG000@Z`
- size: `458`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005e4a0`
- `0x18006504c`

## callees

- `0x180057f20`
- `0x1800580f0`
- `0x180058314`
- `0x180101fc0`
- `0x1801236bc`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005807b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005808c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800580ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005807b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005808c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800580ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CloudStoreItemName_CreateInstance(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  _QWORD *v8; // r14
  _QWORD *v9; // r15
  _QWORD *v10; // r12
  _QWORD *v11; // r13
  _QWORD *v12; // rbx
  _QWORD *v13; // rax
  const char *v14; // r9
  _QWORD *v15; // rdi
  _QWORD *v16; // rbp
  _QWORD *v17; // rbx
  HSTRING string; // [rsp+28h] [rbp-70h] BYREF
  HSTRING v20; // [rsp+30h] [rbp-68h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-60h] BYREF
  HSTRING v22[11]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v8 = (_QWORD *)WideStringToHString(v22, a5, 0);
  v9 = (_QWORD *)WideStringToHString(&v21, a4, 1);
  v10 = (_QWORD *)WideStringToHString(&v20, 0, 1);
  v11 = (_QWORD *)WideStringToHString(&string, a2, 1);
  v12 = 0;
  v13 = operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v15 = v13;
  v16 = 0;
  if ( v13 )
  {
    v17 = v13 + 1;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(v13 + 1);
    v15[7] = 1;
    *v15 = &Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable';
    *v17 = &Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
    v15[2] = &Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v15 = &Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable';
    *v17 = &Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable'{for `IWeakReferenceSource'};
    v15[2] = &Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v15[8] = *v11;
    *v11 = 0;
    v15[9] = *v10;
    *v10 = 0;
    v15[10] = *v9;
    *v9 = 0;
    v15[11] = *v8;
    *v8 = 0;
    v12 = v15;
    v16 = v15;
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v20 )
    WindowsDeleteString(v20);
  if ( v21 )
    WindowsDeleteString(v21);
  if ( v22[0] )
    WindowsDeleteString(v22[0]);
  if ( !v16 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreitemname.cpp",
      v14);
  *a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x180057f20  mov     [rsp+arg_10], r8
0x180057f25  push    rbx
0x180057f26  push    rbp
0x180057f27  push    rsi
0x180057f28  push    rdi
0x180057f29  push    r12
0x180057f2b  push    r13
0x180057f2d  push    r14
0x180057f2f  push    r15
0x180057f31  sub     rsp, 58h
0x180057f35  mov     rbx, r9
0x180057f38  mov     rdi, rdx
0x180057f3b  mov     rsi, rcx
0x180057f3e  xor     r8d, r8d
0x180057f41  mov     rdx, [rsp+98h+arg_20]
0x180057f49  lea     rcx, [rsp+98h+var_58]
0x180057f4e  call    ?WideStringToHString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGW4WideStringToHStringFlags@@@Z; WideStringToHString(ushort const *,WideStringToHStringFlags)
0x180057f53  mov     r14, rax
0x180057f56  mov     r8d, 1
0x180057f5c  mov     rdx, rbx
0x180057f5f  lea     rcx, [rsp+98h+var_60]
0x180057f64  call    ?WideStringToHString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGW4WideStringToHStringFlags@@@Z; WideStringToHString(ushort const *,WideStringToHStringFlags)
0x180057f69  mov     r15, rax
0x180057f6c  xor     edx, edx
0x180057f6e  lea     r8d, [rdx+1]
0x180057f72  lea     rcx, [rsp+98h+var_68]
0x180057f77  call    ?WideStringToHString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGW4WideStringToHStringFlags@@@Z; WideStringToHString(ushort const *,WideStringToHStringFlags)
0x180057f7c  mov     r12, rax
0x180057f7f  mov     r8d, 1
0x180057f85  mov     rdx, rdi
0x180057f88  lea     rcx, [rsp+98h+string]
0x180057f8d  call    ?WideStringToHString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGW4WideStringToHStringFlags@@@Z; WideStringToHString(ushort const *,WideStringToHStringFlags)
0x180057f92  mov     r13, rax
0x180057f95  xor     ebx, ebx
0x180057f97  mov     [rsp+98h+arg_10], rbx
0x180057f9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057fa6  lea     ecx, [rbx+60h]; unsigned __int64
0x180057fa9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180057fae  mov     rdi, rax
0x180057fb1  xor     ebp, ebp
0x180057fb3  test    rax, rax
0x180057fb6  jz      loc_180058071
0x180057fbc  lea     rbx, [rax+8]
0x180057fc0  mov     rcx, rbx
0x180057fc3  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(void)
0x180057fc8  mov     qword ptr [rdi+38h], 1
0x180057fd0  lea     rax, ??_7?$RuntimeClass@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable'
0x180057fd7  mov     [rdi], rax
0x180057fda  lea     rax, ??_7?$RuntimeClass@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180057fe1  mov     [rbx], rax
0x180057fe4  lea     rax, ??_7?$RuntimeClass@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::Storage::Cloud::ICloudStoreItemName,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180057feb  mov     [rdi+10h], rax
0x180057fef  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180057ff6  test    rcx, rcx
0x180057ff9  jz      short loc_180058008
0x180057ffb  mov     rax, [rcx]
0x180057ffe  mov     rax, [rax+8]
0x180058002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058007  nop
0x180058008  lea     rax, ??_7CloudStoreItemName@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable'
0x18005800f  mov     [rdi], rax
0x180058012  lea     rax, ??_7CloudStoreItemName@Cloud@Storage@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable'{for `IWeakReferenceSource'}
0x180058019  mov     [rbx], rax
0x18005801c  lea     rax, ??_7CloudStoreItemName@Cloud@Storage@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Storage::Cloud::CloudStoreItemName::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180058023  mov     [rdi+10h], rax
0x180058027  mov     rax, [r13+0]
0x18005802b  mov     [rdi+40h], rax
0x18005802f  mov     qword ptr [r13+0], 0
0x180058037  mov     rax, [r12]
0x18005803b  mov     [rdi+48h], rax
0x18005803f  mov     qword ptr [r12], 0
0x180058047  mov     rax, [r15]
0x18005804a  mov     [rdi+50h], rax
0x18005804e  mov     qword ptr [r15], 0
0x180058055  mov     rax, [r14]
0x180058058  mov     [rdi+58h], rax
0x18005805c  mov     qword ptr [r14], 0
0x180058063  mov     rbx, rdi
0x180058066  mov     [rsp+98h+arg_10], rbx
0x18005806e  mov     rbp, rdi
0x180058071  mov     rcx, [rsp+98h+string]; string
0x180058076  test    rcx, rcx
0x180058079  jz      short loc_180058082
0x18005807b  call    cs:__imp_WindowsDeleteString
0x180058081  nop
0x180058082  mov     rcx, [rsp+98h+var_68]; string
0x180058087  test    rcx, rcx
0x18005808a  jz      short loc_180058093
0x18005808c  call    cs:__imp_WindowsDeleteString
0x180058092  nop
0x180058093  mov     rcx, [rsp+98h+var_60]; string
0x180058098  test    rcx, rcx
0x18005809b  jz      short loc_1800580A4
0x18005809d  call    cs:__imp_WindowsDeleteString
0x1800580a3  nop
0x1800580a4  mov     rcx, [rsp+98h+var_58]; string
0x1800580a9  test    rcx, rcx
0x1800580ac  jz      short loc_1800580B4
0x1800580ae  call    cs:__imp_WindowsDeleteString
0x1800580b4  mov     rcx, [rsp+98h]; this
0x1800580bc  test    rbp, rbp
0x1800580bf  jz      short loc_1800580D8
0x1800580c1  mov     [rsi], rbx
0x1800580c4  mov     rax, rsi
0x1800580c7  add     rsp, 58h
0x1800580cb  pop     r15
0x1800580cd  pop     r14
0x1800580cf  pop     r13
0x1800580d1  pop     r12
0x1800580d3  pop     rdi
0x1800580d4  pop     rsi
0x1800580d5  pop     rbp
0x1800580d6  pop     rbx
0x1800580d7  retn
0x1800580d8  lea     r8, aOnecoreuapShel_43; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800580df  mov     edx, 36h ; '6'; void *
0x1800580e4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
