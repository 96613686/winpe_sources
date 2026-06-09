# Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(ulong,bool &)

- ea: `0x1800197f4`
- end: `0x180019acc`
- name: `?CheckIfHardwareChanged@HardwareInfo@Autopilot@Windows@Microsoft@@SAJKAEA_N@Z`
- size: `728`
- prototype: `__int64 __fastcall(int, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ba54`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800132d8`
- `0x180013a40`
- `0x180013be0`
- `0x1800174f0`
- `0x1800197f4`
- `0x18001b938`
- `0x18001c234`
- `0x18001ca58`
- `0x18001d0d8`
- `0x18002e010`

## string_xrefs

- `0x180019a6a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019aaa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(int a1, bool *a2)
{
  __int64 *v4; // rbx
  int v5; // eax
  unsigned int StringFromStorage; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // edi
  __int64 v13; // rcx
  size_t v14; // rdi
  const wchar_t *v15; // rdx
  size_t v16; // rsi
  const wchar_t *v17; // rcx
  size_t v18; // r8
  __int128 *v20; // [rsp+20h] [rbp-59h]
  wchar_t *S2[2]; // [rsp+28h] [rbp-51h] BYREF
  size_t v22; // [rsp+38h] [rbp-41h]
  unsigned __int64 v23; // [rsp+40h] [rbp-39h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-31h] BYREF
  size_t N; // [rsp+58h] [rbp-21h]
  unsigned __int64 v26; // [rsp+60h] [rbp-19h]
  __int128 v27; // [rsp+68h] [rbp-11h] BYREF
  __int128 v28; // [rsp+78h] [rbp-1h]
  _OWORD v29[2]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v4 = &qword_1800300C0;
  while ( (a1 & *(_DWORD *)v4) == *(_DWORD *)v4 )
  {
LABEL_25:
    v4 += 4;
    if ( v4 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  *(_OWORD *)S2 = 0;
  v22 = 0;
  v23 = 7;
  LOWORD(S2[0]) = 0;
  v5 = ((__int64 (__fastcall *)(wchar_t **))v4[2])(S2);
  StringFromStorage = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      (int)v20);
    goto LABEL_32;
  }
  *(_OWORD *)S1 = 0;
  N = 0;
  v26 = 7;
  LOWORD(S1[0]) = 0;
  v7 = v4[1];
  v27 = 0;
  v28 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v7 + 2 * v8) );
  std::wstring::_Construct<1,unsigned short const *>(&v27, v7, v8);
  StringFromStorage = Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(
                        *((_DWORD *)v4 + 1),
                        (const WCHAR *)&v27,
                        (__int64)S1);
  std::wstring::_Tidy_deallocate(&v27);
  if ( (StringFromStorage & 0x80000000) == 0 )
  {
    if ( *((_BYTE *)v4 + 24) )
    {
      v14 = v22;
      v15 = (const wchar_t *)S2;
      if ( v23 > 7 )
        v15 = S2[0];
      v16 = N;
      v17 = (const wchar_t *)S1;
      if ( v26 > 7 )
        v17 = S1[0];
      v18 = v22;
      if ( v22 >= N )
        v18 = N;
      if ( wmemcmp(v17, v15, v18) || v16 < v14 || v16 > v14 )
      {
        *a2 = 1;
        std::wstring::_Tidy_deallocate(S1);
        std::wstring::_Tidy_deallocate(S2);
        return 0;
      }
    }
    goto LABEL_24;
  }
  v9 = StringFromStorage + 2147024894;
  if ( (unsigned int)v9 <= 1 )
  {
    v20 = &v27;
    v27 = 0;
    v28 = 0u;
    std::wstring::_Construct<2,unsigned short const *>(&v27);
    v10 = v4[1];
    memset(v29, 0, sizeof(v29));
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    std::wstring::_Construct<1,unsigned short const *>(v29, v10, v11);
    v12 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
            *((_DWORD *)v4 + 1),
            (__int64)v29,
            (const unsigned __int16 *)&v27);
    std::wstring::_Tidy_deallocate(v29);
    if ( v12 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(v13, AutopilotRestorationHardwareWriteFailure, (unsigned int)v12, v4[1], &v27);
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged",
        (const unsigned __int16 *)v4[1],
        v12);
    }
LABEL_24:
    std::wstring::_Tidy_deallocate(S1);
    std::wstring::_Tidy_deallocate(S2);
    goto LABEL_25;
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0dz_EventWriteTransfer(v9, AutopilotRestorationHardwareReadFailure, StringFromStorage, v4[1], v20);
  Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
    L"Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged",
    (const unsigned __int16 *)v4[1],
    StringFromStorage);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBE,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)StringFromStorage,
    (int)v20);
  std::wstring::_Tidy_deallocate(S1);
LABEL_32:
  std::wstring::_Tidy_deallocate(S2);
  return StringFromStorage;
}

```

## disassembly

```asm
0x1800197f4  mov     [rsp-8+arg_0], rbx
0x1800197f9  mov     [rsp-8+arg_10], rsi
0x1800197fe  push    rbp
0x1800197ff  push    rdi
0x180019800  push    r12
0x180019802  push    r14
0x180019804  push    r15
0x180019806  lea     rbp, [rsp-37h]
0x18001980b  sub     rsp, 0B0h
0x180019812  mov     rax, cs:__security_cookie
0x180019819  xor     rax, rsp
0x18001981c  mov     [rbp+57h+var_28], rax
0x180019820  mov     r14, rdx
0x180019823  mov     r15d, ecx
0x180019826  xor     r12d, r12d
0x180019829  mov     [rdx], r12b
0x18001982c  lea     rbx, qword_1800300C0
0x180019833  mov     eax, [rbx]
0x180019835  and     eax, r15d
0x180019838  cmp     eax, [rbx]
0x18001983a  jz      loc_1800199F6
0x180019840  xorps   xmm0, xmm0
0x180019843  movups  xmmword ptr [rbp+57h+S2], xmm0
0x180019847  mov     [rbp+57h+var_98], r12
0x18001984b  mov     [rbp+57h+var_90], 7
0x180019853  mov     word ptr [rbp+57h+S2], r12w
0x180019858  lea     rcx, [rbp+57h+S2]
0x18001985c  mov     rax, [rbx+10h]
0x180019860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019865  mov     edi, eax
0x180019867  test    eax, eax
0x180019869  js      loc_180019AA3
0x18001986f  xorps   xmm0, xmm0
0x180019872  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180019876  mov     [rbp+57h+N], r12
0x18001987a  mov     [rbp+57h+var_70], 7
0x180019882  mov     word ptr [rbp+57h+S1], r12w
0x180019887  mov     rdx, [rbx+8]
0x18001988b  movups  [rbp+57h+var_68], xmm0
0x18001988f  xorps   xmm1, xmm1
0x180019892  movdqu  [rbp+57h+var_58], xmm1
0x180019897  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001989b  inc     r8
0x18001989e  cmp     [rdx+r8*2], r12w
0x1800198a3  jnz     short loc_18001989B
0x1800198a5  lea     rcx, [rbp+57h+var_68]
0x1800198a9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800198ae  nop
0x1800198af  lea     r8, [rbp+57h+S1]
0x1800198b3  lea     rdx, [rbp+57h+var_68]
0x1800198b7  mov     ecx, [rbx+4]
0x1800198ba  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x1800198bf  mov     edi, eax
0x1800198c1  lea     rcx, [rbp+57h+var_68]
0x1800198c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198ca  test    edi, edi
0x1800198cc  jns     loc_180019993
0x1800198d2  lea     ecx, [rdi+7FF8FFFEh]
0x1800198d8  cmp     ecx, 1
0x1800198db  ja      loc_180019A34
0x1800198e1  lea     rax, [rbp+57h+var_68]
0x1800198e5  mov     [rbp+57h+var_B0], rax
0x1800198e9  xorps   xmm0, xmm0
0x1800198ec  movups  [rbp+57h+var_68], xmm0
0x1800198f0  mov     qword ptr [rbp+57h+var_58], r12
0x1800198f4  mov     qword ptr [rbp+57h+var_58+8], r12
0x1800198f8  lea     rdx, [rbp+57h+S2]
0x1800198fc  cmp     [rbp+57h+var_90], 7
0x180019901  cmova   rdx, [rbp+57h+S2]
0x180019906  mov     r8, [rbp+57h+var_98]
0x18001990a  lea     rcx, [rbp+57h+var_68]
0x18001990e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019913  nop
0x180019914  mov     rdx, [rbx+8]
0x180019918  xorps   xmm0, xmm0
0x18001991b  movups  [rbp+57h+var_48], xmm0
0x18001991f  xorps   xmm1, xmm1
0x180019922  movdqu  [rbp+57h+var_38], xmm1
0x180019927  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001992b  inc     r8
0x18001992e  cmp     [rdx+r8*2], r12w
0x180019933  jnz     short loc_18001992B
0x180019935  lea     rcx, [rbp+57h+var_48]
0x180019939  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001993e  nop
0x18001993f  lea     r8, [rbp+57h+var_68]
0x180019943  lea     rdx, [rbp+57h+var_48]
0x180019947  mov     ecx, [rbx+4]
0x18001994a  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x18001994f  mov     edi, eax
0x180019951  lea     rcx, [rbp+57h+var_48]
0x180019955  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001995a  test    edi, edi
0x18001995c  jns     loc_1800199E3
0x180019962  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180019969  jz      short loc_18001997E
0x18001996b  mov     r9, [rbx+8]
0x18001996f  mov     r8d, edi
0x180019972  lea     rdx, AutopilotRestorationHardwareWriteFailure
0x180019979  call    McTemplateU0dz_EventWriteTransfer
0x18001997e  mov     r8d, edi; int
0x180019981  mov     rdx, [rbx+8]; unsigned __int16 *
0x180019985  lea     rcx, aMicrosoftWindo_0; "Microsoft::Windows::Autopilot::Hardware"...
0x18001998c  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x180019991  jmp     short loc_1800199E3
0x180019993  cmp     [rbx+18h], r12b
0x180019997  jz      short loc_1800199E3
0x180019999  mov     rdi, [rbp+57h+var_98]
0x18001999d  lea     rdx, [rbp+57h+S2]
0x1800199a1  cmp     [rbp+57h+var_90], 7
0x1800199a6  cmova   rdx, [rbp+57h+S2]; S2
0x1800199ab  mov     rsi, [rbp+57h+N]
0x1800199af  lea     rcx, [rbp+57h+S1]
0x1800199b3  cmp     [rbp+57h+var_70], 7
0x1800199b8  cmova   rcx, [rbp+57h+S1]; S1
0x1800199bd  mov     r8, rdi
0x1800199c0  cmp     rdi, rsi
0x1800199c3  cmovnb  r8, rsi; N
0x1800199c7  call    wmemcmp
0x1800199cc  test    eax, eax
0x1800199ce  jnz     loc_180019A87
0x1800199d4  cmp     rsi, rdi
0x1800199d7  jb      loc_180019A87
0x1800199dd  ja      loc_180019A87
0x1800199e3  lea     rcx, [rbp+57h+S1]
0x1800199e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800199ec  nop
0x1800199ed  lea     rcx, [rbp+57h+S2]
0x1800199f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800199f6  add     rbx, 20h ; ' '
0x1800199fa  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180019a01  cmp     rbx, rax
0x180019a04  jnz     loc_180019833
0x180019a0a  xor     eax, eax
0x180019a0c  mov     rcx, [rbp+57h+var_28]
0x180019a10  xor     rcx, rsp; StackCookie
0x180019a13  call    __security_check_cookie
0x180019a18  lea     r11, [rsp+0D0h+var_20]
0x180019a20  mov     rbx, [r11+30h]
0x180019a24  mov     rsi, [r11+40h]
0x180019a28  mov     rsp, r11
0x180019a2b  pop     r15
0x180019a2d  pop     r14
0x180019a2f  pop     r12
0x180019a31  pop     rdi
0x180019a32  pop     rbp
0x180019a33  retn
0x180019a34  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180019a3b  jz      short loc_180019A50
0x180019a3d  mov     r9, [rbx+8]
0x180019a41  mov     r8d, edi
0x180019a44  lea     rdx, AutopilotRestorationHardwareReadFailure
0x180019a4b  call    McTemplateU0dz_EventWriteTransfer
0x180019a50  mov     r8d, edi; int
0x180019a53  mov     rdx, [rbx+8]; unsigned __int16 *
0x180019a57  lea     rcx, aMicrosoftWindo_0; "Microsoft::Windows::Autopilot::Hardware"...
0x180019a5e  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x180019a63  mov     rcx, [rbp+5Fh]; this
0x180019a67  mov     r9d, edi; char *
0x180019a6a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019a71  mov     edx, 0BEh; void *
0x180019a76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a7b  nop
0x180019a7c  lea     rcx, [rbp+57h+S1]
0x180019a80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019a85  jmp     short loc_180019ABC
0x180019a87  mov     byte ptr [r14], 1
0x180019a8b  lea     rcx, [rbp+57h+S1]
0x180019a8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019a94  nop
0x180019a95  lea     rcx, [rbp+57h+S2]
0x180019a99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019a9e  jmp     loc_180019A0A
0x180019aa3  mov     rcx, [rbp+5Fh]; this
0x180019aa7  mov     r9d, eax; char *
0x180019aaa  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019ab1  mov     edx, 9Fh; void *
0x180019ab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019abb  nop
0x180019abc  lea     rcx, [rbp+57h+S2]
0x180019ac0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019ac5  mov     eax, edi
0x180019ac7  jmp     loc_180019A0C
```
