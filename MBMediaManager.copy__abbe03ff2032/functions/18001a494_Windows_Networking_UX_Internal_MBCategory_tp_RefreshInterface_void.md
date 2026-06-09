# Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(void)

- ea: `0x18001a494`
- end: `0x18001a6e0`
- name: `?tp_RefreshInterface@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ`
- size: `588`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009f60`
- `0x18000c890`
- `0x18000da00`
- `0x18000ead4`
- `0x180019e2c`
- `0x18001a864`

## callees

- `0x180005fc0`
- `0x180009150`
- `0x18000ad20`
- `0x18000c6ac`
- `0x18000c724`
- `0x18000cc50`
- `0x18000ccb0`
- `0x1800116e0`
- `0x1800148b8`
- `0x1800164ec`
- `0x18001a494`
- `0x18001c268`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a56d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a56d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5dd`

## string_xrefs

- `0x18001a65a`: `interfaceGuid=%hs, Connectivity=%d, BlockedReason=%d,ActionRequiredReason=%d, fAutoConnect=%hs, IsRoaming=%hs, Name=%ls, BrandingIconPath=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(HSTRING *this)
{
  bool v2; // dl
  bool v3; // di
  bool v4; // dl
  bool v5; // dl
  HSTRING *v6; // rbx
  const wchar_t *StringRawBuffer; // r13
  const wchar_t *v8; // r12
  const char *v9; // r15
  const char *v10; // r14
  int v11; // ebx
  int v12; // edi
  int v13; // esi
  __int64 v14; // rax
  unsigned __int16 *v15; // [rsp+60h] [rbp-79h] BYREF
  __int64 v16; // [rsp+68h] [rbp-71h]
  __int64 v17; // [rsp+70h] [rbp-69h]
  LPVOID pv; // [rsp+78h] [rbp-61h] BYREF
  __int64 v19; // [rsp+80h] [rbp-59h]
  __int64 v20; // [rsp+88h] [rbp-51h]
  Windows::Networking::UX::Internal::MBCategory *v21; // [rsp+90h] [rbp-49h]
  char v22[40]; // [rsp+98h] [rbp-41h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-19h] BYREF
  _BYTE v24[19]; // [rsp+D0h] [rbp-9h]

  v21 = (Windows::Networking::UX::Internal::MBCategory *)this;
  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface", 0xC1Fu, "Enter");
  v3 = Windows::Networking::UX::Internal::MBCategory::_CalculateConnectivity(
         (Windows::Networking::UX::Internal::MBCategory *)this,
         v2);
  pv = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    &pv,
    &sourceString,
    -1);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v19 = -1;
  v20 = -1;
  if ( (int)Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(
              (Windows::Networking::UX::Internal::MBCategory *)this,
              v4,
              (unsigned __int16 **)&pv) >= 0 )
  {
    Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(this + 5);
    v3 = 1;
  }
  v15 = 0;
  v16 = 0;
  v17 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    &v15,
    &sourceString,
    -1);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  v16 = -1;
  v17 = -1;
  if ( (int)Windows::Networking::UX::Internal::MBCategory::_CalculateBrandingIconPath(
              (Windows::Networking::UX::Internal::MBCategory *)this,
              v5,
              &v15) < 0
    || (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&v15) )
  {
    v6 = this + 8;
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(this + 8), &sourceString, 0);
    if ( !v3 )
      goto LABEL_16;
  }
  else
  {
    v6 = this + 8;
    Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(this + 8);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*v6, 0);
  v8 = WindowsGetStringRawBuffer(this[5], 0);
  v9 = "true";
  v10 = "true";
  if ( !*((_BYTE *)this + 88) )
    v10 = "false";
  if ( !*((_BYTE *)this + 90) )
    v9 = "false";
  v11 = *((_DWORD *)this + 20);
  v12 = *((_DWORD *)this + 19);
  v13 = *((_DWORD *)this + 18);
  v14 = MbLoggingHelperGuidToString(v22);
  v23 = *(_OWORD *)v14;
  *(_OWORD *)v24 = *(_OWORD *)(v14 + 16);
  *(_DWORD *)&v24[15] = *(_DWORD *)(v14 + 31);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface",
    0xC4Du,
    "interfaceGuid=%hs, Connectivity=%d, BlockedReason=%d,ActionRequiredReason=%d, fAutoConnect=%hs, IsRoaming=%hs, Name="
    "%ls, BrandingIconPath=%ls",
    (const char *)&v23,
    v13,
    v12,
    v11,
    v9,
    v10,
    v8,
    StringRawBuffer);
  Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange(v21);
LABEL_16:
  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface", 0xC51u, "Exit");
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  v16 = 0;
  v17 = 0;
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18001a494  push    rbp
0x18001a496  push    rbx
0x18001a497  push    rsi
0x18001a498  push    rdi
0x18001a499  push    r12
0x18001a49b  push    r13
0x18001a49d  push    r14
0x18001a49f  push    r15
0x18001a4a1  lea     rbp, [rsp-1Fh]
0x18001a4a6  sub     rsp, 0F8h
0x18001a4ad  mov     rax, cs:__security_cookie
0x18001a4b4  xor     rax, rsp
0x18001a4b7  mov     [rbp+57h+var_48], rax
0x18001a4bb  mov     rsi, rcx
0x18001a4be  mov     [rbp+57h+var_A0], rcx
0x18001a4c2  lea     r8, aEnter; "Enter"
0x18001a4c9  mov     edx, 0C1Fh; unsigned int
0x18001a4ce  lea     rcx, aWindowsNetwork_35; "Windows::Networking::UX::Internal::MBCa"...
0x18001a4d5  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18001a4da  mov     rcx, rsi; this
0x18001a4dd  call    ?_CalculateConnectivity@MBCategory@Internal@UX@Networking@Windows@@AEAA_N_N@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateConnectivity(bool)
0x18001a4e2  mov     dil, al
0x18001a4e5  xor     r14d, r14d
0x18001a4e8  mov     [rbp+57h+pv], r14
0x18001a4ec  mov     [rbp+57h+var_B0], r14
0x18001a4f0  mov     [rbp+57h+var_A8], r14
0x18001a4f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a4f8  mov     r8, rbx
0x18001a4fb  lea     r15, sourceString
0x18001a502  mov     rdx, r15
0x18001a505  lea     rcx, [rbp+57h+pv]
0x18001a509  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001a50e  mov     rcx, [rbp+57h+pv]; pv
0x18001a512  test    rcx, rcx
0x18001a515  jz      short loc_18001A521
0x18001a517  call    cs:__imp_CoTaskMemFree
0x18001a51d  mov     [rbp+57h+pv], r14
0x18001a521  mov     [rbp+57h+var_B0], rbx
0x18001a525  mov     [rbp+57h+var_A8], rbx
0x18001a529  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x18001a52d  mov     rcx, rsi; this
0x18001a530  call    ?_CalculateCategoryName@MBCategory@Internal@UX@Networking@Windows@@AEAAJ_NPEAPEAG@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(bool,ushort * *)
0x18001a535  test    eax, eax
0x18001a537  js      short loc_18001A549
0x18001a539  lea     rcx, [rsi+28h]; string
0x18001a53d  lea     rdx, [rbp+57h+pv]
0x18001a541  call    ??$Set@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18001a546  mov     dil, 1
0x18001a549  mov     [rbp+57h+var_D0], r14
0x18001a54d  mov     [rbp+57h+var_C8], r14
0x18001a551  mov     [rbp+57h+var_C0], r14
0x18001a555  mov     r8, rbx
0x18001a558  mov     rdx, r15
0x18001a55b  lea     rcx, [rbp+57h+var_D0]
0x18001a55f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001a564  mov     rcx, [rbp+57h+var_D0]; pv
0x18001a568  test    rcx, rcx
0x18001a56b  jz      short loc_18001A577
0x18001a56d  call    cs:__imp_CoTaskMemFree
0x18001a573  mov     [rbp+57h+var_D0], r14
0x18001a577  mov     [rbp+57h+var_C8], rbx
0x18001a57b  mov     [rbp+57h+var_C0], rbx
0x18001a57f  lea     r8, [rbp+57h+var_D0]; unsigned __int16 **
0x18001a583  mov     rcx, rsi; this
0x18001a586  call    ?_CalculateBrandingIconPath@MBCategory@Internal@UX@Networking@Windows@@AEAAJ_NPEAPEAG@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateBrandingIconPath(bool,ushort * *)
0x18001a58b  test    eax, eax
0x18001a58d  js      short loc_18001A5AE
0x18001a58f  lea     rcx, [rbp+57h+var_D0]
0x18001a593  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x18001a598  test    al, al
0x18001a59a  jnz     short loc_18001A5AE
0x18001a59c  lea     rbx, [rsi+40h]
0x18001a5a0  lea     rdx, [rbp+57h+var_D0]
0x18001a5a4  mov     rcx, rbx; string
0x18001a5a7  call    ??$Set@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18001a5ac  jmp     short loc_18001A5C9
0x18001a5ae  lea     rbx, [rsi+40h]
0x18001a5b2  xor     r8d, r8d; unsigned int
0x18001a5b5  mov     rdx, r15; unsigned __int16 *
0x18001a5b8  mov     rcx, rbx; this
0x18001a5bb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001a5c0  test    dil, dil
0x18001a5c3  jz      loc_18001A67E
0x18001a5c9  xor     edx, edx; length
0x18001a5cb  mov     rcx, [rbx]; string
0x18001a5ce  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a5d4  mov     r13, rax
0x18001a5d7  xor     edx, edx; length
0x18001a5d9  mov     rcx, [rsi+28h]; string
0x18001a5dd  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a5e3  mov     r12, rax
0x18001a5e6  lea     rax, aFalse; "false"
0x18001a5ed  lea     r15, aTrue; "true"
0x18001a5f4  mov     r14, r15
0x18001a5f7  cmp     byte ptr [rsi+58h], 0
0x18001a5fb  cmovz   r14, rax
0x18001a5ff  cmp     byte ptr [rsi+5Ah], 0
0x18001a603  cmovz   r15, rax
0x18001a607  mov     ebx, [rsi+50h]
0x18001a60a  mov     edi, [rsi+4Ch]
0x18001a60d  mov     esi, [rsi+48h]
0x18001a610  mov     rdx, [rbp+57h+var_A0]
0x18001a614  add     rdx, 18h
0x18001a618  lea     rcx, [rbp+57h+var_98]; char *
0x18001a61c  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x18001a621  movups  xmm0, xmmword ptr [rax]
0x18001a624  movups  [rbp+57h+var_70], xmm0
0x18001a628  movups  xmm1, xmmword ptr [rax+10h]
0x18001a62c  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18001a630  mov     eax, [rax+1Fh]
0x18001a633  mov     dword ptr [rbp+57h+var_60+0Fh], eax
0x18001a636  mov     [rsp+130h+var_E0], r13
0x18001a63b  mov     [rsp+130h+var_E8], r12
0x18001a640  mov     [rsp+130h+var_F0], r14
0x18001a645  mov     [rsp+130h+var_F8], r15
0x18001a64a  mov     [rsp+130h+var_100], ebx
0x18001a64e  mov     [rsp+130h+var_108], edi
0x18001a652  mov     [rsp+130h+var_110], esi
0x18001a656  lea     r9, [rbp+57h+var_70]
0x18001a65a  lea     r8, aInterfaceguidH_0; "interfaceGuid=%hs, Connectivity=%d, Blo"...
0x18001a661  mov     edx, 0C4Dh; unsigned int
0x18001a666  lea     rcx, aWindowsNetwork_35; "Windows::Networking::UX::Internal::MBCa"...
0x18001a66d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001a672  mov     rcx, [rbp+57h+var_A0]; this
0x18001a676  call    ?_SubmitThreadpoolInvokeCategoryChange@MBCategory@Internal@UX@Networking@Windows@@AEAAJXZ; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvokeCategoryChange(void)
0x18001a67b  xor     r14d, r14d
0x18001a67e  lea     r8, aExit; "Exit"
0x18001a685  mov     edx, 0C51h; unsigned int
0x18001a68a  lea     rcx, aWindowsNetwork_35; "Windows::Networking::UX::Internal::MBCa"...
0x18001a691  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18001a696  mov     rcx, [rbp+57h+var_D0]; pv
0x18001a69a  test    rcx, rcx
0x18001a69d  jz      short loc_18001A6A9
0x18001a69f  call    cs:__imp_CoTaskMemFree
0x18001a6a5  mov     [rbp+57h+var_D0], r14
0x18001a6a9  mov     [rbp+57h+var_C8], r14
0x18001a6ad  mov     [rbp+57h+var_C0], r14
0x18001a6b1  mov     rcx, [rbp+57h+pv]; pv
0x18001a6b5  test    rcx, rcx
0x18001a6b8  jz      short loc_18001A6C0
0x18001a6ba  call    cs:__imp_CoTaskMemFree
0x18001a6c0  mov     rcx, [rbp+57h+var_48]
0x18001a6c4  xor     rcx, rsp; StackCookie
0x18001a6c7  call    __security_check_cookie
0x18001a6cc  add     rsp, 0F8h
0x18001a6d3  pop     r15
0x18001a6d5  pop     r14
0x18001a6d7  pop     r13
0x18001a6d9  pop     r12
0x18001a6db  pop     rdi
0x18001a6dc  pop     rsi
0x18001a6dd  pop     rbx
0x18001a6de  pop     rbp
0x18001a6df  retn
```
