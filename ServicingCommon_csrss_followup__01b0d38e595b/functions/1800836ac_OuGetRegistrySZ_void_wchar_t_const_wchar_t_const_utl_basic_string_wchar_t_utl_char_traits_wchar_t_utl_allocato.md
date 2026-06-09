# OuGetRegistrySZ(void *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool *)

- ea: `0x1800836ac`
- end: `0x18008383e`
- name: `?OuGetRegistrySZ@@YAJPEAXPEB_W1PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_N@Z`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180081ffc`
- `0x180082e0c`

## callees

- `0x18001f840`
- `0x18002d2b0`
- `0x18007cb18`
- `0x18007e08c`
- `0x1800836ac`
- `0x1800843a4`

## string_xrefs

- `0x180083706`: `RelativePath`
- `0x18008374c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008378c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800837d3`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180083763`: `OuGetRegistrySZ`
- `0x1800837a3`: `OuGetRegistrySZ`
- `0x1800837ea`: `OuGetRegistrySZ`

## pseudocode

```c
__int64 __fastcall OuGetRegistrySZ(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  _WORD *v6; // rcx
  int RegistryValue; // ebx
  _QWORD *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r8
  unsigned int v13; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v14[4]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v15[4]; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v16[4]; // [rsp+88h] [rbp+7h] BYREF
  int v17; // [rsp+A8h] [rbp+27h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+2Fh] BYREF

  v17 = 0;
  v6 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  *v6 = 0;
  if ( a5 )
    *a5 = 0;
  v18 = 0;
  v13 = 0;
  RegistryValue = OuGetRegistryValue(a1, (__int64)L"RelativePath", a1, 1, &v18, &v13, a5);
  if ( RegistryValue >= 0 )
  {
    if ( !a5 || !*a5 )
    {
      if ( (v13 & 1) != 0 )
      {
        v14[2] = 601;
        v14[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v9 = v14;
        v14[3] = 0;
        v14[1] = "OuGetRegistrySZ";
LABEL_8:
        v10 = 3221227787LL;
LABEL_9:
        RegistryValue = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                          &v17,
                          v9,
                          v10);
        goto LABEL_17;
      }
      if ( !v13 )
      {
        v15[2] = 607;
        v15[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v9 = v15;
        v15[3] = 0;
        v15[1] = "OuGetRegistrySZ";
        goto LABEL_8;
      }
      v11 = (v13 >> 1) - 1;
      if ( *(_WORD *)(v18 + 2 * v11) )
        v11 = v13 >> 1;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a4,
                               v18,
                               v11) )
      {
        v16[2] = 623;
        v16[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v9 = v16;
        v10 = 3221225495LL;
        v16[1] = "OuGetRegistrySZ";
        v16[3] = "Value->assign( StringBuffer, ValueLengthChars)";
        goto LABEL_9;
      }
    }
    RegistryValue = 0;
  }
LABEL_17:
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v18);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x1800836ac  mov     [rsp-8+arg_8], rbx
0x1800836b1  mov     [rsp-8+arg_10], rsi
0x1800836b6  push    rbp
0x1800836b7  push    rdi
0x1800836b8  push    r14
0x1800836ba  lea     rbp, [rsp-3Fh]
0x1800836bf  sub     rsp, 0C0h
0x1800836c6  mov     rax, cs:__security_cookie
0x1800836cd  xor     rax, rsp
0x1800836d0  mov     [rbp+4Fh+var_18], rax
0x1800836d4  mov     rdi, [rbp+4Fh+arg_20]
0x1800836d8  xor     r14d, r14d
0x1800836db  mov     [rbp+4Fh+var_28], r14d
0x1800836df  mov     r8, rcx
0x1800836e2  mov     rcx, [r9]
0x1800836e5  mov     rsi, r9
0x1800836e8  mov     [r9+8], rcx
0x1800836ec  mov     [rcx], r14w
0x1800836f0  test    rdi, rdi
0x1800836f3  jz      short loc_1800836F8
0x1800836f5  mov     [rdi], r14b
0x1800836f8  lea     rax, [rbp+4Fh+var_90]
0x1800836fc  mov     [rsp+0D0h+var_A0], rdi
0x180083701  mov     [rsp+0D0h+var_A8], rax
0x180083706  lea     rdx, aRelativepath; "RelativePath"
0x18008370d  lea     rax, [rbp+4Fh+var_20]
0x180083711  mov     [rbp+4Fh+var_20], r14
0x180083715  mov     r9d, 1
0x18008371b  mov     [rsp+0D0h+var_B0], rax
0x180083720  mov     rcx, r8
0x180083723  mov     [rbp+4Fh+var_90], r14d
0x180083727  call    ?OuGetRegistryValue@@YAJPEAXPEB_W1KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@PEAKPEA_N@Z; OuGetRegistryValue(void *,wchar_t const *,wchar_t const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &,ulong *,bool *)
0x18008372c  mov     ebx, eax
0x18008372e  test    eax, eax
0x180083730  js      loc_18008380E
0x180083736  test    rdi, rdi
0x180083739  jz      short loc_180083744
0x18008373b  cmp     [rdi], r14b
0x18008373e  jnz     loc_18008380B
0x180083744  mov     ecx, [rbp+4Fh+var_90]
0x180083747  test    cl, 1
0x18008374a  jz      short loc_180083788
0x18008374c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180083753  mov     [rbp+4Fh+var_78], 259h
0x18008375b  mov     [rbp+4Fh+var_88], rax
0x18008375f  lea     rdx, [rbp+4Fh+var_88]
0x180083763  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x18008376a  mov     [rbp+4Fh+var_70], r14
0x18008376e  mov     [rbp+4Fh+var_80], rax
0x180083772  mov     r8d, 0C000090Bh
0x180083778  lea     rcx, [rbp+4Fh+var_28]
0x18008377c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180083781  mov     ebx, eax
0x180083783  jmp     loc_18008380E
0x180083788  test    ecx, ecx
0x18008378a  jnz     short loc_1800837B4
0x18008378c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180083793  mov     [rbp+4Fh+var_58], 25Fh
0x18008379b  mov     [rbp+4Fh+var_68], rax
0x18008379f  lea     rdx, [rbp+4Fh+var_68]
0x1800837a3  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x1800837aa  mov     [rbp+4Fh+var_50], r14
0x1800837ae  mov     [rbp+4Fh+var_60], rax
0x1800837b2  jmp     short loc_180083772
0x1800837b4  mov     rdx, [rbp+4Fh+var_20]
0x1800837b8  shr     ecx, 1
0x1800837ba  lea     r8d, [rcx-1]
0x1800837be  cmp     [rdx+r8*2], r14w
0x1800837c3  cmovnz  r8d, ecx
0x1800837c7  mov     rcx, rsi
0x1800837ca  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800837cf  test    al, al
0x1800837d1  jnz     short loc_18008380B
0x1800837d3  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800837da  mov     [rbp+4Fh+var_38], 26Fh
0x1800837e2  mov     [rbp+4Fh+var_48], rax
0x1800837e6  lea     rdx, [rbp+4Fh+var_48]
0x1800837ea  lea     rax, aOugetregistrys; "OuGetRegistrySZ"
0x1800837f1  mov     r8d, 0C0000017h
0x1800837f7  mov     [rbp+4Fh+var_40], rax
0x1800837fb  lea     rax, aValueAssignStr; "Value->assign( StringBuffer, ValueLengt"...
0x180083802  mov     [rbp+4Fh+var_30], rax
0x180083806  jmp     loc_180083778
0x18008380b  mov     ebx, r14d
0x18008380e  lea     rcx, [rbp+4Fh+var_20]
0x180083812  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180083817  mov     eax, ebx
0x180083819  mov     rcx, [rbp+4Fh+var_18]
0x18008381d  xor     rcx, rsp; StackCookie
0x180083820  call    __security_check_cookie
0x180083825  lea     r11, [rsp+0D0h+var_10]
0x18008382d  mov     rbx, [r11+28h]
0x180083831  mov     rsi, [r11+30h]
0x180083835  mov     rsp, r11
0x180083838  pop     r14
0x18008383a  pop     rdi
0x18008383b  pop     rbp
0x18008383c  retn
```
