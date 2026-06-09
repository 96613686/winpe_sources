# WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(winrt::Windows::Data::Json::JsonObject)

- ea: `0x1800176ec`
- end: `0x180017c4b`
- name: `?ParseCommand@MidiTransportCommandHelper@WindowsMidiServicesInternal@@SA?AV12@UJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017c54`

## callees

- `0x180004180`
- `0x1800041d0`
- `0x180005000`
- `0x18000509c`
- `0x180005108`
- `0x18000b740`
- `0x18000e178`
- `0x1800145d8`
- `0x180014974`
- `0x180014d48`
- `0x180015464`
- `0x18001656c`
- `0x180016b60`
- `0x180016ca0`
- `0x180016f4c`
- `0x180017024`
- `0x180017168`
- `0x180017620`
- `0x180017690`
- `0x1800176ec`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b17`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b90`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b97`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017c37`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b17`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b90`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017b97`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017c37`

## string_xrefs

- `0x180017786`: `transportCommand`
- `0x1800177f5`: `commandName`
- `0x180017893`: `commandArguments`
- `0x180017a15`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
_QWORD *__fastcall WindowsMidiServicesInternal::MidiTransportCommandHelper::ParseCommand(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rax
  _WORD *v5; // rcx
  volatile signed __int32 *v6; // rdi
  const wchar_t *v7; // r9
  unsigned __int64 v8; // rdx
  char *v9; // rsi
  __int64 v10; // rbx
  LPVOID v11; // rbx
  int v12; // esi
  int v13; // esi
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  __int64 v16; // r8
  void *v17; // r14
  int v18; // eax
  HANDLE ProcessHeap; // rax
  __int64 v20; // rdx
  int v21; // eax
  LPVOID v22; // r13
  const wchar_t *v23; // r9
  unsigned __int64 v24; // rdx
  void **v25; // r14
  __int64 v26; // rsi
  int v27; // eax
  HANDLE v28; // rax
  void *v29; // r14
  int v30; // eax
  HANDLE v31; // rax
  int v32; // r12d
  HANDLE v33; // rax
  LPVOID v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36; // [rsp+28h] [rbp-D8h]
  LPVOID v37; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v38; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v42; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v45; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v46[3]; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v47[3]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v48; // [rsp+A8h] [rbp-58h]
  _BYTE v49[16]; // [rsp+B0h] [rbp-50h] BYREF
  void *v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v51; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-28h]
  _OWORD v53[2]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = a2;
  v42 = a2;
  v47[1] = a1;
  v47[2] = a2;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  a1[4] = 0;
  a1[5] = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  a1[4] = v4;
  v36 = 1;
  v35 = 0;
  v50[1] = (void *)0x1000000001LL;
  v52 = (unsigned __int64)L"transportCommand";
  v50[0] = &v50[1];
  winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
    v2,
    &v40,
    v50,
    &v35);
  v35 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v40, &v35) )
  {
    if ( a1[3] <= 7u )
      v5 = a1;
    else
      v5 = (_WORD *)*a1;
    a1[2] = 0;
    *v5 = 0;
  }
  else
  {
    *(_QWORD *)&v53[0] = 0;
    v46[0] = 0xB00000001LL;
    v46[2] = L"commandName";
    v45 = v46;
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
      &v40,
      v47,
      &v45,
      v53);
    v6 = (volatile signed __int32 *)v47[0];
    if ( v47[0] )
      v7 = (const wchar_t *)*((_QWORD *)v47[0] + 2);
    else
      v7 = &S2;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    if ( v8 > a1[3] )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(a1);
    }
    else
    {
      if ( a1[3] <= 7u )
        v9 = (char *)a1;
      else
        v9 = (char *)*a1;
      a1[2] = v8;
      v10 = 2 * v8;
      memmove_0(v9, v7, 2 * v8);
      *(_WORD *)&v9[v10] = 0;
    }
    v35 = 0;
    v50[1] = (void *)0x1000000001LL;
    v52 = (unsigned __int64)L"commandArguments";
    v50[0] = &v50[1];
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
      &v40,
      &v39,
      v50,
      &v35);
    v35 = 0;
    if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v39, &v35) )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(
        &v39,
        &v37);
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::HasCurrent(&v37) )
      {
        v11 = v37;
        v38 = v37;
      }
      else
      {
        v11 = 0;
        v38 = 0;
        if ( v37 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
      }
      v12 = 7;
      v36 = 7;
      v44 = 0;
      while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v38, &v44) )
      {
        winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Data::Json::IJsonValue>::Current(
          &v38,
          &v41);
        v13 = v12 | 8;
        v36 = v13;
        v14 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                &v41,
                &lpMem);
        if ( *(_QWORD *)v14 )
          v15 = *(const wchar_t **)(*(_QWORD *)v14 + 16LL);
        else
          v15 = &S2;
        memset(v53, 0, sizeof(v53));
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        std::wstring::_Construct<1,unsigned short const *>(v53, v15);
        v17 = lpMem;
        if ( lpMem )
        {
          v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v18 )
          {
            if ( v18 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v17);
          }
          lpMem = 0;
        }
        *(_OWORD *)v50 = 0;
        v51 = 0;
        v52 = 7;
        LOWORD(v50[0]) = 0;
        v20 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                           &v41,
                           &v35);
        v37 = 0;
        LODWORD(v45) = 242;
        v46[0] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
        v46[1] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v39 + 80LL))(v39, v20, &v37);
        if ( v21 < 0 )
          winrt::throw_hresult((unsigned int)v21, &v45);
        v22 = v37;
        v48 = v37;
        v12 = v13 | 0x10;
        LODWORD(v37) = v12;
        v36 = v12;
        if ( v48 )
          v23 = (const wchar_t *)*((_QWORD *)v22 + 2);
        else
          v23 = &S2;
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        if ( v24 > v52 )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(v50);
        }
        else
        {
          v25 = v50;
          if ( v52 > 7 )
            v25 = (void **)v50[0];
          v51 = v24;
          v26 = 2 * v24;
          memmove_0(v25, v23, 2 * v24);
          *(_WORD *)((char *)v25 + v26) = 0;
          v12 = (int)v37;
        }
        if ( v22 )
        {
          v27 = _InterlockedDecrement((volatile signed __int32 *)v22 + 6);
          if ( v27 )
          {
            if ( v27 < 0 )
              abort();
          }
          else
          {
            v28 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v28, 0, v22);
          }
        }
        v29 = v35;
        if ( v35 )
        {
          v30 = _InterlockedDecrement((volatile signed __int32 *)v35 + 6);
          if ( v30 )
          {
            if ( v30 < 0 )
              abort();
          }
          else
          {
            v31 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v31, 0, v29);
          }
          v35 = 0;
        }
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(
          a1 + 4,
          v49,
          v53,
          v50);
        std::wstring::~wstring(v50);
        std::wstring::~wstring(v53);
        if ( v41 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
        if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::MoveNext(&v38) )
        {
          if ( v11 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
          v11 = 0;
          v38 = 0;
        }
      }
      if ( v11 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    if ( v6 )
    {
      v32 = _InterlockedDecrement(v6 + 6);
      if ( v32 )
      {
        if ( v32 < 0 )
          abort();
      }
      else
      {
        v33 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v33, 0, (LPVOID)v6);
      }
    }
    v2 = v42;
  }
  if ( v40 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  return a1;
}

```

## disassembly

```asm
0x1800176ec  mov     [rsp-8+arg_10], rbx
0x1800176f1  push    rbp
0x1800176f2  push    rsi
0x1800176f3  push    rdi
0x1800176f4  push    r12
0x1800176f6  push    r13
0x1800176f8  push    r14
0x1800176fa  push    r15
0x1800176fc  lea     rbp, [rsp-10h]
0x180017701  sub     rsp, 110h
0x180017708  mov     rax, cs:__security_cookie
0x18001770f  xor     rax, rsp
0x180017712  mov     [rbp+40h+var_40], rax
0x180017716  mov     rbx, rdx
0x180017719  mov     [rsp+140h+var_E8], rdx
0x18001771e  mov     r15, rcx
0x180017721  mov     [rbp+40h+var_A8], rcx
0x180017725  mov     [rbp+40h+var_A0], rdx
0x180017729  xor     r13d, r13d
0x18001772c  mov     [rsp+140h+var_118], r13d
0x180017731  xorps   xmm0, xmm0
0x180017734  movups  xmmword ptr [rcx], xmm0
0x180017737  mov     [rcx+10h], r13
0x18001773b  mov     qword ptr [rcx+18h], 7
0x180017743  mov     [rcx], r13w
0x180017747  mov     [rcx+20h], r13
0x18001774b  mov     [rcx+28h], r13
0x18001774f  lea     ecx, [r13+60h]; Size
0x180017753  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017758  mov     [rax], rax
0x18001775b  mov     [rax+8], rax
0x18001775f  mov     [rax+10h], rax
0x180017763  lea     r14d, [r13+1]
0x180017767  mov     word ptr [rax+18h], 101h
0x18001776d  mov     [r15+20h], rax
0x180017771  mov     [rsp+140h+var_118], r14d
0x180017776  mov     [rsp+140h+var_120], r13
0x18001777b  mov     dword ptr [rbp+40h+var_80+8], r14d
0x18001777f  mov     dword ptr [rbp+40h+var_80+0Ch], 10h
0x180017786  lea     rax, aTransportcomma; "transportCommand"
0x18001778d  mov     [rbp+40h+var_68], rax
0x180017791  lea     rax, [rbp+40h+var_80+8]
0x180017795  mov     [rbp+40h+var_80], rax
0x180017799  lea     r9, [rsp+140h+var_120]
0x18001779e  lea     r8, [rbp+40h+var_80]
0x1800177a2  lea     rdx, [rsp+140h+var_F8]
0x1800177a7  mov     rcx, rbx
0x1800177aa  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x1800177af  nop
0x1800177b0  mov     [rsp+140h+var_120], r13
0x1800177b5  lea     rdx, [rsp+140h+var_120]
0x1800177ba  lea     rcx, [rsp+140h+var_F8]
0x1800177bf  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800177c4  test    al, al
0x1800177c6  jz      short loc_1800177E4
0x1800177c8  cmp     qword ptr [r15+18h], 7
0x1800177cd  jbe     short loc_1800177D4
0x1800177cf  mov     rcx, [r15]
0x1800177d2  jmp     short loc_1800177D7
0x1800177d4  mov     rcx, r15
0x1800177d7  mov     [r15+10h], r13
0x1800177db  mov     [rcx], r13w
0x1800177df  jmp     loc_180017BE9
0x1800177e4  mov     qword ptr [rbp+40h+var_60], r13
0x1800177e8  mov     dword ptr [rsp+140h+var_C8], r14d
0x1800177ed  mov     dword ptr [rsp+140h+var_C8+4], 0Bh
0x1800177f5  lea     rax, aCommandname; "commandName"
0x1800177fc  mov     [rbp+40h+var_B8], rax
0x180017800  lea     rax, [rsp+140h+var_C8]
0x180017805  mov     [rsp+140h+var_D0], rax
0x18001780a  lea     r9, [rbp+40h+var_60]
0x18001780e  lea     r8, [rsp+140h+var_D0]
0x180017813  lea     rdx, [rbp+40h+var_B0]
0x180017817  lea     rcx, [rsp+140h+var_F8]
0x18001781c  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x180017821  nop
0x180017822  mov     rdi, [rbp+40h+var_B0]
0x180017826  test    rdi, rdi
0x180017829  jz      short loc_180017831
0x18001782b  mov     r9, [rdi+10h]
0x18001782f  jmp     short loc_180017838
0x180017831  lea     r9, S2
0x180017838  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001783c  mov     rdx, r12
0x18001783f  inc     rdx
0x180017842  cmp     [r9+rdx*2], r13w
0x180017847  jnz     short loc_18001783F
0x180017849  cmp     rdx, [r15+18h]
0x18001784d  ja      short loc_18001787B
0x18001784f  cmp     qword ptr [r15+18h], 7
0x180017854  jbe     short loc_18001785B
0x180017856  mov     rsi, [r15]
0x180017859  jmp     short loc_18001785E
0x18001785b  mov     rsi, r15
0x18001785e  mov     [r15+10h], rdx
0x180017862  lea     rbx, [rdx+rdx]
0x180017866  mov     r8, rbx; Size
0x180017869  mov     rdx, r9; Src
0x18001786c  mov     rcx, rsi; void *
0x18001786f  call    memmove_0
0x180017874  mov     [rbx+rsi], r13w
0x180017879  jmp     short loc_180017883
0x18001787b  mov     rcx, r15
0x18001787e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180017883  mov     [rsp+140h+var_120], r13
0x180017888  mov     dword ptr [rbp+40h+var_80+8], r14d
0x18001788c  mov     dword ptr [rbp+40h+var_80+0Ch], 10h
0x180017893  lea     rax, aCommandargumen; "commandArguments"
0x18001789a  mov     [rbp+40h+var_68], rax
0x18001789e  lea     rax, [rbp+40h+var_80+8]
0x1800178a2  mov     [rbp+40h+var_80], rax
0x1800178a6  lea     r9, [rsp+140h+var_120]
0x1800178ab  lea     r8, [rbp+40h+var_80]
0x1800178af  lea     rdx, [rsp+140h+var_100]
0x1800178b4  lea     rcx, [rsp+140h+var_F8]
0x1800178b9  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x1800178be  nop
0x1800178bf  mov     [rsp+140h+var_120], r13
0x1800178c4  lea     rdx, [rsp+140h+var_120]
0x1800178c9  lea     rcx, [rsp+140h+var_100]
0x1800178ce  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800178d3  test    al, al
0x1800178d5  jnz     loc_180017BAE
0x1800178db  lea     rdx, [rsp+140h+var_110]
0x1800178e0  lea     rcx, [rsp+140h+var_100]
0x1800178e5  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(void)
0x1800178ea  nop
0x1800178eb  lea     rcx, [rsp+140h+var_110]
0x1800178f0  call    ?HasCurrent@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::HasCurrent(void)
0x1800178f5  test    al, al
0x1800178f7  jnz     short loc_180017914
0x1800178f9  mov     rbx, r13
0x1800178fc  mov     [rsp+140h+var_108], rbx
0x180017901  cmp     [rsp+140h+var_110], r13
0x180017906  jz      short loc_18001791E
0x180017908  lea     rcx, [rsp+140h+var_110]
0x18001790d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017912  jmp     short loc_18001791E
0x180017914  mov     rbx, [rsp+140h+var_110]
0x180017919  mov     [rsp+140h+var_108], rbx
0x18001791e  mov     esi, 7
0x180017923  mov     [rsp+140h+var_118], esi
0x180017927  mov     [rsp+140h+var_D8], r13
0x18001792c  lea     rdx, [rsp+140h+var_D8]
0x180017931  lea     rcx, [rsp+140h+var_108]
0x180017936  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001793b  test    al, al
0x18001793d  jnz     loc_180017B9E
0x180017943  lea     rdx, [rsp+140h+var_F0]
0x180017948  lea     rcx, [rsp+140h+var_108]
0x18001794d  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Data::Json::IJsonValue>::Current(void)
0x180017952  or      esi, 8
0x180017955  mov     [rsp+140h+var_118], esi
0x180017959  lea     rdx, [rsp+140h+lpMem]
0x18001795e  lea     rcx, [rsp+140h+var_F0]
0x180017963  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x180017968  nop
0x180017969  mov     rdx, [rax]
0x18001796c  test    rdx, rdx
0x18001796f  jz      short loc_180017977
0x180017971  mov     rdx, [rdx+10h]
0x180017975  jmp     short loc_18001797E
0x180017977  lea     rdx, S2
0x18001797e  xorps   xmm0, xmm0
0x180017981  movups  [rbp+40h+var_60], xmm0
0x180017985  xorps   xmm1, xmm1
0x180017988  movdqu  [rbp+40h+var_50], xmm1
0x18001798d  mov     r8, r12
0x180017990  inc     r8
0x180017993  cmp     [rdx+r8*2], r13w
0x180017998  jnz     short loc_180017990
0x18001799a  lea     rcx, [rbp+40h+var_60]
0x18001799e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800179a3  nop
0x1800179a4  mov     r14, [rsp+140h+lpMem]
0x1800179a9  test    r14, r14
0x1800179ac  jz      short loc_1800179DE
0x1800179ae  mov     eax, r12d
0x1800179b1  lock xadd [r14+18h], eax
0x1800179b7  sub     eax, 1
0x1800179ba  jnz     short loc_1800179D1
0x1800179bc  nop
0x1800179bd  call    WINRT_IMPL_GetProcessHeap
0x1800179c2  mov     rcx, rax; hHeap
0x1800179c5  mov     r8, r14; lpMem
0x1800179c8  xor     edx, edx; dwFlags
0x1800179ca  call    WINRT_IMPL_HeapFree
0x1800179cf  jmp     short loc_1800179D9
0x1800179d1  test    eax, eax
0x1800179d3  js      loc_180017B90
0x1800179d9  mov     [rsp+140h+lpMem], r13
0x1800179de  xorps   xmm0, xmm0
0x1800179e1  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x1800179e5  mov     [rbp+40h+var_70], r13
0x1800179e9  mov     [rbp+40h+var_68], 7
0x1800179f1  mov     word ptr [rbp+40h+var_80], r13w
0x1800179f6  lea     rdx, [rsp+140h+var_120]
0x1800179fb  lea     rcx, [rsp+140h+var_F0]
0x180017a00  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x180017a05  mov     rdx, [rax]
0x180017a08  mov     [rsp+140h+var_110], r13
0x180017a0d  mov     dword ptr [rsp+140h+var_D0], 0F2h
0x180017a15  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180017a1c  mov     [rsp+140h+var_C8], rax
0x180017a21  mov     [rbp+40h+var_C0], r13
0x180017a25  mov     rcx, [rsp+140h+var_100]
0x180017a2a  mov     rax, [rcx]
0x180017a2d  lea     r8, [rsp+140h+var_110]
0x180017a32  mov     rax, [rax+50h]
0x180017a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a3b  test    eax, eax
0x180017a3d  js      loc_180017C3E
0x180017a43  mov     r13, [rsp+140h+var_110]
0x180017a48  mov     [rbp+40h+var_98], r13
0x180017a4c  or      esi, 10h
0x180017a4f  mov     dword ptr [rsp+140h+var_110], esi
0x180017a53  mov     [rsp+140h+var_118], esi
0x180017a57  xor     r14d, r14d
0x180017a5a  test    r13, r13
0x180017a5d  jz      short loc_180017A65
0x180017a5f  mov     r9, [r13+10h]
0x180017a63  jmp     short loc_180017A6C
0x180017a65  lea     r9, S2
0x180017a6c  mov     rdx, r12
0x180017a6f  inc     rdx
0x180017a72  cmp     [r9+rdx*2], r14w
0x180017a77  jnz     short loc_180017A6F
0x180017a79  cmp     rdx, [rbp+40h+var_68]
0x180017a7d  ja      short loc_180017AB0
0x180017a7f  lea     r14, [rbp+40h+var_80]
0x180017a83  cmp     [rbp+40h+var_68], 7
0x180017a88  cmova   r14, [rbp+40h+var_80]
0x180017a8d  mov     [rbp+40h+var_70], rdx
0x180017a91  lea     rsi, [rdx+rdx]
0x180017a95  mov     r8, rsi; Size
0x180017a98  mov     rdx, r9; Src
0x180017a9b  mov     rcx, r14; void *
0x180017a9e  call    memmove_0
0x180017aa3  xor     eax, eax
0x180017aa5  mov     [rsi+r14], ax
0x180017aaa  mov     esi, dword ptr [rsp+140h+var_110]
0x180017aae  jmp     short loc_180017ABA
0x180017ab0  lea     rcx, [rbp+40h+var_80]
0x180017ab4  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180017ab9  nop
0x180017aba  test    r13, r13
0x180017abd  jz      short loc_180017AE0
0x180017abf  mov     eax, r12d
0x180017ac2  lock xadd [r13+18h], eax
0x180017ac8  sub     eax, 1
0x180017acb  jnz     short loc_180017B10
0x180017acd  nop
0x180017ace  call    WINRT_IMPL_GetProcessHeap
0x180017ad3  mov     rcx, rax; hHeap
0x180017ad6  mov     r8, r13; lpMem
0x180017ad9  xor     edx, edx; dwFlags
0x180017adb  call    WINRT_IMPL_HeapFree
0x180017ae0  xor     r13d, r13d
0x180017ae3  mov     r14, [rsp+140h+var_120]
0x180017ae8  test    r14, r14
0x180017aeb  jz      short loc_180017B27
0x180017aed  mov     eax, r12d
0x180017af0  lock xadd [r14+18h], eax
0x180017af6  sub     eax, 1
0x180017af9  jnz     short loc_180017B1E
0x180017afb  nop
0x180017afc  call    WINRT_IMPL_GetProcessHeap
0x180017b01  mov     rcx, rax; hHeap
0x180017b04  mov     r8, r14; lpMem
0x180017b07  xor     edx, edx; dwFlags
0x180017b09  call    WINRT_IMPL_HeapFree
0x180017b0e  jmp     short loc_180017B22
0x180017b10  xor     r13d, r13d
0x180017b13  test    eax, eax
0x180017b15  jns     short loc_180017AE3
0x180017b17  call    cs:__imp_abort
0x180017b1e  test    eax, eax
0x180017b20  js      short loc_180017B97
0x180017b22  mov     [rsp+140h+var_120], r13
0x180017b27  lea     r9, [rbp+40h+var_80]
0x180017b2b  lea     r8, [rbp+40h+var_60]
0x180017b2f  lea     rdx, [rbp+40h+var_90]
0x180017b33  lea     rcx, [r15+20h]
0x180017b37  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x180017b3c  nop
0x180017b3d  lea     rcx, [rbp+40h+var_80]; void *
0x180017b41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b46  nop
0x180017b47  lea     rcx, [rbp+40h+var_60]; void *
0x180017b4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b50  nop
0x180017b51  cmp     [rsp+140h+var_F0], r13
0x180017b56  jz      short loc_180017B62
0x180017b58  lea     rcx, [rsp+140h+var_F0]
0x180017b5d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017b62  lea     rcx, [rsp+140h+var_108]
0x180017b67  call    ?MoveNext@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::MoveNext(void)
0x180017b6c  test    al, al
0x180017b6e  jnz     loc_18001792C
0x180017b74  test    rbx, rbx
  ... truncated ...
```
