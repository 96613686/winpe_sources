# Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x180019c14`
- end: `0x180019e34`
- name: `?CopyHardwareComponentsCache@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@0@Z`
- size: `544`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ba54`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x180013be0`
- `0x1800174f0`
- `0x180019c14`
- `0x18001b1f4`
- `0x18001c234`
- `0x18001ca58`

## string_xrefs

- `0x180019dca`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019dee`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache()
{
  __int64 *v0; // rdi
  __m128i si128; // xmm6
  __int64 v2; // rdx
  __int64 v3; // r8
  int StorageLocationName; // ebx
  int StringFromStorage; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // [rsp+28h] [rbp-69h]
  __int128 v15; // [rsp+30h] [rbp-61h] BYREF
  __int128 v16; // [rsp+40h] [rbp-51h]
  __int128 v17; // [rsp+50h] [rbp-41h] BYREF
  __int64 v18; // [rsp+60h] [rbp-31h]
  __int64 v19; // [rsp+68h] [rbp-29h]
  _OWORD v20[2]; // [rsp+70h] [rbp-21h] BYREF
  _OWORD v21[2]; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v0 = &qword_1800300C0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v21[0] = 0;
    v21[1] = si128;
    LOWORD(v21[0]) = 0;
    v17 = 0;
    v18 = 0;
    v19 = 7;
    LOWORD(v17) = 0;
    v2 = v0[1];
    v15 = 0;
    v16 = 0;
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)(v2 + 2 * v3) );
    std::wstring::_Construct<1,unsigned short const *>(&v15, v2, v3);
    StorageLocationName = Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(1, (__int64)&v15, v21);
    std::wstring::_Tidy_deallocate(&v15);
    if ( StorageLocationName < 0 )
    {
      v10 = (unsigned int)StorageLocationName;
      v11 = 527;
      goto LABEL_18;
    }
    StringFromStorage = Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(
                          *((_DWORD *)v0 + 1),
                          (const WCHAR *)v21,
                          (__int64)&v17);
    StorageLocationName = StringFromStorage;
    if ( StringFromStorage < 0 && (unsigned int)(StringFromStorage + 2147024894) > 1 )
      break;
    v20[0] = 0;
    v20[1] = si128;
    LOWORD(v20[0]) = 0;
    v6 = v0[1];
    v15 = 0;
    v16 = 0;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    std::wstring::_Construct<1,unsigned short const *>(&v15, v6, v7);
    StorageLocationName = Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(0, (__int64)&v15, v20);
    std::wstring::_Tidy_deallocate(&v15);
    if ( StorageLocationName < 0 )
    {
      v12 = (unsigned int)StorageLocationName;
      v13 = 539;
      goto LABEL_16;
    }
    v15 = 0;
    v16 = 0u;
    std::wstring::_Construct<2,unsigned short const *>(&v15);
    v8 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
           *((_DWORD *)v0 + 1),
           (__int64)v20,
           (const unsigned __int16 *)&v15);
    StorageLocationName = v8;
    if ( v8 < 0 )
    {
      v12 = (unsigned int)v8;
      v13 = 540;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v12,
        v14);
      std::wstring::_Tidy_deallocate(v20);
      goto LABEL_19;
    }
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(&v17);
    std::wstring::_Tidy_deallocate(v21);
    v0 += 4;
    if ( v0 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  v10 = (unsigned int)StringFromStorage;
  v11 = 535;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)v10,
    v14);
LABEL_19:
  std::wstring::_Tidy_deallocate(&v17);
  std::wstring::_Tidy_deallocate(v21);
  return (unsigned int)StorageLocationName;
}

```

## disassembly

```asm
0x180019c14  mov     rax, rsp
0x180019c17  push    rbp
0x180019c18  push    rbx
0x180019c19  push    rsi
0x180019c1a  push    rdi
0x180019c1b  lea     rbp, [rax-5Fh]
0x180019c1f  sub     rsp, 0C8h
0x180019c26  movaps  xmmword ptr [rax-38h], xmm6
0x180019c2a  mov     rax, cs:__security_cookie
0x180019c31  xor     rax, rsp
0x180019c34  mov     qword ptr [rbp+57h+var_38], rax
0x180019c38  lea     rdi, qword_1800300C0
0x180019c3f  xor     esi, esi
0x180019c41  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180019c49  xorps   xmm0, xmm0
0x180019c4c  movups  [rbp+57h+var_58], xmm0
0x180019c50  movdqu  [rbp+57h+var_48], xmm6
0x180019c55  mov     word ptr [rbp+57h+var_58], si
0x180019c59  movups  [rbp+57h+var_98], xmm0
0x180019c5d  mov     [rbp+57h+var_88], rsi
0x180019c61  mov     [rbp+57h+var_80], 7
0x180019c69  mov     word ptr [rbp+57h+var_98], si
0x180019c6d  mov     rdx, [rdi+8]
0x180019c71  movups  [rbp+57h+var_B8], xmm0
0x180019c75  xorps   xmm1, xmm1
0x180019c78  movdqu  [rbp+57h+var_A8], xmm1
0x180019c7d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019c81  inc     r8
0x180019c84  cmp     [rdx+r8*2], si
0x180019c89  jnz     short loc_180019C81
0x180019c8b  lea     rcx, [rbp+57h+var_B8]
0x180019c8f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019c94  nop
0x180019c95  lea     r8, [rbp+57h+var_58]
0x180019c99  lea     rdx, [rbp+57h+var_B8]
0x180019c9d  mov     ecx, 1
0x180019ca2  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x180019ca7  mov     ebx, eax
0x180019ca9  lea     rcx, [rbp+57h+var_B8]
0x180019cad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019cb2  test    ebx, ebx
0x180019cb4  js      loc_180019DE6
0x180019cba  lea     r8, [rbp+57h+var_98]
0x180019cbe  lea     rdx, [rbp+57h+var_58]
0x180019cc2  mov     ecx, [rdi+4]
0x180019cc5  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x180019cca  mov     ebx, eax
0x180019ccc  test    eax, eax
0x180019cce  jns     short loc_180019CDF
0x180019cd0  lea     ecx, [rax+7FF8FFFEh]
0x180019cd6  cmp     ecx, 1
0x180019cd9  ja      loc_180019DAE
0x180019cdf  xorps   xmm0, xmm0
0x180019ce2  movups  [rbp+57h+var_78], xmm0
0x180019ce6  movdqu  [rbp+57h+var_68], xmm6
0x180019ceb  mov     word ptr [rbp+57h+var_78], si
0x180019cef  mov     rdx, [rdi+8]
0x180019cf3  movups  [rbp+57h+var_B8], xmm0
0x180019cf7  xorps   xmm1, xmm1
0x180019cfa  movdqu  [rbp+57h+var_A8], xmm1
0x180019cff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019d03  inc     r8
0x180019d06  cmp     [rdx+r8*2], si
0x180019d0b  jnz     short loc_180019D03
0x180019d0d  lea     rcx, [rbp+57h+var_B8]
0x180019d11  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019d16  nop
0x180019d17  lea     r8, [rbp+57h+var_78]
0x180019d1b  lea     rdx, [rbp+57h+var_B8]
0x180019d1f  xor     ecx, ecx
0x180019d21  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x180019d26  mov     ebx, eax
0x180019d28  lea     rcx, [rbp+57h+var_B8]
0x180019d2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d31  test    ebx, ebx
0x180019d33  js      loc_180019DC2
0x180019d39  xorps   xmm0, xmm0
0x180019d3c  movups  [rbp+57h+var_B8], xmm0
0x180019d40  mov     qword ptr [rbp+57h+var_A8], rsi
0x180019d44  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x180019d48  lea     rdx, [rbp+57h+var_98]
0x180019d4c  cmp     [rbp+57h+var_80], 7
0x180019d51  cmova   rdx, qword ptr [rbp+57h+var_98]
0x180019d56  mov     r8, [rbp+57h+var_88]
0x180019d5a  lea     rcx, [rbp+57h+var_B8]
0x180019d5e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019d63  lea     r8, [rbp+57h+var_B8]
0x180019d67  lea     rdx, [rbp+57h+var_78]
0x180019d6b  mov     ecx, [rdi+4]
0x180019d6e  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x180019d73  mov     ebx, eax
0x180019d75  test    eax, eax
0x180019d77  js      short loc_180019DB8
0x180019d79  lea     rcx, [rbp+57h+var_78]
0x180019d7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d82  nop
0x180019d83  lea     rcx, [rbp+57h+var_98]
0x180019d87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d8c  nop
0x180019d8d  lea     rcx, [rbp+57h+var_58]
0x180019d91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d96  add     rdi, 20h ; ' '
0x180019d9a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180019da1  cmp     rdi, rax
0x180019da4  jnz     loc_180019C49
0x180019daa  xor     eax, eax
0x180019dac  jmp     short loc_180019E14
0x180019dae  mov     r9d, eax
0x180019db1  mov     edx, 217h
0x180019db6  jmp     short loc_180019DEE
0x180019db8  mov     r9d, eax
0x180019dbb  mov     edx, 21Ch
0x180019dc0  jmp     short loc_180019DCA
0x180019dc2  mov     r9d, ebx; char *
0x180019dc5  mov     edx, 21Bh; void *
0x180019dca  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019dd1  mov     rcx, [rbp+5Fh]; this
0x180019dd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dda  nop
0x180019ddb  lea     rcx, [rbp+57h+var_78]
0x180019ddf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019de4  jmp     short loc_180019DFF
0x180019de6  mov     r9d, ebx; char *
0x180019de9  mov     edx, 20Fh; void *
0x180019dee  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019df5  mov     rcx, [rbp+5Fh]; this
0x180019df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dfe  nop
0x180019dff  lea     rcx, [rbp+57h+var_98]
0x180019e03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019e08  nop
0x180019e09  lea     rcx, [rbp+57h+var_58]
0x180019e0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019e12  mov     eax, ebx
0x180019e14  mov     rcx, qword ptr [rbp+57h+var_38]
0x180019e18  xor     rcx, rsp; StackCookie
0x180019e1b  call    __security_check_cookie
0x180019e20  movaps  xmm6, [rsp+0E0h+var_38+8]
0x180019e28  add     rsp, 0C8h
0x180019e2f  pop     rdi
0x180019e30  pop     rsi
0x180019e31  pop     rbx
0x180019e32  pop     rbp
0x180019e33  retn
```
