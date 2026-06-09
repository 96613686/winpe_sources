# Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001a510`
- end: `0x18001a6e9`
- name: `?GetAutopilotProfile@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b430`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x18001a510`
- `0x18001f030`
- `0x180026358`
- `0x1800275ac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a60f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a60f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a6ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a6ad`

## string_xrefs

- `0x18001a57d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a5c0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a564`: `AutopilotDDSZTDFile.json`

## pseudocode

```c
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
                                           (__int64)L"AutopilotDDSZTDFile.json",
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
    std::wstring::_Construct<1,unsigned short const *>(&v15, StringRawBuffer);
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
0x18001a510  push    rbp
0x18001a512  push    rbx
0x18001a513  push    rsi
0x18001a514  push    rdi
0x18001a515  lea     rbp, [rsp-3Fh]
0x18001a51a  sub     rsp, 98h
0x18001a521  mov     rax, cs:__security_cookie
0x18001a528  xor     rax, rsp
0x18001a52b  mov     [rbp+57h+var_28], rax
0x18001a52f  mov     rdi, rcx
0x18001a532  xorps   xmm0, xmm0
0x18001a535  movups  [rbp+57h+var_48], xmm0
0x18001a539  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001a541  movdqu  [rbp+57h+var_38], xmm1
0x18001a546  xor     esi, esi
0x18001a548  mov     word ptr [rbp+57h+var_48], si
0x18001a54c  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001a550  mov     qword ptr [rbp+57h+var_78], rsi
0x18001a554  mov     qword ptr [rbp+57h+var_78+8], 7
0x18001a55c  mov     word ptr [rbp+57h+var_88], si
0x18001a560  lea     rdx, [rbp+57h+var_48]
0x18001a564  lea     rcx, aAutopilotddszt; "AutopilotDDSZTDFile.json"
0x18001a56b  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001a570  mov     ebx, eax
0x18001a572  test    eax, eax
0x18001a574  jns     short loc_18001A593
0x18001a576  mov     rcx, [rbp+5Fh]; this
0x18001a57a  mov     r9d, eax; char *
0x18001a57d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a584  mov     edx, 275h; void *
0x18001a589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a58e  jmp     loc_18001A6BB
0x18001a593  mov     [rbp+57h+string], rsi
0x18001a597  lea     rcx, [rbp+57h+var_48]
0x18001a59b  cmp     qword ptr [rbp+57h+var_38+8], 7
0x18001a5a0  cmova   rcx, qword ptr [rbp+57h+var_48]
0x18001a5a5  lea     rdx, [rbp+57h+string]
0x18001a5a9  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001a5ae  mov     ebx, eax
0x18001a5b0  test    eax, eax
0x18001a5b2  jns     short loc_18001A609
0x18001a5b4  cmp     eax, 80070002h
0x18001a5b9  jz      short loc_18001A5F2
0x18001a5bb  mov     edx, 27Dh; void *
0x18001a5c0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a5c7  mov     r9d, eax; char *
0x18001a5ca  mov     rcx, [rbp+5Fh]; this
0x18001a5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5d3  nop
0x18001a5d4  mov     rcx, [rbp+57h+string]; string
0x18001a5d8  test    rcx, rcx
0x18001a5db  jz      loc_18001A6BB
0x18001a5e1  call    cs:__imp_WindowsDeleteString
0x18001a5e8  nop     dword ptr [rax+rax+00h]
0x18001a5ed  jmp     loc_18001A6BB
0x18001a5f2  lea     rcx, [rbp+57h+var_88]
0x18001a5f6  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001a5fb  cmova   rcx, [rbp+57h+var_88]
0x18001a600  mov     qword ptr [rbp+57h+var_78], rsi
0x18001a604  mov     [rcx], si
0x18001a607  jmp     short loc_18001A677
0x18001a609  xor     edx, edx; length
0x18001a60b  mov     rcx, [rbp+57h+string]; string
0x18001a60f  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a616  nop     dword ptr [rax+rax+00h]
0x18001a61b  xorps   xmm0, xmm0
0x18001a61e  movups  [rbp+57h+var_68], xmm0
0x18001a622  xorps   xmm1, xmm1
0x18001a625  movdqu  [rbp+57h+var_58], xmm1
0x18001a62a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a62e  inc     r8
0x18001a631  cmp     [rax+r8*2], si
0x18001a636  jnz     short loc_18001A62E
0x18001a638  mov     rdx, rax
0x18001a63b  lea     rcx, [rbp+57h+var_68]
0x18001a63f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a644  lea     rcx, [rbp+57h+var_88]
0x18001a648  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a64d  movups  xmm0, [rbp+57h+var_68]
0x18001a651  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001a655  movups  xmm1, [rbp+57h+var_58]
0x18001a659  movups  [rbp+57h+var_78], xmm1
0x18001a65d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001a665  movdqu  [rbp+57h+var_58], xmm0
0x18001a66a  mov     word ptr [rbp+57h+var_68], si
0x18001a66e  lea     rcx, [rbp+57h+var_68]
0x18001a672  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a677  lea     r8, [rbp+57h+var_88]
0x18001a67b  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001a680  cmova   r8, [rbp+57h+var_88]; unsigned __int16 *
0x18001a685  lea     rdx, aAutopilotprofi; "AutopilotProfile"
0x18001a68c  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x18001a68f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001a694  mov     ebx, eax
0x18001a696  test    eax, eax
0x18001a698  jns     short loc_18001A6A4
0x18001a69a  mov     edx, 288h
0x18001a69f  jmp     loc_18001A5C0
0x18001a6a4  mov     rcx, [rbp+57h+string]; string
0x18001a6a8  test    rcx, rcx
0x18001a6ab  jz      short loc_18001A6B9
0x18001a6ad  call    cs:__imp_WindowsDeleteString
0x18001a6b4  nop     dword ptr [rax+rax+00h]
0x18001a6b9  mov     ebx, esi
0x18001a6bb  lea     rcx, [rbp+57h+var_88]
0x18001a6bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6c4  nop
0x18001a6c5  lea     rcx, [rbp+57h+var_48]
0x18001a6c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a6ce  mov     eax, ebx
0x18001a6d0  mov     rcx, [rbp+57h+var_28]
0x18001a6d4  xor     rcx, rsp; StackCookie
0x18001a6d7  call    __security_check_cookie
0x18001a6dc  add     rsp, 98h
0x18001a6e3  pop     rdi
0x18001a6e4  pop     rsi
0x18001a6e5  pop     rbx
0x18001a6e6  pop     rbp
0x18001a6e7  retn
```
