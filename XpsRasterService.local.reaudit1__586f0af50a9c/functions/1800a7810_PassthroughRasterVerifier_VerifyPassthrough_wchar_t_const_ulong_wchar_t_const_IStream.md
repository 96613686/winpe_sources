# PassthroughRasterVerifier::VerifyPassthrough(wchar_t const *,ulong,wchar_t const *,IStream *)

- ea: `0x1800a7810`
- end: `0x1800a7b03`
- name: `?VerifyPassthrough@PassthroughRasterVerifier@@UEAAJPEB_WK0PEAUIStream@@@Z`
- size: `755`
- prototype: `int(PassthroughRasterVerifier *__hidden this, const wchar_t *, unsigned int, const wchar_t *, struct IStream *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003180`
- `0x180003cc4`
- `0x1800a2cb8`
- `0x1800a5be8`
- `0x1800a61a8`
- `0x1800a61e4`
- `0x1800a6290`
- `0x1800a62c0`
- `0x1800a635c`
- `0x1800a6560`
- `0x1800a6590`
- `0x1800a7810`
- `0x1800a7b88`
- `0x1800a7ba8`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800a79b8`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800a79b8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800a7934`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800a7934`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800a7961`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800a7961`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800a7a0c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800a7a0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PassthroughRasterVerifier::VerifyPassthrough(
        PassthroughRasterVerifier *this,
        const wchar_t *a2,
        int a3,
        const wchar_t *a4,
        struct IStream *pstmFrom)
{
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int v15; // r8d
  IStream *v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  IStream *v19; // rbx
  HRESULT v20; // eax
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // r8d
  int v24; // eax
  unsigned int v25; // r8d
  __int64 v26; // rbx
  unsigned int UniqueContext; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // ebx
  unsigned int v31; // r8d
  const char *v32; // r9
  __int64 result; // rax
  int v34; // [rsp+20h] [rbp-108h]
  int v35; // [rsp+20h] [rbp-108h]
  int v36; // [rsp+30h] [rbp-F8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-E8h] BYREF
  IStream *v39; // [rsp+48h] [rbp-E0h] BYREF
  _QWORD v40[2]; // [rsp+50h] [rbp-D8h] BYREF
  int v41[2]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v42[64]; // [rsp+70h] [rbp-B8h] BYREF
  _BYTE v43[16]; // [rsp+B0h] [rbp-78h] BYREF
  DWORD cb; // [rsp+C0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v36 = a3;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
    &string,
    a2);
  try
  {
    ((void (*)(void))wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>)();
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    if ( !*(_QWORD *)v41 || !**(_QWORD **)v41 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x14, v7, v8);
    v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
           &string,
           a4);
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(
      v40,
      v9);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    if ( !v40[0] || !*(_QWORD *)v40[0] )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x16, v10, v11);
    memset_0(v43, 0, 0x50u);
    v12 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)pstmFrom + 96LL))(pstmFrom, v43, 1);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1A, v13, (const char *)(unsigned int)v12, v34);
    v14 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)pstmFrom + 40LL))(
            pstmFrom,
            0,
            0,
            0);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x1C, v15, (const char *)(unsigned int)v14, v34);
    v16 = SHCreateMemStream(0, 0);
    v19 = v16;
    v39 = v16;
    if ( !v16 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1F, v17, v18);
    v20 = IStream_Copy(pstmFrom, v16, cb);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x20, v21, (const char *)(unsigned int)v20, v34);
    v22 = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, 0, 0, 0);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x21, v23, (const char *)(unsigned int)v22, v34);
    v38 = 0;
    v24 = CreateRandomAccessStreamOverStream(v19, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v38);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x24, v25, (const char *)(unsigned int)v24, v34);
    wil::com_ptr_t<PassthroughRasterVerifier,wil::err_exception_policy>::com_ptr_t<PassthroughRasterVerifier,wil::err_exception_policy>(
      &string,
      this);
    v26 = lambda_f8b475fe85083a88d500a1b676630133_::_lambda_f8b475fe85083a88d500a1b676630133_(
            (unsigned int)v42,
            (unsigned int)&string,
            (unsigned int)&v38,
            (unsigned int)&v36,
            (__int64)v41,
            (__int64)v40);
    UniqueContext = SHTaskPoolGetUniqueContext();
    v30 = Windows::Internal::ComTaskPool::QueueTask__lambda_f8b475fe85083a88d500a1b676630133___(
            v29,
            v28,
            UniqueContext,
            v26);
    lambda_f8b475fe85083a88d500a1b676630133_::__lambda_f8b475fe85083a88d500a1b676630133_(v42);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x2C, v31, (const char *)(unsigned int)v30, v35);
    wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(&string);
    wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(&v38);
    wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(&v39);
    std::shared_ptr<ID2D1Factory1>::~shared_ptr<ID2D1Factory1>(v40);
    std::shared_ptr<ID2D1Factory1>::~shared_ptr<ID2D1Factory1>(v41);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x30,
                           (unsigned int)"onecoreuap\\printscan\\dox\\render\\xpsras\\lib\\passthroughrasterverfierimpl.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x1800a7810  push    rbx
0x1800a7812  push    rsi
0x1800a7813  push    rdi
0x1800a7814  sub     rsp, 110h
0x1800a781b  mov     rax, cs:__security_cookie
0x1800a7822  xor     rax, rsp
0x1800a7825  mov     [rsp+128h+var_28], rax
0x1800a782d  mov     rbx, r9
0x1800a7830  mov     rsi, rcx
0x1800a7833  mov     [rsp+128h+var_F8], r8d
0x1800a7838  mov     rdi, [rsp+128h+pstmFrom]
0x1800a7840  lea     rcx, [rsp+128h+string]; string
0x1800a7845  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800a784a  nop
0x1800a784b  mov     rdx, rax
0x1800a784e  lea     rcx, [rsp+128h+var_C8]
0x1800a7853  call    ??0?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800a7858  nop
0x1800a7859  lea     rcx, [rsp+128h+string]
0x1800a785e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800a7863  mov     rcx, [rsp+128h]; this
0x1800a786b  mov     rax, qword ptr [rsp+128h+var_C8]
0x1800a7870  test    rax, rax
0x1800a7873  jz      loc_1800A7AF7
0x1800a7879  cmp     qword ptr [rax], 0
0x1800a787d  jz      loc_1800A7AF7
0x1800a7883  mov     rdx, rbx; sourceString
0x1800a7886  lea     rcx, [rsp+128h+string]; string
0x1800a788b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800a7890  nop
0x1800a7891  mov     rdx, rax
0x1800a7894  lea     rcx, [rsp+128h+var_D8]
0x1800a7899  call    ??0?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800a789e  nop
0x1800a789f  lea     rcx, [rsp+128h+string]
0x1800a78a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800a78a9  mov     rcx, [rsp+128h]; this
0x1800a78b1  mov     rax, [rsp+128h+var_D8]
0x1800a78b6  test    rax, rax
0x1800a78b9  jz      loc_1800A7AEC
0x1800a78bf  cmp     qword ptr [rax], 0
0x1800a78c3  jz      loc_1800A7AEC
0x1800a78c9  xor     edx, edx; Val
0x1800a78cb  lea     r8d, [rdx+50h]; Size
0x1800a78cf  lea     rcx, [rsp+128h+var_78]; void *
0x1800a78d7  call    memset_0
0x1800a78dc  mov     rax, [rdi]
0x1800a78df  mov     r8d, 1
0x1800a78e5  lea     rdx, [rsp+128h+var_78]
0x1800a78ed  mov     rcx, rdi
0x1800a78f0  mov     rax, [rax+60h]
0x1800a78f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a78f9  mov     rcx, [rsp+128h]; this
0x1800a7901  test    eax, eax
0x1800a7903  js      loc_1800A7A92
0x1800a7909  xor     edx, edx
0x1800a790b  mov     rax, [rdi]
0x1800a790e  xor     r9d, r9d
0x1800a7911  xor     r8d, r8d
0x1800a7914  mov     rcx, rdi
0x1800a7917  mov     rax, [rax+28h]
0x1800a791b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7920  mov     rcx, [rsp+128h]; this
0x1800a7928  test    eax, eax
0x1800a792a  js      loc_1800A7A9F
0x1800a7930  xor     edx, edx; cbInit
0x1800a7932  xor     ecx, ecx; pInit
0x1800a7934  call    cs:__imp_SHCreateMemStream
0x1800a793a  mov     rbx, rax
0x1800a793d  mov     [rsp+128h+var_E0], rax
0x1800a7942  mov     rcx, [rsp+128h]; this
0x1800a794a  test    rax, rax
0x1800a794d  jz      loc_1800A7AAD
0x1800a7953  mov     r8d, [rsp+128h+cb]; cb
0x1800a795b  mov     rdx, rbx; pstmTo
0x1800a795e  mov     rcx, rdi; pstmFrom
0x1800a7961  call    cs:__imp_IStream_Copy
0x1800a7967  mov     rcx, [rsp+128h]; this
0x1800a796f  test    eax, eax
0x1800a7971  js      loc_1800A7AB5
0x1800a7977  xor     edx, edx
0x1800a7979  mov     rax, [rbx]
0x1800a797c  xor     r9d, r9d
0x1800a797f  xor     r8d, r8d
0x1800a7982  mov     rcx, rbx
0x1800a7985  mov     rax, [rax+28h]
0x1800a7989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a798e  mov     rcx, [rsp+128h]; this
0x1800a7996  test    eax, eax
0x1800a7998  js      loc_1800A7AC2
0x1800a799e  mov     [rsp+128h+var_E8], 0
0x1800a79a7  lea     r9, [rsp+128h+var_E8]
0x1800a79ac  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800a79b3  xor     edx, edx
0x1800a79b5  mov     rcx, rbx
0x1800a79b8  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1800a79be  mov     rcx, [rsp+128h]; this
0x1800a79c6  test    eax, eax
0x1800a79c8  js      loc_1800A7AD0
0x1800a79ce  mov     rdx, rsi
0x1800a79d1  lea     rcx, [rsp+128h+string]
0x1800a79d6  call    ??0?$com_ptr_t@VPassthroughRasterVerifier@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVPassthroughRasterVerifier@@@Z; wil::com_ptr_t<PassthroughRasterVerifier,wil::err_exception_policy>::com_ptr_t<PassthroughRasterVerifier,wil::err_exception_policy>(PassthroughRasterVerifier *)
0x1800a79db  nop
0x1800a79dc  lea     rax, [rsp+128h+var_D8]
0x1800a79e1  mov     [rsp+128h+var_100], rax
0x1800a79e6  lea     rax, [rsp+128h+var_C8]
0x1800a79eb  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800a79f0  lea     r9, [rsp+128h+var_F8]
0x1800a79f5  lea     r8, [rsp+128h+var_E8]
0x1800a79fa  lea     rdx, [rsp+128h+string]
0x1800a79ff  lea     rcx, [rsp+128h+var_B8]
0x1800a7a04  call    _lambda_f8b475fe85083a88d500a1b676630133____lambda_f8b475fe85083a88d500a1b676630133_
0x1800a7a09  mov     rbx, rax
0x1800a7a0c  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800a7a12  mov     r9, rbx
0x1800a7a15  mov     r8d, eax
0x1800a7a18  call    Windows__Internal__ComTaskPool__QueueTask__lambda_f8b475fe85083a88d500a1b676630133___
0x1800a7a1d  mov     ebx, eax
0x1800a7a1f  lea     rcx, [rsp+128h+var_B8]
0x1800a7a24  call    _lambda_f8b475fe85083a88d500a1b676630133_____lambda_f8b475fe85083a88d500a1b676630133_
0x1800a7a29  mov     rcx, [rsp+128h]; this
0x1800a7a31  test    ebx, ebx
0x1800a7a33  js      loc_1800A7ADE
0x1800a7a39  lea     rcx, [rsp+128h+string]
0x1800a7a3e  call    ??1?$com_ptr_t@UIRandomAccessStream@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(void)
0x1800a7a43  nop
0x1800a7a44  lea     rcx, [rsp+128h+var_E8]
0x1800a7a49  call    ??1?$com_ptr_t@UIRandomAccessStream@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(void)
0x1800a7a4e  nop
0x1800a7a4f  lea     rcx, [rsp+128h+var_E0]
0x1800a7a54  call    ??1?$com_ptr_t@UIRandomAccessStream@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::Streams::IRandomAccessStream,wil::err_exception_policy>(void)
0x1800a7a59  nop
0x1800a7a5a  lea     rcx, [rsp+128h+var_D8]
0x1800a7a5f  call    ??1?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::~shared_ptr<ID2D1Factory1>(void)
0x1800a7a64  nop
0x1800a7a65  lea     rcx, [rsp+128h+var_C8]
0x1800a7a6a  call    ??1?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::~shared_ptr<ID2D1Factory1>(void)
0x1800a7a6f  xor     eax, eax
0x1800a7a71  jmp     short loc_1800A7A77
0x1800a7a73  mov     eax, [rsp+128h+var_F8]
0x1800a7a77  mov     rcx, [rsp+128h+var_28]
0x1800a7a7f  xor     rcx, rsp; StackCookie
0x1800a7a82  call    __security_check_cookie
0x1800a7a87  add     rsp, 110h
0x1800a7a8e  pop     rdi
0x1800a7a8f  pop     rsi
0x1800a7a90  pop     rbx
0x1800a7a91  retn
0x1800a7a92  mov     r9d, eax; char *
0x1800a7a95  mov     edx, 1Ah; void *
0x1800a7a9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7a9f  mov     r9d, eax; char *
0x1800a7aa2  mov     edx, 1Ch; void *
0x1800a7aa7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7aad  lea     edx, [rax+1Fh]; void *
0x1800a7ab0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a7ab5  mov     r9d, eax; char *
0x1800a7ab8  mov     edx, 20h ; ' '; void *
0x1800a7abd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7ac2  mov     r9d, eax; char *
0x1800a7ac5  mov     edx, 21h ; '!'; void *
0x1800a7aca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7ad0  mov     r9d, eax; char *
0x1800a7ad3  mov     edx, 24h ; '$'; void *
0x1800a7ad8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7ade  mov     r9d, ebx; char *
0x1800a7ae1  mov     edx, 2Ch ; ','; void *
0x1800a7ae6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a7aec  mov     edx, 16h; void *
0x1800a7af1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a7af7  mov     edx, 14h; void *
0x1800a7afc  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
