# Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180019ef0`
- end: `0x18001a0b6`
- name: `?GetAutopilotProfile@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ada0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x180019ef0`
- `0x18001e7b4`
- `0x18002553c`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a081`

## string_xrefs

- `0x180019f5d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019fa0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019f44`: `AutopilotDDSZTDFile.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(
        struct Windows::Data::Json::IJsonObject **a1)
{
  int StateSeparationAwareExpandedFilePath; // eax
  unsigned int v3; // ebx
  const WCHAR *v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  unsigned __int16 **v7; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // r8
  const unsigned __int16 *v10; // r8
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int16 *v13[2]; // [rsp+28h] [rbp-31h] BYREF
  __m128i v14; // [rsp+38h] [rbp-21h]
  __int128 v15; // [rsp+48h] [rbp-11h] BYREF
  __m128i v16; // [rsp+58h] [rbp-1h]
  __int128 v17; // [rsp+68h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17) = 0;
  *(_OWORD *)v13 = 0;
  v14.m128i_i64[0] = 0;
  v14.m128i_i64[1] = 7;
  LOWORD(v13[0]) = 0;
  StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                           L"AutopilotDDSZTDFile.json",
                                           &v17);
  v3 = StateSeparationAwareExpandedFilePath;
  if ( StateSeparationAwareExpandedFilePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
      (int)string);
    goto LABEL_23;
  }
  string = 0;
  v4 = (const WCHAR *)&v17;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = (const WCHAR *)v17;
  v5 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(v4, &string);
  v3 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v15 = 0;
    v16 = 0;
    v9 = -1;
    do
      ++v9;
    while ( StringRawBuffer[v9] );
    std::wstring::_Construct<1,unsigned short const *>(&v15, StringRawBuffer, v9);
    std::wstring::_Tidy_deallocate(v13);
    *(_OWORD *)v13 = v15;
    v14 = v16;
    v16 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    std::wstring::_Tidy_deallocate(&v15);
  }
  else
  {
    if ( v5 != -2147024894 )
    {
      v6 = 637;
      goto LABEL_8;
    }
    v7 = v13;
    if ( v14.m128i_i64[1] > 7uLL )
      v7 = (unsigned __int16 **)v13[0];
    v14.m128i_i64[0] = 0;
    *(_WORD *)v7 = 0;
  }
  v10 = (const unsigned __int16 *)v13;
  if ( v14.m128i_i64[1] > 7uLL )
    v10 = v13[0];
  v5 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a1, L"AutopilotProfile", v10);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 648;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_23;
  }
  if ( string )
    WindowsDeleteString(string);
  v3 = 0;
LABEL_23:
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(&v17);
  return v3;
}

```

## disassembly

```asm
0x180019ef0  push    rbp
0x180019ef2  push    rbx
0x180019ef3  push    rsi
0x180019ef4  push    rdi
0x180019ef5  lea     rbp, [rsp-3Fh]
0x180019efa  sub     rsp, 98h
0x180019f01  mov     rax, cs:__security_cookie
0x180019f08  xor     rax, rsp
0x180019f0b  mov     [rbp+57h+var_28], rax
0x180019f0f  mov     rdi, rcx
0x180019f12  xorps   xmm0, xmm0
0x180019f15  movups  [rbp+57h+var_48], xmm0
0x180019f19  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019f21  movdqu  [rbp+57h+var_38], xmm1
0x180019f26  xor     esi, esi
0x180019f28  mov     word ptr [rbp+57h+var_48], si
0x180019f2c  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x180019f30  mov     qword ptr [rbp+57h+var_78], rsi
0x180019f34  mov     qword ptr [rbp+57h+var_78+8], 7
0x180019f3c  mov     word ptr [rbp+57h+var_88], si
0x180019f40  lea     rdx, [rbp+57h+var_48]
0x180019f44  lea     rcx, aAutopilotddszt; "AutopilotDDSZTDFile.json"
0x180019f4b  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x180019f50  mov     ebx, eax
0x180019f52  test    eax, eax
0x180019f54  jns     short loc_180019F73
0x180019f56  mov     rcx, [rbp+5Fh]; this
0x180019f5a  mov     r9d, eax; char *
0x180019f5d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019f64  mov     edx, 275h; void *
0x180019f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f6e  jmp     loc_18001A089
0x180019f73  mov     [rbp+57h+string], rsi
0x180019f77  lea     rcx, [rbp+57h+var_48]
0x180019f7b  cmp     qword ptr [rbp+57h+var_38+8], 7
0x180019f80  cmova   rcx, qword ptr [rbp+57h+var_48]
0x180019f85  lea     rdx, [rbp+57h+string]
0x180019f89  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180019f8e  mov     ebx, eax
0x180019f90  test    eax, eax
0x180019f92  jns     short loc_180019FE3
0x180019f94  cmp     eax, 80070002h
0x180019f99  jz      short loc_180019FCC
0x180019f9b  mov     edx, 27Dh; void *
0x180019fa0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019fa7  mov     r9d, eax; char *
0x180019faa  mov     rcx, [rbp+5Fh]; this
0x180019fae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fb3  nop
0x180019fb4  mov     rcx, [rbp+57h+string]; string
0x180019fb8  test    rcx, rcx
0x180019fbb  jz      loc_18001A089
0x180019fc1  call    cs:__imp_WindowsDeleteString
0x180019fc7  jmp     loc_18001A089
0x180019fcc  lea     rcx, [rbp+57h+var_88]
0x180019fd0  cmp     qword ptr [rbp+57h+var_78+8], 7
0x180019fd5  cmova   rcx, [rbp+57h+var_88]
0x180019fda  mov     qword ptr [rbp+57h+var_78], rsi
0x180019fde  mov     [rcx], si
0x180019fe1  jmp     short loc_18001A04B
0x180019fe3  xor     edx, edx; length
0x180019fe5  mov     rcx, [rbp+57h+string]; string
0x180019fe9  call    cs:__imp_WindowsGetStringRawBuffer
0x180019fef  xorps   xmm0, xmm0
0x180019ff2  movups  [rbp+57h+var_68], xmm0
0x180019ff6  xorps   xmm1, xmm1
0x180019ff9  movdqu  [rbp+57h+var_58], xmm1
0x180019ffe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a002  inc     r8
0x18001a005  cmp     [rax+r8*2], si
0x18001a00a  jnz     short loc_18001A002
0x18001a00c  mov     rdx, rax
0x18001a00f  lea     rcx, [rbp+57h+var_68]
0x18001a013  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a018  lea     rcx, [rbp+57h+var_88]
0x18001a01c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a021  movups  xmm0, [rbp+57h+var_68]
0x18001a025  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001a029  movups  xmm1, [rbp+57h+var_58]
0x18001a02d  movups  [rbp+57h+var_78], xmm1
0x18001a031  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001a039  movdqu  [rbp+57h+var_58], xmm0
0x18001a03e  mov     word ptr [rbp+57h+var_68], si
0x18001a042  lea     rcx, [rbp+57h+var_68]
0x18001a046  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a04b  lea     r8, [rbp+57h+var_88]
0x18001a04f  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001a054  cmova   r8, [rbp+57h+var_88]; unsigned __int16 *
0x18001a059  lea     rdx, aAutopilotprofi; "AutopilotProfile"
0x18001a060  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x18001a063  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001a068  mov     ebx, eax
0x18001a06a  test    eax, eax
0x18001a06c  jns     short loc_18001A078
0x18001a06e  mov     edx, 288h
0x18001a073  jmp     loc_180019FA0
0x18001a078  mov     rcx, [rbp+57h+string]; string
0x18001a07c  test    rcx, rcx
0x18001a07f  jz      short loc_18001A087
0x18001a081  call    cs:__imp_WindowsDeleteString
0x18001a087  mov     ebx, esi
0x18001a089  lea     rcx, [rbp+57h+var_88]
0x18001a08d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a092  nop
0x18001a093  lea     rcx, [rbp+57h+var_48]
0x18001a097  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a09c  mov     eax, ebx
0x18001a09e  mov     rcx, [rbp+57h+var_28]
0x18001a0a2  xor     rcx, rsp; StackCookie
0x18001a0a5  call    __security_check_cookie
0x18001a0aa  add     rsp, 98h
0x18001a0b1  pop     rdi
0x18001a0b2  pop     rsi
0x18001a0b3  pop     rbx
0x18001a0b4  pop     rbp
0x18001a0b5  retn
```
