# CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x180027b50`
- end: `0x180027f1d`
- name: `?OnDeviceRemoved@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `973`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017d0`
- `0x180005020`
- `0x180005044`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000d430`
- `0x18000dc8c`
- `0x180010b94`
- `0x1800117d8`
- `0x180013118`
- `0x180013498`
- `0x180014194`
- `0x180019290`
- `0x180019924`
- `0x18001a844`
- `0x1800254f8`
- `0x180027b50`
- `0x180029298`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027d6a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027d79`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027d6a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027d79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027cf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027cf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ec5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ec5`

## string_xrefs

- `0x180027be9`: `CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved`
- `0x180027d00`: `CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved`
- `0x180027dc3`: `Found device to remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _DWORD *v5; // rdi
  const wchar_t *v6; // rsi
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  const wchar_t *v10; // rax
  void *v11; // rdi
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  void *v17; // rdi
  int v18; // ebx
  HANDLE v19; // rax
  wchar_t **v20; // r14
  __int64 v21; // rbx
  const wchar_t *v22; // rdx
  size_t v23; // rdi
  size_t v24; // rsi
  const wchar_t *v25; // rcx
  size_t v26; // r8
  int v27; // eax
  char v28; // al
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  wchar_t **v32; // rax
  wchar_t **v33; // rdx
  int v34; // eax
  __int64 **v35; // rcx
  __int64 v36; // rdx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v39; // rdi
  _QWORD *v40; // r14
  _QWORD *v41; // r13
  int v43; // [rsp+20h] [rbp-B9h]
  LPVOID lpMem; // [rsp+40h] [rbp-99h] BYREF
  const char *v45; // [rsp+48h] [rbp-91h] BYREF
  int v46[2]; // [rsp+50h] [rbp-89h] BYREF
  wchar_t **v47; // [rsp+58h] [rbp-81h] BYREF
  const wchar_t *v48; // [rsp+60h] [rbp-79h] BYREF
  const wchar_t *v49; // [rsp+68h] [rbp-71h] BYREF
  _QWORD *v50; // [rsp+70h] [rbp-69h]
  _QWORD *v51; // [rsp+78h] [rbp-61h]
  _QWORD *v52; // [rsp+80h] [rbp-59h]
  _QWORD *v53; // [rsp+88h] [rbp-51h]
  char v54[32]; // [rsp+90h] [rbp-49h] BYREF
  wchar_t *S1[2]; // [rsp+B0h] [rbp-29h] BYREF
  size_t v56; // [rsp+C0h] [rbp-19h]
  unsigned __int64 v57; // [rsp+C8h] [rbp-11h]
  __int128 v58; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v59; // [rsp+E0h] [rbp+7h]
  __int64 v60; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v50 = a3;
  v51 = a2;
  v47 = (wchar_t **)a1;
  v52 = a2;
  v53 = a3;
  v5 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  v6 = &::S1;
  if ( *v5 > 4u )
  {
    v7 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
           a3,
           &lpMem);
    v10 = *(_QWORD *)v7 ? *(const wchar_t **)(*(_QWORD *)v7 + 16LL) : &::S1;
    v48 = v10;
    v49 = L"Enter";
    *(_QWORD *)v46 = a1;
    v45 = "CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v5,
      (unsigned int)byte_1800891BD,
      v8,
      v9,
      (__int64)&v45,
      (__int64)v46,
      (__int64)&v49,
      (__int64)&v48);
    v11 = lpMem;
    if ( lpMem )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
      }
    }
  }
  v14 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
          a3,
          &lpMem);
  if ( *(_QWORD *)v14 )
    v6 = *(const wchar_t **)(*(_QWORD *)v14 + 16LL);
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v15 = -1;
  do
    ++v15;
  while ( v6[v15] );
  std::wstring::_Construct<1,unsigned short const *>(&v58);
  v16 = std::wstring::wstring(v54, &v58);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v16);
  std::wstring::~wstring(&v58);
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
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, v17);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v49 = (const wchar_t *)(a1 + 32);
  v20 = v47;
  while ( 1 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::_Find_lower_bound<std::wstring>(
      a1 + 72,
      &v58,
      S1);
    v21 = v59;
    if ( *(_BYTE *)(v59 + 25) )
      break;
    v22 = (const wchar_t *)(v59 + 32);
    v23 = *(_QWORD *)(v59 + 48);
    if ( *(_QWORD *)(v59 + 56) > 7u )
      v22 = *(const wchar_t **)v22;
    v24 = v56;
    v25 = (const wchar_t *)S1;
    if ( v57 > 7 )
      v25 = S1[0];
    v26 = v56;
    if ( v23 < v56 )
      v26 = *(_QWORD *)(v59 + 48);
    v27 = wmemcmp(v25, v22, v26);
    if ( v27 )
    {
      if ( v27 < 0 )
        goto LABEL_31;
    }
    else
    {
      if ( v24 < v23 )
      {
LABEL_31:
        v28 = -1;
        goto LABEL_34;
      }
      if ( v24 <= v23 )
        goto LABEL_35;
    }
    v28 = 1;
LABEL_34:
    if ( v28 < 0 )
      break;
LABEL_35:
    if ( v21 == *(_QWORD *)(a1 + 72) )
      break;
    v29 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u )
    {
      v32 = S1;
      if ( v57 > 7 )
        v32 = (wchar_t **)S1[0];
      v47 = v32;
      lpMem = L"Found device to remove";
      v45 = (const char *)v20;
      *(_QWORD *)v46 = "CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v29,
        (unsigned int)qword_180089180,
        v30,
        v31,
        (__int64)v46,
        (__int64)&v45,
        (__int64)&lpMem,
        (__int64)&v47);
    }
    v33 = S1;
    if ( v57 > 7 )
      v33 = (wchar_t **)S1[0];
    v34 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v20[2] + 72LL))(v20[2], v33);
    if ( v34 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DD,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
        (const char *)(unsigned int)v34,
        v43);
    v35 = *(__int64 ***)(v21 + 16);
    v36 = v21;
    if ( *((_BYTE *)v35 + 25) )
    {
      for ( i = *(_QWORD *)(v21 + 8); !*(_BYTE *)(i + 25) && v21 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v21 = i;
    }
    else
    {
      for ( j = *v35; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v39 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>>::_Extract(
            a1 + 72,
            v36);
    KsAggregateEndpointDefinition::~KsAggregateEndpointDefinition((KsAggregateEndpointDefinition *)(v39 + 64));
    std::wstring::~wstring((void *)(v39 + 32));
    operator delete((void *)v39);
  }
  v40 = v50;
  v41 = v51;
  if ( a1 != -32 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  std::wstring::~wstring(S1);
  if ( *v41 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v41);
  if ( *v40 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v40);
  return 0;
}

```

## disassembly

```asm
0x180027b50  mov     [rsp-8+arg_18], rbx
0x180027b55  push    rbp
0x180027b56  push    rsi
0x180027b57  push    rdi
0x180027b58  push    r12
0x180027b5a  push    r13
0x180027b5c  push    r14
0x180027b5e  push    r15
0x180027b60  lea     rbp, [rsp-27h]
0x180027b65  sub     rsp, 100h
0x180027b6c  mov     rax, cs:__security_cookie
0x180027b73  xor     rax, rsp
0x180027b76  mov     [rbp+57h+var_40], rax
0x180027b7a  mov     r14, r8
0x180027b7d  mov     [rbp+57h+var_C0], r8
0x180027b81  mov     [rbp+57h+var_B8], rdx
0x180027b85  mov     r12, rcx
0x180027b88  mov     [rsp+130h+var_D8], rcx
0x180027b8d  mov     [rbp+57h+var_B0], rdx
0x180027b91  mov     [rbp+57h+var_A8], r8
0x180027b95  xor     r15d, r15d
0x180027b98  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180027b9d  mov     rdi, [rax+8]
0x180027ba1  mov     eax, [rdi]
0x180027ba3  lea     rsi, S1
0x180027baa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027bae  cmp     eax, 4
0x180027bb1  jbe     loc_180027C57
0x180027bb7  lea     rdx, [rsp+130h+lpMem]
0x180027bbc  mov     rcx, r14
0x180027bbf  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x180027bc4  mov     rcx, [rax]
0x180027bc7  test    rcx, rcx
0x180027bca  jz      short loc_180027BD2
0x180027bcc  mov     rax, [rcx+10h]
0x180027bd0  jmp     short loc_180027BD5
0x180027bd2  mov     rax, rsi
0x180027bd5  mov     [rbp+57h+var_D0], rax
0x180027bd9  lea     rax, aEnter_0; "Enter"
0x180027be0  mov     [rbp+57h+var_C8], rax
0x180027be4  mov     qword ptr [rsp+130h+var_E0], r12
0x180027be9  lea     rax, aCmidi2ksaggreg_22; "CMidi2KSAggregateMidiEndpointManager::O"...
0x180027bf0  mov     [rsp+130h+var_E8], rax
0x180027bf5  lea     rax, [rbp+57h+var_D0]
0x180027bf9  mov     [rsp+130h+var_F8], rax
0x180027bfe  lea     rax, [rbp+57h+var_C8]
0x180027c02  mov     [rsp+130h+var_100], rax
0x180027c07  lea     rax, [rsp+130h+var_E0]
0x180027c0c  mov     [rsp+130h+var_108], rax
0x180027c11  lea     rax, [rsp+130h+var_E8]
0x180027c16  mov     qword ptr [rsp+130h+var_110], rax
0x180027c1b  lea     rdx, byte_1800891BD
0x180027c22  mov     rcx, rdi
0x180027c25  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027c2a  mov     rdi, [rsp+130h+lpMem]
0x180027c2f  test    rdi, rdi
0x180027c32  jz      short loc_180027C57
0x180027c34  mov     eax, ebx
0x180027c36  lock xadd [rdi+18h], eax
0x180027c3b  sub     eax, 1
0x180027c3e  jnz     loc_180027D62
0x180027c44  nop
0x180027c45  call    WINRT_IMPL_GetProcessHeap
0x180027c4a  mov     rcx, rax; hHeap
0x180027c4d  mov     r8, rdi; lpMem
0x180027c50  xor     edx, edx; dwFlags
0x180027c52  call    WINRT_IMPL_HeapFree
0x180027c57  lea     rdx, [rsp+130h+lpMem]
0x180027c5c  mov     rcx, r14
0x180027c5f  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x180027c64  nop
0x180027c65  mov     rcx, [rax]
0x180027c68  test    rcx, rcx
0x180027c6b  jz      short loc_180027C71
0x180027c6d  mov     rsi, [rcx+10h]
0x180027c71  xorps   xmm0, xmm0
0x180027c74  movups  [rbp+57h+var_60], xmm0
0x180027c78  mov     [rbp+57h+var_50], r15
0x180027c7c  mov     [rbp+57h+var_48], r15
0x180027c80  mov     r8, rbx
0x180027c83  inc     r8
0x180027c86  cmp     [rsi+r8*2], r15w
0x180027c8b  jnz     short loc_180027C83
0x180027c8d  mov     rdx, rsi
0x180027c90  lea     rcx, [rbp+57h+var_60]
0x180027c94  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027c99  nop
0x180027c9a  lea     rdx, [rbp+57h+var_60]
0x180027c9e  lea     rcx, [rbp+57h+var_A0]
0x180027ca2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180027ca7  mov     rdx, rax
0x180027caa  lea     rcx, [rbp+57h+S1]
0x180027cae  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x180027cb3  nop
0x180027cb4  lea     rcx, [rbp+57h+var_60]; void *
0x180027cb8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027cbd  nop
0x180027cbe  mov     rdi, [rsp+130h+lpMem]
0x180027cc3  test    rdi, rdi
0x180027cc6  jz      short loc_180027CE9
0x180027cc8  lock xadd [rdi+18h], ebx
0x180027ccd  sub     ebx, 1
0x180027cd0  jnz     loc_180027D71
0x180027cd6  nop
0x180027cd7  call    WINRT_IMPL_GetProcessHeap
0x180027cdc  mov     rcx, rax; hHeap
0x180027cdf  mov     r8, rdi; lpMem
0x180027ce2  xor     edx, edx; dwFlags
0x180027ce4  call    WINRT_IMPL_HeapFree
0x180027ce9  lea     r15, [r12+20h]
0x180027cee  mov     rcx, r15; lpCriticalSection
0x180027cf1  call    cs:__imp_EnterCriticalSection
0x180027cf7  mov     [rbp+57h+var_C8], r15
0x180027cfb  mov     r14, [rsp+130h+var_D8]
0x180027d00  lea     r13, aCmidi2ksaggreg_22; "CMidi2KSAggregateMidiEndpointManager::O"...
0x180027d07  lea     r8, [rbp+57h+S1]
0x180027d0b  lea     rdx, [rbp+57h+var_60]
0x180027d0f  lea     rcx, [r12+48h]
0x180027d14  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180027d19  mov     rbx, [rbp+57h+var_50]
0x180027d1d  cmp     byte ptr [rbx+19h], 0
0x180027d21  jnz     loc_180027EB5
0x180027d27  lea     rdx, [rbx+20h]
0x180027d2b  mov     rdi, [rdx+10h]
0x180027d2f  cmp     qword ptr [rdx+18h], 7
0x180027d34  jbe     short loc_180027D39
0x180027d36  mov     rdx, [rdx]; S2
0x180027d39  mov     rsi, [rbp+57h+var_70]
0x180027d3d  lea     rcx, [rbp+57h+S1]
0x180027d41  cmp     [rbp+57h+var_68], 7
0x180027d46  cmova   rcx, [rbp+57h+S1]; S1
0x180027d4b  mov     r8, rsi
0x180027d4e  cmp     rdi, rsi
0x180027d51  cmovb   r8, rdi; N
0x180027d55  call    wmemcmp
0x180027d5a  test    eax, eax
0x180027d5c  jz      short loc_180027D80
0x180027d5e  jns     short loc_180027D8B
0x180027d60  jmp     short loc_180027D85
0x180027d62  test    eax, eax
0x180027d64  jns     loc_180027C57
0x180027d6a  call    cs:__imp_abort
0x180027d71  test    ebx, ebx
0x180027d73  jns     loc_180027CE9
0x180027d79  call    cs:__imp_abort
0x180027d80  cmp     rsi, rdi
0x180027d83  jnb     short loc_180027D89
0x180027d85  mov     al, 0FFh
0x180027d87  jmp     short loc_180027D8D
0x180027d89  jbe     short loc_180027D95
0x180027d8b  mov     al, 1
0x180027d8d  test    al, al
0x180027d8f  js      loc_180027EB5
0x180027d95  cmp     rbx, [r12+48h]
0x180027d9a  jz      loc_180027EB5
0x180027da0  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180027da5  mov     rcx, [rax+8]
0x180027da9  mov     eax, [rcx]
0x180027dab  cmp     eax, 4
0x180027dae  jbe     short loc_180027E0D
0x180027db0  lea     rax, [rbp+57h+S1]
0x180027db4  cmp     [rbp+57h+var_68], 7
0x180027db9  cmova   rax, [rbp+57h+S1]
0x180027dbe  mov     [rsp+130h+var_D8], rax
0x180027dc3  lea     rax, aFoundDeviceToR; "Found device to remove"
0x180027dca  mov     [rsp+130h+lpMem], rax
0x180027dcf  mov     [rsp+130h+var_E8], r14
0x180027dd4  mov     qword ptr [rsp+130h+var_E0], r13
0x180027dd9  lea     rax, [rsp+130h+var_D8]
0x180027dde  mov     [rsp+130h+var_F8], rax
0x180027de3  lea     rax, [rsp+130h+lpMem]
0x180027de8  mov     [rsp+130h+var_100], rax
0x180027ded  lea     rax, [rsp+130h+var_E8]
0x180027df2  mov     [rsp+130h+var_108], rax
0x180027df7  lea     rax, [rsp+130h+var_E0]
0x180027dfc  mov     qword ptr [rsp+130h+var_110], rax; int
0x180027e01  lea     rdx, qword_180089180
0x180027e08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027e0d  mov     rcx, [r14+10h]
0x180027e11  mov     rax, [rcx]
0x180027e14  lea     rdx, [rbp+57h+S1]
0x180027e18  cmp     [rbp+57h+var_68], 7
0x180027e1d  cmova   rdx, [rbp+57h+S1]
0x180027e22  mov     rax, [rax+48h]
0x180027e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e2b  mov     rcx, [rbp+5Fh]; this
0x180027e2f  test    eax, eax
0x180027e31  jns     short loc_180027E47
0x180027e33  mov     r9d, eax; char *
0x180027e36  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180027e3d  mov     edx, 4DDh; void *
0x180027e42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027e47  mov     rcx, [rbx+10h]
0x180027e4b  mov     rdx, rbx
0x180027e4e  cmp     byte ptr [rcx+19h], 0
0x180027e52  jz      short loc_180027E6F
0x180027e54  mov     rax, [rbx+8]
0x180027e58  jmp     short loc_180027E67
0x180027e5a  cmp     rbx, [rax+10h]
0x180027e5e  jnz     short loc_180027E84
0x180027e60  mov     rbx, rax
0x180027e63  mov     rax, [rax+8]
0x180027e67  cmp     byte ptr [rax+19h], 0
0x180027e6b  jz      short loc_180027E5A
0x180027e6d  jmp     short loc_180027E84
0x180027e6f  mov     rcx, [rcx]
0x180027e72  cmp     byte ptr [rcx+19h], 0
0x180027e76  jnz     short loc_180027E84
0x180027e78  mov     rax, [rcx]
0x180027e7b  mov     rcx, rax
0x180027e7e  cmp     byte ptr [rax+19h], 0
0x180027e82  jz      short loc_180027E78
0x180027e84  lea     rcx, [r12+48h]
0x180027e89  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>>,std::_Iterator_base0>)
0x180027e8e  mov     rdi, rax
0x180027e91  lea     rcx, [rax+40h]; this
0x180027e95  call    ??1KsAggregateEndpointDefinition@@QEAA@XZ; KsAggregateEndpointDefinition::~KsAggregateEndpointDefinition(void)
0x180027e9a  lea     rcx, [rdi+20h]; void *
0x180027e9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027ea3  mov     edx, 178h
0x180027ea8  mov     rcx, rdi; Block
0x180027eab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027eb0  jmp     loc_180027D07
0x180027eb5  test    r15, r15
0x180027eb8  mov     r14, [rbp+57h+var_C0]
0x180027ebc  mov     r13, [rbp+57h+var_B8]
0x180027ec0  jz      short loc_180027ECC
0x180027ec2  mov     rcx, r15; lpCriticalSection
0x180027ec5  call    cs:__imp_LeaveCriticalSection
0x180027ecb  nop
0x180027ecc  lea     rcx, [rbp+57h+S1]; void *
0x180027ed0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027ed5  nop
0x180027ed6  cmp     qword ptr [r13+0], 0
0x180027edb  jz      short loc_180027EE6
0x180027edd  mov     rcx, r13
0x180027ee0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027ee5  nop
0x180027ee6  cmp     qword ptr [r14], 0
0x180027eea  jz      short loc_180027EF4
0x180027eec  mov     rcx, r14
0x180027eef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027ef4  xor     eax, eax
0x180027ef6  mov     rcx, [rbp+57h+var_40]
0x180027efa  xor     rcx, rsp; StackCookie
0x180027efd  call    __security_check_cookie
0x180027f02  mov     rbx, [rsp+130h+arg_18]
0x180027f0a  add     rsp, 100h
0x180027f11  pop     r15
0x180027f13  pop     r14
0x180027f15  pop     r13
0x180027f17  pop     r12
0x180027f19  pop     rdi
0x180027f1a  pop     rsi
0x180027f1b  pop     rbp
0x180027f1c  retn
```
