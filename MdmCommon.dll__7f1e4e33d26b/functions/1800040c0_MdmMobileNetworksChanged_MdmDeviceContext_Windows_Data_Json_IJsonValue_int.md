# MdmMobileNetworksChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,int *)

- ea: `0x1800040c0`
- end: `0x1800043a9`
- name: `?MdmMobileNetworksChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@PEAH@Z`
- size: `745`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de4`
- `0x1800040c0`
- `0x1800064f0`
- `0x180006548`
- `0x1800066b0`
- `0x180008a6c`
- `0x180012a24`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000424e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000424e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004383`

## string_xrefs

- `0x180004182`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800041e2`: `CHR(MdmSettings::GetMobileNetworksHash(eDeviceType, wstrMobileNetworksHashFromRegistry))`

## pseudocode

```c
__int64 __fastcall MdmMobileNetworksChanged(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // ebx
  __int64 v6; // r8
  int MobileNetworksHash; // ebx
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  BYTE *v12; // rdi
  __int64 v13; // rbx
  size_t v14; // rdi
  const wchar_t *v15; // rdx
  size_t v16; // rsi
  const wchar_t *v17; // rcx
  size_t v18; // r8
  unsigned int v19; // eax
  char v21; // [rsp+20h] [rbp-89h]
  const char *v22; // [rsp+28h] [rbp-81h]
  HSTRING string; // [rsp+30h] [rbp-79h] BYREF
  int v24; // [rsp+38h] [rbp-71h] BYREF
  BYTE pbData[16]; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-59h]
  unsigned __int64 v27; // [rsp+58h] [rbp-51h]
  wchar_t *S1[2]; // [rsp+60h] [rbp-49h] BYREF
  size_t N; // [rsp+70h] [rbp-39h]
  unsigned __int64 v30; // [rsp+78h] [rbp-31h]
  wchar_t *S2[2]; // [rsp+80h] [rbp-29h] BYREF
  size_t v32; // [rsp+90h] [rbp-19h]
  unsigned __int64 v33; // [rsp+98h] [rbp-11h]
  _BYTE v34[16]; // [rsp+A0h] [rbp-9h] BYREF
  int *v35; // [rsp+B0h] [rbp+7h]
  __int64 v36; // [rsp+B8h] [rbp+Fh]

  v5 = a1;
  string = 0;
  *(_OWORD *)S2 = 0;
  v32 = 0;
  v33 = 7;
  LOWORD(S2[0]) = 0;
  *(_OWORD *)S1 = 0;
  N = 0;
  v30 = 7;
  LOWORD(S1[0]) = 0;
  *(_OWORD *)pbData = 0;
  v26 = 0;
  v27 = 7;
  *(_WORD *)pbData = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_MOBILE_NETWORKS_CHANGED, a3, 1, v34);
  if ( !a2 )
  {
    v6 = 2147942487LL;
    MobileNetworksHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CPR(pMobileNetworks)";
    v21 = -118;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v6 = 2147942487LL;
    MobileNetworksHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        139,
        "CPR(pfChanged)");
    goto LABEL_39;
  }
  MobileNetworksHash = MdmSettings::GetMobileNetworksHash(v5, S2);
  if ( MobileNetworksHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(MdmSettings::GetMobileNetworksHash(eDeviceType, wstrMobileNetworksHashFromRegistry))";
    v21 = -114;
LABEL_14:
    LODWORD(v6) = MobileNetworksHash;
LABEL_6:
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      v21,
      v22);
    goto LABEL_39;
  }
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(string);
  string = 0;
  MobileNetworksHash = v8(a2, &string);
  if ( MobileNetworksHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(pMobileNetworks->Stringify(hstrMobileNetworks.GetAddressOf()))";
    v21 = -111;
    goto LABEL_14;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v11 = -1;
  do
    ++v11;
  while ( StringRawBuffer[v11] );
  if ( v11 > v27 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)pbData,
      v11,
      v10,
      StringRawBuffer);
  }
  else
  {
    v12 = pbData;
    if ( v27 > 7 )
      v12 = *(BYTE **)pbData;
    v26 = v11;
    v13 = 2 * v11;
    memmove_0(v12, StringRawBuffer, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
  }
  MobileNetworksHash = MdmCrypto::HashString(pbData, S1);
  if ( MobileNetworksHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(MdmCrypto::HashString(wstrMobileNetworks, wstrMobileNetworksNewHash))";
    v21 = -107;
    goto LABEL_14;
  }
  v14 = v32;
  v15 = (const wchar_t *)S2;
  if ( v33 > 7 )
    v15 = S2[0];
  v16 = N;
  v17 = (const wchar_t *)S1;
  if ( v30 > 7 )
    v17 = S1[0];
  v18 = v32;
  if ( v32 >= N )
    v18 = N;
  v19 = wmemcmp(v17, v15, v18);
  v6 = v19;
  if ( !v19 )
  {
    if ( v16 >= v14 )
      v6 = v16 > v14;
    else
      v6 = 0xFFFFFFFFLL;
  }
  *a3 = v6 != 0;
LABEL_39:
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v24 = MobileNetworksHash;
    v35 = &v24;
    v36 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_MOBILE_NETWORKS_CHANGED_RESULT, v6, 2, v34);
  }
  std::wstring::~wstring((char **)pbData);
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring((char **)S2);
  WindowsDeleteString(string);
  return (unsigned int)MobileNetworksHash;
}

```

## disassembly

```asm
0x1800040c0  push    rbp
0x1800040c2  push    rbx
0x1800040c3  push    rsi
0x1800040c4  push    rdi
0x1800040c5  push    r13
0x1800040c7  push    r14
0x1800040c9  push    r15
0x1800040cb  lea     rbp, [rsp-27h]
0x1800040d0  sub     rsp, 0D0h
0x1800040d7  mov     rax, cs:__security_cookie
0x1800040de  xor     rax, rsp
0x1800040e1  mov     [rbp+57h+var_40], rax
0x1800040e5  mov     r14, r8
0x1800040e8  mov     rdi, rdx
0x1800040eb  mov     ebx, ecx
0x1800040ed  xor     r15d, r15d
0x1800040f0  mov     [rbp+57h+string], r15
0x1800040f4  xorps   xmm0, xmm0
0x1800040f7  movups  xmmword ptr [rbp+57h+S2], xmm0
0x1800040fb  mov     [rbp+57h+var_70], r15
0x1800040ff  lea     r13d, [r15+7]
0x180004103  mov     [rbp+57h+var_68], r13
0x180004107  mov     word ptr [rbp+57h+S2], r15w
0x18000410c  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180004110  mov     [rbp+57h+N], r15
0x180004114  mov     [rbp+57h+var_88], r13
0x180004118  mov     word ptr [rbp+57h+S1], r15w
0x18000411d  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x180004121  mov     [rbp+57h+var_B0], r15
0x180004125  mov     [rbp+57h+var_A8], r13
0x180004129  mov     word ptr [rbp+57h+pbData], r15w
0x18000412e  lea     esi, [r15+1]
0x180004132  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004139  jz      short loc_180004153
0x18000413b  lea     rax, [rbp+57h+var_60]
0x18000413f  mov     [rsp+100h+var_E0], rax
0x180004144  mov     r9d, esi
0x180004147  lea     rdx, MDMCOMMON_MOBILE_NETWORKS_CHANGED
0x18000414e  call    McGenEventWrite_EventWriteTransfer
0x180004153  test    rdi, rdi
0x180004156  jnz     short loc_180004193
0x180004158  mov     r8d, 80070057h
0x18000415e  mov     ebx, r8d
0x180004161  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180004168  jz      loc_180004329
0x18000416e  lea     rax, aCprPmobilenetw; "CPR(pMobileNetworks)"
0x180004175  mov     [rsp+100h+var_D8], rax
0x18000417a  mov     dword ptr [rsp+100h+var_E0], 28Ah
0x180004182  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004189  call    McTemplateU0dsqs_EventWriteTransfer
0x18000418e  jmp     loc_180004329
0x180004193  test    r14, r14
0x180004196  jnz     short loc_1800041C4
0x180004198  mov     r8d, 80070057h
0x18000419e  mov     ebx, r8d
0x1800041a1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800041a8  jz      loc_180004329
0x1800041ae  lea     rax, aCprPfchanged; "CPR(pfChanged)"
0x1800041b5  mov     [rsp+100h+var_D8], rax
0x1800041ba  mov     dword ptr [rsp+100h+var_E0], 28Bh
0x1800041c2  jmp     short loc_180004182
0x1800041c4  lea     rdx, [rbp+57h+S2]
0x1800041c8  mov     ecx, ebx
0x1800041ca  call    ?GetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetMobileNetworksHash(MdmDeviceContext,std::wstring &)
0x1800041cf  mov     ebx, eax
0x1800041d1  test    eax, eax
0x1800041d3  jns     short loc_1800041FB
0x1800041d5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800041dc  jz      loc_180004329
0x1800041e2  lea     rax, aChrMdmsettings_22; "CHR(MdmSettings::GetMobileNetworksHash("...
0x1800041e9  mov     [rsp+100h+var_D8], rax
0x1800041ee  mov     dword ptr [rsp+100h+var_E0], 28Eh
0x1800041f6  mov     r8d, ebx
0x1800041f9  jmp     short loc_180004182
0x1800041fb  mov     rax, [rdi]
0x1800041fe  mov     rbx, [rax+38h]
0x180004202  mov     rcx, [rbp+57h+string]; string
0x180004206  call    cs:__imp_WindowsDeleteString
0x18000420c  mov     [rbp+57h+string], r15
0x180004210  lea     rdx, [rbp+57h+string]
0x180004214  mov     rcx, rdi
0x180004217  mov     rax, rbx
0x18000421a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421f  mov     ebx, eax
0x180004221  test    eax, eax
0x180004223  jns     short loc_180004248
0x180004225  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x18000422c  jz      loc_180004329
0x180004232  lea     rax, aChrPmobilenetw; "CHR(pMobileNetworks->Stringify(hstrMobi"...
0x180004239  mov     [rsp+100h+var_D8], rax
0x18000423e  mov     dword ptr [rsp+100h+var_E0], 291h
0x180004246  jmp     short loc_1800041F6
0x180004248  xor     edx, edx; length
0x18000424a  mov     rcx, [rbp+57h+string]; string
0x18000424e  call    cs:__imp_WindowsGetStringRawBuffer
0x180004254  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180004258  inc     rdx
0x18000425b  cmp     [rax+rdx*2], r15w
0x180004260  jnz     short loc_180004258
0x180004262  cmp     rdx, [rbp+57h+var_A8]
0x180004266  ja      short loc_180004292
0x180004268  lea     rdi, [rbp+57h+pbData]
0x18000426c  cmp     [rbp+57h+var_A8], r13
0x180004270  cmova   rdi, qword ptr [rbp+57h+pbData]
0x180004275  mov     [rbp+57h+var_B0], rdx
0x180004279  lea     rbx, [rdx+rdx]
0x18000427d  mov     r8, rbx; Size
0x180004280  mov     rdx, rax; Src
0x180004283  mov     rcx, rdi; void *
0x180004286  call    memmove_0
0x18000428b  mov     [rbx+rdi], r15w
0x180004290  jmp     short loc_18000429E
0x180004292  mov     r9, rax
0x180004295  lea     rcx, [rbp+57h+pbData]
0x180004299  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000429e  lea     rdx, [rbp+57h+S1]
0x1800042a2  lea     rcx, [rbp+57h+pbData]; pbData
0x1800042a6  call    ?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MdmCrypto::HashString(std::wstring &,std::wstring &)
0x1800042ab  mov     ebx, eax
0x1800042ad  test    eax, eax
0x1800042af  jns     short loc_1800042D3
0x1800042b1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800042b8  jz      short loc_180004329
0x1800042ba  lea     rax, aChrMdmcryptoHa_0; "CHR(MdmCrypto::HashString(wstrMobileNet"...
0x1800042c1  mov     [rsp+100h+var_D8], rax
0x1800042c6  mov     dword ptr [rsp+100h+var_E0], 295h
0x1800042ce  jmp     loc_1800041F6
0x1800042d3  mov     rdi, [rbp+57h+var_70]
0x1800042d7  lea     rdx, [rbp+57h+S2]
0x1800042db  cmp     [rbp+57h+var_68], r13
0x1800042df  cmova   rdx, [rbp+57h+S2]; S2
0x1800042e4  mov     rsi, [rbp+57h+N]
0x1800042e8  lea     rcx, [rbp+57h+S1]
0x1800042ec  cmp     [rbp+57h+var_88], r13
0x1800042f0  cmova   rcx, [rbp+57h+S1]; S1
0x1800042f5  mov     r8, rdi
0x1800042f8  cmp     rdi, rsi
0x1800042fb  cmovnb  r8, rsi; N
0x1800042ff  call    wmemcmp
0x180004304  mov     r8d, eax
0x180004307  test    eax, eax
0x180004309  jnz     short loc_18000431D
0x18000430b  cmp     rsi, rdi
0x18000430e  jnb     short loc_180004316
0x180004310  or      r8d, 0FFFFFFFFh
0x180004314  jmp     short loc_18000431D
0x180004316  mov     r8d, r15d
0x180004319  setnbe  r8b
0x18000431d  mov     eax, r15d
0x180004320  test    r8d, r8d
0x180004323  setnz   al
0x180004326  mov     [r14], eax
0x180004329  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004330  jz      short loc_180004361
0x180004332  mov     [rbp+57h+var_C8], ebx
0x180004335  lea     rax, [rbp+57h+var_C8]
0x180004339  mov     [rbp+57h+var_50], rax
0x18000433d  mov     [rbp+57h+var_48], 4
0x180004345  lea     rax, [rbp+57h+var_60]
0x180004349  mov     [rsp+100h+var_E0], rax
0x18000434e  mov     r9d, 2
0x180004354  lea     rdx, MDMCOMMON_MOBILE_NETWORKS_CHANGED_RESULT
0x18000435b  call    McGenEventWrite_EventWriteTransfer
0x180004360  nop
0x180004361  lea     rcx, [rbp+57h+pbData]
0x180004365  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000436a  nop
0x18000436b  lea     rcx, [rbp+57h+S1]
0x18000436f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004374  nop
0x180004375  lea     rcx, [rbp+57h+S2]
0x180004379  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000437e  nop
0x18000437f  mov     rcx, [rbp+57h+string]; string
0x180004383  call    cs:__imp_WindowsDeleteString
0x180004389  mov     eax, ebx
0x18000438b  mov     rcx, [rbp+57h+var_40]
0x18000438f  xor     rcx, rsp; StackCookie
0x180004392  call    __security_check_cookie
0x180004397  add     rsp, 0D0h
0x18000439e  pop     r15
0x1800043a0  pop     r14
0x1800043a2  pop     r13
0x1800043a4  pop     rdi
0x1800043a5  pop     rsi
0x1800043a6  pop     rbx
0x1800043a7  pop     rbp
0x1800043a8  retn
```
