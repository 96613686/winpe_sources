# Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)

- ea: `0x180019ad4`
- end: `0x180019c0b`
- name: `?CollectHardwareSnapshot@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `311`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ba54`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x180013be0`
- `0x1800174f0`
- `0x180019ad4`
- `0x18001ca58`
- `0x18002e010`

## string_xrefs

- `0x180019bd7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)
{
  __int64 *v0; // rbx
  int v1; // edi
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v5; // rdx
  __int128 v6; // [rsp+20h] [rbp-39h] BYREF
  __int64 v7; // [rsp+30h] [rbp-29h]
  __int64 v8; // [rsp+38h] [rbp-21h]
  __int128 *v9; // [rsp+40h] [rbp-19h]
  __int128 v10; // [rsp+48h] [rbp-11h] BYREF
  __int64 v11; // [rsp+58h] [rbp-1h]
  __int64 v12; // [rsp+60h] [rbp+7h]
  _OWORD v13[2]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v0 = &qword_1800300C0;
  while ( 1 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 7;
    LOWORD(v10) = 0;
    v1 = ((__int64 (__fastcall *)(__int128 *))v0[2])(&v10);
    if ( v1 < 0 )
      break;
    v9 = &v6;
    v6 = 0;
    v7 = 0;
    v8 = 0;
    std::wstring::_Construct<2,unsigned short const *>(&v6);
    v2 = v0[1];
    memset(v13, 0, sizeof(v13));
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)(v2 + 2 * v3) );
    std::wstring::_Construct<1,unsigned short const *>(v13, v2, v3);
    v1 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
           *((_DWORD *)v0 + 1),
           (__int64)v13,
           (const unsigned __int16 *)&v6);
    std::wstring::_Tidy_deallocate(v13);
    if ( v1 < 0 )
    {
      v5 = 215;
      goto LABEL_10;
    }
    std::wstring::_Tidy_deallocate(&v10);
    v0 += 4;
    if ( v0 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  v5 = 211;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)v1,
    v6);
  std::wstring::_Tidy_deallocate(&v10);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180019ad4  push    rbp
0x180019ad6  push    rbx
0x180019ad7  push    rsi
0x180019ad8  push    rdi
0x180019ad9  lea     rbp, [rsp-3Fh]
0x180019ade  sub     rsp, 98h
0x180019ae5  mov     rax, cs:__security_cookie
0x180019aec  xor     rax, rsp
0x180019aef  mov     [rbp+57h+var_28], rax
0x180019af3  lea     rbx, qword_1800300C0
0x180019afa  xor     esi, esi
0x180019afc  xorps   xmm0, xmm0
0x180019aff  movups  [rbp+57h+var_68], xmm0
0x180019b03  mov     [rbp+57h+var_58], rsi
0x180019b07  mov     [rbp+57h+var_50], 7
0x180019b0f  mov     word ptr [rbp+57h+var_68], si
0x180019b13  lea     rcx, [rbp+57h+var_68]
0x180019b17  mov     rax, [rbx+10h]
0x180019b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b20  mov     edi, eax
0x180019b22  test    eax, eax
0x180019b24  js      loc_180019BCF
0x180019b2a  lea     rax, [rbp+57h+var_90]
0x180019b2e  mov     [rbp+57h+var_70], rax
0x180019b32  xorps   xmm0, xmm0
0x180019b35  movups  [rbp+57h+var_90], xmm0
0x180019b39  mov     [rbp+57h+var_80], rsi
0x180019b3d  mov     [rbp+57h+var_78], rsi
0x180019b41  lea     rdx, [rbp+57h+var_68]
0x180019b45  cmp     [rbp+57h+var_50], 7
0x180019b4a  cmova   rdx, qword ptr [rbp+57h+var_68]
0x180019b4f  mov     r8, [rbp+57h+var_58]
0x180019b53  lea     rcx, [rbp+57h+var_90]
0x180019b57  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019b5c  nop
0x180019b5d  mov     rdx, [rbx+8]
0x180019b61  xorps   xmm0, xmm0
0x180019b64  movups  [rbp+57h+var_48], xmm0
0x180019b68  xorps   xmm1, xmm1
0x180019b6b  movdqu  [rbp+57h+var_38], xmm1
0x180019b70  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019b74  inc     r8
0x180019b77  cmp     [rdx+r8*2], si
0x180019b7c  jnz     short loc_180019B74
0x180019b7e  lea     rcx, [rbp+57h+var_48]
0x180019b82  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019b87  nop
0x180019b88  lea     r8, [rbp+57h+var_90]
0x180019b8c  lea     rdx, [rbp+57h+var_48]
0x180019b90  mov     ecx, [rbx+4]
0x180019b93  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x180019b98  mov     edi, eax
0x180019b9a  lea     rcx, [rbp+57h+var_48]
0x180019b9e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019ba3  test    edi, edi
0x180019ba5  js      short loc_180019BC8
0x180019ba7  lea     rcx, [rbp+57h+var_68]
0x180019bab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019bb0  add     rbx, 20h ; ' '
0x180019bb4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180019bbb  cmp     rbx, rax
0x180019bbe  jnz     loc_180019AFC
0x180019bc4  xor     eax, eax
0x180019bc6  jmp     short loc_180019BF3
0x180019bc8  mov     edx, 0D7h
0x180019bcd  jmp     short loc_180019BD4
0x180019bcf  mov     edx, 0D3h; void *
0x180019bd4  mov     r9d, edi; char *
0x180019bd7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019bde  mov     rcx, [rbp+5Fh]; this
0x180019be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019be7  nop
0x180019be8  lea     rcx, [rbp+57h+var_68]
0x180019bec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019bf1  mov     eax, edi
0x180019bf3  mov     rcx, [rbp+57h+var_28]
0x180019bf7  xor     rcx, rsp; StackCookie
0x180019bfa  call    __security_check_cookie
0x180019bff  add     rsp, 98h
0x180019c06  pop     rdi
0x180019c07  pop     rsi
0x180019c08  pop     rbx
0x180019c09  pop     rbp
0x180019c0a  retn
```
