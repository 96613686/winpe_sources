# CDPComResourcePolicyBroker::OnHostEmpty(char const *)

- ea: `0x18004fbb0`
- end: `0x18004ff79`
- name: `?OnHostEmpty@CDPComResourcePolicyBroker@@UEAAJPEBD@Z`
- size: `969`
- prototype: `__int64 __fastcall(CDPComResourcePolicyBroker *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800010a8`
- `0x180003678`
- `0x180004a58`
- `0x180006494`
- `0x18000ecb8`
- `0x18001b1f0`
- `0x18001b92c`
- `0x18001c284`
- `0x180020cc4`
- `0x180021398`
- `0x18002c570`
- `0x18004f8e8`
- `0x18004f9e8`
- `0x18004fbb0`
- `0x1800505bc`
- `0x180064010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18004fd57`
- `msvcp_win!_Mtx_unlock` at `0x18004fddf`
- `msvcp_win!_Mtx_unlock` at `0x18004fd57`
- `msvcp_win!_Mtx_unlock` at `0x18004fddf`

## string_xrefs

- `0x18004fc04`: `..\cdpcomresourcepolicybroker.cpp`
- `0x18004fd42`: `..\cdpcomresourcepolicybroker.cpp`
- `0x18004fe39`: `..\cdpcomresourcepolicybroker.cpp`
- `0x18004feb8`: `..\cdpcomresourcepolicybroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CDPComResourcePolicyBroker::OnHostEmpty(__int64 **this, const char *a2)
{
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // r12
  __int64 v6; // r8
  _DWORD *v7; // r9
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 **); // rbx
  struct _Mtx_internal_imp_t *v9; // rsi
  _QWORD *v10; // r13
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *v13; // rdi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 **); // r15
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 **); // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // [rsp+30h] [rbp-B8h] BYREF
  int v23; // [rsp+34h] [rbp-B4h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-B0h] BYREF
  int v25; // [rsp+40h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-A0h] BYREF
  const char *v27; // [rsp+50h] [rbp-98h] BYREF
  int *v28; // [rsp+58h] [rbp-90h] BYREF
  char *v29; // [rsp+60h] [rbp-88h] BYREF
  int v30; // [rsp+68h] [rbp-80h] BYREF
  char v31; // [rsp+6Ch] [rbp-7Ch]
  char v32[16]; // [rsp+70h] [rbp-78h] BYREF
  _DWORD v33[4]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v34[32]; // [rsp+90h] [rbp-58h] BYREF

  v4 = 0;
  if ( !a2 )
  {
    v22 = -2147024809;
    v25 = 47;
    Log<long &,char const (&)[40],int>((__int64)this, 0, &v22, "..\\cdpcomresourcepolicybroker.cpp", &v25);
    return v22;
  }
  v30 = 0;
  v31 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v30);
  if ( (unsigned int)dword_180094048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180094048, 0x400000000000LL, v6) )
  {
    v27 = a2;
    if ( v31 && (v33[0] || v33[1] || v33[2] || v33[3]) )
      v7 = v33;
    else
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)&dword_180094048,
      (__int64)byte_1800838E1,
      (__int64)v32,
      (__int64)v7,
      &v27);
  }
  v28 = &v30;
  v27 = (const char *)&v28;
  v25 = 0;
  std::string::string((__int64)v34, (__int64)a2);
  v8 = 0;
  v26 = 0;
  v9 = (struct _Mtx_internal_imp_t *)(this + 17);
  v29 = (char *)(this + 17);
  std::_Mutex_base::lock((std::_Mutex_base *)(this + 17));
  v10 = this + 9;
  std::_Hash<std::_Umap_traits<std::string,Microsoft::WRL::ComPtr<IUnknown>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>,0>>::find(
    this + 9,
    &v24,
    v34);
  v13 = v24;
  if ( v24 == this[10] )
  {
    v22 = -2147023728;
    v23 = 65;
    Log<long &,char const (&)[40],int>(v12, v11, &v22, "..\\cdpcomresourcepolicybroker.cpp", &v23);
    _Mtx_unlock((_Mtx_t)(this + 17));
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    std::string::_Tidy_deallocate(v34);
    ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___::_ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___(&v27);
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v30);
    return v22;
  }
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v24[6];
  if ( v14 )
  {
    v24 = (__int64 *)v24[6];
    Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(&v24);
    v24 = 0;
    v8 = v14;
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v14;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v14;
  }
  std::_Hash<std::_Umap_traits<std::string,Microsoft::WRL::ComPtr<IUnknown>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>,0>(
    v10,
    &v29,
    v13);
  _Mtx_unlock(v9);
  if ( v4 )
  {
    v24 = 0;
    v15 = **v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v16 = v15(v8, &GUID_c2d3a50d_ce51_4c91_96bb_8420e327a616, &v24);
    if ( v16 < 0 )
    {
      v22 = v16;
      v23 = 74;
      Log<long &,char const (&)[40],int>(v18, v17, &v22, "..\\cdpcomresourcepolicybroker.cpp", &v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      std::string::_Tidy_deallocate(v34);
      ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___::_ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___(&v27);
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v30);
      return v22;
    }
    v19 = (*(__int64 (__fastcall **)(__int64 *))(*v24 + 48))(v24);
    if ( v19 < 0 )
    {
      v22 = v19;
      v23 = 75;
      Log<long &,char const (&)[40],int>(v21, v20, &v22, "..\\cdpcomresourcepolicybroker.cpp", &v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      std::string::_Tidy_deallocate(v34);
      ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___::_ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___(&v27);
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v30);
      return v22;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  std::string::_Tidy_deallocate(v34);
  ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___::_ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___(&v27);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v30);
  return 0;
}

```

## disassembly

```asm
0x18004fbb0  mov     [rsp+arg_10], rbx
0x18004fbb5  mov     [rsp+arg_18], rsi
0x18004fbba  push    rdi
0x18004fbbb  push    r12
0x18004fbbd  push    r13
0x18004fbbf  push    r14
0x18004fbc1  push    r15
0x18004fbc3  sub     rsp, 0C0h
0x18004fbca  mov     rax, cs:__security_cookie
0x18004fbd1  xor     rax, rsp
0x18004fbd4  mov     [rsp+0E8h+var_38], rax
0x18004fbdc  mov     rbx, rdx
0x18004fbdf  mov     r15, rcx
0x18004fbe2  xor     r12d, r12d
0x18004fbe5  test    rdx, rdx
0x18004fbe8  jnz     short loc_18004FC1E
0x18004fbea  mov     [rsp+0E8h+var_B8], 80070057h
0x18004fbf2  mov     [rsp+0E8h+var_A8], 2Fh ; '/'
0x18004fbfa  lea     rax, [rsp+0E8h+var_A8]
0x18004fbff  mov     [rsp+0E8h+var_C8], rax
0x18004fc04  lea     r9, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x18004fc0b  lea     r8, [rsp+0E8h+var_B8]
0x18004fc10  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18004fc15  mov     eax, [rsp+0E8h+var_B8]
0x18004fc19  jmp     loc_18004FF4C
0x18004fc1e  mov     [rsp+0E8h+var_80], r12d
0x18004fc23  mov     [rsp+0E8h+var_7C], r12b
0x18004fc28  lea     rcx, [rsp+0E8h+var_80]
0x18004fc2d  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18004fc32  mov     eax, cs:dword_180094048
0x18004fc38  cmp     eax, 5
0x18004fc3b  jbe     short loc_18004FCBA
0x18004fc3d  mov     rdx, 400000000000h
0x18004fc47  lea     rcx, dword_180094048
0x18004fc4e  call    _tlgKeywordOn
0x18004fc53  test    al, al
0x18004fc55  jz      short loc_18004FCBA
0x18004fc57  mov     [rsp+0E8h+var_98], rbx
0x18004fc5c  cmp     [rsp+0E8h+var_7C], r12b
0x18004fc61  jz      short loc_18004FC95
0x18004fc63  cmp     [rsp+0E8h+var_68], r12d
0x18004fc6b  jnz     short loc_18004FC8B
0x18004fc6d  cmp     [rsp+0E8h+var_64], r12d
0x18004fc75  jnz     short loc_18004FC8B
0x18004fc77  cmp     [rsp+0E8h+var_60], r12d
0x18004fc7f  jnz     short loc_18004FC8B
0x18004fc81  cmp     [rsp+0E8h+var_5C], r12d
0x18004fc89  jz      short loc_18004FC95
0x18004fc8b  lea     r9, [rsp+0E8h+var_68]
0x18004fc93  jmp     short loc_18004FC98
0x18004fc95  mov     r9, r12
0x18004fc98  lea     rax, [rsp+0E8h+var_98]
0x18004fc9d  mov     [rsp+0E8h+var_C8], rax
0x18004fca2  lea     r8, [rsp+0E8h+var_78]
0x18004fca7  lea     rdx, byte_1800838E1
0x18004fcae  lea     rcx, dword_180094048
0x18004fcb5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18004fcba  lea     rax, [rsp+0E8h+var_80]
0x18004fcbf  mov     [rsp+0E8h+var_90], rax
0x18004fcc4  lea     rax, [rsp+0E8h+var_90]
0x18004fcc9  mov     [rsp+0E8h+var_98], rax
0x18004fcce  mov     r14d, r12d
0x18004fcd1  mov     [rsp+0E8h+var_A8], r12d
0x18004fcd6  mov     rdx, rbx
0x18004fcd9  lea     rcx, [rsp+0E8h+var_58]
0x18004fce1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004fce6  nop
0x18004fce7  mov     rbx, r12
0x18004fcea  mov     [rsp+0E8h+var_A0], rbx
0x18004fcef  lea     rsi, [r15+88h]
0x18004fcf6  mov     [rsp+0E8h+var_88], rsi
0x18004fcfb  mov     rcx, rsi; this
0x18004fcfe  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004fd03  nop
0x18004fd04  lea     r13, [r15+48h]
0x18004fd08  lea     r8, [rsp+0E8h+var_58]
0x18004fd10  lea     rdx, [rsp+0E8h+var_B0]
0x18004fd15  mov     rcx, r13
0x18004fd18  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Hash<std::_Umap_traits<std::string,Microsoft::WRL::ComPtr<IUnknown>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>,0>>::find(std::string const &)
0x18004fd1d  mov     rdi, [rsp+0E8h+var_B0]
0x18004fd22  cmp     rdi, [r15+50h]
0x18004fd26  jnz     short loc_18004FD95
0x18004fd28  mov     [rsp+0E8h+var_B8], 80070490h
0x18004fd30  mov     [rsp+0E8h+var_B4], 41h ; 'A'
0x18004fd38  lea     rax, [rsp+0E8h+var_B4]
0x18004fd3d  mov     [rsp+0E8h+var_C8], rax
0x18004fd42  lea     r9, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x18004fd49  lea     r8, [rsp+0E8h+var_B8]
0x18004fd4e  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18004fd53  nop
0x18004fd54  mov     rcx, rsi; _Mtx_t
0x18004fd57  call    cs:__imp__Mtx_unlock
0x18004fd5d  nop
0x18004fd5e  lea     rcx, [rsp+0E8h+var_A0]
0x18004fd63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fd68  nop
0x18004fd69  lea     rcx, [rsp+0E8h+var_58]
0x18004fd71  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004fd76  nop
0x18004fd77  lea     rcx, [rsp+0E8h+var_98]
0x18004fd7c  call    ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74______ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___
0x18004fd81  nop
0x18004fd82  lea     rcx, [rsp+0E8h+var_80]
0x18004fd87  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004fd8c  mov     eax, [rsp+0E8h+var_B8]
0x18004fd90  jmp     loc_18004FF4C
0x18004fd95  mov     r15, [rdi+30h]
0x18004fd99  test    r15, r15
0x18004fd9c  jz      short loc_18004FDCB
0x18004fd9e  mov     [rsp+0E8h+var_B0], r15
0x18004fda3  lea     rcx, [rsp+0E8h+var_B0]
0x18004fda8  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x18004fdad  mov     [rsp+0E8h+var_B0], 0
0x18004fdb6  mov     rbx, r15
0x18004fdb9  mov     [rsp+0E8h+var_A0], rbx
0x18004fdbe  lea     rcx, [rsp+0E8h+var_B0]
0x18004fdc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fdc8  mov     r12, r15
0x18004fdcb  mov     r8, rdi
0x18004fdce  lea     rdx, [rsp+0E8h+var_88]
0x18004fdd3  mov     rcx, r13
0x18004fdd6  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<std::string,Microsoft::WRL::ComPtr<IUnknown>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,Microsoft::WRL::ComPtr<IUnknown>>>>>)
0x18004fddb  nop
0x18004fddc  mov     rcx, rsi; _Mtx_t
0x18004fddf  call    cs:__imp__Mtx_unlock
0x18004fde5  test    r12, r12
0x18004fde8  jz      loc_18004FF14
0x18004fdee  mov     [rsp+0E8h+var_B0], 0
0x18004fdf7  mov     rax, [rbx]
0x18004fdfa  mov     rdi, [rax]
0x18004fdfd  lea     rcx, [rsp+0E8h+var_B0]
0x18004fe02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fe07  lea     r8, [rsp+0E8h+var_B0]
0x18004fe0c  lea     rdx, _GUID_c2d3a50d_ce51_4c91_96bb_8420e327a616
0x18004fe13  mov     rcx, rbx
0x18004fe16  mov     rax, rdi
0x18004fe19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe1e  nop
0x18004fe1f  test    eax, eax
0x18004fe21  jns     short loc_18004FE8D
0x18004fe23  mov     [rsp+0E8h+var_B8], eax
0x18004fe27  mov     [rsp+0E8h+var_B4], 4Ah ; 'J'
0x18004fe2f  lea     rax, [rsp+0E8h+var_B4]
0x18004fe34  mov     [rsp+0E8h+var_C8], rax
0x18004fe39  lea     r9, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x18004fe40  lea     r8, [rsp+0E8h+var_B8]
0x18004fe45  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18004fe4a  nop
0x18004fe4b  lea     rcx, [rsp+0E8h+var_B0]
0x18004fe50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fe55  nop
0x18004fe56  lea     rcx, [rsp+0E8h+var_A0]
0x18004fe5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fe60  nop
0x18004fe61  lea     rcx, [rsp+0E8h+var_58]
0x18004fe69  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004fe6e  nop
0x18004fe6f  lea     rcx, [rsp+0E8h+var_98]
0x18004fe74  call    ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74______ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___
0x18004fe79  nop
0x18004fe7a  lea     rcx, [rsp+0E8h+var_80]
0x18004fe7f  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004fe84  mov     eax, [rsp+0E8h+var_B8]
0x18004fe88  jmp     loc_18004FF4C
0x18004fe8d  mov     rcx, [rsp+0E8h+var_B0]
0x18004fe92  mov     rax, [rcx]
0x18004fe95  mov     rax, [rax+30h]
0x18004fe99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe9e  test    eax, eax
0x18004fea0  jns     short loc_18004FF09
0x18004fea2  mov     [rsp+0E8h+var_B8], eax
0x18004fea6  mov     [rsp+0E8h+var_B4], 4Bh ; 'K'
0x18004feae  lea     rax, [rsp+0E8h+var_B4]
0x18004feb3  mov     [rsp+0E8h+var_C8], rax
0x18004feb8  lea     r9, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x18004febf  lea     r8, [rsp+0E8h+var_B8]
0x18004fec4  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18004fec9  nop
0x18004feca  lea     rcx, [rsp+0E8h+var_B0]
0x18004fecf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fed4  nop
0x18004fed5  lea     rcx, [rsp+0E8h+var_A0]
0x18004feda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fedf  nop
0x18004fee0  lea     rcx, [rsp+0E8h+var_58]
0x18004fee8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004feed  nop
0x18004feee  lea     rcx, [rsp+0E8h+var_98]
0x18004fef3  call    ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74______ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___
0x18004fef8  nop
0x18004fef9  lea     rcx, [rsp+0E8h+var_80]
0x18004fefe  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004ff03  mov     eax, [rsp+0E8h+var_B8]
0x18004ff07  jmp     short loc_18004FF4C
0x18004ff09  lea     rcx, [rsp+0E8h+var_B0]
0x18004ff0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ff13  nop
0x18004ff14  lea     rcx, [rsp+0E8h+var_A0]
0x18004ff19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ff1e  nop
0x18004ff1f  lea     rcx, [rsp+0E8h+var_58]
0x18004ff27  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004ff2c  nop
0x18004ff2d  jmp     short loc_18004FF34
0x18004ff2f  mov     r14d, [rsp+0E8h+var_A8]
0x18004ff34  lea     rcx, [rsp+0E8h+var_98]
0x18004ff39  call    ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74______ScopeWarden__lambda_c3a2ea4e6dcd93a63bfd330854a01c74___
0x18004ff3e  nop
0x18004ff3f  lea     rcx, [rsp+0E8h+var_80]
0x18004ff44  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hCDPUserServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hCDPUserServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18004ff49  mov     eax, r14d
0x18004ff4c  mov     rcx, [rsp+0E8h+var_38]
0x18004ff54  xor     rcx, rsp; StackCookie
0x18004ff57  call    __security_check_cookie
0x18004ff5c  lea     r11, [rsp+0E8h+var_28]
0x18004ff64  mov     rbx, [r11+40h]
0x18004ff68  mov     rsi, [r11+48h]
0x18004ff6c  mov     rsp, r11
0x18004ff6f  pop     r15
0x18004ff71  pop     r14
0x18004ff73  pop     r13
0x18004ff75  pop     r12
0x18004ff77  pop     rdi
0x18004ff78  retn
```
