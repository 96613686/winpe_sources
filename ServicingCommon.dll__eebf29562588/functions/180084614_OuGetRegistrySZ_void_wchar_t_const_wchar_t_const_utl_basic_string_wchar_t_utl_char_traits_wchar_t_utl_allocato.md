# OuGetRegistrySZ(void *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool *)

- ea: `0x180084614`
- end: `0x1800847a6`
- name: `?OuGetRegistrySZ@@YAJPEAXPEB_W1PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_N@Z`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180082f64`
- `0x180083d74`

## callees

- `0x18001f5d4`
- `0x1800293a0`
- `0x18007dab4`
- `0x18007f018`
- `0x180084614`
- `0x18008530c`

## string_xrefs

- `0x18008466e`: `RelativePath`
- `0x1800846b4`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800846f4`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008473b`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800846cb`: `OuGetRegistrySZ`
- `0x18008470b`: `OuGetRegistrySZ`
- `0x180084752`: `OuGetRegistrySZ`

## pseudocode

```c
__int64 __fastcall OuGetRegistrySZ(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  _WORD *v6; // rcx
  const struct std::nothrow_t *v8; // rdx
  int RegistryValue; // ebx
  _QWORD *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r8
  unsigned int v14; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v16[4]; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v17[4]; // [rsp+88h] [rbp+7h] BYREF
  int v18; // [rsp+A8h] [rbp+27h] BYREF
  _WORD *v19; // [rsp+B0h] [rbp+2Fh] BYREF

  v18 = 0;
  v6 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v6 = 0;
  if ( a5 )
    *a5 = 0;
  v19 = 0;
  v14 = 0;
  RegistryValue = OuGetRegistryValue(a1, (__int64)L"RelativePath", a1, 1, (void **)&v19, &v14, a5);
  if ( RegistryValue >= 0 )
  {
    if ( !a5 || !*a5 )
    {
      if ( (v14 & 1) != 0 )
      {
        v15[2] = 601;
        v15[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v10 = v15;
        v15[3] = 0;
        v15[1] = "OuGetRegistrySZ";
LABEL_8:
        v11 = 3221227787LL;
LABEL_9:
        RegistryValue = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                          &v18,
                          v10,
                          v11);
        goto LABEL_17;
      }
      if ( !v14 )
      {
        v16[2] = 607;
        v16[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v10 = v16;
        v16[3] = 0;
        v16[1] = "OuGetRegistrySZ";
        goto LABEL_8;
      }
      v12 = (v14 >> 1) - 1;
      if ( v19[v12] )
        v12 = v14 >> 1;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a4,
                               v19,
                               v12) )
      {
        v17[2] = 623;
        v17[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v10 = v17;
        v11 = 3221225495LL;
        v17[1] = "OuGetRegistrySZ";
        v17[3] = "Value->assign( StringBuffer, ValueLengthChars)";
        goto LABEL_9;
      }
    }
    RegistryValue = 0;
  }
LABEL_17:
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(
    (void **)&v19,
    v8);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x180084614  mov     [rsp-8+arg_8], rbx
0x180084619  mov     [rsp-8+arg_10], rsi
0x18008461e  push    rbp
0x18008461f  push    rdi
0x180084620  push    r14
0x180084622  lea     rbp, [rsp-3Fh]
0x180084627  sub     rsp, 0C0h
0x18008462e  mov     rax, cs:__security_cookie
0x180084635  xor     rax, rsp
0x180084638  mov     [rbp+4Fh+var_18], rax
0x18008463c  mov     rdi, [rbp+4Fh+arg_20]
0x180084640  xor     r14d, r14d
0x180084643  mov     [rbp+4Fh+var_28], r14d
0x180084647  mov     r8, rcx
0x18008464a  mov     rcx, [r9]
0x18008464d  mov     rsi, r9
0x180084650  mov     [r9+8], rcx
0x180084654  mov     [rcx], r14w
0x180084658  test    rdi, rdi
0x18008465b  jz      short loc_180084660
0x18008465d  mov     [rdi], r14b
0x180084660  lea     rax, [rbp+4Fh+var_90]
0x180084664  mov     [rsp+0D0h+var_A0], rdi
0x180084669  mov     [rsp+0D0h+var_A8], rax
0x18008466e  lea     rdx, aRelativepath; "RelativePath"
0x180084675  lea     rax, [rbp+4Fh+var_20]
0x180084679  mov     [rbp+4Fh+var_20], r14
0x18008467d  mov     r9d, 1
0x180084683  mov     [rsp+0D0h+var_B0], rax
0x180084688  mov     rcx, r8
0x18008468b  mov     [rbp+4Fh+var_90], r14d
0x18008468f  call    ?OuGetRegistryValue@@YAJPEAXPEB_W1KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@PEAKPEA_N@Z; OuGetRegistryValue(void *,wchar_t const *,wchar_t const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &,ulong *,bool *)
0x180084694  mov     ebx, eax
0x180084696  test    eax, eax
0x180084698  js      loc_180084776
0x18008469e  test    rdi, rdi
0x1800846a1  jz      short loc_1800846AC
0x1800846a3  cmp     [rdi], r14b
0x1800846a6  jnz     loc_180084773
0x1800846ac  mov     ecx, [rbp+4Fh+var_90]
0x1800846af  test    cl, 1
0x1800846b2  jz      short loc_1800846F0
0x1800846b4  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800846bb  mov     [rbp+4Fh+var_78], 259h
0x1800846c3  mov     [rbp+4Fh+var_88], rax
0x1800846c7  lea     rdx, [rbp+4Fh+var_88]
0x1800846cb  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x1800846d2  mov     [rbp+4Fh+var_70], r14
0x1800846d6  mov     [rbp+4Fh+var_80], rax
0x1800846da  mov     r8d, 0C000090Bh
0x1800846e0  lea     rcx, [rbp+4Fh+var_28]
0x1800846e4  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800846e9  mov     ebx, eax
0x1800846eb  jmp     loc_180084776
0x1800846f0  test    ecx, ecx
0x1800846f2  jnz     short loc_18008471C
0x1800846f4  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800846fb  mov     [rbp+4Fh+var_58], 25Fh
0x180084703  mov     [rbp+4Fh+var_68], rax
0x180084707  lea     rdx, [rbp+4Fh+var_68]
0x18008470b  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x180084712  mov     [rbp+4Fh+var_50], r14
0x180084716  mov     [rbp+4Fh+var_60], rax
0x18008471a  jmp     short loc_1800846DA
0x18008471c  mov     rdx, [rbp+4Fh+var_20]
0x180084720  shr     ecx, 1
0x180084722  lea     r8d, [rcx-1]
0x180084726  cmp     [rdx+r8*2], r14w
0x18008472b  cmovnz  r8d, ecx
0x18008472f  mov     rcx, rsi
0x180084732  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180084737  test    al, al
0x180084739  jnz     short loc_180084773
0x18008473b  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180084742  mov     [rbp+4Fh+var_38], 26Fh
0x18008474a  mov     [rbp+4Fh+var_48], rax
0x18008474e  lea     rdx, [rbp+4Fh+var_48]
0x180084752  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x180084759  mov     r8d, 0C0000017h
0x18008475f  mov     [rbp+4Fh+var_40], rax
0x180084763  lea     rax, aValueAssignStr; "Value->assign( StringBuffer, ValueLengt"...
0x18008476a  mov     [rbp+4Fh+var_30], rax
0x18008476e  jmp     loc_1800846E0
0x180084773  mov     ebx, r14d
0x180084776  lea     rcx, [rbp+4Fh+var_20]
0x18008477a  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008477f  mov     eax, ebx
0x180084781  mov     rcx, [rbp+4Fh+var_18]
0x180084785  xor     rcx, rsp; StackCookie
0x180084788  call    __security_check_cookie
0x18008478d  lea     r11, [rsp+0D0h+var_10]
0x180084795  mov     rbx, [r11+28h]
0x180084799  mov     rsi, [r11+30h]
0x18008479d  mov     rsp, r11
0x1800847a0  pop     r14
0x1800847a2  pop     rdi
0x1800847a3  pop     rbp
0x1800847a4  retn
```
