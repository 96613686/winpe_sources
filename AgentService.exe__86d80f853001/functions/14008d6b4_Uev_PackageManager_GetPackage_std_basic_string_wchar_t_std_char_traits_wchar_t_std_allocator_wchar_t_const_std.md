# Uev::PackageManager::GetPackage(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,boost::filesystem::path &)

- ea: `0x14008d6b4`
- end: `0x14008da55`
- name: `?GetPackage@PackageManager@Uev@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAVpath@filesystem@boost@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(__int64, __int64, boost::filesystem::path *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140036b50`
- `0x14003cc50`

## callees

- `0x140003e50`
- `0x140004d40`
- `0x140005b30`
- `0x140006b10`
- `0x140008e60`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000bacc`
- `0x1400231f8`
- `0x14008d60c`
- `0x14008d6b4`
- `0x14008da78`
- `0x14008dae4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14008d6fc`
- `KERNEL32!GetCurrentThreadId` at `0x14008d6fc`
- `KERNEL32!SetEvent` at `0x14008da16`
- `KERNEL32!SetEvent` at `0x14008da16`

## pseudocode

```c
__int64 __fastcall Uev::PackageManager::GetPackage(__int64 a1, __int64 a2, boost::filesystem::path *a3)
{
  DWORD CurrentThreadId; // eax
  __int32 v6; // ebx
  __int64 ConfiguredRootPath; // rbx
  __int128 v8; // xmm6
  __m128i v9; // xmm7
  __int64 v10; // r8
  __int128 *v11; // r9
  __int64 *v12; // rax
  unsigned int v13; // ebx
  signed __int32 v14; // eax
  void *event; // rax
  __int64 result; // rax
  boost::filesystem::filesystem_error *v17; // rdi
  __int64 v18; // rax
  int v19; // eax
  const wchar_t *v20; // rbx
  boost::system::error_code *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  int v26; // edx
  int v27; // ecx
  int v28; // r9d
  __int64 v29; // rax
  __int128 v30; // [rsp+40h] [rbp-178h] BYREF
  __m128i si128; // [rsp+50h] [rbp-168h]
  __int128 v32; // [rsp+60h] [rbp-158h] BYREF
  __m128i v33; // [rsp+70h] [rbp-148h]
  __int64 v34; // [rsp+80h] [rbp-138h]
  _OWORD v35[2]; // [rsp+88h] [rbp-130h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-110h] BYREF
  __m128i v37; // [rsp+B8h] [rbp-100h]
  _BYTE v38[8]; // [rsp+C8h] [rbp-F0h] BYREF
  boost::filesystem::filesystem_error *v39; // [rsp+D0h] [rbp-E8h] BYREF
  _BYTE v40[32]; // [rsp+D8h] [rbp-E0h] BYREF
  _BYTE v41[32]; // [rsp+F8h] [rbp-C0h] BYREF
  _BYTE v42[40]; // [rsp+118h] [rbp-A0h] BYREF
  _BYTE v43[64]; // [rsp+140h] [rbp-78h] BYREF
  void *v44; // [rsp+180h] [rbp-38h] BYREF

  v34 = a2;
  v44 = &Uev::PackageManager::m_packagePathMutex;
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    v6 = CurrentThreadId;
    if ( dword_1400D19B4 == CurrentThreadId )
    {
      ++Uev::PackageManager::m_packagePathMutex;
    }
    else
    {
      boost::detail::basic_timed_mutex::lock((boost::detail::basic_timed_mutex *)&dword_1400D19B8);
      _InterlockedExchange(&dword_1400D19B4, v6);
      Uev::PackageManager::m_packagePathMutex = 1;
    }
    std::wstring::wstring(v42, a2);
    std::wstring::wstring(v41, Uev::PackageManager::currentDirName);
    std::wstring::wstring(v35, a2);
    ConfiguredRootPath = Uev::PackageManager::GetConfiguredRootPath(v40);
    boost::filesystem::path::append_v3(
      (boost::filesystem::path *)ConfiguredRootPath,
      (const struct boost::filesystem::path *)v35);
    v30 = 0;
    si128 = 0;
    v30 = *(_OWORD *)ConfiguredRootPath;
    si128 = *(__m128i *)(ConfiguredRootPath + 16);
    *(_QWORD *)(ConfiguredRootPath + 16) = 0;
    *(_QWORD *)(ConfiguredRootPath + 24) = 7;
    *(_WORD *)ConfiguredRootPath = 0;
    boost::filesystem::path::append_v3((boost::filesystem::path *)&v30, (const struct boost::filesystem::path *)v41);
    v32 = v30;
    v33 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v30) = 0;
    boost::filesystem::path::append_v3((boost::filesystem::path *)&v32, (const struct boost::filesystem::path *)v42);
    v8 = v32;
    v36 = v32;
    v9 = v33;
    v37 = v33;
    v33 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v32) = 0;
    if ( a3 != (boost::filesystem::path *)&v36 )
    {
      std::wstring::_Tidy_deallocate(a3);
      *(_OWORD *)a3 = v8;
      *((__m128i *)a3 + 1) = v9;
      v37 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v36) = 0;
    }
    std::wstring::_Tidy_deallocate(&v36);
    std::wstring::_Tidy_deallocate(&v32);
    std::wstring::_Tidy_deallocate(&v30);
    std::wstring::_Tidy_deallocate(v40);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(v41);
    std::wstring::_Tidy_deallocate(v42);
    boost::filesystem::path::extension_v3(a3, &v30);
    if ( 0x7FFFFFFFFFFFFFFELL - si128.m128i_i64[0] < (unsigned __int64)qword_1400D1E70 )
      std::_Xlen_string();
    v11 = &v30;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v30;
    v12 = &Uev::packageExtension;
    if ( (unsigned __int64)qword_1400D1E78 > 7 )
      v12 = (__int64 *)Uev::packageExtension;
    std::wstring::wstring(&v32, qword_1400D1E70, v10, v11, si128.m128i_i64[0], v12, qword_1400D1E70);
    v35[0] = v32;
    v35[1] = v33;
    v33 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v32) = 0;
    boost::filesystem::path::replace_extension_v3(a3, (const struct boost::filesystem::path *)v35);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(&v32);
    std::wstring::_Tidy_deallocate(&v30);
    v13 = *(_DWORD *)boost::filesystem::detail::status(v38, a3, 0) <= 1u ? 0x80070002 : 0;
    if ( !--Uev::PackageManager::m_packagePathMutex )
    {
      _InterlockedExchange(&dword_1400D19B4, 0);
      v14 = _InterlockedExchangeAdd((volatile signed __int32 *)&dword_1400D19B8, 0x80000000);
      if ( (v14 & 0x40000000) == 0
        && v14 != 0x80000000
        && !_interlockedbittestandset((volatile signed __int32 *)&dword_1400D19B8, 0x1Eu) )
      {
        event = boost::detail::basic_timed_mutex::get_event((boost::detail::basic_timed_mutex *)&dword_1400D19B8);
        SetEvent(event);
      }
    }
    result = v13;
  }
  catch ( boost::filesystem::filesystem_error *v39 )
  {
    std::unique_ptr<wchar_t [0]>::unique_ptr<wchar_t [0]>(&v44);
    v17 = v39;
    v18 = (*(__int64 (__fastcall **)(boost::filesystem::filesystem_error *))(*(_QWORD *)v17 + 8LL))(v17);
    v19 = Uev::PackageManager::ConvertMultibyteStringToWideString(v18, &v44);
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
    {
      if ( v19 < 0 )
        v20 = L"Unknown";
      else
        v20 = (const wchar_t *)std::_Ptr_base<Uev::ConfigUtil>::get(&v44);
      v21 = (boost::system::error_code *)boost::system::system_error::code(v17, &v30);
      v22 = boost::system::error_code::value(v21);
      v25 = std::wstring::c_str(v34, v23, v24, v22);
      McTemplateU0zdz_EventWriteTransfer(v27, v26, v25, v28, (__int64)v20);
    }
    v29 = (*(__int64 (__fastcall **)(boost::filesystem::filesystem_error *))(*(_QWORD *)v17 + 8LL))(v17);
    std::string::string(v40, v29);
    Uev::PackageManagerException::PackageManagerException(v43, v40);
    throw (Uev::PackageManagerException *)v43;
  }
  v6 = CurrentThreadId;
}

```

## disassembly

```asm
0x14008d6b4  mov     r11, rsp
0x14008d6b7  mov     [r11+8], rbx
0x14008d6bb  mov     [r11+20h], rsi
0x14008d6bf  push    rdi
0x14008d6c0  sub     rsp, 1B0h
0x14008d6c7  movaps  xmmword ptr [r11-18h], xmm6
0x14008d6cc  movaps  xmmword ptr [r11-28h], xmm7
0x14008d6d1  mov     rax, cs:__security_cookie
0x14008d6d8  xor     rax, rsp
0x14008d6db  mov     [rsp+1B8h+var_30], rax
0x14008d6e3  mov     rsi, r8
0x14008d6e6  mov     rdi, rdx
0x14008d6e9  mov     [rsp+1B8h+var_138], rdx
0x14008d6f1  lea     rax, ?m_packagePathMutex@PackageManager@Uev@@0Vrecursive_mutex@boost@@A; boost::recursive_mutex Uev::PackageManager::m_packagePathMutex
0x14008d6f8  mov     [r11-38h], rax
0x14008d6fc  call    cs:__imp_GetCurrentThreadId
0x14008d702  mov     ebx, eax
0x14008d704  mov     ecx, cs:dword_1400D19B4
0x14008d70a  nop
0x14008d70b  cmp     ecx, eax
0x14008d70d  jnz     short loc_14008D717
0x14008d70f  inc     cs:?m_packagePathMutex@PackageManager@Uev@@0Vrecursive_mutex@boost@@A; boost::recursive_mutex Uev::PackageManager::m_packagePathMutex
0x14008d715  jmp     short loc_14008D733
0x14008d717  lea     rcx, dword_1400D19B8; this
0x14008d71e  call    ?lock@basic_timed_mutex@detail@boost@@QEAAXXZ; boost::detail::basic_timed_mutex::lock(void)
0x14008d723  xchg    ebx, cs:dword_1400D19B4
0x14008d729  mov     cs:?m_packagePathMutex@PackageManager@Uev@@0Vrecursive_mutex@boost@@A, 1; boost::recursive_mutex Uev::PackageManager::m_packagePathMutex
0x14008d733  mov     rdx, rdi
0x14008d736  lea     rcx, [rsp+1B8h+var_A0]
0x14008d73e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008d743  nop
0x14008d744  lea     rdx, ?currentDirName@PackageManager@Uev@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::PackageManager::currentDirName
0x14008d74b  lea     rcx, [rsp+1B8h+var_C0]
0x14008d753  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008d758  nop
0x14008d759  mov     rdx, rdi
0x14008d75c  lea     rcx, [rsp+1B8h+var_130]
0x14008d764  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008d769  nop
0x14008d76a  lea     rcx, [rsp+1B8h+var_E0]
0x14008d772  call    ?GetConfiguredRootPath@PackageManager@Uev@@CA?AVpath@filesystem@boost@@XZ; Uev::PackageManager::GetConfiguredRootPath(void)
0x14008d777  mov     rbx, rax
0x14008d77a  lea     rdx, [rsp+1B8h+var_130]; struct boost::filesystem::path *
0x14008d782  mov     rcx, rax; this
0x14008d785  call    ?append_v3@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::append_v3(boost::filesystem::path const &)
0x14008d78a  xorps   xmm0, xmm0
0x14008d78d  movups  [rsp+1B8h+var_178], xmm0
0x14008d792  xorps   xmm1, xmm1
0x14008d795  movdqu  [rsp+1B8h+var_168], xmm1
0x14008d79b  movups  xmm0, xmmword ptr [rbx]
0x14008d79e  movups  [rsp+1B8h+var_178], xmm0
0x14008d7a3  movups  xmm1, xmmword ptr [rbx+10h]
0x14008d7a7  movups  [rsp+1B8h+var_168], xmm1
0x14008d7ac  mov     qword ptr [rbx+10h], 0
0x14008d7b4  mov     qword ptr [rbx+18h], 7
0x14008d7bc  xor     eax, eax
0x14008d7be  mov     [rbx], ax
0x14008d7c1  lea     rdx, [rsp+1B8h+var_C0]; struct boost::filesystem::path *
0x14008d7c9  lea     rcx, [rsp+1B8h+var_178]; this
0x14008d7ce  call    ?append_v3@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::append_v3(boost::filesystem::path const &)
0x14008d7d3  movups  xmm0, [rsp+1B8h+var_178]
0x14008d7d8  movups  [rsp+1B8h+var_158], xmm0
0x14008d7dd  movups  xmm1, [rsp+1B8h+var_168]
0x14008d7e2  movups  [rsp+1B8h+var_148], xmm1
0x14008d7e7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008d7ef  movdqu  [rsp+1B8h+var_168], xmm0
0x14008d7f5  xor     eax, eax
0x14008d7f7  mov     word ptr [rsp+1B8h+var_178], ax
0x14008d7fc  lea     rdx, [rsp+1B8h+var_A0]; struct boost::filesystem::path *
0x14008d804  lea     rcx, [rsp+1B8h+var_158]; this
0x14008d809  call    ?append_v3@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::append_v3(boost::filesystem::path const &)
0x14008d80e  movups  xmm6, [rsp+1B8h+var_158]
0x14008d813  movups  [rsp+1B8h+var_110], xmm6
0x14008d81b  movups  xmm7, [rsp+1B8h+var_148]
0x14008d820  movdqu  [rsp+1B8h+var_100], xmm7
0x14008d829  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008d831  movdqu  [rsp+1B8h+var_148], xmm0
0x14008d837  xor     eax, eax
0x14008d839  mov     word ptr [rsp+1B8h+var_158], ax
0x14008d83e  lea     rax, [rsp+1B8h+var_110]
0x14008d846  cmp     rsi, rax
0x14008d849  jz      short loc_14008D875
0x14008d84b  mov     rcx, rsi
0x14008d84e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d853  movups  xmmword ptr [rsi], xmm6
0x14008d856  movups  xmmword ptr [rsi+10h], xmm7
0x14008d85a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008d862  movdqu  [rsp+1B8h+var_100], xmm0
0x14008d86b  xor     eax, eax
0x14008d86d  mov     word ptr [rsp+1B8h+var_110], ax
0x14008d875  lea     rcx, [rsp+1B8h+var_110]
0x14008d87d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d882  nop
0x14008d883  lea     rcx, [rsp+1B8h+var_158]
0x14008d888  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d88d  nop
0x14008d88e  lea     rcx, [rsp+1B8h+var_178]
0x14008d893  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d898  nop
0x14008d899  lea     rcx, [rsp+1B8h+var_E0]
0x14008d8a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d8a6  nop
0x14008d8a7  lea     rcx, [rsp+1B8h+var_130]
0x14008d8af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d8b4  nop
0x14008d8b5  lea     rcx, [rsp+1B8h+var_C0]
0x14008d8bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d8c2  nop
0x14008d8c3  lea     rcx, [rsp+1B8h+var_A0]
0x14008d8cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d8d0  lea     rdx, [rsp+1B8h+var_178]
0x14008d8d5  mov     rcx, rsi
0x14008d8d8  call    ?extension_v3@path@filesystem@boost@@AEBA?AV123@XZ; boost::filesystem::path::extension_v3(void)
0x14008d8dd  nop
0x14008d8de  mov     rcx, qword ptr [rsp+1B8h+var_168]
0x14008d8e3  mov     rdx, cs:qword_1400D1E70
0x14008d8ea  mov     rax, 7FFFFFFFFFFFFFFEh
0x14008d8f4  sub     rax, rcx
0x14008d8f7  cmp     rax, rdx
0x14008d8fa  jb      loc_14008DA4E
0x14008d900  lea     r9, [rsp+1B8h+var_178]
0x14008d905  cmp     qword ptr [rsp+1B8h+var_168+8], 7
0x14008d90b  cmova   r9, qword ptr [rsp+1B8h+var_178]
0x14008d911  lea     rax, ?packageExtension@Uev@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::packageExtension
0x14008d918  cmp     cs:qword_1400D1E78, 7
0x14008d920  cmova   rax, cs:?packageExtension@Uev@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::packageExtension
0x14008d928  mov     [rsp+1B8h+var_188], rdx
0x14008d92d  mov     [rsp+1B8h+var_190], rax
0x14008d932  mov     [rsp+1B8h+var_198], rcx
0x14008d937  lea     rcx, [rsp+1B8h+var_158]
0x14008d93c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008d941  nop
0x14008d942  movups  xmm0, [rsp+1B8h+var_158]
0x14008d947  movups  [rsp+1B8h+var_130], xmm0
0x14008d94f  movups  xmm1, [rsp+1B8h+var_148]
0x14008d954  movups  [rsp+1B8h+var_120], xmm1
0x14008d95c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008d964  movdqu  [rsp+1B8h+var_148], xmm0
0x14008d96a  xor     eax, eax
0x14008d96c  mov     word ptr [rsp+1B8h+var_158], ax
0x14008d971  lea     rdx, [rsp+1B8h+var_130]; struct boost::filesystem::path *
0x14008d979  mov     rcx, rsi; this
0x14008d97c  call    ?replace_extension_v3@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::replace_extension_v3(boost::filesystem::path const &)
0x14008d981  nop
0x14008d982  lea     rcx, [rsp+1B8h+var_130]
0x14008d98a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d98f  nop
0x14008d990  lea     rcx, [rsp+1B8h+var_158]
0x14008d995  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d99a  nop
0x14008d99b  lea     rcx, [rsp+1B8h+var_178]
0x14008d9a0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008d9a5  xor     r8d, r8d
0x14008d9a8  mov     rdx, rsi
0x14008d9ab  lea     rcx, [rsp+1B8h+var_F0]
0x14008d9b3  call    ?status@detail@filesystem@boost@@YA?AVfile_status@23@AEBVpath@23@PEAVerror_code@system@3@@Z; boost::filesystem::detail::status(boost::filesystem::path const &,boost::system::error_code *)
0x14008d9b8  cmp     dword ptr [rax], 1
0x14008d9bb  setnbe  al
0x14008d9be  neg     al
0x14008d9c0  sbb     ebx, ebx
0x14008d9c2  not     ebx
0x14008d9c4  and     ebx, 80070002h
0x14008d9ca  mov     eax, cs:?m_packagePathMutex@PackageManager@Uev@@0Vrecursive_mutex@boost@@A; boost::recursive_mutex Uev::PackageManager::m_packagePathMutex
0x14008d9d0  sub     eax, 1
0x14008d9d3  mov     cs:?m_packagePathMutex@PackageManager@Uev@@0Vrecursive_mutex@boost@@A, eax; boost::recursive_mutex Uev::PackageManager::m_packagePathMutex
0x14008d9d9  jnz     short loc_14008DA1D
0x14008d9db  xor     eax, eax
0x14008d9dd  xchg    eax, cs:dword_1400D19B4
0x14008d9e3  mov     ecx, 80000000h
0x14008d9e8  mov     eax, ecx
0x14008d9ea  lock xadd cs:dword_1400D19B8, eax
0x14008d9f2  bt      eax, 1Eh
0x14008d9f6  jb      short loc_14008DA1D
0x14008d9f8  cmp     eax, ecx
0x14008d9fa  jle     short loc_14008DA1D
0x14008d9fc  lock bts cs:dword_1400D19B8, 1Eh
0x14008da05  jb      short loc_14008DA1D
0x14008da07  lea     rcx, dword_1400D19B8; this
0x14008da0e  call    ?get_event@basic_timed_mutex@detail@boost@@AEAAPEAXXZ; boost::detail::basic_timed_mutex::get_event(void)
0x14008da13  mov     rcx, rax; hEvent
0x14008da16  call    cs:__imp_SetEvent
0x14008da1c  nop
0x14008da1d  mov     eax, ebx
0x14008da1f  mov     rcx, [rsp+1B8h+var_30]
0x14008da27  xor     rcx, rsp; StackCookie
0x14008da2a  call    __security_check_cookie
0x14008da2f  lea     r11, [rsp+1B8h+var_8]
0x14008da37  mov     rbx, [r11+10h]
0x14008da3b  mov     rsi, [r11+28h]
0x14008da3f  movaps  xmm6, xmmword ptr [r11-10h]
0x14008da44  movaps  xmm7, xmmword ptr [r11-20h]
0x14008da49  mov     rsp, r11
0x14008da4c  pop     rdi
0x14008da4d  retn
0x14008da4e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
