# Windows::Globalization::Spelling::CHostSpellCheckProvider::InitializeWordlistFromFileMappings(WORDLIST_TYPE,ulong,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const *)

- ea: `0x14000afe0`
- end: `0x14000b3b8`
- name: `?InitializeWordlistFromFileMappings@CHostSpellCheckProvider@Spelling@Globalization@Windows@@UEAAJW4WORDLIST_TYPE@@KPEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@@Z`
- size: `984`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140001780`
- `0x1400077ec`
- `0x140007ba0`
- `0x140009b40`
- `0x14000ae40`
- `0x14000afe0`
- `0x14000e94c`
- `0x14000ec30`
- `0x14000f9b0`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000b107`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b385`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b107`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b2e1`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostSpellCheckProvider::InitializeWordlistFromFileMappings(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rbx
  int v7; // r14d
  _QWORD *v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rcx
  __int64 *v11; // r12
  __int64 *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r14d
  __int64 v16; // rax
  __int64 *i; // rax
  __int64 *v18; // rcx
  int v19; // esi
  void *v20; // rbx
  int v21; // eax
  __int64 v22; // r8
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  bool v27[8]; // [rsp+30h] [rbp-D8h] BYREF
  int v28; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+40h] [rbp-C8h]
  void *v30[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD *v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-98h]
  _BYTE v35[16]; // [rsp+80h] [rbp-88h] BYREF
  void **v36; // [rsp+90h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-70h]
  const wchar_t *v38; // [rsp+A0h] [rbp-68h]
  int v39; // [rsp+A8h] [rbp-60h]
  int v40; // [rsp+ACh] [rbp-5Ch]
  int *v41; // [rsp+B0h] [rbp-58h]
  __int64 v42; // [rsp+B8h] [rbp-50h]

  v5 = (unsigned int)a3;
  v34 = a1;
  v29 = a2;
  v7 = 0;
  v28 = 0;
  if ( (Microsoft_Windows_Spellchecking_HostEnableBits & 2) != 0 )
  {
    LODWORD(v30[0]) = a2;
    v36 = v30;
    v37 = 4;
    McGenEventWrite_EventWriteTransfer(a1, ThirdPartyProviderInitializeWordlistSend, a3, 2, v35);
  }
  v32 = 0;
  v33 = 0;
  v32 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
  v8 = (_QWORD *)(a1 - 16);
  v9 = a4 + 16 * v5;
  while ( a4 != v9 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v27[0] = v29 == 3;
      v10 = v8[11];
      if ( !v10 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64, void **, __int64, bool *))(*(_QWORD *)v10 + 16LL))(v10, v30, a4, v27);
      v11 = (__int64 *)v30[0];
      v12 = *(__int64 **)v30[0];
      while ( 1 )
      {
        do
        {
LABEL_8:
          if ( v12 == v11 )
          {
            v7 |= 1u;
            v28 = v7;
            std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
              (__int64)v30,
              *((__int64 **)v30[0] + 1));
            *((void **)v30[0] + 1) = v30[0];
            *(_QWORD *)v30[0] = v30[0];
            *((void **)v30[0] + 2) = v30[0];
            v30[1] = 0;
            operator delete(v30[0]);
            a4 += 16;
            goto LABEL_41;
          }
          v15 = (int)v32;
          v16 = std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring const,std::wstring> &>(
                  &v32,
                  v12 + 4);
          std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_hint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(
            (int)&v32,
            (int)&pv,
            v15,
            v16 + 32,
            v16);
          v7 = v28;
        }
        while ( *((_BYTE *)v12 + 25) );
        i = (__int64 *)v12[2];
        if ( *((_BYTE *)i + 25) )
          break;
        v18 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_19;
        do
        {
          v12 = v18;
          v18 = (__int64 *)*v18;
        }
        while ( !*((_BYTE *)v18 + 25) );
      }
      for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v12 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v12 = i;
LABEL_19:
      v12 = i;
      goto LABEL_8;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v30[0]) = -2147024882;
        v19 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000B2FE);
        goto LABEL_36;
      }
    }
LABEL_41:
    ;
  }
  pv = 0;
  v19 = ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::CreateInstance(&pv);
  if ( v19 < 0 )
  {
    v20 = 0;
  }
  else
  {
    v20 = pv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 8LL))(pv);
  }
  v30[0] = v20;
  if ( v19 >= 0 )
  {
    v19 = Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Init(
            (__int64)v20,
            &v32);
    if ( v19 >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**(_QWORD **)(v34 + 32) + 96LL))(
              *(_QWORD *)(v34 + 32),
              v29,
              v20);
      if ( v19 < 0 )
      {
        pv = 0;
        v21 = (*(__int64 (__fastcall **)(_QWORD *, LPVOID *))(*v8 + 24LL))(v8, &pv);
        v19 = v21;
        if ( (Microsoft_Windows_Spellchecking_HostEnableBits & 1) != 0 )
        {
          v28 = v21;
          v23 = (const wchar_t *)pv;
          LODWORD(v30[0]) = v29;
          v36 = v30;
          v37 = 4;
          if ( pv )
          {
            v24 = -1;
            do
              ++v24;
            while ( *((_WORD *)pv + v24) );
            v25 = 2 * v24 + 2;
          }
          else
          {
            v23 = L"NULL";
            v25 = 10;
          }
          v38 = v23;
          v39 = v25;
          v40 = 0;
          v41 = &v28;
          v42 = 4;
          McGenEventWrite_EventWriteTransfer(v23, ThirdPartyProviderInitializeWordlistFailed, v22, 4, v35);
        }
        CoTaskMemFree(pv);
      }
    }
  }
  if ( v20 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_36:
  if ( (Microsoft_Windows_Spellchecking_HostEnableBits & 2) != 0 )
  {
    LODWORD(v30[0]) = v29;
    v36 = v30;
    v37 = 4;
    McGenEventWrite_EventWriteTransfer(v13, ThirdPartyProviderInitializeWordlistReceive, v14, 2, v35);
  }
  std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
    (__int64)&v32,
    (__int64 *)v32[1]);
  v32[1] = v32;
  *v32 = v32;
  v32[2] = v32;
  v33 = 0;
  operator delete(v32);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000afe0  mov     r11, rsp
0x14000afe3  push    rbx
0x14000afe4  push    rsi
0x14000afe5  push    rdi
0x14000afe6  push    r12
0x14000afe8  push    r13
0x14000afea  push    r14
0x14000afec  push    r15
0x14000afee  sub     rsp, 0D0h
0x14000aff5  mov     rax, cs:__security_cookie
0x14000affc  xor     rax, rsp
0x14000afff  mov     [rsp+108h+var_48], rax
0x14000b007  mov     r15, r9
0x14000b00a  mov     ebx, r8d
0x14000b00d  mov     r12, rcx
0x14000b010  mov     [rsp+108h+var_98], rcx
0x14000b015  mov     [rsp+108h+var_C8], edx
0x14000b019  xor     edi, edi
0x14000b01b  mov     r14d, edi
0x14000b01e  mov     [rsp+108h+var_D0], edi
0x14000b022  test    cs:Microsoft_Windows_Spellchecking_HostEnableBits, 2
0x14000b029  jz      short loc_14000B05C
0x14000b02b  mov     dword ptr [rsp+108h+var_C0], edx
0x14000b02f  lea     rax, [rsp+108h+var_C0]
0x14000b034  mov     [r11-78h], rax
0x14000b038  mov     qword ptr [r11-70h], 4
0x14000b040  lea     rax, [r11-88h]
0x14000b047  mov     [rsp+108h+var_E8], rax
0x14000b04c  lea     r9d, [rdi+2]
0x14000b050  lea     rdx, ThirdPartyProviderInitializeWordlistSend
0x14000b057  call    McGenEventWrite_EventWriteTransfer
0x14000b05c  mov     [rsp+108h+var_A8], rdi
0x14000b061  mov     [rsp+108h+var_A0], rdi
0x14000b066  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x14000b06b  mov     [rsp+108h+var_A8], rax
0x14000b070  lea     r13, [r12-10h]
0x14000b075  mov     rsi, rbx
0x14000b078  shl     rsi, 4
0x14000b07c  add     rsi, r15
0x14000b07f  cmp     r15, rsi
0x14000b082  jz      loc_14000B19C
0x14000b088  cmp     [rsp+108h+var_C8], 3
0x14000b08d  setz    [rsp+108h+var_D8]
0x14000b092  mov     rcx, [r13+58h]
0x14000b096  test    rcx, rcx
0x14000b099  jz      loc_14000B3B1
0x14000b09f  mov     rax, [rcx]
0x14000b0a2  lea     r9, [rsp+108h+var_D8]
0x14000b0a7  mov     r8, r15
0x14000b0aa  lea     rdx, [rsp+108h+var_C0]
0x14000b0af  mov     rax, [rax+10h]
0x14000b0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0b8  nop
0x14000b0b9  mov     r12, [rsp+108h+var_C0]
0x14000b0be  mov     rbx, [r12]
0x14000b0c2  cmp     rbx, r12
0x14000b0c5  jnz     short loc_14000B117
0x14000b0c7  or      r14d, 1
0x14000b0cb  mov     [rsp+108h+var_D0], r14d
0x14000b0d0  mov     rdx, [rsp+108h+var_C0]
0x14000b0d5  mov     rdx, [rdx+8]
0x14000b0d9  lea     rcx, [rsp+108h+var_C0]
0x14000b0de  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000b0e3  mov     rax, [rsp+108h+var_C0]
0x14000b0e8  mov     [rax+8], rax
0x14000b0ec  mov     rax, [rsp+108h+var_C0]
0x14000b0f1  mov     [rax], rax
0x14000b0f4  mov     rax, [rsp+108h+var_C0]
0x14000b0f9  mov     [rax+10h], rax
0x14000b0fd  mov     [rsp+108h+var_B8], rdi
0x14000b102  mov     rcx, [rsp+108h+var_C0]
0x14000b107  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b10d  nop
0x14000b10e  add     r15, 10h
0x14000b112  jmp     loc_14000B07F
0x14000b117  mov     r14, [rsp+108h+var_A8]
0x14000b11c  lea     rdx, [rbx+20h]
0x14000b120  lea     rcx, [rsp+108h+var_A8]
0x14000b125  call    ??$_Buynode@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring const,std::wstring> &>(std::pair<std::wstring const,std::wstring> &)
0x14000b12a  lea     r9, [rax+20h]
0x14000b12e  mov     [rsp+108h+var_E8], rax
0x14000b133  mov     r8, r14
0x14000b136  lea     rdx, [rsp+108h+pv]
0x14000b13b  lea     rcx, [rsp+108h+var_A8]
0x14000b140  call    ??$_Insert_hint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_hint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>>,std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000b145  cmp     [rbx+19h], dil
0x14000b149  mov     r14d, [rsp+108h+var_D0]
0x14000b14e  jnz     loc_14000B0C2
0x14000b154  mov     rax, [rbx+10h]
0x14000b158  cmp     [rax+19h], dil
0x14000b15c  jnz     short loc_14000B17B
0x14000b15e  mov     rcx, [rax]
0x14000b161  cmp     [rcx+19h], dil
0x14000b165  jnz     short loc_14000B194
0x14000b167  mov     rbx, rcx
0x14000b16a  mov     rax, [rcx]
0x14000b16d  mov     rcx, rax
0x14000b170  cmp     [rax+19h], dil
0x14000b174  jz      short loc_14000B167
0x14000b176  jmp     loc_14000B0C2
0x14000b17b  mov     rax, [rbx+8]
0x14000b17f  jmp     short loc_14000B18E
0x14000b181  cmp     rbx, [rax+10h]
0x14000b185  jnz     short loc_14000B194
0x14000b187  mov     rbx, rax
0x14000b18a  mov     rax, [rax+8]
0x14000b18e  cmp     [rax+19h], dil
0x14000b192  jz      short loc_14000B181
0x14000b194  mov     rbx, rax
0x14000b197  jmp     loc_14000B0C2
0x14000b19c  mov     [rsp+108h+pv], rdi
0x14000b1a1  lea     rcx, [rsp+108h+pv]
0x14000b1a6  call    ?CreateInstance@?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>> * *)
0x14000b1ab  mov     esi, eax
0x14000b1ad  test    eax, eax
0x14000b1af  js      short loc_14000B1C7
0x14000b1b1  mov     rbx, [rsp+108h+pv]
0x14000b1b6  mov     rax, [rbx]
0x14000b1b9  mov     rcx, rbx
0x14000b1bc  mov     rax, [rax+8]
0x14000b1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1c5  jmp     short loc_14000B1CA
0x14000b1c7  mov     rbx, rdi
0x14000b1ca  mov     [rsp+108h+var_C0], rbx
0x14000b1cf  test    esi, esi
0x14000b1d1  js      loc_14000B2E8
0x14000b1d7  lea     rdx, [rsp+108h+var_A8]
0x14000b1dc  mov     rcx, rbx
0x14000b1df  call    ?Init@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@QEAAJAEAV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Init(std::map<std::wstring const,std::wstring> &)
0x14000b1e4  mov     esi, eax
0x14000b1e6  test    eax, eax
0x14000b1e8  js      loc_14000B2E8
0x14000b1ee  mov     rcx, [rsp+108h+var_98]
0x14000b1f3  mov     rcx, [rcx+20h]
0x14000b1f7  mov     rax, [rcx]
0x14000b1fa  mov     r8, rbx
0x14000b1fd  mov     edx, [rsp+108h+var_C8]
0x14000b201  mov     rax, [rax+60h]
0x14000b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b20a  mov     esi, eax
0x14000b20c  test    eax, eax
0x14000b20e  jns     loc_14000B2E8
0x14000b214  mov     [rsp+108h+pv], rdi
0x14000b219  mov     rax, [r13+0]
0x14000b21d  lea     rdx, [rsp+108h+pv]
0x14000b222  mov     rcx, r13
0x14000b225  mov     rax, [rax+18h]
0x14000b229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b22e  mov     esi, eax
0x14000b230  test    cs:Microsoft_Windows_Spellchecking_HostEnableBits, 1
0x14000b237  jz      loc_14000B2DC
0x14000b23d  mov     [rsp+108h+var_D0], eax
0x14000b241  mov     rcx, [rsp+108h+pv]
0x14000b246  mov     eax, [rsp+108h+var_C8]
0x14000b24a  mov     dword ptr [rsp+108h+var_C0], eax
0x14000b24e  lea     rax, [rsp+108h+var_C0]
0x14000b253  mov     [rsp+108h+var_78], rax
0x14000b25b  mov     [rsp+108h+var_70], 4
0x14000b267  test    rcx, rcx
0x14000b26a  jz      short loc_14000B282
0x14000b26c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b270  inc     rax
0x14000b273  cmp     [rcx+rax*2], di
0x14000b277  jnz     short loc_14000B270
0x14000b279  lea     eax, ds:2[rax*2]
0x14000b280  jmp     short loc_14000B28E
0x14000b282  lea     rcx, aNull; "NULL"
0x14000b289  mov     eax, 0Ah
0x14000b28e  mov     [rsp+108h+var_68], rcx
0x14000b296  mov     [rsp+108h+var_60], eax
0x14000b29d  mov     [rsp+108h+var_5C], edi
0x14000b2a4  lea     rax, [rsp+108h+var_D0]
0x14000b2a9  mov     [rsp+108h+var_58], rax
0x14000b2b1  mov     [rsp+108h+var_50], 4
0x14000b2bd  lea     rax, [rsp+108h+var_88]
0x14000b2c5  mov     [rsp+108h+var_E8], rax
0x14000b2ca  mov     r9d, 4
0x14000b2d0  lea     rdx, ThirdPartyProviderInitializeWordlistFailed
0x14000b2d7  call    McGenEventWrite_EventWriteTransfer
0x14000b2dc  mov     rcx, [rsp+108h+pv]; pv
0x14000b2e1  call    cs:__imp_CoTaskMemFree
0x14000b2e7  nop
0x14000b2e8  test    rbx, rbx
0x14000b2eb  jz      short loc_14000B304
0x14000b2ed  mov     rax, [rbx]
0x14000b2f0  mov     rcx, rbx
0x14000b2f3  mov     rax, [rax+10h]
0x14000b2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2fc  jmp     short loc_14000B304
0x14000b2fe  xor     edi, edi
0x14000b300  mov     esi, dword ptr [rsp+108h+var_C0]
0x14000b304  test    cs:Microsoft_Windows_Spellchecking_HostEnableBits, 2
0x14000b30b  jz      short loc_14000B34E
0x14000b30d  mov     eax, [rsp+108h+var_C8]
0x14000b311  mov     dword ptr [rsp+108h+var_C0], eax
0x14000b315  lea     rax, [rsp+108h+var_C0]
0x14000b31a  mov     [rsp+108h+var_78], rax
0x14000b322  mov     [rsp+108h+var_70], 4
0x14000b32e  lea     rax, [rsp+108h+var_88]
0x14000b336  mov     [rsp+108h+var_E8], rax
0x14000b33b  mov     r9d, 2
0x14000b341  lea     rdx, ThirdPartyProviderInitializeWordlistReceive
0x14000b348  call    McGenEventWrite_EventWriteTransfer
0x14000b34d  nop
0x14000b34e  mov     rdx, [rsp+108h+var_A8]
0x14000b353  mov     rdx, [rdx+8]
0x14000b357  lea     rcx, [rsp+108h+var_A8]
0x14000b35c  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000b361  mov     rax, [rsp+108h+var_A8]
0x14000b366  mov     [rax+8], rax
0x14000b36a  mov     rax, [rsp+108h+var_A8]
0x14000b36f  mov     [rax], rax
0x14000b372  mov     rax, [rsp+108h+var_A8]
0x14000b377  mov     [rax+10h], rax
0x14000b37b  mov     [rsp+108h+var_A0], rdi
0x14000b380  mov     rcx, [rsp+108h+var_A8]
0x14000b385  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b38b  nop
0x14000b38c  mov     eax, esi
0x14000b38e  mov     rcx, [rsp+108h+var_48]
0x14000b396  xor     rcx, rsp; StackCookie
0x14000b399  call    __security_check_cookie
0x14000b39e  add     rsp, 0D0h
0x14000b3a5  pop     r15
0x14000b3a7  pop     r14
0x14000b3a9  pop     r13
0x14000b3ab  pop     r12
0x14000b3ad  pop     rdi
0x14000b3ae  pop     rsi
0x14000b3af  pop     rbx
0x14000b3b0  retn
0x14000b3b1  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
