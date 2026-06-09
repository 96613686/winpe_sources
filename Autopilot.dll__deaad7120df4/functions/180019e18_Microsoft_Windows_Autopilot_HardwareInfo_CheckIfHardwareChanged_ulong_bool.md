# Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(ulong,bool &)

- ea: `0x180019e18`
- end: `0x18001a0f1`
- name: `?CheckIfHardwareChanged@HardwareInfo@Autopilot@Windows@Microsoft@@SAJKAEA_N@Z`
- size: `729`
- prototype: `__int64 __fastcall(int, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c190`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013580`
- `0x180013de4`
- `0x180013f88`
- `0x180017a20`
- `0x180019e18`
- `0x18001c070`
- `0x18001c958`
- `0x18001d1c0`
- `0x18001d85c`
- `0x18002f010`

## string_xrefs

- `0x18001a08f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a0cf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged(int a1, bool *a2)
{
  __int64 *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  wchar_t **v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // edi
  __int64 v14; // rcx
  size_t v15; // rdi
  const wchar_t *v16; // rdx
  size_t v17; // rsi
  const wchar_t *v18; // rcx
  size_t v19; // r8
  __int128 *v21; // [rsp+20h] [rbp-59h]
  wchar_t *S2[2]; // [rsp+28h] [rbp-51h] BYREF
  size_t v23; // [rsp+38h] [rbp-41h]
  unsigned __int64 v24; // [rsp+40h] [rbp-39h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-31h] BYREF
  size_t N; // [rsp+58h] [rbp-21h]
  unsigned __int64 v27; // [rsp+60h] [rbp-19h]
  __int128 v28; // [rsp+68h] [rbp-11h] BYREF
  __int128 v29; // [rsp+78h] [rbp-1h]
  _OWORD v30[2]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v4 = &qword_1800310C0;
  while ( (a1 & *(_DWORD *)v4) == *(_DWORD *)v4 )
  {
LABEL_27:
    v4 += 4;
    if ( v4 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  *(_OWORD *)S2 = 0;
  v23 = 0;
  v24 = 7;
  LOWORD(S2[0]) = 0;
  v5 = ((__int64 (__fastcall *)(wchar_t **))v4[2])(S2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      (int)v21);
    goto LABEL_34;
  }
  *(_OWORD *)S1 = 0;
  N = 0;
  v27 = 7;
  LOWORD(S1[0]) = 0;
  v7 = v4[1];
  v28 = 0;
  v29 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v7 + 2 * v8) );
  std::wstring::_Construct<1,unsigned short const *>(&v28, v7);
  v6 = Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(*((unsigned int *)v4 + 1), &v28, S1);
  std::wstring::_Tidy_deallocate(&v28);
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( *((_BYTE *)v4 + 24) )
    {
      v15 = v23;
      v16 = (const wchar_t *)S2;
      if ( v24 > 7 )
        v16 = S2[0];
      v17 = N;
      v18 = (const wchar_t *)S1;
      if ( v27 > 7 )
        v18 = S1[0];
      v19 = v23;
      if ( v23 >= N )
        v19 = N;
      if ( wmemcmp(v18, v16, v19) || v17 < v15 || v17 > v15 )
      {
        *a2 = 1;
        std::wstring::_Tidy_deallocate(S1);
        std::wstring::_Tidy_deallocate(S2);
        return 0;
      }
    }
    goto LABEL_26;
  }
  v9 = v6 + 2147024894;
  if ( (unsigned int)v9 <= 1 )
  {
    v21 = &v28;
    v28 = 0;
    v29 = 0u;
    v10 = S2;
    if ( v24 > 7 )
      v10 = (wchar_t **)S2[0];
    std::wstring::_Construct<2,unsigned short const *>(&v28, v10, v23);
    v11 = v4[1];
    memset(v30, 0, sizeof(v30));
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v11 + 2 * v12) );
    std::wstring::_Construct<1,unsigned short const *>(v30, v11);
    v13 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(*((unsigned int *)v4 + 1), v30, &v28);
    std::wstring::_Tidy_deallocate(v30);
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(v14, AutopilotRestorationHardwareWriteFailure, (unsigned int)v13, v4[1], &v28);
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged",
        (const unsigned __int16 *)v4[1],
        v13);
    }
LABEL_26:
    std::wstring::_Tidy_deallocate(S1);
    std::wstring::_Tidy_deallocate(S2);
    goto LABEL_27;
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    McTemplateU0dz_EventWriteTransfer(v9, AutopilotRestorationHardwareReadFailure, v6, v4[1], v21);
  Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
    L"Microsoft::Windows::Autopilot::HardwareInfo::CheckIfHardwareChanged",
    (const unsigned __int16 *)v4[1],
    v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBE,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)v6,
    (int)v21);
  std::wstring::_Tidy_deallocate(S1);
LABEL_34:
  std::wstring::_Tidy_deallocate(S2);
  return v6;
}

```

## disassembly

```asm
0x180019e18  mov     [rsp-8+arg_0], rbx
0x180019e1d  mov     [rsp-8+arg_10], rsi
0x180019e22  push    rbp
0x180019e23  push    rdi
0x180019e24  push    r12
0x180019e26  push    r14
0x180019e28  push    r15
0x180019e2a  lea     rbp, [rsp-37h]
0x180019e2f  sub     rsp, 0B0h
0x180019e36  mov     rax, cs:__security_cookie
0x180019e3d  xor     rax, rsp
0x180019e40  mov     [rbp+57h+var_28], rax
0x180019e44  mov     r14, rdx
0x180019e47  mov     r15d, ecx
0x180019e4a  xor     r12d, r12d
0x180019e4d  mov     [rdx], r12b
0x180019e50  lea     rbx, qword_1800310C0
0x180019e57  mov     eax, [rbx]
0x180019e59  and     eax, r15d
0x180019e5c  cmp     eax, [rbx]
0x180019e5e  jz      loc_18001A01A
0x180019e64  xorps   xmm0, xmm0
0x180019e67  movups  xmmword ptr [rbp+57h+S2], xmm0
0x180019e6b  mov     [rbp+57h+var_98], r12
0x180019e6f  mov     [rbp+57h+var_90], 7
0x180019e77  mov     word ptr [rbp+57h+S2], r12w
0x180019e7c  lea     rcx, [rbp+57h+S2]
0x180019e80  mov     rax, [rbx+10h]
0x180019e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e89  mov     edi, eax
0x180019e8b  test    eax, eax
0x180019e8d  js      loc_18001A0C8
0x180019e93  xorps   xmm0, xmm0
0x180019e96  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180019e9a  mov     [rbp+57h+N], r12
0x180019e9e  mov     [rbp+57h+var_70], 7
0x180019ea6  mov     word ptr [rbp+57h+S1], r12w
0x180019eab  mov     rdx, [rbx+8]
0x180019eaf  movups  [rbp+57h+var_68], xmm0
0x180019eb3  xorps   xmm1, xmm1
0x180019eb6  movdqu  [rbp+57h+var_58], xmm1
0x180019ebb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019ebf  inc     r8
0x180019ec2  cmp     [rdx+r8*2], r12w
0x180019ec7  jnz     short loc_180019EBF
0x180019ec9  lea     rcx, [rbp+57h+var_68]
0x180019ecd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019ed2  nop
0x180019ed3  lea     r8, [rbp+57h+S1]
0x180019ed7  lea     rdx, [rbp+57h+var_68]
0x180019edb  mov     ecx, [rbx+4]
0x180019ede  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x180019ee3  mov     edi, eax
0x180019ee5  lea     rcx, [rbp+57h+var_68]
0x180019ee9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019eee  test    edi, edi
0x180019ef0  jns     loc_180019FB7
0x180019ef6  lea     ecx, [rdi+7FF8FFFEh]
0x180019efc  cmp     ecx, 1
0x180019eff  ja      loc_18001A059
0x180019f05  lea     rax, [rbp+57h+var_68]
0x180019f09  mov     [rbp+57h+var_B0], rax
0x180019f0d  xorps   xmm0, xmm0
0x180019f10  movups  [rbp+57h+var_68], xmm0
0x180019f14  mov     qword ptr [rbp+57h+var_58], r12
0x180019f18  mov     qword ptr [rbp+57h+var_58+8], r12
0x180019f1c  lea     rdx, [rbp+57h+S2]
0x180019f20  cmp     [rbp+57h+var_90], 7
0x180019f25  cmova   rdx, [rbp+57h+S2]
0x180019f2a  mov     r8, [rbp+57h+var_98]
0x180019f2e  lea     rcx, [rbp+57h+var_68]
0x180019f32  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019f37  nop
0x180019f38  mov     rdx, [rbx+8]
0x180019f3c  xorps   xmm0, xmm0
0x180019f3f  movups  [rbp+57h+var_48], xmm0
0x180019f43  xorps   xmm1, xmm1
0x180019f46  movdqu  [rbp+57h+var_38], xmm1
0x180019f4b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019f4f  inc     r8
0x180019f52  cmp     [rdx+r8*2], r12w
0x180019f57  jnz     short loc_180019F4F
0x180019f59  lea     rcx, [rbp+57h+var_48]
0x180019f5d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019f62  nop
0x180019f63  lea     r8, [rbp+57h+var_68]
0x180019f67  lea     rdx, [rbp+57h+var_48]
0x180019f6b  mov     ecx, [rbx+4]
0x180019f6e  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x180019f73  mov     edi, eax
0x180019f75  lea     rcx, [rbp+57h+var_48]
0x180019f79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019f7e  test    edi, edi
0x180019f80  jns     loc_18001A007
0x180019f86  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180019f8d  jz      short loc_180019FA2
0x180019f8f  mov     r9, [rbx+8]
0x180019f93  mov     r8d, edi
0x180019f96  lea     rdx, AutopilotRestorationHardwareWriteFailure
0x180019f9d  call    McTemplateU0dz_EventWriteTransfer
0x180019fa2  mov     r8d, edi; int
0x180019fa5  mov     rdx, [rbx+8]; unsigned __int16 *
0x180019fa9  lea     rcx, aMicrosoftWindo_0; "Microsoft::Windows::Autopilot::Hardware"...
0x180019fb0  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x180019fb5  jmp     short loc_18001A007
0x180019fb7  cmp     [rbx+18h], r12b
0x180019fbb  jz      short loc_18001A007
0x180019fbd  mov     rdi, [rbp+57h+var_98]
0x180019fc1  lea     rdx, [rbp+57h+S2]
0x180019fc5  cmp     [rbp+57h+var_90], 7
0x180019fca  cmova   rdx, [rbp+57h+S2]; S2
0x180019fcf  mov     rsi, [rbp+57h+N]
0x180019fd3  lea     rcx, [rbp+57h+S1]
0x180019fd7  cmp     [rbp+57h+var_70], 7
0x180019fdc  cmova   rcx, [rbp+57h+S1]; S1
0x180019fe1  mov     r8, rdi
0x180019fe4  cmp     rdi, rsi
0x180019fe7  cmovnb  r8, rsi; N
0x180019feb  call    wmemcmp
0x180019ff0  test    eax, eax
0x180019ff2  jnz     loc_18001A0AC
0x180019ff8  cmp     rsi, rdi
0x180019ffb  jb      loc_18001A0AC
0x18001a001  ja      loc_18001A0AC
0x18001a007  lea     rcx, [rbp+57h+S1]
0x18001a00b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a010  nop
0x18001a011  lea     rcx, [rbp+57h+S2]
0x18001a015  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a01a  add     rbx, 20h ; ' '
0x18001a01e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a025  cmp     rbx, rax
0x18001a028  jnz     loc_180019E57
0x18001a02e  xor     eax, eax
0x18001a030  mov     rcx, [rbp+57h+var_28]
0x18001a034  xor     rcx, rsp; StackCookie
0x18001a037  call    __security_check_cookie
0x18001a03c  lea     r11, [rsp+0D0h+var_20]
0x18001a044  mov     rbx, [r11+30h]
0x18001a048  mov     rsi, [r11+40h]
0x18001a04c  mov     rsp, r11
0x18001a04f  pop     r15
0x18001a051  pop     r14
0x18001a053  pop     r12
0x18001a055  pop     rdi
0x18001a056  pop     rbp
0x18001a057  retn
0x18001a059  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001a060  jz      short loc_18001A075
0x18001a062  mov     r9, [rbx+8]
0x18001a066  mov     r8d, edi
0x18001a069  lea     rdx, AutopilotRestorationHardwareReadFailure
0x18001a070  call    McTemplateU0dz_EventWriteTransfer
0x18001a075  mov     r8d, edi; int
0x18001a078  mov     rdx, [rbx+8]; unsigned __int16 *
0x18001a07c  lea     rcx, aMicrosoftWindo_0; "Microsoft::Windows::Autopilot::Hardware"...
0x18001a083  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001a088  mov     rcx, [rbp+5Fh]; this
0x18001a08c  mov     r9d, edi; char *
0x18001a08f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a096  mov     edx, 0BEh; void *
0x18001a09b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0a0  nop
0x18001a0a1  lea     rcx, [rbp+57h+S1]
0x18001a0a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0aa  jmp     short loc_18001A0E1
0x18001a0ac  mov     byte ptr [r14], 1
0x18001a0b0  lea     rcx, [rbp+57h+S1]
0x18001a0b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0b9  nop
0x18001a0ba  lea     rcx, [rbp+57h+S2]
0x18001a0be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0c3  jmp     loc_18001A02E
0x18001a0c8  mov     rcx, [rbp+5Fh]; this
0x18001a0cc  mov     r9d, eax; char *
0x18001a0cf  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a0d6  mov     edx, 9Fh; void *
0x18001a0db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0e0  nop
0x18001a0e1  lea     rcx, [rbp+57h+S2]
0x18001a0e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0ea  mov     eax, edi
0x18001a0ec  jmp     loc_18001A030
```
