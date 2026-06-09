# GetOverlayConfigurationPath(wchar_t const * const,wchar_t const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180081d64`
- end: `0x180081fbf`
- name: `?GetOverlayConfigurationPath@@YAJQEB_W0AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180081914`

## callees

- `0x18001f840`
- `0x18002d2b0`
- `0x18007df88`
- `0x18007e064`
- `0x18007e08c`
- `0x18007e328`
- `0x180080f3c`
- `0x180081d64`

## string_xrefs

- `0x180081de0`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081e57`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081f07`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081dfa`: `GetOverlayConfigurationPath`
- `0x180081e71`: `GetOverlayConfigurationPath`
- `0x180081f21`: `GetOverlayConfigurationPath`

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
0x180081d64  push    rbp
0x180081d66  push    rbx
0x180081d67  push    rsi
0x180081d68  push    rdi
0x180081d69  push    r14
0x180081d6b  lea     rbp, [rsp-10h]
0x180081d70  sub     rsp, 110h
0x180081d77  mov     rax, cs:__security_cookie
0x180081d7e  xor     rax, rsp
0x180081d81  mov     [rbp+30h+var_28], rax
0x180081d85  xor     r14d, r14d
0x180081d88  lea     rax, [rbp+30h+var_58]
0x180081d8c  mov     rsi, r8
0x180081d8f  mov     [rbp+30h+var_68], rax
0x180081d93  mov     r8, rdx
0x180081d96  mov     [rbp+30h+var_B0], r14d
0x180081d9a  mov     [rbp+30h+var_58], r14w
0x180081d9f  lea     rax, [rbp+30h+var_58]
0x180081da3  mov     [rbp+30h+var_60], rax
0x180081da7  mov     rbx, rcx
0x180081daa  lea     rdx, aWindowsWinsxsC; "\\Windows\\WinSxS\\CIMs"
0x180081db1  test    r8, r8
0x180081db4  jz      short loc_180081DBE
0x180081db6  cmp     [r8], r14w
0x180081dba  cmovnz  rdx, r8
0x180081dbe  lea     rax, [rbp+30h+var_38]
0x180081dc2  mov     [rbp+30h+var_38], r14w
0x180081dc7  mov     [rbp+30h+var_48], rax
0x180081dcb  lea     rcx, [rbp+30h+var_48]
0x180081dcf  lea     rax, [rbp+30h+var_38]
0x180081dd3  mov     [rbp+30h+var_40], rax
0x180081dd7  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180081ddc  test    al, al
0x180081dde  jnz     short loc_180081E28
0x180081de0  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081de7  mov     [rsp+130h+var_100], 4E7h
0x180081df0  mov     [rsp+130h+var_110], rax
0x180081df5  lea     rdx, [rsp+130h+var_110]
0x180081dfa  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180081e01  mov     r8d, 0C0000017h
0x180081e07  mov     [rsp+130h+var_108], rax
0x180081e0c  lea     rcx, [rbp+30h+var_B0]
0x180081e10  lea     rax, aCimroottouseAs; "CimRootToUse.assign(CimRootPtr)"
0x180081e17  mov     [rsp+130h+var_F8], rax
0x180081e1c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081e21  mov     ebx, eax
0x180081e23  jmp     loc_180081F90
0x180081e28  lea     rax, [rbp+30h+var_98]
0x180081e2c  mov     [rbp+30h+var_98], r14w
0x180081e31  mov     [rbp+30h+var_A8], rax
0x180081e35  lea     rdx, aOverlay; "OVERLAY"
0x180081e3c  lea     rax, [rbp+30h+var_98]
0x180081e40  mov     r8d, 7
0x180081e46  lea     rcx, [rbp+30h+var_A8]
0x180081e4a  mov     [rbp+30h+var_A0], rax
0x180081e4e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180081e53  test    al, al
0x180081e55  jnz     short loc_180081EA8
0x180081e57  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081e5e  mov     [rsp+130h+var_E0], 4EAh
0x180081e67  mov     [rsp+130h+var_F0], rax
0x180081e6c  lea     rdx, [rsp+130h+var_F0]
0x180081e71  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180081e78  mov     r8d, 0C0000017h
0x180081e7e  mov     [rsp+130h+var_E8], rax
0x180081e83  lea     rcx, [rbp+30h+var_B0]
0x180081e87  lea     rax, aHivenameAssign; "HiveName.assign(g_DefaultHiveName)"
0x180081e8e  mov     [rsp+130h+var_D8], rax
0x180081e93  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081e98  mov     ebx, eax
0x180081e9a  lea     rcx, [rbp+30h+var_A8]
0x180081e9e  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081ea3  jmp     loc_180081F90
0x180081ea8  lea     r8, [rbp+30h+var_68]
0x180081eac  lea     rdx, [rbp+30h+var_A8]
0x180081eb0  lea     rcx, [rbp+30h+var_48]
0x180081eb4  call    ?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180081eb9  mov     edi, eax
0x180081ebb  test    eax, eax
0x180081ebd  jns     short loc_180081ECF
0x180081ebf  lea     rcx, [rbp+30h+var_A8]
0x180081ec3  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081ec8  mov     ebx, edi
0x180081eca  jmp     loc_180081F90
0x180081ecf  test    rbx, rbx
0x180081ed2  jz      loc_180081F78
0x180081ed8  cmp     [rbx], r14w
0x180081edc  jz      loc_180081F78
0x180081ee2  lea     rax, [rbp+30h+var_78]
0x180081ee6  mov     [rbp+30h+var_78], r14w
0x180081eeb  mov     [rbp+30h+var_88], rax
0x180081eef  lea     rcx, [rbp+30h+var_88]
0x180081ef3  lea     rax, [rbp+30h+var_78]
0x180081ef7  mov     rdx, rbx
0x180081efa  mov     [rbp+30h+var_80], rax
0x180081efe  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180081f03  test    al, al
0x180081f05  jnz     short loc_180081F58
0x180081f07  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081f0e  mov     [rsp+130h+var_C0], 4F1h
0x180081f17  mov     [rsp+130h+var_D0], rax
0x180081f1c  lea     rdx, [rsp+130h+var_D0]
0x180081f21  lea     rax, aGetoverlayconf; "GetOverlayConfigurationPath"
0x180081f28  mov     r8d, 0C0000017h
0x180081f2e  mov     [rsp+130h+var_C8], rax
0x180081f33  lea     rcx, [rbp+30h+var_B0]
0x180081f37  lea     rax, aLocalimageroot; "LocalImageRoot.assign(ImageRoot)"
0x180081f3e  mov     [rsp+130h+var_B8], rax
0x180081f43  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081f48  mov     ebx, eax
0x180081f4a  lea     rcx, [rbp+30h+var_88]
0x180081f4e  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081f53  jmp     loc_180081E9A
0x180081f58  lea     r8, [rbp+30h+var_68]
0x180081f5c  lea     rdx, [rbp+30h+var_68]
0x180081f60  lea     rcx, [rbp+30h+var_88]
0x180081f64  call    ?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z; CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180081f69  lea     rcx, [rbp+30h+var_88]
0x180081f6d  mov     ebx, eax
0x180081f6f  test    eax, eax
0x180081f71  js      short loc_180081F4E
0x180081f73  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081f78  lea     rdx, [rbp+30h+var_68]
0x180081f7c  mov     rcx, rsi
0x180081f7f  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180081f84  lea     rcx, [rbp+30h+var_A8]
0x180081f88  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081f8d  mov     ebx, r14d
0x180081f90  lea     rcx, [rbp+30h+var_48]
0x180081f94  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081f99  lea     rcx, [rbp+30h+var_68]
0x180081f9d  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180081fa2  mov     eax, ebx
0x180081fa4  mov     rcx, [rbp+30h+var_28]
0x180081fa8  xor     rcx, rsp; StackCookie
0x180081fab  call    __security_check_cookie
0x180081fb0  add     rsp, 110h
0x180081fb7  pop     r14
0x180081fb9  pop     rdi
0x180081fba  pop     rsi
0x180081fbb  pop     rbx
0x180081fbc  pop     rbp
0x180081fbd  retn
```
