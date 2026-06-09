# Windows::COM::CIdentityAuthority::Format<IReferenceIdentity>(ulong,IReferenceIdentity *,wchar_t * *)

- ea: `0x180077ee0`
- end: `0x18007806c`
- name: `??$Format@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIReferenceIdentity@@PEAPEA_W@Z`
- size: `396`
- prototype: `__int64 __fastcall(__int64, unsigned int, Windows::COM *, const struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180079ab0`

## callees

- `0x180002564`
- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180077ee0`
- `0x1800795bc`
- `0x1800857b4`
- `0x180085a38`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180077f3f`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077f7f`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077f52`: `Windows::COM::CIdentityAuthority::Format`
- `0x180077f92`: `Windows::COM::CIdentityAuthority::Format`
- `0x180077f5d`: `Not-null check failed: pICOMIdentity`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Format<IReferenceIdentity>(
        __int64 a1,
        unsigned int a2,
        Windows::COM *a3,
        const struct _LUNICODE_STRING *a4)
{
  __int64 result; // rax
  struct Windows::Identity::Rtl::IRtlReferenceIdentity **v7; // r8
  const char *v8; // rax
  __int64 v9; // rcx
  int IdentityAuthority; // eax
  int v11; // ebx
  int v12; // eax
  wchar_t **v13; // r8
  unsigned int v14; // [rsp+30h] [rbp-9h] BYREF
  const char *v15; // [rsp+38h] [rbp-1h] BYREF
  const char *v16; // [rsp+40h] [rbp+7h]
  __int64 v17; // [rsp+48h] [rbp+Fh]
  const char *v18; // [rsp+50h] [rbp+17h]
  __int64 v19; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v20; // [rsp+60h] [rbp+27h] BYREF
  __int128 v21; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v22; // [rsp+78h] [rbp+3Fh]

  LODWORD(v20) = 0;
  if ( a4 )
    *(_QWORD *)a4 = 0;
  v14 = 0;
  result = Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapFormatFlags(a2, &v14);
  if ( (int)result >= 0 )
  {
    if ( !a3 )
    {
      v17 = 201;
      v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v16 = "Windows::COM::CIdentityAuthority::Format";
      v8 = "Not-null check failed: pICOMIdentity";
LABEL_6:
      v18 = v8;
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v20,
               &v15);
    }
    if ( !a4 )
    {
      v17 = 202;
      v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v16 = "Windows::COM::CIdentityAuthority::Format";
      v8 = "Not-null check failed: ppszFormattedIdentity";
      goto LABEL_6;
    }
    v19 = 0;
    result = Windows::COM::ConvertIn(a3, (struct IReferenceIdentity *)&v19, v7);
    if ( (int)result >= 0 )
    {
      v20 = 0;
      IdentityAuthority = RtlGetIdentityAuthority(v9, &v20);
      if ( IdentityAuthority >= 0 )
      {
        v22 = 0;
        v21 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *))(*(_QWORD *)v20 + 32LL))(
                v20,
                v14,
                v19,
                &v21);
        if ( v12 >= 0 )
        {
          v11 = Windows::COM::CopyOut((Windows::COM *)&v21, a4, v13);
          if ( v11 >= 0 )
          {
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
            v11 = 0;
            goto LABEL_17;
          }
        }
        else
        {
          v11 = ConvertNtStatusToHResult((unsigned int)v12);
        }
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
      }
      else
      {
        v11 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
      }
LABEL_17:
      Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v20);
      return (unsigned int)v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180077ee0  mov     [rsp-8+arg_0], rbx
0x180077ee5  mov     [rsp-8+arg_8], rdi
0x180077eea  push    rbp
0x180077eeb  lea     rbp, [rsp-57h]
0x180077ef0  sub     rsp, 90h
0x180077ef7  mov     rax, cs:__security_cookie
0x180077efe  xor     rax, rsp
0x180077f01  mov     [rbp+57h+var_10], rax
0x180077f05  mov     dword ptr [rbp+57h+var_30], 0
0x180077f0c  mov     rbx, r9
0x180077f0f  mov     rdi, r8
0x180077f12  mov     eax, edx
0x180077f14  test    r9, r9
0x180077f17  jz      short loc_180077F20
0x180077f19  mov     qword ptr [r9], 0
0x180077f20  lea     rdx, [rbp+57h+var_60]
0x180077f24  mov     [rbp+57h+var_60], 0
0x180077f2b  mov     ecx, eax
0x180077f2d  call    ?MapFormatFlags@?$CCOMToRtlInterfaceMapper@UIReferenceIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapFormatFlags(ulong,ulong *)
0x180077f32  test    eax, eax
0x180077f34  js      loc_18007804A
0x180077f3a  test    rdi, rdi
0x180077f3d  jnz     short loc_180077F7A
0x180077f3f  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077f46  mov     [rbp+57h+var_48], 0C9h
0x180077f4e  mov     [rbp+57h+var_58], rax
0x180077f52  lea     rax, aWindowsComCide_7; "Windows::COM::CIdentityAuthority::Forma"...
0x180077f59  mov     [rbp+57h+var_50], rax
0x180077f5d  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x180077f64  lea     rdx, [rbp+57h+var_58]
0x180077f68  mov     [rbp+57h+var_40], rax
0x180077f6c  lea     rcx, [rbp+57h+var_30]
0x180077f70  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180077f75  jmp     loc_18007804A
0x180077f7a  test    rbx, rbx
0x180077f7d  jnz     short loc_180077FA6
0x180077f7f  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077f86  mov     [rbp+57h+var_48], 0CAh
0x180077f8e  mov     [rbp+57h+var_58], rax
0x180077f92  lea     rax, aWindowsComCide_7; "Windows::COM::CIdentityAuthority::Forma"...
0x180077f99  mov     [rbp+57h+var_50], rax
0x180077f9d  lea     rax, aNotNullCheckFa_105; "Not-null check failed: ppszFormattedIde"...
0x180077fa4  jmp     short loc_180077F64
0x180077fa6  lea     rdx, [rbp+57h+var_38]; struct IReferenceIdentity *
0x180077faa  mov     [rbp+57h+var_38], 0
0x180077fb2  mov     rcx, rdi; this
0x180077fb5  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x180077fba  test    eax, eax
0x180077fbc  js      loc_18007804A
0x180077fc2  lea     rdx, [rbp+57h+var_30]
0x180077fc6  mov     [rbp+57h+var_30], 0
0x180077fce  call    RtlGetIdentityAuthority
0x180077fd3  test    eax, eax
0x180077fd5  jns     short loc_180077FE2
0x180077fd7  mov     ecx, eax
0x180077fd9  call    ConvertNtStatusToHResult
0x180077fde  mov     ebx, eax
0x180077fe0  jmp     short loc_18007803F
0x180077fe2  mov     rcx, [rbp+57h+var_30]
0x180077fe6  lea     r9, [rbp+57h+var_28]
0x180077fea  mov     r8, [rbp+57h+var_38]
0x180077fee  xor     eax, eax
0x180077ff0  mov     edx, [rbp+57h+var_60]
0x180077ff3  xorps   xmm0, xmm0
0x180077ff6  mov     [rbp+57h+var_18], rax
0x180077ffa  movups  [rbp+57h+var_28], xmm0
0x180077ffe  mov     rax, [rcx]
0x180078001  mov     rax, [rax+20h]
0x180078005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007800a  test    eax, eax
0x18007800c  jns     short loc_180078022
0x18007800e  mov     ecx, eax
0x180078010  call    ConvertNtStatusToHResult
0x180078015  mov     ebx, eax
0x180078017  lea     rcx, [rbp+57h+var_28]
0x18007801b  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180078020  jmp     short loc_18007803F
0x180078022  mov     rdx, rbx; struct _LUNICODE_STRING *
0x180078025  lea     rcx, [rbp+57h+var_28]; this
0x180078029  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x18007802e  lea     rcx, [rbp+57h+var_28]
0x180078032  mov     ebx, eax
0x180078034  test    eax, eax
0x180078036  js      short loc_18007801B
0x180078038  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18007803d  xor     ebx, ebx
0x18007803f  lea     rcx, [rbp+57h+var_30]
0x180078043  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078048  mov     eax, ebx
0x18007804a  mov     rcx, [rbp+57h+var_10]
0x18007804e  xor     rcx, rsp; StackCookie
0x180078051  call    __security_check_cookie
0x180078056  lea     r11, [rsp+90h+var_s0]
0x18007805e  mov     rbx, [r11+10h]
0x180078062  mov     rdi, [r11+18h]
0x180078066  mov     rsp, r11
0x180078069  pop     rbp
0x18007806a  retn
```
