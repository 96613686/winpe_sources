# Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x18001a280`
- end: `0x18001a4de`
- name: `?GetCachedHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z`
- size: `606`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ada0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x18001a280`
- `0x18001b1f4`
- `0x18001e7b4`
- `0x18002553c`
- `0x18002661c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a3ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a3ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a3da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a3da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a497`

## string_xrefs

- `0x18001a46f`: `CachedHardwareBlob`
- `0x18001a2d1`: `CachedHash.txt`
- `0x18001a308`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a366`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a3bd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
  std::wstring::_Construct<1,unsigned short const *>(&v17, L"CachedHash.txt", 14);
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
                                           v4,
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
    std::wstring::_Construct<1,unsigned short const *>(&v17, StringRawBuffer, v11);
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
0x18001a280  mov     rax, rsp
0x18001a283  push    rbp
0x18001a284  push    rbx
0x18001a285  push    rsi
0x18001a286  push    rdi
0x18001a287  lea     rbp, [rax-5Fh]
0x18001a28b  sub     rsp, 0C8h
0x18001a292  movaps  xmmword ptr [rax-38h], xmm6
0x18001a296  mov     rax, cs:__security_cookie
0x18001a29d  xor     rax, rsp
0x18001a2a0  mov     qword ptr [rbp+57h+var_38], rax
0x18001a2a4  mov     rdi, rcx
0x18001a2a7  xorps   xmm0, xmm0
0x18001a2aa  movups  [rbp+57h+var_58], xmm0
0x18001a2ae  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001a2b6  movdqu  [rbp+57h+var_48], xmm6
0x18001a2bb  xor     esi, esi
0x18001a2bd  mov     word ptr [rbp+57h+var_58], si
0x18001a2c1  movups  [rbp+57h+var_98], xmm0
0x18001a2c5  xorps   xmm1, xmm1
0x18001a2c8  movdqu  [rbp+57h+var_88], xmm1
0x18001a2cd  lea     r8d, [rsi+0Eh]
0x18001a2d1  lea     rdx, aCachedhashTxt; "CachedHash.txt"
0x18001a2d8  lea     rcx, [rbp+57h+var_98]
0x18001a2dc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a2e1  nop
0x18001a2e2  lea     r8, [rbp+57h+var_58]
0x18001a2e6  lea     rdx, [rbp+57h+var_98]
0x18001a2ea  lea     ecx, [rsi+1]
0x18001a2ed  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x18001a2f2  mov     ebx, eax
0x18001a2f4  lea     rcx, [rbp+57h+var_98]
0x18001a2f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a2fd  test    ebx, ebx
0x18001a2ff  jns     short loc_18001A31E
0x18001a301  mov     rcx, [rbp+5Fh]; this
0x18001a305  mov     r9d, ebx; char *
0x18001a308  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a30f  mov     edx, 225h; void *
0x18001a314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a319  jmp     loc_18001A4B3
0x18001a31e  xorps   xmm0, xmm0
0x18001a321  movups  [rbp+57h+var_78], xmm0
0x18001a325  movdqu  [rbp+57h+var_68], xmm6
0x18001a32a  mov     word ptr [rbp+57h+var_78], si
0x18001a32e  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x18001a332  mov     qword ptr [rbp+57h+var_A8], rsi
0x18001a336  mov     qword ptr [rbp+57h+var_A8+8], 7
0x18001a33e  mov     word ptr [rbp+57h+var_B8], si
0x18001a342  lea     rcx, [rbp+57h+var_58]
0x18001a346  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18001a34b  cmova   rcx, qword ptr [rbp+57h+var_58]
0x18001a350  lea     rdx, [rbp+57h+var_78]
0x18001a354  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18001a359  mov     ebx, eax
0x18001a35b  test    eax, eax
0x18001a35d  jns     short loc_18001A390
0x18001a35f  mov     rcx, [rbp+5Fh]; this
0x18001a363  mov     r9d, eax; char *
0x18001a366  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a36d  mov     edx, 229h; void *
0x18001a372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a377  nop
0x18001a378  lea     rcx, [rbp+57h+var_B8]
0x18001a37c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a381  nop
0x18001a382  lea     rcx, [rbp+57h+var_78]
0x18001a386  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a38b  jmp     loc_18001A4B3
0x18001a390  mov     [rbp+57h+string], rsi
0x18001a394  lea     rcx, [rbp+57h+var_78]
0x18001a398  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18001a39d  cmova   rcx, qword ptr [rbp+57h+var_78]
0x18001a3a2  lea     rdx, [rbp+57h+string]
0x18001a3a6  call    ?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18001a3ab  mov     ebx, eax
0x18001a3ad  test    eax, eax
0x18001a3af  jns     short loc_18001A3F9
0x18001a3b1  cmp     eax, 80070002h
0x18001a3b6  jz      short loc_18001A3E2
0x18001a3b8  mov     edx, 231h; void *
0x18001a3bd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a3c4  mov     r9d, eax; char *
0x18001a3c7  mov     rcx, [rbp+5Fh]; this
0x18001a3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3d0  nop
0x18001a3d1  mov     rcx, [rbp+57h+string]; string
0x18001a3d5  test    rcx, rcx
0x18001a3d8  jz      short loc_18001A378
0x18001a3da  call    cs:__imp_WindowsDeleteString
0x18001a3e0  jmp     short loc_18001A378
0x18001a3e2  lea     rcx, [rbp+57h+var_B8]
0x18001a3e6  cmp     qword ptr [rbp+57h+var_A8+8], 7
0x18001a3eb  cmova   rcx, [rbp+57h+var_B8]
0x18001a3f0  mov     qword ptr [rbp+57h+var_A8], rsi
0x18001a3f4  mov     [rcx], si
0x18001a3f7  jmp     short loc_18001A461
0x18001a3f9  xor     edx, edx; length
0x18001a3fb  mov     rcx, [rbp+57h+string]; string
0x18001a3ff  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a405  xorps   xmm0, xmm0
0x18001a408  movups  [rbp+57h+var_98], xmm0
0x18001a40c  xorps   xmm1, xmm1
0x18001a40f  movdqu  [rbp+57h+var_88], xmm1
0x18001a414  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a418  inc     r8
0x18001a41b  cmp     [rax+r8*2], si
0x18001a420  jnz     short loc_18001A418
0x18001a422  mov     rdx, rax
0x18001a425  lea     rcx, [rbp+57h+var_98]
0x18001a429  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a42e  lea     rcx, [rbp+57h+var_B8]
0x18001a432  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a437  movups  xmm0, [rbp+57h+var_98]
0x18001a43b  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x18001a43f  movups  xmm1, [rbp+57h+var_88]
0x18001a443  movups  [rbp+57h+var_A8], xmm1
0x18001a447  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001a44f  movdqu  [rbp+57h+var_88], xmm0
0x18001a454  mov     word ptr [rbp+57h+var_98], si
0x18001a458  lea     rcx, [rbp+57h+var_98]
0x18001a45c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a461  lea     r8, [rbp+57h+var_B8]
0x18001a465  cmp     qword ptr [rbp+57h+var_A8+8], 7
0x18001a46a  cmova   r8, [rbp+57h+var_B8]; unsigned __int16 *
0x18001a46f  lea     rdx, aCachedhardware; "CachedHardwareBlob"
0x18001a476  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x18001a479  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001a47e  mov     ebx, eax
0x18001a480  test    eax, eax
0x18001a482  jns     short loc_18001A48E
0x18001a484  mov     edx, 23Ch
0x18001a489  jmp     loc_18001A3BD
0x18001a48e  mov     rcx, [rbp+57h+string]; string
0x18001a492  test    rcx, rcx
0x18001a495  jz      short loc_18001A49E
0x18001a497  call    cs:__imp_WindowsDeleteString
0x18001a49d  nop
0x18001a49e  lea     rcx, [rbp+57h+var_B8]
0x18001a4a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a4a7  nop
0x18001a4a8  lea     rcx, [rbp+57h+var_78]
0x18001a4ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a4b1  mov     ebx, esi
0x18001a4b3  lea     rcx, [rbp+57h+var_58]
0x18001a4b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a4bc  mov     eax, ebx
0x18001a4be  mov     rcx, qword ptr [rbp+57h+var_38]
0x18001a4c2  xor     rcx, rsp; StackCookie
0x18001a4c5  call    __security_check_cookie
0x18001a4ca  movaps  xmm6, [rsp+0E0h+var_38+8]
0x18001a4d2  add     rsp, 0C8h
0x18001a4d9  pop     rdi
0x18001a4da  pop     rsi
0x18001a4db  pop     rbx
0x18001a4dc  pop     rbp
0x18001a4dd  retn
```
