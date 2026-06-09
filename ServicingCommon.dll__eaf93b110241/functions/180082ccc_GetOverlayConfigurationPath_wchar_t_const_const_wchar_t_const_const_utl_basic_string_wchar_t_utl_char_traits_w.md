# GetOverlayConfigurationPath(wchar_t const * const,wchar_t const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180082ccc`
- end: `0x180082f27`
- name: `?GetOverlayConfigurationPath@@YAJQEB_W0AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008287c`

## callees

- `0x18001f5d4`
- `0x1800293a0`
- `0x18007ef14`
- `0x18007eff0`
- `0x18007f018`
- `0x18007f2b4`
- `0x180081ea4`
- `0x180082ccc`

## string_xrefs

- `0x180082d48`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082dbf`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082e6f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082d62`: `GetOverlayConfigurationPath`
- `0x180082dd9`: `GetOverlayConfigurationPath`
- `0x180082e89`: `GetOverlayConfigurationPath`

## pseudocode

```c
__int64 __fastcall GetOverlayConfigurationPath(_WORD *a1, const wchar_t *a2, __int64 a3)
{
  const wchar_t *v6; // rdx
  int v7; // ebx
  int v8; // edi
  _QWORD v10[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v14[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v15[8]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v16[2]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v17[8]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v18[2]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v19[8]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v20[2]; // [rsp+E8h] [rbp-18h] BYREF
  _WORD v21[8]; // [rsp+F8h] [rbp-8h] BYREF

  v18[0] = v19;
  v13 = 0;
  v19[0] = 0;
  v18[1] = v19;
  v6 = L"\\Windows\\WinSxS\\CIMs";
  if ( a2 && *a2 )
    v6 = a2;
  v21[0] = 0;
  v20[0] = v21;
  v20[1] = v21;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v20, v6) )
  {
    v15[0] = 0;
    v14[0] = v15;
    v14[1] = v15;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v14,
                             L"OVERLAY",
                             7) )
    {
      v11[2] = 1258;
      v11[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v11[1] = "GetOverlayConfigurationPath";
      v11[3] = "HiveName.assign(g_DefaultHiveName)";
      v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v13,
             v11,
             3221225495LL);
LABEL_8:
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v14);
      goto LABEL_19;
    }
    v8 = CombinePaths(v20, (__int64)v14, (__int64)v18);
    if ( v8 < 0 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v14);
      v7 = v8;
      goto LABEL_19;
    }
    if ( a1 && *a1 )
    {
      v17[0] = 0;
      v16[0] = v17;
      v16[1] = v17;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v16,
                               a1) )
      {
        v12[2] = 1265;
        v12[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v12[1] = "GetOverlayConfigurationPath";
        v12[3] = "LocalImageRoot.assign(ImageRoot)";
        v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v13,
               v12,
               3221225495LL);
LABEL_15:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v16);
        goto LABEL_8;
      }
      v7 = CombinePaths(v16, (__int64)v18, (__int64)v18);
      if ( v7 < 0 )
        goto LABEL_15;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v16);
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(a3, v18);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v14);
    v7 = 0;
    goto LABEL_19;
  }
  v10[2] = 1255;
  v10[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
  v10[1] = "GetOverlayConfigurationPath";
  v10[3] = "CimRootToUse.assign(CimRootPtr)";
  v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
         &v13,
         v10,
         3221225495LL);
LABEL_19:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v20);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180082ccc  push    rbp
0x180082cce  push    rbx
0x180082ccf  push    rsi
0x180082cd0  push    rdi
0x180082cd1  push    r14
0x180082cd3  lea     rbp, [rsp-10h]
0x180082cd8  sub     rsp, 110h
0x180082cdf  mov     rax, cs:__security_cookie
0x180082ce6  xor     rax, rsp
0x180082ce9  mov     [rbp+30h+var_28], rax
0x180082ced  xor     r14d, r14d
0x180082cf0  lea     rax, [rbp+30h+var_58]
0x180082cf4  mov     rsi, r8
0x180082cf7  mov     [rbp+30h+var_68], rax
0x180082cfb  mov     r8, rdx
0x180082cfe  mov     [rbp+30h+var_B0], r14d
0x180082d02  mov     [rbp+30h+var_58], r14w
0x180082d07  lea     rax, [rbp+30h+var_58]
0x180082d0b  mov     [rbp+30h+var_60], rax
0x180082d0f  mov     rbx, rcx
0x180082d12  lea     rdx, aWindowsWinsxsC; "\\Windows\\WinSxS\\CIMs"
0x180082d19  test    r8, r8
0x180082d1c  jz      short loc_180082D26
0x180082d1e  cmp     [r8], r14w
0x180082d22  cmovnz  rdx, r8
0x180082d26  lea     rax, [rbp+30h+var_38]
0x180082d2a  mov     [rbp+30h+var_38], r14w
0x180082d2f  mov     [rbp+30h+var_48], rax
0x180082d33  lea     rcx, [rbp+30h+var_48]
0x180082d37  lea     rax, [rbp+30h+var_38]
0x180082d3b  mov     [rbp+30h+var_40], rax
0x180082d3f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180082d44  test    al, al
0x180082d46  jnz     short loc_180082D90
0x180082d48  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082d4f  mov     [rsp+130h+var_100], 4E7h
0x180082d58  mov     [rsp+130h+var_110], rax
0x180082d5d  lea     rdx, [rsp+130h+var_110]
0x180082d62  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180082d69  mov     r8d, 0C0000017h
0x180082d6f  mov     [rsp+130h+var_108], rax
0x180082d74  lea     rcx, [rbp+30h+var_B0]
0x180082d78  lea     rax, aCimroottouseAs; "CimRootToUse.assign(CimRootPtr)"
0x180082d7f  mov     [rsp+130h+var_F8], rax
0x180082d84  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082d89  mov     ebx, eax
0x180082d8b  jmp     loc_180082EF8
0x180082d90  lea     rax, [rbp+30h+var_98]
0x180082d94  mov     [rbp+30h+var_98], r14w
0x180082d99  mov     [rbp+30h+var_A8], rax
0x180082d9d  lea     rdx, aOverlay; "OVERLAY"
0x180082da4  lea     rax, [rbp+30h+var_98]
0x180082da8  mov     r8d, 7
0x180082dae  lea     rcx, [rbp+30h+var_A8]
0x180082db2  mov     [rbp+30h+var_A0], rax
0x180082db6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180082dbb  test    al, al
0x180082dbd  jnz     short loc_180082E10
0x180082dbf  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082dc6  mov     [rsp+130h+var_E0], 4EAh
0x180082dcf  mov     [rsp+130h+var_F0], rax
0x180082dd4  lea     rdx, [rsp+130h+var_F0]
0x180082dd9  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180082de0  mov     r8d, 0C0000017h
0x180082de6  mov     [rsp+130h+var_E8], rax
0x180082deb  lea     rcx, [rbp+30h+var_B0]
0x180082def  lea     rax, aHivenameAssign; "HiveName.assign(g_DefaultHiveName)"
0x180082df6  mov     [rsp+130h+var_D8], rax
0x180082dfb  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082e00  mov     ebx, eax
0x180082e02  lea     rcx, [rbp+30h+var_A8]
0x180082e06  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082e0b  jmp     loc_180082EF8
0x180082e10  lea     r8, [rbp+30h+var_68]
0x180082e14  lea     rdx, [rbp+30h+var_A8]
0x180082e18  lea     rcx, [rbp+30h+var_48]
0x180082e1c  call    ?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180082e21  mov     edi, eax
0x180082e23  test    eax, eax
0x180082e25  jns     short loc_180082E37
0x180082e27  lea     rcx, [rbp+30h+var_A8]
0x180082e2b  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082e30  mov     ebx, edi
0x180082e32  jmp     loc_180082EF8
0x180082e37  test    rbx, rbx
0x180082e3a  jz      loc_180082EE0
0x180082e40  cmp     [rbx], r14w
0x180082e44  jz      loc_180082EE0
0x180082e4a  lea     rax, [rbp+30h+var_78]
0x180082e4e  mov     [rbp+30h+var_78], r14w
0x180082e53  mov     [rbp+30h+var_88], rax
0x180082e57  lea     rcx, [rbp+30h+var_88]
0x180082e5b  lea     rax, [rbp+30h+var_78]
0x180082e5f  mov     rdx, rbx
0x180082e62  mov     [rbp+30h+var_80], rax
0x180082e66  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180082e6b  test    al, al
0x180082e6d  jnz     short loc_180082EC0
0x180082e6f  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082e76  mov     [rsp+130h+var_C0], 4F1h
0x180082e7f  mov     [rsp+130h+var_D0], rax
0x180082e84  lea     rdx, [rsp+130h+var_D0]
0x180082e89  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180082e90  mov     r8d, 0C0000017h
0x180082e96  mov     [rsp+130h+var_C8], rax
0x180082e9b  lea     rcx, [rbp+30h+var_B0]
0x180082e9f  lea     rax, aLocalimageroot; "LocalImageRoot.assign(ImageRoot)"
0x180082ea6  mov     [rsp+130h+var_B8], rax
0x180082eab  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082eb0  mov     ebx, eax
0x180082eb2  lea     rcx, [rbp+30h+var_88]
0x180082eb6  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082ebb  jmp     loc_180082E02
0x180082ec0  lea     r8, [rbp+30h+var_68]
0x180082ec4  lea     rdx, [rbp+30h+var_68]
0x180082ec8  lea     rcx, [rbp+30h+var_88]
0x180082ecc  call    ?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180082ed1  lea     rcx, [rbp+30h+var_88]
0x180082ed5  mov     ebx, eax
0x180082ed7  test    eax, eax
0x180082ed9  js      short loc_180082EB6
0x180082edb  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082ee0  lea     rdx, [rbp+30h+var_68]
0x180082ee4  mov     rcx, rsi
0x180082ee7  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180082eec  lea     rcx, [rbp+30h+var_A8]
0x180082ef0  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082ef5  mov     ebx, r14d
0x180082ef8  lea     rcx, [rbp+30h+var_48]
0x180082efc  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082f01  lea     rcx, [rbp+30h+var_68]
0x180082f05  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180082f0a  mov     eax, ebx
0x180082f0c  mov     rcx, [rbp+30h+var_28]
0x180082f10  xor     rcx, rsp; StackCookie
0x180082f13  call    __security_check_cookie
0x180082f18  add     rsp, 110h
0x180082f1f  pop     r14
0x180082f21  pop     rdi
0x180082f22  pop     rsi
0x180082f23  pop     rbx
0x180082f24  pop     rbp
0x180082f25  retn
```
