# CMidiConfigurationManager::LoadCurrentConfigurationFile(void)

- ea: `0x140025978`
- end: `0x140025f99`
- name: `?LoadCurrentConfigurationFile@CMidiConfigurationManager@@QEAAJXZ`
- size: `1569`
- prototype: `__int64 __fastcall(wchar_t *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025258`

## callees

- `0x1400018e4`
- `0x1400054c0`
- `0x1400060f8`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000ca00`
- `0x14000cc2c`
- `0x14001440c`
- `0x140021614`
- `0x140021fe0`
- `0x1400221d0`
- `0x1400223c0`
- `0x140023108`
- `0x140023678`
- `0x140025978`
- `0x1400261d4`
- `0x140026344`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025b09`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025d7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025e3c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025e82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025b09`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025d7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025e3c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140025e82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140025a21`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140025a21`

## string_xrefs

- `0x140025db0`: `Configuration file JSON parsing failed`
- `0x140025e99`: `Configuration file JSON is empty`
- `0x140025dc1`: `CMidiConfigurationManager::LoadCurrentConfigurationFile`
- `0x140025eaa`: `CMidiConfigurationManager::LoadCurrentConfigurationFile`
- `0x140025f17`: `CMidiConfigurationManager::LoadCurrentConfigurationFile`
- `0x140025f06`: `Missing MIDI configuration file`

## pseudocode

```c
__int64 __fastcall CMidiConfigurationManager::LoadCurrentConfigurationFile(wchar_t *this)
{
  const WCHAR *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  _QWORD *v6; // rcx
  int v7; // eax
  __int64 v8; // rdi
  int v9; // eax
  __int64 v10; // rdi
  volatile signed __int32 **v11; // rax
  volatile signed __int32 **v12; // rcx
  void *v13; // r15
  int v14; // eax
  HANDLE ProcessHeap; // rax
  char v16; // al
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // r14d
  HANDLE v21; // rax
  int v23; // r14d
  HANDLE v24; // rax
  _DWORD *v25; // rcx
  int v26; // r8d
  int v27; // r9d
  _DWORD *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // [rsp+40h] [rbp-318h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-310h] BYREF
  const wchar_t *v36; // [rsp+50h] [rbp-308h] BYREF
  const char *v37; // [rsp+58h] [rbp-300h] BYREF
  volatile signed __int32 *v38; // [rsp+60h] [rbp-2F8h] BYREF
  _QWORD v39[2]; // [rsp+68h] [rbp-2F0h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+78h] [rbp-2E0h] BYREF
  __int64 v41; // [rsp+88h] [rbp-2D0h]
  unsigned __int64 v42; // [rsp+90h] [rbp-2C8h]
  __int64 *v43; // [rsp+98h] [rbp-2C0h]
  __int128 v44; // [rsp+A0h] [rbp-2B8h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-2A8h]
  _QWORD v46[2]; // [rsp+C0h] [rbp-298h] BYREF
  __int64 v47; // [rsp+D0h] [rbp-288h]
  unsigned __int64 v48; // [rsp+D8h] [rbp-280h]
  _QWORD v49[4]; // [rsp+E0h] [rbp-278h] BYREF
  WCHAR Dst[264]; // [rsp+100h] [rbp-258h] BYREF

  v39[0] = this;
  CMidiConfigurationManager::GetCurrentConfigurationFileName(this, v46);
  *(_OWORD *)lpSrc = 0;
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpSrc, L"%ALLUSERSPROFILE%\\Microsoft\\MIDI\\", 33);
  v36 = (const wchar_t *)lpSrc;
  memset_0(Dst, 0, 0x20Au);
  v2 = (const WCHAR *)lpSrc;
  if ( v42 > 7 )
    v2 = lpSrc[0];
  ExpandEnvironmentStringsW(v2, Dst, 0x105u);
  v44 = 0;
  v45 = 0;
  v3 = -1;
  do
    ++v3;
  while ( Dst[v3] );
  std::wstring::_Construct<1,unsigned short const *>(&v44, Dst, v3);
  std::wstring::~wstring(lpSrc);
  v4 = std::operator+<unsigned short>(v49, &v44, v46);
  std::wstring::operator=(v46, v4);
  std::wstring::~wstring(v49);
  std::wstring::~wstring(&v44);
  if ( !v47 )
  {
    v28 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v28 > 3u )
    {
      v39[0] = L"Missing MIDI configuration file";
      v36 = this;
      lpMem = "CMidiConfigurationManager::LoadCurrentConfigurationFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)&word_140088A26,
        v29,
        v30,
        (__int64)&lpMem,
        (__int64)&v36,
        (__int64)v39);
    }
    goto LABEL_45;
  }
  v5 = 0;
  v38 = 0;
  v6 = v46;
  if ( v48 > 7 )
    v6 = (_QWORD *)v46[0];
  if ( (_DWORD)v47 )
  {
    if ( *((_WORD *)v6 + (unsigned int)v47) )
      abort();
    DWORD2(v44) = 1;
    HIDWORD(v44) = v47;
    *((_QWORD *)&v45 + 1) = v6;
    *(_QWORD *)&v44 = (char *)&v44 + 8;
  }
  else
  {
    *(_QWORD *)&v44 = 0;
  }
  try
  {
    lpMem = &v44;
    v36 = (const wchar_t *)&qword_140096A38;
    _InterlockedIncrement64(&qword_140096A38);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics> )
    {
      v34 = 0;
      LODWORD(lpSrc[0]) = 2187;
      lpSrc[1] = (LPCWSTR)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Storage.h";
      v41 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics>
                                                                 + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics>,
             v44,
             &v34);
      if ( v7 < 0 )
        winrt::throw_hresult((unsigned int)v7, lpSrc);
      v8 = v34;
      _InterlockedAdd64(&qword_140096A38, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_140096A38, 0xFFFFFFFFFFFFFFFFuLL);
      ___call_AEAV_lambda_1___1__GetFileFromPathAsync_StorageFile_Storage_Windows_winrt__SA_AEBUhstring_param_6__Z____factory_cache_entry_UStorageFile_Storage_Windows_winrt__UIStorageFileStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetFileFromPathAsync_StorageFile_Storage_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        0,
        &v34,
        &lpMem);
      v8 = v34;
    }
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::get(
      &v34,
      &v37);
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
    v36 = (const wchar_t *)&v37;
    v43 = &qword_140096A18;
    _InterlockedIncrement64(&qword_140096A18);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics> )
    {
      v34 = 0;
      LODWORD(lpSrc[0]) = 857;
      lpSrc[1] = (LPCWSTR)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Storage.h";
      v41 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, const char *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics>
                                                                       + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics>,
             v37,
             &v34);
      if ( v9 < 0 )
        winrt::throw_hresult((unsigned int)v9, lpSrc);
      v10 = v34;
      _InterlockedAdd64(&qword_140096A18, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_140096A18, 0xFFFFFFFFFFFFFFFFuLL);
      ___call_AEAV_lambda_1___1__ReadTextAsync_FileIO_Storage_Windows_winrt__SA_AEBUIStorageFile_456__Z____factory_cache_entry_UFileIO_Storage_Windows_winrt__UIFileIOStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__ReadTextAsync_FileIO_Storage_Windows_2_SA_AEBUIStorageFile_672__Z__Z(
        0,
        &v34,
        &v36);
      v10 = v34;
    }
    v11 = (volatile signed __int32 **)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::hstring>::get(
                                        &v34,
                                        &lpMem);
    v12 = &v38;
    if ( &v38 != v11 )
    {
      v5 = *v11;
      *v11 = 0;
      v38 = v5;
    }
  }
  catch ( ... )
  {
    v31 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v31 > 3u )
    {
      v36 = L"Missing or inaccessible MIDI configuration file";
      lpMem = "CMidiConfigurationManager::LoadCurrentConfigurationFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v31,
        (unsigned int)&unk_140088858,
        v32,
        v33,
        (__int64)&lpMem,
        (__int64)v39,
        (__int64)&v36);
    }
    v5 = v38;
    if ( v38 )
      goto LABEL_48;
    goto LABEL_45;
  }
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
  if ( v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  if ( v5 )
  {
    v49[0] = v5;
    v39[0] = v49;
    v39[1] = this + 8;
    v43 = &qword_140096A98;
    _InterlockedIncrement64(&qword_140096A98);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
    {
      v16 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
              v39,
              &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
      _InterlockedAdd64(&qword_140096A98, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_140096A98, 0xFFFFFFFFFFFFFFFFuLL);
      v16 = ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
              v12,
              v39);
    }
    if ( v16 )
    {
LABEL_48:
      v23 = _InterlockedDecrement(v5 + 6);
      if ( v23 )
      {
        if ( v23 < 0 )
          abort();
      }
      else
      {
        v24 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v24, 0, (LPVOID)v5);
      }
      goto LABEL_45;
    }
    v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v17 > 2u )
    {
      v36 = L"Configuration file JSON parsing failed";
      lpMem = this;
      v37 = "CMidiConfigurationManager::LoadCurrentConfigurationFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (unsigned int)qword_140088770,
        v18,
        v19,
        (__int64)&v37,
        (__int64)&lpMem,
        (__int64)&v36);
    }
    v20 = _InterlockedDecrement(v5 + 6);
    if ( v20 )
    {
      if ( v20 < 0 )
        abort();
    }
    else
    {
      v21 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v21, 0, (LPVOID)v5);
    }
    v38 = 0;
  }
  else
  {
    v25 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v25 > 3u )
    {
      v36 = L"Configuration file JSON is empty";
      lpMem = this;
      v37 = "CMidiConfigurationManager::LoadCurrentConfigurationFile";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v25,
        (unsigned int)&unk_140088950,
        v26,
        v27,
        (__int64)&v37,
        (__int64)&lpMem,
        (__int64)&v36);
    }
  }
LABEL_45:
  std::wstring::~wstring(v46);
  return 0;
}

```

## disassembly

```asm
0x140025978  push    rbx
0x14002597a  push    rsi
0x14002597b  push    rdi
0x14002597c  push    r13
0x14002597e  push    r14
0x140025980  push    r15
0x140025982  sub     rsp, 328h
0x140025989  mov     rax, cs:__security_cookie
0x140025990  xor     rax, rsp
0x140025993  mov     [rsp+358h+var_48], rax
0x14002599b  mov     r13, rcx
0x14002599e  mov     [rsp+358h+var_2F0], rcx
0x1400259a3  xor     esi, esi
0x1400259a5  lea     rdx, [rsp+358h+var_298]
0x1400259ad  call    ?GetCurrentConfigurationFileName@CMidiConfigurationManager@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CMidiConfigurationManager::GetCurrentConfigurationFileName(void)
0x1400259b2  nop
0x1400259b3  xorps   xmm0, xmm0
0x1400259b6  movups  xmmword ptr [rsp+358h+lpSrc], xmm0
0x1400259bb  mov     [rsp+358h+var_2D0], rsi
0x1400259c3  mov     [rsp+358h+var_2C8], rsi
0x1400259cb  lea     r8d, [rsi+21h]
0x1400259cf  lea     rdx, aAllusersprofil; "%ALLUSERSPROFILE%\\Microsoft\\MIDI\\"
0x1400259d6  lea     rcx, [rsp+358h+lpSrc]
0x1400259db  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400259e0  lea     rax, [rsp+358h+lpSrc]
0x1400259e5  mov     [rsp+358h+var_308], rax
0x1400259ea  xor     edx, edx; Val
0x1400259ec  mov     r8d, 20Ah; Size
0x1400259f2  lea     rcx, [rsp+358h+Dst]; void *
0x1400259fa  call    memset_0
0x1400259ff  lea     rcx, [rsp+358h+lpSrc]
0x140025a04  cmp     [rsp+358h+var_2C8], 7
0x140025a0d  cmova   rcx, [rsp+358h+lpSrc]; lpSrc
0x140025a13  mov     r8d, 105h; nSize
0x140025a19  lea     rdx, [rsp+358h+Dst]; lpDst
0x140025a21  call    cs:__imp_ExpandEnvironmentStringsW
0x140025a27  xorps   xmm0, xmm0
0x140025a2a  movups  [rsp+358h+var_2B8], xmm0
0x140025a32  xorps   xmm1, xmm1
0x140025a35  movdqu  [rsp+358h+var_2A8], xmm1
0x140025a3e  lea     rax, [rsp+358h+Dst]
0x140025a46  or      r14, 0FFFFFFFFFFFFFFFFh
0x140025a4a  mov     r8, r14
0x140025a4d  inc     r8
0x140025a50  cmp     [rax+r8*2], si
0x140025a55  jnz     short loc_140025A4D
0x140025a57  lea     rdx, [rsp+358h+Dst]
0x140025a5f  lea     rcx, [rsp+358h+var_2B8]
0x140025a67  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140025a6c  nop
0x140025a6d  lea     rcx, [rsp+358h+lpSrc]; void *
0x140025a72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025a77  nop
0x140025a78  lea     r8, [rsp+358h+var_298]
0x140025a80  lea     rdx, [rsp+358h+var_2B8]
0x140025a88  lea     rcx, [rsp+358h+var_278]
0x140025a90  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140025a95  mov     rdx, rax
0x140025a98  lea     rcx, [rsp+358h+var_298]
0x140025aa0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140025aa5  lea     rcx, [rsp+358h+var_278]; void *
0x140025aad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025ab2  nop
0x140025ab3  lea     rcx, [rsp+358h+var_2B8]; void *
0x140025abb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025ac0  mov     rdx, [rsp+358h+var_288]
0x140025ac8  test    rdx, rdx
0x140025acb  jz      loc_140025EF6
0x140025ad1  mov     rbx, rsi
0x140025ad4  mov     [rsp+358h+var_2F8], rbx
0x140025ad9  lea     rcx, [rsp+358h+var_298]
0x140025ae1  cmp     [rsp+358h+var_280], 7
0x140025aea  cmova   rcx, [rsp+358h+var_298]
0x140025af3  test    edx, edx
0x140025af5  jnz     short loc_140025B01
0x140025af7  mov     qword ptr [rsp+358h+var_2B8], rsi
0x140025aff  jmp     short loc_140025B3A
0x140025b01  mov     eax, edx
0x140025b03  cmp     [rcx+rax*2], si
0x140025b07  jz      short loc_140025B10
0x140025b09  call    cs:__imp_abort
0x140025b10  mov     dword ptr [rsp+358h+var_2B8+8], 1
0x140025b1b  mov     dword ptr [rsp+358h+var_2B8+0Ch], edx
0x140025b22  mov     qword ptr [rsp+358h+var_2A8+8], rcx
0x140025b2a  lea     rax, [rsp+358h+var_2B8+8]
0x140025b32  mov     qword ptr [rsp+358h+var_2B8], rax
0x140025b3a  lea     rax, [rsp+358h+var_2B8]
0x140025b42  mov     [rsp+358h+lpMem], rax
0x140025b47  lea     rax, qword_140096A38
0x140025b4e  mov     [rsp+358h+var_308], rax
0x140025b53  lock inc cs:qword_140096A38
0x140025b5b  mov     rcx, cs:??$factory_cache_entry_v@UStorageFile@Storage@Windows@winrt@@UIStorageFileStatics@234@@impl@winrt@@3U?$factory_cache_entry@UStorageFile@Storage@Windows@winrt@@UIStorageFileStatics@234@@12@A; factory_cache_entry<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::StorageFile,winrt::Windows::Storage::IStorageFileStatics>
0x140025b62  test    rcx, rcx
0x140025b65  jz      short loc_140025BC0
0x140025b67  mov     [rsp+358h+var_318], rsi
0x140025b6c  mov     dword ptr [rsp+358h+lpSrc], 88Bh
0x140025b74  lea     r15, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140025b7b  mov     [rsp+358h+lpSrc+8], r15
0x140025b83  mov     [rsp+358h+var_2D0], rsi
0x140025b8b  mov     rax, [rcx]
0x140025b8e  lea     r8, [rsp+358h+var_318]
0x140025b93  mov     rdx, qword ptr [rsp+358h+var_2B8]
0x140025b9b  mov     rax, [rax+30h]
0x140025b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025ba4  test    eax, eax
0x140025ba6  js      loc_140025F7E
0x140025bac  mov     rdi, [rsp+358h+var_318]
0x140025bb1  mov     [rsp+358h+var_318], rdi
0x140025bb6  lock add cs:qword_140096A38, r14
0x140025bbe  jmp     short loc_140025BE3
0x140025bc0  lock add cs:qword_140096A38, r14
0x140025bc8  lea     r8, [rsp+358h+lpMem]
0x140025bcd  lea     rdx, [rsp+358h+var_318]
0x140025bd2  call    ??$call@AEAV_lambda_1_@?1??GetFileFromPathAsync@StorageFile@Storage@Windows@winrt@@SA@AEBUhstring@param@6@@Z@@?$factory_cache_entry@UStorageFile@Storage@Windows@winrt@@UIStorageFileStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetFileFromPathAsync@StorageFile@Storage@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x140025bd7  lea     r15, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140025bde  mov     rdi, [rsp+358h+var_318]
0x140025be3  lea     rdx, [rsp+358h+var_300]
0x140025be8  lea     rcx, [rsp+358h+var_318]
0x140025bed  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFile@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::get(void)
0x140025bf2  nop
0x140025bf3  test    rdi, rdi
0x140025bf6  jz      short loc_140025C02
0x140025bf8  lea     rcx, [rsp+358h+var_318]
0x140025bfd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140025c02  lea     rax, [rsp+358h+var_300]
0x140025c07  mov     [rsp+358h+var_308], rax
0x140025c0c  lea     rax, qword_140096A18
0x140025c13  mov     [rsp+358h+var_2C0], rax
0x140025c1b  lock inc cs:qword_140096A18
0x140025c23  mov     rcx, cs:??$factory_cache_entry_v@UFileIO@Storage@Windows@winrt@@UIFileIOStatics@234@@impl@winrt@@3U?$factory_cache_entry@UFileIO@Storage@Windows@winrt@@UIFileIOStatics@234@@12@A; factory_cache_entry<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::FileIO,winrt::Windows::Storage::IFileIOStatics>
0x140025c2a  test    rcx, rcx
0x140025c2d  jz      short loc_140025C7E
0x140025c2f  mov     [rsp+358h+var_318], rsi
0x140025c34  mov     dword ptr [rsp+358h+lpSrc], 359h
0x140025c3c  mov     [rsp+358h+lpSrc+8], r15
0x140025c44  mov     [rsp+358h+var_2D0], rsi
0x140025c4c  mov     rax, [rcx]
0x140025c4f  lea     r8, [rsp+358h+var_318]
0x140025c54  mov     rdx, [rsp+358h+var_300]
0x140025c59  mov     rax, [rax+30h]
0x140025c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025c62  test    eax, eax
0x140025c64  js      loc_140025F8B
0x140025c6a  mov     rdi, [rsp+358h+var_318]
0x140025c6f  mov     [rsp+358h+var_318], rdi
0x140025c74  lock add cs:qword_140096A18, r14
0x140025c7c  jmp     short loc_140025C9A
0x140025c7e  lock add cs:qword_140096A18, r14
0x140025c86  lea     r8, [rsp+358h+var_308]
0x140025c8b  lea     rdx, [rsp+358h+var_318]
0x140025c90  call    ??$call@AEAV_lambda_1_@?1??ReadTextAsync@FileIO@Storage@Windows@winrt@@SA@AEBUIStorageFile@456@@Z@@?$factory_cache_entry@UFileIO@Storage@Windows@winrt@@UIFileIOStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??ReadTextAsync@FileIO@Storage@Windows@2@SA@AEBUIStorageFile@672@@Z@@Z
0x140025c95  mov     rdi, [rsp+358h+var_318]
0x140025c9a  lea     rdx, [rsp+358h+lpMem]
0x140025c9f  lea     rcx, [rsp+358h+var_318]
0x140025ca4  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@Uhstring@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::hstring>::get(void)
0x140025ca9  lea     rcx, [rsp+358h+var_2F8]
0x140025cae  cmp     rcx, rax
0x140025cb1  jz      short loc_140025CBE
0x140025cb3  mov     rbx, [rax]
0x140025cb6  mov     [rax], rsi
0x140025cb9  mov     [rsp+358h+var_2F8], rbx
0x140025cbe  mov     r15, [rsp+358h+lpMem]
0x140025cc3  test    r15, r15
0x140025cc6  jz      short loc_140025CF2
0x140025cc8  mov     eax, r14d
0x140025ccb  lock xadd [r15+18h], eax
0x140025cd1  sub     eax, 1
0x140025cd4  jnz     loc_140025D77
0x140025cda  nop
0x140025cdb  call    WINRT_IMPL_GetProcessHeap
0x140025ce0  mov     rcx, rax; hHeap
0x140025ce3  mov     r8, r15; lpMem
0x140025ce6  xor     edx, edx; dwFlags
0x140025ce8  call    WINRT_IMPL_HeapFree
0x140025ced  mov     [rsp+358h+lpMem], rsi
0x140025cf2  test    rdi, rdi
0x140025cf5  jz      short loc_140025D02
0x140025cf7  lea     rcx, [rsp+358h+var_318]
0x140025cfc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140025d01  nop
0x140025d02  cmp     [rsp+358h+var_300], rsi
0x140025d07  jz      short loc_140025D14
0x140025d09  lea     rcx, [rsp+358h+var_300]
0x140025d0e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140025d13  nop
0x140025d14  test    rbx, rbx
0x140025d17  jz      loc_140025E89
0x140025d1d  mov     [rsp+358h+var_278], rbx
0x140025d25  lea     rax, [rsp+358h+var_278]
0x140025d2d  mov     [rsp+358h+var_2F0], rax
0x140025d32  lea     rax, [r13+10h]
0x140025d36  mov     [rsp+358h+var_2E8], rax
0x140025d3b  lea     rax, qword_140096A98
0x140025d42  mov     [rsp+358h+var_2C0], rax
0x140025d4a  lock inc cs:qword_140096A98
0x140025d52  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rsi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x140025d59  jz      short loc_140025D86
0x140025d5b  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x140025d62  lea     rcx, [rsp+358h+var_2F0]
0x140025d67  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x140025d6c  nop
0x140025d6d  lock add cs:qword_140096A98, r14
0x140025d75  jmp     short loc_140025D98
0x140025d77  test    eax, eax
0x140025d79  jns     loc_140025CED
0x140025d7f  call    cs:__imp_abort
0x140025d86  lock add cs:qword_140096A98, r14
0x140025d8e  lea     rdx, [rsp+358h+var_2F0]
0x140025d93  call    ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z
0x140025d98  test    al, al
0x140025d9a  jnz     loc_140025E35
0x140025da0  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140025da5  mov     rcx, [rax+8]
0x140025da9  mov     eax, [rcx]
0x140025dab  cmp     eax, 2
0x140025dae  jbe     short loc_140025DF8
0x140025db0  lea     rax, aConfigurationF; "Configuration file JSON parsing failed"
0x140025db7  mov     [rsp+358h+var_308], rax
0x140025dbc  mov     [rsp+358h+lpMem], r13
0x140025dc1  lea     rax, aCmidiconfigura_7; "CMidiConfigurationManager::LoadCurrentC"...
0x140025dc8  mov     [rsp+358h+var_300], rax
0x140025dcd  lea     rax, [rsp+358h+var_308]
0x140025dd2  mov     [rsp+358h+var_328], rax
0x140025dd7  lea     rax, [rsp+358h+lpMem]
0x140025ddc  mov     [rsp+358h+var_330], rax
0x140025de1  lea     rax, [rsp+358h+var_300]
0x140025de6  mov     [rsp+358h+var_338], rax
0x140025deb  lea     rdx, qword_140088770
0x140025df2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140025df7  nop
0x140025df8  test    rbx, rbx
0x140025dfb  jz      short loc_140025E21
0x140025dfd  lock xadd [rbx+18h], r14d
0x140025e03  sub     r14d, 1
0x140025e07  jnz     short loc_140025E37
0x140025e09  nop
0x140025e0a  call    WINRT_IMPL_GetProcessHeap
0x140025e0f  mov     rcx, rax; hHeap
0x140025e12  mov     r8, rbx; lpMem
0x140025e15  xor     edx, edx; dwFlags
0x140025e17  call    WINRT_IMPL_HeapFree
0x140025e1c  mov     [rsp+358h+var_2F8], rsi
0x140025e21  lea     rcx, [rsp+358h+var_298]; void *
0x140025e29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025e2e  xor     eax, eax
0x140025e30  jmp     loc_140025F5D
0x140025e35  jmp     short loc_140025E4C
0x140025e37  test    r14d, r14d
0x140025e3a  jns     short loc_140025E1C
0x140025e3c  call    cs:__imp_abort
0x140025e43  or      r14, 0FFFFFFFFFFFFFFFFh
0x140025e47  mov     rbx, [rsp+358h+var_2F8]
0x140025e4c  test    rbx, rbx
0x140025e4f  jz      loc_140025F4E
0x140025e55  lock xadd [rbx+18h], r14d
0x140025e5b  sub     r14d, 1
0x140025e5f  jnz     short loc_140025E79
0x140025e61  nop
0x140025e62  call    WINRT_IMPL_GetProcessHeap
0x140025e67  mov     r8, rbx; lpMem
0x140025e6a  xor     edx, edx; dwFlags
0x140025e6c  mov     rcx, rax; hHeap
0x140025e6f  call    WINRT_IMPL_HeapFree
0x140025e74  jmp     loc_140025F4E
0x140025e79  test    r14d, r14d
0x140025e7c  jns     loc_140025F4E
0x140025e82  call    cs:__imp_abort
0x140025e89  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140025e8e  mov     rcx, [rax+8]
0x140025e92  mov     eax, [rcx]
0x140025e94  cmp     eax, 3
0x140025e97  jbe     short loc_140025EE1
0x140025e99  lea     rax, aConfigurationF_0; "Configuration file JSON is empty"
0x140025ea0  mov     [rsp+358h+var_308], rax
0x140025ea5  mov     [rsp+358h+lpMem], r13
0x140025eaa  lea     rax, aCmidiconfigura_7; "CMidiConfigurationManager::LoadCurrentC"...
0x140025eb1  mov     [rsp+358h+var_300], rax
0x140025eb6  lea     rax, [rsp+358h+var_308]
0x140025ebb  mov     [rsp+358h+var_328], rax
0x140025ec0  lea     rax, [rsp+358h+lpMem]
0x140025ec5  mov     [rsp+358h+var_330], rax
0x140025eca  lea     rax, [rsp+358h+var_300]
0x140025ecf  mov     [rsp+358h+var_338], rax
0x140025ed4  lea     rdx, unk_140088950
0x140025edb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140025ee0  nop
0x140025ee1  jmp     short loc_140025F4E
0x140025ee3  mov     rbx, [rsp+358h+var_2F8]
0x140025ee8  test    rbx, rbx
0x140025eeb  jz      short loc_140025F4E
0x140025eed  or      r14, 0FFFFFFFFFFFFFFFFh
0x140025ef1  jmp     loc_140025E55
0x140025ef6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140025efb  mov     rcx, [rax+8]
0x140025eff  mov     eax, [rcx]
0x140025f01  cmp     eax, 3
0x140025f04  jbe     short loc_140025F4E
0x140025f06  lea     rax, aMissingMidiCon; "Missing MIDI configuration file"
0x140025f0d  mov     [rsp+358h+var_2F0], rax
0x140025f12  mov     [rsp+358h+var_308], r13
  ... truncated ...
```
