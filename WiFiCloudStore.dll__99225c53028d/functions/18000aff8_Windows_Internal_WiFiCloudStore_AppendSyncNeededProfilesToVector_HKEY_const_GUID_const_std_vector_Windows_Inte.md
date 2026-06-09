# Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(HKEY__ * const,_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile,std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>> &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration)

- ea: `0x18000aff8`
- end: `0x18000b2ff`
- name: `?AppendSyncNeededProfilesToVector@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@AEBU_GUID@@AEAV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@W4ProfileModificationType@123@W4ProfileGeneration@123@@Z`
- size: `775`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000aebc`

## callees

- `0x180006afc`
- `0x18000aff8`
- `0x18000b508`
- `0x18000b6a0`
- `0x18000b714`
- `0x18000b788`
- `0x18000b7f8`
- `0x180025308`
- `0x180025404`
- `0x18002714c`
- `0x180031ce4`
- `0x18003d3f8`
- `0x18003d450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b061`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b061`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b16f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b242`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b16f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000b242`

## string_xrefs

- `0x18000b0c5`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x18000b1f6`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::WiFiCloudStore::AppendSyncNeededProfilesToVector(
        HKEY hKey,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5)
{
  unsigned int v8; // eax
  DWORD v9; // esi
  WCHAR *v10; // rdi
  BYTE *v11; // r14
  __int64 result; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  const char *v16; // rax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-B1h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-B1h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-B1h]
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-A1h]
  LPDWORD lpcbMaxClassLena; // [rsp+30h] [rbp-A1h]
  WCHAR *v22; // [rsp+60h] [rbp-71h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-69h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-65h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-61h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-5Dh] BYREF
  _QWORD v27[3]; // [rsp+78h] [rbp-59h] BYREF
  LPBYTE lpData[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-31h]
  LPWSTR lpValueName[2]; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-19h]
  _QWORD v32[2]; // [rsp+C0h] [rbp-11h] BYREF
  char v33; // [rsp+D0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]
  __int64 v35; // [rsp+148h] [rbp+77h] BYREF

  LODWORD(v35) = a4;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
      (const char *)v8,
      lpcSubKeys);
  std::vector<bond::blob>::vector<bond::blob>(v27);
  v32[0] = a2;
  v32[1] = v27;
  v33 = 1;
  *(_OWORD *)lpValueName = 0;
  v31 = 0;
  std::vector<unsigned short>::_Construct_n<>(lpValueName, cbMaxValueNameLen + 1);
  *(_OWORD *)lpData = 0;
  v29 = 0;
  std::vector<unsigned char>::_Construct_n<>(lpData, 16);
  v9 = 0;
  v10 = lpValueName[0];
  v11 = lpData[0];
  while ( v9 < cValues )
  {
    cchValueName = lpValueName[1] - v10;
    cbData = LODWORD(lpData[1]) - (_DWORD)v11;
    v15 = RegEnumValueW(hKey, v9, v10, &cchValueName, 0, 0, v11, &cbData);
    if ( v15 == 234 )
    {
      v13 = RegEnumValueW(hKey, v9, v10, &cchValueName, 0, 0, 0, 0);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
          (const char *)v13,
          lpcSubKeysa);
      LODWORD(lpcbMaxClassLen) = cbData;
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)0xD,
        (unsigned int)"Value name: %ws, Size: %d",
        (const char *)v10,
        lpcbMaxClassLen);
      v22 = v10;
      std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<unsigned short *,enum Windows::Internal::WiFiCloudStore::ProfileModificationType const &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
        v27,
        &v22,
        &v35,
        &a5);
    }
    else if ( v15 )
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)v15,
        lpcSubKeysb);
    }
    if ( cbData < 4 )
    {
      v14 = 85;
LABEL_20:
      LODWORD(lpcbMaxClassLena) = cbData;
      v16 = "Value name: %ws, Size: %d";
      goto LABEL_21;
    }
    if ( *(_DWORD *)v11 == 1 )
    {
      if ( cbData == 16 )
      {
        v22 = v10;
        std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<unsigned short *,_FILETIME &,enum Windows::Internal::WiFiCloudStore::ProfileModificationType &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
          a3,
          (unsigned int)&v22,
          (_DWORD)v11 + 4,
          (_DWORD)v11 + 12,
          (__int64)&a5);
        goto LABEL_22;
      }
      v14 = 68;
      goto LABEL_20;
    }
    LODWORD(lpcbMaxClassLena) = *(_DWORD *)v11;
    v16 = "Value name: %ws, Version: %d";
    v14 = 79;
LABEL_21:
    wil::details::in1diag3::Log_Win32Msg(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
      (const char *)0xD,
      (unsigned int)v16,
      (const char *)v10,
      lpcbMaxClassLena);
    v22 = v10;
    std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<unsigned short *,enum Windows::Internal::WiFiCloudStore::ProfileModificationType const &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
      v27,
      &v22,
      &v35,
      &a5);
LABEL_22:
    ++v9;
  }
  std::vector<unsigned char>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(lpValueName);
  v33 = 0;
  result = lambda_ff5c2e37f76c59f81b707e2467719f41_::operator()(v32);
  if ( v27[0] )
  {
    std::_Destroy_range<std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>>(v27[0], v27[1]);
    return std::_Deallocate<16>(v27[0], 16 * ((__int64)(v27[2] - v27[0]) >> 4));
  }
  return result;
}

```

## disassembly

```asm
0x18000aff8  mov     dword ptr [rsp-8+arg_18], r9d
0x18000affd  push    rbp
0x18000affe  push    rbx
0x18000afff  push    rsi
0x18000b000  push    rdi
0x18000b001  push    r12
0x18000b003  push    r13
0x18000b005  push    r14
0x18000b007  push    r15
0x18000b009  lea     rbp, [rsp-17h]
0x18000b00e  sub     rsp, 0E8h
0x18000b015  mov     r12, r8
0x18000b018  mov     rbx, rdx
0x18000b01b  mov     r15, rcx
0x18000b01e  xor     r13d, r13d
0x18000b021  mov     [rbp+4Fh+cValues], r13d
0x18000b025  mov     [rbp+4Fh+cbMaxValueNameLen], r13d
0x18000b029  mov     [rsp+120h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000b02e  mov     [rsp+120h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000b033  mov     [rsp+120h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000b038  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x18000b03c  mov     [rsp+120h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000b041  lea     rax, [rbp+4Fh+cValues]
0x18000b045  mov     [rsp+120h+lpcValues], rax; lpcValues
0x18000b04a  mov     [rsp+120h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000b04f  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18000b054  mov     [rsp+120h+lpcSubKeys], r13; unsigned int
0x18000b059  xor     r9d, r9d; lpReserved
0x18000b05c  xor     r8d, r8d; lpcchClass
0x18000b05f  xor     edx, edx; lpClass
0x18000b061  call    cs:__imp_RegQueryInfoKeyW
0x18000b067  mov     rcx, [rbp+57h]; this
0x18000b06b  test    eax, eax
0x18000b06d  jnz     loc_18000B1F3
0x18000b073  lea     rcx, [rbp+4Fh+var_A8]
0x18000b077  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18000b07c  nop
0x18000b07d  mov     [rbp+4Fh+var_60], rbx
0x18000b081  lea     rax, [rbp+4Fh+var_A8]
0x18000b085  mov     [rbp+4Fh+var_58], rax
0x18000b089  mov     [rbp+4Fh+var_50], 1
0x18000b08d  xorps   xmm0, xmm0
0x18000b090  movdqu  xmmword ptr [rbp+4Fh+lpValueName], xmm0
0x18000b095  mov     [rbp+4Fh+var_68], r13
0x18000b099  mov     edx, [rbp+4Fh+cbMaxValueNameLen]
0x18000b09c  inc     edx
0x18000b09e  lea     rcx, [rbp+4Fh+lpValueName]
0x18000b0a2  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x18000b0a7  nop
0x18000b0a8  xorps   xmm0, xmm0
0x18000b0ab  movdqu  xmmword ptr [rbp+4Fh+lpData], xmm0
0x18000b0b0  mov     [rbp+4Fh+var_80], r13
0x18000b0b4  lea     edx, [r13+10h]
0x18000b0b8  lea     rcx, [rbp+4Fh+lpData]
0x18000b0bc  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18000b0c1  nop
0x18000b0c2  mov     esi, r13d
0x18000b0c5  lea     rbx, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18000b0cc  mov     rdi, [rbp+4Fh+lpValueName]
0x18000b0d0  mov     r14, [rbp+4Fh+lpData]
0x18000b0d4  cmp     esi, [rbp+4Fh+cValues]
0x18000b0d7  jb      loc_18000B208
0x18000b0dd  lea     rcx, [rbp+4Fh+lpData]
0x18000b0e1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b0e6  nop
0x18000b0e7  lea     rcx, [rbp+4Fh+lpValueName]
0x18000b0eb  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18000b0f0  nop
0x18000b0f1  mov     [rbp+4Fh+var_50], r13b
0x18000b0f5  lea     rcx, [rbp+4Fh+var_60]
0x18000b0f9  call    _lambda_ff5c2e37f76c59f81b707e2467719f41___operator__
0x18000b0fe  nop
0x18000b0ff  mov     rcx, [rbp+4Fh+var_A8]
0x18000b103  test    rcx, rcx
0x18000b106  jz      short loc_18000B13B
0x18000b108  mov     rdx, [rbp+4Fh+var_A0]
0x18000b10c  call    ??$_Destroy_range@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@YAXPEAUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@QEAU1234@AEAV?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>>(Windows::Internal::WiFiCloudStore::SyncNeededProfile *,Windows::Internal::WiFiCloudStore::SyncNeededProfile * const,std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile> &)
0x18000b111  mov     rcx, [rbp+4Fh+var_A8]
0x18000b115  mov     rax, [rbp+4Fh+var_98]
0x18000b119  sub     rax, rcx
0x18000b11c  sar     rax, 4
0x18000b120  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000b12a  imul    rax, rdx
0x18000b12e  lea     rdx, [rax+rax*2]
0x18000b132  shl     rdx, 4
0x18000b136  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b13b  add     rsp, 0E8h
0x18000b142  pop     r15
0x18000b144  pop     r14
0x18000b146  pop     r13
0x18000b148  pop     r12
0x18000b14a  pop     rdi
0x18000b14b  pop     rsi
0x18000b14c  pop     rbx
0x18000b14d  pop     rbp
0x18000b14e  retn
0x18000b14f  mov     [rsp+120h+lpcValues], r13; lpcbData
0x18000b154  mov     [rsp+120h+lpcbMaxClassLen], r13; lpData
0x18000b159  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; lpType
0x18000b15e  mov     [rsp+120h+lpcSubKeys], r13; unsigned int
0x18000b163  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x18000b167  mov     r8, rdi; lpValueName
0x18000b16a  mov     edx, esi; dwIndex
0x18000b16c  mov     rcx, r15; hKey
0x18000b16f  call    cs:__imp_RegEnumValueW
0x18000b175  mov     rcx, [rbp+57h]; this
0x18000b179  mov     r8, rbx; unsigned int
0x18000b17c  test    eax, eax
0x18000b17e  jnz     loc_18000B2F1
0x18000b184  mov     rcx, [rbp+57h]; this
0x18000b188  mov     eax, [rbp+4Fh+cbData]
0x18000b18b  mov     dword ptr [rsp+120h+lpcbMaxClassLen], eax
0x18000b18f  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; char *
0x18000b194  lea     rax, aValueNameWsSiz; "Value name: %ws, Size: %d"
0x18000b19b  mov     [rsp+120h+lpcSubKeys], rax; unsigned int
0x18000b1a0  mov     r9d, 0Dh; char *
0x18000b1a6  lea     edx, [r9+26h]; void *
0x18000b1aa  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b1af  mov     [rbp+4Fh+var_C0], rdi
0x18000b1b3  lea     r9, [rbp+4Fh+arg_20]
0x18000b1b7  lea     r8, [rbp+4Fh+arg_18]
0x18000b1bb  lea     rdx, [rbp+4Fh+var_C0]
0x18000b1bf  lea     rcx, [rbp+4Fh+var_A8]
0x18000b1c3  call    ??$emplace_back@PEAGAEBW4ProfileModificationType@WiFiCloudStore@Internal@Windows@@AEBW4ProfileGeneration@234@@?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@QEAAAEAUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@$$QEAPEAGAEBW4ProfileModificationType@345@AEBW4ProfileGeneration@345@@Z; std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<ushort *,Windows::Internal::WiFiCloudStore::ProfileModificationType const &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort * &&,Windows::Internal::WiFiCloudStore::ProfileModificationType const &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x18000b1c8  mov     eax, [rbp+4Fh+cbData]
0x18000b1cb  cmp     eax, 4
0x18000b1ce  jb      loc_18000B2A5
0x18000b1d4  mov     edx, [r14]
0x18000b1d7  cmp     edx, 1
0x18000b1da  jnz     loc_18000B293
0x18000b1e0  cmp     eax, 10h
0x18000b1e3  jz      loc_18000B270
0x18000b1e9  mov     edx, 44h ; 'D'
0x18000b1ee  jmp     loc_18000B2AA
0x18000b1f3  mov     r9d, eax; char *
0x18000b1f6  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18000b1fd  mov     edx, 11h; void *
0x18000b202  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000b208  mov     rax, [rbp+4Fh+lpValueName+8]
0x18000b20c  sub     rax, rdi
0x18000b20f  sar     rax, 1
0x18000b212  mov     [rbp+4Fh+cchValueName], eax
0x18000b215  mov     eax, dword ptr [rbp+4Fh+lpData+8]
0x18000b218  sub     eax, r14d
0x18000b21b  mov     [rbp+4Fh+cbData], eax
0x18000b21e  lea     rax, [rbp+4Fh+cbData]
0x18000b222  mov     [rsp+120h+lpcValues], rax; lpcbData
0x18000b227  mov     [rsp+120h+lpcbMaxClassLen], r14; lpData
0x18000b22c  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; lpType
0x18000b231  mov     [rsp+120h+lpcSubKeys], r13; unsigned int
0x18000b236  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x18000b23a  mov     r8, rdi; lpValueName
0x18000b23d  mov     edx, esi; dwIndex
0x18000b23f  mov     rcx, r15; hKey
0x18000b242  call    cs:__imp_RegEnumValueW
0x18000b248  cmp     eax, 0EAh
0x18000b24d  jz      loc_18000B14F
0x18000b253  test    eax, eax
0x18000b255  jz      loc_18000B1C8
0x18000b25b  mov     rcx, [rbp+57h]; this
0x18000b25f  mov     r9d, eax; char *
0x18000b262  mov     r8, rbx; unsigned int
0x18000b265  mov     edx, 38h ; '8'; void *
0x18000b26a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000b270  mov     [rbp+4Fh+var_C0], rdi
0x18000b274  lea     r9, [r14+0Ch]
0x18000b278  lea     r8, [r14+4]
0x18000b27c  lea     rax, [rbp+4Fh+arg_20]
0x18000b280  mov     [rsp+120h+lpcSubKeys], rax
0x18000b285  lea     rdx, [rbp+4Fh+var_C0]
0x18000b289  mov     rcx, r12
0x18000b28c  call    ??$emplace_back@PEAGAEAU_FILETIME@@AEAW4ProfileModificationType@WiFiCloudStore@Internal@Windows@@AEBW4ProfileGeneration@345@@?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@QEAAAEAUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@$$QEAPEAGAEAU_FILETIME@@AEAW4ProfileModificationType@345@AEBW4ProfileGeneration@345@@Z; std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<ushort *,_FILETIME &,Windows::Internal::WiFiCloudStore::ProfileModificationType &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort * &&,_FILETIME &,Windows::Internal::WiFiCloudStore::ProfileModificationType &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x18000b291  jmp     short loc_18000B2EA
0x18000b293  mov     dword ptr [rsp+120h+lpcbMaxClassLen], edx
0x18000b297  lea     rax, aValueNameWsVer; "Value name: %ws, Version: %d"
0x18000b29e  mov     edx, 4Fh ; 'O'
0x18000b2a3  jmp     short loc_18000B2B5
0x18000b2a5  mov     edx, 55h ; 'U'; void *
0x18000b2aa  mov     dword ptr [rsp+120h+lpcbMaxClassLen], eax
0x18000b2ae  lea     rax, aValueNameWsSiz; "Value name: %ws, Size: %d"
0x18000b2b5  mov     [rsp+120h+lpcbMaxSubKeyLen], rdi; char *
0x18000b2ba  mov     [rsp+120h+lpcSubKeys], rax; unsigned int
0x18000b2bf  mov     r9d, 0Dh; char *
0x18000b2c5  mov     r8, rbx; unsigned int
0x18000b2c8  mov     rcx, [rbp+57h]; this
0x18000b2cc  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b2d1  mov     [rbp+4Fh+var_C0], rdi
0x18000b2d5  lea     r9, [rbp+4Fh+arg_20]
0x18000b2d9  lea     r8, [rbp+4Fh+arg_18]
0x18000b2dd  lea     rdx, [rbp+4Fh+var_C0]
0x18000b2e1  lea     rcx, [rbp+4Fh+var_A8]
0x18000b2e5  call    ??$emplace_back@PEAGAEBW4ProfileModificationType@WiFiCloudStore@Internal@Windows@@AEBW4ProfileGeneration@234@@?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@QEAAAEAUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@$$QEAPEAGAEBW4ProfileModificationType@345@AEBW4ProfileGeneration@345@@Z; std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<ushort *,Windows::Internal::WiFiCloudStore::ProfileModificationType const &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort * &&,Windows::Internal::WiFiCloudStore::ProfileModificationType const &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x18000b2ea  inc     esi
0x18000b2ec  jmp     loc_18000B0D4
0x18000b2f1  mov     r9d, eax; char *
0x18000b2f4  mov     edx, 32h ; '2'; void *
0x18000b2f9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
