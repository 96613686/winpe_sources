# Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)

- ea: `0x18001a0f8`
- end: `0x18001a230`
- name: `?CollectHardwareSnapshot@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `312`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c190`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180013f88`
- `0x180017a20`
- `0x18001a0f8`
- `0x18001d1c0`
- `0x18002f010`

## string_xrefs

- `0x18001a1fb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::HardwareInfo::CollectHardwareSnapshot(void)
{
  __int64 *v0; // rbx
  int v1; // edi
  __int128 *v2; // rdx
  _WORD *v3; // rdx
  unsigned __int64 v4; // r8
  __int64 v6; // rdx
  __int128 v7; // [rsp+20h] [rbp-39h] BYREF
  __int64 v8; // [rsp+30h] [rbp-29h]
  __int64 v9; // [rsp+38h] [rbp-21h]
  __int128 *v10; // [rsp+40h] [rbp-19h]
  __int128 v11; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp-1h]
  unsigned __int64 v13; // [rsp+60h] [rbp+7h]
  _OWORD v14[2]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v0 = &qword_1800310C0;
  while ( 1 )
  {
    v11 = 0;
    v12 = 0;
    v13 = 7;
    LOWORD(v11) = 0;
    v1 = ((__int64 (__fastcall *)(__int128 *))v0[2])(&v11);
    if ( v1 < 0 )
      break;
    v10 = &v7;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v2 = &v11;
    if ( v13 > 7 )
      v2 = (__int128 *)v11;
    std::wstring::_Construct<2,unsigned short const *>((__int64)&v7, v2, v12);
    v3 = (_WORD *)v0[1];
    memset(v14, 0, sizeof(v14));
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    std::wstring::_Construct<1,unsigned short const *>(v14, v3, v4);
    v1 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
           *((_DWORD *)v0 + 1),
           (__int64)v14,
           (const unsigned __int16 *)&v7);
    std::wstring::_Tidy_deallocate((char **)v14);
    if ( v1 < 0 )
    {
      v6 = 215;
      goto LABEL_12;
    }
    std::wstring::_Tidy_deallocate((char **)&v11);
    v0 += 4;
    if ( v0 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  v6 = 211;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)v1,
    v7);
  std::wstring::_Tidy_deallocate((char **)&v11);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001a0f8  push    rbp
0x18001a0fa  push    rbx
0x18001a0fb  push    rsi
0x18001a0fc  push    rdi
0x18001a0fd  lea     rbp, [rsp-3Fh]
0x18001a102  sub     rsp, 98h
0x18001a109  mov     rax, cs:__security_cookie
0x18001a110  xor     rax, rsp
0x18001a113  mov     [rbp+57h+var_28], rax
0x18001a117  lea     rbx, qword_1800310C0
0x18001a11e  xor     esi, esi
0x18001a120  xorps   xmm0, xmm0
0x18001a123  movups  [rbp+57h+var_68], xmm0
0x18001a127  mov     [rbp+57h+var_58], rsi
0x18001a12b  mov     [rbp+57h+var_50], 7
0x18001a133  mov     word ptr [rbp+57h+var_68], si
0x18001a137  lea     rcx, [rbp+57h+var_68]
0x18001a13b  mov     rax, [rbx+10h]
0x18001a13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a144  mov     edi, eax
0x18001a146  test    eax, eax
0x18001a148  js      loc_18001A1F3
0x18001a14e  lea     rax, [rbp+57h+var_90]
0x18001a152  mov     [rbp+57h+var_70], rax
0x18001a156  xorps   xmm0, xmm0
0x18001a159  movups  [rbp+57h+var_90], xmm0
0x18001a15d  mov     [rbp+57h+var_80], rsi
0x18001a161  mov     [rbp+57h+var_78], rsi
0x18001a165  lea     rdx, [rbp+57h+var_68]
0x18001a169  cmp     [rbp+57h+var_50], 7
0x18001a16e  cmova   rdx, qword ptr [rbp+57h+var_68]
0x18001a173  mov     r8, [rbp+57h+var_58]
0x18001a177  lea     rcx, [rbp+57h+var_90]
0x18001a17b  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001a180  nop
0x18001a181  mov     rdx, [rbx+8]
0x18001a185  xorps   xmm0, xmm0
0x18001a188  movups  [rbp+57h+var_48], xmm0
0x18001a18c  xorps   xmm1, xmm1
0x18001a18f  movdqu  [rbp+57h+var_38], xmm1
0x18001a194  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a198  inc     r8
0x18001a19b  cmp     [rdx+r8*2], si
0x18001a1a0  jnz     short loc_18001A198
0x18001a1a2  lea     rcx, [rbp+57h+var_48]
0x18001a1a6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a1ab  nop
0x18001a1ac  lea     r8, [rbp+57h+var_90]
0x18001a1b0  lea     rdx, [rbp+57h+var_48]
0x18001a1b4  mov     ecx, [rbx+4]
0x18001a1b7  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x18001a1bc  mov     edi, eax
0x18001a1be  lea     rcx, [rbp+57h+var_48]
0x18001a1c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a1c7  test    edi, edi
0x18001a1c9  js      short loc_18001A1EC
0x18001a1cb  lea     rcx, [rbp+57h+var_68]
0x18001a1cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a1d4  add     rbx, 20h ; ' '
0x18001a1d8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a1df  cmp     rbx, rax
0x18001a1e2  jnz     loc_18001A120
0x18001a1e8  xor     eax, eax
0x18001a1ea  jmp     short loc_18001A217
0x18001a1ec  mov     edx, 0D7h
0x18001a1f1  jmp     short loc_18001A1F8
0x18001a1f3  mov     edx, 0D3h; void *
0x18001a1f8  mov     r9d, edi; char *
0x18001a1fb  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a202  mov     rcx, [rbp+5Fh]; this
0x18001a206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a20b  nop
0x18001a20c  lea     rcx, [rbp+57h+var_68]
0x18001a210  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a215  mov     eax, edi
0x18001a217  mov     rcx, [rbp+57h+var_28]
0x18001a21b  xor     rcx, rsp; StackCookie
0x18001a21e  call    __security_check_cookie
0x18001a223  add     rsp, 98h
0x18001a22a  pop     rdi
0x18001a22b  pop     rsi
0x18001a22c  pop     rbx
0x18001a22d  pop     rbp
0x18001a22e  retn
```
