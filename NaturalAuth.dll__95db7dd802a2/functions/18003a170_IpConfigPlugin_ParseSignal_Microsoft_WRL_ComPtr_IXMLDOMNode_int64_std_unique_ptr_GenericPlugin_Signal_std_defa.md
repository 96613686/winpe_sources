# IpConfigPlugin::ParseSignal(Microsoft::WRL::ComPtr<IXMLDOMNode>,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x18003a170`
- end: `0x18003a79d`
- name: `?ParseSignal@IpConfigPlugin@@UEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `1581`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004170`
- `0x18000aac4`
- `0x18000aea4`
- `0x18000b370`
- `0x180014e7c`
- `0x18001f634`
- `0x18001fa4c`
- `0x18001fc6c`
- `0x18002072c`
- `0x180021df4`
- `0x18002cc48`
- `0x18002d008`
- `0x18002d018`
- `0x180037720`
- `0x1800392cc`
- `0x180039608`
- `0x180039a74`
- `0x180039c68`
- `0x180039d3c`
- `0x180039edc`
- `0x180039fcc`
- `0x18003a170`
- `0x18003a9a8`
- `0x180041d94`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003a6c7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003a6c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall IpConfigPlugin::ParseSignal(__int64 a1, __int64 *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **Address; // rax
  int v20; // eax
  const wchar_t **v21; // rbx
  const wchar_t *v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  const wchar_t *v25; // rdx
  const wchar_t *v26; // rdx
  const wchar_t *v27; // rdx
  __int64 v28; // rbx
  size_t size_of; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  const wchar_t *v32; // rdx
  const wchar_t *v33; // rdx
  const wchar_t *v34; // rdx
  __int64 v35; // rbx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  const wchar_t *v40; // rdx
  const wchar_t *v41; // r9
  __int64 v43; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v44; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  int v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t **v48; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int128 *v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h]
  __int64 *v54; // [rsp+80h] [rbp-80h]
  Properties v55; // [rsp+90h] [rbp-70h] BYREF
  __int64 v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-58h]
  char v59; // [rsp+B0h] [rbp-50h]
  __int128 v60; // [rsp+B8h] [rbp-48h]
  __int16 v61; // [rsp+C8h] [rbp-38h]
  __int128 v62; // [rsp+CAh] [rbp-36h]
  __int128 v63; // [rsp+DAh] [rbp-26h]
  __int128 v64; // [rsp+F0h] [rbp-10h] BYREF
  char v65; // [rsp+100h] [rbp+0h]
  _QWORD v66[3]; // [rsp+108h] [rbp+8h] BYREF

  v54 = a2;
  v47 = 0;
  v46 = 0;
  v7 = *a2;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  v9 = v8(v7, &v47);
  if ( v9 < 0 )
    _com_issue_error(v9);
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 64LL))(v47, &v46);
  if ( v10 < 0 )
    _com_issue_error(v10);
  if ( !v46 )
  {
    SetSource<IXMLDOMNode>((unsigned __int16 *)(a5 + 8), v11, a2);
    v12 = -2147023431;
    goto LABEL_87;
  }
  v55.lpVtbl = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  std::list<in_addr>::_Alloc_sentinel_and_proxy(&v57);
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  std::list<GenericPlugin::DefaultSignal::CallbackInfo>::_Alloc_sentinel_and_proxy(&v64);
  v65 = 0;
  v66[0] = 0;
  v66[1] = 0;
  std::list<std::wstring>::_Alloc_sentinel_and_proxy(v66);
  for ( i = 0; (int)i < v46; ++i )
  {
    v44 = 0;
    v14 = v47;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v16 = v15(v14, i, &v44);
    if ( v16 < 0 )
      _com_issue_error(v16);
    v48 = 0;
    v17 = v44;
    v18 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v44 + 56LL);
    Address = _bstr_t::GetAddress((_bstr_t *)&v48);
    v20 = v18(v17, Address);
    if ( v20 < 0 )
      _com_issue_error(v20);
    LODWORD(v45) = 0;
    v49 = 0;
    v21 = v48;
    if ( v48 )
      v22 = *v48;
    else
      v22 = 0;
    if ( !wcscmp_0(L"ipv4Prefix", v22) )
    {
      v45 = v44;
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
      v23 = ParseIpv4Prefix(&v45, &v55);
      goto LABEL_74;
    }
    if ( v21 )
      v25 = *v21;
    else
      v25 = 0;
    if ( !wcscmp_0(L"ipv4Gateway", v25) )
    {
      v43 = v44;
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
      v12 = ParseIpv4Address(&v43, &v45);
      if ( v12 < 0 )
        goto LABEL_84;
      v59 |= 2u;
      LODWORD(v56) = v45;
    }
    else
    {
      if ( v21 )
        v26 = *v21;
      else
        v26 = 0;
      if ( !wcscmp_0(L"ipv4DhcpServer", v26) )
      {
        v43 = v44;
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
        v12 = ParseIpv4Address(&v43, &v45);
        if ( v12 < 0 )
          goto LABEL_84;
        v59 |= 4u;
        HIDWORD(v56) = v45;
      }
      else
      {
        if ( v21 )
          v27 = *v21;
        else
          v27 = 0;
        if ( !wcscmp_0(L"ipv4DnsServer", v27) )
        {
          v43 = v44;
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
          v12 = ParseIpv4Address(&v43, &v45);
          if ( v12 < 0 )
            goto LABEL_84;
          if ( v58 == 0xAAAAAAAAAAAAAAALL )
            goto LABEL_76;
          v28 = v57;
          v50 = &v57;
          v51 = 0;
          size_of = std::_Get_size_of_n<24>(1);
          v30 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
          *((_DWORD *)v30 + 4) = v45;
          ++v58;
          v31 = *(_QWORD **)(v28 + 8);
          *v30 = v28;
          v30[1] = v31;
          v51 = 0;
          *(_QWORD *)(v28 + 8) = v30;
          *v31 = v30;
          std::_Alloc_construct_ptr<std::allocator<std::_List_node<in_addr,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<in_addr,void *>>>(&v50);
        }
        else
        {
          if ( v21 )
            v32 = *v21;
          else
            v32 = 0;
          if ( !wcscmp_0(L"ipv6Prefix", v32) )
          {
            v43 = v44;
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
            v23 = ParseIpv6Prefix(&v43, &v55);
LABEL_74:
            v12 = v23;
            if ( v23 < 0 )
              goto LABEL_84;
            goto LABEL_75;
          }
          if ( v21 )
            v33 = *v21;
          else
            v33 = 0;
          if ( !wcscmp_0(L"ipv6Gateway", v33) )
          {
            v43 = v44;
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
            v12 = ParseIpv6Address(&v43, &v49);
            if ( v12 < 0 )
              goto LABEL_84;
            v65 |= 2u;
            v62 = v49;
          }
          else
          {
            if ( v21 )
              v34 = *v21;
            else
              v34 = 0;
            if ( wcscmp_0(L"ipv6DnsServer", v34) )
            {
              if ( v21 )
                v40 = *v21;
              else
                v40 = 0;
              if ( wcscmp_0(L"dnsSuffix", v40) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  if ( v21 )
                    v41 = *v21;
                  else
                    v41 = 0;
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids,
                    v41);
                }
                v12 = -805265277;
LABEL_84:
                SetSource<IXMLDOMNode>((unsigned __int16 *)(a5 + 8), v24, &v44);
                _bstr_t::_Free((_bstr_t *)&v48);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
                if ( v12 < 0 )
                  goto LABEL_86;
                break;
              }
              v43 = v44;
              if ( v44 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
              v23 = ParseDnsName(&v43, v66);
              goto LABEL_74;
            }
            v43 = v44;
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
            v12 = ParseIpv6Address(&v43, &v49);
            if ( v12 < 0 )
              goto LABEL_84;
            if ( *((_QWORD *)&v64 + 1) == 0x7FFFFFFFFFFFFFFLL )
LABEL_76:
              std::_Xlength_error("list too long");
            v52 = &v64;
            v53 = 0;
            v35 = v64;
            v36 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
            v38 = (_QWORD *)std::_Default_allocator_traits<std::allocator<std::_List_node<CallbackInfo,void *>>>::construct<CallbackInfo,CallbackInfo>(
                              v37,
                              v36 + 2,
                              &v49);
            ++*((_QWORD *)&v64 + 1);
            v39 = *(_QWORD **)(v35 + 8);
            *v38 = v35;
            v38[1] = v39;
            v53 = 0;
            *(_QWORD *)(v35 + 8) = v38;
            *v39 = v38;
            std::_Alloc_construct_ptr<std::allocator<std::_List_node<GenericPlugin::DefaultSignal::CallbackInfo,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<GenericPlugin::DefaultSignal::CallbackInfo,void *>>>((__int64)&v52);
          }
        }
      }
    }
LABEL_75:
    _bstr_t::_Free((_bstr_t *)&v48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  }
  v12 = IpConfigSignal::Create(a3, &v55);
LABEL_86:
  IpConfigSignal::Properties::~Properties((void **)&v55.lpVtbl);
LABEL_87:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003a170  mov     [rsp-8+arg_0], rbx
0x18003a175  push    rbp
0x18003a176  push    rsi
0x18003a177  push    rdi
0x18003a178  push    r12
0x18003a17a  push    r13
0x18003a17c  push    r14
0x18003a17e  push    r15
0x18003a180  lea     rbp, [rsp-30h]
0x18003a185  sub     rsp, 130h
0x18003a18c  mov     rax, cs:__security_cookie
0x18003a193  xor     rax, rsp
0x18003a196  mov     [rbp+60h+var_40], rax
0x18003a19a  mov     r13, r9
0x18003a19d  mov     r12, r8
0x18003a1a0  mov     r14, rdx
0x18003a1a3  mov     [rbp+60h+var_E0], rdx
0x18003a1a7  mov     r15, [rbp+60h+arg_20]
0x18003a1ae  mov     [rsp+160h+var_120], 0
0x18003a1b7  mov     [rsp+160h+var_128], 0
0x18003a1bf  mov     rdi, [rdx]
0x18003a1c2  mov     rax, [rdi]
0x18003a1c5  mov     rbx, [rax+60h]
0x18003a1c9  lea     rcx, [rsp+160h+var_120]
0x18003a1ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a1d3  lea     rdx, [rsp+160h+var_120]
0x18003a1d8  mov     rcx, rdi
0x18003a1db  mov     rax, rbx
0x18003a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1e3  xor     edi, edi
0x18003a1e5  test    eax, eax
0x18003a1e7  jns     short loc_18003A1F1
0x18003a1e9  mov     ecx, eax; int
0x18003a1eb  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a1f1  mov     rcx, [rsp+160h+var_120]
0x18003a1f6  mov     rax, [rcx]
0x18003a1f9  lea     rdx, [rsp+160h+var_128]
0x18003a1fe  mov     rax, [rax+40h]
0x18003a202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a207  test    eax, eax
0x18003a209  jns     short loc_18003A213
0x18003a20b  mov     ecx, eax; int
0x18003a20d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a213  cmp     [rsp+160h+var_128], edi
0x18003a217  jnz     short loc_18003A22F
0x18003a219  lea     rcx, [r15+8]; unsigned __int16 *
0x18003a21d  mov     r8, r14
0x18003a220  call    ??$SetSource@UIXMLDOMNode@@@@YAXPEAG_KAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; SetSource<IXMLDOMNode>(ushort *,unsigned __int64,Microsoft::WRL::ComPtr<IXMLDOMNode> const &)
0x18003a225  mov     ebx, 800705B9h
0x18003a22a  jmp     loc_18003A751
0x18003a22f  xor     eax, eax
0x18003a231  mov     [rbp+60h+var_D0.lpVtbl], rax
0x18003a235  mov     [rbp+60h+var_C8], rax
0x18003a239  mov     [rbp+60h+var_C0], rdi
0x18003a23d  mov     [rbp+60h+var_B8], rdi
0x18003a241  lea     rcx, [rbp+60h+var_C0]
0x18003a245  call    ?_Alloc_sentinel_and_proxy@?$list@Uin_addr@@V?$allocator@Uin_addr@@@std@@@std@@AEAAXXZ; std::list<in_addr>::_Alloc_sentinel_and_proxy(void)
0x18003a24a  mov     [rbp+60h+var_B0], dil
0x18003a24e  xorps   xmm0, xmm0
0x18003a251  xor     eax, eax
0x18003a253  movups  [rbp+60h+var_A8], xmm0
0x18003a257  mov     [rbp+60h+var_98], ax
0x18003a25b  movups  [rbp+60h+var_96], xmm0
0x18003a25f  xorps   xmm1, xmm1
0x18003a262  movups  [rbp+60h+var_86], xmm1
0x18003a266  movdqa  [rbp+60h+var_70], xmm0
0x18003a26b  lea     rcx, [rbp+60h+var_70]
0x18003a26f  call    ?_Alloc_sentinel_and_proxy@?$list@UCallbackInfo@DefaultSignal@GenericPlugin@@V?$allocator@UCallbackInfo@DefaultSignal@GenericPlugin@@@std@@@std@@AEAAXXZ; std::list<GenericPlugin::DefaultSignal::CallbackInfo>::_Alloc_sentinel_and_proxy(void)
0x18003a274  mov     [rbp+60h+var_60], dil
0x18003a278  mov     [rbp+60h+var_58], rdi
0x18003a27c  mov     [rbp+60h+var_50], rdi
0x18003a280  lea     rcx, [rbp+60h+var_58]
0x18003a284  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x18003a289  nop
0x18003a28a  mov     esi, edi
0x18003a28c  cmp     esi, [rsp+160h+var_128]
0x18003a290  jge     loc_18003A736
0x18003a296  mov     [rsp+160h+var_138], rdi
0x18003a29b  mov     rdi, [rsp+160h+var_120]
0x18003a2a0  mov     rax, [rdi]
0x18003a2a3  mov     rbx, [rax+38h]
0x18003a2a7  lea     rcx, [rsp+160h+var_138]
0x18003a2ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a2b1  lea     r8, [rsp+160h+var_138]
0x18003a2b6  mov     edx, esi
0x18003a2b8  mov     rcx, rdi
0x18003a2bb  mov     rax, rbx
0x18003a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2c3  test    eax, eax
0x18003a2c5  js      loc_18003A795
0x18003a2cb  mov     [rsp+160h+var_118], 0
0x18003a2d4  mov     rdi, [rsp+160h+var_138]
0x18003a2d9  mov     rax, [rdi]
0x18003a2dc  mov     rbx, [rax+38h]
0x18003a2e0  lea     rcx, [rsp+160h+var_118]; this
0x18003a2e5  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x18003a2ea  mov     rdx, rax
0x18003a2ed  mov     rcx, rdi
0x18003a2f0  mov     rax, rbx
0x18003a2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2f8  xor     edi, edi
0x18003a2fa  test    eax, eax
0x18003a2fc  js      loc_18003A78D
0x18003a302  mov     dword ptr [rsp+160h+var_130], edi
0x18003a306  xorps   xmm0, xmm0
0x18003a309  movups  [rsp+160h+var_110], xmm0
0x18003a30e  mov     rbx, [rsp+160h+var_118]
0x18003a313  test    rbx, rbx
0x18003a316  jz      short loc_18003A31D
0x18003a318  mov     rdx, [rbx]
0x18003a31b  jmp     short loc_18003A320
0x18003a31d  mov     rdx, rdi; String2
0x18003a320  lea     rcx, aIpv4prefix; "ipv4Prefix"
0x18003a327  call    wcscmp_0
0x18003a32c  test    eax, eax
0x18003a32e  jnz     short loc_18003A35F
0x18003a330  mov     rcx, [rsp+160h+var_138]
0x18003a335  mov     [rsp+160h+var_130], rcx
0x18003a33a  test    rcx, rcx
0x18003a33d  jz      short loc_18003A34C
0x18003a33f  mov     rax, [rcx]
0x18003a342  mov     rax, [rax+8]
0x18003a346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a34b  nop
0x18003a34c  lea     rdx, [rbp+60h+var_D0]
0x18003a350  lea     rcx, [rsp+160h+var_130]
0x18003a355  call    ParseIpv4Prefix
0x18003a35a  jmp     loc_18003A69E
0x18003a35f  test    rbx, rbx
0x18003a362  jz      short loc_18003A369
0x18003a364  mov     rdx, [rbx]
0x18003a367  jmp     short loc_18003A36C
0x18003a369  mov     rdx, rdi; String2
0x18003a36c  lea     rcx, aIpv4gateway; "ipv4Gateway"
0x18003a373  call    wcscmp_0
0x18003a378  test    eax, eax
0x18003a37a  jnz     short loc_18003A3C1
0x18003a37c  mov     rcx, [rsp+160h+var_138]
0x18003a381  mov     [rsp+160h+var_140], rcx
0x18003a386  test    rcx, rcx
0x18003a389  jz      short loc_18003A398
0x18003a38b  mov     rax, [rcx]
0x18003a38e  mov     rax, [rax+8]
0x18003a392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a397  nop
0x18003a398  lea     rdx, [rsp+160h+var_130]
0x18003a39d  lea     rcx, [rsp+160h+var_140]
0x18003a3a2  call    ParseIpv4Address
0x18003a3a7  mov     ebx, eax
0x18003a3a9  test    eax, eax
0x18003a3ab  js      loc_18003A70E
0x18003a3b1  or      [rbp+60h+var_B0], 2
0x18003a3b5  mov     eax, dword ptr [rsp+160h+var_130]
0x18003a3b9  mov     dword ptr [rbp+60h+var_C8], eax
0x18003a3bc  jmp     loc_18003A6A4
0x18003a3c1  test    rbx, rbx
0x18003a3c4  jz      short loc_18003A3CB
0x18003a3c6  mov     rdx, [rbx]
0x18003a3c9  jmp     short loc_18003A3CE
0x18003a3cb  mov     rdx, rdi; String2
0x18003a3ce  lea     rcx, aIpv4dhcpserver; "ipv4DhcpServer"
0x18003a3d5  call    wcscmp_0
0x18003a3da  test    eax, eax
0x18003a3dc  jnz     short loc_18003A423
0x18003a3de  mov     rcx, [rsp+160h+var_138]
0x18003a3e3  mov     [rsp+160h+var_140], rcx
0x18003a3e8  test    rcx, rcx
0x18003a3eb  jz      short loc_18003A3FA
0x18003a3ed  mov     rax, [rcx]
0x18003a3f0  mov     rax, [rax+8]
0x18003a3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3f9  nop
0x18003a3fa  lea     rdx, [rsp+160h+var_130]
0x18003a3ff  lea     rcx, [rsp+160h+var_140]
0x18003a404  call    ParseIpv4Address
0x18003a409  mov     ebx, eax
0x18003a40b  test    eax, eax
0x18003a40d  js      loc_18003A70E
0x18003a413  or      [rbp+60h+var_B0], 4
0x18003a417  mov     eax, dword ptr [rsp+160h+var_130]
0x18003a41b  mov     dword ptr [rbp+60h+var_C8+4], eax
0x18003a41e  jmp     loc_18003A6A4
0x18003a423  test    rbx, rbx
0x18003a426  jz      short loc_18003A42D
0x18003a428  mov     rdx, [rbx]
0x18003a42b  jmp     short loc_18003A430
0x18003a42d  mov     rdx, rdi; String2
0x18003a430  lea     rcx, aIpv4dnsserver; "ipv4DnsServer"
0x18003a437  call    wcscmp_0
0x18003a43c  test    eax, eax
0x18003a43e  jnz     loc_18003A4E2
0x18003a444  mov     rcx, [rsp+160h+var_138]
0x18003a449  mov     [rsp+160h+var_140], rcx
0x18003a44e  test    rcx, rcx
0x18003a451  jz      short loc_18003A460
0x18003a453  mov     rax, [rcx]
0x18003a456  mov     rax, [rax+8]
0x18003a45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a45f  nop
0x18003a460  lea     rdx, [rsp+160h+var_130]
0x18003a465  lea     rcx, [rsp+160h+var_140]
0x18003a46a  call    ParseIpv4Address
0x18003a46f  mov     ebx, eax
0x18003a471  test    eax, eax
0x18003a473  js      loc_18003A70E
0x18003a479  mov     rax, 0AAAAAAAAAAAAAAAh
0x18003a483  cmp     [rbp+60h+var_B8], rax
0x18003a487  jz      loc_18003A6C0
0x18003a48d  mov     rbx, [rbp+60h+var_C0]
0x18003a491  lea     rax, [rbp+60h+var_C0]
0x18003a495  mov     [rsp+160h+var_100], rax
0x18003a49a  mov     [rsp+160h+var_F8], rdi
0x18003a49f  mov     ecx, 1
0x18003a4a4  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18003a4a9  mov     rcx, rax
0x18003a4ac  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003a4b1  mov     ecx, dword ptr [rsp+160h+var_130]
0x18003a4b5  mov     [rax+10h], ecx
0x18003a4b8  inc     [rbp+60h+var_B8]
0x18003a4bc  mov     rcx, [rbx+8]
0x18003a4c0  mov     [rax], rbx
0x18003a4c3  mov     [rax+8], rcx
0x18003a4c7  mov     [rsp+160h+var_F8], rdi
0x18003a4cc  mov     [rbx+8], rax
0x18003a4d0  mov     [rcx], rax
0x18003a4d3  lea     rcx, [rsp+160h+var_100]
0x18003a4d8  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@Uin_addr@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<in_addr,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<in_addr,void *>>>(void)
0x18003a4dd  jmp     loc_18003A6A4
0x18003a4e2  test    rbx, rbx
0x18003a4e5  jz      short loc_18003A4EC
0x18003a4e7  mov     rdx, [rbx]
0x18003a4ea  jmp     short loc_18003A4EF
0x18003a4ec  mov     rdx, rdi; String2
0x18003a4ef  lea     rcx, aIpv6prefix; "ipv6Prefix"
0x18003a4f6  call    wcscmp_0
0x18003a4fb  test    eax, eax
0x18003a4fd  jnz     short loc_18003A52E
0x18003a4ff  mov     rcx, [rsp+160h+var_138]
0x18003a504  mov     [rsp+160h+var_140], rcx
0x18003a509  test    rcx, rcx
0x18003a50c  jz      short loc_18003A51B
0x18003a50e  mov     rax, [rcx]
0x18003a511  mov     rax, [rax+8]
0x18003a515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a51a  nop
0x18003a51b  lea     rdx, [rbp+60h+var_D0]
0x18003a51f  lea     rcx, [rsp+160h+var_140]
0x18003a524  call    ParseIpv6Prefix
0x18003a529  jmp     loc_18003A69E
0x18003a52e  test    rbx, rbx
0x18003a531  jz      short loc_18003A538
0x18003a533  mov     rdx, [rbx]
0x18003a536  jmp     short loc_18003A53B
0x18003a538  mov     rdx, rdi; String2
0x18003a53b  lea     rcx, aIpv6gateway; "ipv6Gateway"
0x18003a542  call    wcscmp_0
0x18003a547  test    eax, eax
0x18003a549  jnz     short loc_18003A59B
0x18003a54b  mov     rcx, [rsp+160h+var_138]
0x18003a550  mov     [rsp+160h+var_140], rcx
0x18003a555  test    rcx, rcx
0x18003a558  jz      short loc_18003A567
0x18003a55a  mov     rax, [rcx]
0x18003a55d  mov     rax, [rax+8]
0x18003a561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a566  nop
0x18003a567  lea     rdx, [rsp+160h+var_110]
0x18003a56c  lea     rcx, [rsp+160h+var_140]
0x18003a571  call    ParseIpv6Address
0x18003a576  mov     ebx, eax
0x18003a578  test    eax, eax
0x18003a57a  js      loc_18003A70E
0x18003a580  or      [rbp+60h+var_60], 2
0x18003a584  mov     rax, qword ptr [rsp+160h+var_110]
0x18003a589  mov     qword ptr [rbp+60h+var_96], rax
0x18003a58d  mov     rax, qword ptr [rsp+160h+var_110+8]
0x18003a592  mov     qword ptr [rbp+60h+var_96+8], rax
0x18003a596  jmp     loc_18003A6A4
0x18003a59b  test    rbx, rbx
0x18003a59e  jz      short loc_18003A5A5
0x18003a5a0  mov     rdx, [rbx]
0x18003a5a3  jmp     short loc_18003A5A8
0x18003a5a5  mov     rdx, rdi; String2
0x18003a5a8  lea     rcx, aIpv6dnsserver; "ipv6DnsServer"
0x18003a5af  call    wcscmp_0
0x18003a5b4  test    eax, eax
0x18003a5b6  jnz     loc_18003A657
0x18003a5bc  mov     rcx, [rsp+160h+var_138]
0x18003a5c1  mov     [rsp+160h+var_140], rcx
0x18003a5c6  test    rcx, rcx
0x18003a5c9  jz      short loc_18003A5D8
0x18003a5cb  mov     rax, [rcx]
0x18003a5ce  mov     rax, [rax+8]
0x18003a5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5d7  nop
0x18003a5d8  lea     rdx, [rsp+160h+var_110]
0x18003a5dd  lea     rcx, [rsp+160h+var_140]
0x18003a5e2  call    ParseIpv6Address
0x18003a5e7  mov     ebx, eax
0x18003a5e9  test    eax, eax
  ... truncated ...
```
