# MdmProtectionStateChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,int *)

- ea: `0x1800050a0`
- end: `0x18000539c`
- name: `?MdmProtectionStateChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@PEAH@Z`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800028e4`
- `0x180002de8`
- `0x1800050a0`
- `0x180006560`
- `0x1800065c0`
- `0x180006734`
- `0x180008be0`
- `0x1800130b4`
- `0x18001dbfc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000536f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800051e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000536f`

## string_xrefs

- `0x180005162`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800051c2`: `CHR(MdmSettings::GetProtectionStateHash(eDeviceType, wstrProtectionStateHashFromRegistry))`

## pseudocode

```c
__int64 __fastcall MdmProtectionStateChanged(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // ebx
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
  ProtectionStateHash = MdmCrypto::HashString(pbData);
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
  std::wstring::~wstring(pbData);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(S2);
  WindowsDeleteString(string);
  return (unsigned int)ProtectionStateHash;
}

```

## disassembly

```asm
0x1800050a0  push    rbp
0x1800050a2  push    rbx
0x1800050a3  push    rsi
0x1800050a4  push    rdi
0x1800050a5  push    r13
0x1800050a7  push    r14
0x1800050a9  push    r15
0x1800050ab  lea     rbp, [rsp-27h]
0x1800050b0  sub     rsp, 0D0h
0x1800050b7  mov     rax, cs:__security_cookie
0x1800050be  xor     rax, rsp
0x1800050c1  mov     [rbp+57h+var_40], rax
0x1800050c5  mov     r14, r8
0x1800050c8  mov     rdi, rdx
0x1800050cb  mov     ebx, ecx
0x1800050cd  xor     r15d, r15d
0x1800050d0  mov     [rbp+57h+string], r15
0x1800050d4  xorps   xmm0, xmm0
0x1800050d7  movups  xmmword ptr [rbp+57h+S2], xmm0
0x1800050db  mov     [rbp+57h+var_70], r15
0x1800050df  lea     r13d, [r15+7]
0x1800050e3  mov     [rbp+57h+var_68], r13
0x1800050e7  mov     word ptr [rbp+57h+S2], r15w
0x1800050ec  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1800050f0  mov     [rbp+57h+N], r15
0x1800050f4  mov     [rbp+57h+var_88], r13
0x1800050f8  mov     word ptr [rbp+57h+S1], r15w
0x1800050fd  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x180005101  mov     [rbp+57h+var_B0], r15
0x180005105  mov     [rbp+57h+var_A8], r13
0x180005109  mov     word ptr [rbp+57h+pbData], r15w
0x18000510e  lea     esi, [r15+1]
0x180005112  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005119  jz      short loc_180005133
0x18000511b  lea     rax, [rbp+57h+var_60]
0x18000511f  mov     [rsp+100h+var_E0], rax
0x180005124  mov     r9d, esi
0x180005127  lea     rdx, MDMCOMMON_PROTECTION_STATE_CHANGED
0x18000512e  call    McGenEventWrite_EventWriteTransfer
0x180005133  test    rdi, rdi
0x180005136  jnz     short loc_180005173
0x180005138  mov     r8d, 80070057h
0x18000513e  mov     ebx, r8d
0x180005141  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005148  jz      loc_180005315
0x18000514e  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x180005155  mov     [rsp+100h+var_D8], rax
0x18000515a  mov     dword ptr [rsp+100h+var_E0], 2AFh
0x180005162  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005169  call    McTemplateU0dsqs_EventWriteTransfer
0x18000516e  jmp     loc_180005315
0x180005173  test    r14, r14
0x180005176  jnz     short loc_1800051A4
0x180005178  mov     r8d, 80070057h
0x18000517e  mov     ebx, r8d
0x180005181  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005188  jz      loc_180005315
0x18000518e  lea     rax, aCprPfchanged; "CPR(pfChanged)"
0x180005195  mov     [rsp+100h+var_D8], rax
0x18000519a  mov     dword ptr [rsp+100h+var_E0], 2B0h
0x1800051a2  jmp     short loc_180005162
0x1800051a4  lea     rdx, [rbp+57h+S2]
0x1800051a8  mov     ecx, ebx
0x1800051aa  call    ?GetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetProtectionStateHash(MdmDeviceContext,std::wstring &)
0x1800051af  mov     ebx, eax
0x1800051b1  test    eax, eax
0x1800051b3  jns     short loc_1800051DB
0x1800051b5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800051bc  jz      loc_180005315
0x1800051c2  lea     rax, aChrMdmsettings_14; "CHR(MdmSettings::GetProtectionStateHash"...
0x1800051c9  mov     [rsp+100h+var_D8], rax
0x1800051ce  mov     dword ptr [rsp+100h+var_E0], 2B3h
0x1800051d6  mov     r8d, ebx
0x1800051d9  jmp     short loc_180005162
0x1800051db  mov     rax, [rdi]
0x1800051de  mov     rbx, [rax+38h]
0x1800051e2  mov     rcx, [rbp+57h+string]; string
0x1800051e6  call    cs:__imp_WindowsDeleteString
0x1800051ed  nop     dword ptr [rax+rax+00h]
0x1800051f2  mov     [rbp+57h+string], r15
0x1800051f6  lea     rdx, [rbp+57h+string]
0x1800051fa  mov     rcx, rdi
0x1800051fd  mov     rax, rbx
0x180005200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005205  mov     ebx, eax
0x180005207  test    eax, eax
0x180005209  jns     short loc_18000522E
0x18000520b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180005212  jz      loc_180005315
0x180005218  lea     rax, aChrPprotection; "CHR(pProtectionState->Stringify(hstrPro"...
0x18000521f  mov     [rsp+100h+var_D8], rax
0x180005224  mov     dword ptr [rsp+100h+var_E0], 2B6h
0x18000522c  jmp     short loc_1800051D6
0x18000522e  xor     edx, edx; length
0x180005230  mov     rcx, [rbp+57h+string]; string
0x180005234  call    cs:__imp_WindowsGetStringRawBuffer
0x18000523b  nop     dword ptr [rax+rax+00h]
0x180005240  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005244  inc     rdx
0x180005247  cmp     [rax+rdx*2], r15w
0x18000524c  jnz     short loc_180005244
0x18000524e  cmp     rdx, [rbp+57h+var_A8]
0x180005252  ja      short loc_18000527E
0x180005254  lea     rdi, [rbp+57h+pbData]
0x180005258  cmp     [rbp+57h+var_A8], r13
0x18000525c  cmova   rdi, qword ptr [rbp+57h+pbData]
0x180005261  mov     [rbp+57h+var_B0], rdx
0x180005265  lea     rbx, [rdx+rdx]
0x180005269  mov     r8, rbx; Size
0x18000526c  mov     rdx, rax; Src
0x18000526f  mov     rcx, rdi; void *
0x180005272  call    memmove_0
0x180005277  mov     [rbx+rdi], r15w
0x18000527c  jmp     short loc_18000528A
0x18000527e  mov     r9, rax
0x180005281  lea     rcx, [rbp+57h+pbData]
0x180005285  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000528a  lea     rdx, [rbp+57h+S1]
0x18000528e  lea     rcx, [rbp+57h+pbData]; pbData
0x180005292  call    ?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MdmCrypto::HashString(std::wstring &,std::wstring &)
0x180005297  mov     ebx, eax
0x180005299  test    eax, eax
0x18000529b  jns     short loc_1800052BF
0x18000529d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x1800052a4  jz      short loc_180005315
0x1800052a6  lea     rax, aChrMdmcryptoHa_3; "CHR(MdmCrypto::HashString(wstrProtectio"...
0x1800052ad  mov     [rsp+100h+var_D8], rax
0x1800052b2  mov     dword ptr [rsp+100h+var_E0], 2BAh
0x1800052ba  jmp     loc_1800051D6
0x1800052bf  mov     rdi, [rbp+57h+var_70]
0x1800052c3  lea     rdx, [rbp+57h+S2]
0x1800052c7  cmp     [rbp+57h+var_68], r13
0x1800052cb  cmova   rdx, [rbp+57h+S2]; S2
0x1800052d0  mov     rsi, [rbp+57h+N]
0x1800052d4  lea     rcx, [rbp+57h+S1]
0x1800052d8  cmp     [rbp+57h+var_88], r13
0x1800052dc  cmova   rcx, [rbp+57h+S1]; S1
0x1800052e1  mov     r8, rdi
0x1800052e4  cmp     rdi, rsi
0x1800052e7  cmovnb  r8, rsi; N
0x1800052eb  call    wmemcmp
0x1800052f0  mov     r8d, eax
0x1800052f3  test    eax, eax
0x1800052f5  jnz     short loc_180005309
0x1800052f7  cmp     rsi, rdi
0x1800052fa  jnb     short loc_180005302
0x1800052fc  or      r8d, 0FFFFFFFFh
0x180005300  jmp     short loc_180005309
0x180005302  mov     r8d, r15d
0x180005305  setnbe  r8b
0x180005309  mov     eax, r15d
0x18000530c  test    r8d, r8d
0x18000530f  setnz   al
0x180005312  mov     [r14], eax
0x180005315  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000531c  jz      short loc_18000534D
0x18000531e  mov     [rbp+57h+var_C8], ebx
0x180005321  lea     rax, [rbp+57h+var_C8]
0x180005325  mov     [rbp+57h+var_50], rax
0x180005329  mov     [rbp+57h+var_48], 4
0x180005331  lea     rax, [rbp+57h+var_60]
0x180005335  mov     [rsp+100h+var_E0], rax
0x18000533a  mov     r9d, 2
0x180005340  lea     rdx, MDMCOMMON_PROTECTION_STATE_CHANGED_RESULT
0x180005347  call    McGenEventWrite_EventWriteTransfer
0x18000534c  nop
0x18000534d  lea     rcx, [rbp+57h+pbData]
0x180005351  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005356  nop
0x180005357  lea     rcx, [rbp+57h+S1]
0x18000535b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005360  nop
0x180005361  lea     rcx, [rbp+57h+S2]
0x180005365  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000536a  nop
0x18000536b  mov     rcx, [rbp+57h+string]; string
0x18000536f  call    cs:__imp_WindowsDeleteString
0x180005376  nop     dword ptr [rax+rax+00h]
0x18000537b  mov     eax, ebx
0x18000537d  mov     rcx, [rbp+57h+var_40]
0x180005381  xor     rcx, rsp; StackCookie
0x180005384  call    __security_check_cookie
0x180005389  add     rsp, 0D0h
0x180005390  pop     r15
0x180005392  pop     r14
0x180005394  pop     r13
0x180005396  pop     rdi
0x180005397  pop     rsi
0x180005398  pop     rbx
0x180005399  pop     rbp
0x18000539a  retn
```
