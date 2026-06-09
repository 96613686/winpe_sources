# MdmMobileNetworksChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,int *)

- ea: `0x1800040d0`
- end: `0x1800043cc`
- name: `?MdmMobileNetworksChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@PEAH@Z`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de8`
- `0x1800040d0`
- `0x180006560`
- `0x1800065c0`
- `0x180006734`
- `0x180008be0`
- `0x180012e08`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000439f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000439f`

## string_xrefs

- `0x180004192`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800041f2`: `CHR(MdmSettings::GetMobileNetworksHash(eDeviceType, wstrMobileNetworksHashFromRegistry))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmMobileNetworksChanged(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // ebx
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
      pbData,
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
  MobileNetworksHash = MdmCrypto::HashString(pbData);
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
  std::wstring::~wstring(pbData);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(S2);
  WindowsDeleteString(string);
  return (unsigned int)MobileNetworksHash;
}

```

## disassembly

```asm
0x1800040d0  push    rbp
0x1800040d2  push    rbx
0x1800040d3  push    rsi
0x1800040d4  push    rdi
0x1800040d5  push    r13
0x1800040d7  push    r14
0x1800040d9  push    r15
0x1800040db  lea     rbp, [rsp-27h]
0x1800040e0  sub     rsp, 0D0h
0x1800040e7  mov     rax, cs:__security_cookie
0x1800040ee  xor     rax, rsp
0x1800040f1  mov     [rbp+57h+var_40], rax
0x1800040f5  mov     r14, r8
0x1800040f8  mov     rdi, rdx
0x1800040fb  mov     ebx, ecx
0x1800040fd  xor     r15d, r15d
0x180004100  mov     [rbp+57h+string], r15
0x180004104  xorps   xmm0, xmm0
0x180004107  movups  xmmword ptr [rbp+57h+S2], xmm0
0x18000410b  mov     [rbp+57h+var_70], r15
0x18000410f  lea     r13d, [r15+7]
0x180004113  mov     [rbp+57h+var_68], r13
0x180004117  mov     word ptr [rbp+57h+S2], r15w
0x18000411c  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180004120  mov     [rbp+57h+N], r15
0x180004124  mov     [rbp+57h+var_88], r13
0x180004128  mov     word ptr [rbp+57h+S1], r15w
0x18000412d  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x180004131  mov     [rbp+57h+var_B0], r15
0x180004135  mov     [rbp+57h+var_A8], r13
0x180004139  mov     word ptr [rbp+57h+pbData], r15w
0x18000413e  lea     esi, [r15+1]
0x180004142  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004149  jz      short loc_180004163
0x18000414b  lea     rax, [rbp+57h+var_60]
0x18000414f  mov     [rsp+100h+var_E0], rax
0x180004154  mov     r9d, esi
0x180004157  lea     rdx, MDMCOMMON_MOBILE_NETWORKS_CHANGED
0x18000415e  call    McGenEventWrite_EventWriteTransfer
0x180004163  test    rdi, rdi
0x180004166  jnz     short loc_1800041A3
0x180004168  mov     r8d, 80070057h
0x18000416e  mov     ebx, r8d
0x180004171  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180004178  jz      loc_180004345
0x18000417e  lea     rax, aCprPmobilenetw; "CPR(pMobileNetworks)"
0x180004185  mov     [rsp+100h+var_D8], rax
0x18000418a  mov     dword ptr [rsp+100h+var_E0], 28Ah
0x180004192  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004199  call    McTemplateU0dsqs_EventWriteTransfer
0x18000419e  jmp     loc_180004345
0x1800041a3  test    r14, r14
0x1800041a6  jnz     short loc_1800041D4
0x1800041a8  mov     r8d, 80070057h
0x1800041ae  mov     ebx, r8d
0x1800041b1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800041b8  jz      loc_180004345
0x1800041be  lea     rax, aCprPfchanged; "CPR(pfChanged)"
0x1800041c5  mov     [rsp+100h+var_D8], rax
0x1800041ca  mov     dword ptr [rsp+100h+var_E0], 28Bh
0x1800041d2  jmp     short loc_180004192
0x1800041d4  lea     rdx, [rbp+57h+S2]
0x1800041d8  mov     ecx, ebx
0x1800041da  call    ?GetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetMobileNetworksHash(MdmDeviceContext,std::wstring &)
0x1800041df  mov     ebx, eax
0x1800041e1  test    eax, eax
0x1800041e3  jns     short loc_18000420B
0x1800041e5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800041ec  jz      loc_180004345
0x1800041f2  lea     rax, aChrMdmsettings_22; "CHR(MdmSettings::GetMobileNetworksHash("...
0x1800041f9  mov     [rsp+100h+var_D8], rax
0x1800041fe  mov     dword ptr [rsp+100h+var_E0], 28Eh
0x180004206  mov     r8d, ebx
0x180004209  jmp     short loc_180004192
0x18000420b  mov     rax, [rdi]
0x18000420e  mov     rbx, [rax+38h]
0x180004212  mov     rcx, [rbp+57h+string]; string
0x180004216  call    cs:__imp_WindowsDeleteString
0x18000421d  nop     dword ptr [rax+rax+00h]
0x180004222  mov     [rbp+57h+string], r15
0x180004226  lea     rdx, [rbp+57h+string]
0x18000422a  mov     rcx, rdi
0x18000422d  mov     rax, rbx
0x180004230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004235  mov     ebx, eax
0x180004237  test    eax, eax
0x180004239  jns     short loc_18000425E
0x18000423b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180004242  jz      loc_180004345
0x180004248  lea     rax, aChrPmobilenetw; "CHR(pMobileNetworks->Stringify(hstrMobi"...
0x18000424f  mov     [rsp+100h+var_D8], rax
0x180004254  mov     dword ptr [rsp+100h+var_E0], 291h
0x18000425c  jmp     short loc_180004206
0x18000425e  xor     edx, edx; length
0x180004260  mov     rcx, [rbp+57h+string]; string
0x180004264  call    cs:__imp_WindowsGetStringRawBuffer
0x18000426b  nop     dword ptr [rax+rax+00h]
0x180004270  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180004274  inc     rdx
0x180004277  cmp     [rax+rdx*2], r15w
0x18000427c  jnz     short loc_180004274
0x18000427e  cmp     rdx, [rbp+57h+var_A8]
0x180004282  ja      short loc_1800042AE
0x180004284  lea     rdi, [rbp+57h+pbData]
0x180004288  cmp     [rbp+57h+var_A8], r13
0x18000428c  cmova   rdi, qword ptr [rbp+57h+pbData]
0x180004291  mov     [rbp+57h+var_B0], rdx
0x180004295  lea     rbx, [rdx+rdx]
0x180004299  mov     r8, rbx; Size
0x18000429c  mov     rdx, rax; Src
0x18000429f  mov     rcx, rdi; void *
0x1800042a2  call    memmove_0
0x1800042a7  mov     [rbx+rdi], r15w
0x1800042ac  jmp     short loc_1800042BA
0x1800042ae  mov     r9, rax
0x1800042b1  lea     rcx, [rbp+57h+pbData]
0x1800042b5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800042ba  lea     rdx, [rbp+57h+S1]
0x1800042be  lea     rcx, [rbp+57h+pbData]; pbData
0x1800042c2  call    ?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MdmCrypto::HashString(std::wstring &,std::wstring &)
0x1800042c7  mov     ebx, eax
0x1800042c9  test    eax, eax
0x1800042cb  jns     short loc_1800042EF
0x1800042cd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800042d4  jz      short loc_180004345
0x1800042d6  lea     rax, aChrMdmcryptoHa_0; "CHR(MdmCrypto::HashString(wstrMobileNet"...
0x1800042dd  mov     [rsp+100h+var_D8], rax
0x1800042e2  mov     dword ptr [rsp+100h+var_E0], 295h
0x1800042ea  jmp     loc_180004206
0x1800042ef  mov     rdi, [rbp+57h+var_70]
0x1800042f3  lea     rdx, [rbp+57h+S2]
0x1800042f7  cmp     [rbp+57h+var_68], r13
0x1800042fb  cmova   rdx, [rbp+57h+S2]; S2
0x180004300  mov     rsi, [rbp+57h+N]
0x180004304  lea     rcx, [rbp+57h+S1]
0x180004308  cmp     [rbp+57h+var_88], r13
0x18000430c  cmova   rcx, [rbp+57h+S1]; S1
0x180004311  mov     r8, rdi
0x180004314  cmp     rdi, rsi
0x180004317  cmovnb  r8, rsi; N
0x18000431b  call    wmemcmp
0x180004320  mov     r8d, eax
0x180004323  test    eax, eax
0x180004325  jnz     short loc_180004339
0x180004327  cmp     rsi, rdi
0x18000432a  jnb     short loc_180004332
0x18000432c  or      r8d, 0FFFFFFFFh
0x180004330  jmp     short loc_180004339
0x180004332  mov     r8d, r15d
0x180004335  setnbe  r8b
0x180004339  mov     eax, r15d
0x18000433c  test    r8d, r8d
0x18000433f  setnz   al
0x180004342  mov     [r14], eax
0x180004345  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000434c  jz      short loc_18000437D
0x18000434e  mov     [rbp+57h+var_C8], ebx
0x180004351  lea     rax, [rbp+57h+var_C8]
0x180004355  mov     [rbp+57h+var_50], rax
0x180004359  mov     [rbp+57h+var_48], 4
0x180004361  lea     rax, [rbp+57h+var_60]
0x180004365  mov     [rsp+100h+var_E0], rax
0x18000436a  mov     r9d, 2
0x180004370  lea     rdx, MDMCOMMON_MOBILE_NETWORKS_CHANGED_RESULT
0x180004377  call    McGenEventWrite_EventWriteTransfer
0x18000437c  nop
0x18000437d  lea     rcx, [rbp+57h+pbData]
0x180004381  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004386  nop
0x180004387  lea     rcx, [rbp+57h+S1]
0x18000438b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004390  nop
0x180004391  lea     rcx, [rbp+57h+S2]
0x180004395  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000439a  nop
0x18000439b  mov     rcx, [rbp+57h+string]; string
0x18000439f  call    cs:__imp_WindowsDeleteString
0x1800043a6  nop     dword ptr [rax+rax+00h]
0x1800043ab  mov     eax, ebx
0x1800043ad  mov     rcx, [rbp+57h+var_40]
0x1800043b1  xor     rcx, rsp; StackCookie
0x1800043b4  call    __security_check_cookie
0x1800043b9  add     rsp, 0D0h
0x1800043c0  pop     r15
0x1800043c2  pop     r14
0x1800043c4  pop     r13
0x1800043c6  pop     rdi
0x1800043c7  pop     rsi
0x1800043c8  pop     rbx
0x1800043c9  pop     rbp
0x1800043ca  retn
```
