# Windows::COM::CIdentityAuthority::Format<IDefinitionIdentity>(ulong,IDefinitionIdentity *,wchar_t * *)

- ea: `0x180077d4c`
- end: `0x180077ed8`
- name: `??$Format@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@PEAPEA_W@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180079390`

## callees

- `0x180002564`
- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180077d4c`
- `0x18007953c`
- `0x1800857b4`
- `0x18008597c`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180077dab`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077deb`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077dbe`: `Windows::COM::CIdentityAuthority::Format`
- `0x180077dfe`: `Windows::COM::CIdentityAuthority::Format`
- `0x180077dc9`: `Not-null check failed: pICOMIdentity`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Format<IDefinitionIdentity>(
        __int64 a1,
        unsigned int a2,
        Windows::COM *a3,
        _QWORD *a4)
{
  __int64 result; // rax
  struct Windows::Identity::Rtl::IRtlDefinitionIdentity **v7; // r8
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
    *a4 = 0;
  v14 = 0;
  result = Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapFormatFlags(a2, &v14);
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
    result = Windows::COM::ConvertIn(a3, (struct IDefinitionIdentity *)&v19, v7);
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
          v11 = Windows::COM::CopyOut((Windows::COM *)&v21, (unsigned __int64)a4, v13);
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
0x180077d4c  mov     [rsp-8+arg_0], rbx
0x180077d51  mov     [rsp-8+arg_8], rdi
0x180077d56  push    rbp
0x180077d57  lea     rbp, [rsp-57h]
0x180077d5c  sub     rsp, 90h
0x180077d63  mov     rax, cs:__security_cookie
0x180077d6a  xor     rax, rsp
0x180077d6d  mov     [rbp+57h+var_10], rax
0x180077d71  mov     dword ptr [rbp+57h+var_30], 0
0x180077d78  mov     rbx, r9
0x180077d7b  mov     rdi, r8
0x180077d7e  mov     eax, edx
0x180077d80  test    r9, r9
0x180077d83  jz      short loc_180077D8C
0x180077d85  mov     qword ptr [r9], 0
0x180077d8c  lea     rdx, [rbp+57h+var_60]
0x180077d90  mov     [rbp+57h+var_60], 0
0x180077d97  mov     ecx, eax
0x180077d99  call    ?MapFormatFlags@?$CCOMToRtlInterfaceMapper@UIDefinitionIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapFormatFlags(ulong,ulong *)
0x180077d9e  test    eax, eax
0x180077da0  js      loc_180077EB6
0x180077da6  test    rdi, rdi
0x180077da9  jnz     short loc_180077DE6
0x180077dab  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077db2  mov     [rbp+57h+var_48], 0C9h
0x180077dba  mov     [rbp+57h+var_58], rax
0x180077dbe  lea     rax, aWindowsComCide_7; "Windows::COM::CIdentityAuthority::Forma"...
0x180077dc5  mov     [rbp+57h+var_50], rax
0x180077dc9  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x180077dd0  lea     rdx, [rbp+57h+var_58]
0x180077dd4  mov     [rbp+57h+var_40], rax
0x180077dd8  lea     rcx, [rbp+57h+var_30]
0x180077ddc  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180077de1  jmp     loc_180077EB6
0x180077de6  test    rbx, rbx
0x180077de9  jnz     short loc_180077E12
0x180077deb  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077df2  mov     [rbp+57h+var_48], 0CAh
0x180077dfa  mov     [rbp+57h+var_58], rax
0x180077dfe  lea     rax, aWindowsComCide_7; "Windows::COM::CIdentityAuthority::Forma"...
0x180077e05  mov     [rbp+57h+var_50], rax
0x180077e09  lea     rax, aNotNullCheckFa_105; "Not-null check failed: ppszFormattedIde"...
0x180077e10  jmp     short loc_180077DD0
0x180077e12  lea     rdx, [rbp+57h+var_38]; struct IDefinitionIdentity *
0x180077e16  mov     [rbp+57h+var_38], 0
0x180077e1e  mov     rcx, rdi; this
0x180077e21  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x180077e26  test    eax, eax
0x180077e28  js      loc_180077EB6
0x180077e2e  lea     rdx, [rbp+57h+var_30]
0x180077e32  mov     [rbp+57h+var_30], 0
0x180077e3a  call    RtlGetIdentityAuthority
0x180077e3f  test    eax, eax
0x180077e41  jns     short loc_180077E4E
0x180077e43  mov     ecx, eax
0x180077e45  call    ConvertNtStatusToHResult
0x180077e4a  mov     ebx, eax
0x180077e4c  jmp     short loc_180077EAB
0x180077e4e  mov     rcx, [rbp+57h+var_30]
0x180077e52  lea     r9, [rbp+57h+var_28]
0x180077e56  mov     r8, [rbp+57h+var_38]
0x180077e5a  xor     eax, eax
0x180077e5c  mov     edx, [rbp+57h+var_60]
0x180077e5f  xorps   xmm0, xmm0
0x180077e62  mov     [rbp+57h+var_18], rax
0x180077e66  movups  [rbp+57h+var_28], xmm0
0x180077e6a  mov     rax, [rcx]
0x180077e6d  mov     rax, [rax+20h]
0x180077e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e76  test    eax, eax
0x180077e78  jns     short loc_180077E8E
0x180077e7a  mov     ecx, eax
0x180077e7c  call    ConvertNtStatusToHResult
0x180077e81  mov     ebx, eax
0x180077e83  lea     rcx, [rbp+57h+var_28]
0x180077e87  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180077e8c  jmp     short loc_180077EAB
0x180077e8e  mov     rdx, rbx; struct _LUNICODE_STRING *
0x180077e91  lea     rcx, [rbp+57h+var_28]; this
0x180077e95  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x180077e9a  lea     rcx, [rbp+57h+var_28]
0x180077e9e  mov     ebx, eax
0x180077ea0  test    eax, eax
0x180077ea2  js      short loc_180077E87
0x180077ea4  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180077ea9  xor     ebx, ebx
0x180077eab  lea     rcx, [rbp+57h+var_30]
0x180077eaf  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077eb4  mov     eax, ebx
0x180077eb6  mov     rcx, [rbp+57h+var_10]
0x180077eba  xor     rcx, rsp; StackCookie
0x180077ebd  call    __security_check_cookie
0x180077ec2  lea     r11, [rsp+90h+var_s0]
0x180077eca  mov     rbx, [r11+10h]
0x180077ece  mov     rdi, [r11+18h]
0x180077ed2  mov     rsp, r11
0x180077ed5  pop     rbp
0x180077ed6  retn
```
