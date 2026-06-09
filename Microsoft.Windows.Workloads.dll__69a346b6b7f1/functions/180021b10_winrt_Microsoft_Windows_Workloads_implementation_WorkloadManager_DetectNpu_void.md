# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DetectNpu(void)

- ea: `0x180021b10`
- end: `0x18002225b`
- name: `?DetectNpu@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `1867`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x180004a00`
- `0x18000d970`
- `0x1800119b0`
- `0x180013330`
- `0x180013bd0`
- `0x180014e70`
- `0x180019d50`
- `0x18001b430`
- `0x18001b800`
- `0x18001bbb0`
- `0x180021b10`
- `0x180028730`
- `0x18002aad0`
- `0x180034828`
- `0x180034ef0`
- `0x180036f4c`
- `0x180039893`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180021ffb`
- `KERNEL32!GetCurrentProcessId` at `0x180021ffb`
- `KERNEL32!GetLastError` at `0x1800221b7`
- `KERNEL32!GetLastError` at `0x18002221d`
- `KERNEL32!GetLastError` at `0x1800221b7`
- `KERNEL32!GetLastError` at `0x18002221d`
- `KERNEL32!FreeLibrary` at `0x180022154`
- `KERNEL32!FreeLibrary` at `0x180022154`
- `KERNEL32!ProcessIdToSessionId` at `0x180022008`
- `KERNEL32!ProcessIdToSessionId` at `0x180022008`
- `KERNEL32!GetProcAddress` at `0x180021d11`
- `KERNEL32!GetProcAddress` at `0x180021d11`
- `KERNEL32!LoadLibraryExW` at `0x180021cf0`
- `KERNEL32!LoadLibraryExW` at `0x180021cf0`
- `ADVAPI32!EventWriteTransfer` at `0x180021fdc`
- `ADVAPI32!EventWriteTransfer` at `0x18002214a`
- `ADVAPI32!EventWriteTransfer` at `0x180021fdc`
- `ADVAPI32!EventWriteTransfer` at `0x18002214a`

## string_xrefs

- `0x1800221fb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`
- `0x180021c9b`: `NPUDetect\npudetect.dll`
- `0x18002220d`: `Failed to load npudetect.dll.`
- `0x1800221a7`: `Failed to find proc in npudetect.dll.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DetectNpu(
        winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *this)
{
  __m128i si128; // xmm6
  int v3; // eax
  const wchar_t *v4; // r8
  std::filesystem *v5; // rdi
  const wchar_t *v6; // rbx
  const wchar_t *root_name_end; // rax
  const wchar_t *v8; // rcx
  __int16 v9; // dx
  const wchar_t *v10; // rcx
  __int16 v11; // dx
  __int64 v12; // rcx
  const WCHAR *v13; // rcx
  HMODULE Library; // rax
  HMODULE v15; // rbx
  FARPROC ProcAddress; // rax
  __int64 v17; // rdi
  size_t v18; // r8
  __int64 v19; // rcx
  char v20; // al
  __int64 v21; // rcx
  char v22; // al
  __int64 v23; // rcx
  char v24; // al
  __int64 v25; // rcx
  char v26; // al
  __int64 v27; // rcx
  char v28; // al
  __int64 v29; // rcx
  char v30; // al
  __int64 v31; // rcx
  char v32; // al
  __int64 v33; // rcx
  char v34; // al
  const struct _tlgProvider_t *v35; // rcx
  __int64 v36; // rax
  DWORD CurrentProcessId; // eax
  LPVOID v38; // rdx
  LPVOID v39; // rcx
  const struct _tlgProvider_t *v40; // rax
  signed int v41; // eax
  winrt::hresult *v42; // rax
  signed int LastError; // eax
  winrt::hresult *v44; // rax
  int UserDataCount; // [rsp+28h] [rbp-E0h]
  LPVOID v46; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE pSessionId[40]; // [rsp+50h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR v49; // [rsp+78h] [rbp-90h] BYREF
  __m128i v50; // [rsp+88h] [rbp-80h]
  LPCWSTR lpLibFileName[4]; // [rsp+98h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v53; // [rsp+C8h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D8h] [rbp-30h] BYREF
  char *p_ppv; // [rsp+E8h] [rbp-20h]
  __int64 v56; // [rsp+F0h] [rbp-18h]
  __int128 *v57; // [rsp+F8h] [rbp-10h]
  __int64 v58; // [rsp+100h] [rbp-8h]
  __int128 *p_Src; // [rsp+108h] [rbp+0h]
  int v60; // [rsp+110h] [rbp+8h]
  int v61; // [rsp+114h] [rbp+Ch]
  ULONG *p_Size; // [rsp+148h] [rbp+40h]
  __int128 Src; // [rsp+158h] [rbp+50h] BYREF
  __int128 v64; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]

  EventDescriptor = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v53 = si128;
  EventDescriptor.Id = 0;
  *(_DWORD *)pSessionId = 1;
  v46 = (LPVOID)0x180000000LL;
  ppv = 0;
  *(_QWORD *)&UserData.Size = &wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  p_ppv = (char *)&ppv;
  v56 = (__int64)&v46;
  p_Size = &UserData.Size;
  v3 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>((__int64)&EventDescriptor, (__int64)&UserData);
  if ( v3 < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v3,
      UserDataCount);
  }
  v49 = EventDescriptor;
  v50 = v53;
  v53 = si128;
  EventDescriptor.Id = 0;
  std::wstring::_Tidy_deallocate((__int64)&EventDescriptor);
  v5 = (std::filesystem *)&v49;
  if ( v50.m128i_i64[1] > 7uLL )
    v5 = *(std::filesystem **)&v49.Id;
  v6 = (const wchar_t *)((char *)v5 + 2 * v50.m128i_i64[0]);
  root_name_end = std::filesystem::_Find_root_name_end(v5, v6, v4);
  if ( root_name_end != v6 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v6 );
    if ( root_name_end != v6 )
    {
      while ( 1 )
      {
        v8 = v6 - 1;
        v9 = *(v6 - 1);
        if ( v9 == 92 || v9 == 47 )
          break;
        --v6;
        if ( root_name_end == v8 )
          goto LABEL_17;
      }
      if ( root_name_end != v6 )
      {
        do
        {
          v10 = v6 - 1;
          v11 = *(v6 - 1);
          if ( v11 != 92 && v11 != 47 )
            break;
          --v6;
        }
        while ( root_name_end != v10 );
      }
    }
  }
LABEL_17:
  memset(&pSessionId[8], 0, 32);
  std::wstring::_Construct<1,wchar_t const *>(&pSessionId[8], v5, ((char *)v6 - (char *)v5) >> 1);
  _std_fs_code_page(v12);
  *(_QWORD *)&EventDescriptor.Id = "NPUDetect\\npudetect.dll";
  EventDescriptor.Keyword = 23;
  std::filesystem::_Convert_narrow_to_wide(&UserData);
  std::filesystem::operator/((std::filesystem *)lpLibFileName, &pSessionId[8], &UserData);
  std::wstring::_Tidy_deallocate((__int64)&UserData);
  v13 = (const WCHAR *)lpLibFileName;
  if ( lpLibFileName[3] > (LPCWSTR)7 )
    v13 = lpLibFileName[0];
  Library = LoadLibraryExW(v13, 0, 0x1100u);
  v15 = Library;
  if ( !Library )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)&UserData, L"Failed to load npudetect.dll.");
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v44 = winrt::hresult::hresult((winrt::hresult *)&v46, LastError);
    winrt::hresult_error::hresult_error(&EventDescriptor, *(unsigned int *)v44, &UserData);
    throw (winrt::hresult_error *)&EventDescriptor;
  }
  ProcAddress = GetProcAddress(Library, "npudetect_detect_npu");
  if ( !ProcAddress )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)&UserData, L"Failed to find proc in npudetect.dll.");
    v41 = GetLastError();
    if ( v41 > 0 )
      v41 = (unsigned __int16)v41 | 0x80070000;
    v42 = winrt::hresult::hresult((winrt::hresult *)&v46, v41);
    winrt::hresult_error::hresult_error(&EventDescriptor, *(unsigned int *)v42, &UserData);
    throw (winrt::hresult_error *)&EventDescriptor;
  }
  *((_DWORD *)this + 46) = 0;
  v64 = 0;
  Src = 0;
  if ( ((int (__fastcall *)(__int128 *, __int64, __int128 *))ProcAddress)(&v64, 16, &Src) <= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl'::`2'::impl) )
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( ProcessIdToSessionId(CurrentProcessId, (DWORD *)pSessionId) )
      {
        v46 = 0;
        ppv = 0;
        if ( *(_DWORD *)pSessionId )
        {
          *(_DWORD *)&EventDescriptor.Id = 1404625999;
          *(_DWORD *)&EventDescriptor.Level = 1203190916;
          EventDescriptor.Keyword = 0x91CB337234654684uLL;
        }
        else
        {
          *(_DWORD *)&EventDescriptor.Id = -1660147340;
          *(_DWORD *)&EventDescriptor.Level = 1108319961;
          EventDescriptor.Keyword = 0xCF7D381EE4CCB89EuLL;
        }
        CoCreateInstance_0((const IID *const)&EventDescriptor, 0, 4u, &winrt::impl::guid_v<IHCFContractManager>, &ppv);
        v38 = ppv;
        v39 = ppv;
        v46 = ppv;
        if ( ppv )
          *((_DWORD *)this + 46) = 4;
        if ( v39 )
          winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(&v46, v38);
      }
    }
  }
  else
  {
    v17 = -1;
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)&Src + v18) );
    std::string::assign((char *)this + 192, &Src, v18);
    v19 = 0;
    while ( 1 )
    {
      v20 = *((_BYTE *)&v64 + v19++);
      if ( v20 != aQnn_0[v19 - 1] )
        break;
      if ( v19 == 4 )
      {
        v21 = 0;
        while ( 1 )
        {
          v22 = *((_BYTE *)&Src + v21++);
          if ( v22 != aV73[v21 - 1] )
            break;
          if ( v21 == 4 )
          {
            *((_DWORD *)this + 46) = 1;
            goto LABEL_68;
          }
        }
        v23 = 0;
        while ( 1 )
        {
          v24 = *((_BYTE *)&Src + v23++);
          if ( v24 != aV81[v23 - 1] )
            goto LABEL_35;
          if ( v23 == 4 )
          {
            *((_DWORD *)this + 46) = 1;
            goto LABEL_68;
          }
        }
      }
    }
LABEL_35:
    v25 = 0;
    while ( 1 )
    {
      v26 = *((_BYTE *)&v64 + v25++);
      if ( v26 != aOpv[v25 - 1] )
        break;
      if ( v25 == 4 )
      {
        v27 = 0;
        while ( 1 )
        {
          v28 = *((_BYTE *)&Src + v27++);
          if ( v28 != aLnl_0[v27 - 1] )
            break;
          if ( v27 == 4 )
          {
            *((_DWORD *)this + 46) = 2;
            goto LABEL_68;
          }
        }
        v29 = 0;
        while ( 1 )
        {
          v30 = *((_BYTE *)&Src + v29++);
          if ( v30 != aPtl[v29 - 1] )
            goto LABEL_46;
          if ( v29 == 4 )
          {
            *((_DWORD *)this + 46) = 2;
            goto LABEL_68;
          }
        }
      }
    }
LABEL_46:
    v31 = 0;
    while ( 1 )
    {
      v32 = *((_BYTE *)&v64 + v31++);
      if ( v32 != aVit[v31 - 1] )
        break;
      if ( v31 == 4 )
      {
        v33 = 0;
        while ( 1 )
        {
          v34 = *((_BYTE *)&Src + v33++);
          if ( v34 != aStx_0[v33 - 1] )
            goto LABEL_53;
          if ( v33 == 4 )
          {
            *((_DWORD *)this + 46) = 3;
            goto LABEL_68;
          }
        }
      }
    }
LABEL_53:
    v35 = TraceLogger::Provider();
    if ( *(_DWORD *)v35 > 5u )
    {
      v36 = -1;
      do
        ++v36;
      while ( *((_BYTE *)&Src + v36) );
      p_Src = &Src;
      v60 = v36 + 1;
      v61 = 0;
      do
        ++v17;
      while ( *((_BYTE *)&v64 + v17) );
      v57 = &v64;
      v58 = (unsigned int)(v17 + 1);
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *((_QWORD *)v35 + 1);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      p_ppv = byte_18004DB1D;
      v56 = 0x10000001DLL;
      *(_DWORD *)pSessionId = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*((_QWORD *)v35 + 4), &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
LABEL_68:
  v40 = TraceLogger::Provider();
  if ( *(_DWORD *)v40 > 5u )
  {
    *(_DWORD *)pSessionId = *((_DWORD *)this + 46);
    v57 = (__int128 *)pSessionId;
    v58 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *((_QWORD *)v40 + 1);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    p_ppv = byte_18004DAF5;
    v56 = 0x10000001CLL;
    LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v40 + 4), &EventDescriptor, 0, 0, 3u, &UserData);
  }
  FreeLibrary(v15);
  std::wstring::_Tidy_deallocate((__int64)lpLibFileName);
  std::wstring::_Tidy_deallocate((__int64)&pSessionId[8]);
  std::wstring::_Tidy_deallocate((__int64)&v49);
}

```

## disassembly

```asm
0x180021b10  mov     rax, rsp
0x180021b13  mov     [rax+10h], rbx
0x180021b17  mov     [rax+18h], rsi
0x180021b1b  push    rbp
0x180021b1c  push    rdi
0x180021b1d  push    r12
0x180021b1f  push    r14
0x180021b21  push    r15
0x180021b23  lea     rbp, [rax-0B8h]
0x180021b2a  sub     rsp, 190h
0x180021b31  movaps  xmmword ptr [rax-38h], xmm6
0x180021b35  mov     rax, cs:__security_cookie
0x180021b3c  xor     rax, rsp
0x180021b3f  mov     [rbp+0B0h+var_40], rax
0x180021b43  mov     rsi, rcx
0x180021b46  xor     r15d, r15d
0x180021b49  mov     dword ptr [rsp+1B0h+pSessionId], r15d
0x180021b4e  xorps   xmm0, xmm0
0x180021b51  movups  xmmword ptr [rbp+0B0h+EventDescriptor.Id], xmm0
0x180021b55  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180021b5d  movdqu  [rbp+0B0h+var_F0], xmm6
0x180021b62  mov     [rbp+0B0h+EventDescriptor.Id], r15w
0x180021b67  mov     dword ptr [rsp+1B0h+pSessionId], 1
0x180021b6f  lea     rax, cs:180000000h
0x180021b76  mov     [rsp+1B0h+var_178], rax
0x180021b7b  mov     [rsp+1B0h+ppv], r15
0x180021b80  lea     rax, ??_7?$__func@V_lambda_2d860dc2582dcbaaba41b7ebab4cc740_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180021b87  mov     qword ptr [rbp+0B0h+var_E0.Size], rax
0x180021b8b  lea     rax, [rsp+1B0h+ppv]
0x180021b90  mov     [rbp+0B0h+var_D0], rax
0x180021b94  lea     rax, [rsp+1B0h+var_178]
0x180021b99  mov     [rbp+0B0h+var_C8], rax
0x180021b9d  lea     rax, [rbp+0B0h+var_E0.Size]
0x180021ba1  mov     [rbp+0B0h+var_70], rax
0x180021ba5  lea     rdx, [rbp+0B0h+var_E0]
0x180021ba9  lea     rcx, [rbp+0B0h+EventDescriptor]
0x180021bad  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(std::wstring &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x180021bb2  mov     rcx, [rbp+0B8h]; this
0x180021bb9  test    eax, eax
0x180021bbb  js      loc_1800221F5
0x180021bc1  movups  xmm0, xmmword ptr [rbp+0B0h+EventDescriptor.Id]
0x180021bc5  movups  xmmword ptr [rsp+1B0h+var_148+8], xmm0
0x180021bca  movups  xmm1, [rbp+0B0h+var_F0]
0x180021bce  movups  [rbp+0B0h+var_130], xmm1
0x180021bd2  movdqu  [rbp+0B0h+var_F0], xmm6
0x180021bd7  mov     [rbp+0B0h+EventDescriptor.Id], r15w
0x180021bdc  lea     rcx, [rbp+0B0h+EventDescriptor]
0x180021be0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021be5  lea     rdi, [rsp+1B0h+var_148+8]
0x180021bea  cmp     qword ptr [rbp+0B0h+var_130+8], 7
0x180021bef  cmova   rdi, qword ptr [rsp+1B0h+var_148+8]
0x180021bf5  mov     rax, qword ptr [rbp+0B0h+var_130]
0x180021bf9  lea     rbx, [rdi+rax*2]
0x180021bfd  mov     rdx, rbx; wchar_t *
0x180021c00  mov     rcx, rdi; this
0x180021c03  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180021c08  cmp     rax, rbx
0x180021c0b  jz      short loc_180021C6D
0x180021c0d  nop     dword ptr [rax]
0x180021c10  movzx   ecx, word ptr [rax]
0x180021c13  cmp     cx, 5Ch ; '\'
0x180021c17  jz      short loc_180021C1F
0x180021c19  cmp     cx, 2Fh ; '/'
0x180021c1d  jnz     short loc_180021C28
0x180021c1f  add     rax, 2
0x180021c23  cmp     rax, rbx
0x180021c26  jnz     short loc_180021C10
0x180021c28  cmp     rax, rbx
0x180021c2b  jz      short loc_180021C6D
0x180021c2d  nop     dword ptr [rax]
0x180021c30  lea     rcx, [rbx-2]
0x180021c34  movzx   edx, word ptr [rcx]
0x180021c37  cmp     dx, 5Ch ; '\'
0x180021c3b  jz      short loc_180021C4D
0x180021c3d  cmp     dx, 2Fh ; '/'
0x180021c41  jz      short loc_180021C4D
0x180021c43  mov     rbx, rcx
0x180021c46  cmp     rax, rcx
0x180021c49  jnz     short loc_180021C30
0x180021c4b  jmp     short loc_180021C6D
0x180021c4d  cmp     rax, rbx
0x180021c50  jz      short loc_180021C6D
0x180021c52  lea     rcx, [rbx-2]
0x180021c56  movzx   edx, word ptr [rcx]
0x180021c59  cmp     dx, 5Ch ; '\'
0x180021c5d  jz      short loc_180021C65
0x180021c5f  cmp     dx, 2Fh ; '/'
0x180021c63  jnz     short loc_180021C6D
0x180021c65  mov     rbx, rcx
0x180021c68  cmp     rax, rcx
0x180021c6b  jnz     short loc_180021C52
0x180021c6d  sub     rbx, rdi
0x180021c70  sar     rbx, 1
0x180021c73  xorps   xmm0, xmm0
0x180021c76  movups  xmmword ptr [rsp+1B0h+pSessionId+8], xmm0
0x180021c7b  mov     [rsp+1B0h+var_150], r15
0x180021c80  mov     qword ptr [rsp+1B0h+var_148], r15
0x180021c85  mov     r8, rbx
0x180021c88  mov     rdx, rdi
0x180021c8b  lea     rcx, [rsp+1B0h+pSessionId+8]
0x180021c90  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180021c95  nop
0x180021c96  call    __std_fs_code_page
0x180021c9b  lea     rcx, aNpudetectNpude; "NPUDetect\\npudetect.dll"
0x180021ca2  mov     qword ptr [rbp+0B0h+EventDescriptor.Id], rcx
0x180021ca6  mov     [rbp+0B0h+EventDescriptor.Keyword], 17h
0x180021cae  lea     r8, [rbp+0B0h+EventDescriptor]
0x180021cb2  mov     edx, eax
0x180021cb4  lea     rcx, [rbp+0B0h+var_E0]; Src
0x180021cb8  call    ?_Convert_narrow_to_wide@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@W4__std_code_page@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; std::filesystem::_Convert_narrow_to_wide(__std_code_page,std::string_view)
0x180021cbd  nop
0x180021cbe  lea     r8, [rbp+0B0h+var_E0]; void *
0x180021cc2  lea     rdx, [rsp+1B0h+pSessionId+8]; void *
0x180021cc7  lea     rcx, [rbp+0B0h+lpLibFileName]; Src
0x180021ccb  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180021cd0  nop
0x180021cd1  lea     rcx, [rbp+0B0h+var_E0]
0x180021cd5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021cda  lea     rcx, [rbp+0B0h+lpLibFileName]
0x180021cde  cmp     [rbp+0B0h+var_108], 7
0x180021ce3  cmova   rcx, [rbp+0B0h+lpLibFileName]; lpLibFileName
0x180021ce8  xor     edx, edx; hFile
0x180021cea  mov     r8d, 1100h; dwFlags
0x180021cf0  call    cs:__imp_LoadLibraryExW
0x180021cf6  mov     rbx, rax
0x180021cf9  mov     [rsp+1B0h+var_180], rax
0x180021cfe  test    rax, rax
0x180021d01  jz      loc_18002220D
0x180021d07  lea     rdx, aNpudetectDetec; "npudetect_detect_npu"
0x180021d0e  mov     rcx, rax; hModule
0x180021d11  call    cs:__imp_GetProcAddress
0x180021d17  test    rax, rax
0x180021d1a  jz      loc_1800221A7
0x180021d20  mov     [rsi+0B8h], r15d
0x180021d27  xorps   xmm0, xmm0
0x180021d2a  movups  [rbp+0B0h+var_50], xmm0
0x180021d2e  xorps   xmm1, xmm1
0x180021d31  movups  [rbp+0B0h+Src], xmm1
0x180021d35  mov     r9d, 10h
0x180021d3b  lea     r8, [rbp+0B0h+Src]
0x180021d3f  mov     edx, r9d
0x180021d42  lea     rcx, [rbp+0B0h+var_50]
0x180021d46  call    cs:__guard_dispatch_icall_fptr
0x180021d4c  lea     r14, _TraceLoggingMetadataEnd
0x180021d53  lea     r12, _TraceLoggingMetadata
0x180021d5a  test    eax, eax
0x180021d5c  jle     loc_180021FE7
0x180021d62  lea     rax, [rbp+0B0h+Src]
0x180021d66  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180021d6d  mov     r8, rdi
0x180021d70  inc     r8; Size
0x180021d73  cmp     byte ptr [rax+r8], 0
0x180021d78  jnz     short loc_180021D70
0x180021d7a  lea     rcx, [rsi+0C0h]; void *
0x180021d81  lea     rdx, [rbp+0B0h+Src]; Src
0x180021d85  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180021d8a  mov     rcx, r15
0x180021d8d  lea     rdx, [rbp+0B0h+var_50]
0x180021d91  lea     r8, aQnn_0; "QNN"
0x180021d98  nop     dword ptr [rax+rax+00000000h]
0x180021da0  movzx   eax, byte ptr [rdx+rcx]
0x180021da4  inc     rcx
0x180021da7  cmp     al, [r8+rcx-1]
0x180021dac  jnz     short loc_180021E23
0x180021dae  cmp     rcx, 4
0x180021db2  jnz     short loc_180021DA0
0x180021db4  mov     rcx, r15
0x180021db7  lea     rdx, [rbp+0B0h+Src]
0x180021dbb  lea     r8, aV73; "V73"
0x180021dc2  movzx   eax, byte ptr [rdx+rcx]
0x180021dc6  inc     rcx
0x180021dc9  cmp     al, [r8+rcx-1]
0x180021dce  jnz     short loc_180021DE5
0x180021dd0  cmp     rcx, 4
0x180021dd4  jnz     short loc_180021DC2
0x180021dd6  mov     dword ptr [rsi+0B8h], 1
0x180021de0  jmp     loc_1800220B0
0x180021de5  mov     rcx, r15
0x180021de8  lea     rdx, [rbp+0B0h+Src]
0x180021dec  lea     r8, aV81; "V81"
0x180021df3  nop     dword ptr [rax+00h]
0x180021df7  nop     word ptr [rax+rax+00000000h]
0x180021e00  movzx   eax, byte ptr [rdx+rcx]
0x180021e04  inc     rcx
0x180021e07  cmp     al, [r8+rcx-1]
0x180021e0c  jnz     short loc_180021E23
0x180021e0e  cmp     rcx, 4
0x180021e12  jnz     short loc_180021E00
0x180021e14  mov     dword ptr [rsi+0B8h], 1
0x180021e1e  jmp     loc_1800220B0
0x180021e23  mov     rcx, r15
0x180021e26  lea     rdx, [rbp+0B0h+var_50]
0x180021e2a  lea     r8, aOpv; "OPV"
0x180021e31  movzx   eax, byte ptr [rdx+rcx]
0x180021e35  inc     rcx
0x180021e38  cmp     al, [r8+rcx-1]
0x180021e3d  jnz     short loc_180021EB4
0x180021e3f  cmp     rcx, 4
0x180021e43  jnz     short loc_180021E31
0x180021e45  mov     rcx, r15
0x180021e48  lea     rdx, [rbp+0B0h+Src]
0x180021e4c  lea     r8, aLnl_0; "LNL"
0x180021e53  nop     dword ptr [rax+00h]
0x180021e57  nop     word ptr [rax+rax+00000000h]
0x180021e60  movzx   eax, byte ptr [rdx+rcx]
0x180021e64  inc     rcx
0x180021e67  cmp     al, [r8+rcx-1]
0x180021e6c  jnz     short loc_180021E83
0x180021e6e  cmp     rcx, 4
0x180021e72  jnz     short loc_180021E60
0x180021e74  mov     dword ptr [rsi+0B8h], 2
0x180021e7e  jmp     loc_1800220B0
0x180021e83  mov     rcx, r15
0x180021e86  lea     rdx, [rbp+0B0h+Src]
0x180021e8a  lea     r8, aPtl; "PTL"
0x180021e91  movzx   eax, byte ptr [rdx+rcx]
0x180021e95  inc     rcx
0x180021e98  cmp     al, [r8+rcx-1]
0x180021e9d  jnz     short loc_180021EB4
0x180021e9f  cmp     rcx, 4
0x180021ea3  jnz     short loc_180021E91
0x180021ea5  mov     dword ptr [rsi+0B8h], 2
0x180021eaf  jmp     loc_1800220B0
0x180021eb4  mov     rcx, r15
0x180021eb7  lea     rdx, [rbp+0B0h+var_50]
0x180021ebb  lea     r8, aVit; "VIT"
0x180021ec2  movzx   eax, byte ptr [rdx+rcx]
0x180021ec6  inc     rcx
0x180021ec9  cmp     al, [r8+rcx-1]
0x180021ece  jnz     short loc_180021F13
0x180021ed0  cmp     rcx, 4
0x180021ed4  jnz     short loc_180021EC2
0x180021ed6  mov     rcx, r15
0x180021ed9  lea     rdx, [rbp+0B0h+Src]
0x180021edd  lea     r8, aStx_0; "STX"
0x180021ee4  nop     dword ptr [rax+00h]
0x180021ee8  nop     dword ptr [rax+rax+00000000h]
0x180021ef0  movzx   eax, byte ptr [rdx+rcx]
0x180021ef4  inc     rcx
0x180021ef7  cmp     al, [r8+rcx-1]
0x180021efc  jnz     short loc_180021F13
0x180021efe  cmp     rcx, 4
0x180021f02  jnz     short loc_180021EF0
0x180021f04  mov     dword ptr [rsi+0B8h], 3
0x180021f0e  jmp     loc_1800220B0
0x180021f13  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180021f18  mov     rcx, rax
0x180021f1b  cmp     dword ptr [rax], 5
0x180021f1e  jbe     loc_1800220B0
0x180021f24  lea     rdx, [rbp+0B0h+Src]
0x180021f28  mov     rax, rdi
0x180021f2b  nop     dword ptr [rax+rax+00h]
0x180021f30  inc     rax
0x180021f33  cmp     byte ptr [rdx+rax], 0
0x180021f37  jnz     short loc_180021F30
0x180021f39  lea     rdx, [rbp+0B0h+Src]
0x180021f3d  mov     [rbp+0B0h+var_B0], rdx
0x180021f41  inc     eax
0x180021f43  mov     [rbp+0B0h+var_A8], eax
0x180021f46  mov     [rbp+0B0h+var_A4], r15d
0x180021f4a  lea     rax, [rbp+0B0h+var_50]
0x180021f4e  xchg    ax, ax
0x180021f50  lea     rdi, [rdi+1]
0x180021f54  cmp     byte ptr [rax+rdi], 0
0x180021f58  jnz     short loc_180021F50
0x180021f5a  lea     rax, [rbp+0B0h+var_50]
0x180021f5e  mov     [rbp+0B0h+var_C0], rax
0x180021f62  lea     eax, [rdi+1]
0x180021f65  mov     dword ptr [rbp+0B0h+var_B8], eax
0x180021f68  mov     dword ptr [rbp+0B0h+var_B8+4], r15d
0x180021f6c  mov     dword ptr [rbp+0B0h+EventDescriptor.Id], 0B000000h
0x180021f73  movzx   eax, cs:word_18004DB13
0x180021f7a  mov     dword ptr [rbp+0B0h+EventDescriptor.Level], eax
0x180021f7d  mov     [rbp+0B0h+EventDescriptor.Keyword], r15
0x180021f81  mov     rax, [rcx+8]
0x180021f85  mov     [rbp+0B0h+var_E0.Ptr], rax
0x180021f89  movzx   eax, word ptr [rax]
0x180021f8c  mov     [rbp+0B0h+var_E0.Size], eax
0x180021f8f  mov     dword ptr [rbp+0B0h+var_E0.0Ch], 2
0x180021f96  lea     rax, byte_18004DB1D
0x180021f9d  mov     [rbp+0B0h+var_D0], rax
0x180021fa1  mov     dword ptr [rbp+0B0h+var_C8], 1Dh
0x180021fa8  mov     dword ptr [rbp+0B0h+var_C8+4], 1
0x180021faf  mov     rax, r14
0x180021fb2  sub     eax, r12d
0x180021fb5  mov     dword ptr [rsp+1B0h+pSessionId], eax
0x180021fb9  mov     eax, dword ptr [rsp+1B0h+pSessionId]
0x180021fbd  lea     rax, [rbp+0B0h+var_E0]
0x180021fc1  mov     [rsp+1B0h+UserData], rax; UserData
0x180021fc6  mov     [rsp+1B0h+UserDataCount], 4; UserDataCount
0x180021fce  xor     r9d, r9d; RelatedActivityId
0x180021fd1  xor     r8d, r8d; ActivityId
0x180021fd4  lea     rdx, [rbp+0B0h+EventDescriptor]; EventDescriptor
0x180021fd8  mov     rcx, [rcx+20h]; RegHandle
0x180021fdc  call    cs:__imp_EventWriteTransfer
0x180021fe2  jmp     loc_1800220B0
0x180021fe7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57003568@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568> `wil::Feature<__WilFeatureTraits_Feature_57003568>::GetImpl(void)'::`2'::impl
0x180021fee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::__private_IsEnabled(void)
0x180021ff3  test    al, al
0x180021ff5  jz      loc_1800220B0
  ... truncated ...
```
