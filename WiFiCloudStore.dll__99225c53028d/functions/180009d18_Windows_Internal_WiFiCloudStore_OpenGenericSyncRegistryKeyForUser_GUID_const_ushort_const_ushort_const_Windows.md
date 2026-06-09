# Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(_GUID const &,ushort const *,ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration)

- ea: `0x180009d18`
- end: `0x180009fb0`
- name: `?OpenGenericSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG1W4ProfileGeneration@123@@Z`
- size: `664`
- prototype: `PHKEY __fastcall(PHKEY phkResult, GUID *rguid, __int64, __int64, unsigned int)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aebc`
- `0x18000b528`
- `0x18000bca8`
- `0x1800111a8`
- `0x18003cc9c`
- `0x18003cccc`

## callees

- `0x180006a44`
- `0x180009d18`
- `0x180009fb8`
- `0x18000b3cc`
- `0x180025308`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180031ce4`
- `0x18003caa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009d83`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009d83`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009ee4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009ee4`

## string_xrefs

- `0x180009f58`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`
- `0x180009f87`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
PHKEY __fastcall Windows::Internal::WiFiCloudStore::OpenGenericSyncRegistryKeyForUser(
        PHKEY phkResult,
        GUID *rguid,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  void *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r8
  void *v12; // rax
  void *v13; // rax
  __int64 v14; // r8
  void *v15; // rax
  void *v16; // rax
  __int64 v17; // r8
  void *v18; // rax
  void *v19; // r15
  __int64 v20; // r8
  const wchar_t *v21; // rdx
  __int128 *v22; // rdx
  const WCHAR *v23; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h]
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+98h] [rbp-68h]
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(lpSubKey);
  memset_0(sz, 0, 0x4Eu);
  if ( !StringFromGUID2(rguid, sz, 39) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)0x8007007ALL,
      dwOptions);
  v9 = (void *)std::wstring::_Append<unsigned short>(lpSubKey);
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a3 + 2 * v11) );
  v12 = (void *)std::wstring::_Append<unsigned short>(v9);
  v13 = (void *)std::wstring::_Append<unsigned short>(v12);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a4 + 2 * v14) );
  v15 = (void *)std::wstring::_Append<unsigned short>(v13);
  v16 = (void *)std::wstring::_Append<unsigned short>(v15);
  v17 = -1;
  do
    ++v17;
  while ( sz[v17] );
  v18 = (void *)std::wstring::_Append<unsigned short>(v16);
  v19 = (void *)std::wstring::_Append<unsigned short>(v18);
  if ( a5 == 0x80000000 )
  {
    v20 = 10;
    v21 = L"Irrelevant";
LABEL_10:
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v28, v21, v20);
    goto LABEL_11;
  }
  if ( a5 == 0x7FFFFFFF )
  {
    v20 = 3;
    v21 = L"All";
    goto LABEL_10;
  }
  std::_Integral_to_string<unsigned short,int>(&v28, a5);
LABEL_11:
  v22 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    v22 = (__int128 *)v28;
  do
    ++v10;
  while ( *((_WORD *)v22 + v10) );
  std::wstring::_Append<unsigned short>(v19);
  if ( *((_QWORD *)&v29 + 1) > 7u )
    std::_Deallocate<16>(v28, 2LL * *((_QWORD *)&v29 + 1) + 2);
  *phkResult = 0;
  v23 = (const WCHAR *)lpSubKey;
  if ( v31 > 7 )
    v23 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v23, 0, 0, 0, 0xFu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)Key,
      dwOptionsa);
  if ( v31 > 7 )
    std::_Deallocate<16>(lpSubKey[0], 2 * v31 + 2);
  return phkResult;
}

```

## disassembly

```asm
0x180009d18  push    rbp
0x180009d1a  push    rbx
0x180009d1b  push    rsi
0x180009d1c  push    rdi
0x180009d1d  push    r12
0x180009d1f  push    r13
0x180009d21  push    r14
0x180009d23  push    r15
0x180009d25  lea     rbp, [rsp-8]
0x180009d2a  sub     rsp, 108h
0x180009d31  mov     rax, cs:__security_cookie
0x180009d38  xor     rax, rsp
0x180009d3b  mov     [rbp+40h+var_50], rax
0x180009d3f  mov     r12, r9
0x180009d42  mov     r15, r8
0x180009d45  mov     rbx, rdx
0x180009d48  mov     r14, rcx
0x180009d4b  mov     [rsp+140h+var_E8], rcx
0x180009d50  mov     esi, [rbp+40h+arg_20]
0x180009d53  xor     r13d, r13d
0x180009d56  mov     [rsp+140h+var_F0], r13d
0x180009d5b  lea     rcx, [rbp+40h+lpSubKey]; Src
0x180009d5f  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x180009d64  nop
0x180009d65  xor     edx, edx; Val
0x180009d67  lea     r8d, [r13+4Eh]; Size
0x180009d6b  lea     rcx, [rbp+40h+sz]; void *
0x180009d6f  call    memset_0
0x180009d74  mov     rdi, [rbp+48h]
0x180009d78  lea     r8d, [r13+27h]; cchMax
0x180009d7c  lea     rdx, [rbp+40h+sz]; lpsz
0x180009d80  mov     rcx, rbx; rguid
0x180009d83  call    cs:__imp_StringFromGUID2
0x180009d89  test    eax, eax
0x180009d8b  jz      loc_180009F52
0x180009d91  lea     ebx, [r13+1]
0x180009d95  mov     r8d, ebx
0x180009d98  lea     rdx, asc_180043BAC; "\\"
0x180009d9f  lea     rcx, [rbp+40h+lpSubKey]; Src
0x180009da3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009da8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009dac  mov     r8, rdi
0x180009daf  inc     r8
0x180009db2  cmp     [r15+r8*2], r13w
0x180009db7  jnz     short loc_180009DAF
0x180009db9  mov     rdx, r15
0x180009dbc  mov     rcx, rax; Src
0x180009dbf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009dc4  mov     r8, rbx
0x180009dc7  lea     r15, asc_180043BAC; "\\"
0x180009dce  mov     rdx, r15
0x180009dd1  mov     rcx, rax; Src
0x180009dd4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009dd9  mov     r8, rdi
0x180009ddc  inc     r8
0x180009ddf  cmp     [r12+r8*2], r13w
0x180009de4  jnz     short loc_180009DDC
0x180009de6  mov     rdx, r12
0x180009de9  mov     rcx, rax; Src
0x180009dec  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009df1  mov     r8, rbx
0x180009df4  mov     rdx, r15
0x180009df7  mov     rcx, rax; Src
0x180009dfa  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009dff  lea     rcx, [rbp+40h+sz]
0x180009e03  mov     r8, rdi
0x180009e06  inc     r8
0x180009e09  cmp     [rcx+r8*2], r13w
0x180009e0e  jnz     short loc_180009E06
0x180009e10  lea     rdx, [rbp+40h+sz]
0x180009e14  mov     rcx, rax; Src
0x180009e17  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009e1c  mov     r8, rbx
0x180009e1f  mov     rdx, r15
0x180009e22  mov     rcx, rax; Src
0x180009e25  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009e2a  mov     r15, rax
0x180009e2d  lea     rcx, [rsp+140h+var_E0]
0x180009e32  cmp     esi, 80000000h
0x180009e38  jnz     loc_180009F27
0x180009e3e  mov     r8d, 0Ah
0x180009e44  lea     rdx, aIrrelevant; "Irrelevant"
0x180009e4b  xorps   xmm0, xmm0
0x180009e4e  xorps   xmm1, xmm1
0x180009e51  movups  [rsp+140h+var_E0], xmm0
0x180009e56  movdqu  [rsp+140h+var_D0], xmm1
0x180009e5c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009e61  mov     ebx, 2
0x180009e66  mov     [rsp+140h+var_F0], ebx
0x180009e6a  mov     rcx, qword ptr [rsp+140h+var_E0]
0x180009e6f  lea     rdx, [rsp+140h+var_E0]
0x180009e74  cmp     qword ptr [rsp+140h+var_D0+8], 7
0x180009e7a  cmova   rdx, rcx
0x180009e7e  inc     rdi
0x180009e81  cmp     [rdx+rdi*2], r13w
0x180009e86  jnz     short loc_180009E7E
0x180009e88  mov     r8, rdi
0x180009e8b  mov     rcx, r15; Src
0x180009e8e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009e93  nop
0x180009e94  mov     rdx, qword ptr [rsp+140h+var_D0+8]
0x180009e99  cmp     rdx, 7
0x180009e9d  ja      loc_180009F6D
0x180009ea3  or      ebx, 1
0x180009ea6  mov     [rsp+140h+var_F0], ebx
0x180009eaa  mov     [r14], r13
0x180009ead  lea     rdx, [rbp+40h+lpSubKey]
0x180009eb1  cmp     [rbp+40h+var_A8], 7
0x180009eb6  cmova   rdx, [rbp+40h+lpSubKey]; lpSubKey
0x180009ebb  mov     [rsp+140h+lpdwDisposition], r13; lpdwDisposition
0x180009ec0  mov     [rsp+140h+phkResult], r14; phkResult
0x180009ec5  mov     [rsp+140h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180009eca  mov     [rsp+140h+samDesired], 0Fh; samDesired
0x180009ed2  mov     [rsp+140h+dwOptions], r13d; unsigned int
0x180009ed7  xor     r9d, r9d; lpClass
0x180009eda  xor     r8d, r8d; Reserved
0x180009edd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009ee4  call    cs:__imp_RegCreateKeyExW
0x180009eea  mov     rcx, [rbp+48h]; this
0x180009eee  test    eax, eax
0x180009ef0  jnz     loc_180009F84
0x180009ef6  mov     rdx, [rbp+40h+var_A8]
0x180009efa  cmp     rdx, 7
0x180009efe  ja      loc_180009F99
0x180009f04  mov     rax, r14
0x180009f07  mov     rcx, [rbp+40h+var_50]
0x180009f0b  xor     rcx, rsp; StackCookie
0x180009f0e  call    __security_check_cookie
0x180009f13  add     rsp, 108h
0x180009f1a  pop     r15
0x180009f1c  pop     r14
0x180009f1e  pop     r13
0x180009f20  pop     r12
0x180009f22  pop     rdi
0x180009f23  pop     rsi
0x180009f24  pop     rbx
0x180009f25  pop     rbp
0x180009f26  retn
0x180009f27  cmp     esi, 7FFFFFFFh
0x180009f2d  jz      short loc_180009F40
0x180009f2f  mov     edx, esi
0x180009f31  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x180009f36  mov     ebx, 6
0x180009f3b  jmp     loc_180009E66
0x180009f40  mov     r8d, 3
0x180009f46  lea     rdx, aAll; "All"
0x180009f4d  jmp     loc_180009E4B
0x180009f52  mov     r9d, 8007007Ah; char *
0x180009f58  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180009f5f  mov     edx, 8Ch; void *
0x180009f64  mov     rcx, rdi; this
0x180009f67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009f6d  lea     rdx, ds:2[rdx*2]
0x180009f75  mov     rcx, qword ptr [rsp+140h+var_E0]
0x180009f7a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009f7f  jmp     loc_180009EA3
0x180009f84  mov     r9d, eax; char *
0x180009f87  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180009f8e  mov     edx, 93h; void *
0x180009f93  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009f99  lea     rdx, ds:2[rdx*2]
0x180009fa1  mov     rcx, [rbp+40h+lpSubKey]
0x180009fa5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009faa  jmp     loc_180009F04
```
