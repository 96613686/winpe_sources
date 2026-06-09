# CdfPlugin::ParseSignal(Microsoft::WRL::ComPtr<IXMLDOMNode>,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x1800402b0`
- end: `0x180040795`
- name: `?ParseSignal@CdfPlugin@@UEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004170`
- `0x18000a7d0`
- `0x18000b5b0`
- `0x18000b7b8`
- `0x180011c8c`
- `0x180012b0c`
- `0x180014e7c`
- `0x18001aa2c`
- `0x18001f634`
- `0x18001fa4c`
- `0x18001fc6c`
- `0x18002072c`
- `0x180021df4`
- `0x1800220d0`
- `0x18003d01c`
- `0x18003fb10`
- `0x18003fc28`
- `0x1800402b0`
- `0x18004101c`
- `0x180041d94`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800402f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800402f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800406eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800406eb`
- `OLEAUT32!__imp_VariantInit` at `0x18004057f`
- `OLEAUT32!__imp_VariantInit` at `0x18004057f`
- `DeviceCredential!DeviceCredentialMgrCheckPresence` at `0x1800406f1`
- `DeviceCredential!DeviceCredentialMgrCheckPresence` at `0x1800406f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CdfPlugin::ParseSignal(__int64 a1, __int64 *a2, __int64 a3, const wchar_t ***a4, __int64 a5)
{
  RTL_SRWLOCK *v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **Address; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  unsigned int i; // r14d
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **v30; // rax
  int v31; // eax
  const wchar_t **v32; // rbx
  const wchar_t *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64 *); // rbx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, const wchar_t *, __int64 *); // rbx
  int v40; // eax
  int v41; // eax
  const wchar_t *v42; // r9
  const wchar_t **v43; // rax
  const wchar_t **v44; // rdx
  unsigned int v45; // ebx
  int v47; // [rsp+20h] [rbp-C1h] BYREF
  __int64 v48; // [rsp+28h] [rbp-B9h] BYREF
  const wchar_t **v49; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v50; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v51; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v52; // [rsp+48h] [rbp-99h] BYREF
  __int64 v53; // [rsp+50h] [rbp-91h] BYREF
  __int64 v54; // [rsp+58h] [rbp-89h] BYREF
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp-81h] BYREF
  __int128 v56; // [rsp+68h] [rbp-79h] BYREF
  __int64 v57; // [rsp+78h] [rbp-69h]
  __int64 v58; // [rsp+80h] [rbp-61h]
  RTL_SRWLOCK *v59; // [rsp+88h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v61; // [rsp+A8h] [rbp-39h]
  char v62[16]; // [rsp+B0h] [rbp-31h] BYREF
  _BYTE v63[32]; // [rsp+C0h] [rbp-21h] BYREF

  v58 = a3;
  v61 = a2;
  v57 = a5;
  v8 = (RTL_SRWLOCK *)(a1 + 112);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 112));
  v59 = v8;
  v56 = 0;
  std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Alloc_sentinel_and_proxy(&v56);
  v48 = 0;
  v47 = 0;
  v9 = *a2;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  v11 = v10(v9, &v48);
  if ( v11 < 0 )
    _com_issue_error(v11);
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 64LL))(v48, &v47);
  if ( v12 < 0 )
    _com_issue_error(v12);
  if ( v47 == 1 )
  {
    v51 = 0;
    v13 = *a2;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v15 = v14(v13, &v51);
    if ( v15 < 0 )
      _com_issue_error(v15);
    v54 = 0;
    v16 = v51;
    v17 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v51 + 56LL);
    Address = _bstr_t::GetAddress((_bstr_t *)&v54);
    v19 = v17(v16, Address);
    if ( v19 < 0 )
      _com_issue_error(v19);
    v20 = v51;
    v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
    v22 = v21(v20, &v48);
    if ( v22 < 0 )
      _com_issue_error(v22);
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 64LL))(v48, &v47);
    if ( v23 < 0 )
      _com_issue_error(v23);
    for ( i = 0; (int)i < v47; ++i )
    {
      v50 = 0;
      v25 = v48;
      v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      v27 = v26(v25, i, &v50);
      if ( v27 < 0 )
        _com_issue_error(v27);
      v49 = 0;
      v28 = v50;
      v29 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v50 + 56LL);
      v30 = _bstr_t::GetAddress((_bstr_t *)&v49);
      v31 = v29(v28, v30);
      if ( v31 < 0 )
        _com_issue_error(v31);
      v32 = v49;
      if ( v49 )
        v33 = *v49;
      else
        v33 = 0;
      if ( wcscmp_0(v33, L"device") )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v32 )
            v42 = *v32;
          else
            v42 = 0;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f58bb35385b7316b81a3583d99bb799e_Traceguids, v42);
        }
        SetSource<IXMLDOMNode>((unsigned __int16 *)(v57 + 8), v34, &v50);
        _bstr_t::_Free((_bstr_t *)&v49);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        break;
      }
      v53 = 0;
      v35 = v50;
      v36 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 136LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      v37 = v36(v35, &v53);
      if ( v37 < 0 )
        _com_issue_error(v37);
      v52 = 0;
      v38 = v53;
      v39 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v53 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      v40 = v39(v38, L"id", &v52);
      if ( v40 < 0 )
        _com_issue_error(v40);
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v41 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v52 + 64LL))(v52, &pvarg);
      if ( v41 < 0 )
        _com_issue_error(v41);
      std::wstring::wstring((__int64)v63, pvarg.llVal);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(
        &v56,
        v62,
        v63);
      std::wstring::_Tidy_deallocate(v63);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      _bstr_t::_Free((_bstr_t *)&v49);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    }
    _bstr_t::_Free((_bstr_t *)&v54);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  }
  CdfSignal::Factory(&v49, v58, &v56);
  v43 = v49;
  if ( !v49 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f58bb35385b7316b81a3583d99bb799e_Traceguids);
    _com_raise_error(-2147024882, 0);
  }
  v49 = 0;
  v44 = *a4;
  *a4 = v43;
  if ( v44 )
    std::default_delete<NASignal>::operator()();
  *(_BYTE *)(a1 + 104) = 1;
  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 96), &pftDueTime, 0, 0);
  v45 = DeviceCredentialMgrCheckPresence();
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>((__int64 (__fastcall ****)(_QWORD, __int64))&v49);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    &v56,
    &v56);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v45;
}

```

## disassembly

```asm
0x1800402b0  push    rbp
0x1800402b2  push    rbx
0x1800402b3  push    rsi
0x1800402b4  push    rdi
0x1800402b5  push    r12
0x1800402b7  push    r13
0x1800402b9  push    r14
0x1800402bb  push    r15
0x1800402bd  lea     rbp, [rsp-17h]
0x1800402c2  sub     rsp, 0F8h
0x1800402c9  mov     rax, cs:__security_cookie
0x1800402d0  xor     rax, rsp
0x1800402d3  mov     [rbp+4Fh+var_50], rax
0x1800402d7  mov     r12, r9
0x1800402da  mov     [rbp+4Fh+var_B0], r8
0x1800402de  mov     r13, rdx
0x1800402e1  mov     r15, rcx
0x1800402e4  mov     [rbp+4Fh+var_88], rdx
0x1800402e8  mov     rax, [rbp+4Fh+arg_20]
0x1800402ec  mov     [rbp+4Fh+var_B8], rax
0x1800402f0  lea     rbx, [rcx+70h]
0x1800402f4  mov     rcx, rbx; SRWLock
0x1800402f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800402fd  mov     [rbp+4Fh+var_A8], rbx
0x180040301  xorps   xmm0, xmm0
0x180040304  movdqu  [rbp+4Fh+var_C8], xmm0
0x180040309  lea     rcx, [rbp+4Fh+var_C8]
0x18004030d  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Alloc_sentinel_and_proxy(void)
0x180040312  nop
0x180040313  mov     [rsp+130h+var_108], 0
0x18004031c  mov     [rsp+130h+var_110], 0
0x180040324  mov     rdi, [r13+0]
0x180040328  mov     rax, [rdi]
0x18004032b  mov     rbx, [rax+60h]
0x18004032f  lea     rcx, [rsp+130h+var_108]
0x180040334  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040339  lea     rdx, [rsp+130h+var_108]
0x18004033e  mov     rcx, rdi
0x180040341  mov     rax, rbx
0x180040344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040349  test    eax, eax
0x18004034b  jns     short loc_180040355
0x18004034d  mov     ecx, eax; int
0x18004034f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040355  mov     rcx, [rsp+130h+var_108]
0x18004035a  mov     rax, [rcx]
0x18004035d  lea     rdx, [rsp+130h+var_110]
0x180040362  mov     rax, [rax+40h]
0x180040366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004036b  test    eax, eax
0x18004036d  jns     short loc_180040377
0x18004036f  mov     ecx, eax; int
0x180040371  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040377  lea     rbx, WPP_GLOBAL_Control
0x18004037e  mov     esi, 1
0x180040383  cmp     [rsp+130h+var_110], esi
0x180040387  jnz     loc_180040693
0x18004038d  mov     [rsp+130h+var_F0], 0
0x180040396  mov     rdi, [r13+0]
0x18004039a  mov     rax, [rdi]
0x18004039d  mov     rbx, [rax+68h]
0x1800403a1  lea     rcx, [rsp+130h+var_F0]
0x1800403a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800403ab  lea     rdx, [rsp+130h+var_F0]
0x1800403b0  mov     rcx, rdi
0x1800403b3  mov     rax, rbx
0x1800403b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403bb  test    eax, eax
0x1800403bd  jns     short loc_1800403C7
0x1800403bf  mov     ecx, eax; int
0x1800403c1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800403c7  mov     [rsp+130h+var_D8], 0
0x1800403d0  mov     rdi, [rsp+130h+var_F0]
0x1800403d5  mov     rax, [rdi]
0x1800403d8  mov     rbx, [rax+38h]
0x1800403dc  lea     rcx, [rsp+130h+var_D8]; this
0x1800403e1  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x1800403e6  mov     rdx, rax
0x1800403e9  mov     rcx, rdi
0x1800403ec  mov     rax, rbx
0x1800403ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403f4  test    eax, eax
0x1800403f6  jns     short loc_180040400
0x1800403f8  mov     ecx, eax; int
0x1800403fa  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040400  mov     rdi, [rsp+130h+var_F0]
0x180040405  mov     rax, [rdi]
0x180040408  mov     rbx, [rax+60h]
0x18004040c  lea     rcx, [rsp+130h+var_108]
0x180040411  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040416  lea     rdx, [rsp+130h+var_108]
0x18004041b  mov     rcx, rdi
0x18004041e  mov     rax, rbx
0x180040421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040426  test    eax, eax
0x180040428  jns     short loc_180040432
0x18004042a  mov     ecx, eax; int
0x18004042c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040432  mov     rcx, [rsp+130h+var_108]
0x180040437  mov     rax, [rcx]
0x18004043a  lea     rdx, [rsp+130h+var_110]
0x18004043f  mov     rax, [rax+40h]
0x180040443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040448  test    eax, eax
0x18004044a  jns     short loc_180040454
0x18004044c  mov     ecx, eax; int
0x18004044e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040454  xor     r14d, r14d
0x180040457  cmp     r14d, [rsp+130h+var_110]
0x18004045c  jge     loc_180040677
0x180040462  mov     [rsp+130h+var_F8], 0
0x18004046b  mov     rdi, [rsp+130h+var_108]
0x180040470  mov     rax, [rdi]
0x180040473  mov     rbx, [rax+38h]
0x180040477  lea     rcx, [rsp+130h+var_F8]
0x18004047c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040481  lea     r8, [rsp+130h+var_F8]
0x180040486  mov     edx, r14d
0x180040489  mov     rcx, rdi
0x18004048c  mov     rax, rbx
0x18004048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040494  test    eax, eax
0x180040496  js      loc_180040759
0x18004049c  mov     [rsp+130h+var_100], 0
0x1800404a5  mov     rdi, [rsp+130h+var_F8]
0x1800404aa  mov     rax, [rdi]
0x1800404ad  mov     rbx, [rax+38h]
0x1800404b1  lea     rcx, [rsp+130h+var_100]; this
0x1800404b6  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x1800404bb  mov     rdx, rax
0x1800404be  mov     rcx, rdi
0x1800404c1  mov     rax, rbx
0x1800404c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404c9  test    eax, eax
0x1800404cb  js      loc_180040751
0x1800404d1  mov     rbx, [rsp+130h+var_100]
0x1800404d6  test    rbx, rbx
0x1800404d9  jz      short loc_1800404E0
0x1800404db  mov     rcx, [rbx]
0x1800404de  jmp     short loc_1800404E2
0x1800404e0  xor     ecx, ecx; String1
0x1800404e2  lea     rdx, aDevice; "device"
0x1800404e9  call    wcscmp_0
0x1800404ee  test    eax, eax
0x1800404f0  jnz     loc_180040613
0x1800404f6  mov     [rsp+130h+var_E0], 0
0x1800404ff  mov     rdi, [rsp+130h+var_F8]
0x180040504  mov     rax, [rdi]
0x180040507  mov     rbx, [rax+88h]
0x18004050e  lea     rcx, [rsp+130h+var_E0]
0x180040513  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040518  lea     rdx, [rsp+130h+var_E0]
0x18004051d  mov     rcx, rdi
0x180040520  mov     rax, rbx
0x180040523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040528  test    eax, eax
0x18004052a  js      loc_18004060B
0x180040530  mov     [rsp+130h+var_E8], 0
0x180040539  mov     rdi, [rsp+130h+var_E0]
0x18004053e  mov     rax, [rdi]
0x180040541  mov     rbx, [rax+38h]
0x180040545  lea     rcx, [rsp+130h+var_E8]
0x18004054a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004054f  lea     r8, [rsp+130h+var_E8]
0x180040554  lea     rdx, aId; "id"
0x18004055b  mov     rcx, rdi
0x18004055e  mov     rax, rbx
0x180040561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040566  test    eax, eax
0x180040568  js      loc_180040603
0x18004056e  xorps   xmm0, xmm0
0x180040571  xor     eax, eax
0x180040573  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180040577  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x18004057b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004057f  call    cs:__imp_VariantInit
0x180040585  mov     rcx, [rsp+130h+var_E8]
0x18004058a  mov     rax, [rcx]
0x18004058d  lea     rdx, [rbp+4Fh+pvarg]
0x180040591  mov     rax, [rax+40h]
0x180040595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004059a  test    eax, eax
0x18004059c  js      short loc_1800405FB
0x18004059e  mov     rdx, qword ptr [rbp+4Fh+pvarg+8]
0x1800405a2  lea     rcx, [rbp+4Fh+var_70]
0x1800405a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800405ab  nop
0x1800405ac  lea     r8, [rbp+4Fh+var_70]
0x1800405b0  lea     rdx, [rbp+4Fh+var_80]
0x1800405b4  lea     rcx, [rbp+4Fh+var_C8]
0x1800405b8  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(std::wstring const &)
0x1800405bd  nop
0x1800405be  lea     rcx, [rbp+4Fh+var_70]
0x1800405c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800405c7  nop
0x1800405c8  lea     rcx, [rsp+130h+var_E8]
0x1800405cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800405d2  nop
0x1800405d3  lea     rcx, [rsp+130h+var_E0]
0x1800405d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800405dd  nop
0x1800405de  lea     rcx, [rsp+130h+var_100]; this
0x1800405e3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800405e8  nop
0x1800405e9  lea     rcx, [rsp+130h+var_F8]
0x1800405ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800405f3  add     r14d, esi
0x1800405f6  jmp     loc_180040457
0x1800405fb  mov     ecx, eax; int
0x1800405fd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040603  mov     ecx, eax; int
0x180040605  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004060b  mov     ecx, eax; int
0x18004060d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180040613  mov     rcx, cs:WPP_GLOBAL_Control
0x18004061a  lea     rax, WPP_GLOBAL_Control
0x180040621  cmp     rcx, rax
0x180040624  jz      short loc_18004064E
0x180040626  test    [rcx+1Ch], sil
0x18004062a  jz      short loc_18004064E
0x18004062c  test    rbx, rbx
0x18004062f  jz      short loc_180040636
0x180040631  mov     r9, [rbx]
0x180040634  jmp     short loc_180040639
0x180040636  xor     r9d, r9d
0x180040639  mov     edx, 0Dh
0x18004063e  lea     r8, WPP_f58bb35385b7316b81a3583d99bb799e_Traceguids
0x180040645  mov     rcx, [rcx+10h]
0x180040649  call    WPP_SF_S
0x18004064e  mov     rcx, [rbp+4Fh+var_B8]
0x180040652  add     rcx, 8; unsigned __int16 *
0x180040656  lea     r8, [rsp+130h+var_F8]
0x18004065b  call    ??$SetSource@UIXMLDOMNode@@@@YAXPEAG_KAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; SetSource<IXMLDOMNode>(ushort *,unsigned __int64,Microsoft::WRL::ComPtr<IXMLDOMNode> const &)
0x180040660  nop
0x180040661  lea     rcx, [rsp+130h+var_100]; this
0x180040666  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004066b  nop
0x18004066c  lea     rcx, [rsp+130h+var_F8]
0x180040671  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040676  nop
0x180040677  lea     rcx, [rsp+130h+var_D8]; this
0x18004067c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180040681  nop
0x180040682  lea     rcx, [rsp+130h+var_F0]
0x180040687  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004068c  lea     rbx, WPP_GLOBAL_Control
0x180040693  lea     r8, [rbp+4Fh+var_C8]
0x180040697  mov     rdx, [rbp+4Fh+var_B0]
0x18004069b  lea     rcx, [rsp+130h+var_100]
0x1800406a0  call    ?Factory@CdfSignal@@SA?AV?$unique_ptr@VCdfSignal@@U?$default_delete@VCdfSignal@@@std@@@std@@_JAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@K@Z; CdfSignal::Factory(__int64,std::set<std::wstring> const &,ulong)
0x1800406a5  nop
0x1800406a6  mov     rax, [rsp+130h+var_100]
0x1800406ab  test    rax, rax
0x1800406ae  jz      loc_180040761
0x1800406b4  mov     [rsp+130h+var_100], 0
0x1800406bd  mov     rdx, [r12]
0x1800406c1  mov     [r12], rax
0x1800406c5  test    rdx, rdx
0x1800406c8  jz      short loc_1800406CF
0x1800406ca  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x1800406cf  xchg    sil, [r15+68h]
0x1800406d3  mov     qword ptr [rsp+130h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x1800406dc  xor     r9d, r9d; msWindowLength
0x1800406df  xor     r8d, r8d; msPeriod
0x1800406e2  lea     rdx, [rsp+130h+pftDueTime]; pftDueTime
0x1800406e7  mov     rcx, [r15+60h]; pti
0x1800406eb  call    cs:__imp_SetThreadpoolTimer
0x1800406f1  call    cs:__imp_DeviceCredentialMgrCheckPresence
0x1800406f7  mov     ebx, eax
0x1800406f9  lea     rcx, [rsp+130h+var_100]
0x1800406fe  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x180040703  nop
0x180040704  lea     rcx, [rsp+130h+var_108]
0x180040709  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004070e  nop
0x18004070f  lea     rdx, [rbp+4Fh+var_C8]
0x180040713  lea     rcx, [rbp+4Fh+var_C8]
0x180040717  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x18004071c  nop
0x18004071d  lea     rcx, [rbp+4Fh+var_A8]
0x180040721  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180040726  nop
0x180040727  mov     rcx, r13
0x18004072a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004072f  mov     eax, ebx
0x180040731  mov     rcx, [rbp+4Fh+var_50]
0x180040735  xor     rcx, rsp; StackCookie
0x180040738  call    __security_check_cookie
0x18004073d  add     rsp, 0F8h
0x180040744  pop     r15
0x180040746  pop     r14
0x180040748  pop     r13
0x18004074a  pop     r12
0x18004074c  pop     rdi
0x18004074d  pop     rsi
0x18004074e  pop     rbx
0x18004074f  pop     rbp
0x180040750  retn
0x180040751  mov     ecx, eax; int
0x180040753  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
  ... truncated ...
```
