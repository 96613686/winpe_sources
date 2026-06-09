# CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice(winrt::Windows::Devices::Enumeration::DeviceInformation,std::shared_ptr<KsAggregateEndpointDefinition2> &)

- ea: `0x1800365e8`
- end: `0x180036d56`
- name: `?CreatePendingEndpointDefinitionForFilterDevice@CMidi2KSAggregateMidiEndpointManager2@@AEAAJUDeviceInformation@Enumeration@Devices@Windows@winrt@@AEAV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@@Z`
- size: `1902`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18003c890`

## callees

- `0x1800016dc`
- `0x1800017d0`
- `0x180005020`
- `0x180005070`
- `0x180005e9c`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000b394`
- `0x18000d430`
- `0x180010b94`
- `0x1800117d8`
- `0x18001996c`
- `0x18001aa6c`
- `0x18001f870`
- `0x180021b3c`
- `0x1800229bc`
- `0x18002548c`
- `0x18002aba0`
- `0x180033838`
- `0x180033928`
- `0x180034024`
- `0x1800344e4`
- `0x1800365e8`
- `0x180039ef0`
- `0x18003add4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180036792`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180036792`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180036c41`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180036c41`

## string_xrefs

- `0x18003662d`: `CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice`
- `0x180036c02`: `CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice(
        __int64 a1,
        LARGE_INTEGER *a2,
        __int64 a3)
{
  _DWORD *v6; // rbx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  const wchar_t *v10; // rax
  void *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  LARGE_INTEGER v14; // rcx
  int ParentDeviceDefinitionForFilterDevice; // eax
  unsigned int v16; // edi
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v19; // rbx
  bool v20; // zf
  char *v21; // rdi
  volatile signed __int32 *v22; // rbx
  int UnusedEndpointIndexForParentDevice; // eax
  unsigned int v24; // r15d
  volatile signed __int32 *v25; // rbx
  DWORD LowPart; // ebx
  _QWORD *v27; // rcx
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // r9
  _WORD *v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int128 *v34; // rax
  LPVOID *v35; // rcx
  DWORD v36; // ebx
  __int64 v37; // rax
  __int64 v38; // rax
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  _QWORD *v42; // rdx
  volatile signed __int32 *v43; // rbx
  int v44; // [rsp+20h] [rbp-E0h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v46; // [rsp+50h] [rbp-B0h] BYREF
  const char *v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v49[4]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v51; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v53; // [rsp+C8h] [rbp-38h]
  _BYTE Src[42]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[6]; // [rsp+FAh] [rbp-6h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v49[2] = a2;
  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v7 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
           a2,
           lpMem);
    v10 = *(_QWORD *)v7 ? *(const wchar_t **)(*(_QWORD *)v7 + 16LL) : &S1;
    PerformanceCount.QuadPart = (LONGLONG)v10;
    v49[0] = L"Enter.";
    v47 = (const char *)a1;
    *(_QWORD *)v48 = "CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)byte_18008A0DD,
      v8,
      v9,
      (__int64)v48,
      (__int64)&v47,
      (__int64)v49,
      (__int64)&PerformanceCount);
    v11 = lpMem[0];
    if ( lpMem[0] )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
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
  v46 = 0;
  v14 = *a2;
  PerformanceCount = v14;
  if ( v14.QuadPart )
    (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v14.QuadPart + 8LL))(v14);
  ParentDeviceDefinitionForFilterDevice = CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice(
                                            a1,
                                            (__int64 *)&PerformanceCount,
                                            (const wchar_t *)&v46);
  v16 = ParentDeviceDefinitionForFilterDevice;
  if ( ParentDeviceDefinitionForFilterDevice < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x640,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)ParentDeviceDefinitionForFilterDevice,
      v44);
    v17 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    if ( a2->QuadPart )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return v16;
  }
  if ( !(_QWORD)v46 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x642,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80004003LL,
      v44);
    v19 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = a2->QuadPart == 0;
LABEL_35:
    if ( !v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 2147500035LL;
  }
  v21 = (char *)operator new(0x110u);
  lpMem[0] = v21;
  *(_OWORD *)v21 = 0;
  *((_DWORD *)v21 + 2) = 1;
  *((_DWORD *)v21 + 3) = 1;
  *(_QWORD *)v21 = &std::_Ref_count_obj2<KsAggregateEndpointDefinition2>::`vftable';
  memset_0(v21 + 16, 0, 0x100u);
  KsAggregateEndpointDefinition2::KsAggregateEndpointDefinition2((KsAggregateEndpointDefinition2 *)(v21 + 16));
  v49[0] = v21 + 16;
  v49[1] = v21;
  if ( v21 == (char *)-16LL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80004003LL,
      v44);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL, 0xFFFFFFFF) == 1 )
    {
      ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
    }
    v22 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
    v20 = a2->QuadPart == 0;
    goto LABEL_35;
  }
  PerformanceCount.LowPart = 0;
  *(_OWORD *)lpMem = 0;
  if ( *((_QWORD *)&v46 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL));
  *(_OWORD *)lpMem = v46;
  UnusedEndpointIndexForParentDevice = CMidi2KSAggregateMidiEndpointManager2::FindUnusedEndpointIndexForParentDevice(
                                         a1,
                                         lpMem,
                                         &PerformanceCount);
  v24 = UnusedEndpointIndexForParentDevice;
  if ( UnusedEndpointIndexForParentDevice >= 0 )
  {
    LowPart = PerformanceCount.LowPart;
    *((_DWORD *)v21 + 62) = PerformanceCount.LowPart;
    std::wstring::operator=(v21 + 16, v46 + 32);
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v27 = (_QWORD *)(v46 + 32);
    if ( *(_QWORD *)(v46 + 56) > 7u )
      v27 = (_QWORD *)*v27;
    v28 = 0xCBF29CE484222325uLL;
    v29 = 0;
    v30 = 2LL * *(_QWORD *)(v46 + 48);
    if ( v30 )
    {
      do
        v28 = 0x100000001B3LL * (*((unsigned __int8 *)v27 + v29++) ^ v28);
      while ( v29 < v30 );
    }
    v31 = v55;
    do
    {
      *--v31 = v28 % 0xA + 48;
      v28 /= 0xAu;
    }
    while ( v28 );
    std::wstring::wstring(lpMem, v31, v55);
    std::wstring::operator=(&v51, lpMem);
    std::wstring::~wstring(lpMem);
    if ( LowPart )
    {
      v36 = LowPart + 1;
      PerformanceCount.LowPart = v36;
      lpMem[0] = L"{0}{1}_{2:0>3}";
      lpMem[1] = (LPVOID)14;
      v37 = std::format<unsigned short const (&)[11],std::wstring &,unsigned int>(Src, (__int64)&PerformanceCount);
      std::wstring::operator=(v21 + 112, v37);
      std::wstring::~wstring(Src);
      PerformanceCount.LowPart = v36;
      lpMem[0] = L"{0} ({1})";
      lpMem[1] = (LPVOID)9;
      v38 = std::format<std::wstring &,unsigned int>(Src);
      std::wstring::operator=(v21 + 80, v38);
      v35 = (LPVOID *)Src;
    }
    else
    {
      std::wstring::operator=(v21 + 80, v46);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v52) < 0xA )
        std::_Xlen_string();
      v34 = &v51;
      if ( v53 > 7 )
        v34 = (__int128 *)v51;
      std::wstring::wstring(lpMem, v32, v33, L"MIDIU_KSA_", 10, v34, v52);
      std::wstring::operator=(v21 + 112, lpMem);
      v35 = lpMem;
    }
    std::wstring::~wstring(v35);
    v39 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v39 > 4u )
    {
      lpMem[0] = L"Adding pending aggregate UMP endpoint.";
      *(_QWORD *)v48 = a1;
      v47 = "CMidi2KSAggregateMidiEndpointManager2::CreatePendingEndpointDefinitionForFilterDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v39,
        (unsigned int)byte_18008A0AB,
        v40,
        v41,
        (__int64)&v47,
        (__int64)v48,
        (__int64)lpMem);
    }
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    _InterlockedExchange64((volatile __int64 *)v21 + 32, PerformanceCount.QuadPart);
    v42 = *(_QWORD **)(a1 + 112);
    if ( v42 == *(_QWORD **)(a1 + 120) )
    {
      std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::_Emplace_reallocate<std::shared_ptr<KsAggregateEndpointDefinition2> const &>(
        a1 + 104,
        v42,
        v49);
    }
    else
    {
      *v42 = 0;
      v42[1] = 0;
      _InterlockedIncrement((volatile signed __int32 *)v21 + 2);
      *v42 = v21 + 16;
      v42[1] = v21;
      *(_QWORD *)(a1 + 112) += 16LL;
    }
    std::shared_ptr<KsAggregateEndpointDefinition2>::operator=(a3, v49);
    std::wstring::~wstring(&v51);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v21)(v21);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
    }
    v43 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
        if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
      }
    }
    if ( a2->QuadPart )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x654,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)UnusedEndpointIndexForParentDevice,
      v44);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v21)(v21);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
    }
    v25 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    if ( a2->QuadPart )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return v24;
  }
}

```

## disassembly

```asm
0x1800365e8  mov     [rsp-8+arg_18], rbx
0x1800365ed  push    rbp
0x1800365ee  push    rsi
0x1800365ef  push    rdi
0x1800365f0  push    r12
0x1800365f2  push    r13
0x1800365f4  push    r14
0x1800365f6  push    r15
0x1800365f8  lea     rbp, [rsp-10h]
0x1800365fd  sub     rsp, 110h
0x180036604  mov     rax, cs:__security_cookie
0x18003660b  xor     rax, rsp
0x18003660e  mov     [rbp+40h+var_40], rax
0x180036612  mov     r12, r8
0x180036615  mov     rsi, rdx
0x180036618  mov     r13, rcx
0x18003661b  mov     [rbp+40h+var_C0], rdx
0x18003661f  xor     r14d, r14d
0x180036622  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180036627  mov     rbx, [rax+8]
0x18003662b  mov     eax, [rbx]
0x18003662d  lea     rdi, aCmidi2ksaggreg; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180036634  or      r15d, 0FFFFFFFFh
0x180036638  cmp     eax, 4
0x18003663b  jbe     loc_1800366E1
0x180036641  lea     rdx, [rbp+40h+lpMem]
0x180036645  mov     rcx, rsi
0x180036648  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x18003664d  mov     rcx, [rax]
0x180036650  test    rcx, rcx
0x180036653  jz      short loc_18003665B
0x180036655  mov     rax, [rcx+10h]
0x180036659  jmp     short loc_180036662
0x18003665b  lea     rax, S1
0x180036662  mov     qword ptr [rsp+140h+PerformanceCount], rax
0x180036667  lea     rax, aEnter; "Enter."
0x18003666e  mov     [rsp+140h+var_D0], rax
0x180036673  mov     [rsp+140h+var_E0], r13
0x180036678  mov     qword ptr [rsp+140h+var_D8], rdi
0x18003667d  lea     rax, [rsp+140h+PerformanceCount]
0x180036682  mov     [rsp+140h+var_108], rax
0x180036687  lea     rax, [rsp+140h+var_D0]
0x18003668c  mov     [rsp+140h+var_110], rax
0x180036691  lea     rax, [rsp+140h+var_E0]
0x180036696  mov     [rsp+140h+var_118], rax
0x18003669b  lea     rax, [rsp+140h+var_D8]
0x1800366a0  mov     [rsp+140h+var_120], rax; int
0x1800366a5  lea     rdx, byte_18008A0DD
0x1800366ac  mov     rcx, rbx
0x1800366af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800366b4  mov     rbx, [rbp+40h+lpMem]
0x1800366b8  test    rbx, rbx
0x1800366bb  jz      short loc_1800366E1
0x1800366bd  mov     eax, r15d
0x1800366c0  lock xadd [rbx+18h], eax
0x1800366c5  sub     eax, 1
0x1800366c8  jnz     loc_18003678A
0x1800366ce  nop
0x1800366cf  call    WINRT_IMPL_GetProcessHeap
0x1800366d4  mov     rcx, rax; hHeap
0x1800366d7  mov     r8, rbx; lpMem
0x1800366da  xor     edx, edx; dwFlags
0x1800366dc  call    WINRT_IMPL_HeapFree
0x1800366e1  xorps   xmm0, xmm0
0x1800366e4  movdqa  [rsp+140h+var_F0], xmm0
0x1800366ea  mov     rcx, [rsi]
0x1800366ed  mov     qword ptr [rsp+140h+PerformanceCount], rcx
0x1800366f2  test    rcx, rcx
0x1800366f5  jz      short loc_180036703
0x1800366f7  mov     rax, [rcx]
0x1800366fa  mov     rax, [rax+8]
0x1800366fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036703  lea     r8, [rsp+140h+var_F0]
0x180036708  lea     rdx, [rsp+140h+PerformanceCount]
0x18003670d  mov     rcx, r13
0x180036710  call    ?FindOrCreateParentDeviceDefinitionForFilterDevice@CMidi2KSAggregateMidiEndpointManager2@@AEAAJUDeviceInformation@Enumeration@Devices@Windows@winrt@@AEAV?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@std@@@Z; CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice(winrt::Windows::Devices::Enumeration::DeviceInformation,std::shared_ptr<KsAggregateParentDeviceDefinition2> &)
0x180036715  mov     edi, eax
0x180036717  test    eax, eax
0x180036719  jns     short loc_180036799
0x18003671b  mov     rcx, [rbp+48h]; this
0x18003671f  mov     r9d, eax; char *
0x180036722  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180036729  mov     edx, 640h; void *
0x18003672e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036733  nop
0x180036734  mov     rbx, qword ptr [rsp+140h+var_F0+8]
0x180036739  test    rbx, rbx
0x18003673c  jz      short loc_180036776
0x18003673e  mov     eax, r15d
0x180036741  lock xadd [rbx+8], eax
0x180036746  add     eax, r15d
0x180036749  jnz     short loc_180036776
0x18003674b  mov     rax, [rbx]
0x18003674e  mov     rcx, rbx
0x180036751  mov     rax, [rax]
0x180036754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036759  mov     eax, r15d
0x18003675c  lock xadd [rbx+0Ch], eax
0x180036761  add     eax, r15d
0x180036764  jnz     short loc_180036776
0x180036766  mov     rax, [rbx]
0x180036769  mov     rcx, rbx
0x18003676c  mov     rax, [rax+8]
0x180036770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036775  nop
0x180036776  cmp     [rsi], r14
0x180036779  jz      short loc_180036783
0x18003677b  mov     rcx, rsi
0x18003677e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180036783  mov     eax, edi
0x180036785  jmp     loc_180036D29
0x18003678a  test    eax, eax
0x18003678c  jns     loc_1800366E1
0x180036792  call    cs:__imp_abort
0x180036799  cmp     qword ptr [rsp+140h+var_F0], r14
0x18003679e  jnz     short loc_180036806
0x1800367a0  mov     rcx, [rbp+48h]; this
0x1800367a4  mov     r9d, 80004003h; char *
0x1800367aa  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800367b1  mov     edx, 642h; void *
0x1800367b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800367bb  nop
0x1800367bc  mov     rbx, qword ptr [rsp+140h+var_F0+8]
0x1800367c1  test    rbx, rbx
0x1800367c4  jz      short loc_1800367FE
0x1800367c6  mov     eax, r15d
0x1800367c9  lock xadd [rbx+8], eax
0x1800367ce  add     eax, r15d
0x1800367d1  jnz     short loc_1800367FE
0x1800367d3  mov     rax, [rbx]
0x1800367d6  mov     rcx, rbx
0x1800367d9  mov     rax, [rax]
0x1800367dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367e1  mov     eax, r15d
0x1800367e4  lock xadd [rbx+0Ch], eax
0x1800367e9  add     eax, r15d
0x1800367ec  jnz     short loc_1800367FE
0x1800367ee  mov     rax, [rbx]
0x1800367f1  mov     rcx, rbx
0x1800367f4  mov     rax, [rax+8]
0x1800367f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367fd  nop
0x1800367fe  cmp     [rsi], r14
0x180036801  jmp     loc_1800368FF
0x180036806  mov     ecx, 110h; Size
0x18003680b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036810  mov     rdi, rax
0x180036813  mov     [rbp+40h+lpMem], rax
0x180036817  xorps   xmm0, xmm0
0x18003681a  movups  xmmword ptr [rax], xmm0
0x18003681d  mov     dword ptr [rax+8], 1
0x180036824  mov     dword ptr [rax+0Ch], 1
0x18003682b  lea     rax, ??_7?$_Ref_count_obj2@UKsAggregateEndpointDefinition2@@@std@@6B@; const std::_Ref_count_obj2<KsAggregateEndpointDefinition2>::`vftable'
0x180036832  mov     [rdi], rax
0x180036835  lea     r14, [rdi+10h]
0x180036839  xor     edx, edx; Val
0x18003683b  mov     r8d, 100h; Size
0x180036841  mov     rcx, r14; void *
0x180036844  call    memset_0
0x180036849  mov     rcx, r14; this
0x18003684c  call    ??0KsAggregateEndpointDefinition2@@QEAA@XZ; KsAggregateEndpointDefinition2::KsAggregateEndpointDefinition2(void)
0x180036851  nop
0x180036852  mov     [rsp+140h+var_D0], r14
0x180036857  mov     [rsp+140h+var_C8], rdi
0x18003685c  test    r14, r14
0x18003685f  jnz     loc_180036913
0x180036865  mov     rcx, [rbp+48h]; this
0x180036869  mov     r9d, 80004003h; char *
0x18003686f  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180036876  mov     edx, 646h; void *
0x18003687b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036880  nop
0x180036881  mov     eax, r15d
0x180036884  lock xadd [rdi+8], eax
0x180036889  add     eax, r15d
0x18003688c  jnz     short loc_1800368B9
0x18003688e  mov     rax, [rdi]
0x180036891  mov     rcx, rdi
0x180036894  mov     rax, [rax]
0x180036897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003689c  mov     eax, r15d
0x18003689f  lock xadd [rdi+0Ch], eax
0x1800368a4  add     eax, r15d
0x1800368a7  jnz     short loc_1800368B9
0x1800368a9  mov     rax, [rdi]
0x1800368ac  mov     rcx, rdi
0x1800368af  mov     rax, [rax+8]
0x1800368b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368b8  nop
0x1800368b9  mov     rbx, qword ptr [rsp+140h+var_F0+8]
0x1800368be  test    rbx, rbx
0x1800368c1  jz      short loc_1800368FB
0x1800368c3  mov     eax, r15d
0x1800368c6  lock xadd [rbx+8], eax
0x1800368cb  add     eax, r15d
0x1800368ce  jnz     short loc_1800368FB
0x1800368d0  mov     rax, [rbx]
0x1800368d3  mov     rcx, rbx
0x1800368d6  mov     rax, [rax]
0x1800368d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368de  mov     eax, r15d
0x1800368e1  lock xadd [rbx+0Ch], eax
0x1800368e6  add     eax, r15d
0x1800368e9  jnz     short loc_1800368FB
0x1800368eb  mov     rax, [rbx]
0x1800368ee  mov     rcx, rbx
0x1800368f1  mov     rax, [rax+8]
0x1800368f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368fa  nop
0x1800368fb  cmp     qword ptr [rsi], 0
0x1800368ff  jz      short loc_180036909
0x180036901  mov     rcx, rsi
0x180036904  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180036909  mov     eax, 80004003h
0x18003690e  jmp     loc_180036D29
0x180036913  mov     dword ptr [rsp+140h+PerformanceCount], 0
0x18003691b  xorps   xmm0, xmm0
0x18003691e  movdqa  xmmword ptr [rbp+40h+lpMem], xmm0
0x180036923  mov     rax, qword ptr [rsp+140h+var_F0+8]
0x180036928  test    rax, rax
0x18003692b  jz      short loc_180036931
0x18003692d  lock inc dword ptr [rax+8]
0x180036931  movaps  xmm0, [rsp+140h+var_F0]
0x180036936  movdqa  xmmword ptr [rbp+40h+lpMem], xmm0
0x18003693b  lea     r8, [rsp+140h+PerformanceCount]
0x180036940  lea     rdx, [rbp+40h+lpMem]
0x180036944  mov     rcx, r13
0x180036947  call    ?FindUnusedEndpointIndexForParentDevice@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@std@@AEAI@Z; CMidi2KSAggregateMidiEndpointManager2::FindUnusedEndpointIndexForParentDevice(std::shared_ptr<KsAggregateParentDeviceDefinition2>,uint &)
0x18003694c  mov     r15d, eax
0x18003694f  test    eax, eax
0x180036951  jns     loc_180036A04
0x180036957  mov     rcx, [rbp+48h]; this
0x18003695b  mov     r9d, eax; char *
0x18003695e  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180036965  mov     edx, 654h; void *
0x18003696a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003696f  nop
0x180036970  or      r14d, 0FFFFFFFFh
0x180036974  mov     ecx, r14d
0x180036977  lock xadd [rdi+8], ecx
0x18003697c  add     ecx, r14d
0x18003697f  jnz     short loc_1800369AC
0x180036981  mov     rax, [rdi]
0x180036984  mov     rcx, rdi
0x180036987  mov     rax, [rax]
0x18003698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003698f  mov     eax, r14d
0x180036992  lock xadd [rdi+0Ch], eax
0x180036997  add     eax, r14d
0x18003699a  jnz     short loc_1800369AC
0x18003699c  mov     rax, [rdi]
0x18003699f  mov     rcx, rdi
0x1800369a2  mov     rax, [rax+8]
0x1800369a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369ab  nop
0x1800369ac  mov     rbx, qword ptr [rsp+140h+var_F0+8]
0x1800369b1  test    rbx, rbx
0x1800369b4  jz      short loc_1800369EE
0x1800369b6  mov     eax, r14d
0x1800369b9  lock xadd [rbx+8], eax
0x1800369be  add     eax, r14d
0x1800369c1  jnz     short loc_1800369EE
0x1800369c3  mov     rax, [rbx]
0x1800369c6  mov     rcx, rbx
0x1800369c9  mov     rax, [rax]
0x1800369cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369d1  mov     eax, r14d
0x1800369d4  lock xadd [rbx+0Ch], eax
0x1800369d9  add     eax, r14d
0x1800369dc  jnz     short loc_1800369EE
0x1800369de  mov     rax, [rbx]
0x1800369e1  mov     rcx, rbx
0x1800369e4  mov     rax, [rax+8]
0x1800369e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369ed  nop
0x1800369ee  cmp     qword ptr [rsi], 0
0x1800369f2  jz      short loc_1800369FC
0x1800369f4  mov     rcx, rsi
0x1800369f7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800369fc  mov     eax, r15d
0x1800369ff  jmp     loc_180036D29
0x180036a04  mov     ebx, dword ptr [rsp+140h+PerformanceCount]
0x180036a08  mov     [r14+0E8h], ebx
0x180036a0f  mov     rdx, qword ptr [rsp+140h+var_F0]
0x180036a14  add     rdx, 20h ; ' '
0x180036a18  mov     rcx, r14
0x180036a1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036a20  xorps   xmm0, xmm0
0x180036a23  movups  [rbp+40h+var_90], xmm0
0x180036a27  xor     r15d, r15d
0x180036a2a  mov     [rbp+40h+var_80], r15
0x180036a2e  mov     [rbp+40h+var_78], 7
0x180036a36  mov     word ptr [rbp+40h+var_90], r15w
0x180036a3b  mov     rcx, qword ptr [rsp+140h+var_F0]
0x180036a40  add     rcx, 20h ; ' '
0x180036a44  mov     r9, [rcx+10h]
0x180036a48  cmp     qword ptr [rcx+18h], 7
0x180036a4d  jbe     short loc_180036A52
0x180036a4f  mov     rcx, [rcx]
0x180036a52  mov     r8, 0CBF29CE484222325h
  ... truncated ...
```
