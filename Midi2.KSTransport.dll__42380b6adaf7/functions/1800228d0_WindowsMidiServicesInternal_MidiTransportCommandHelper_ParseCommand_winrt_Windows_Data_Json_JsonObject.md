# WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)

- ea: `0x1800228d0`
- end: `0x180022e31`
- name: `?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e38`

## callees

- `0x180004410`
- `0x180004460`
- `0x180005260`
- `0x1800052fc`
- `0x180005374`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000f304`
- `0x18000f684`
- `0x1800112b0`
- `0x180015348`
- `0x180021190`
- `0x180022330`
- `0x180022408`
- `0x180022478`
- `0x180022860`
- `0x1800228d0`
- `0x180024bbc`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d64`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d6b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d72`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e12`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d64`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d6b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d72`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e12`

## string_xrefs

- `0x180022967`: `transportCommand`
- `0x1800229d3`: `commandName`
- `0x180022a70`: `commandArguments`

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
        std::wstring::_Construct<1,unsigned short const *>(v59, v17, v18);
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
0x1800228d0  mov     [rsp-8+arg_10], rbx
0x1800228d5  push    rbp
0x1800228d6  push    rsi
0x1800228d7  push    rdi
0x1800228d8  push    r12
0x1800228da  push    r13
0x1800228dc  push    r14
0x1800228de  push    r15
0x1800228e0  lea     rbp, [rsp-20h]
0x1800228e5  sub     rsp, 120h
0x1800228ec  mov     rax, cs:__security_cookie
0x1800228f3  xor     rax, rsp
0x1800228f6  mov     [rbp+50h+var_40], rax
0x1800228fa  mov     rbx, rdx
0x1800228fd  mov     [rsp+150h+var_F8], rdx
0x180022902  mov     r14, rcx
0x180022905  mov     [rbp+50h+var_B0], rcx
0x180022909  mov     [rbp+50h+var_A8], rdx
0x18002290d  xor     esi, esi
0x18002290f  mov     [rsp+150h+var_120], esi
0x180022913  xorps   xmm0, xmm0
0x180022916  movups  xmmword ptr [rcx], xmm0
0x180022919  mov     [rcx+10h], rsi
0x18002291d  mov     qword ptr [rcx+18h], 7
0x180022925  mov     [rcx], si
0x180022928  mov     [rcx+20h], rsi
0x18002292c  mov     [rcx+28h], rsi
0x180022930  lea     ecx, [rsi+60h]; Size
0x180022933  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022938  mov     [rax], rax
0x18002293b  mov     [rax+8], rax
0x18002293f  mov     [rax+10h], rax
0x180022943  lea     r12d, [rsi+1]
0x180022947  mov     word ptr [rax+18h], 101h
0x18002294d  mov     [r14+20h], rax
0x180022951  mov     [rsp+150h+var_120], r12d
0x180022956  mov     [rsp+150h+var_128], rsi
0x18002295b  mov     dword ptr [rbp+50h+var_80+8], r12d
0x18002295f  lea     r13d, [rsi+10h]
0x180022963  mov     dword ptr [rbp+50h+var_80+0Ch], r13d
0x180022967  lea     rax, aTransportcomma; "transportCommand"
0x18002296e  mov     [rbp+50h+var_68], rax
0x180022972  lea     rax, [rbp+50h+var_80+8]
0x180022976  mov     [rbp+50h+var_80], rax
0x18002297a  lea     r9, [rsp+150h+var_128]
0x18002297f  lea     r8, [rbp+50h+var_80]
0x180022983  lea     rdx, [rsp+150h+var_100]
0x180022988  mov     rcx, rbx
0x18002298b  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x180022990  nop
0x180022991  mov     [rsp+150h+var_128], rsi
0x180022996  lea     rdx, [rsp+150h+var_128]
0x18002299b  lea     rcx, [rsp+150h+var_100]
0x1800229a0  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800229a5  test    al, al
0x1800229a7  jz      short loc_1800229C4
0x1800229a9  cmp     qword ptr [r14+18h], 7
0x1800229ae  jbe     short loc_1800229B5
0x1800229b0  mov     rcx, [r14]
0x1800229b3  jmp     short loc_1800229B8
0x1800229b5  mov     rcx, r14
0x1800229b8  mov     [r14+10h], rsi
0x1800229bc  mov     [rcx], si
0x1800229bf  jmp     loc_180022DC4
0x1800229c4  mov     qword ptr [rbp+50h+var_60], rsi
0x1800229c8  mov     [rbp+50h+var_C8], r12d
0x1800229cc  mov     [rbp+50h+var_C4], 0Bh
0x1800229d3  lea     rax, aCommandname; "commandName"
0x1800229da  mov     [rbp+50h+var_B8], rax
0x1800229de  lea     rax, [rbp+50h+var_C8]
0x1800229e2  mov     [rbp+50h+var_D0], rax
0x1800229e6  lea     r9, [rbp+50h+var_60]
0x1800229ea  lea     r8, [rbp+50h+var_D0]
0x1800229ee  lea     rdx, [rsp+150h+var_D8]
0x1800229f3  lea     rcx, [rsp+150h+var_100]
0x1800229f8  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x1800229fd  nop
0x1800229fe  mov     rbx, [rsp+150h+var_D8]
0x180022a03  test    rbx, rbx
0x180022a06  jz      short loc_180022A0E
0x180022a08  mov     r9, [rbx+10h]
0x180022a0c  jmp     short loc_180022A15
0x180022a0e  lea     r9, S1
0x180022a15  or      r15, 0FFFFFFFFFFFFFFFFh
0x180022a19  mov     rdx, r15
0x180022a1c  inc     rdx
0x180022a1f  cmp     [r9+rdx*2], si
0x180022a24  jnz     short loc_180022A1C
0x180022a26  cmp     rdx, [r14+18h]
0x180022a2a  ja      short loc_180022A5B
0x180022a2c  cmp     qword ptr [r14+18h], 7
0x180022a31  jbe     short loc_180022A38
0x180022a33  mov     rsi, [r14]
0x180022a36  jmp     short loc_180022A3B
0x180022a38  mov     rsi, r14
0x180022a3b  mov     [r14+10h], rdx
0x180022a3f  lea     rdi, [rdx+rdx]
0x180022a43  mov     r8, rdi; Size
0x180022a46  mov     rdx, r9; Src
0x180022a49  mov     rcx, rsi; void *
0x180022a4c  call    memmove_0
0x180022a51  xor     eax, eax
0x180022a53  mov     [rdi+rsi], ax
0x180022a57  xor     esi, esi
0x180022a59  jmp     short loc_180022A63
0x180022a5b  mov     rcx, r14
0x180022a5e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180022a63  mov     [rsp+150h+var_128], rsi
0x180022a68  mov     dword ptr [rbp+50h+var_80+8], r12d
0x180022a6c  mov     dword ptr [rbp+50h+var_80+0Ch], r13d
0x180022a70  lea     rax, aCommandargumen; "commandArguments"
0x180022a77  mov     [rbp+50h+var_68], rax
0x180022a7b  lea     rax, [rbp+50h+var_80+8]
0x180022a7f  mov     [rbp+50h+var_80], rax
0x180022a83  lea     r9, [rsp+150h+var_128]
0x180022a88  lea     r8, [rbp+50h+var_80]
0x180022a8c  lea     rdx, [rsp+150h+var_108]
0x180022a91  lea     rcx, [rsp+150h+var_100]
0x180022a96  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x180022a9b  nop
0x180022a9c  mov     [rsp+150h+var_128], rsi
0x180022aa1  lea     rdx, [rsp+150h+var_128]
0x180022aa6  lea     rcx, [rsp+150h+var_108]
0x180022aab  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180022ab0  test    al, al
0x180022ab2  jnz     loc_180022D89
0x180022ab8  lea     rdx, [rsp+150h+var_110]
0x180022abd  lea     rcx, [rsp+150h+var_108]
0x180022ac2  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x180022ac7  nop
0x180022ac8  mov     [rsp+150h+var_E0], rsi
0x180022acd  lea     rdi, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022ad4  mov     r13, [rsp+150h+var_110]
0x180022ad9  lea     rdx, [rsp+150h+var_E0]
0x180022ade  lea     rcx, [rsp+150h+var_110]
0x180022ae3  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180022ae8  test    al, al
0x180022aea  jnz     loc_180022D79
0x180022af0  mov     [rsp+150h+var_118], rsi
0x180022af5  or      r12d, 4
0x180022af9  mov     [rsp+150h+var_120], r12d
0x180022afe  mov     dword ptr [rbp+50h+var_80], 2Eh ; '.'
0x180022b05  mov     [rbp+50h+var_80+8], rdi
0x180022b09  mov     [rbp+50h+var_70], rsi
0x180022b0d  mov     rax, [r13+0]
0x180022b11  lea     rdx, [rsp+150h+var_118]
0x180022b16  mov     rcx, r13
0x180022b19  mov     rax, [rax+30h]
0x180022b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b22  test    eax, eax
0x180022b24  js      loc_180022E19
0x180022b2a  and     r12d, 0FFFFFFFBh
0x180022b2e  or      r12d, 2
0x180022b32  mov     [rsp+150h+var_120], r12d
0x180022b37  lea     rdx, [rsp+150h+lpMem]
0x180022b3c  lea     rcx, [rsp+150h+var_118]
0x180022b41  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x180022b46  nop
0x180022b47  mov     rdx, [rax]
0x180022b4a  test    rdx, rdx
0x180022b4d  jz      short loc_180022B55
0x180022b4f  mov     rdx, [rdx+10h]
0x180022b53  jmp     short loc_180022B5C
0x180022b55  lea     rdx, S1
0x180022b5c  xorps   xmm0, xmm0
0x180022b5f  movups  [rbp+50h+var_60], xmm0
0x180022b63  xorps   xmm1, xmm1
0x180022b66  movdqu  [rbp+50h+var_50], xmm1
0x180022b6b  mov     r8, r15
0x180022b6e  inc     r8
0x180022b71  cmp     [rdx+r8*2], si
0x180022b76  jnz     short loc_180022B6E
0x180022b78  lea     rcx, [rbp+50h+var_60]
0x180022b7c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022b81  nop
0x180022b82  mov     rdi, [rsp+150h+lpMem]
0x180022b87  test    rdi, rdi
0x180022b8a  jz      short loc_180022BBB
0x180022b8c  mov     eax, r15d
0x180022b8f  lock xadd [rdi+18h], eax
0x180022b94  sub     eax, 1
0x180022b97  jnz     short loc_180022BAE
0x180022b99  nop
0x180022b9a  call    WINRT_IMPL_GetProcessHeap
0x180022b9f  mov     rcx, rax; hHeap
0x180022ba2  mov     r8, rdi; lpMem
0x180022ba5  xor     edx, edx; dwFlags
0x180022ba7  call    WINRT_IMPL_HeapFree
0x180022bac  jmp     short loc_180022BB6
0x180022bae  test    eax, eax
0x180022bb0  js      loc_180022D64
0x180022bb6  mov     [rsp+150h+lpMem], rsi
0x180022bbb  xorps   xmm0, xmm0
0x180022bbe  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x180022bc2  mov     [rbp+50h+var_70], rsi
0x180022bc6  mov     [rbp+50h+var_68], 7
0x180022bce  mov     word ptr [rbp+50h+var_80], si
0x180022bd2  lea     rdx, [rsp+150h+var_128]
0x180022bd7  lea     rcx, [rsp+150h+var_118]
0x180022bdc  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x180022be1  nop
0x180022be2  mov     rax, [rax]
0x180022be5  mov     [rbp+50h+var_A0], rax
0x180022be9  lea     r8, [rbp+50h+var_A0]
0x180022bed  lea     rdx, [rsp+150h+var_E8]
0x180022bf2  lea     rcx, [rsp+150h+var_108]
0x180022bf7  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180022bfc  nop
0x180022bfd  mov     r9, [rax]
0x180022c00  test    r9, r9
0x180022c03  jz      short loc_180022C0B
0x180022c05  mov     r9, [r9+10h]
0x180022c09  jmp     short loc_180022C12
0x180022c0b  lea     r9, S1
0x180022c12  mov     rdx, r15
0x180022c15  inc     rdx
0x180022c18  cmp     [r9+rdx*2], si
0x180022c1d  jnz     short loc_180022C15
0x180022c1f  cmp     rdx, [rbp+50h+var_68]
0x180022c23  ja      short loc_180022C53
0x180022c25  lea     rsi, [rbp+50h+var_80]
0x180022c29  cmp     [rbp+50h+var_68], 7
0x180022c2e  cmova   rsi, [rbp+50h+var_80]
0x180022c33  mov     [rbp+50h+var_70], rdx
0x180022c37  lea     rdi, [rdx+rdx]
0x180022c3b  mov     r8, rdi; Size
0x180022c3e  mov     rdx, r9; Src
0x180022c41  mov     rcx, rsi; void *
0x180022c44  call    memmove_0
0x180022c49  xor     eax, eax
0x180022c4b  mov     [rdi+rsi], ax
0x180022c4f  xor     esi, esi
0x180022c51  jmp     short loc_180022C5D
0x180022c53  lea     rcx, [rbp+50h+var_80]
0x180022c57  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180022c5c  nop
0x180022c5d  mov     rdi, [rsp+150h+var_E8]
0x180022c62  test    rdi, rdi
0x180022c65  jz      short loc_180022C96
0x180022c67  mov     eax, r15d
0x180022c6a  lock xadd [rdi+18h], eax
0x180022c6f  sub     eax, 1
0x180022c72  jnz     short loc_180022C89
0x180022c74  nop
0x180022c75  call    WINRT_IMPL_GetProcessHeap
0x180022c7a  mov     rcx, rax; hHeap
0x180022c7d  mov     r8, rdi; lpMem
0x180022c80  xor     edx, edx; dwFlags
0x180022c82  call    WINRT_IMPL_HeapFree
0x180022c87  jmp     short loc_180022C91
0x180022c89  test    eax, eax
0x180022c8b  js      loc_180022D6B
0x180022c91  mov     [rsp+150h+var_E8], rsi
0x180022c96  mov     rdi, [rsp+150h+var_128]
0x180022c9b  test    rdi, rdi
0x180022c9e  jz      short loc_180022CCF
0x180022ca0  mov     eax, r15d
0x180022ca3  lock xadd [rdi+18h], eax
0x180022ca8  sub     eax, 1
0x180022cab  jnz     short loc_180022CC2
0x180022cad  nop
0x180022cae  call    WINRT_IMPL_GetProcessHeap
0x180022cb3  mov     rcx, rax; hHeap
0x180022cb6  mov     r8, rdi; lpMem
0x180022cb9  xor     edx, edx; dwFlags
0x180022cbb  call    WINRT_IMPL_HeapFree
0x180022cc0  jmp     short loc_180022CCA
0x180022cc2  test    eax, eax
0x180022cc4  js      loc_180022D72
0x180022cca  mov     [rsp+150h+var_128], rsi
0x180022ccf  lea     r9, [rbp+50h+var_80]
0x180022cd3  lea     r8, [rbp+50h+var_60]
0x180022cd7  lea     rdx, [rbp+50h+var_D0]
0x180022cdb  lea     rcx, [r14+20h]
0x180022cdf  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x180022ce4  nop
0x180022ce5  lea     rcx, [rbp+50h+var_80]; void *
0x180022ce9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022cee  nop
0x180022cef  lea     rcx, [rbp+50h+var_60]; void *
0x180022cf3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022cf8  nop
0x180022cf9  cmp     [rsp+150h+var_118], rsi
0x180022cfe  jz      short loc_180022D0A
0x180022d00  lea     rcx, [rsp+150h+var_118]
0x180022d05  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180022d0a  mov     byte ptr [rsp+150h+var_130], sil
0x180022d0f  mov     dword ptr [rbp+50h+var_80], 52h ; 'R'
0x180022d16  lea     rdi, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180022d1d  mov     [rbp+50h+var_80+8], rdi
0x180022d21  mov     [rbp+50h+var_70], rsi
0x180022d25  mov     rax, [r13+0]
0x180022d29  lea     rdx, [rsp+150h+var_130]
0x180022d2e  mov     rcx, r13
0x180022d31  mov     rax, [rax+40h]
0x180022d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d3a  test    eax, eax
0x180022d3c  js      loc_180022E25
0x180022d42  cmp     byte ptr [rsp+150h+var_130], sil
0x180022d47  jnz     loc_180022AD9
  ... truncated ...
```
