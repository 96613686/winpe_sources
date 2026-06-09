# Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x18001a8b4`
- end: `0x18001ab25`
- name: `?GetCachedHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b430`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x18001a8b4`
- `0x18001b898`
- `0x18001f030`
- `0x180026358`
- `0x1800275ac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001aa39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001aa39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aa0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aa0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001aad7`

## string_xrefs

- `0x18001aaaf`: `CachedHardwareBlob`
- `0x18001a905`: `CachedHash.txt`
- `0x18001a93c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a99a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a9f1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(
        struct Windows::Data::Json::IJsonObject **a1)
{
  __m128i si128; // xmm6
  int StorageLocationName; // ebx
  __int128 *v4; // rcx
  int StateSeparationAwareExpandedFilePath; // eax
  const WCHAR *v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  unsigned __int16 **v9; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // r8
  const unsigned __int16 *v12; // r8
  HSTRING string; // [rsp+28h] [rbp-69h] BYREF
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-61h] BYREF
  __m128i v16; // [rsp+40h] [rbp-51h]
  __int128 v17; // [rsp+50h] [rbp-41h] BYREF
  __m128i v18; // [rsp+60h] [rbp-31h]
  __int128 v19; // [rsp+70h] [rbp-21h] BYREF
  __m128i v20; // [rsp+80h] [rbp-11h]
  __int128 v21; // [rsp+90h] [rbp-1h] BYREF
  __m128i v22; // [rsp+A0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v22 = si128;
  LOWORD(v21) = 0;
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v17, L"CachedHash.txt");
  StorageLocationName = Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(1, &v17, &v21);
  std::wstring::_Tidy_deallocate(&v17);
  if ( StorageLocationName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)StorageLocationName,
      (int)string);
    goto LABEL_28;
  }
  v19 = 0;
  v20 = si128;
  LOWORD(v19) = 0;
  *(_OWORD *)v15 = 0;
  v16.m128i_i64[0] = 0;
  v16.m128i_i64[1] = 7;
  LOWORD(v15[0]) = 0;
  v4 = &v21;
  if ( v22.m128i_i64[1] > 7uLL )
    v4 = (__int128 *)v21;
  StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                           (__int64)v4,
                                           &v19);
  StorageLocationName = StateSeparationAwareExpandedFilePath;
  if ( StateSeparationAwareExpandedFilePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
      (int)string);
LABEL_7:
    std::wstring::_Tidy_deallocate(v15);
    std::wstring::_Tidy_deallocate(&v19);
    goto LABEL_28;
  }
  string = 0;
  v6 = (const WCHAR *)&v19;
  if ( v20.m128i_i64[1] > 7uLL )
    v6 = (const WCHAR *)v19;
  v7 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(v6, &string);
  StorageLocationName = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v17 = 0;
    v18 = 0;
    v11 = -1;
    do
      ++v11;
    while ( StringRawBuffer[v11] );
    std::wstring::_Construct<1,unsigned short const *>(&v17, StringRawBuffer);
    std::wstring::_Tidy_deallocate(v15);
    *(_OWORD *)v15 = v17;
    v16 = v18;
    v18 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17) = 0;
    std::wstring::_Tidy_deallocate(&v17);
  }
  else
  {
    if ( v7 != -2147024894 )
    {
      v8 = 561;
      goto LABEL_13;
    }
    v9 = v15;
    if ( v16.m128i_i64[1] > 7uLL )
      v9 = (unsigned __int16 **)v15[0];
    v16.m128i_i64[0] = 0;
    *(_WORD *)v9 = 0;
  }
  v12 = (const unsigned __int16 *)v15;
  if ( v16.m128i_i64[1] > 7uLL )
    v12 = v15[0];
  v7 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a1, L"CachedHardwareBlob", v12);
  StorageLocationName = v7;
  if ( v7 < 0 )
  {
    v8 = 572;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_7;
  }
  if ( string )
    WindowsDeleteString(string);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(&v19);
  StorageLocationName = 0;
LABEL_28:
  std::wstring::_Tidy_deallocate(&v21);
  return (unsigned int)StorageLocationName;
}

```

## disassembly

```asm
0x18001a8b4  mov     rax, rsp
0x18001a8b7  push    rbp
0x18001a8b8  push    rbx
0x18001a8b9  push    rsi
0x18001a8ba  push    rdi
0x18001a8bb  lea     rbp, [rax-5Fh]
0x18001a8bf  sub     rsp, 0C8h
0x18001a8c6  movaps  xmmword ptr [rax-38h], xmm6
0x18001a8ca  mov     rax, cs:__security_cookie
0x18001a8d1  xor     rax, rsp
0x18001a8d4  mov     qword ptr [rbp+57h+var_38], rax
0x18001a8d8  mov     rdi, rcx
0x18001a8db  xorps   xmm0, xmm0
0x18001a8de  movups  [rbp+57h+var_58], xmm0
0x18001a8e2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001a8ea  movdqu  [rbp+57h+var_48], xmm6
0x18001a8ef  xor     esi, esi
0x18001a8f1  mov     word ptr [rbp+57h+var_58], si
0x18001a8f5  movups  [rbp+57h+var_98], xmm0
0x18001a8f9  xorps   xmm1, xmm1
0x18001a8fc  movdqu  [rbp+57h+var_88], xmm1
0x18001a901  lea     r8d, [rsi+0Eh]
0x18001a905  lea     rdx, aCachedhashTxt; "CachedHash.txt"
0x18001a90c  lea     rcx, [rbp+57h+var_98]
0x18001a910  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a915  nop
0x18001a916  lea     r8, [rbp+57h+var_58]
0x18001a91a  lea     rdx, [rbp+57h+var_98]
0x18001a91e  lea     ecx, [rsi+1]
0x18001a921  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x18001a926  mov     ebx, eax
0x18001a928  lea     rcx, [rbp+57h+var_98]
0x18001a92c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a931  test    ebx, ebx
0x18001a933  jns     short loc_18001A952
0x18001a935  mov     rcx, [rbp+5Fh]; this
0x18001a939  mov     r9d, ebx; char *
0x18001a93c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a943  mov     edx, 225h; void *
0x18001a948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a94d  jmp     loc_18001AAF9
0x18001a952  xorps   xmm0, xmm0
0x18001a955  movups  [rbp+57h+var_78], xmm0
0x18001a959  movdqu  [rbp+57h+var_68], xmm6
0x18001a95e  mov     word ptr [rbp+57h+var_78], si
0x18001a962  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x18001a966  mov     qword ptr [rbp+57h+var_A8], rsi
0x18001a96a  mov     qword ptr [rbp+57h+var_A8+8], 7
0x18001a972  mov     word ptr [rbp+57h+var_B8], si
0x18001a976  lea     rcx, [rbp+57h+var_58]
0x18001a97a  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18001a97f  cmova   rcx, qword ptr [rbp+57h+var_58]
0x18001a984  lea     rdx, [rbp+57h+var_78]
0x18001a988  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001a98d  mov     ebx, eax
0x18001a98f  test    eax, eax
0x18001a991  jns     short loc_18001A9C4
0x18001a993  mov     rcx, [rbp+5Fh]; this
0x18001a997  mov     r9d, eax; char *
0x18001a99a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a9a1  mov     edx, 229h; void *
0x18001a9a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9ab  nop
0x18001a9ac  lea     rcx, [rbp+57h+var_B8]
0x18001a9b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a9b5  nop
0x18001a9b6  lea     rcx, [rbp+57h+var_78]
0x18001a9ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a9bf  jmp     loc_18001AAF9
0x18001a9c4  mov     [rbp+57h+string], rsi
0x18001a9c8  lea     rcx, [rbp+57h+var_78]
0x18001a9cc  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18001a9d1  cmova   rcx, qword ptr [rbp+57h+var_78]
0x18001a9d6  lea     rdx, [rbp+57h+string]
0x18001a9da  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001a9df  mov     ebx, eax
0x18001a9e1  test    eax, eax
0x18001a9e3  jns     short loc_18001AA33
0x18001a9e5  cmp     eax, 80070002h
0x18001a9ea  jz      short loc_18001AA1C
0x18001a9ec  mov     edx, 231h; void *
0x18001a9f1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a9f8  mov     r9d, eax; char *
0x18001a9fb  mov     rcx, [rbp+5Fh]; this
0x18001a9ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa04  nop
0x18001aa05  mov     rcx, [rbp+57h+string]; string
0x18001aa09  test    rcx, rcx
0x18001aa0c  jz      short loc_18001A9AC
0x18001aa0e  call    cs:__imp_WindowsDeleteString
0x18001aa15  nop     dword ptr [rax+rax+00h]
0x18001aa1a  jmp     short loc_18001A9AC
0x18001aa1c  lea     rcx, [rbp+57h+var_B8]
0x18001aa20  cmp     qword ptr [rbp+57h+var_A8+8], 7
0x18001aa25  cmova   rcx, [rbp+57h+var_B8]
0x18001aa2a  mov     qword ptr [rbp+57h+var_A8], rsi
0x18001aa2e  mov     [rcx], si
0x18001aa31  jmp     short loc_18001AAA1
0x18001aa33  xor     edx, edx; length
0x18001aa35  mov     rcx, [rbp+57h+string]; string
0x18001aa39  call    cs:__imp_WindowsGetStringRawBuffer
0x18001aa40  nop     dword ptr [rax+rax+00h]
0x18001aa45  xorps   xmm0, xmm0
0x18001aa48  movups  [rbp+57h+var_98], xmm0
0x18001aa4c  xorps   xmm1, xmm1
0x18001aa4f  movdqu  [rbp+57h+var_88], xmm1
0x18001aa54  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001aa58  inc     r8
0x18001aa5b  cmp     [rax+r8*2], si
0x18001aa60  jnz     short loc_18001AA58
0x18001aa62  mov     rdx, rax
0x18001aa65  lea     rcx, [rbp+57h+var_98]
0x18001aa69  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001aa6e  lea     rcx, [rbp+57h+var_B8]
0x18001aa72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aa77  movups  xmm0, [rbp+57h+var_98]
0x18001aa7b  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x18001aa7f  movups  xmm1, [rbp+57h+var_88]
0x18001aa83  movups  [rbp+57h+var_A8], xmm1
0x18001aa87  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001aa8f  movdqu  [rbp+57h+var_88], xmm0
0x18001aa94  mov     word ptr [rbp+57h+var_98], si
0x18001aa98  lea     rcx, [rbp+57h+var_98]
0x18001aa9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aaa1  lea     r8, [rbp+57h+var_B8]
0x18001aaa5  cmp     qword ptr [rbp+57h+var_A8+8], 7
0x18001aaaa  cmova   r8, [rbp+57h+var_B8]; unsigned __int16 *
0x18001aaaf  lea     rdx, aCachedhardware; "CachedHardwareBlob"
0x18001aab6  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x18001aab9  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001aabe  mov     ebx, eax
0x18001aac0  test    eax, eax
0x18001aac2  jns     short loc_18001AACE
0x18001aac4  mov     edx, 23Ch
0x18001aac9  jmp     loc_18001A9F1
0x18001aace  mov     rcx, [rbp+57h+string]; string
0x18001aad2  test    rcx, rcx
0x18001aad5  jz      short loc_18001AAE4
0x18001aad7  call    cs:__imp_WindowsDeleteString
0x18001aade  nop     dword ptr [rax+rax+00h]
0x18001aae3  nop
0x18001aae4  lea     rcx, [rbp+57h+var_B8]
0x18001aae8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aaed  nop
0x18001aaee  lea     rcx, [rbp+57h+var_78]
0x18001aaf2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001aaf7  mov     ebx, esi
0x18001aaf9  lea     rcx, [rbp+57h+var_58]
0x18001aafd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ab02  mov     eax, ebx
0x18001ab04  mov     rcx, qword ptr [rbp+57h+var_38]
0x18001ab08  xor     rcx, rsp; StackCookie
0x18001ab0b  call    __security_check_cookie
0x18001ab10  movaps  xmm6, [rsp+0E0h+var_38+8]
0x18001ab18  add     rsp, 0C8h
0x18001ab1f  pop     rdi
0x18001ab20  pop     rsi
0x18001ab21  pop     rbx
0x18001ab22  pop     rbp
0x18001ab23  retn
```
