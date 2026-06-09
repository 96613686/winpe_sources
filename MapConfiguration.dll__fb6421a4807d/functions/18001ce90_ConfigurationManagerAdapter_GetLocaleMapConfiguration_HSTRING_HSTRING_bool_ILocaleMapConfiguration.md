# ConfigurationManagerAdapter::GetLocaleMapConfiguration(HSTRING__ *,HSTRING__ *,bool,ILocaleMapConfiguration * *)

- ea: `0x18001ce90`
- end: `0x18001d007`
- name: `?GetLocaleMapConfiguration@ConfigurationManagerAdapter@@UEAAJPEAUHSTRING__@@0_NPEAPEAUILocaleMapConfiguration@@@Z`
- size: `375`
- prototype: `int(ConfigurationManagerAdapter *__hidden this, HSTRING, HSTRING, bool, struct ILocaleMapConfiguration **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000b8c8`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c3ac`
- `0x180010f34`
- `0x180011e18`
- `0x180013d04`
- `0x1800153e8`
- `0x18001cb70`
- `0x18001ce90`
- `0x18001d254`
- `0x180020ec0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cf82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cf82`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConfigurationManagerAdapter::GetLocaleMapConfiguration(
        MapControl::ConfigurationManager **this,
        HSTRING a2,
        HSTRING a3,
        char a4,
        struct ILocaleMapConfiguration **a5)
{
  HSTRING v8; // r8
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  PCWSTR v12; // rax
  unsigned int v13; // ebx
  UINT32 length; // [rsp+20h] [rbp-51h] BYREF
  UINT32 v16; // [rsp+24h] [rbp-4Dh] BYREF
  char v17[16]; // [rsp+28h] [rbp-49h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-29h]
  __int64 v20[4]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v21[32]; // [rsp+78h] [rbp+7h] BYREF

  length = 0;
  v16 = 0;
  std::wstring::wstring((__int64)v18);
  std::wstring::wstring((__int64)v21);
  std::wstring::wstring((__int64)v20);
  StringRawBuffer = WindowsGetStringRawBuffer(v8, &length);
  std::wstring::assign(v18, StringRawBuffer, length);
  v10 = std::wstring::find(v18, 59, 0);
  if ( v10 == -1 )
  {
    std::wstring::operator=(v21);
  }
  else
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Check_offset(v18, 0);
    if ( v19 < v10 )
      v10 = v19;
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    std::wstring::_Assign<unsigned short>(v21, v11, v10);
  }
  if ( a4 )
  {
    std::wstring::assign(v20, L"CN");
  }
  else
  {
    v12 = WindowsGetStringRawBuffer(a3, &v16);
    std::wstring::assign(v20, v12, v16);
  }
  MapControl::ConfigurationManager::getConfiguration(this[4], v17, v20, (__int64)v21);
  v13 = Microsoft::WRL::Details::MakeAndInitialize<LocaleMapConfigurationAdapter,ILocaleMapConfiguration,Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> &>(
          a5,
          (__int64)v17);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v18);
  return v13;
}

```

## disassembly

```asm
0x18001ce90  mov     [rsp-8+arg_18], rbx
0x18001ce95  push    rbp
0x18001ce96  push    rsi
0x18001ce97  push    rdi
0x18001ce98  push    r14
0x18001ce9a  push    r15
0x18001ce9c  lea     rbp, [rsp-2Fh]
0x18001cea1  sub     rsp, 0A0h
0x18001cea8  mov     rax, cs:__security_cookie
0x18001ceaf  xor     rax, rsp
0x18001ceb2  mov     [rbp+4Fh+var_28], rax
0x18001ceb6  mov     dil, r9b
0x18001ceb9  mov     rsi, r8
0x18001cebc  mov     r8, rdx
0x18001cebf  mov     r14, rcx
0x18001cec2  mov     r15, [rbp+4Fh+arg_20]
0x18001cec6  mov     [rbp+4Fh+length], 0
0x18001cecd  mov     [rbp+4Fh+var_9C], 0
0x18001ced4  lea     rcx, [rbp+4Fh+var_88]
0x18001ced8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cedd  nop
0x18001cede  lea     rcx, [rbp+4Fh+var_48]
0x18001cee2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cee7  nop
0x18001cee8  lea     rcx, [rbp+4Fh+var_68]
0x18001ceec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cef1  nop
0x18001cef2  lea     rdx, [rbp+4Fh+length]; length
0x18001cef6  mov     rcx, r8; string
0x18001cef9  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ceff  mov     r8d, [rbp+4Fh+length]
0x18001cf03  mov     rdx, rax
0x18001cf06  lea     rcx, [rbp+4Fh+var_88]
0x18001cf0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18001cf0f  mov     edx, 3Bh ; ';'
0x18001cf14  xor     r8d, r8d
0x18001cf17  lea     rcx, [rbp+4Fh+var_88]
0x18001cf1b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18001cf20  mov     rbx, rax
0x18001cf23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cf27  jz      short loc_18001CF57
0x18001cf29  xor     edx, edx
0x18001cf2b  lea     rcx, [rbp+4Fh+var_88]
0x18001cf2f  call    ?_Check_offset@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<ushort>>::_Check_offset(unsigned __int64)
0x18001cf34  cmp     [rbp+4Fh+var_78], rbx
0x18001cf38  cmovb   rbx, [rbp+4Fh+var_78]
0x18001cf3d  lea     rcx, [rbp+4Fh+var_88]
0x18001cf41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cf46  mov     rdx, rax
0x18001cf49  mov     r8, rbx
0x18001cf4c  lea     rcx, [rbp+4Fh+var_48]
0x18001cf50  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001cf55  jmp     short loc_18001CF64
0x18001cf57  lea     rdx, [rbp+4Fh+var_88]
0x18001cf5b  lea     rcx, [rbp+4Fh+var_48]
0x18001cf5f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001cf64  test    dil, dil
0x18001cf67  jz      short loc_18001CF7B
0x18001cf69  lea     rdx, aCn; "CN"
0x18001cf70  lea     rcx, [rbp+4Fh+var_68]
0x18001cf74  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18001cf79  jmp     short loc_18001CF98
0x18001cf7b  lea     rdx, [rbp+4Fh+var_9C]; length
0x18001cf7f  mov     rcx, rsi; string
0x18001cf82  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cf88  mov     r8d, [rbp+4Fh+var_9C]
0x18001cf8c  mov     rdx, rax
0x18001cf8f  lea     rcx, [rbp+4Fh+var_68]
0x18001cf93  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18001cf98  lea     r9, [rbp+4Fh+var_48]
0x18001cf9c  lea     r8, [rbp+4Fh+var_68]
0x18001cfa0  lea     rdx, [rbp+4Fh+var_98]
0x18001cfa4  mov     rcx, [r14+20h]; this
0x18001cfa8  call    ?getConfiguration@ConfigurationManager@MapControl@@QEAA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapControl::ConfigurationManager::getConfiguration(std::wstring const &,std::wstring const &)
0x18001cfad  lea     rdx, [rbp+4Fh+var_98]
0x18001cfb1  mov     rcx, r15
0x18001cfb4  call    ??$MakeAndInitialize@VLocaleMapConfigurationAdapter@@UILocaleMapConfiguration@@AEAV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Details@WRL@Microsoft@@YAJPEAPEAUILocaleMapConfiguration@@AEAV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Z; Microsoft::WRL::Details::MakeAndInitialize<LocaleMapConfigurationAdapter,ILocaleMapConfiguration,Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> &>(ILocaleMapConfiguration * *,Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> &)
0x18001cfb9  mov     ebx, eax
0x18001cfbb  lea     rcx, [rbp+4Fh+var_98]
0x18001cfbf  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18001cfc4  nop
0x18001cfc5  lea     rcx, [rbp+4Fh+var_68]
0x18001cfc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cfce  nop
0x18001cfcf  lea     rcx, [rbp+4Fh+var_48]
0x18001cfd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cfd8  nop
0x18001cfd9  lea     rcx, [rbp+4Fh+var_88]
0x18001cfdd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cfe2  mov     eax, ebx
0x18001cfe4  mov     rcx, [rbp+4Fh+var_28]
0x18001cfe8  xor     rcx, rsp; StackCookie
0x18001cfeb  call    __security_check_cookie
0x18001cff0  mov     rbx, [rsp+0C0h+arg_18]
0x18001cff8  add     rsp, 0A0h
0x18001cfff  pop     r15
0x18001d001  pop     r14
0x18001d003  pop     rdi
0x18001d004  pop     rsi
0x18001d005  pop     rbp
0x18001d006  retn
```
