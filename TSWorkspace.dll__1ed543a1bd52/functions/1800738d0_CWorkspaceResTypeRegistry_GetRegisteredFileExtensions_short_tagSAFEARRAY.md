# CWorkspaceResTypeRegistry::GetRegisteredFileExtensions(short,tagSAFEARRAY * *)

- ea: `0x1800738d0`
- end: `0x180073b61`
- name: `?GetRegisteredFileExtensions@CWorkspaceResTypeRegistry@@UEAAJFPEAPEAUtagSAFEARRAY@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(CWorkspaceResTypeRegistry *__hidden this, __int16, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000ff00`
- `0x18001ead4`
- `0x180020a68`
- `0x1800276f4`
- `0x18002830c`
- `0x180028ca0`
- `0x180028d04`
- `0x18003add8`
- `0x1800738d0`
- `0x18007bef4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800739ef`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800739ef`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180073b39`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180073b39`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180073abc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180073abc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWorkspaceResTypeRegistry::GetRegisteredFileExtensions(
        CWorkspaceResTypeRegistry *this,
        __int16 a2,
        struct tagSAFEARRAY **a3)
{
  unsigned int v5; // eax
  HRESULT ResourceTypeMap; // ebx
  unsigned int v7; // eax
  SAFEARRAY *v8; // rdi
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  const unsigned __int16 *v13; // rax
  _QWORD *v14; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LONG rgIndices; // [rsp+30h] [rbp-40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h]
  _BYTE v20[8]; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-18h] BYREF
  ULONG v23; // [rsp+60h] [rbp-10h]
  __int64 v24; // [rsp+A0h] [rbp+30h] BYREF
  char v25; // [rsp+A8h] [rbp+38h] BYREF

  v19 = -2;
  std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(v22);
  if ( a3 )
  {
    *a3 = 0;
    ResourceTypeMap = CResourceTypeManager::GetResourceTypeMap(a2 == -1);
    if ( ResourceTypeMap >= 0 )
    {
      rgsabound.cElements = v23;
      rgsabound.lLbound = 0;
      v8 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( v8 )
      {
        rgIndices = 0;
        v24 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
                           v22,
                           &v24,
                           v9);
        while ( 1 )
        {
          v11 = std::vector<unsigned int>::begin(v22, v20);
          if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                   v11,
                                   &v24) )
          {
            *a3 = v8;
            ResourceTypeMap = 0;
            goto LABEL_30;
          }
          v12 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(&v24);
          v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
          v14 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v25, v13);
          if ( v14 )
            v14 = (_QWORD *)*v14;
          ResourceTypeMap = SafeArrayPutElement(v8, &rgIndices, v14);
          _bstr_t::_Free((_bstr_t *)&v25);
          if ( ResourceTypeMap < 0 )
            break;
          std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
            &v24,
            v21);
          ++rgIndices;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"SafeArrayPutElement failed",
            ResourceTypeMap);
        }
        SafeArrayDestroy(v8);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids,
            v10,
            -2147024882);
        }
        ResourceTypeMap = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids,
        v7,
        (__int64)"GetResourceTypeMap failed",
        ResourceTypeMap);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids,
        v5,
        -2147024809);
    }
    ResourceTypeMap = -2147024809;
  }
LABEL_30:
  std::map<std::wstring,ResourceTypeInfo>::~map<std::wstring,ResourceTypeInfo>(v22);
  return (unsigned int)ResourceTypeMap;
}

```

## disassembly

```asm
0x1800738d0  mov     rax, rsp
0x1800738d3  push    rbp
0x1800738d4  push    rsi
0x1800738d5  push    rdi
0x1800738d6  mov     rbp, rsp
0x1800738d9  sub     rsp, 70h
0x1800738dd  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1800738e5  mov     [rax+8], rbx
0x1800738e9  mov     rsi, r8
0x1800738ec  movzx   ebx, dx
0x1800738ef  lea     rcx, [rbp+var_18]
0x1800738f3  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ResourceTypeInfo>::map<std::wstring,ResourceTypeInfo>(void)
0x1800738f8  nop
0x1800738f9  test    rsi, rsi
0x1800738fc  jnz     short loc_180073951
0x1800738fe  lea     rax, WPP_GLOBAL_Control
0x180073905  mov     rcx, cs:WPP_GLOBAL_Control
0x18007390c  cmp     rcx, rax
0x18007390f  jz      short loc_180073947
0x180073911  test    byte ptr [rcx+1Ch], 8
0x180073915  jz      short loc_180073947
0x180073917  cmp     byte ptr [rcx+19h], 2
0x18007391b  jb      short loc_180073947
0x18007391d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073922  lea     edx, [rsi+0Fh]
0x180073925  mov     dword ptr [rsp+70h+var_50], 80070057h
0x18007392d  mov     r9d, eax
0x180073930  lea     r8, WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids
0x180073937  mov     rcx, cs:WPP_GLOBAL_Control
0x18007393e  mov     rcx, [rcx+10h]
0x180073942  call    WPP_SF_Dd
0x180073947  mov     ebx, 80070057h
0x18007394c  jmp     loc_180073B46
0x180073951  mov     qword ptr [rsi], 0
0x180073958  or      eax, 0FFFFFFFFh
0x18007395b  xor     ecx, ecx
0x18007395d  cmp     ax, bx
0x180073960  setz    cl; int
0x180073963  lea     rdx, [rbp+var_18]
0x180073967  call    ?GetResourceTypeMap@CResourceTypeManager@@SAJHAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@@Z; CResourceTypeManager::GetResourceTypeMap(int,std::map<std::wstring,ResourceTypeInfo> &)
0x18007396c  mov     ebx, eax
0x18007396e  test    eax, eax
0x180073970  jns     short loc_1800739D6
0x180073972  lea     rax, WPP_GLOBAL_Control
0x180073979  mov     rcx, cs:WPP_GLOBAL_Control
0x180073980  cmp     rcx, rax
0x180073983  jz      loc_180073B46
0x180073989  test    byte ptr [rcx+1Ch], 8
0x18007398d  jz      loc_180073B46
0x180073993  cmp     byte ptr [rcx+19h], 2
0x180073997  jb      loc_180073B46
0x18007399d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800739a2  mov     edx, 10h
0x1800739a7  mov     [rsp+70h+var_48], ebx
0x1800739ab  lea     rcx, aGetresourcetyp; "GetResourceTypeMap failed"
0x1800739b2  mov     [rsp+70h+var_50], rcx
0x1800739b7  mov     r9d, eax
0x1800739ba  lea     r8, WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids
0x1800739c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800739c8  mov     rcx, [rcx+10h]
0x1800739cc  call    WPP_SF_DsD
0x1800739d1  jmp     loc_180073B46
0x1800739d6  mov     eax, [rbp+var_10]
0x1800739d9  mov     [rbp+rgsabound.cElements], eax
0x1800739dc  mov     [rbp+rgsabound.lLbound], 0
0x1800739e3  mov     ecx, 8; vt
0x1800739e8  lea     r8, [rbp+rgsabound]; rgsabound
0x1800739ec  lea     edx, [rcx-7]; cDims
0x1800739ef  call    cs:__imp_SafeArrayCreate
0x1800739f5  mov     rdi, rax
0x1800739f8  test    rax, rax
0x1800739fb  jnz     short loc_180073A50
0x1800739fd  lea     rax, WPP_GLOBAL_Control
0x180073a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a0b  cmp     rcx, rax
0x180073a0e  jz      short loc_180073A46
0x180073a10  test    byte ptr [rcx+1Ch], 8
0x180073a14  jz      short loc_180073A46
0x180073a16  cmp     byte ptr [rcx+19h], 2
0x180073a1a  jb      short loc_180073A46
0x180073a1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073a21  lea     edx, [rdi+11h]
0x180073a24  mov     dword ptr [rsp+70h+var_50], 8007000Eh
0x180073a2c  mov     r9d, eax
0x180073a2f  lea     r8, WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids
0x180073a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a3d  mov     rcx, [rcx+10h]
0x180073a41  call    WPP_SF_Dd
0x180073a46  mov     ebx, 8007000Eh
0x180073a4b  jmp     loc_180073B46
0x180073a50  mov     [rbp+rgIndices], 0
0x180073a57  lea     rdx, [rbp+arg_10]
0x180073a5b  lea     rcx, [rbp+var_18]
0x180073a5f  call    ?begin@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(void)
0x180073a64  mov     rcx, [rax]
0x180073a67  mov     [rbp+arg_10], rcx
0x180073a6b  lea     rdx, [rbp+var_28]
0x180073a6f  lea     rcx, [rbp+var_18]
0x180073a73  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x180073a78  lea     rdx, [rbp+arg_10]
0x180073a7c  mov     rcx, rax
0x180073a7f  call    ??9?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>> const &)
0x180073a84  test    al, al
0x180073a86  jz      loc_180073B41
0x180073a8c  lea     rcx, [rbp+arg_10]
0x180073a90  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x180073a95  mov     rcx, rax
0x180073a98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073a9d  mov     rdx, rax; unsigned __int16 *
0x180073aa0  lea     rcx, [rbp+arg_18]; this
0x180073aa4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180073aa9  nop
0x180073aaa  mov     r8, [rax]
0x180073aad  test    r8, r8
0x180073ab0  jz      short loc_180073AB5
0x180073ab2  mov     r8, [r8]; pv
0x180073ab5  lea     rdx, [rbp+rgIndices]; rgIndices
0x180073ab9  mov     rcx, rdi; psa
0x180073abc  call    cs:__imp_SafeArrayPutElement
0x180073ac2  mov     ebx, eax
0x180073ac4  lea     rcx, [rbp+arg_18]; this
0x180073ac8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180073acd  test    ebx, ebx
0x180073acf  js      short loc_180073AE3
0x180073ad1  lea     rdx, [rbp+var_20]
0x180073ad5  lea     rcx, [rbp+arg_10]
0x180073ad9  call    ??E?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_DOWNLOAD_INFO@@@std@@@std@@@std@@@std@@QEAA?AV01@H@Z; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(int)
0x180073ade  inc     [rbp+rgIndices]
0x180073ae1  jmp     short loc_180073A6B
0x180073ae3  lea     rax, WPP_GLOBAL_Control
0x180073aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180073af1  cmp     rcx, rax
0x180073af4  jz      short loc_180073B36
0x180073af6  test    byte ptr [rcx+1Ch], 8
0x180073afa  jz      short loc_180073B36
0x180073afc  cmp     byte ptr [rcx+19h], 2
0x180073b00  jb      short loc_180073B36
0x180073b02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180073b07  mov     edx, 12h
0x180073b0c  mov     [rsp+70h+var_48], ebx
0x180073b10  lea     rcx, aSafearrayputel; "SafeArrayPutElement failed"
0x180073b17  mov     [rsp+70h+var_50], rcx
0x180073b1c  mov     r9d, eax
0x180073b1f  lea     r8, WPP_1c6cb5b7c27d3bb56de469f18c65c0fa_Traceguids
0x180073b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b2d  mov     rcx, [rcx+10h]
0x180073b31  call    WPP_SF_DsD
0x180073b36  mov     rcx, rdi; psa
0x180073b39  call    cs:__imp_SafeArrayDestroy
0x180073b3f  jmp     short loc_180073B46
0x180073b41  mov     [rsi], rdi
0x180073b44  xor     ebx, ebx
0x180073b46  lea     rcx, [rbp+var_18]
0x180073b4a  call    ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ResourceTypeInfo>::~map<std::wstring,ResourceTypeInfo>(void)
0x180073b4f  mov     eax, ebx
0x180073b51  mov     rbx, [rsp+70h+arg_0]
0x180073b59  add     rsp, 70h
0x180073b5d  pop     rdi
0x180073b5e  pop     rsi
0x180073b5f  pop     rbp
0x180073b60  retn
```
