# WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)

- ea: `0x18001d580`
- end: `0x18001dae1`
- name: `?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001dae8`

## callees

- `0x180005020`
- `0x180005070`
- `0x180005e90`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000d430`
- `0x180010b94`
- `0x180013118`
- `0x180013540`
- `0x180014ff4`
- `0x18001a4a8`
- `0x18001bd38`
- `0x18001cfe4`
- `0x18001d0bc`
- `0x18001d12c`
- `0x18001d510`
- `0x18001d580`
- `0x18001f5c0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da1b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da22`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dac2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da1b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da22`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001dac2`

## string_xrefs

- `0x18001d617`: `transportCommand`
- `0x18001d683`: `commandName`
- `0x18001d720`: `commandArguments`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
char *__fastcall WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(char *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rax
  unsigned int v5; // r12d
  _WORD *v6; // rcx
  __int64 v7; // r8
  volatile signed __int32 *v8; // rbx
  const wchar_t *v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // r13
  int v14; // r12d
  int v15; // eax
  __int64 v16; // rax
  const wchar_t *v17; // rdx
  __int64 v18; // r8
  void *v19; // rdi
  int v20; // eax
  HANDLE ProcessHeap; // rax
  __int64 NamedString; // rax
  __int64 v23; // r8
  const wchar_t *v24; // r9
  unsigned __int64 v25; // rdx
  void **v26; // rsi
  __int64 v27; // rdi
  void *v28; // rdi
  int v29; // eax
  HANDLE v30; // rax
  void *v31; // rdi
  int v32; // eax
  HANDLE v33; // rax
  int v34; // eax
  int v35; // r15d
  HANDLE v36; // rax
  __int64 v38; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v39; // [rsp+28h] [rbp-D8h] BYREF
  int v40; // [rsp+30h] [rbp-D0h]
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v45; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v49; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v50; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v51[4]; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v52; // [rsp+98h] [rbp-68h]
  char *v53; // [rsp+A0h] [rbp-60h]
  _QWORD *v54; // [rsp+A8h] [rbp-58h]
  __int64 v55[4]; // [rsp+B0h] [rbp-50h] BYREF
  void *v56[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v57; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v58; // [rsp+E8h] [rbp-18h]
  _OWORD v59[2]; // [rsp+F0h] [rbp-10h] BYREF

  v2 = a2;
  v45 = a2;
  v53 = a1;
  v54 = a2;
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 7;
  *(_WORD *)a1 = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  v5 = 1;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)a1 + 4) = v4;
  v40 = 1;
  v39 = 0;
  v56[1] = (void *)0x1000000001LL;
  v58 = (unsigned __int64)L"transportCommand";
  v56[0] = &v56[1];
  winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
    v2,
    &v44,
    v56,
    &v39);
  v39 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v44, &v39) )
  {
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v6 = a1;
    else
      v6 = *(_WORD **)a1;
    *((_QWORD *)a1 + 2) = 0;
    *v6 = 0;
  }
  else
  {
    *(_QWORD *)&v59[0] = 0;
    v51[0] = 1;
    v51[1] = 11;
    v52 = L"commandName";
    v50 = v51;
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
      &v44,
      &v49,
      &v50,
      v59,
      v38,
      v39);
    v8 = (volatile signed __int32 *)v49;
    if ( v49 )
      v9 = (const wchar_t *)*((_QWORD *)v49 + 2);
    else
      v9 = &S1;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( v10 > *((_QWORD *)a1 + 3) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        a1,
        v10,
        v7,
        v9);
    }
    else
    {
      if ( *((_QWORD *)a1 + 3) <= 7u )
        v11 = a1;
      else
        v11 = *(char **)a1;
      *((_QWORD *)a1 + 2) = v10;
      v12 = 2 * v10;
      memmove_0(v11, v9, 2 * v10);
      *(_WORD *)&v11[v12] = 0;
    }
    v39 = 0;
    v56[1] = (void *)0x1000000001LL;
    v58 = (unsigned __int64)L"commandArguments";
    v56[0] = &v56[1];
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
      &v44,
      &v43,
      v56,
      &v39);
    v39 = 0;
    if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v43, &v39) )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
        &v43,
        &v42);
      v48 = 0;
      v13 = v42;
      while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v42, &v48) )
      {
        v41 = 0;
        v14 = v5 | 4;
        v40 = v14;
        LODWORD(v56[0]) = 46;
        v56[1] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
        v57 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL))(v13, &v41);
        if ( v15 < 0 )
          winrt::throw_hresult((unsigned int)v15, v56);
        v5 = v14 & 0xFFFFFFF9 | 2;
        v40 = v5;
        v16 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                &v41,
                &lpMem);
        if ( *(_QWORD *)v16 )
          v17 = *(const wchar_t **)(*(_QWORD *)v16 + 16LL);
        else
          v17 = &S1;
        memset(v59, 0, sizeof(v59));
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        std::wstring::_Construct<1,unsigned short const *>(v59);
        v19 = lpMem;
        if ( lpMem )
        {
          v20 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v20 )
          {
            if ( v20 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v19);
          }
          lpMem = 0;
        }
        *(_OWORD *)v56 = 0;
        v57 = 0;
        v58 = 7;
        LOWORD(v56[0]) = 0;
        v55[0] = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                              &v41,
                              &v39);
        NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                        &v43,
                        &v47,
                        v55);
        if ( *(_QWORD *)NamedString )
          v24 = *(const wchar_t **)(*(_QWORD *)NamedString + 16LL);
        else
          v24 = &S1;
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        if ( v25 > v58 )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
            v56,
            v25,
            v23,
            v24);
        }
        else
        {
          v26 = v56;
          if ( v58 > 7 )
            v26 = (void **)v56[0];
          v57 = v25;
          v27 = 2 * v25;
          memmove_0(v26, v24, 2 * v25);
          *(_WORD *)((char *)v26 + v27) = 0;
        }
        v28 = v47;
        if ( v47 )
        {
          v29 = _InterlockedDecrement((volatile signed __int32 *)v47 + 6);
          if ( v29 )
          {
            if ( v29 < 0 )
              abort();
          }
          else
          {
            v30 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v30, 0, v28);
          }
          v47 = 0;
        }
        v31 = v39;
        if ( v39 )
        {
          v32 = _InterlockedDecrement((volatile signed __int32 *)v39 + 6);
          if ( v32 )
          {
            if ( v32 < 0 )
              abort();
          }
          else
          {
            v33 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v33, 0, v31);
          }
          v39 = 0;
        }
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(
          a1 + 32,
          &v50,
          v59,
          v56);
        std::wstring::~wstring(v56);
        std::wstring::~wstring(v59);
        if ( v41 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
        LOBYTE(v38) = 0;
        LODWORD(v56[0]) = 82;
        v56[1] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
        v57 = 0;
        v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 64LL))(v13, &v38);
        if ( v34 < 0 )
          winrt::throw_hresult((unsigned int)v34, v56);
        if ( !(_BYTE)v38 )
        {
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
          v13 = 0;
          v42 = 0;
        }
      }
      if ( v13 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
    }
    if ( v43 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
    if ( v8 )
    {
      v35 = _InterlockedDecrement(v8 + 6);
      if ( v35 )
      {
        if ( v35 < 0 )
          abort();
      }
      else
      {
        v36 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v36, 0, (LPVOID)v8);
      }
    }
    v2 = v45;
  }
  if ( v44 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  return a1;
}

```

## disassembly

```asm
0x18001d580  mov     [rsp-8+arg_10], rbx
0x18001d585  push    rbp
0x18001d586  push    rsi
0x18001d587  push    rdi
0x18001d588  push    r12
0x18001d58a  push    r13
0x18001d58c  push    r14
0x18001d58e  push    r15
0x18001d590  lea     rbp, [rsp-20h]
0x18001d595  sub     rsp, 120h
0x18001d59c  mov     rax, cs:__security_cookie
0x18001d5a3  xor     rax, rsp
0x18001d5a6  mov     [rbp+50h+var_40], rax
0x18001d5aa  mov     rbx, rdx
0x18001d5ad  mov     [rsp+150h+var_F8], rdx
0x18001d5b2  mov     r14, rcx
0x18001d5b5  mov     [rbp+50h+var_B0], rcx
0x18001d5b9  mov     [rbp+50h+var_A8], rdx
0x18001d5bd  xor     esi, esi
0x18001d5bf  mov     [rsp+150h+var_120], esi
0x18001d5c3  xorps   xmm0, xmm0
0x18001d5c6  movups  xmmword ptr [rcx], xmm0
0x18001d5c9  mov     [rcx+10h], rsi
0x18001d5cd  mov     qword ptr [rcx+18h], 7
0x18001d5d5  mov     [rcx], si
0x18001d5d8  mov     [rcx+20h], rsi
0x18001d5dc  mov     [rcx+28h], rsi
0x18001d5e0  lea     ecx, [rsi+60h]; Size
0x18001d5e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d5e8  mov     [rax], rax
0x18001d5eb  mov     [rax+8], rax
0x18001d5ef  mov     [rax+10h], rax
0x18001d5f3  lea     r12d, [rsi+1]
0x18001d5f7  mov     word ptr [rax+18h], 101h
0x18001d5fd  mov     [r14+20h], rax
0x18001d601  mov     [rsp+150h+var_120], r12d
0x18001d606  mov     [rsp+150h+var_128], rsi
0x18001d60b  mov     dword ptr [rbp+50h+var_80+8], r12d
0x18001d60f  lea     r13d, [rsi+10h]
0x18001d613  mov     dword ptr [rbp+50h+var_80+0Ch], r13d
0x18001d617  lea     rax, aTransportcomma; "transportCommand"
0x18001d61e  mov     [rbp+50h+var_68], rax
0x18001d622  lea     rax, [rbp+50h+var_80+8]
0x18001d626  mov     [rbp+50h+var_80], rax
0x18001d62a  lea     r9, [rsp+150h+var_128]
0x18001d62f  lea     r8, [rbp+50h+var_80]
0x18001d633  lea     rdx, [rsp+150h+var_100]
0x18001d638  mov     rcx, rbx
0x18001d63b  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x18001d640  nop
0x18001d641  mov     [rsp+150h+var_128], rsi
0x18001d646  lea     rdx, [rsp+150h+var_128]
0x18001d64b  lea     rcx, [rsp+150h+var_100]
0x18001d650  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001d655  test    al, al
0x18001d657  jz      short loc_18001D674
0x18001d659  cmp     qword ptr [r14+18h], 7
0x18001d65e  jbe     short loc_18001D665
0x18001d660  mov     rcx, [r14]
0x18001d663  jmp     short loc_18001D668
0x18001d665  mov     rcx, r14
0x18001d668  mov     [r14+10h], rsi
0x18001d66c  mov     [rcx], si
0x18001d66f  jmp     loc_18001DA74
0x18001d674  mov     qword ptr [rbp+50h+var_60], rsi
0x18001d678  mov     [rbp+50h+var_C8], r12d
0x18001d67c  mov     [rbp+50h+var_C4], 0Bh
0x18001d683  lea     rax, aCommandname; "commandName"
0x18001d68a  mov     [rbp+50h+var_B8], rax
0x18001d68e  lea     rax, [rbp+50h+var_C8]
0x18001d692  mov     [rbp+50h+var_D0], rax
0x18001d696  lea     r9, [rbp+50h+var_60]
0x18001d69a  lea     r8, [rbp+50h+var_D0]
0x18001d69e  lea     rdx, [rsp+150h+var_D8]
0x18001d6a3  lea     rcx, [rsp+150h+var_100]
0x18001d6a8  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18001d6ad  nop
0x18001d6ae  mov     rbx, [rsp+150h+var_D8]
0x18001d6b3  test    rbx, rbx
0x18001d6b6  jz      short loc_18001D6BE
0x18001d6b8  mov     r9, [rbx+10h]
0x18001d6bc  jmp     short loc_18001D6C5
0x18001d6be  lea     r9, S1
0x18001d6c5  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001d6c9  mov     rdx, r15
0x18001d6cc  inc     rdx
0x18001d6cf  cmp     [r9+rdx*2], si
0x18001d6d4  jnz     short loc_18001D6CC
0x18001d6d6  cmp     rdx, [r14+18h]
0x18001d6da  ja      short loc_18001D70B
0x18001d6dc  cmp     qword ptr [r14+18h], 7
0x18001d6e1  jbe     short loc_18001D6E8
0x18001d6e3  mov     rsi, [r14]
0x18001d6e6  jmp     short loc_18001D6EB
0x18001d6e8  mov     rsi, r14
0x18001d6eb  mov     [r14+10h], rdx
0x18001d6ef  lea     rdi, [rdx+rdx]
0x18001d6f3  mov     r8, rdi; Size
0x18001d6f6  mov     rdx, r9; Src
0x18001d6f9  mov     rcx, rsi; void *
0x18001d6fc  call    memmove_0
0x18001d701  xor     eax, eax
0x18001d703  mov     [rdi+rsi], ax
0x18001d707  xor     esi, esi
0x18001d709  jmp     short loc_18001D713
0x18001d70b  mov     rcx, r14
0x18001d70e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001d713  mov     [rsp+150h+var_128], rsi
0x18001d718  mov     dword ptr [rbp+50h+var_80+8], r12d
0x18001d71c  mov     dword ptr [rbp+50h+var_80+0Ch], r13d
0x18001d720  lea     rax, aCommandargumen; "commandArguments"
0x18001d727  mov     [rbp+50h+var_68], rax
0x18001d72b  lea     rax, [rbp+50h+var_80+8]
0x18001d72f  mov     [rbp+50h+var_80], rax
0x18001d733  lea     r9, [rsp+150h+var_128]
0x18001d738  lea     r8, [rbp+50h+var_80]
0x18001d73c  lea     rdx, [rsp+150h+var_108]
0x18001d741  lea     rcx, [rsp+150h+var_100]
0x18001d746  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x18001d74b  nop
0x18001d74c  mov     [rsp+150h+var_128], rsi
0x18001d751  lea     rdx, [rsp+150h+var_128]
0x18001d756  lea     rcx, [rsp+150h+var_108]
0x18001d75b  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001d760  test    al, al
0x18001d762  jnz     loc_18001DA39
0x18001d768  lea     rdx, [rsp+150h+var_110]
0x18001d76d  lea     rcx, [rsp+150h+var_108]
0x18001d772  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x18001d777  nop
0x18001d778  mov     [rsp+150h+var_E0], rsi
0x18001d77d  lea     rdi, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d784  mov     r13, [rsp+150h+var_110]
0x18001d789  lea     rdx, [rsp+150h+var_E0]
0x18001d78e  lea     rcx, [rsp+150h+var_110]
0x18001d793  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001d798  test    al, al
0x18001d79a  jnz     loc_18001DA29
0x18001d7a0  mov     [rsp+150h+var_118], rsi
0x18001d7a5  or      r12d, 4
0x18001d7a9  mov     [rsp+150h+var_120], r12d
0x18001d7ae  mov     dword ptr [rbp+50h+var_80], 2Eh ; '.'
0x18001d7b5  mov     [rbp+50h+var_80+8], rdi
0x18001d7b9  mov     [rbp+50h+var_70], rsi
0x18001d7bd  mov     rax, [r13+0]
0x18001d7c1  lea     rdx, [rsp+150h+var_118]
0x18001d7c6  mov     rcx, r13
0x18001d7c9  mov     rax, [rax+30h]
0x18001d7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d2  test    eax, eax
0x18001d7d4  js      loc_18001DAC9
0x18001d7da  and     r12d, 0FFFFFFFBh
0x18001d7de  or      r12d, 2
0x18001d7e2  mov     [rsp+150h+var_120], r12d
0x18001d7e7  lea     rdx, [rsp+150h+lpMem]
0x18001d7ec  lea     rcx, [rsp+150h+var_118]
0x18001d7f1  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18001d7f6  nop
0x18001d7f7  mov     rdx, [rax]
0x18001d7fa  test    rdx, rdx
0x18001d7fd  jz      short loc_18001D805
0x18001d7ff  mov     rdx, [rdx+10h]
0x18001d803  jmp     short loc_18001D80C
0x18001d805  lea     rdx, S1
0x18001d80c  xorps   xmm0, xmm0
0x18001d80f  movups  [rbp+50h+var_60], xmm0
0x18001d813  xorps   xmm1, xmm1
0x18001d816  movdqu  [rbp+50h+var_50], xmm1
0x18001d81b  mov     r8, r15
0x18001d81e  inc     r8
0x18001d821  cmp     [rdx+r8*2], si
0x18001d826  jnz     short loc_18001D81E
0x18001d828  lea     rcx, [rbp+50h+var_60]
0x18001d82c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d831  nop
0x18001d832  mov     rdi, [rsp+150h+lpMem]
0x18001d837  test    rdi, rdi
0x18001d83a  jz      short loc_18001D86B
0x18001d83c  mov     eax, r15d
0x18001d83f  lock xadd [rdi+18h], eax
0x18001d844  sub     eax, 1
0x18001d847  jnz     short loc_18001D85E
0x18001d849  nop
0x18001d84a  call    WINRT_IMPL_GetProcessHeap
0x18001d84f  mov     rcx, rax; hHeap
0x18001d852  mov     r8, rdi; lpMem
0x18001d855  xor     edx, edx; dwFlags
0x18001d857  call    WINRT_IMPL_HeapFree
0x18001d85c  jmp     short loc_18001D866
0x18001d85e  test    eax, eax
0x18001d860  js      loc_18001DA14
0x18001d866  mov     [rsp+150h+lpMem], rsi
0x18001d86b  xorps   xmm0, xmm0
0x18001d86e  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x18001d872  mov     [rbp+50h+var_70], rsi
0x18001d876  mov     [rbp+50h+var_68], 7
0x18001d87e  mov     word ptr [rbp+50h+var_80], si
0x18001d882  lea     rdx, [rsp+150h+var_128]
0x18001d887  lea     rcx, [rsp+150h+var_118]
0x18001d88c  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18001d891  nop
0x18001d892  mov     rax, [rax]
0x18001d895  mov     [rbp+50h+var_A0], rax
0x18001d899  lea     r8, [rbp+50h+var_A0]
0x18001d89d  lea     rdx, [rsp+150h+var_E8]
0x18001d8a2  lea     rcx, [rsp+150h+var_108]
0x18001d8a7  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x18001d8ac  nop
0x18001d8ad  mov     r9, [rax]
0x18001d8b0  test    r9, r9
0x18001d8b3  jz      short loc_18001D8BB
0x18001d8b5  mov     r9, [r9+10h]
0x18001d8b9  jmp     short loc_18001D8C2
0x18001d8bb  lea     r9, S1
0x18001d8c2  mov     rdx, r15
0x18001d8c5  inc     rdx
0x18001d8c8  cmp     [r9+rdx*2], si
0x18001d8cd  jnz     short loc_18001D8C5
0x18001d8cf  cmp     rdx, [rbp+50h+var_68]
0x18001d8d3  ja      short loc_18001D903
0x18001d8d5  lea     rsi, [rbp+50h+var_80]
0x18001d8d9  cmp     [rbp+50h+var_68], 7
0x18001d8de  cmova   rsi, [rbp+50h+var_80]
0x18001d8e3  mov     [rbp+50h+var_70], rdx
0x18001d8e7  lea     rdi, [rdx+rdx]
0x18001d8eb  mov     r8, rdi; Size
0x18001d8ee  mov     rdx, r9; Src
0x18001d8f1  mov     rcx, rsi; void *
0x18001d8f4  call    memmove_0
0x18001d8f9  xor     eax, eax
0x18001d8fb  mov     [rdi+rsi], ax
0x18001d8ff  xor     esi, esi
0x18001d901  jmp     short loc_18001D90D
0x18001d903  lea     rcx, [rbp+50h+var_80]
0x18001d907  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001d90c  nop
0x18001d90d  mov     rdi, [rsp+150h+var_E8]
0x18001d912  test    rdi, rdi
0x18001d915  jz      short loc_18001D946
0x18001d917  mov     eax, r15d
0x18001d91a  lock xadd [rdi+18h], eax
0x18001d91f  sub     eax, 1
0x18001d922  jnz     short loc_18001D939
0x18001d924  nop
0x18001d925  call    WINRT_IMPL_GetProcessHeap
0x18001d92a  mov     rcx, rax; hHeap
0x18001d92d  mov     r8, rdi; lpMem
0x18001d930  xor     edx, edx; dwFlags
0x18001d932  call    WINRT_IMPL_HeapFree
0x18001d937  jmp     short loc_18001D941
0x18001d939  test    eax, eax
0x18001d93b  js      loc_18001DA1B
0x18001d941  mov     [rsp+150h+var_E8], rsi
0x18001d946  mov     rdi, [rsp+150h+var_128]
0x18001d94b  test    rdi, rdi
0x18001d94e  jz      short loc_18001D97F
0x18001d950  mov     eax, r15d
0x18001d953  lock xadd [rdi+18h], eax
0x18001d958  sub     eax, 1
0x18001d95b  jnz     short loc_18001D972
0x18001d95d  nop
0x18001d95e  call    WINRT_IMPL_GetProcessHeap
0x18001d963  mov     rcx, rax; hHeap
0x18001d966  mov     r8, rdi; lpMem
0x18001d969  xor     edx, edx; dwFlags
0x18001d96b  call    WINRT_IMPL_HeapFree
0x18001d970  jmp     short loc_18001D97A
0x18001d972  test    eax, eax
0x18001d974  js      loc_18001DA22
0x18001d97a  mov     [rsp+150h+var_128], rsi
0x18001d97f  lea     r9, [rbp+50h+var_80]
0x18001d983  lea     r8, [rbp+50h+var_60]
0x18001d987  lea     rdx, [rbp+50h+var_D0]
0x18001d98b  lea     rcx, [r14+20h]
0x18001d98f  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x18001d994  nop
0x18001d995  lea     rcx, [rbp+50h+var_80]; void *
0x18001d999  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d99e  nop
0x18001d99f  lea     rcx, [rbp+50h+var_60]; void *
0x18001d9a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d9a8  nop
0x18001d9a9  cmp     [rsp+150h+var_118], rsi
0x18001d9ae  jz      short loc_18001D9BA
0x18001d9b0  lea     rcx, [rsp+150h+var_118]
0x18001d9b5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d9ba  mov     byte ptr [rsp+150h+var_130], sil
0x18001d9bf  mov     dword ptr [rbp+50h+var_80], 52h ; 'R'
0x18001d9c6  lea     rdi, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001d9cd  mov     [rbp+50h+var_80+8], rdi
0x18001d9d1  mov     [rbp+50h+var_70], rsi
0x18001d9d5  mov     rax, [r13+0]
0x18001d9d9  lea     rdx, [rsp+150h+var_130]
0x18001d9de  mov     rcx, r13
0x18001d9e1  mov     rax, [rax+40h]
0x18001d9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ea  test    eax, eax
0x18001d9ec  js      loc_18001DAD5
0x18001d9f2  cmp     byte ptr [rsp+150h+var_130], sil
0x18001d9f7  jnz     loc_18001D789
  ... truncated ...
```
