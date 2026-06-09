# MdmProtectionStateChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,int *)

- ea: `0x180005070`
- end: `0x180005359`
- name: `?MdmProtectionStateChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@PEAH@Z`
- size: `745`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de4`
- `0x180005070`
- `0x1800064f0`
- `0x180006548`
- `0x1800066b0`
- `0x180008a6c`
- `0x180012cd0`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800051fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800051fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005333`

## string_xrefs

- `0x180005132`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005192`: `CHR(MdmSettings::GetProtectionStateHash(eDeviceType, wstrProtectionStateHashFromRegistry))`

## pseudocode

```c
__int64 __fastcall MdmProtectionStateChanged(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // ebx
  __int64 v6; // r8
  int ProtectionStateHash; // ebx
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
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_PROTECTION_STATE_CHANGED, a3, 1, v34);
  if ( !a2 )
  {
    v6 = 2147942487LL;
    ProtectionStateHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CPR(pProtectionState)";
    v21 = -81;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v6 = 2147942487LL;
    ProtectionStateHash = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        176,
        "CPR(pfChanged)");
    goto LABEL_39;
  }
  ProtectionStateHash = MdmSettings::GetProtectionStateHash(v5, S2);
  if ( ProtectionStateHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(MdmSettings::GetProtectionStateHash(eDeviceType, wstrProtectionStateHashFromRegistry))";
    v21 = -77;
LABEL_14:
    LODWORD(v6) = ProtectionStateHash;
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
  ProtectionStateHash = v8(a2, &string);
  if ( ProtectionStateHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(pProtectionState->Stringify(hstrProtectionState.GetAddressOf()))";
    v21 = -74;
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
  ProtectionStateHash = MdmCrypto::HashString(pbData, S1);
  if ( ProtectionStateHash < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_39;
    v22 = "CHR(MdmCrypto::HashString(wstrProtectionState, wstrProtectionStateNewHash))";
    v21 = -70;
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
    v24 = ProtectionStateHash;
    v35 = &v24;
    v36 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_PROTECTION_STATE_CHANGED_RESULT, v6, 2, v34);
  }
  std::wstring::~wstring((char **)pbData);
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring((char **)S2);
  WindowsDeleteString(string);
  return (unsigned int)ProtectionStateHash;
}

```

## disassembly

```asm
0x180005070  push    rbp
0x180005072  push    rbx
0x180005073  push    rsi
0x180005074  push    rdi
0x180005075  push    r13
0x180005077  push    r14
0x180005079  push    r15
0x18000507b  lea     rbp, [rsp-27h]
0x180005080  sub     rsp, 0D0h
0x180005087  mov     rax, cs:__security_cookie
0x18000508e  xor     rax, rsp
0x180005091  mov     [rbp+57h+var_40], rax
0x180005095  mov     r14, r8
0x180005098  mov     rdi, rdx
0x18000509b  mov     ebx, ecx
0x18000509d  xor     r15d, r15d
0x1800050a0  mov     [rbp+57h+string], r15
0x1800050a4  xorps   xmm0, xmm0
0x1800050a7  movups  xmmword ptr [rbp+57h+S2], xmm0
0x1800050ab  mov     [rbp+57h+var_70], r15
0x1800050af  lea     r13d, [r15+7]
0x1800050b3  mov     [rbp+57h+var_68], r13
0x1800050b7  mov     word ptr [rbp+57h+S2], r15w
0x1800050bc  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1800050c0  mov     [rbp+57h+N], r15
0x1800050c4  mov     [rbp+57h+var_88], r13
0x1800050c8  mov     word ptr [rbp+57h+S1], r15w
0x1800050cd  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x1800050d1  mov     [rbp+57h+var_B0], r15
0x1800050d5  mov     [rbp+57h+var_A8], r13
0x1800050d9  mov     word ptr [rbp+57h+pbData], r15w
0x1800050de  lea     esi, [r15+1]
0x1800050e2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800050e9  jz      short loc_180005103
0x1800050eb  lea     rax, [rbp+57h+var_60]
0x1800050ef  mov     [rsp+100h+var_E0], rax
0x1800050f4  mov     r9d, esi
0x1800050f7  lea     rdx, MDMCOMMON_PROTECTION_STATE_CHANGED
0x1800050fe  call    McGenEventWrite_EventWriteTransfer
0x180005103  test    rdi, rdi
0x180005106  jnz     short loc_180005143
0x180005108  mov     r8d, 80070057h
0x18000510e  mov     ebx, r8d
0x180005111  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005118  jz      loc_1800052D9
0x18000511e  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x180005125  mov     [rsp+100h+var_D8], rax
0x18000512a  mov     dword ptr [rsp+100h+var_E0], 2AFh
0x180005132  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005139  call    McTemplateU0dsqs_EventWriteTransfer
0x18000513e  jmp     loc_1800052D9
0x180005143  test    r14, r14
0x180005146  jnz     short loc_180005174
0x180005148  mov     r8d, 80070057h
0x18000514e  mov     ebx, r8d
0x180005151  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005158  jz      loc_1800052D9
0x18000515e  lea     rax, aCprPfchanged; "CPR(pfChanged)"
0x180005165  mov     [rsp+100h+var_D8], rax
0x18000516a  mov     dword ptr [rsp+100h+var_E0], 2B0h
0x180005172  jmp     short loc_180005132
0x180005174  lea     rdx, [rbp+57h+S2]
0x180005178  mov     ecx, ebx
0x18000517a  call    ?GetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetProtectionStateHash(MdmDeviceContext,std::wstring &)
0x18000517f  mov     ebx, eax
0x180005181  test    eax, eax
0x180005183  jns     short loc_1800051AB
0x180005185  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x18000518c  jz      loc_1800052D9
0x180005192  lea     rax, aChrMdmsettings_14; "CHR(MdmSettings::GetProtectionStateHash"...
0x180005199  mov     [rsp+100h+var_D8], rax
0x18000519e  mov     dword ptr [rsp+100h+var_E0], 2B3h
0x1800051a6  mov     r8d, ebx
0x1800051a9  jmp     short loc_180005132
0x1800051ab  mov     rax, [rdi]
0x1800051ae  mov     rbx, [rax+38h]
0x1800051b2  mov     rcx, [rbp+57h+string]; string
0x1800051b6  call    cs:__imp_WindowsDeleteString
0x1800051bc  mov     [rbp+57h+string], r15
0x1800051c0  lea     rdx, [rbp+57h+string]
0x1800051c4  mov     rcx, rdi
0x1800051c7  mov     rax, rbx
0x1800051ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051cf  mov     ebx, eax
0x1800051d1  test    eax, eax
0x1800051d3  jns     short loc_1800051F8
0x1800051d5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800051dc  jz      loc_1800052D9
0x1800051e2  lea     rax, aChrPprotection; "CHR(pProtectionState->Stringify(hstrPro"...
0x1800051e9  mov     [rsp+100h+var_D8], rax
0x1800051ee  mov     dword ptr [rsp+100h+var_E0], 2B6h
0x1800051f6  jmp     short loc_1800051A6
0x1800051f8  xor     edx, edx; length
0x1800051fa  mov     rcx, [rbp+57h+string]; string
0x1800051fe  call    cs:__imp_WindowsGetStringRawBuffer
0x180005204  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005208  inc     rdx
0x18000520b  cmp     [rax+rdx*2], r15w
0x180005210  jnz     short loc_180005208
0x180005212  cmp     rdx, [rbp+57h+var_A8]
0x180005216  ja      short loc_180005242
0x180005218  lea     rdi, [rbp+57h+pbData]
0x18000521c  cmp     [rbp+57h+var_A8], r13
0x180005220  cmova   rdi, qword ptr [rbp+57h+pbData]
0x180005225  mov     [rbp+57h+var_B0], rdx
0x180005229  lea     rbx, [rdx+rdx]
0x18000522d  mov     r8, rbx; Size
0x180005230  mov     rdx, rax; Src
0x180005233  mov     rcx, rdi; void *
0x180005236  call    memmove_0
0x18000523b  mov     [rbx+rdi], r15w
0x180005240  jmp     short loc_18000524E
0x180005242  mov     r9, rax
0x180005245  lea     rcx, [rbp+57h+pbData]
0x180005249  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000524e  lea     rdx, [rbp+57h+S1]
0x180005252  lea     rcx, [rbp+57h+pbData]; pbData
0x180005256  call    ?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MdmCrypto::HashString(std::wstring &,std::wstring &)
0x18000525b  mov     ebx, eax
0x18000525d  test    eax, eax
0x18000525f  jns     short loc_180005283
0x180005261  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005268  jz      short loc_1800052D9
0x18000526a  lea     rax, aChrMdmcryptoHa_3; "CHR(MdmCrypto::HashString(wstrProtectio"...
0x180005271  mov     [rsp+100h+var_D8], rax
0x180005276  mov     dword ptr [rsp+100h+var_E0], 2BAh
0x18000527e  jmp     loc_1800051A6
0x180005283  mov     rdi, [rbp+57h+var_70]
0x180005287  lea     rdx, [rbp+57h+S2]
0x18000528b  cmp     [rbp+57h+var_68], r13
0x18000528f  cmova   rdx, [rbp+57h+S2]; S2
0x180005294  mov     rsi, [rbp+57h+N]
0x180005298  lea     rcx, [rbp+57h+S1]
0x18000529c  cmp     [rbp+57h+var_88], r13
0x1800052a0  cmova   rcx, [rbp+57h+S1]; S1
0x1800052a5  mov     r8, rdi
0x1800052a8  cmp     rdi, rsi
0x1800052ab  cmovnb  r8, rsi; N
0x1800052af  call    wmemcmp
0x1800052b4  mov     r8d, eax
0x1800052b7  test    eax, eax
0x1800052b9  jnz     short loc_1800052CD
0x1800052bb  cmp     rsi, rdi
0x1800052be  jnb     short loc_1800052C6
0x1800052c0  or      r8d, 0FFFFFFFFh
0x1800052c4  jmp     short loc_1800052CD
0x1800052c6  mov     r8d, r15d
0x1800052c9  setnbe  r8b
0x1800052cd  mov     eax, r15d
0x1800052d0  test    r8d, r8d
0x1800052d3  setnz   al
0x1800052d6  mov     [r14], eax
0x1800052d9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800052e0  jz      short loc_180005311
0x1800052e2  mov     [rbp+57h+var_C8], ebx
0x1800052e5  lea     rax, [rbp+57h+var_C8]
0x1800052e9  mov     [rbp+57h+var_50], rax
0x1800052ed  mov     [rbp+57h+var_48], 4
0x1800052f5  lea     rax, [rbp+57h+var_60]
0x1800052f9  mov     [rsp+100h+var_E0], rax
0x1800052fe  mov     r9d, 2
0x180005304  lea     rdx, MDMCOMMON_PROTECTION_STATE_CHANGED_RESULT
0x18000530b  call    McGenEventWrite_EventWriteTransfer
0x180005310  nop
0x180005311  lea     rcx, [rbp+57h+pbData]
0x180005315  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000531a  nop
0x18000531b  lea     rcx, [rbp+57h+S1]
0x18000531f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005324  nop
0x180005325  lea     rcx, [rbp+57h+S2]
0x180005329  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000532e  nop
0x18000532f  mov     rcx, [rbp+57h+string]; string
0x180005333  call    cs:__imp_WindowsDeleteString
0x180005339  mov     eax, ebx
0x18000533b  mov     rcx, [rbp+57h+var_40]
0x18000533f  xor     rcx, rsp; StackCookie
0x180005342  call    __security_check_cookie
0x180005347  add     rsp, 0D0h
0x18000534e  pop     r15
0x180005350  pop     r14
0x180005352  pop     r13
0x180005354  pop     rdi
0x180005355  pop     rsi
0x180005356  pop     rbx
0x180005357  pop     rbp
0x180005358  retn
```
