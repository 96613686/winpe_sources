# UsageAndQualityInsights::Utilities::ParseAttributes(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x180028510`
- end: `0x1800289b9`
- name: `?ParseAttributes@Utilities@UsageAndQualityInsights@@YA?AV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1193`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800296b4`

## callees

- `0x1800033d0`
- `0x1800038b8`
- `0x180003fac`
- `0x1800040a0`
- `0x180004140`
- `0x180005e7c`
- `0x18000c844`
- `0x18000d9d4`
- `0x18000eee0`
- `0x18001112c`
- `0x180019794`
- `0x180019b64`
- `0x18001a8f4`
- `0x180026730`
- `0x180027ba4`
- `0x180027cc4`
- `0x180027d8c`
- `0x180027f54`
- `0x180028190`
- `0x1800282c0`
- `0x1800283f4`
- `0x180028510`
- `0x18002aa84`
- `0x18002ac8c`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028958`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002895f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028958`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002895f`

## string_xrefs

- `0x1800285a0`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18002899b`: `onecore\base\usageandqualityinsights\service\lib\utilities\metriceventparser.cpp`
- `0x18002898f`: `Unsupported JSON value type for attribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall UsageAndQualityInsights::Utilities::ParseAttributes(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  unsigned int v5; // esi
  int v6; // esi
  int v7; // eax
  int v8; // eax
  __int64 *String; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  unsigned __int64 v12; // r8
  void *v13; // rbx
  int v14; // eax
  HANDLE ProcessHeap; // rax
  _WORD *v16; // rbx
  double Number; // xmm0_8
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // r8
  int v20; // eax
  __int64 v21; // r8
  const wchar_t *v22; // r9
  unsigned __int64 v23; // rdx
  void **v24; // rdi
  __int64 v25; // rbx
  __int64 *v26; // rax
  __int64 v27; // rcx
  const wchar_t *v28; // rdx
  unsigned __int64 v29; // r8
  __int64 v30; // rax
  void *v31; // rbx
  int v32; // eax
  HANDLE v33; // rax
  unsigned int v35; // eax
  const char *v36; // [rsp+28h] [rbp-91h]
  _BYTE v37[4]; // [rsp+30h] [rbp-89h] BYREF
  int v38; // [rsp+34h] [rbp-85h]
  __int64 v39; // [rsp+38h] [rbp-81h] BYREF
  __int64 v40; // [rsp+40h] [rbp-79h] BYREF
  int v41; // [rsp+48h] [rbp-71h] BYREF
  __int64 v42; // [rsp+50h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-61h] BYREF
  LPVOID v44; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v45[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v46; // [rsp+78h] [rbp-41h] BYREF
  __int128 v47; // [rsp+88h] [rbp-31h]
  void *v48[2]; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int64 v49; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v50; // [rsp+B0h] [rbp-9h]
  _BYTE v51[6]; // [rsp+E2h] [rbp+29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v45[1] = a1;
  *a1 = 0;
  a1[1] = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  v5 = 1;
  *((_WORD *)v4 + 12) = 257;
  *a1 = v4;
  v38 = 1;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
    a2,
    &v40);
  v45[0] = 0;
  while ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v40, v45) )
  {
    v42 = 0;
    v6 = v5 | 4;
    v38 = v6;
    LODWORD(v46) = 46;
    *((_QWORD *)&v46 + 1) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    *(_QWORD *)&v47 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, &v42);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v46);
    v5 = v6 & 0xFFFFFFF9 | 2;
    v38 = v5;
    *(_OWORD *)v48 = 0;
    v49 = 0;
    v50 = 7;
    LOWORD(v48[0]) = 0;
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
      &v42,
      &v39);
    v41 = 0;
    LODWORD(v46) = 440;
    *((_QWORD *)&v46 + 1) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    *(_QWORD *)&v47 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 48LL))(v39, &v41);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v46);
    switch ( v41 )
    {
      case 1:
        v37[0] = 0;
        LODWORD(v46) = 512;
        *((_QWORD *)&v46 + 1) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
        *(_QWORD *)&v47 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v39 + 80LL))(v39, v37);
        if ( v20 < 0 )
          winrt::throw_hresult((unsigned int)v20, &v46);
        v22 = L"true";
        if ( !v37[0] )
          v22 = L"false";
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        if ( v23 > v50 )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
            v48,
            v23,
            v21,
            v22);
        }
        else
        {
          v24 = v48;
          if ( v50 > 7 )
            v24 = (void **)v48[0];
          v49 = v23;
          v25 = 2 * v23;
          memmove_0(v24, v22, 2 * v23);
          *(_WORD *)((char *)v24 + v25) = 0;
        }
        break;
      case 2:
        v16 = v51;
        Number = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v39);
        v18 = 0;
        if ( Number >= 9.223372036854776e18 )
        {
          Number = Number - 9.223372036854776e18;
          if ( Number < 9.223372036854776e18 )
            v18 = 0x8000000000000000uLL;
        }
        v19 = v18 + (unsigned int)(int)Number;
        do
        {
          *--v16 = v19 % 0xA + 48;
          v19 /= 0xAu;
        }
        while ( v19 );
        std::wstring::wstring(&v46, v16, v51);
        v5 |= 0x18u;
        v38 = v5;
        std::wstring::operator=(v48, &v46);
        std::wstring::~wstring((char **)&v46);
        break;
      case 3:
        String = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetString(
                              &v39,
                              &lpMem);
        v46 = 0;
        v47 = 0;
        v10 = *String;
        if ( *String )
        {
          v11 = *(const wchar_t **)(v10 + 16);
          v12 = *(unsigned int *)(v10 + 4);
        }
        else
        {
          v11 = &S1;
          v12 = 0;
        }
        std::wstring::_Construct<1,wchar_t const *>((char **)&v46, v11, v12);
        std::wstring::operator=(v48, &v46);
        std::wstring::~wstring((char **)&v46);
        v13 = lpMem;
        if ( lpMem )
        {
          v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v14 )
          {
            if ( v14 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
          }
          lpMem = 0;
        }
        break;
      default:
        v35 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\utilities\\metriceventparser.cpp",
          (const char *)v35,
          (int)"Unsupported JSON value type for attribute",
          v36);
    }
    v26 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                       &v42,
                       &v44);
    v46 = 0;
    v47 = 0;
    v27 = *v26;
    if ( *v26 )
    {
      v28 = *(const wchar_t **)(v27 + 16);
      v29 = *(unsigned int *)(v27 + 4);
    }
    else
    {
      v28 = &S1;
      v29 = 0;
    }
    std::wstring::_Construct<1,wchar_t const *>((char **)&v46, v28, v29);
    v30 = std::map<std::wstring,std::wstring>::operator[](a1, &v46);
    std::wstring::operator=(v30, v48);
    std::wstring::~wstring((char **)&v46);
    v31 = v44;
    if ( v44 )
    {
      v32 = _InterlockedDecrement((volatile signed __int32 *)v44 + 6);
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
      v44 = 0;
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v39);
    std::wstring::~wstring((char **)v48);
    if ( v42 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v42);
    winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v40);
  }
  if ( v40 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v40);
  return a1;
}

```

## disassembly

```asm
0x180028510  mov     [rsp-8+arg_10], rbx
0x180028515  mov     [rsp-8+arg_18], rsi
0x18002851a  push    rbp
0x18002851b  push    rdi
0x18002851c  push    r13
0x18002851e  push    r14
0x180028520  push    r15
0x180028522  lea     rbp, [rsp-37h]
0x180028527  sub     rsp, 0F0h
0x18002852e  mov     rax, cs:__security_cookie
0x180028535  xor     rax, rsp
0x180028538  mov     [rbp+57h+var_28], rax
0x18002853c  mov     rbx, rdx
0x18002853f  mov     r14, rcx
0x180028542  mov     [rbp+57h+var_A0], rcx
0x180028546  xor     r15d, r15d
0x180028549  mov     [rsp+110h+var_DC], r15d
0x18002854e  mov     [rcx], r15
0x180028551  mov     [rcx+8], r15
0x180028555  lea     ecx, [r15+60h]; Size
0x180028559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002855e  mov     [rax], rax
0x180028561  mov     [rax+8], rax
0x180028565  mov     [rax+10h], rax
0x180028569  lea     esi, [r15+1]
0x18002856d  mov     word ptr [rax+18h], 101h
0x180028573  mov     [r14], rax
0x180028576  mov     [rsp+110h+var_DC], esi
0x18002857a  lea     rdx, [rbp+57h+var_D0]
0x18002857e  mov     rcx, rbx
0x180028581  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x180028586  nop
0x180028587  mov     [rbp+57h+var_A8], r15
0x18002858b  lea     rdx, [rbp+57h+var_A8]
0x18002858f  lea     rcx, [rbp+57h+var_D0]
0x180028593  call    ??9Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator!=(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180028598  test    al, al
0x18002859a  jz      loc_18002891E
0x1800285a0  lea     r13, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800285a7  mov     [rbp+57h+var_C0], r15
0x1800285ab  or      esi, 4
0x1800285ae  mov     [rsp+110h+var_DC], esi
0x1800285b2  mov     rcx, [rbp+57h+var_D0]
0x1800285b6  mov     dword ptr [rbp+57h+var_98], 2Eh ; '.'
0x1800285bd  lea     rax, aOnecoreuapInte; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800285c4  mov     qword ptr [rbp+57h+var_98+8], rax
0x1800285c8  mov     qword ptr [rbp+57h+var_88], r15
0x1800285cc  mov     rax, [rcx]
0x1800285cf  lea     rdx, [rbp+57h+var_C0]
0x1800285d3  mov     rax, [rax+30h]
0x1800285d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285dc  test    eax, eax
0x1800285de  js      loc_180028972
0x1800285e4  and     esi, 0FFFFFFFBh
0x1800285e7  or      esi, 2
0x1800285ea  mov     [rsp+110h+var_DC], esi
0x1800285ee  xorps   xmm0, xmm0
0x1800285f1  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800285f5  mov     [rbp+57h+var_68], r15
0x1800285f9  mov     [rbp+57h+var_60], 7
0x180028601  mov     word ptr [rbp+57h+var_78], r15w
0x180028606  lea     rdx, [rsp+110h+var_D8]
0x18002860b  lea     rcx, [rbp+57h+var_C0]
0x18002860f  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(void)
0x180028614  nop
0x180028615  mov     [rbp+57h+var_C8], r15d
0x180028619  mov     rcx, [rsp+110h+var_D8]
0x18002861e  mov     dword ptr [rbp+57h+var_98], 1B8h
0x180028625  mov     qword ptr [rbp+57h+var_98+8], r13
0x180028629  mov     qword ptr [rbp+57h+var_88], r15
0x18002862d  mov     rax, [rcx]
0x180028630  lea     rdx, [rbp+57h+var_C8]
0x180028634  mov     rax, [rax+30h]
0x180028638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002863d  test    eax, eax
0x18002863f  js      loc_180028966
0x180028645  mov     ecx, [rbp+57h+var_C8]
0x180028648  sub     ecx, 1
0x18002864b  jz      loc_1800287A7
0x180028651  sub     ecx, 1
0x180028654  jz      loc_1800286FD
0x18002865a  cmp     ecx, 1
0x18002865d  jnz     loc_18002897E
0x180028663  lea     rdx, [rbp+57h+lpMem]
0x180028667  lea     rcx, [rsp+110h+var_D8]
0x18002866c  call    ?GetString@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetString(void)
0x180028671  nop
0x180028672  xorps   xmm0, xmm0
0x180028675  movups  [rbp+57h+var_98], xmm0
0x180028679  xorps   xmm1, xmm1
0x18002867c  movdqu  [rbp+57h+var_88], xmm1
0x180028681  mov     rcx, [rax]
0x180028684  test    rcx, rcx
0x180028687  jz      short loc_180028693
0x180028689  mov     rdx, [rcx+10h]
0x18002868d  mov     r8d, [rcx+4]
0x180028691  jmp     short loc_18002869D
0x180028693  lea     rdx, S1
0x18002869a  mov     r8, r15
0x18002869d  lea     rcx, [rbp+57h+var_98]
0x1800286a1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800286a6  lea     rdx, [rbp+57h+var_98]
0x1800286aa  lea     rcx, [rbp+57h+var_78]
0x1800286ae  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800286b3  lea     rcx, [rbp+57h+var_98]; void *
0x1800286b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800286bc  nop
0x1800286bd  mov     rbx, [rbp+57h+lpMem]
0x1800286c1  test    rbx, rbx
0x1800286c4  jz      loc_180028838
0x1800286ca  or      eax, 0FFFFFFFFh
0x1800286cd  lock xadd [rbx+18h], eax
0x1800286d2  sub     eax, 1
0x1800286d5  jnz     short loc_1800286EC
0x1800286d7  nop
0x1800286d8  call    WINRT_IMPL_GetProcessHeap
0x1800286dd  mov     rcx, rax; hHeap
0x1800286e0  mov     r8, rbx; lpMem
0x1800286e3  xor     edx, edx; dwFlags
0x1800286e5  call    WINRT_IMPL_HeapFree
0x1800286ea  jmp     short loc_1800286F4
0x1800286ec  test    eax, eax
0x1800286ee  js      loc_180028958
0x1800286f4  mov     [rbp+57h+lpMem], r15
0x1800286f8  jmp     loc_180028838
0x1800286fd  lea     rbx, [rbp+57h+var_2E]
0x180028701  lea     rcx, [rsp+110h+var_D8]
0x180028706  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x18002870b  xor     eax, eax
0x18002870d  comisd  xmm0, cs:__real@43e0000000000000
0x180028715  jb      short loc_180028736
0x180028717  subsd   xmm0, cs:__real@43e0000000000000
0x18002871f  comisd  xmm0, cs:__real@43e0000000000000
0x180028727  jnb     short loc_180028736
0x180028729  mov     rcx, 8000000000000000h
0x180028733  mov     rax, rcx
0x180028736  cvttsd2si r8, xmm0
0x18002873b  add     r8, rax
0x18002873e  sub     rbx, 2
0x180028742  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002874c  mul     r8
0x18002874f  shr     rdx, 3
0x180028753  movzx   eax, dx
0x180028756  shl     ax, 2
0x18002875a  lea     ecx, [rax+rdx]
0x18002875d  add     cx, cx
0x180028760  sub     r8w, cx
0x180028764  add     r8w, 30h ; '0'
0x180028769  mov     [rbx], r8w
0x18002876d  mov     r8, rdx
0x180028770  test    rdx, rdx
0x180028773  jnz     short loc_18002873E
0x180028775  lea     r8, [rbp+57h+var_2E]
0x180028779  mov     rdx, rbx
0x18002877c  lea     rcx, [rbp+57h+var_98]
0x180028780  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x180028785  or      esi, 18h
0x180028788  mov     [rsp+110h+var_DC], esi
0x18002878c  lea     rdx, [rbp+57h+var_98]
0x180028790  lea     rcx, [rbp+57h+var_78]
0x180028794  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028799  lea     rcx, [rbp+57h+var_98]; void *
0x18002879d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800287a2  jmp     loc_180028838
0x1800287a7  mov     [rsp+110h+var_E0], r15b
0x1800287ac  mov     rcx, [rsp+110h+var_D8]
0x1800287b1  mov     dword ptr [rbp+57h+var_98], 200h
0x1800287b8  mov     qword ptr [rbp+57h+var_98+8], r13
0x1800287bc  mov     qword ptr [rbp+57h+var_88], r15
0x1800287c0  mov     rax, [rcx]
0x1800287c3  lea     rdx, [rsp+110h+var_E0]
0x1800287c8  mov     rax, [rax+50h]
0x1800287cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287d1  test    eax, eax
0x1800287d3  js      loc_1800289AD
0x1800287d9  lea     r9, aTrue; "true"
0x1800287e0  lea     rax, aFalse_0; "false"
0x1800287e7  cmp     [rsp+110h+var_E0], r15b
0x1800287ec  cmovz   r9, rax
0x1800287f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800287f4  inc     rdx
0x1800287f7  cmp     [r9+rdx*2], r15w
0x1800287fc  jnz     short loc_1800287F4
0x1800287fe  cmp     rdx, [rbp+57h+var_60]
0x180028802  ja      short loc_18002882F
0x180028804  lea     rdi, [rbp+57h+var_78]
0x180028808  cmp     [rbp+57h+var_60], 7
0x18002880d  cmova   rdi, [rbp+57h+var_78]
0x180028812  mov     [rbp+57h+var_68], rdx
0x180028816  lea     rbx, [rdx+rdx]
0x18002881a  mov     r8, rbx; Size
0x18002881d  mov     rdx, r9; Src
0x180028820  mov     rcx, rdi; void *
0x180028823  call    memmove_0
0x180028828  mov     [rdi+rbx], r15w
0x18002882d  jmp     short loc_180028838
0x18002882f  lea     rcx, [rbp+57h+var_78]
0x180028833  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180028838  lea     rdx, [rbp+57h+var_B0]
0x18002883c  lea     rcx, [rbp+57h+var_C0]
0x180028840  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x180028845  nop
0x180028846  xorps   xmm0, xmm0
0x180028849  movups  [rbp+57h+var_98], xmm0
0x18002884d  xorps   xmm1, xmm1
0x180028850  movdqu  [rbp+57h+var_88], xmm1
0x180028855  mov     rcx, [rax]
0x180028858  test    rcx, rcx
0x18002885b  jz      short loc_180028867
0x18002885d  mov     rdx, [rcx+10h]
0x180028861  mov     r8d, [rcx+4]
0x180028865  jmp     short loc_180028871
0x180028867  lea     rdx, S1
0x18002886e  mov     r8, r15
0x180028871  lea     rcx, [rbp+57h+var_98]
0x180028875  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002887a  nop
0x18002887b  lea     rdx, [rbp+57h+var_98]
0x18002887f  mov     rcx, r14
0x180028882  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028887  mov     rcx, rax
0x18002888a  lea     rdx, [rbp+57h+var_78]
0x18002888e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180028893  nop
0x180028894  lea     rcx, [rbp+57h+var_98]; void *
0x180028898  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002889d  nop
0x18002889e  mov     rbx, [rbp+57h+var_B0]
0x1800288a2  test    rbx, rbx
0x1800288a5  jz      short loc_1800288D5
0x1800288a7  or      eax, 0FFFFFFFFh
0x1800288aa  lock xadd [rbx+18h], eax
0x1800288af  sub     eax, 1
0x1800288b2  jnz     short loc_1800288C9
0x1800288b4  nop
0x1800288b5  call    WINRT_IMPL_GetProcessHeap
0x1800288ba  mov     rcx, rax; hHeap
0x1800288bd  mov     r8, rbx; lpMem
0x1800288c0  xor     edx, edx; dwFlags
0x1800288c2  call    WINRT_IMPL_HeapFree
0x1800288c7  jmp     short loc_1800288D1
0x1800288c9  test    eax, eax
0x1800288cb  js      loc_18002895F
0x1800288d1  mov     [rbp+57h+var_B0], r15
0x1800288d5  cmp     [rsp+110h+var_D8], r15
0x1800288da  jz      short loc_1800288E7
0x1800288dc  lea     rcx, [rsp+110h+var_D8]
0x1800288e1  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800288e6  nop
0x1800288e7  lea     rcx, [rbp+57h+var_78]; void *
0x1800288eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800288f0  nop
0x1800288f1  cmp     [rbp+57h+var_C0], r15
0x1800288f5  jz      short loc_180028900
0x1800288f7  lea     rcx, [rbp+57h+var_C0]
0x1800288fb  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180028900  lea     rcx, [rbp+57h+var_D0]
0x180028904  call    ??E?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEAA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(void)
0x180028909  lea     rdx, [rbp+57h+var_A8]
0x18002890d  lea     rcx, [rbp+57h+var_D0]
0x180028911  call    ??9Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator!=(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180028916  test    al, al
0x180028918  jnz     loc_1800285A7
0x18002891e  cmp     [rbp+57h+var_D0], r15
0x180028922  jz      short loc_18002892D
0x180028924  lea     rcx, [rbp+57h+var_D0]
0x180028928  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002892d  mov     rax, r14
0x180028930  mov     rcx, [rbp+57h+var_28]
0x180028934  xor     rcx, rsp; StackCookie
0x180028937  call    __security_check_cookie
0x18002893c  lea     r11, [rsp+110h+var_20]
0x180028944  mov     rbx, [r11+40h]
0x180028948  mov     rsi, [r11+48h]
0x18002894c  mov     rsp, r11
0x18002894f  pop     r15
0x180028951  pop     r14
0x180028953  pop     r13
0x180028955  pop     rdi
0x180028956  pop     rbp
0x180028957  retn
0x180028958  call    cs:__imp_abort
0x18002895f  call    cs:__imp_abort
0x180028966  lea     rdx, [rbp+57h+var_98]
0x18002896a  mov     ecx, eax
0x18002896c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028972  lea     rdx, [rbp+57h+var_98]
0x180028976  mov     ecx, eax
0x180028978  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002897e  mov     ecx, 80070057h
0x180028983  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180028988  mov     r9d, eax; char *
0x18002898b  mov     rcx, [rbp+5Fh]; this
0x18002898f  lea     rax, aUnsupportedJso; "Unsupported JSON value type for attribu"...
0x180028996  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18002899b  lea     r8, aOnecoreBaseUsa_16; "onecore\\base\\usageandqualityinsights"...
0x1800289a2  mov     edx, 4Ah ; 'J'; void *
0x1800289a7  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800289ad  lea     rdx, [rbp+57h+var_98]
0x1800289b1  mov     ecx, eax
  ... truncated ...
```
