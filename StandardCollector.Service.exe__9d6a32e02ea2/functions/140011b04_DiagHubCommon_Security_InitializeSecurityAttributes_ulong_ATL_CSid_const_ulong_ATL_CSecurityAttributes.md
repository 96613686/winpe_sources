# DiagHubCommon::Security::InitializeSecurityAttributes(ulong,ATL::CSid const &,ulong,ATL::CSecurityAttributes *)

- ea: `0x140011b04`
- end: `0x140011caf`
- name: `?InitializeSecurityAttributes@Security@DiagHubCommon@@SAJKAEBVCSid@ATL@@KPEAVCSecurityAttributes@4@@Z`
- size: `427`
- prototype: `__int64 __fastcall(__int64, const struct ATL::CSid *, __int64, struct ATL::CSecurityAttributes *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400086fc`

## callees

- `0x140002e74`
- `0x14000918c`
- `0x1400093b4`
- `0x1400094c0`
- `0x140011b04`
- `0x140011cb0`
- `0x1400121e0`
- `0x140012610`
- `0x140012710`
- `0x1400137e0`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall DiagHubCommon::Security::InitializeSecurityAttributes(
        __int64 a1,
        const struct ATL::CSid *a2,
        __int64 a3,
        struct ATL::CSecurityAttributes *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  unsigned __int8 v8; // r9
  bool v9; // si
  unsigned int v10; // r8d
  unsigned __int8 v11; // r9
  bool v12; // r8
  unsigned int v14; // ecx
  int v15; // [rsp+34h] [rbp-F4h] BYREF
  _BYTE v16[128]; // [rsp+40h] [rbp-E8h] BYREF
  void **v17; // [rsp+C0h] [rbp-68h] BYREF
  struct _SECURITY_DESCRIPTOR *v18; // [rsp+C8h] [rbp-60h]
  _QWORD v19[2]; // [rsp+D0h] [rbp-58h] BYREF
  int v20; // [rsp+E0h] [rbp-48h]
  int v21; // [rsp+E4h] [rbp-44h]
  __int128 v22; // [rsp+E8h] [rbp-40h]
  __int64 v23; // [rsp+F8h] [rbp-30h]
  __int64 v24; // [rsp+100h] [rbp-28h]

  try
  {
    v6 = 0;
    v17 = &ATL::CSecurityDesc::`vftable';
    v18 = 0;
    v20 = 0;
    v24 = 0;
    v19[1] = 0;
    v21 = 2;
    v19[0] = &ATL::CDacl::`vftable';
    v22 = 0;
    v23 = 0;
    ATL::CSid::CSid(
      (ATL::CSid *)v16,
      (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
      2u,
      32,
      544);
    v9 = ATL::CDacl::AddAllowedAce((ATL::CDacl *)v19, (const struct ATL::CSid *)v16, v7, v8);
    ATL::CSid::~CSid((ATL::CSid *)v16);
    if ( !v9 )
      ATL::AtlThrowImpl(-2147023559);
    if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)v19, a2, v10, v11) )
      ATL::AtlThrowImpl(-2147023559);
    ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)&v17, (const struct ATL::CDacl *)v19, v12);
    if ( (void ***)((char *)a4 + 24) != &v17 )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)a4 + 3) + 8LL))((char *)a4 + 24);
      if ( v18 )
        ATL::CSecurityDesc::Init((struct ATL::CSecurityAttributes *)((char *)a4 + 24), v18);
    }
    *(_DWORD *)a4 = 24;
    *((_QWORD *)a4 + 1) = *((_QWORD *)a4 + 4);
    *((_DWORD *)a4 + 4) = 0;
    ATL::CDacl::~CDacl((ATL::CDacl *)v19);
    v17 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v17);
  }
  catch ( ATL::CAtlException v15 )
  {
    v14 = -2147467259;
    if ( v15 < 0 )
      return (unsigned int)v15;
    return v14;
  }
  v6 = 0;
}

```

## disassembly

```asm
0x140011b04  mov     r11, rsp
0x140011b07  mov     [r11+8], rbx
0x140011b0b  mov     [r11+18h], rsi
0x140011b0f  push    rdi
0x140011b10  push    r14
0x140011b12  push    r15
0x140011b14  sub     rsp, 110h
0x140011b1b  mov     rax, cs:__security_cookie
0x140011b22  xor     rax, rsp
0x140011b25  mov     [rsp+128h+var_20], rax
0x140011b2d  mov     rdi, r9
0x140011b30  mov     r14, rdx
0x140011b33  xor     ebx, ebx
0x140011b35  xorps   xmm0, xmm0
0x140011b38  movups  xmmword ptr [r11-68h], xmm0
0x140011b3d  lea     r15, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x140011b44  mov     [r11-68h], r15
0x140011b48  mov     [r11-60h], rbx
0x140011b4c  xor     eax, eax
0x140011b4e  movups  xmmword ptr [r11-58h], xmm0
0x140011b53  movups  xmmword ptr [r11-48h], xmm0
0x140011b58  movups  xmmword ptr [r11-38h], xmm0
0x140011b5d  mov     [r11-28h], rax
0x140011b61  mov     [r11-50h], rbx
0x140011b65  mov     [r11-48h], bl
0x140011b69  lea     r8d, [rbx+2]; unsigned __int8
0x140011b6d  mov     [r11-44h], r8d
0x140011b71  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x140011b78  mov     [r11-58h], rax
0x140011b7c  movdqu  xmmword ptr [r11-40h], xmm0
0x140011b82  mov     [r11-30h], rbx
0x140011b86  mov     [r11-28h], ebx
0x140011b8a  mov     [rsp+128h+var_108], 220h
0x140011b92  lea     r9d, [rbx+20h]
0x140011b96  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x140011b9d  lea     rcx, [rsp+128h+var_E8]; this
0x140011ba2  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x140011ba7  nop
0x140011ba8  lea     rdx, [rsp+128h+var_E8]; struct ATL::CSid *
0x140011bad  lea     rcx, [rsp+128h+var_58]; this
0x140011bb5  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140011bba  mov     sil, al
0x140011bbd  lea     rcx, [rsp+128h+var_E8]; this
0x140011bc2  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140011bc7  test    sil, sil
0x140011bca  jz      loc_140011C99
0x140011bd0  mov     rdx, r14; struct ATL::CSid *
0x140011bd3  lea     rcx, [rsp+128h+var_58]; this
0x140011bdb  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140011be0  test    al, al
0x140011be2  jz      loc_140011CA3
0x140011be8  lea     rdx, [rsp+128h+var_58]; struct ATL::CDacl *
0x140011bf0  lea     rcx, [rsp+128h+var_68]; this
0x140011bf8  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x140011bfd  lea     rsi, [rdi+18h]
0x140011c01  lea     rax, [rsp+128h+var_68]
0x140011c09  cmp     rsi, rax
0x140011c0c  jz      short loc_140011C33
0x140011c0e  mov     rax, [rsi]
0x140011c11  mov     rcx, rsi
0x140011c14  mov     rax, [rax+8]
0x140011c18  call    cs:__guard_dispatch_icall_fptr
0x140011c1e  mov     rdx, [rsp+128h+var_60]; struct _SECURITY_DESCRIPTOR *
0x140011c26  test    rdx, rdx
0x140011c29  jz      short loc_140011C33
0x140011c2b  mov     rcx, rsi; this
0x140011c2e  call    ?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z; ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)
0x140011c33  mov     dword ptr [rdi], 18h
0x140011c39  mov     rax, [rdi+20h]
0x140011c3d  mov     [rdi+8], rax
0x140011c41  mov     [rdi+10h], ebx
0x140011c44  lea     rcx, [rsp+128h+var_58]; this
0x140011c4c  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x140011c51  nop
0x140011c52  mov     [rsp+128h+var_68], r15
0x140011c5a  lea     rcx, [rsp+128h+var_68]; this
0x140011c62  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x140011c67  nop
0x140011c68  jmp     short loc_140011C6E
0x140011c6a  mov     ebx, [rsp+128h+var_F8]
0x140011c6e  mov     eax, ebx
0x140011c70  mov     rcx, [rsp+128h+var_20]
0x140011c78  xor     rcx, rsp; StackCookie
0x140011c7b  call    __security_check_cookie
0x140011c80  lea     r11, [rsp+128h+var_18]
0x140011c88  mov     rbx, [r11+20h]
0x140011c8c  mov     rsi, [r11+30h]
0x140011c90  mov     rsp, r11
0x140011c93  pop     r15
0x140011c95  pop     r14
0x140011c97  pop     rdi
0x140011c98  retn
0x140011c99  mov     ecx, 80070539h; int
0x140011c9e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011ca3  mov     ecx, 80070539h; int
0x140011ca8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
