# CMidiDeviceManager::GetGroupTerminalBlockPortInfo(ushort const *,winrt::Windows::Devices::Enumeration::DeviceInformation,std::map<uint,_PORT_INFO,std::less<uint>,std::allocator<std::pair<uint const,_PORT_INFO>>> * const)

- ea: `0x14002f77c`
- end: `0x14002fce9`
- name: `?GetGroupTerminalBlockPortInfo@CMidiDeviceManager@@AEAAJPEBGUDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAV?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@@Z`
- size: `1389`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x140032ff4`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x1400060ec`
- `0x14000617c`
- `0x1400061e8`
- `0x140006200`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000cc2c`
- `0x14001440c`
- `0x14001bd28`
- `0x14001c390`
- `0x14001fa84`
- `0x14002308c`
- `0x1400285c4`
- `0x140029128`
- `0x14002f77c`
- `0x14003182c`
- `0x14003550c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002fca9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14002fca9`

## string_xrefs

- `0x14002f8c1`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMidiDeviceManager::GetGroupTerminalBlockPortInfo(__int64 a1, void *a2, void **a3, __int64 a4)
{
  __int64 v4; // r13
  int v8; // r15d
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  wchar_t *v13; // rbx
  _DWORD *v14; // r14
  char *v16; // rsi
  unsigned int v17; // edx
  _WORD *v18; // rax
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // r8
  __int128 *v21; // rdx
  int v22; // r15d
  __int64 v23; // rax
  const wchar_t *v24; // rdx
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r8
  __int128 *v27; // rdx
  int v28; // eax
  HANDLE ProcessHeap; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  void **v32; // rcx
  unsigned __int64 v33; // rdx
  char *v34; // r15
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // r13
  __int64 v38; // rax
  __int64 v39; // r8
  void **v40; // rcx
  unsigned __int64 v41; // rdx
  char *v42; // r15
  __int64 v43; // rbx
  __int64 v44; // rax
  int v45; // [rsp+20h] [rbp-E0h]
  int v46[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v47; // [rsp+48h] [rbp-B8h]
  int v48; // [rsp+4Ch] [rbp-B4h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v50; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v51; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h]
  void **v54; // [rsp+78h] [rbp-88h]
  LPVOID pv[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v57; // [rsp+A0h] [rbp-60h]
  const wchar_t *v58; // [rsp+A8h] [rbp-58h]
  __int128 v59; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-40h]
  __int128 v61; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v62; // [rsp+E0h] [rbp-20h]
  _OWORD v63[2]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = a4;
  v53 = a4;
  v54 = a3;
  v8 = 0;
  v48 = 0;
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    lpMem = a2;
    v50 = L"Enter";
    v49 = a1;
    *(_QWORD *)v46 = "CMidiDeviceManager::GetGroupTerminalBlockPortInfo";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)qword_140088CB8,
      v10,
      v11,
      v46,
      (__int64)&v49,
      &v50,
      &lpMem);
  }
  v12 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          a3,
          &v49);
  *((_QWORD *)&v56 + 1) = 0x2900000001LL;
  v58 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 50";
  *(_QWORD *)&v56 = (char *)&v56 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v12,
    &v51,
    &v56);
  v13 = 0;
  if ( v49 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v49);
  if ( v51 )
  {
    winrt::unbox_value<winrt::Windows::Foundation::IReferenceArray<unsigned char>>(&v50, &v51);
    winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<unsigned char>,unsigned char>::Value(
      &v50,
      pv);
    v14 = pv[0];
    if ( *((_DWORD *)pv[0] + 1) )
    {
      v16 = (char *)pv[0] + 8;
      v17 = 0;
      LODWORD(v49) = 0;
      do
      {
        v47 = *(_WORD *)v16;
        v46[0] = (unsigned __int8)v16[4];
        if ( v46[0] < v46[0] + (unsigned int)(unsigned __int8)v16[5] )
        {
          v18 = v16 + 11;
          do
          {
            v59 = 0;
            v60 = 0;
            v19 = -1;
            do
              ++v19;
            while ( v18[v19] != (_WORD)v13 );
            std::wstring::_Construct<1,unsigned short const *>((char **)&v59, v18, v19);
            v56 = 0;
            v57 = v13;
            v58 = v13;
            v20 = 31;
            if ( (unsigned __int64)v60 < 0x1F )
              v20 = v60;
            v21 = &v59;
            if ( *((_QWORD *)&v60 + 1) > 7u )
              v21 = (__int128 *)v59;
            std::wstring::_Construct<1,unsigned short const *>((char **)&v56, v21, v20);
            v22 = v8 | 1;
            std::wstring::~wstring((char **)&v59);
            if ( v57 == v13 )
            {
              v23 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
                      a3,
                      &lpMem);
              if ( *(_QWORD *)v23 )
                v24 = *(const wchar_t **)(*(_QWORD *)v23 + 16LL);
              else
                v24 = &S2;
              v61 = 0;
              v62 = 0;
              v25 = -1;
              do
                ++v25;
              while ( v24[v25] != (_WORD)v13 );
              std::wstring::_Construct<1,unsigned short const *>((char **)&v61, v24, v25);
              memset(v63, 0, sizeof(v63));
              v26 = 31;
              if ( (unsigned __int64)v62 < 0x1F )
                v26 = v62;
              v27 = &v61;
              if ( *((_QWORD *)&v62 + 1) > 7u )
                v27 = (__int128 *)v61;
              std::wstring::_Construct<1,unsigned short const *>((char **)v63, v27, v26);
              v48 = v22 | 2;
              std::wstring::operator=((char **)&v56, (__int64)v63);
              std::wstring::~wstring((char **)v63);
              std::wstring::~wstring((char **)&v61);
              v13 = (wchar_t *)lpMem;
              if ( lpMem )
              {
                v28 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
                if ( v28 )
                {
                  v13 = 0;
                  if ( v28 < 0 )
                    abort();
                }
                else
                {
                  ProcessHeap = WINRT_IMPL_GetProcessHeap();
                  WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
                  v13 = 0;
                }
                lpMem = 0;
              }
            }
            else
            {
              v48 = v22;
            }
            if ( (v16[3] & 0xFD) == 0 )
            {
              *(_BYTE *)std::map<unsigned int,_PORT_INFO>::operator[](v4, v46) = 1;
              *(_BYTE *)(std::map<unsigned int,_PORT_INFO>::operator[](v4, v46) + 1) = 1;
              *(_DWORD *)(std::map<unsigned int,_PORT_INFO>::operator[](v4, v46) + 40) = (_DWORD)v13;
              v30 = std::map<unsigned int,_PORT_INFO>::operator[](v4, v46);
              v32 = (void **)(v30 + 8);
              v33 = -1;
              do
                ++v33;
              while ( *((_WORD *)a2 + v33) != (_WORD)v13 );
              if ( v33 > *(_QWORD *)(v30 + 32) )
              {
                ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
                  v32,
                  v33,
                  v31,
                  a2);
              }
              else
              {
                if ( *(_QWORD *)(v30 + 32) <= 7u )
                  v34 = (char *)(v30 + 8);
                else
                  v34 = (char *)*v32;
                *(_QWORD *)(v30 + 24) = v33;
                v35 = 2 * v33;
                memmove_0(v34, a2, 2 * v33);
                *(_WORD *)&v34[v35] = 0;
                v13 = 0;
              }
              v36 = std::map<unsigned int,_PORT_INFO>::operator[](v4, v46);
              std::wstring::operator=(v36 + 48, &v56);
            }
            if ( (unsigned __int8)v16[3] <= 1u )
            {
              v37 = v4 + 16;
              *(_BYTE *)std::map<unsigned int,_PORT_INFO>::operator[](v37, v46) = 1;
              *(_BYTE *)(std::map<unsigned int,_PORT_INFO>::operator[](v37, v46) + 1) = 1;
              *(_DWORD *)(std::map<unsigned int,_PORT_INFO>::operator[](v37, v46) + 40) = 1;
              v38 = std::map<unsigned int,_PORT_INFO>::operator[](v37, v46);
              v40 = (void **)(v38 + 8);
              v41 = -1;
              do
                ++v41;
              while ( *((_WORD *)a2 + v41) != (_WORD)v13 );
              if ( v41 > *(_QWORD *)(v38 + 32) )
              {
                ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
                  v40,
                  v41,
                  v39,
                  a2);
              }
              else
              {
                if ( *(_QWORD *)(v38 + 32) <= 7u )
                  v42 = (char *)(v38 + 8);
                else
                  v42 = (char *)*v40;
                *(_QWORD *)(v38 + 24) = v41;
                v43 = 2 * v41;
                memmove_0(v42, a2, 2 * v41);
                *(_WORD *)&v42[v43] = 0;
                v13 = 0;
              }
              v44 = std::map<unsigned int,_PORT_INFO>::operator[](v37, v46);
              std::wstring::operator=(v44 + 48, &v56);
              v4 = v53;
            }
            std::wstring::~wstring((char **)&v56);
            ++v46[0];
            v8 = v48;
            v18 = v16 + 11;
          }
          while ( v46[0] < (unsigned __int8)v16[4] + (unsigned int)(unsigned __int8)v16[5] );
          v17 = v49;
        }
        v16 += v47;
        LODWORD(v49) = ++v17;
      }
      while ( v17 < v14[1] );
      if ( v14 )
        CoTaskMemFree_0(v14);
      if ( v50 != v13 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
      if ( v51 != v13 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
      if ( *a3 != v13 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98E,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x8000FFFFLL,
        v45);
      CoTaskMemFree_0(v14);
      if ( v50 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
      if ( v51 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
      if ( *a3 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
      return 2147549183LL;
    }
  }
  else
  {
    if ( *a3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x14002f77c  mov     [rsp-8+arg_0], rbx
0x14002f781  push    rbp
0x14002f782  push    rsi
0x14002f783  push    rdi
0x14002f784  push    r12
0x14002f786  push    r13
0x14002f788  push    r14
0x14002f78a  push    r15
0x14002f78c  lea     rbp, [rsp-20h]
0x14002f791  sub     rsp, 120h
0x14002f798  mov     rax, cs:__security_cookie
0x14002f79f  xor     rax, rsp
0x14002f7a2  mov     [rbp+50h+var_40], rax
0x14002f7a6  mov     r13, r9
0x14002f7a9  mov     [rsp+150h+var_E0], r9
0x14002f7ae  mov     rdi, r8
0x14002f7b1  mov     r12, rdx
0x14002f7b4  mov     rbx, rcx
0x14002f7b7  mov     [rsp+150h+var_D8], r8
0x14002f7bc  xor     ecx, ecx
0x14002f7be  mov     r15d, ecx
0x14002f7c1  mov     [rsp+150h+var_104], ecx
0x14002f7c5  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002f7ca  mov     rcx, [rax+8]
0x14002f7ce  mov     eax, [rcx]
0x14002f7d0  cmp     eax, 4
0x14002f7d3  jbe     short loc_14002F82B
0x14002f7d5  mov     [rsp+150h+lpMem], r12
0x14002f7da  lea     rax, aEnter; "Enter"
0x14002f7e1  mov     [rsp+150h+var_F8], rax
0x14002f7e6  mov     [rsp+150h+var_100], rbx
0x14002f7eb  lea     rax, aCmidideviceman_11; "CMidiDeviceManager::GetGroupTerminalBlo"...
0x14002f7f2  mov     qword ptr [rsp+150h+var_110], rax
0x14002f7f7  lea     rax, [rsp+150h+lpMem]
0x14002f7fc  mov     [rsp+150h+var_118], rax
0x14002f801  lea     rax, [rsp+150h+var_F8]
0x14002f806  mov     [rsp+150h+var_120], rax
0x14002f80b  lea     rax, [rsp+150h+var_100]
0x14002f810  mov     [rsp+150h+var_128], rax
0x14002f815  lea     rax, [rsp+150h+var_110]
0x14002f81a  mov     qword ptr [rsp+150h+var_130], rax; int
0x14002f81f  lea     rdx, qword_140088CB8
0x14002f826  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002f82b  lea     rdx, [rsp+150h+var_100]
0x14002f830  mov     rcx, rdi
0x14002f833  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x14002f838  nop
0x14002f839  mov     dword ptr [rbp+50h+var_C0+8], 1
0x14002f840  mov     dword ptr [rbp+50h+var_C0+0Ch], 29h ; ')'
0x14002f847  lea     rcx, a3f114a6a11fa4b_4; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14002f84e  mov     [rbp+50h+var_A8], rcx
0x14002f852  lea     rcx, [rbp+50h+var_C0+8]
0x14002f856  mov     qword ptr [rbp+50h+var_C0], rcx
0x14002f85a  lea     r8, [rbp+50h+var_C0]
0x14002f85e  lea     rdx, [rsp+150h+var_F0]
0x14002f863  mov     rcx, rax
0x14002f866  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x14002f86b  nop
0x14002f86c  xor     ebx, ebx
0x14002f86e  cmp     [rsp+150h+var_100], rbx
0x14002f873  jz      short loc_14002F87F
0x14002f875  lea     rcx, [rsp+150h+var_100]
0x14002f87a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002f87f  cmp     [rsp+150h+var_F0], rbx
0x14002f884  jz      loc_14002FCB0
0x14002f88a  lea     rdx, [rsp+150h+var_F0]
0x14002f88f  lea     rcx, [rsp+150h+var_F8]
0x14002f894  call    ??$unbox_value@U?$IReferenceArray@E@Foundation@Windows@winrt@@@winrt@@YA?AU?$IReferenceArray@E@Foundation@Windows@0@AEBUIInspectable@230@@Z; winrt::unbox_value<winrt::Windows::Foundation::IReferenceArray<uchar>>(winrt::Windows::Foundation::IInspectable const &)
0x14002f899  nop
0x14002f89a  lea     rdx, [rbp+50h+pv]
0x14002f89e  lea     rcx, [rsp+150h+var_F8]
0x14002f8a3  call    ?Value@?$consume_Windows_Foundation_IReferenceArray@U?$IReferenceArray@E@Foundation@Windows@winrt@@E@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<uchar>,uchar>::Value(void)
0x14002f8a8  nop
0x14002f8a9  mov     r14, [rbp+50h+pv]
0x14002f8ad  mov     eax, [r14+4]
0x14002f8b1  test    eax, eax
0x14002f8b3  jnz     short loc_14002F914
0x14002f8b5  mov     rcx, [rbp+58h]; this
0x14002f8b9  mov     esi, 8000FFFFh
0x14002f8be  mov     r9d, esi; char *
0x14002f8c1  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002f8c8  mov     edx, 98Eh; void *
0x14002f8cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f8d2  nop
0x14002f8d3  mov     rcx, r14; pv
0x14002f8d6  call    CoTaskMemFree_0
0x14002f8db  nop
0x14002f8dc  cmp     [rsp+150h+var_F8], rbx
0x14002f8e1  jz      short loc_14002F8EE
0x14002f8e3  lea     rcx, [rsp+150h+var_F8]
0x14002f8e8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002f8ed  nop
0x14002f8ee  cmp     [rsp+150h+var_F0], rbx
0x14002f8f3  jz      short loc_14002F900
0x14002f8f5  lea     rcx, [rsp+150h+var_F0]
0x14002f8fa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002f8ff  nop
0x14002f900  cmp     [rdi], rbx
0x14002f903  jz      short loc_14002F90D
0x14002f905  mov     rcx, rdi
0x14002f908  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002f90d  mov     eax, esi
0x14002f90f  jmp     loc_14002FCC2
0x14002f914  lea     rsi, [r14+8]
0x14002f918  mov     edx, ebx
0x14002f91a  mov     dword ptr [rsp+150h+var_100], ebx
0x14002f91e  test    eax, eax
0x14002f920  jz      loc_14002FC66
0x14002f926  movzx   eax, word ptr [rsi]
0x14002f929  mov     [rsp+150h+var_108], ax
0x14002f92e  movzx   ecx, byte ptr [rsi+4]
0x14002f932  mov     [rsp+150h+var_110], ecx
0x14002f936  movzx   eax, byte ptr [rsi+5]
0x14002f93a  add     eax, ecx
0x14002f93c  cmp     ecx, eax
0x14002f93e  jnb     loc_14002FC4E
0x14002f944  lea     rax, [rsi+0Bh]
0x14002f948  xorps   xmm0, xmm0
0x14002f94b  movups  [rbp+50h+var_A0], xmm0
0x14002f94f  xorps   xmm1, xmm1
0x14002f952  movdqu  [rbp+50h+var_90], xmm1
0x14002f957  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002f95b  inc     r8
0x14002f95e  cmp     [rax+r8*2], bx
0x14002f963  jnz     short loc_14002F95B
0x14002f965  mov     rdx, rax
0x14002f968  lea     rcx, [rbp+50h+var_A0]
0x14002f96c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002f971  nop
0x14002f972  xorps   xmm0, xmm0
0x14002f975  movups  [rbp+50h+var_C0], xmm0
0x14002f979  mov     [rbp+50h+var_B0], rbx
0x14002f97d  mov     [rbp+50h+var_A8], rbx
0x14002f981  mov     r8d, 1Fh
0x14002f987  cmp     qword ptr [rbp+50h+var_90], r8
0x14002f98b  cmovb   r8, qword ptr [rbp+50h+var_90]
0x14002f990  lea     rdx, [rbp+50h+var_A0]
0x14002f994  cmp     qword ptr [rbp+50h+var_90+8], 7
0x14002f999  cmova   rdx, qword ptr [rbp+50h+var_A0]
0x14002f99e  lea     rcx, [rbp+50h+var_C0]
0x14002f9a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002f9a7  or      r15d, 1
0x14002f9ab  lea     rcx, [rbp+50h+var_A0]; void *
0x14002f9af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002f9b4  cmp     [rbp+50h+var_B0], rbx
0x14002f9b8  jnz     loc_14002FAA6
0x14002f9be  lea     rdx, [rsp+150h+lpMem]
0x14002f9c3  mov     rcx, rdi
0x14002f9c6  call    ?Name@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(void)
0x14002f9cb  nop
0x14002f9cc  mov     rcx, [rax]
0x14002f9cf  test    rcx, rcx
0x14002f9d2  jz      short loc_14002F9DA
0x14002f9d4  mov     rdx, [rcx+10h]
0x14002f9d8  jmp     short loc_14002F9E1
0x14002f9da  lea     rdx, S2
0x14002f9e1  xorps   xmm0, xmm0
0x14002f9e4  movups  [rbp+50h+var_80], xmm0
0x14002f9e8  xorps   xmm1, xmm1
0x14002f9eb  movdqu  [rbp+50h+var_70], xmm1
0x14002f9f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002f9f4  inc     r8
0x14002f9f7  cmp     [rdx+r8*2], bx
0x14002f9fc  jnz     short loc_14002F9F4
0x14002f9fe  lea     rcx, [rbp+50h+var_80]
0x14002fa02  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002fa07  nop
0x14002fa08  xorps   xmm0, xmm0
0x14002fa0b  movups  [rbp+50h+var_60], xmm0
0x14002fa0f  xorps   xmm1, xmm1
0x14002fa12  movdqu  [rbp+50h+var_50], xmm1
0x14002fa17  mov     r8d, 1Fh
0x14002fa1d  cmp     qword ptr [rbp+50h+var_70], r8
0x14002fa21  cmovb   r8, qword ptr [rbp+50h+var_70]
0x14002fa26  lea     rdx, [rbp+50h+var_80]
0x14002fa2a  cmp     qword ptr [rbp+50h+var_70+8], 7
0x14002fa2f  cmova   rdx, qword ptr [rbp+50h+var_80]
0x14002fa34  lea     rcx, [rbp+50h+var_60]
0x14002fa38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002fa3d  or      r15d, 2
0x14002fa41  mov     [rsp+150h+var_104], r15d
0x14002fa46  lea     rdx, [rbp+50h+var_60]
0x14002fa4a  lea     rcx, [rbp+50h+var_C0]
0x14002fa4e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002fa53  lea     rcx, [rbp+50h+var_60]; void *
0x14002fa57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002fa5c  nop
0x14002fa5d  lea     rcx, [rbp+50h+var_80]; void *
0x14002fa61  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002fa66  nop
0x14002fa67  mov     rbx, [rsp+150h+lpMem]
0x14002fa6c  test    rbx, rbx
0x14002fa6f  jz      short loc_14002FAAB
0x14002fa71  or      eax, 0FFFFFFFFh
0x14002fa74  lock xadd [rbx+18h], eax
0x14002fa79  sub     eax, 1
0x14002fa7c  jnz     short loc_14002FA95
0x14002fa7e  nop
0x14002fa7f  call    WINRT_IMPL_GetProcessHeap
0x14002fa84  mov     rcx, rax; hHeap
0x14002fa87  mov     r8, rbx; lpMem
0x14002fa8a  xor     edx, edx; dwFlags
0x14002fa8c  call    WINRT_IMPL_HeapFree
0x14002fa91  xor     ebx, ebx
0x14002fa93  jmp     short loc_14002FA9F
0x14002fa95  xor     ebx, ebx
0x14002fa97  test    eax, eax
0x14002fa99  js      loc_14002FCA9
0x14002fa9f  mov     [rsp+150h+lpMem], rbx
0x14002faa4  jmp     short loc_14002FAAB
0x14002faa6  mov     [rsp+150h+var_104], r15d
0x14002faab  test    byte ptr [rsi+3], 0FDh
0x14002faaf  jnz     loc_14002FB5D
0x14002fab5  lea     rdx, [rsp+150h+var_110]
0x14002faba  mov     rcx, r13
0x14002fabd  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fac2  mov     byte ptr [rax], 1
0x14002fac5  lea     rdx, [rsp+150h+var_110]
0x14002faca  mov     rcx, r13
0x14002facd  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fad2  mov     byte ptr [rax+1], 1
0x14002fad6  lea     rdx, [rsp+150h+var_110]
0x14002fadb  mov     rcx, r13
0x14002fade  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fae3  mov     [rax+28h], ebx
0x14002fae6  lea     rdx, [rsp+150h+var_110]
0x14002faeb  mov     rcx, r13
0x14002faee  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002faf3  lea     rcx, [rax+8]
0x14002faf7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002fafb  inc     rdx
0x14002fafe  cmp     [r12+rdx*2], bx
0x14002fb03  jnz     short loc_14002FAFB
0x14002fb05  cmp     rdx, [rcx+18h]
0x14002fb09  ja      short loc_14002FB3B
0x14002fb0b  cmp     qword ptr [rcx+18h], 7
0x14002fb10  jbe     short loc_14002FB17
0x14002fb12  mov     r15, [rcx]
0x14002fb15  jmp     short loc_14002FB1A
0x14002fb17  mov     r15, rcx
0x14002fb1a  mov     [rcx+10h], rdx
0x14002fb1e  lea     rbx, [rdx+rdx]
0x14002fb22  mov     r8, rbx; Size
0x14002fb25  mov     rdx, r12; Src
0x14002fb28  mov     rcx, r15; void *
0x14002fb2b  call    memmove_0
0x14002fb30  xor     ecx, ecx
0x14002fb32  mov     [r15+rbx], cx
0x14002fb37  xor     ebx, ebx
0x14002fb39  jmp     short loc_14002FB43
0x14002fb3b  mov     r9, r12
0x14002fb3e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14002fb43  lea     rdx, [rsp+150h+var_110]
0x14002fb48  mov     rcx, r13
0x14002fb4b  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fb50  lea     rcx, [rax+30h]
0x14002fb54  lea     rdx, [rbp+50h+var_C0]
0x14002fb58  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002fb5d  cmp     byte ptr [rsi+3], 1
0x14002fb61  ja      loc_14002FC1C
0x14002fb67  add     r13, 10h
0x14002fb6b  lea     rdx, [rsp+150h+var_110]
0x14002fb70  mov     rcx, r13
0x14002fb73  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fb78  mov     byte ptr [rax], 1
0x14002fb7b  lea     rdx, [rsp+150h+var_110]
0x14002fb80  mov     rcx, r13
0x14002fb83  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fb88  mov     byte ptr [rax+1], 1
0x14002fb8c  lea     rdx, [rsp+150h+var_110]
0x14002fb91  mov     rcx, r13
0x14002fb94  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fb99  mov     dword ptr [rax+28h], 1
0x14002fba0  lea     rdx, [rsp+150h+var_110]
0x14002fba5  mov     rcx, r13
0x14002fba8  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14002fbad  lea     rcx, [rax+8]
0x14002fbb1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002fbb5  inc     rdx
0x14002fbb8  cmp     [r12+rdx*2], bx
0x14002fbbd  jnz     short loc_14002FBB5
0x14002fbbf  cmp     rdx, [rcx+18h]
0x14002fbc3  ja      short loc_14002FBF5
0x14002fbc5  cmp     qword ptr [rcx+18h], 7
0x14002fbca  jbe     short loc_14002FBD1
0x14002fbcc  mov     r15, [rcx]
0x14002fbcf  jmp     short loc_14002FBD4
0x14002fbd1  mov     r15, rcx
0x14002fbd4  mov     [rcx+10h], rdx
0x14002fbd8  lea     rbx, [rdx+rdx]
0x14002fbdc  mov     r8, rbx; Size
0x14002fbdf  mov     rdx, r12; Src
0x14002fbe2  mov     rcx, r15; void *
0x14002fbe5  call    memmove_0
0x14002fbea  xor     ecx, ecx
0x14002fbec  mov     [r15+rbx], cx
0x14002fbf1  xor     ebx, ebx
0x14002fbf3  jmp     short loc_14002FBFD
0x14002fbf5  mov     r9, r12
0x14002fbf8  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
  ... truncated ...
```
