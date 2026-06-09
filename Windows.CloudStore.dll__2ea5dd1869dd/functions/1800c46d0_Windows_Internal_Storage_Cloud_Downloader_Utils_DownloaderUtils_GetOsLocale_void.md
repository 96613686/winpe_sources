# Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetOsLocale(void)

- ea: `0x1800c46d0`
- end: `0x1800c4824`
- name: `?GetOsLocale@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@QEAA?AUhstring@winrt@@XZ`
- size: `340`
- prototype: `struct winrt::hstring __high(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c482c`

## callees

- `0x1800122f4`
- `0x1800238d0`
- `0x180085f8c`
- `0x1800c46d0`
- `0x1800c67cc`
- `0x1800e48f8`
- `0x1800e49a0`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c475f`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c47a1`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c475f`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c47a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c470f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c470f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt::hstring *__fastcall Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetOsLocale(
        RTL_SRWLOCK *a1,
        winrt::hstring *a2)
{
  winrt::hstring *v2; // rdi
  const struct winrt::hstring *v4; // rbx
  BOOL SystemPreferredUILanguages; // eax
  WCHAR *v6; // r8
  const char *v7; // r9
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-68h] BYREF
  ULONG pulNumLanguages[3]; // [rsp+24h] [rbp-64h] BYREF
  winrt::hstring *v11; // [rsp+30h] [rbp-58h]
  const struct winrt::hstring *v12; // [rsp+38h] [rbp-50h]
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-40h] BYREF
  PZZWSTR pwszLanguagesBuffer[2]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v16; // [rsp+68h] [rbp-20h]
  unsigned __int64 v17; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = a2;
  v11 = a2;
  v4 = (const struct winrt::hstring *)&a1[2];
  v12 = (const struct winrt::hstring *)&a1[2];
  if ( !a1[2].Ptr )
  {
    AcquireSRWLockExclusive(a1);
    v13 = a1;
    if ( !*(_QWORD *)v4 )
    {
      *(_OWORD *)pwszLanguagesBuffer = 0;
      v16 = 0;
      v17 = 7;
      LOWORD(pwszLanguagesBuffer[0]) = 0;
      pulNumLanguages[0] = 0;
      pcchLanguagesBuffer = 0;
      SystemPreferredUILanguages = GetSystemPreferredUILanguages(8u, pulNumLanguages, 0, &pcchLanguagesBuffer);
      try
      {
        if ( SystemPreferredUILanguages && pulNumLanguages[0] && pcchLanguagesBuffer )
        {
          std::wstring::resize(pwszLanguagesBuffer);
          v6 = (WCHAR *)pwszLanguagesBuffer;
          if ( v17 > 7 )
            v6 = pwszLanguagesBuffer[0];
          GetSystemPreferredUILanguages(8u, pulNumLanguages, v6, &pcchLanguagesBuffer);
          std::wstring::resize(pwszLanguagesBuffer);
          std::wstring::operator std::basic_string_view<unsigned short>(pwszLanguagesBuffer, v14);
          winrt::hstring::operator=(v4);
        }
        std::wstring::~wstring(pwszLanguagesBuffer);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
          v7);
        v2 = v11;
        v4 = v12;
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v13);
  }
  winrt::hstring::hstring(v2, v4);
  return v2;
}

```

## disassembly

```asm
0x1800c46d0  mov     [rsp+arg_10], rbx
0x1800c46d5  mov     [rsp+arg_18], rsi
0x1800c46da  push    rdi
0x1800c46db  sub     rsp, 80h
0x1800c46e2  mov     rax, cs:__security_cookie
0x1800c46e9  xor     rax, rsp
0x1800c46ec  mov     [rsp+88h+var_10], rax
0x1800c46f1  mov     rdi, rdx
0x1800c46f4  mov     rsi, rcx
0x1800c46f7  mov     [rsp+88h+var_58], rdx
0x1800c46fc  lea     rbx, [rcx+10h]
0x1800c4700  mov     [rsp+88h+var_50], rbx
0x1800c4705  cmp     qword ptr [rbx], 0
0x1800c4709  jnz     loc_1800C47F4
0x1800c470f  call    cs:__imp_AcquireSRWLockExclusive
0x1800c4715  mov     [rsp+88h+var_48], rsi
0x1800c471a  cmp     qword ptr [rbx], 0
0x1800c471e  jnz     loc_1800C47EA
0x1800c4724  xorps   xmm0, xmm0
0x1800c4727  movups  xmmword ptr [rsp+88h+pwszLanguagesBuffer], xmm0
0x1800c472c  mov     [rsp+88h+var_20], 0
0x1800c4735  mov     [rsp+88h+var_18], 7
0x1800c473e  xor     eax, eax
0x1800c4740  mov     word ptr [rsp+88h+pwszLanguagesBuffer], ax
0x1800c4745  mov     [rsp+88h+pulNumLanguages], eax
0x1800c4749  mov     [rsp+88h+pcchLanguagesBuffer], eax
0x1800c474d  lea     r9, [rsp+88h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800c4752  xor     r8d, r8d; pwszLanguagesBuffer
0x1800c4755  lea     rdx, [rsp+88h+pulNumLanguages]; pulNumLanguages
0x1800c475a  lea     esi, [rax+8]
0x1800c475d  mov     ecx, esi; dwFlags
0x1800c475f  call    cs:__imp_GetSystemPreferredUILanguages
0x1800c4765  test    eax, eax
0x1800c4767  jz      short loc_1800C47D3
0x1800c4769  cmp     [rsp+88h+pulNumLanguages], 0
0x1800c476e  jbe     short loc_1800C47D3
0x1800c4770  mov     eax, [rsp+88h+pcchLanguagesBuffer]
0x1800c4774  test    eax, eax
0x1800c4776  jz      short loc_1800C47D3
0x1800c4778  mov     edx, eax
0x1800c477a  lea     rcx, [rsp+88h+pwszLanguagesBuffer]; Src
0x1800c477f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800c4784  lea     r8, [rsp+88h+pwszLanguagesBuffer]
0x1800c4789  cmp     [rsp+88h+var_18], 7
0x1800c478f  cmova   r8, [rsp+88h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1800c4795  lea     r9, [rsp+88h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800c479a  lea     rdx, [rsp+88h+pulNumLanguages]; pulNumLanguages
0x1800c479f  mov     ecx, esi; dwFlags
0x1800c47a1  call    cs:__imp_GetSystemPreferredUILanguages
0x1800c47a7  mov     rdx, [rsp+88h+var_20]
0x1800c47ac  lea     rcx, [rsp+88h+pwszLanguagesBuffer]; Src
0x1800c47b1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800c47b6  lea     rdx, [rsp+88h+var_40]
0x1800c47bb  lea     rcx, [rsp+88h+pwszLanguagesBuffer]
0x1800c47c0  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x1800c47c5  lea     rdx, [rsp+88h+var_40]
0x1800c47ca  mov     rcx, rbx
0x1800c47cd  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x1800c47d2  nop
0x1800c47d3  lea     rcx, [rsp+88h+pwszLanguagesBuffer]
0x1800c47d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c47dd  nop
0x1800c47de  jmp     short loc_1800C47EA
0x1800c47e0  mov     rdi, [rsp+88h+var_58]
0x1800c47e5  mov     rbx, [rsp+88h+var_50]
0x1800c47ea  lea     rcx, [rsp+88h+var_48]
0x1800c47ef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c47f4  mov     rdx, rbx; struct winrt::hstring *
0x1800c47f7  mov     rcx, rdi; this
0x1800c47fa  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800c47ff  mov     rax, rdi
0x1800c4802  mov     rcx, [rsp+88h+var_10]
0x1800c4807  xor     rcx, rsp; StackCookie
0x1800c480a  call    __security_check_cookie
0x1800c480f  lea     r11, [rsp+88h+var_8]
0x1800c4817  mov     rbx, [r11+20h]
0x1800c481b  mov     rsi, [r11+28h]
0x1800c481f  mov     rsp, r11
0x1800c4822  pop     rdi
0x1800c4823  retn
```
