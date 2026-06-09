# CMidiConfigurationManager::GetSavedConfigurationForTransport(_GUID)

- ea: `0x140024010`
- end: `0x140024499`
- name: `?GetSavedConfigurationForTransport@CMidiConfigurationManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140030b10`

## callees

- `0x140002670`
- `0x1400054c0`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x1400145bc`
- `0x140023ec8`
- `0x140024010`
- `0x1400250ac`
- `0x140025190`
- `0x1400260e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002423b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002424a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024259`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400242dc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024444`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002423b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002424a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024259`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400242dc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024444`

## string_xrefs

- `0x1400240ee`: `endpointTransportPluginSettings`
- `0x1400241da`: `endpointTransportPluginSettings`
- `0x14002405f`: `CMidiConfigurationManager::GetSavedConfigurationForTransport`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CMidiConfigurationManager::GetSavedConfigurationForTransport(
        __int64 a1,
        __int64 a2,
        volatile signed __int32 *a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  volatile signed __int32 *v9; // rbx
  unsigned int v10; // edx
  struct winrt::impl::shared_hstring_header *v11; // rsi
  unsigned int v12; // edx
  volatile signed __int32 *v13; // r15
  unsigned int v14; // r12d
  const void *v15; // rbx
  char HasKey; // r12
  int v17; // ecx
  HANDLE ProcessHeap; // rax
  int v19; // eax
  HANDLE v20; // rax
  char **v21; // rcx
  char **v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  unsigned __int64 v26; // r8
  void *v27; // rbx
  int v28; // r13d
  HANDLE v29; // rax
  __int64 v31; // [rsp+40h] [rbp-C8h] BYREF
  volatile signed __int32 *v32; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID lpMem[3]; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v34; // [rsp+68h] [rbp-A0h]
  __int64 v35; // [rsp+78h] [rbp-90h]
  __int128 v36; // [rsp+80h] [rbp-88h] BYREF
  __m128i si128; // [rsp+90h] [rbp-78h]
  char *v38[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v40; // [rsp+B8h] [rbp-50h]

  v35 = a2;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v32 = a3;
    v31 = a1;
    lpMem[0] = "CMidiConfigurationManager::GetSavedConfigurationForTransport";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      (__int64)v6,
      (__int64)qword_1400888B8,
      v7,
      v8,
      lpMem);
  }
  *(_OWORD *)lpMem = *(_OWORD *)a3;
  WindowsMidiServicesInternal::GuidToString((__int64)v38, (const IID *)lpMem);
  lpMem[0] = 0;
  v9 = (volatile signed __int32 *)(a1 + 16);
  v32 = (volatile signed __int32 *)(a1 + 16);
  if ( winrt::Windows::Foundation::operator==((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 16), lpMem) )
    goto LABEL_49;
  v11 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x1F, v10);
  memcpy_s((char *)v11 + 28, 0x3Eu, L"endpointTransportPluginSettings", 0x3Eu);
  lpMem[0] = v11;
  if ( !v11 )
    goto LABEL_5;
  if ( (*(_BYTE *)v11 & 1) != 0 )
  {
    v14 = *((_DWORD *)v11 + 1);
    if ( !v14 )
    {
LABEL_5:
      v13 = 0;
      goto LABEL_10;
    }
    v15 = (const void *)*((_QWORD *)v11 + 2);
    v13 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v12);
    memcpy_s((void *const)(v13 + 7), 2LL * v14, v15, 2LL * v14);
    v9 = v32;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v11 + 6);
    v13 = (volatile signed __int32 *)v11;
  }
LABEL_10:
  v32 = v13;
  *(_QWORD *)&v36 = v13;
  HasKey = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
             v9,
             &v36);
  if ( v13 )
  {
    v17 = _InterlockedDecrement(v13 + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
    }
  }
  if ( v11 )
  {
    v19 = _InterlockedDecrement((volatile signed __int32 *)v11 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, v11);
    }
  }
  if ( !HasKey )
    goto LABEL_49;
  lpMem[1] = (LPVOID)0x1F00000001LL;
  v34 = L"endpointTransportPluginSettings";
  lpMem[0] = &lpMem[1];
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    v9,
    &v31,
    lpMem);
  v21 = v38;
  if ( v40 > 7 )
    v21 = (char **)v38[0];
  if ( (_DWORD)v39 )
  {
    if ( *((_WORD *)v21 + (unsigned int)v39) )
      abort();
    DWORD2(v36) = 1;
    HIDWORD(v36) = v39;
    si128.m128i_i64[1] = (__int64)v21;
    *(_QWORD *)&v36 = (char *)&v36 + 8;
  }
  else
  {
    *(_QWORD *)&v36 = 0;
  }
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v31,
                           &v36) )
  {
    if ( v31 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
LABEL_49:
    std::wstring::~wstring(v38);
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)a2, &S2, 0);
    return a2;
  }
  v22 = v38;
  if ( v40 > 7 )
    v22 = (char **)v38[0];
  if ( (_DWORD)v39 )
  {
    if ( *((_WORD *)v22 + (unsigned int)v39) )
      abort();
    DWORD2(v36) = 1;
    HIDWORD(v36) = v39;
    si128.m128i_i64[1] = (__int64)v22;
    *(_QWORD *)&v36 = (char *)&v36 + 8;
  }
  else
  {
    *(_QWORD *)&v36 = 0;
  }
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    &v31,
    &v32,
    &v36);
  v23 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                     &v32,
                     lpMem);
  v36 = 0;
  si128 = 0;
  v24 = *v23;
  if ( v24 )
  {
    v25 = *(const wchar_t **)(v24 + 16);
    v26 = *(unsigned int *)(v24 + 4);
  }
  else
  {
    v25 = &S2;
    v26 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>((char **)&v36, v25, v26);
  v27 = lpMem[0];
  if ( lpMem[0] )
  {
    v28 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v28 )
    {
      if ( v28 < 0 )
        abort();
    }
    else
    {
      v29 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v29, 0, v27);
    }
  }
  *(_OWORD *)a2 = v36;
  *(__m128i *)(a2 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36) = 0;
  std::wstring::~wstring((char **)&v36);
  if ( v32 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
  if ( v31 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v31);
  std::wstring::~wstring(v38);
  return a2;
}

```

## disassembly

```asm
0x140024010  push    rbx
0x140024012  push    rsi
0x140024013  push    rdi
0x140024014  push    r12
0x140024016  push    r13
0x140024018  push    r14
0x14002401a  push    r15
0x14002401c  sub     rsp, 0D0h
0x140024023  mov     rax, cs:__security_cookie
0x14002402a  xor     rax, rsp
0x14002402d  mov     [rsp+108h+var_48], rax
0x140024035  mov     rbx, r8
0x140024038  mov     r14, rdx
0x14002403b  mov     rsi, rcx
0x14002403e  mov     [rsp+108h+var_90], rdx
0x140024043  xor     edi, edi
0x140024045  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002404a  mov     rcx, [rax+8]
0x14002404e  mov     eax, [rcx]
0x140024050  cmp     eax, 4
0x140024053  jbe     short loc_140024096
0x140024055  mov     [rsp+108h+var_C0], rbx
0x14002405a  mov     [rsp+108h+var_C8], rsi
0x14002405f  lea     rax, aCmidiconfigura; "CMidiConfigurationManager::GetSavedConf"...
0x140024066  mov     [rsp+108h+lpMem], rax
0x14002406b  lea     rax, [rsp+108h+var_C0]
0x140024070  mov     [rsp+108h+var_D8], rax
0x140024075  lea     rax, [rsp+108h+var_C8]
0x14002407a  mov     [rsp+108h+var_E0], rax
0x14002407f  lea     rax, [rsp+108h+lpMem]
0x140024084  mov     [rsp+108h+var_E8], rax
0x140024089  lea     rdx, qword_1400888B8
0x140024090  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x140024095  nop
0x140024096  movups  xmm0, xmmword ptr [rbx]
0x140024099  movdqu  xmmword ptr [rsp+108h+lpMem], xmm0
0x14002409f  lea     rdx, [rsp+108h+lpMem]
0x1400240a4  lea     rcx, [rsp+108h+var_68]
0x1400240ac  call    ?GuidToString@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z; WindowsMidiServicesInternal::GuidToString(_GUID)
0x1400240b1  nop
0x1400240b2  mov     [rsp+108h+lpMem], rdi
0x1400240b7  lea     rbx, [rsi+10h]
0x1400240bb  mov     [rsp+108h+var_C0], rbx
0x1400240c0  lea     rdx, [rsp+108h+lpMem]
0x1400240c5  mov     rcx, rbx
0x1400240c8  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1400240cd  test    al, al
0x1400240cf  jnz     loc_14002442B
0x1400240d5  mov     ecx, 1Fh; this
0x1400240da  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1400240df  mov     rsi, rax
0x1400240e2  lea     rcx, [rax+1Ch]; Destination
0x1400240e6  mov     edx, 3Eh ; '>'; DestinationSize
0x1400240eb  mov     r9d, edx; SourceSize
0x1400240ee  lea     r8, aEndpointtransp; "endpointTransportPluginSettings"
0x1400240f5  call    memcpy_s
0x1400240fa  mov     [rsp+108h+lpMem], rsi
0x1400240ff  test    rsi, rsi
0x140024102  jnz     short loc_140024109
0x140024104  mov     r15, rdi
0x140024107  jmp     short loc_140024149
0x140024109  test    byte ptr [rsi], 1
0x14002410c  jnz     short loc_140024117
0x14002410e  lock inc dword ptr [rsi+18h]
0x140024112  mov     r15, rsi
0x140024115  jmp     short loc_140024149
0x140024117  mov     r12d, [rsi+4]
0x14002411b  test    r12d, r12d
0x14002411e  jz      short loc_140024104
0x140024120  mov     rbx, [rsi+10h]
0x140024124  mov     ecx, r12d; this
0x140024127  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14002412c  mov     r15, rax
0x14002412f  mov     edx, r12d
0x140024132  add     rdx, rdx; DestinationSize
0x140024135  lea     rcx, [rax+1Ch]; Destination
0x140024139  mov     r9, rdx; SourceSize
0x14002413c  mov     r8, rbx; Source
0x14002413f  call    memcpy_s
0x140024144  mov     rbx, [rsp+108h+var_C0]
0x140024149  mov     [rsp+108h+var_C0], r15
0x14002414e  mov     qword ptr [rsp+108h+var_88], r15
0x140024156  lea     rdx, [rsp+108h+var_88]
0x14002415e  mov     rcx, rbx
0x140024161  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x140024166  mov     r12b, al
0x140024169  or      r13d, 0FFFFFFFFh
0x14002416d  test    r15, r15
0x140024170  jz      short loc_140024198
0x140024172  mov     ecx, r13d
0x140024175  lock xadd [r15+18h], ecx
0x14002417b  sub     ecx, 1
0x14002417e  jnz     loc_140024233
0x140024184  nop
0x140024185  call    WINRT_IMPL_GetProcessHeap
0x14002418a  mov     rcx, rax; hHeap
0x14002418d  mov     r8, r15; lpMem
0x140024190  xor     edx, edx; dwFlags
0x140024192  call    WINRT_IMPL_HeapFree
0x140024197  nop
0x140024198  test    rsi, rsi
0x14002419b  jz      short loc_1400241C1
0x14002419d  mov     eax, r13d
0x1400241a0  lock xadd [rsi+18h], eax
0x1400241a5  sub     eax, 1
0x1400241a8  jnz     loc_140024242
0x1400241ae  nop
0x1400241af  call    WINRT_IMPL_GetProcessHeap
0x1400241b4  mov     rcx, rax; hHeap
0x1400241b7  mov     r8, rsi; lpMem
0x1400241ba  xor     edx, edx; dwFlags
0x1400241bc  call    WINRT_IMPL_HeapFree
0x1400241c1  test    r12b, r12b
0x1400241c4  jz      loc_14002442B
0x1400241ca  mov     dword ptr [rsp+108h+lpMem+8], 1
0x1400241d2  mov     dword ptr [rsp+108h+lpMem+0Ch], 1Fh
0x1400241da  lea     rax, aEndpointtransp; "endpointTransportPluginSettings"
0x1400241e1  mov     [rsp+108h+var_A0], rax
0x1400241e6  lea     rax, [rsp+108h+lpMem+8]
0x1400241eb  mov     [rsp+108h+lpMem], rax
0x1400241f0  lea     r8, [rsp+108h+lpMem]
0x1400241f5  lea     rdx, [rsp+108h+var_C8]
0x1400241fa  mov     rcx, rbx
0x1400241fd  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x140024202  nop
0x140024203  mov     rdx, [rsp+108h+var_58]
0x14002420b  lea     rcx, [rsp+108h+var_68]
0x140024213  cmp     [rsp+108h+var_50], 7
0x14002421c  cmova   rcx, [rsp+108h+var_68]
0x140024225  test    edx, edx
0x140024227  jnz     short loc_140024251
0x140024229  mov     qword ptr [rsp+108h+var_88], rdi
0x140024231  jmp     short loc_14002428A
0x140024233  test    ecx, ecx
0x140024235  jns     loc_140024198
0x14002423b  call    cs:__imp_abort
0x140024242  test    eax, eax
0x140024244  jns     loc_1400241C1
0x14002424a  call    cs:__imp_abort
0x140024251  mov     eax, edx
0x140024253  cmp     [rcx+rax*2], di
0x140024257  jz      short loc_140024260
0x140024259  call    cs:__imp_abort
0x140024260  mov     dword ptr [rsp+108h+var_88+8], 1
0x14002426b  mov     dword ptr [rsp+108h+var_88+0Ch], edx
0x140024272  mov     [rsp+108h+var_70], rcx
0x14002427a  lea     rax, [rsp+108h+var_88+8]
0x140024282  mov     qword ptr [rsp+108h+var_88], rax
0x14002428a  lea     rdx, [rsp+108h+var_88]
0x140024292  lea     rcx, [rsp+108h+var_C8]
0x140024297  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x14002429c  test    al, al
0x14002429e  jz      loc_140024419
0x1400242a4  mov     rdx, [rsp+108h+var_58]
0x1400242ac  lea     rcx, [rsp+108h+var_68]
0x1400242b4  cmp     [rsp+108h+var_50], 7
0x1400242bd  cmova   rcx, [rsp+108h+var_68]
0x1400242c6  test    edx, edx
0x1400242c8  jnz     short loc_1400242D4
0x1400242ca  mov     qword ptr [rsp+108h+var_88], rdi
0x1400242d2  jmp     short loc_14002430D
0x1400242d4  mov     eax, edx
0x1400242d6  cmp     [rcx+rax*2], di
0x1400242da  jz      short loc_1400242E3
0x1400242dc  call    cs:__imp_abort
0x1400242e3  mov     dword ptr [rsp+108h+var_88+8], 1
0x1400242ee  mov     dword ptr [rsp+108h+var_88+0Ch], edx
0x1400242f5  mov     [rsp+108h+var_70], rcx
0x1400242fd  lea     rax, [rsp+108h+var_88+8]
0x140024305  mov     qword ptr [rsp+108h+var_88], rax
0x14002430d  lea     r8, [rsp+108h+var_88]
0x140024315  lea     rdx, [rsp+108h+var_C0]
0x14002431a  lea     rcx, [rsp+108h+var_C8]
0x14002431f  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x140024324  nop
0x140024325  lea     rdx, [rsp+108h+lpMem]
0x14002432a  lea     rcx, [rsp+108h+var_C0]
0x14002432f  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x140024334  nop
0x140024335  xorps   xmm0, xmm0
0x140024338  movups  [rsp+108h+var_88], xmm0
0x140024340  xorps   xmm1, xmm1
0x140024343  movdqu  xmmword ptr [rsp+90h], xmm1
0x14002434c  mov     rax, [rax]
0x14002434f  test    rax, rax
0x140024352  jz      short loc_14002435E
0x140024354  mov     rdx, [rax+10h]
0x140024358  mov     r8d, [rax+4]
0x14002435c  jmp     short loc_140024368
0x14002435e  lea     rdx, S2
0x140024365  mov     r8, rdi
0x140024368  lea     rcx, [rsp+108h+var_88]
0x140024370  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140024375  nop
0x140024376  mov     rbx, [rsp+108h+lpMem]
0x14002437b  test    rbx, rbx
0x14002437e  jz      short loc_1400243A3
0x140024380  lock xadd [rbx+18h], r13d
0x140024386  sub     r13d, 1
0x14002438a  jnz     loc_14002443B
0x140024390  nop
0x140024391  call    WINRT_IMPL_GetProcessHeap
0x140024396  mov     rcx, rax; hHeap
0x140024399  mov     r8, rbx; lpMem
0x14002439c  xor     edx, edx; dwFlags
0x14002439e  call    WINRT_IMPL_HeapFree
0x1400243a3  movups  xmm0, [rsp+108h+var_88]
0x1400243ab  movups  xmmword ptr [r14], xmm0
0x1400243af  movups  xmm1, xmmword ptr [rsp+90h]
0x1400243b7  movups  xmmword ptr [r14+10h], xmm1
0x1400243bc  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1400243c4  movdqu  xmmword ptr [rsp+90h], xmm0
0x1400243cd  mov     word ptr [rsp+108h+var_88], di
0x1400243d5  lea     rcx, [rsp+108h+var_88]; void *
0x1400243dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400243e2  nop
0x1400243e3  cmp     [rsp+108h+var_C0], rdi
0x1400243e8  jz      short loc_1400243F5
0x1400243ea  lea     rcx, [rsp+108h+var_C0]
0x1400243ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400243f4  nop
0x1400243f5  cmp     [rsp+108h+var_C8], rdi
0x1400243fa  jz      short loc_140024407
0x1400243fc  lea     rcx, [rsp+108h+var_C8]
0x140024401  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024406  nop
0x140024407  lea     rcx, [rsp+108h+var_68]; void *
0x14002440f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024414  mov     rax, r14
0x140024417  jmp     short loc_140024476
0x140024419  cmp     [rsp+108h+var_C8], rdi
0x14002441e  jz      short loc_14002442B
0x140024420  lea     rcx, [rsp+108h+var_C8]
0x140024425  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002442a  nop
0x14002442b  lea     rcx, [rsp+108h+var_68]; void *
0x140024433  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024438  nop
0x140024439  jmp     short loc_140024452
0x14002443b  test    r13d, r13d
0x14002443e  jns     loc_1400243A3
0x140024444  call    cs:__imp_abort
0x14002444b  xor     edi, edi
0x14002444d  mov     r14, [rsp+108h+var_90]
0x140024452  xorps   xmm0, xmm0
0x140024455  movups  xmmword ptr [r14], xmm0
0x140024459  mov     [r14+10h], rdi
0x14002445d  mov     [r14+18h], rdi
0x140024461  xor     r8d, r8d
0x140024464  lea     rdx, S2
0x14002446b  mov     rcx, r14
0x14002446e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140024473  mov     rax, r14
0x140024476  mov     rcx, [rsp+108h+var_48]
0x14002447e  xor     rcx, rsp; StackCookie
0x140024481  call    __security_check_cookie
0x140024486  add     rsp, 0D0h
0x14002448d  pop     r15
0x14002448f  pop     r14
0x140024491  pop     r13
0x140024493  pop     r12
0x140024495  pop     rdi
0x140024496  pop     rsi
0x140024497  pop     rbx
0x140024498  retn
```
