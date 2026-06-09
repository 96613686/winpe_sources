# Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl::DeviceInformationImpl(Microsoft::Applications::Events::IRuntimeConfig &)

- ea: `0x140100614`
- end: `0x140100bd0`
- name: `??0DeviceInformationImpl@PlatformAbstraction@Events@Applications@Microsoft@@QEAA@AEAVIRuntimeConfig@234@@Z`
- size: `1468`
- prototype: `__int64 __fastcall(Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl *__hidden this, struct Microsoft::Applications::Events::IRuntimeConfig *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400feeb8`

## callees

- `0x14003a5c0`
- `0x14007e088`
- `0x14007f0f4`
- `0x140084a18`
- `0x14009d4d0`
- `0x1400fe950`
- `0x1400ff188`
- `0x140100614`
- `0x14015f8e0`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1401007ed`
- `KERNEL32!HeapFree` at `0x140100886`
- `KERNEL32!HeapFree` at `0x1401007ed`
- `KERNEL32!HeapFree` at `0x140100886`
- `KERNEL32!GetSystemPowerStatus` at `0x140100b78`
- `KERNEL32!GetSystemPowerStatus` at `0x140100b78`
- `KERNEL32!HeapAlloc` at `0x1401007a7`
- `KERNEL32!HeapAlloc` at `0x140100804`
- `KERNEL32!HeapAlloc` at `0x1401007a7`
- `KERNEL32!HeapAlloc` at `0x140100804`
- `KERNEL32!GetProcessHeap` at `0x140100799`
- `KERNEL32!GetProcessHeap` at `0x1401007df`
- `KERNEL32!GetProcessHeap` at `0x1401007f6`
- `KERNEL32!GetProcessHeap` at `0x140100878`
- `KERNEL32!GetProcessHeap` at `0x140100799`
- `KERNEL32!GetProcessHeap` at `0x1401007df`
- `KERNEL32!GetProcessHeap` at `0x1401007f6`
- `KERNEL32!GetProcessHeap` at `0x140100878`
- `KERNEL32!GetNativeSystemInfo` at `0x14010072d`
- `KERNEL32!GetNativeSystemInfo` at `0x14010072d`
- `ADVAPI32!RegGetValueA` at `0x140100959`
- `ADVAPI32!RegGetValueA` at `0x140100aa1`
- `ADVAPI32!RegGetValueA` at `0x140100959`
- `ADVAPI32!RegGetValueA` at `0x140100aa1`
- `IPHLPAPI!GetAdaptersInfo` at `0x1401007c7`
- `IPHLPAPI!GetAdaptersInfo` at `0x1401007c7`

## string_xrefs

- `0x140100a8c`: `SystemProductName`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl::DeviceInformationImpl(
        Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl *this,
        struct Microsoft::Applications::Events::IRuntimeConfig *a2)
{
  int v3; // edi
  size_t v4; // r13
  __int128 *v5; // r12
  void **v6; // r14
  void **v7; // rsi
  int v8; // eax
  HANDLE ProcessHeap; // rax
  struct _IP_ADAPTER_INFO *v10; // rbx
  char *AdapterName; // r15
  ULONG AdaptersInfo; // eax
  HANDLE v13; // rax
  ULONG v14; // ebx
  HANDLE v15; // rax
  size_t v16; // r8
  HANDLE v17; // rax
  __int64 v18; // r8
  _BYTE *v19; // rbx
  Microsoft::Applications::Events::PlatformAbstraction *v20; // rcx
  __int64 v21; // r8
  size_t v22; // r8
  __int64 v23; // r8
  void **v24; // r9
  size_t v25; // rbx
  void *v26; // r15
  _BYTE *v27; // rbx
  Microsoft::Applications::Events::PlatformAbstraction *v28; // rcx
  __int64 v29; // r8
  void **v30; // r9
  size_t v31; // rbx
  void *v32; // r14
  __int64 result; // rax
  __int128 v34; // [rsp+50h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A8h]
  _BYTE v36[40]; // [rsp+70h] [rbp-98h] BYREF
  ULONG SizePointer; // [rsp+98h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+9Ch] [rbp-6Ch] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+A0h] [rbp-68h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-58h] BYREF
  size_t Size; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v42; // [rsp+C8h] [rbp-40h]
  void *v43[2]; // [rsp+D0h] [rbp-38h] BYREF
  size_t v44; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v45; // [rsp+E8h] [rbp-20h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE pvData[256]; // [rsp+128h] [rbp+20h] BYREF

  *(_QWORD *)v36 = this;
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = this;
  v3 = 0;
  *(_QWORD *)this = &Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 15;
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 6) = &Microsoft::Applications::Events::PlatformAbstraction::InformatonProviderImpl::`vftable';
  *((_QWORD *)this + 7) = 2;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  v4 = -1;
  *((_DWORD *)this + 32) = -1;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  v5 = (__int128 *)((char *)this + 168);
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 15;
  *((_BYTE *)this + 168) = 0;
  v6 = (void **)((char *)this + 200);
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 15;
  *((_BYTE *)this + 200) = 0;
  v7 = (void **)((char *)this + 232);
  *(_OWORD *)((char *)this + 232) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 15;
  *((_BYTE *)this + 232) = 0;
  *((_QWORD *)this + 33) = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetNativeSystemInfo(&SystemInfo);
  v8 = 1;
  if ( SystemInfo.wProcessorArchitecture )
  {
    if ( SystemInfo.wProcessorArchitecture == 5 )
    {
      v8 = 3;
    }
    else if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
    {
      v8 = 2;
    }
    else
    {
      v8 = 0;
    }
  }
  *((_DWORD *)this + 10) = v8;
  v34 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v34, "{deadbeef-fade-dead-c0de-cafebabefeed}", 0x26u);
  SizePointer = 704;
  ProcessHeap = GetProcessHeap();
  v10 = (struct _IP_ADAPTER_INFO *)HeapAlloc(ProcessHeap, 0, 0x2C0u);
  if ( v10 )
  {
    while ( 1 )
    {
      AdapterName = v10->AdapterName;
      v10->AdapterName[0] = 0;
      AdaptersInfo = GetAdaptersInfo(v10, &SizePointer);
      if ( AdaptersInfo != 111 )
        break;
      if ( SizePointer <= 0x2C0 )
        goto LABEL_18;
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v10);
      v14 = SizePointer;
      v15 = GetProcessHeap();
      v10 = (struct _IP_ADAPTER_INFO *)HeapAlloc(v15, 0, v14);
      if ( !v10 )
        goto LABEL_19;
    }
    if ( !AdaptersInfo && *AdapterName )
    {
      memset(&v36[8], 0, 32);
      v16 = -1;
      do
        ++v16;
      while ( AdapterName[v16] );
      std::string::_Construct<1,char const *>(&v36[8], v10->AdapterName, v16);
      Microsoft::Applications::Events::toLower(&SystemInfo, &v36[8]);
      std::string::_Tidy_deallocate(&v36[8]);
      std::string::operator=(&v34);
      std::string::_Tidy_deallocate(&SystemInfo);
    }
LABEL_18:
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v10);
  }
LABEL_19:
  if ( v5 != &v34 )
  {
    std::string::_Tidy_deallocate(v5);
    *v5 = v34;
    v5[1] = (__int128)si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v34) = 0;
  }
  std::string::_Tidy_deallocate(&v34);
  memset(pvData, 0, sizeof(pvData));
  pcbData = 256;
  if ( (unsigned __int64)v6[3] < 0x14 )
  {
    std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
      v6,
      20,
      v18,
      "Unknown Manufacturer");
  }
  else
  {
    v19 = *v6;
    v6[2] = (void *)20;
    memmove(v19, "Unknown Manufacturer", 0x14u);
    v19[20] = 0;
  }
  if ( !RegGetValueA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Control\\SystemInformation",
          "SystemManufacturer",
          2u,
          0,
          pvData,
          &pcbData) )
  {
    *(_OWORD *)Src = 0;
    Size = 0;
    v42 = 0;
    v22 = -1;
    do
      ++v22;
    while ( pvData[v22] );
    std::string::_Construct<1,char const *>(Src, pvData, v22);
    if ( v6 != Src )
    {
      v24 = Src;
      if ( v42 > 0xF )
        v24 = (void **)Src[0];
      v25 = Size;
      if ( Size > (unsigned __int64)v6[3] )
      {
        _mm_lfence();
        std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v6, Size, v23, v24);
      }
      else
      {
        v26 = v6;
        if ( (unsigned __int64)v6[3] > 0xF )
          v26 = *v6;
        v6[2] = (void *)Size;
        memmove(v26, v24, v25);
        *((_BYTE *)v26 + v25) = 0;
      }
    }
    std::string::_Tidy_deallocate(Src);
  }
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    if ( (unsigned __int64)v6[3] > 0xF )
      v6 = (void **)*v6;
    Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v20);
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK.PAL",
      "Device Manufacturer=%s",
      (const char *)v6);
  }
  pcbData = 256;
  if ( (unsigned __int64)v7[3] < 0xD )
  {
    std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v7, 13, v21, "Unknown Model");
  }
  else
  {
    v27 = v7;
    if ( (unsigned __int64)v7[3] > 0xF )
      v27 = *v7;
    v7[2] = (void *)13;
    memmove(v27, "Unknown Model", 0xDu);
    v27[13] = 0;
  }
  if ( !RegGetValueA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Control\\SystemInformation",
          "SystemProductName",
          2u,
          0,
          pvData,
          &pcbData) )
  {
    *(_OWORD *)v43 = 0;
    v44 = 0;
    v45 = 0;
    do
      ++v4;
    while ( pvData[v4] );
    std::string::_Construct<1,char const *>(v43, pvData, v4);
    if ( v7 != v43 )
    {
      v30 = v43;
      if ( v45 > 0xF )
        v30 = (void **)v43[0];
      v31 = v44;
      if ( v44 > (unsigned __int64)v7[3] )
      {
        _mm_lfence();
        std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v7, v44, v29, v30);
      }
      else
      {
        v32 = v7;
        if ( (unsigned __int64)v7[3] > 0xF )
          v32 = *v7;
        v7[2] = (void *)v44;
        memmove(v32, v30, v31);
        *((_BYTE *)v32 + v31) = 0;
      }
    }
    std::string::_Tidy_deallocate(v43);
  }
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    if ( (unsigned __int64)v7[3] > 0xF )
      v7 = (void **)*v7;
    Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v28);
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK.PAL",
      "Device Model=%s",
      (const char *)v7);
  }
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    if ( SystemPowerStatus.ACLineStatus == 1 )
    {
      v3 = 2;
    }
    else if ( !SystemPowerStatus.ACLineStatus )
    {
      v3 = 1;
    }
  }
  result = *(_QWORD *)v36;
  *(_DWORD *)(*(_QWORD *)v36 + 44LL) = v3;
  return result;
}

```

## disassembly

```asm
0x140100614  mov     rax, rsp
0x140100617  mov     [rax+10h], rbx
0x14010061b  mov     [rax+18h], rsi
0x14010061f  mov     [rax+20h], rdi
0x140100623  push    rbp
0x140100624  push    r12
0x140100626  push    r13
0x140100628  push    r14
0x14010062a  push    r15
0x14010062c  lea     rbp, [rax-158h]
0x140100633  sub     rsp, 230h
0x14010063a  mov     rax, cs:__security_cookie
0x140100641  xor     rax, rsp
0x140100644  mov     [rbp+150h+var_30], rax
0x14010064b  mov     rbx, rcx
0x14010064e  mov     qword ptr [rsp+250h+var_1E8], rcx
0x140100653  mov     qword ptr [rbp+150h+SystemPowerStatus.ACLineStatus], rcx
0x140100657  xor     edi, edi
0x140100659  mov     dword ptr [rsp+250h+var_210], edi
0x14010065d  lea     rax, ??_7DeviceInformationImpl@PlatformAbstraction@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::PlatformAbstraction::DeviceInformationImpl::`vftable'
0x140100664  mov     [rcx], rax
0x140100667  xorps   xmm0, xmm0
0x14010066a  movups  xmmword ptr [rcx+8], xmm0
0x14010066e  mov     [rcx+18h], rdi
0x140100672  lea     r15d, [rdi+0Fh]
0x140100676  mov     [rcx+20h], r15
0x14010067a  mov     [rcx+8], dil
0x14010067e  lea     rax, ??_7InformatonProviderImpl@PlatformAbstraction@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::PlatformAbstraction::InformatonProviderImpl::`vftable'
0x140100685  mov     [rcx+30h], rax
0x140100689  mov     qword ptr [rcx+38h], 2
0x140100691  movups  xmmword ptr [rcx+50h], xmm0
0x140100695  movups  xmmword ptr [rcx+60h], xmm0
0x140100699  movups  xmmword ptr [rcx+70h], xmm0
0x14010069d  mov     [rcx+40h], rdi
0x1401006a1  mov     [rcx+48h], rdi
0x1401006a5  or      r13, 0FFFFFFFFFFFFFFFFh
0x1401006a9  mov     [rcx+80h], r13d
0x1401006b0  mov     [rcx+84h], edi
0x1401006b6  mov     [rcx+88h], rdi
0x1401006bd  mov     [rcx+90h], rdi
0x1401006c4  mov     [rcx+98h], rdi
0x1401006cb  mov     [rcx+0A0h], edi
0x1401006d1  lea     r12, [rcx+0A8h]
0x1401006d8  movups  xmmword ptr [r12], xmm0
0x1401006dd  mov     [r12+10h], rdi
0x1401006e2  mov     [r12+18h], r15
0x1401006e7  mov     [r12], dil
0x1401006eb  lea     r14, [rcx+0C8h]
0x1401006f2  movups  xmmword ptr [r14], xmm0
0x1401006f6  mov     [r14+10h], rdi
0x1401006fa  mov     [r14+18h], r15
0x1401006fe  mov     [r14], dil
0x140100701  lea     rsi, [rcx+0E8h]
0x140100708  movups  xmmword ptr [rsi], xmm0
0x14010070b  mov     [rsi+10h], rdi
0x14010070f  mov     [rsi+18h], r15
0x140100713  mov     [rsi], dil
0x140100716  mov     [rcx+108h], rdi
0x14010071d  movups  xmmword ptr [rbp+150h+SystemInfo], xmm0
0x140100721  movups  xmmword ptr [rbp+150h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140100725  movups  xmmword ptr [rbp+150h+SystemInfo.dwNumberOfProcessors], xmm0
0x140100729  lea     rcx, [rbp+150h+SystemInfo]; lpSystemInfo
0x14010072d  call    cs:__imp_GetNativeSystemInfo
0x140100733  movzx   ecx, word ptr [rbp+150h+SystemInfo]
0x140100737  lea     eax, [rdi+1]
0x14010073a  test    ecx, ecx
0x14010073c  jz      short loc_14010075E
0x14010073e  sub     ecx, 5
0x140100741  jz      short loc_140100759
0x140100743  sub     ecx, eax
0x140100745  jz      short loc_140100752
0x140100747  lea     eax, [rdi+3]
0x14010074a  cmp     ecx, eax
0x14010074c  jz      short loc_140100752
0x14010074e  mov     eax, edi
0x140100750  jmp     short loc_14010075E
0x140100752  mov     eax, 2
0x140100757  jmp     short loc_14010075E
0x140100759  mov     eax, 3
0x14010075e  mov     [rbx+28h], eax
0x140100761  xorps   xmm0, xmm0
0x140100764  movups  [rsp+250h+var_210+8], xmm0
0x140100769  xorps   xmm1, xmm1
0x14010076c  movdqu  xmmword ptr [rsp+250h+var_200+8], xmm1
0x140100772  mov     r8d, 26h ; '&'
0x140100778  lea     rdx, aDeadbeefFadeDe; "{deadbeef-fade-dead-c0de-cafebabefeed}"
0x14010077f  lea     rcx, [rsp+250h+var_210+8]
0x140100784  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140100789  mov     dword ptr [rsp+250h+var_210], 1
0x140100791  mov     ebx, 2C0h
0x140100796  mov     [rbp+150h+SizePointer], ebx
0x140100799  call    cs:__imp_GetProcessHeap
0x14010079f  mov     r8d, ebx; dwBytes
0x1401007a2  xor     edx, edx; dwFlags
0x1401007a4  mov     rcx, rax; hHeap
0x1401007a7  call    cs:__imp_HeapAlloc
0x1401007ad  mov     rbx, rax
0x1401007b0  test    rax, rax
0x1401007b3  jz      loc_140100892
0x1401007b9  lea     r15, [rbx+0Ch]
0x1401007bd  mov     [r15], dil
0x1401007c0  lea     rdx, [rbp+150h+SizePointer]; SizePointer
0x1401007c4  mov     rcx, rbx; AdapterInfo
0x1401007c7  call    cs:__imp_GetAdaptersInfo
0x1401007cd  cmp     eax, 6Fh ; 'o'
0x1401007d0  jnz     short loc_140100814
0x1401007d2  cmp     [rbp+150h+SizePointer], 2C0h
0x1401007d9  jbe     loc_140100878
0x1401007df  call    cs:__imp_GetProcessHeap
0x1401007e5  mov     rcx, rax; hHeap
0x1401007e8  mov     r8, rbx; lpMem
0x1401007eb  xor     edx, edx; dwFlags
0x1401007ed  call    cs:__imp_HeapFree
0x1401007f3  mov     ebx, [rbp+150h+SizePointer]
0x1401007f6  call    cs:__imp_GetProcessHeap
0x1401007fc  mov     r8d, ebx; dwBytes
0x1401007ff  xor     edx, edx; dwFlags
0x140100801  mov     rcx, rax; hHeap
0x140100804  call    cs:__imp_HeapAlloc
0x14010080a  mov     rbx, rax
0x14010080d  test    rax, rax
0x140100810  jnz     short loc_1401007B9
0x140100812  jmp     short loc_14010088C
0x140100814  test    eax, eax
0x140100816  jnz     short loc_140100878
0x140100818  cmp     [r15], dil
0x14010081b  jz      short loc_140100878
0x14010081d  xorps   xmm0, xmm0
0x140100820  movups  [rsp+250h+var_1E8+8], xmm0
0x140100825  xorps   xmm1, xmm1
0x140100828  movdqu  [rbp+150h+var_1D0], xmm1
0x14010082d  mov     r8, r13
0x140100830  inc     r8
0x140100833  cmp     [r15+r8], dil
0x140100837  jnz     short loc_140100830
0x140100839  mov     rdx, r15
0x14010083c  lea     rcx, [rsp+250h+var_1E8+8]
0x140100841  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140100846  nop
0x140100847  lea     rdx, [rsp+250h+var_1E8+8]
0x14010084c  lea     rcx, [rbp+150h+SystemInfo]
0x140100850  call    ?toLower@Events@Applications@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV45@@Z; Microsoft::Applications::Events::toLower(std::string const &)
0x140100855  nop
0x140100856  lea     rcx, [rsp+250h+var_1E8+8]
0x14010085b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140100860  lea     rdx, [rbp+150h+SystemInfo]
0x140100864  lea     rcx, [rsp+250h+var_210+8]; void *
0x140100869  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x14010086e  nop
0x14010086f  lea     rcx, [rbp+150h+SystemInfo]
0x140100873  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140100878  call    cs:__imp_GetProcessHeap
0x14010087e  mov     rcx, rax; hHeap
0x140100881  mov     r8, rbx; lpMem
0x140100884  xor     edx, edx; dwFlags
0x140100886  call    cs:__imp_HeapFree
0x14010088c  mov     r15d, 0Fh
0x140100892  lea     rax, [rsp+250h+var_210+8]
0x140100897  cmp     r12, rax
0x14010089a  jz      short loc_1401008CC
0x14010089c  mov     rcx, r12
0x14010089f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401008a4  movups  xmm0, [rsp+250h+var_210+8]
0x1401008a9  movups  xmmword ptr [r12], xmm0
0x1401008ae  movups  xmm1, xmmword ptr [rsp+250h+var_200+8]
0x1401008b3  movups  xmmword ptr [r12+10h], xmm1
0x1401008b9  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1401008c1  movdqu  xmmword ptr [rsp+250h+var_200+8], xmm0
0x1401008c7  mov     byte ptr [rsp+250h+var_210+8], dil
0x1401008cc  lea     rcx, [rsp+250h+var_210+8]
0x1401008d1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401008d6  mov     r12d, 100h
0x1401008dc  mov     r8d, r12d; Size
0x1401008df  xor     edx, edx; Val
0x1401008e1  lea     rcx, [rbp+150h+var_130]; void *
0x1401008e5  call    memset
0x1401008ea  mov     [rbp+150h+var_1BC], r12d
0x1401008ee  mov     edx, 14h
0x1401008f3  cmp     [r14+18h], rdx
0x1401008f7  jb      short loc_140100918
0x1401008f9  mov     rbx, [r14]
0x1401008fc  mov     [r14+10h], rdx
0x140100900  mov     r8d, edx; Size
0x140100903  lea     rdx, aUnknownManufac; "Unknown Manufacturer"
0x14010090a  mov     rcx, rbx; void *
0x14010090d  call    memmove
0x140100912  mov     [rbx+14h], dil
0x140100916  jmp     short loc_140100927
0x140100918  lea     r9, aUnknownManufac; "Unknown Manufacturer"
0x14010091f  mov     rcx, r14
0x140100922  call    ??$_Reallocate_for@V_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@Z; std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(unsigned __int64,_lambda_66f57f934f28d61049862f64df852ff0_,char const *)
0x140100927  lea     rax, [rbp+150h+var_1BC]
0x14010092b  mov     [rsp+250h+pcbData], rax; pcbData
0x140100930  lea     rax, [rbp+150h+var_130]
0x140100934  mov     [rsp+250h+pvData], rax; pvData
0x140100939  mov     [rsp+250h+pdwType], rdi; pdwType
0x14010093e  mov     r9d, 2; dwFlags
0x140100944  lea     r8, Value; "SystemManufacturer"
0x14010094b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x140100952  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140100959  call    cs:__imp_RegGetValueA
0x14010095f  test    eax, eax
0x140100961  jnz     loc_1401009F1
0x140100967  xorps   xmm0, xmm0
0x14010096a  movups  xmmword ptr [rbp+150h+Src], xmm0
0x14010096e  mov     [rbp+150h+Size], rdi
0x140100972  mov     [rbp+150h+var_190], rdi
0x140100976  lea     rax, [rbp+150h+var_130]
0x14010097a  mov     r8, r13
0x14010097d  inc     r8
0x140100980  cmp     [rax+r8], dil
0x140100984  jnz     short loc_14010097D
0x140100986  lea     rdx, [rbp+150h+var_130]
0x14010098a  lea     rcx, [rbp+150h+Src]
0x14010098e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140100993  nop
0x140100994  lea     rax, [rbp+150h+Src]
0x140100998  cmp     r14, rax
0x14010099b  jz      short loc_1401009E8
0x14010099d  lea     r9, [rbp+150h+Src]
0x1401009a1  cmp     [rbp+150h+var_190], r15
0x1401009a5  cmova   r9, [rbp+150h+Src]
0x1401009aa  mov     rbx, [rbp+150h+Size]
0x1401009ae  cmp     rbx, [r14+18h]
0x1401009b2  ja      short loc_1401009D9
0x1401009b4  mov     r15, r14
0x1401009b7  cmp     qword ptr [r14+18h], 0Fh
0x1401009bc  jbe     short loc_1401009C1
0x1401009be  mov     r15, [r14]
0x1401009c1  mov     [r14+10h], rbx
0x1401009c5  mov     r8, rbx; Size
0x1401009c8  mov     rdx, r9; Src
0x1401009cb  mov     rcx, r15; void *
0x1401009ce  call    memmove
0x1401009d3  mov     [rbx+r15], dil
0x1401009d7  jmp     short loc_1401009E8
0x1401009d9  lfence
0x1401009dc  mov     rdx, rbx
0x1401009df  mov     rcx, r14
0x1401009e2  call    ??$_Reallocate_for@V_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@Z; std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(unsigned __int64,_lambda_66f57f934f28d61049862f64df852ff0_,char const *)
0x1401009e7  nop
0x1401009e8  lea     rcx, [rbp+150h+Src]
0x1401009ec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401009f1  mov     r15d, 4
0x1401009f7  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r15d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x1401009fe  jl      short loc_140100A28
0x140100a00  cmp     qword ptr [r14+18h], 0Fh
0x140100a05  jbe     short loc_140100A0A
0x140100a07  mov     r14, [r14]
0x140100a0a  call    ?GetPAL@PlatformAbstraction@Events@Applications@Microsoft@@YAAEAVPlatformAbstractionLayer@1234@XZ; Microsoft::Applications::Events::PlatformAbstraction::GetPAL(void)
0x140100a0f  mov     r9, r14
0x140100a12  lea     r8, aDeviceManufact; "Device Manufacturer=%s"
0x140100a19  lea     rdx, aMatsdkPal; "MATSDK.PAL"
0x140100a20  mov     ecx, r15d
0x140100a23  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140100a28  mov     [rbp+150h+var_1BC], r12d
0x140100a2c  mov     edx, 0Dh
0x140100a31  cmp     [rsi+18h], rdx
0x140100a35  jb      short loc_140100A60
0x140100a37  mov     rbx, rsi
0x140100a3a  cmp     qword ptr [rsi+18h], 0Fh
0x140100a3f  jbe     short loc_140100A44
0x140100a41  mov     rbx, [rsi]
0x140100a44  mov     [rsi+10h], rdx
0x140100a48  mov     r8, rdx; Size
0x140100a4b  lea     rdx, aUnknownModel; "Unknown Model"
0x140100a52  mov     rcx, rbx; void *
0x140100a55  call    memmove
0x140100a5a  mov     [rbx+0Dh], dil
0x140100a5e  jmp     short loc_140100A6F
0x140100a60  lea     r9, aUnknownModel; "Unknown Model"
0x140100a67  mov     rcx, rsi
0x140100a6a  call    ??$_Reallocate_for@V_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@Z; std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(unsigned __int64,_lambda_66f57f934f28d61049862f64df852ff0_,char const *)
0x140100a6f  lea     rax, [rbp+150h+var_1BC]
0x140100a73  mov     [rsp+250h+pcbData], rax; pcbData
0x140100a78  lea     rax, [rbp+150h+var_130]
0x140100a7c  mov     [rsp+250h+pvData], rax; pvData
0x140100a81  mov     [rsp+250h+pdwType], rdi; pdwType
0x140100a86  mov     r9d, 2; dwFlags
0x140100a8c  lea     r8, aSystemproductn; "SystemProductName"
0x140100a93  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x140100a9a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140100aa1  call    cs:__imp_RegGetValueA
0x140100aa7  test    eax, eax
0x140100aa9  jnz     loc_140100B3A
0x140100aaf  xorps   xmm0, xmm0
0x140100ab2  movups  xmmword ptr [rbp+150h+var_188], xmm0
0x140100ab6  mov     [rbp+150h+var_178], rdi
0x140100aba  mov     [rbp+150h+var_170], rdi
0x140100abe  lea     rax, [rbp+150h+var_130]
0x140100ac2  inc     r13
0x140100ac5  cmp     [rax+r13], dil
0x140100ac9  jnz     short loc_140100AC2
0x140100acb  mov     r8, r13
0x140100ace  lea     rdx, [rbp+150h+var_130]
0x140100ad2  lea     rcx, [rbp+150h+var_188]
0x140100ad6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140100adb  nop
0x140100adc  lea     rax, [rbp+150h+var_188]
0x140100ae0  cmp     rsi, rax
  ... truncated ...
```
