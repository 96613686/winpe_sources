# Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x18001a238`
- end: `0x18001a459`
- name: `?CopyHardwareComponentsCache@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@0@Z`
- size: `545`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c190`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180013f88`
- `0x180017a20`
- `0x18001a238`
- `0x18001b898`
- `0x18001c958`
- `0x18001d1c0`

## string_xrefs

- `0x18001a3ee`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001a412`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::HardwareInfo::CopyHardwareComponentsCache()
{
  __int64 *v0; // rdi
  __m128i si128; // xmm6
  _WORD *v2; // rdx
  unsigned __int64 v3; // r8
  int StorageLocationName; // ebx
  int StringFromStorage; // eax
  _WORD *v6; // rdx
  unsigned __int64 v7; // r8
  __int128 *v8; // rdx
  int v9; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // [rsp+28h] [rbp-69h]
  __int128 v16; // [rsp+30h] [rbp-61h] BYREF
  __int128 v17; // [rsp+40h] [rbp-51h]
  __int128 v18; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int64 v19; // [rsp+60h] [rbp-31h]
  unsigned __int64 v20; // [rsp+68h] [rbp-29h]
  _OWORD v21[2]; // [rsp+70h] [rbp-21h] BYREF
  _OWORD v22[2]; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v0 = &qword_1800310C0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v22[0] = 0;
    v22[1] = si128;
    LOWORD(v22[0]) = 0;
    v18 = 0;
    v19 = 0;
    v20 = 7;
    LOWORD(v18) = 0;
    v2 = (_WORD *)v0[1];
    v16 = 0;
    v17 = 0;
    v3 = -1;
    do
      ++v3;
    while ( v2[v3] );
    std::wstring::_Construct<1,unsigned short const *>(&v16, v2, v3);
    StorageLocationName = Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(1, &v16, v22);
    std::wstring::_Tidy_deallocate((char **)&v16);
    if ( StorageLocationName < 0 )
      break;
    StringFromStorage = Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(
                          *((_DWORD *)v0 + 1),
                          (const WCHAR *)v22,
                          (__int64)&v18);
    StorageLocationName = StringFromStorage;
    if ( StringFromStorage < 0 && (unsigned int)(StringFromStorage + 2147024894) > 1 )
    {
      v11 = (unsigned int)StringFromStorage;
      v12 = 535;
      goto LABEL_20;
    }
    v21[0] = 0;
    v21[1] = si128;
    LOWORD(v21[0]) = 0;
    v6 = (_WORD *)v0[1];
    v16 = 0;
    v17 = 0;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    std::wstring::_Construct<1,unsigned short const *>(&v16, v6, v7);
    StorageLocationName = Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(0, &v16, v21);
    std::wstring::_Tidy_deallocate((char **)&v16);
    if ( StorageLocationName < 0 )
    {
      v13 = (unsigned int)StorageLocationName;
      v14 = 539;
      goto LABEL_18;
    }
    v16 = 0;
    v17 = 0u;
    v8 = &v18;
    if ( v20 > 7 )
      v8 = (__int128 *)v18;
    std::wstring::_Construct<2,unsigned short const *>((__int64)&v16, v8, v19);
    v9 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
           *((_DWORD *)v0 + 1),
           (__int64)v21,
           (const unsigned __int16 *)&v16);
    StorageLocationName = v9;
    if ( v9 < 0 )
    {
      v13 = (unsigned int)v9;
      v14 = 540;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v13,
        v15);
      std::wstring::_Tidy_deallocate((char **)v21);
      goto LABEL_21;
    }
    std::wstring::_Tidy_deallocate((char **)v21);
    std::wstring::_Tidy_deallocate((char **)&v18);
    std::wstring::_Tidy_deallocate((char **)v22);
    v0 += 4;
    if ( v0 == (__int64 *)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'} )
      return 0;
  }
  v11 = (unsigned int)StorageLocationName;
  v12 = 527;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)v11,
    v15);
LABEL_21:
  std::wstring::_Tidy_deallocate((char **)&v18);
  std::wstring::_Tidy_deallocate((char **)v22);
  return (unsigned int)StorageLocationName;
}

```

## disassembly

```asm
0x18001a238  mov     rax, rsp
0x18001a23b  push    rbp
0x18001a23c  push    rbx
0x18001a23d  push    rsi
0x18001a23e  push    rdi
0x18001a23f  lea     rbp, [rax-5Fh]
0x18001a243  sub     rsp, 0C8h
0x18001a24a  movaps  xmmword ptr [rax-38h], xmm6
0x18001a24e  mov     rax, cs:__security_cookie
0x18001a255  xor     rax, rsp
0x18001a258  mov     qword ptr [rbp+57h+var_38], rax
0x18001a25c  lea     rdi, qword_1800310C0
0x18001a263  xor     esi, esi
0x18001a265  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001a26d  xorps   xmm0, xmm0
0x18001a270  movups  [rbp+57h+var_58], xmm0
0x18001a274  movdqu  [rbp+57h+var_48], xmm6
0x18001a279  mov     word ptr [rbp+57h+var_58], si
0x18001a27d  movups  [rbp+57h+var_98], xmm0
0x18001a281  mov     [rbp+57h+var_88], rsi
0x18001a285  mov     [rbp+57h+var_80], 7
0x18001a28d  mov     word ptr [rbp+57h+var_98], si
0x18001a291  mov     rdx, [rdi+8]
0x18001a295  movups  [rbp+57h+var_B8], xmm0
0x18001a299  xorps   xmm1, xmm1
0x18001a29c  movdqu  [rbp+57h+var_A8], xmm1
0x18001a2a1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a2a5  inc     r8
0x18001a2a8  cmp     [rdx+r8*2], si
0x18001a2ad  jnz     short loc_18001A2A5
0x18001a2af  lea     rcx, [rbp+57h+var_B8]
0x18001a2b3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a2b8  nop
0x18001a2b9  lea     r8, [rbp+57h+var_58]
0x18001a2bd  lea     rdx, [rbp+57h+var_B8]
0x18001a2c1  mov     ecx, 1
0x18001a2c6  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x18001a2cb  mov     ebx, eax
0x18001a2cd  lea     rcx, [rbp+57h+var_B8]
0x18001a2d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a2d6  test    ebx, ebx
0x18001a2d8  js      loc_18001A40A
0x18001a2de  lea     r8, [rbp+57h+var_98]
0x18001a2e2  lea     rdx, [rbp+57h+var_58]
0x18001a2e6  mov     ecx, [rdi+4]
0x18001a2e9  call    ?ReadStringFromStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ReadStringFromStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring &)
0x18001a2ee  mov     ebx, eax
0x18001a2f0  test    eax, eax
0x18001a2f2  jns     short loc_18001A303
0x18001a2f4  lea     ecx, [rax+7FF8FFFEh]
0x18001a2fa  cmp     ecx, 1
0x18001a2fd  ja      loc_18001A3D2
0x18001a303  xorps   xmm0, xmm0
0x18001a306  movups  [rbp+57h+var_78], xmm0
0x18001a30a  movdqu  [rbp+57h+var_68], xmm6
0x18001a30f  mov     word ptr [rbp+57h+var_78], si
0x18001a313  mov     rdx, [rdi+8]
0x18001a317  movups  [rbp+57h+var_B8], xmm0
0x18001a31b  xorps   xmm1, xmm1
0x18001a31e  movdqu  [rbp+57h+var_A8], xmm1
0x18001a323  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a327  inc     r8
0x18001a32a  cmp     [rdx+r8*2], si
0x18001a32f  jnz     short loc_18001A327
0x18001a331  lea     rcx, [rbp+57h+var_B8]
0x18001a335  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001a33a  nop
0x18001a33b  lea     r8, [rbp+57h+var_78]
0x18001a33f  lea     rdx, [rbp+57h+var_B8]
0x18001a343  xor     ecx, ecx
0x18001a345  call    ?GetStorageLocationName@HardwareInfo@Autopilot@Windows@Microsoft@@CAJW4HardwareComponentsCacheType@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetStorageLocationName(Microsoft::Windows::Autopilot::HardwareComponentsCacheType,std::wstring const &,std::wstring &)
0x18001a34a  mov     ebx, eax
0x18001a34c  lea     rcx, [rbp+57h+var_B8]
0x18001a350  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a355  test    ebx, ebx
0x18001a357  js      loc_18001A3E6
0x18001a35d  xorps   xmm0, xmm0
0x18001a360  movups  [rbp+57h+var_B8], xmm0
0x18001a364  mov     qword ptr [rbp+57h+var_A8], rsi
0x18001a368  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x18001a36c  lea     rdx, [rbp+57h+var_98]
0x18001a370  cmp     [rbp+57h+var_80], 7
0x18001a375  cmova   rdx, qword ptr [rbp+57h+var_98]
0x18001a37a  mov     r8, [rbp+57h+var_88]
0x18001a37e  lea     rcx, [rbp+57h+var_B8]
0x18001a382  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001a387  lea     r8, [rbp+57h+var_B8]
0x18001a38b  lea     rdx, [rbp+57h+var_78]
0x18001a38f  mov     ecx, [rdi+4]
0x18001a392  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x18001a397  mov     ebx, eax
0x18001a399  test    eax, eax
0x18001a39b  js      short loc_18001A3DC
0x18001a39d  lea     rcx, [rbp+57h+var_78]
0x18001a3a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a3a6  nop
0x18001a3a7  lea     rcx, [rbp+57h+var_98]
0x18001a3ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a3b0  nop
0x18001a3b1  lea     rcx, [rbp+57h+var_58]
0x18001a3b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a3ba  add     rdi, 20h ; ' '
0x18001a3be  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a3c5  cmp     rdi, rax
0x18001a3c8  jnz     loc_18001A26D
0x18001a3ce  xor     eax, eax
0x18001a3d0  jmp     short loc_18001A438
0x18001a3d2  mov     r9d, eax
0x18001a3d5  mov     edx, 217h
0x18001a3da  jmp     short loc_18001A412
0x18001a3dc  mov     r9d, eax
0x18001a3df  mov     edx, 21Ch
0x18001a3e4  jmp     short loc_18001A3EE
0x18001a3e6  mov     r9d, ebx; char *
0x18001a3e9  mov     edx, 21Bh; void *
0x18001a3ee  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a3f5  mov     rcx, [rbp+5Fh]; this
0x18001a3f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3fe  nop
0x18001a3ff  lea     rcx, [rbp+57h+var_78]
0x18001a403  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a408  jmp     short loc_18001A423
0x18001a40a  mov     r9d, ebx; char *
0x18001a40d  mov     edx, 20Fh; void *
0x18001a412  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a419  mov     rcx, [rbp+5Fh]; this
0x18001a41d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a422  nop
0x18001a423  lea     rcx, [rbp+57h+var_98]
0x18001a427  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a42c  nop
0x18001a42d  lea     rcx, [rbp+57h+var_58]
0x18001a431  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a436  mov     eax, ebx
0x18001a438  mov     rcx, qword ptr [rbp+57h+var_38]
0x18001a43c  xor     rcx, rsp; StackCookie
0x18001a43f  call    __security_check_cookie
0x18001a444  movaps  xmm6, [rsp+0E0h+var_38+8]
0x18001a44c  add     rsp, 0C8h
0x18001a453  pop     rdi
0x18001a454  pop     rsi
0x18001a455  pop     rbx
0x18001a456  pop     rbp
0x18001a457  retn
```
