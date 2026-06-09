# CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint(winrt::Windows::Devices::Enumeration::DeviceInformation const &,uchar,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)

- ea: `0x140030250`
- end: `0x140030a32`
- name: `?GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint@CMidiDeviceManager@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDeviceInformation@Enumeration@Devices@Windows@winrt@@EW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z`
- size: `2018`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x140032ff4`

## callees

- `0x14000179c`
- `0x14000298c`
- `0x1400054c0`
- `0x14000617c`
- `0x1400061e8`
- `0x140006200`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x140013a38`
- `0x14001440c`
- `0x1400145bc`
- `0x14001dccc`
- `0x14002308c`
- `0x1400270dc`
- `0x140030250`
- `0x140030a98`
- `0x140032874`
- `0x14003550c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400304b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030761`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003096f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030a1c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030a2b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400304b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030761`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003096f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030a1c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140030a2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint(
        volatile signed __int32 *a1,
        __int64 a2,
        void *a3,
        char a4,
        int a5)
{
  _DWORD *v7; // rbx
  const wchar_t *v8; // rsi
  int v9; // r14d
  __int64 v10; // rax
  const wchar_t *v11; // rax
  __int64 v12; // rcx
  int v13; // ecx
  void *v14; // rbx
  unsigned int v15; // edx
  int v16; // eax
  HANDLE ProcessHeap; // rax
  void *v18; // rcx
  volatile signed __int32 *v19; // rbx
  unsigned int v20; // edx
  void *v21; // rbx
  unsigned int v22; // eax
  unsigned int v23; // r8d
  LPVOID v24; // r12
  void *v25; // rcx
  struct winrt::impl::shared_hstring_header *v26; // rbx
  volatile signed __int32 *v27; // rbx
  _DWORD *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  const wchar_t *v32; // rax
  unsigned __int64 v33; // r8
  _DWORD *v34; // rbx
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  const wchar_t *v38; // rax
  volatile signed __int32 *v39; // rax
  void *v40; // rbx
  int v41; // eax
  HANDLE v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  bool v45; // bl
  __int64 v46; // rax
  unsigned __int64 v47; // r8
  __int64 v48; // rax
  void *v49; // rbx
  int v50; // edi
  HANDLE v51; // rax
  const wchar_t *v53; // rcx
  void *v54; // rbx
  int v55; // eax
  HANDLE v56; // rax
  const wchar_t *v57; // rdx
  unsigned __int64 v58; // r8
  __int64 v59; // rax
  int v60; // eax
  HANDLE v61; // rax
  LPVOID v62; // [rsp+50h] [rbp-B0h] BYREF
  char v63; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v64; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+68h] [rbp-98h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v67; // [rsp+78h] [rbp-88h] BYREF
  volatile signed __int32 *v68; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v70; // [rsp+90h] [rbp-70h]
  const wchar_t *v71; // [rsp+98h] [rbp-68h] BYREF
  LPVOID *p_lpMem; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v73; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v74; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v75[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v76; // [rsp+D8h] [rbp-28h]
  __int128 v77; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h]
  __int128 v79; // [rsp+100h] [rbp+0h]
  __int128 v80; // [rsp+110h] [rbp+10h] BYREF
  __int64 v81; // [rsp+120h] [rbp+20h]
  unsigned __int64 v82; // [rsp+128h] [rbp+28h]
  char *v83[4]; // [rsp+130h] [rbp+30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v84; // [rsp+150h] [rbp+50h] BYREF
  const char *v85; // [rsp+170h] [rbp+70h]
  __int64 v86; // [rsp+178h] [rbp+78h]
  volatile signed __int32 **v87; // [rsp+180h] [rbp+80h]
  __int64 v88; // [rsp+188h] [rbp+88h]
  const wchar_t *v89; // [rsp+190h] [rbp+90h]
  __int64 v90; // [rsp+198h] [rbp+98h]
  char *v91; // [rsp+1A0h] [rbp+A0h]
  __int64 v92; // [rsp+1A8h] [rbp+A8h]
  LPVOID *v93; // [rsp+1B0h] [rbp+B0h]
  __int64 v94; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v95; // [rsp+1C0h] [rbp+C0h]
  int v96; // [rsp+1C8h] [rbp+C8h]
  int v97; // [rsp+1CCh] [rbp+CCh]

  v64 = a3;
  v68 = a1;
  v76 = a2;
  v65 = 0;
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v8 = &S2;
  v9 = 1;
  if ( *v7 <= 4u )
    goto LABEL_13;
  v10 = *(_QWORD *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
                     v64,
                     &lpMem);
  if ( v10 )
    v11 = *(const wchar_t **)(v10 + 16);
  else
    v11 = &S2;
  LODWORD(v62) = a5;
  v63 = a4;
  v67 = v68;
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &S2;
    v13 = 2;
  }
  v95 = v11;
  v96 = v13;
  v97 = 0;
  v93 = &v62;
  v94 = 4;
  v91 = &v63;
  v92 = 1;
  v89 = L"Enter";
  v90 = 12;
  v87 = &v67;
  v88 = 8;
  v85 = "CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint";
  v86 = 72;
  tlgWriteTransfer_EventWriteTransfer((__int64)v7, (unsigned __int8 *)byte_1400898A9, 0, 0, 8u, &v84);
  v14 = lpMem;
  v15 = 0;
  if ( lpMem )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( !v16 )
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v14);
LABEL_13:
      v15 = 0;
      goto LABEL_14;
    }
    if ( v16 < 0 )
      abort();
  }
LABEL_14:
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  v65 = 1;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 7;
  LOWORD(v80) = 0;
  pv = &lpMem;
  v18 = *(void **)v64;
  lpMem = v18;
  if ( v18 )
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v18 + 8LL))(v18, 0);
  v19 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x29, v15);
  memcpy_s((void *const)(v19 + 7), 0x52u, L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16", 0x52u);
  v67 = v19;
  WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(&v62, &v67, &lpMem);
  v71 = 0;
  if ( !winrt::Windows::Foundation::operator==((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))&v62, &v71) )
  {
    winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<unsigned char>,unsigned char>::Value(
      &v62,
      &pv);
    v21 = pv;
    v20 = 4;
    v22 = *(_DWORD *)pv;
    if ( *(_DWORD *)pv >= v70 )
      v22 = v70;
    if ( v22 >= 0x18uLL )
    {
      do
      {
        v23 = *(_DWORD *)((char *)pv + v20);
        if ( v23 <= 0x14 || v23 > v22 - v20 )
          break;
        if ( *((_BYTE *)pv + v20 + 4) == a4 && *(_DWORD *)((char *)pv + v20 + 12) == a5 )
        {
          LOBYTE(v79) = *((_BYTE *)pv + v20 + 4);
          *(_QWORD *)((char *)&v79 + 4) = *(_QWORD *)((char *)pv + v20 + 8);
          v33 = ((unsigned __int64)*(unsigned int *)((char *)pv + v20) - 18) >> 1;
          if ( v33 <= 1 )
            break;
          v77 = 0;
          v78 = 0;
          std::wstring::_Construct<1,unsigned short const *>((char **)&v77, (char *)pv + v20 + 16, v33);
          std::wstring::operator=(&v80, &v77);
          std::wstring::~wstring((char **)&v77);
          if ( v21 )
            CoTaskMemFree_0(v21);
          if ( v62 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
          if ( v81 )
          {
            v34 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
            if ( *v34 <= 4u )
            {
              v24 = v64;
            }
            else
            {
              v24 = v64;
              v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
                      v64,
                      &v62);
              if ( *(_QWORD *)v35 )
                v38 = *(const wchar_t **)(*(_QWORD *)v35 + 16LL);
              else
                v38 = &S2;
              v71 = v38;
              v39 = (volatile signed __int32 *)&v80;
              if ( v82 > 7 )
                v39 = (volatile signed __int32 *)v80;
              v67 = v39;
              lpMem = L"Using filter Id from pin map entry";
              v64 = (LPVOID)v68;
              v68 = (volatile signed __int32 *)"CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (__int64)v34,
                (__int64)&word_140089006,
                v36,
                v37,
                &v68,
                (__int64)&v64,
                &lpMem,
                &v67,
                &v71);
              v40 = v62;
              if ( v62 )
              {
                v41 = _InterlockedDecrement((volatile signed __int32 *)v62 + 6);
                if ( v41 )
                {
                  if ( v41 < 0 )
                    abort();
                }
                else
                {
                  v42 = WINRT_IMPL_GetProcessHeap();
                  WINRT_IMPL_HeapFree(v42, 0, v40);
                }
              }
            }
            v43 = std::wstring::wstring((__int64)v83, (__int64)&v80);
            WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(&v77, v43);
            v9 = 3;
            v65 = 3;
            std::wstring::operator=((char **)a2, (__int64)&v77);
            std::wstring::~wstring((char **)&v77);
            goto LABEL_57;
          }
          goto LABEL_32;
        }
        v20 += v23;
      }
      while ( (unsigned __int64)v20 + 20 <= v22 );
    }
    if ( pv )
      CoTaskMemFree_0(pv);
  }
  if ( v62 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
LABEL_32:
  pv = &v67;
  v67 = 0;
  p_lpMem = &lpMem;
  v24 = v64;
  v25 = *(void **)v64;
  lpMem = v25;
  if ( v25 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
  v26 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x29, v20);
  memcpy_s((char *)v26 + 28, 0x52u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 19", 0x52u);
  v62 = v26;
  WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(
    (volatile signed __int32 **)&v64,
    (volatile signed __int32 **)&v62,
    &lpMem,
    &v67);
  v27 = (volatile signed __int32 *)v64;
  if ( v64 )
  {
    v28 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v28 > 4u )
    {
      v29 = *(_QWORD *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
                         v24,
                         &pv);
      v32 = v29 ? *(const wchar_t **)(v29 + 16) : &S2;
      v71 = v32;
      v53 = v64 ? (const wchar_t *)*((_QWORD *)v64 + 2) : &S2;
      v74 = v53;
      v73 = L"Using filter Id from single property";
      p_lpMem = (LPVOID *)v68;
      v68 = (volatile signed __int32 *)"CMidiDeviceManager::GetWinMMDeviceInterfaceIdForGroupFromParentEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v28,
        (__int64)&word_14008976E,
        v30,
        v31,
        &v68,
        (__int64)&p_lpMem,
        &v73,
        &v74,
        &v71);
      v54 = pv;
      if ( pv )
      {
        v55 = _InterlockedDecrement((volatile signed __int32 *)pv + 6);
        if ( v55 )
        {
          if ( v55 < 0 )
            abort();
        }
        else
        {
          v56 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v56, 0, v54);
        }
      }
    }
    if ( v64 )
      v57 = (const wchar_t *)*((_QWORD *)v64 + 2);
    else
      v57 = &S2;
    v77 = 0;
    v78 = 0;
    v58 = -1;
    do
      ++v58;
    while ( v57[v58] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v77, v57, v58);
    v59 = std::wstring::wstring((__int64)v75, (__int64)&v77);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v83, v59);
    v9 = 5;
    v65 = 5;
    std::wstring::operator=((char **)a2, (__int64)v83);
    std::wstring::~wstring(v83);
    std::wstring::~wstring((char **)&v77);
    v27 = (volatile signed __int32 *)v64;
  }
  if ( v27 )
  {
    v60 = _InterlockedDecrement(v27 + 6);
    if ( v60 )
    {
      if ( v60 < 0 )
        abort();
    }
    else
    {
      v61 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v61, 0, (LPVOID)v27);
    }
  }
LABEL_57:
  v44 = std::wstring::wstring((__int64)v75, a2);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v83, v44);
  v65 = v9 | 8;
  v45 = v83[2] == 0;
  std::wstring::~wstring(v83);
  if ( v45 )
  {
    v46 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
            v24,
            &pv);
    if ( *(_QWORD *)v46 )
      v8 = *(const wchar_t **)(*(_QWORD *)v46 + 16LL);
    v77 = 0;
    v78 = 0;
    v47 = -1;
    do
      ++v47;
    while ( v8[v47] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v77, v8, v47);
    v48 = std::wstring::wstring((__int64)v75, (__int64)&v77);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v83, v48);
    std::wstring::operator=((char **)a2, (__int64)v83);
    std::wstring::~wstring(v83);
    std::wstring::~wstring((char **)&v77);
    v49 = pv;
    if ( pv )
    {
      v50 = _InterlockedDecrement((volatile signed __int32 *)pv + 6);
      if ( v50 )
      {
        if ( v50 < 0 )
          abort();
      }
      else
      {
        v51 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v51, 0, v49);
      }
    }
  }
  std::wstring::~wstring((char **)&v80);
  return a2;
}

```

## disassembly

```asm
0x140030250  mov     [rsp-8+arg_0], rbx
0x140030255  push    rbp
0x140030256  push    rsi
0x140030257  push    rdi
0x140030258  push    r12
0x14003025a  push    r13
0x14003025c  push    r14
0x14003025e  push    r15
0x140030260  lea     rbp, [rsp-0E0h]
0x140030268  sub     rsp, 1E0h
0x14003026f  mov     rax, cs:__security_cookie
0x140030276  xor     rax, rsp
0x140030279  mov     [rbp+110h+var_40], rax
0x140030280  mov     r12b, r9b
0x140030283  mov     [rsp+210h+var_1B0], r8
0x140030288  mov     r15, rdx
0x14003028b  mov     [rbp+110h+var_190], rcx
0x14003028f  mov     [rbp+110h+var_138], rdx
0x140030293  xor     ebx, ebx
0x140030295  mov     [rsp+210h+var_1A8], ebx
0x140030299  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003029e  mov     rbx, [rax+8]
0x1400302a2  mov     eax, [rbx]
0x1400302a4  lea     rsi, S2
0x1400302ab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400302af  lea     r14d, [rdi+2]
0x1400302b3  mov     r13d, [rbp+110h+arg_20]
0x1400302ba  cmp     eax, 4
0x1400302bd  jbe     loc_1400303EC
0x1400302c3  lea     rdx, [rsp+210h+lpMem]
0x1400302c8  mov     rcx, [rsp+210h+var_1B0]
0x1400302cd  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x1400302d2  mov     rax, [rax]
0x1400302d5  xor     edx, edx
0x1400302d7  test    rax, rax
0x1400302da  jz      short loc_1400302E2
0x1400302dc  mov     rax, [rax+10h]
0x1400302e0  jmp     short loc_1400302E5
0x1400302e2  mov     rax, rsi
0x1400302e5  mov     dword ptr [rsp+210h+var_1C0], r13d
0x1400302ea  mov     [rsp+210h+var_1B8], r12b
0x1400302ef  mov     rcx, [rbp+110h+var_190]
0x1400302f3  mov     [rsp+210h+var_198], rcx
0x1400302f8  test    rax, rax
0x1400302fb  jz      short loc_140030312
0x1400302fd  mov     rcx, rdi
0x140030300  inc     rcx
0x140030303  cmp     [rax+rcx*2], dx
0x140030307  jnz     short loc_140030300
0x140030309  lea     ecx, ds:2[rcx*2]
0x140030310  jmp     short loc_14003031A
0x140030312  mov     rax, rsi
0x140030315  mov     ecx, 2
0x14003031a  mov     [rbp+110h+var_50], rax
0x140030321  mov     [rbp+110h+var_48], ecx
0x140030327  mov     [rbp+110h+var_44], edx
0x14003032d  lea     rax, [rsp+210h+var_1C0]
0x140030332  mov     [rbp+110h+var_60], rax
0x140030339  mov     [rbp+110h+var_58], 4
0x140030344  lea     rax, [rsp+210h+var_1B8]
0x140030349  mov     [rbp+110h+var_70], rax
0x140030350  mov     [rbp+110h+var_68], r14
0x140030357  lea     rax, aEnter; "Enter"
0x14003035e  mov     [rbp+110h+var_80], rax
0x140030365  mov     [rbp+110h+var_78], 0Ch
0x140030370  lea     rax, [rsp+210h+var_198]
0x140030375  mov     [rbp+110h+var_90], rax
0x14003037c  mov     ecx, 8
0x140030381  mov     [rbp+110h+var_88], rcx
0x140030388  lea     rax, aCmidideviceman_15; "CMidiDeviceManager::GetWinMMDeviceInter"...
0x14003038f  mov     [rbp+110h+var_A0], rax
0x140030393  mov     [rbp+110h+var_98], 48h ; 'H'
0x14003039b  lea     rax, [rbp+110h+var_C0]
0x14003039f  mov     [rsp+210h+var_1E8], rax
0x1400303a4  mov     dword ptr [rsp+210h+var_1F0], ecx
0x1400303a8  xor     r9d, r9d
0x1400303ab  xor     r8d, r8d
0x1400303ae  lea     rdx, byte_1400898A9
0x1400303b5  mov     rcx, rbx
0x1400303b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400303bd  mov     rbx, [rsp+210h+lpMem]
0x1400303c2  xor     edx, edx
0x1400303c4  test    rbx, rbx
0x1400303c7  jz      short loc_1400303EE
0x1400303c9  mov     eax, edi
0x1400303cb  lock xadd [rbx+18h], eax
0x1400303d0  sub     eax, r14d
0x1400303d3  jnz     loc_1400304AB
0x1400303d9  nop
0x1400303da  call    WINRT_IMPL_GetProcessHeap
0x1400303df  mov     rcx, rax; hHeap
0x1400303e2  mov     r8, rbx; lpMem
0x1400303e5  xor     edx, edx; dwFlags
0x1400303e7  call    WINRT_IMPL_HeapFree
0x1400303ec  xor     edx, edx
0x1400303ee  xorps   xmm0, xmm0
0x1400303f1  movups  xmmword ptr [r15], xmm0
0x1400303f5  mov     [r15+10h], rdx
0x1400303f9  mov     ecx, 7
0x1400303fe  mov     [r15+18h], rcx
0x140030402  mov     [r15], dx
0x140030406  mov     [rsp+210h+var_1A8], r14d
0x14003040b  movups  [rbp+110h+var_110], xmm0
0x14003040f  xorps   xmm1, xmm1
0x140030412  movups  [rbp+110h+var_100], xmm1
0x140030416  mov     [rbp+110h+var_F0], rdx
0x14003041a  mov     [rbp+110h+var_E8], rcx
0x14003041e  mov     word ptr [rbp+110h+var_100], dx
0x140030422  lea     rax, [rsp+210h+lpMem]
0x140030427  mov     [rbp+110h+pv], rax
0x14003042b  mov     rax, [rsp+210h+var_1B0]
0x140030430  mov     rcx, [rax]
0x140030433  mov     [rsp+210h+lpMem], rcx
0x140030438  test    rcx, rcx
0x14003043b  jz      short loc_14003044A
0x14003043d  mov     rax, [rcx]
0x140030440  mov     rax, [rax+8]
0x140030444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030449  nop
0x14003044a  mov     ecx, 29h ; ')'; this
0x14003044f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x140030454  mov     rbx, rax
0x140030457  lea     rcx, [rax+1Ch]; Destination
0x14003045b  mov     eax, 52h ; 'R'
0x140030460  mov     r9d, eax; SourceSize
0x140030463  lea     r8, a05279cb1002f4e; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x14003046a  mov     edx, eax; DestinationSize
0x14003046c  call    memcpy_s
0x140030471  mov     [rsp+210h+var_198], rbx
0x140030476  lea     r8, [rsp+210h+lpMem]
0x14003047b  lea     rdx, [rsp+210h+var_198]
0x140030480  lea     rcx, [rsp+210h+var_1C0]
0x140030485  call    ?SafeGetSwdBinaryPropertyFromDeviceInformation@WindowsMidiServicesInternal@@YA?AU?$IReferenceArray@E@Foundation@Windows@winrt@@Uhstring@5@UDeviceInformation@Enumeration@Devices@45@@Z; WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x14003048a  nop
0x14003048b  xor     ebx, ebx
0x14003048d  mov     [rbp+110h+var_178], rbx
0x140030491  lea     rdx, [rbp+110h+var_178]
0x140030495  lea     rcx, [rsp+210h+var_1C0]
0x14003049a  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x14003049f  test    al, al
0x1400304a1  jz      short loc_1400304BA
0x1400304a3  xor     r13d, r13d
0x1400304a6  jmp     loc_14003052D
0x1400304ab  test    eax, eax
0x1400304ad  jns     loc_1400303EE
0x1400304b3  call    cs:__imp_abort
0x1400304ba  lea     rdx, [rbp+110h+pv]
0x1400304be  lea     rcx, [rsp+210h+var_1C0]
0x1400304c3  call    ?Value@?$consume_Windows_Foundation_IReferenceArray@U?$IReferenceArray@E@Foundation@Windows@winrt@@E@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<uchar>,uchar>::Value(void)
0x1400304c8  nop
0x1400304c9  mov     rbx, [rbp+110h+pv]
0x1400304cd  mov     edx, 4
0x1400304d2  mov     eax, [rbx]
0x1400304d4  cmp     eax, [rbp+110h+var_180]
0x1400304d7  cmovnb  eax, [rbp+110h+var_180]
0x1400304db  mov     r9d, eax
0x1400304de  cmp     r9, 18h
0x1400304e2  jb      short loc_14003051C
0x1400304e4  mov     ecx, edx
0x1400304e6  mov     r8d, [rcx+rbx]
0x1400304ea  cmp     r8d, 14h
0x1400304ee  jbe     short loc_14003051C
0x1400304f0  mov     eax, r9d
0x1400304f3  sub     eax, edx
0x1400304f5  cmp     r8d, eax
0x1400304f8  ja      short loc_14003051C
0x1400304fa  mov     al, [rcx+rbx+4]
0x1400304fe  cmp     al, r12b
0x140030501  jnz     short loc_14003050E
0x140030503  cmp     [rcx+rbx+0Ch], r13d
0x140030508  jz      loc_1400305FC
0x14003050e  add     edx, r8d
0x140030511  mov     eax, edx
0x140030513  add     rax, 14h
0x140030517  cmp     rax, r9
0x14003051a  jbe     short loc_1400304E4
0x14003051c  xor     r13d, r13d
0x14003051f  test    rbx, rbx
0x140030522  jz      short loc_14003052D
0x140030524  mov     rcx, rbx; pv
0x140030527  call    CoTaskMemFree_0
0x14003052c  nop
0x14003052d  cmp     [rsp+210h+var_1C0], r13
0x140030532  jz      short loc_14003053E
0x140030534  lea     rcx, [rsp+210h+var_1C0]
0x140030539  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003053e  lea     rax, [rsp+210h+var_198]
0x140030543  mov     [rbp+110h+pv], rax
0x140030547  mov     [rsp+210h+var_198], r13
0x14003054c  lea     rax, [rsp+210h+lpMem]
0x140030551  mov     [rbp+110h+var_170], rax
0x140030555  mov     r12, [rsp+210h+var_1B0]
0x14003055a  mov     rcx, [r12]
0x14003055e  mov     [rsp+210h+lpMem], rcx
0x140030563  test    rcx, rcx
0x140030566  jz      short loc_140030575
0x140030568  mov     rax, [rcx]
0x14003056b  mov     rax, [rax+8]
0x14003056f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030574  nop
0x140030575  mov     ecx, 29h ; ')'; this
0x14003057a  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14003057f  mov     rbx, rax
0x140030582  lea     rcx, [rax+1Ch]; Destination
0x140030586  mov     edx, 52h ; 'R'; DestinationSize
0x14003058b  mov     r9d, edx; SourceSize
0x14003058e  lea     r8, a3f114a6a11fa4b_14; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x140030595  call    memcpy_s
0x14003059a  mov     [rsp+210h+var_1C0], rbx
0x14003059f  lea     r9, [rsp+210h+var_198]
0x1400305a4  lea     r8, [rsp+210h+lpMem]
0x1400305a9  lea     rdx, [rsp+210h+var_1C0]
0x1400305ae  lea     rcx, [rsp+210h+var_1B0]
0x1400305b3  call    ??$SafeGetSwdPropertyFromDeviceInformation@Uhstring@winrt@@@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@U12@UDeviceInformation@Enumeration@Devices@Windows@2@0@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::hstring)
0x1400305b8  nop
0x1400305b9  mov     rbx, [rsp+210h+var_1B0]
0x1400305be  test    rbx, rbx
0x1400305c1  jz      loc_1400309E7
0x1400305c7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400305cc  mov     rbx, [rax+8]
0x1400305d0  mov     eax, [rbx]
0x1400305d2  cmp     eax, 4
0x1400305d5  jbe     loc_14003095B
0x1400305db  lea     rdx, [rbp+110h+pv]
0x1400305df  mov     rcx, r12
0x1400305e2  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x1400305e7  mov     rax, [rax]
0x1400305ea  test    rax, rax
0x1400305ed  jz      loc_1400308BB
0x1400305f3  mov     rax, [rax+10h]
0x1400305f7  jmp     loc_1400308BE
0x1400305fc  mov     byte ptr [rbp+110h+var_110], al
0x1400305ff  mov     eax, [rcx+rbx+0Ch]
0x140030603  mov     dword ptr [rbp+110h+var_110+8], eax
0x140030606  mov     eax, [rcx+rbx+8]
0x14003060a  mov     dword ptr [rbp+110h+var_110+4], eax
0x14003060d  mov     r8d, [rcx+rbx]
0x140030611  sub     r8, 12h
0x140030615  shr     r8, 1
0x140030618  cmp     r8, r14
0x14003061b  jbe     loc_14003051C
0x140030621  xorps   xmm0, xmm0
0x140030624  movups  [rbp+110h+var_130], xmm0
0x140030628  xorps   xmm1, xmm1
0x14003062b  movdqu  [rbp+110h+var_120], xmm1
0x140030630  lea     rdx, [rbx+10h]
0x140030634  add     rdx, rcx
0x140030637  lea     rcx, [rbp+110h+var_130]
0x14003063b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140030640  nop
0x140030641  lea     rdx, [rbp+110h+var_130]
0x140030645  lea     rcx, [rbp+110h+var_100]
0x140030649  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003064e  nop
0x14003064f  lea     rcx, [rbp+110h+var_130]; void *
0x140030653  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140030658  nop
0x140030659  xor     r13d, r13d
0x14003065c  test    rbx, rbx
0x14003065f  jz      short loc_14003066A
0x140030661  mov     rcx, rbx; pv
0x140030664  call    CoTaskMemFree_0
0x140030669  nop
0x14003066a  cmp     [rsp+210h+var_1C0], r13
0x14003066f  jz      short loc_14003067B
0x140030671  lea     rcx, [rsp+210h+var_1C0]
0x140030676  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003067b  cmp     [rbp+110h+var_F0], r13
0x14003067f  jz      loc_14003053E
0x140030685  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003068a  mov     rbx, [rax+8]
0x14003068e  mov     eax, [rbx]
0x140030690  cmp     eax, 4
0x140030693  jbe     loc_140030768
0x140030699  lea     rdx, [rsp+210h+var_1C0]
0x14003069e  mov     r12, [rsp+210h+var_1B0]
0x1400306a3  mov     rcx, r12
0x1400306a6  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x1400306ab  mov     rcx, [rax]
0x1400306ae  test    rcx, rcx
0x1400306b1  jz      short loc_1400306B9
0x1400306b3  mov     rax, [rcx+10h]
0x1400306b7  jmp     short loc_1400306BC
0x1400306b9  mov     rax, rsi
0x1400306bc  mov     [rbp+110h+var_178], rax
0x1400306c0  lea     rax, [rbp+110h+var_100]
0x1400306c4  cmp     [rbp+110h+var_E8], 7
0x1400306c9  cmova   rax, qword ptr [rbp+110h+var_100]
0x1400306ce  mov     [rsp+210h+var_198], rax
0x1400306d3  lea     rax, aUsingFilterIdF; "Using filter Id from pin map entry"
0x1400306da  mov     [rsp+210h+lpMem], rax
0x1400306df  mov     rax, [rbp+110h+var_190]
0x1400306e3  mov     [rsp+210h+var_1B0], rax
0x1400306e8  lea     rax, aCmidideviceman_15; "CMidiDeviceManager::GetWinMMDeviceInter"...
0x1400306ef  mov     [rbp+110h+var_190], rax
0x1400306f3  lea     rax, [rbp+110h+var_178]
0x1400306f7  mov     [rsp+210h+var_1D0], rax
0x1400306fc  lea     rax, [rsp+210h+var_198]
0x140030701  mov     [rsp+210h+var_1D8], rax
0x140030706  lea     rax, [rsp+210h+lpMem]
  ... truncated ...
```
