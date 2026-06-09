# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadForResourceDll(winrt::hstring const &)

- ea: `0x18001d320`
- end: `0x18001d8c4`
- name: `?LoadForResourceDll@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@SA?AU13456@AEBUhstring@6@@Z`
- size: `1444`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e40`
- `0x18001d220`
- `0x180025c40`

## callees

- `0x180001b90`
- `0x1800027d0`
- `0x180002880`
- `0x1800029f0`
- `0x180003db0`
- `0x1800040a0`
- `0x180004810`
- `0x18000db50`
- `0x18000e550`
- `0x18000ec80`
- `0x1800101e0`
- `0x1800119b0`
- `0x18001b540`
- `0x18001cc10`
- `0x18001d320`
- `0x18002bee0`
- `0x18002bf50`
- `0x18002c050`
- `0x180034458`
- `0x180034460`
- `0x180034700`
- `0x180034974`
- `0x180034ef0`
- `0x180035060`
- `0x18003bed0`
- `0x18003c6e0`

## import_xrefs

- `VERSION!GetFileVersionInfoSizeW` at `0x18001d49a`
- `VERSION!GetFileVersionInfoSizeW` at `0x18001d49a`
- `VERSION!GetFileVersionInfoW` at `0x18001d567`
- `VERSION!GetFileVersionInfoW` at `0x18001d567`
- `VERSION!VerQueryValueW` at `0x18001d58f`
- `VERSION!VerQueryValueW` at `0x18001d58f`

## string_xrefs

- `0x18001d401`: `Microsoft.Windows.Workloads.Resources_ec.dll`
- `0x18001d408`: `Microsoft.Windows.Workloads.Resources.dll`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadForResourceDll(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v3; // rdx
  const wchar_t *v4; // rdx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r8
  const WCHAR *v7; // rcx
  unsigned int stats; // eax
  __int64 v9; // rdx
  unsigned int v10; // ecx
  bool v11; // al
  const wchar_t *v12; // rdx
  __int128 *v13; // rdx
  const WCHAR *v14; // rsi
  DWORD FileVersionInfoSizeW; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  size_t v18; // r15
  _QWORD *v19; // rdi
  unsigned int v20; // eax
  unsigned int v21; // eax
  bool v22; // zf
  unsigned __int8 v23; // al
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  LPCWSTR *v33; // rbx
  const struct _tlgProvider_t *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  const wchar_t *v37; // rbx
  volatile signed __int64 *v38; // rsi
  signed __int64 v39; // rax
  signed __int64 v40; // rtt
  LPVOID v41; // rbx
  LPVOID v42; // rsi
  __int64 v43; // r14
  __int64 v44; // r8
  BOOL v45; // edx
  __int64 v46; // r9
  __int64 i; // rax
  bool v48; // cf
  int v49; // eax
  __int64 *v50; // rax
  __int128 v52; // [rsp+30h] [rbp-69h] BYREF
  char *v53; // [rsp+40h] [rbp-59h]
  __int64 v54; // [rsp+48h] [rbp-51h]
  unsigned __int64 v55; // [rsp+58h] [rbp-41h]
  _QWORD v56[2]; // [rsp+60h] [rbp-39h] BYREF
  LPVOID lpBuffer; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR lptstrFilename[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v59; // [rsp+88h] [rbp-11h]
  unsigned __int64 v60; // [rsp+90h] [rbp-9h]
  __int128 v61; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v62; // [rsp+A8h] [rbp+Fh]
  unsigned __int64 v63; // [rsp+B0h] [rbp+17h]
  unsigned int puLen[2]; // [rsp+B8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  lpBuffer = a1;
  v3 = *a2;
  if ( v3 )
    v4 = *(const wchar_t **)(v3 + 16);
  else
    v4 = &Src;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  *(_OWORD *)lptstrFilename = 0;
  v59 = 0;
  v60 = 0;
  std::wstring::_Construct<1,wchar_t const *>(lptstrFilename, v4, v6);
  v7 = (const WCHAR *)lptstrFilename;
  if ( v60 > 7 )
    v7 = lptstrFilename[0];
  stats = _std_fs_get_stats(v7);
  v9 = stats;
  if ( stats )
  {
    if ( stats > 0x40 )
    {
      if ( stats == 123 )
        goto LABEL_36;
      v22 = stats == 267;
    }
    else
    {
      if ( stats == 64 )
        goto LABEL_36;
      v20 = stats - 2;
      if ( !v20 )
        goto LABEL_36;
      v21 = v20 - 1;
      if ( !v21 )
        goto LABEL_36;
      v22 = v21 == 50;
    }
    if ( !v22 )
    {
      v23 = 0;
LABEL_37:
      v10 = v23;
      if ( v23 != 1 && v23 != 9 )
        std::filesystem::_Throw_fs_error(v23, v9, (__int64)lptstrFilename);
      goto LABEL_12;
    }
LABEL_36:
    v23 = 1;
    goto LABEL_37;
  }
  if ( (v62 & 0x400) == 0 )
    goto LABEL_26;
  if ( HIDWORD(v62) == -1610612724 )
  {
    v10 = 4;
    goto LABEL_12;
  }
  if ( HIDWORD(v62) == -1610612733 )
    v10 = 10;
  else
LABEL_26:
    v10 = (((unsigned int)v62 >> 4) & 1) + 2;
LABEL_12:
  if ( v10 == 3 )
  {
    v11 = IsRunningOnArm64();
    v12 = L"Microsoft.Windows.Workloads.Resources.dll";
    if ( v11 )
      v12 = L"Microsoft.Windows.Workloads.Resources_ec.dll";
    v61 = 0;
    v62 = 0;
    v63 = 0;
    do
      ++v5;
    while ( v12[v5] );
    std::wstring::_Construct<1,wchar_t const *>(&v61, v12, v5);
    v13 = &v61;
    if ( v63 > 7 )
      v13 = (__int128 *)v61;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v52, v13, v62);
    std::filesystem::path::operator/=((std::filesystem *)lptstrFilename, (std::filesystem *)&v52);
    std::wstring::_Tidy_deallocate((__int64)&v52);
    std::wstring::_Tidy_deallocate((__int64)&v61);
  }
  v14 = (const WCHAR *)lptstrFilename;
  if ( v60 > 7 )
    v14 = lptstrFilename[0];
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(v14, 0);
  v18 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6C, v16, v17);
  v52 = 0;
  v53 = 0;
  _mm_lfence();
  v19 = std::_Allocate<16,std::_Default_allocate_traits>(FileVersionInfoSizeW);
  *(_QWORD *)&v52 = v19;
  v53 = (char *)v19 + v18;
  memset(v19, 0, v18);
  *((_QWORD *)&v52 + 1) = (char *)v19 + v18;
  if ( !GetFileVersionInfoW(v14, 0, v18, v19) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6E, v25, v26);
  lpBuffer = 0;
  if ( !VerQueryValueW(v19, L"\\", &lpBuffer, puLen) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x71, v27, v28);
  v29 = *((unsigned int *)lpBuffer + 3) | ((unsigned __int64)*((unsigned int *)lpBuffer + 2) << 32);
  std::vector<unsigned char>::_Tidy(&v52);
  v56[1] = &winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::s_mutex;
  if ( Mtx_lock((_Mtx_t)&winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::s_mutex) )
    std::_Throw_Cpp_error(5);
  if ( dword_18005838C == 0x7FFFFFFF )
  {
    dword_18005838C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v30 = *(_QWORD *)(winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager + 8);
  v31 = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager;
  while ( !*(_BYTE *)(v30 + 25) )
  {
    if ( *(_QWORD *)(v30 + 32) >= v29 )
    {
      v31 = v30;
      v30 = *(_QWORD *)v30;
    }
    else
    {
      v30 = *(_QWORD *)(v30 + 16);
    }
  }
  if ( *(_BYTE *)(v31 + 25) || v29 < *(_QWORD *)(v31 + 32) )
    v31 = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager;
  if ( v31 == winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager )
  {
    v33 = lptstrFilename;
    if ( v60 > 7 )
      v33 = (LPCWSTR *)lptstrFilename[0];
    v34 = TraceLogger::Provider();
    if ( *(_DWORD *)v34 > 5u )
    {
      lpBuffer = v33;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (__int64)v34,
        (unsigned __int8 *)byte_18004DA33,
        v35,
        v36,
        (const wchar_t **)&lpBuffer);
    }
    v37 = (const wchar_t *)lptstrFilename;
    if ( v60 > 7 )
      v37 = lptstrFilename[0];
    v38 = (volatile signed __int64 *)operator new(0xE8u);
    lpBuffer = (LPVOID)v38;
    winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::WorkloadManager(
      (winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *)v38,
      v29,
      v37);
    *v38 = (volatile signed __int64)&winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::`vftable';
    *(_QWORD *)puLen = v38;
    lpBuffer = (LPVOID)((__int64 (__fastcall *)(volatile signed __int64 *, __int64 *))winrt::implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::find_interface)(
                         v38,
                         &winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager>);
    if ( lpBuffer )
    {
      v39 = *((_QWORD *)v38 + 1);
      if ( v39 < 0 )
      {
LABEL_65:
        _InterlockedIncrement((volatile signed __int32 *)(2 * v39 + 24));
      }
      else
      {
        while ( 1 )
        {
          v40 = v39;
          v39 = _InterlockedCompareExchange64(v38 + 1, v39 + 1, v39);
          if ( v40 == v39 )
            break;
          if ( v39 < 0 )
            goto LABEL_65;
        }
      }
    }
    else
    {
      v49 = winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(
              v38,
              &winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager>,
              &lpBuffer);
      if ( v49 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v49);
      }
    }
    v41 = lpBuffer;
    v55 = v29;
    v42 = lpBuffer;
    v56[0] = lpBuffer;
    if ( lpBuffer )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpBuffer + 8LL))(lpBuffer);
    v43 = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager;
    v44 = *(_QWORD *)(winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager
                    + 8);
    v45 = 0;
    v46 = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager;
    for ( i = v44; !*(_BYTE *)(i + 25); v45 = !v48 )
    {
      v44 = i;
      v48 = *(_QWORD *)(i + 32) < v29;
      if ( *(_QWORD *)(i + 32) >= v29 )
      {
        v46 = i;
        i = *(_QWORD *)i;
      }
      else
      {
        i = *(_QWORD *)(i + 16);
      }
    }
    *(_QWORD *)&v61 = v44;
    DWORD2(v61) = v45;
    if ( *(_BYTE *)(v46 + 25) || v29 < *(_QWORD *)(v46 + 32) )
    {
      if ( qword_180059D48 == 0x555555555555555LL )
        std::_Throw_tree_length_error();
      *(_QWORD *)&v52 = &winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager;
      *((_QWORD *)&v52 + 1) = 0;
      v50 = (__int64 *)operator new(0x30u);
      v50[4] = v29;
      v42 = 0;
      v56[0] = 0;
      v50[5] = (__int64)v41;
      *v50 = v43;
      v50[1] = v43;
      v50[2] = v43;
      *((_WORD *)v50 + 12) = 0;
      v52 = v61;
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(
        &winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager,
        (__int64)&v52,
        (__int64)v50);
    }
    if ( v42 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v56);
    *a1 = v41;
    winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(puLen);
  }
  else
  {
    v32 = *(_QWORD *)(v31 + 40);
    *a1 = v32;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  }
  Mtx_unlock((_Mtx_t)&winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::s_mutex);
  std::wstring::_Tidy_deallocate((__int64)lptstrFilename);
  return a1;
}

```

## disassembly

```asm
0x18001d320  mov     [rsp-8+arg_8], rbx
0x18001d325  mov     [rsp-8+arg_10], rsi
0x18001d32a  mov     [rsp-8+arg_18], rdi
0x18001d32f  push    rbp
0x18001d330  push    r12
0x18001d332  push    r13
0x18001d334  push    r14
0x18001d336  push    r15
0x18001d338  lea     rbp, [rsp-37h]
0x18001d33d  sub     rsp, 0D0h
0x18001d344  mov     rax, cs:__security_cookie
0x18001d34b  xor     rax, rsp
0x18001d34e  mov     [rbp+57h+var_30], rax
0x18001d352  mov     r12, rcx
0x18001d355  mov     [rbp+57h+lpBuffer], rcx
0x18001d359  xor     r13d, r13d
0x18001d35c  mov     rdx, [rdx]
0x18001d35f  test    rdx, rdx
0x18001d362  jz      short loc_18001D36A
0x18001d364  mov     rdx, [rdx+10h]
0x18001d368  jmp     short loc_18001D371
0x18001d36a  lea     rdx, Src
0x18001d371  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001d378  mov     r8, rbx
0x18001d37b  nop     dword ptr [rax+rax+00h]
0x18001d380  inc     r8
0x18001d383  cmp     [rdx+r8*2], r13w
0x18001d388  jnz     short loc_18001D380
0x18001d38a  xorps   xmm0, xmm0
0x18001d38d  movups  xmmword ptr [rbp+57h+lptstrFilename], xmm0
0x18001d391  mov     [rbp+57h+var_68], r13
0x18001d395  mov     [rbp+57h+var_60], r13
0x18001d399  lea     rcx, [rbp+57h+lptstrFilename]
0x18001d39d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d3a2  nop
0x18001d3a3  lea     rcx, [rbp+57h+lptstrFilename]
0x18001d3a7  cmp     [rbp+57h+var_60], 7
0x18001d3ac  cmova   rcx, [rbp+57h+lptstrFilename]; lpFileName
0x18001d3b1  mov     r9d, 0FFFFFFFFh
0x18001d3b7  mov     r8d, 3
0x18001d3bd  lea     rdx, [rbp+57h+var_58]
0x18001d3c1  call    __std_fs_get_stats
0x18001d3c6  mov     edx, eax
0x18001d3c8  test    eax, eax
0x18001d3ca  jnz     loc_18001D50F
0x18001d3d0  mov     ecx, dword ptr [rbp+57h+var_48]
0x18001d3d3  mov     eax, ecx
0x18001d3d5  shr     eax, 0Ah
0x18001d3d8  test    al, 1
0x18001d3da  jz      loc_18001D501
0x18001d3e0  mov     eax, dword ptr [rbp+57h+var_48+4]
0x18001d3e3  cmp     eax, 0A000000Ch
0x18001d3e8  jnz     loc_18001D4F0
0x18001d3ee  mov     ecx, 4
0x18001d3f3  cmp     ecx, 3
0x18001d3f6  jnz     loc_18001D487
0x18001d3fc  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x18001d401  lea     rcx, aMicrosoftWindo_0; "Microsoft.Windows.Workloads.Resources_e"...
0x18001d408  lea     rdx, aMicrosoftWindo_21; "Microsoft.Windows.Workloads.Resources.d"...
0x18001d40f  test    al, al
0x18001d411  cmovnz  rdx, rcx
0x18001d415  xorps   xmm0, xmm0
0x18001d418  movups  [rbp+57h+var_58], xmm0
0x18001d41c  mov     [rbp+57h+var_48], r13
0x18001d420  mov     [rbp+57h+var_40], r13
0x18001d424  inc     rbx
0x18001d427  cmp     word ptr [rdx+rbx*2], 0
0x18001d42c  jnz     short loc_18001D424
0x18001d42e  mov     r8, rbx
0x18001d431  lea     rcx, [rbp+57h+var_58]
0x18001d435  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d43a  nop
0x18001d43b  lea     rdx, [rbp+57h+var_58]
0x18001d43f  cmp     [rbp+57h+var_40], 7
0x18001d444  cmova   rdx, qword ptr [rbp+57h+var_58]
0x18001d449  xorps   xmm0, xmm0
0x18001d44c  movups  [rbp+57h+var_C0], xmm0
0x18001d450  mov     [rbp+57h+var_B0], r13
0x18001d454  mov     [rbp+57h+var_A8], r13
0x18001d458  mov     r8, [rbp+57h+var_48]
0x18001d45c  lea     rcx, [rbp+57h+var_C0]
0x18001d460  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001d465  nop
0x18001d466  lea     rdx, [rbp+57h+var_C0]; void *
0x18001d46a  lea     rcx, [rbp+57h+lptstrFilename]; Src
0x18001d46e  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18001d473  nop
0x18001d474  lea     rcx, [rbp+57h+var_C0]
0x18001d478  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d47d  nop
0x18001d47e  lea     rcx, [rbp+57h+var_58]
0x18001d482  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d487  lea     rsi, [rbp+57h+lptstrFilename]
0x18001d48b  cmp     [rbp+57h+var_60], 7
0x18001d490  cmova   rsi, [rbp+57h+lptstrFilename]
0x18001d495  xor     edx, edx; lpdwHandle
0x18001d497  mov     rcx, rsi; lptstrFilename
0x18001d49a  call    cs:__imp_GetFileVersionInfoSizeW
0x18001d4a0  mov     r15d, eax
0x18001d4a3  mov     rcx, [rbp+5Fh]; this
0x18001d4a7  test    eax, eax
0x18001d4a9  jz      loc_18001D87F
0x18001d4af  xorps   xmm0, xmm0
0x18001d4b2  movdqu  [rbp+57h+var_C0], xmm0
0x18001d4b7  mov     [rbp+57h+var_B0], r13
0x18001d4bb  test    eax, eax
0x18001d4bd  jz      loc_18001D554
0x18001d4c3  lfence
0x18001d4c6  mov     rcx, r15
0x18001d4c9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001d4ce  mov     rdi, rax
0x18001d4d1  mov     qword ptr [rbp+57h+var_C0], rax
0x18001d4d5  lea     rbx, [rax+r15]
0x18001d4d9  mov     [rbp+57h+var_B0], rbx
0x18001d4dd  mov     r8, r15; Size
0x18001d4e0  xor     edx, edx; Val
0x18001d4e2  mov     rcx, rax; void *
0x18001d4e5  call    memset
0x18001d4ea  mov     qword ptr [rbp+57h+var_C0+8], rbx
0x18001d4ee  jmp     short loc_18001D558
0x18001d4f0  cmp     eax, 0A0000003h
0x18001d4f5  jnz     short loc_18001D501
0x18001d4f7  mov     ecx, 0Ah
0x18001d4fc  jmp     loc_18001D3F3
0x18001d501  shr     ecx, 4
0x18001d504  and     ecx, 1
0x18001d507  add     ecx, 2
0x18001d50a  jmp     loc_18001D3F3
0x18001d50f  cmp     edx, 40h ; '@'
0x18001d512  ja      short loc_18001D525
0x18001d514  jz      short loc_18001D536
0x18001d516  sub     eax, 2
0x18001d519  jz      short loc_18001D536
0x18001d51b  sub     eax, 1
0x18001d51e  jz      short loc_18001D536
0x18001d520  cmp     eax, 32h ; '2'
0x18001d523  jmp     short loc_18001D530
0x18001d525  cmp     edx, 7Bh ; '{'
0x18001d528  jz      short loc_18001D536
0x18001d52a  cmp     edx, 10Bh
0x18001d530  jz      short loc_18001D536
0x18001d532  xor     al, al
0x18001d534  jmp     short loc_18001D538
0x18001d536  mov     al, 1
0x18001d538  movzx   eax, al
0x18001d53b  mov     ecx, eax
0x18001d53d  cmp     eax, 1
0x18001d540  jz      loc_18001D3F3
0x18001d546  cmp     eax, 9
0x18001d549  jnz     loc_18001D86A
0x18001d54f  jmp     loc_18001D3F3
0x18001d554  mov     rdi, qword ptr [rbp+57h+var_C0]
0x18001d558  mov     rbx, [rbp+5Fh]
0x18001d55c  mov     r9, rdi; lpData
0x18001d55f  mov     r8d, r15d; dwLen
0x18001d562  xor     edx, edx; dwHandle
0x18001d564  mov     rcx, rsi; lptstrFilename
0x18001d567  call    cs:__imp_GetFileVersionInfoW
0x18001d56d  test    eax, eax
0x18001d56f  jz      loc_18001D88A
0x18001d575  mov     [rbp+57h+lpBuffer], r13
0x18001d579  mov     rbx, [rbp+5Fh]
0x18001d57d  lea     r9, [rbp+57h+puLen]; puLen
0x18001d581  lea     r8, [rbp+57h+lpBuffer]; lplpBuffer
0x18001d585  lea     rdx, SubBlock; "\\"
0x18001d58c  mov     rcx, rdi; pBlock
0x18001d58f  call    cs:__imp_VerQueryValueW
0x18001d595  test    eax, eax
0x18001d597  jz      loc_18001D898
0x18001d59d  mov     rax, [rbp+57h+lpBuffer]
0x18001d5a1  mov     edi, [rax+8]
0x18001d5a4  shl     rdi, 20h
0x18001d5a8  mov     eax, [rax+0Ch]
0x18001d5ab  or      rdi, rax
0x18001d5ae  lea     rcx, [rbp+57h+var_C0]
0x18001d5b2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d5b7  lea     r15, ?s_mutex@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@0Vmutex@std@@A; std::mutex winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::s_mutex
0x18001d5be  mov     [rbp+57h+var_88], r15
0x18001d5c2  mov     rcx, r15; _Mtx_t
0x18001d5c5  call    _Mtx_lock
0x18001d5ca  test    eax, eax
0x18001d5cc  jnz     loc_18001D8A6
0x18001d5d2  mov     eax, cs:dword_18005838C
0x18001d5d8  cmp     eax, 7FFFFFFFh
0x18001d5dd  jz      loc_18001D8B1
0x18001d5e3  mov     rdx, cs:?m_versionToWorkloadManager@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@0V?$map@_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@@7@@std@@A; std::map<unsigned __int64,winrt::Microsoft::Windows::Workloads::WorkloadManager> winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager
0x18001d5ea  mov     rax, [rdx+8]
0x18001d5ee  mov     rcx, rdx
0x18001d5f1  cmp     byte ptr [rax+19h], 0
0x18001d5f5  jnz     short loc_18001D60F
0x18001d5f7  cmp     [rax+20h], rdi
0x18001d5fb  jnb     short loc_18001D603
0x18001d5fd  mov     rax, [rax+10h]
0x18001d601  jmp     short loc_18001D609
0x18001d603  mov     rcx, rax
0x18001d606  mov     rax, [rax]
0x18001d609  cmp     byte ptr [rax+19h], 0
0x18001d60d  jz      short loc_18001D5F7
0x18001d60f  cmp     byte ptr [rcx+19h], 0
0x18001d613  jnz     short loc_18001D61B
0x18001d615  cmp     rdi, [rcx+20h]
0x18001d619  jnb     short loc_18001D61E
0x18001d61b  mov     rcx, rdx
0x18001d61e  cmp     rcx, rdx
0x18001d621  jz      short loc_18001D646
0x18001d623  mov     rcx, [rcx+28h]
0x18001d627  mov     [r12], rcx
0x18001d62b  test    rcx, rcx
0x18001d62e  jz      loc_18001D822
0x18001d634  mov     rdx, [rcx]
0x18001d637  mov     rax, [rdx+8]
0x18001d63b  call    cs:__guard_dispatch_icall_fptr
0x18001d641  jmp     loc_18001D822
0x18001d646  lea     rbx, [rbp+57h+lptstrFilename]
0x18001d64a  cmp     [rbp+57h+var_60], 7
0x18001d64f  cmova   rbx, [rbp+57h+lptstrFilename]
0x18001d654  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001d659  cmp     dword ptr [rax], 5
0x18001d65c  jbe     short loc_18001D67A
0x18001d65e  mov     [rbp+57h+lpBuffer], rbx
0x18001d662  lea     rcx, [rbp+57h+lpBuffer]
0x18001d666  mov     [rsp+0F0h+var_D0], rcx
0x18001d66b  lea     rdx, byte_18004DA33
0x18001d672  mov     rcx, rax
0x18001d675  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001d67a  lea     rbx, [rbp+57h+lptstrFilename]
0x18001d67e  cmp     [rbp+57h+var_60], 7
0x18001d683  cmova   rbx, [rbp+57h+lptstrFilename]
0x18001d688  mov     ecx, 0E8h; Size
0x18001d68d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d692  mov     rsi, rax
0x18001d695  mov     [rbp+57h+lpBuffer], rax
0x18001d699  mov     r8, rbx; wchar_t *
0x18001d69c  mov     rdx, rdi; unsigned __int64
0x18001d69f  mov     rcx, rax; this
0x18001d6a2  call    ??0WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@QEAA@_KPEB_W@Z; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::WorkloadManager(unsigned __int64,wchar_t const *)
0x18001d6a7  lea     rax, ??_7?$heap_implements@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::`vftable'
0x18001d6ae  mov     [rsi], rax
0x18001d6b1  mov     qword ptr [rbp+57h+puLen], rsi
0x18001d6b5  lea     rdx, ??$guid_v@UIWorkloadManager@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager>
0x18001d6bc  mov     rcx, rsi
0x18001d6bf  mov     rax, cs:off_18004A850
0x18001d6c6  call    cs:__guard_dispatch_icall_fptr
0x18001d6cc  mov     [rbp+57h+lpBuffer], rax
0x18001d6d0  test    rax, rax
0x18001d6d3  jz      short loc_18001D74F
0x18001d6d5  mov     rax, [rsi+8]
0x18001d6d9  test    rax, rax
0x18001d6dc  js      short loc_18001D6F1
0x18001d6de  xchg    ax, ax
0x18001d6e0  lea     rcx, [rax+1]
0x18001d6e4  lock cmpxchg [rsi+8], rcx
0x18001d6ea  jz      short loc_18001D6F6
0x18001d6ec  test    rax, rax
0x18001d6ef  jns     short loc_18001D6E0
0x18001d6f1  lock inc dword ptr [rax+rax+18h]
0x18001d6f6  mov     rbx, [rbp+57h+lpBuffer]
0x18001d6fa  mov     [rbp+57h+lpBuffer], rbx
0x18001d6fe  mov     [rbp+57h+var_98], rdi
0x18001d702  mov     rsi, rbx
0x18001d705  mov     [rbp+57h+var_90], rbx
0x18001d709  test    rbx, rbx
0x18001d70c  jz      short loc_18001D71F
0x18001d70e  mov     rax, [rbx]
0x18001d711  mov     rcx, rbx
0x18001d714  mov     rax, [rax+8]
0x18001d718  call    cs:__guard_dispatch_icall_fptr
0x18001d71e  nop
0x18001d71f  mov     r14, cs:?m_versionToWorkloadManager@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@0V?$map@_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@@7@@std@@A; std::map<unsigned __int64,winrt::Microsoft::Windows::Workloads::WorkloadManager> winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::m_versionToWorkloadManager
0x18001d726  mov     r8, [r14+8]
0x18001d72a  mov     edx, r13d
0x18001d72d  mov     r9, r14
0x18001d730  mov     rax, r8
0x18001d733  cmp     [r8+19h], r13b
0x18001d737  jnz     short loc_18001D77E
0x18001d739  nop     dword ptr [rax+00000000h]
0x18001d740  mov     r8, rax
0x18001d743  cmp     [rax+20h], rdi
0x18001d747  jnb     short loc_18001D76C
0x18001d749  mov     rax, [rax+10h]
0x18001d74d  jmp     short loc_18001D772
0x18001d74f  lea     r8, [rbp+57h+lpBuffer]
0x18001d753  lea     rdx, ??$guid_v@UIWorkloadManager@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager>
0x18001d75a  mov     rcx, rsi
0x18001d75d  call    ?query_interface_common@?$root_implements@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@U13456@UIWorkloadManager2@3456@UIWorkloadManager3@3456@UIWorkloadManager4@3456@UIWorkloadManager5@3456@UIWorkloadManager6@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(winrt::guid const &,void * *)
0x18001d762  test    eax, eax
0x18001d764  js      loc_18001D874
0x18001d76a  jmp     short loc_18001D6F6
0x18001d76c  mov     r9, rax
0x18001d76f  mov     rax, [rax]
0x18001d772  mov     edx, r13d
0x18001d775  setnb   dl
0x18001d778  cmp     byte ptr [rax+19h], 0
0x18001d77c  jz      short loc_18001D740
0x18001d77e  mov     qword ptr [rbp+57h+var_58], r8
0x18001d782  mov     dword ptr [rbp+57h+var_58+8], edx
0x18001d785  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x18001d788  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x18001d78b  cmp     byte ptr [r9+19h], 0
0x18001d790  jnz     short loc_18001D798
  ... truncated ...
```
