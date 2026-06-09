# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180011dc4`
- end: `0x180011f0f`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `331`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x180011dc4`
- `0x180011f18`
- `0x18002bd78`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x180031960`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011eca`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011eca`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180011e52`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180011e52`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180011e3c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180011e3c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011eb1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011eb1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180011e98`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180011e98`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180011e82`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180011e82`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  va_list v5; // r14
  DWORD i; // esi
  DWORD v7; // ebx
  DWORD LengthSid; // eax
  int Error; // eax
  _BYTE Sid[80]; // [rsp+30h] [rbp-29h] BYREF
  va_list va; // [rsp+D8h] [rbp+7Fh] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 112);
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    goto LABEL_7;
  if ( !InitializeSid(Sid, a2, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_7:
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, Sid) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(Error);
  }
  *((_DWORD *)this + 20) = 8;
  return this;
}

```

## disassembly

```asm
0x180011dc4  mov     [rsp-8+nSubAuthorityCount], r8b
0x180011dc9  mov     [rsp-8+arg_18], r9
0x180011dce  push    rbp
0x180011dcf  push    rbx
0x180011dd0  push    rsi
0x180011dd1  push    rdi
0x180011dd2  push    r14
0x180011dd4  lea     rbp, [rsp-37h]
0x180011dd9  sub     rsp, 90h
0x180011de0  mov     rax, cs:__security_cookie
0x180011de7  xor     rax, rsp
0x180011dea  mov     [rbp+57h+var_30], rax
0x180011dee  mov     rbx, rdx
0x180011df1  mov     rdi, rcx
0x180011df4  mov     [rbp+57h+var_90], rcx
0x180011df8  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180011dff  mov     [rcx], rax
0x180011e02  mov     byte ptr [rcx+4Ch], 0
0x180011e06  mov     dword ptr [rcx+50h], 7
0x180011e0d  add     rcx, 58h ; 'X'
0x180011e11  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011e16  nop
0x180011e17  lea     rcx, [rdi+60h]
0x180011e1b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011e20  nop
0x180011e21  lea     rcx, [rdi+68h]
0x180011e25  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011e2a  nop
0x180011e2b  lea     rcx, [rdi+70h]
0x180011e2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011e34  nop
0x180011e35  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180011e38  test    cl, cl
0x180011e3a  jz      short loc_180011EA2
0x180011e3c  call    cs:__imp_GetSidLengthRequired
0x180011e42  cmp     eax, 44h ; 'D'
0x180011e45  ja      short loc_180011EA2
0x180011e47  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180011e4b  mov     rdx, rbx; pIdentifierAuthority
0x180011e4e  lea     rcx, [rbp+57h+Sid]; Sid
0x180011e52  call    cs:__imp_InitializeSid
0x180011e58  test    eax, eax
0x180011e5a  jz      loc_180011EF8
0x180011e60  mov     [rbp+57h+var_88], 0
0x180011e68  lea     r14, [rbp+57h+arg_18]
0x180011e6c  xor     esi, esi
0x180011e6e  cmp     [rbp+57h+nSubAuthorityCount], sil
0x180011e72  jbe     short loc_180011E94
0x180011e74  lea     r14, [r14+8]
0x180011e78  mov     ebx, [r14-8]
0x180011e7c  mov     edx, esi; nSubAuthority
0x180011e7e  lea     rcx, [rbp+57h+Sid]; pSid
0x180011e82  call    cs:__imp_GetSidSubAuthority
0x180011e88  mov     [rax], ebx
0x180011e8a  inc     esi
0x180011e8c  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x180011e90  cmp     esi, eax
0x180011e92  jb      short loc_180011E74
0x180011e94  lea     rcx, [rbp+57h+Sid]; pSid
0x180011e98  call    cs:__imp_IsValidSid
0x180011e9e  test    eax, eax
0x180011ea0  jnz     short loc_180011EAD
0x180011ea2  mov     ecx, 80070057h; int
0x180011ea7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011ead  lea     rcx, [rbp+57h+Sid]; pSid
0x180011eb1  call    cs:__imp_GetLengthSid
0x180011eb7  cmp     eax, 44h ; 'D'
0x180011eba  ja      short loc_180011EA2
0x180011ebc  mov     byte ptr [rdi+4Ch], 1
0x180011ec0  lea     rdx, [rdi+8]; pDestinationSid
0x180011ec4  lea     r8, [rbp+57h+Sid]; pSourceSid
0x180011ec8  mov     ecx, eax; nDestinationSidLength
0x180011eca  call    cs:__imp_CopySid
0x180011ed0  test    eax, eax
0x180011ed2  jz      short loc_180011EFE
0x180011ed4  mov     dword ptr [rdi+50h], 8
0x180011edb  mov     rax, rdi
0x180011ede  mov     rcx, [rbp+57h+var_30]
0x180011ee2  xor     rcx, rsp; StackCookie
0x180011ee5  call    __security_check_cookie
0x180011eea  add     rsp, 90h
0x180011ef1  pop     r14
0x180011ef3  pop     rdi
0x180011ef4  pop     rsi
0x180011ef5  pop     rbx
0x180011ef6  pop     rbp
0x180011ef7  retn
0x180011ef8  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180011efe  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011f03  mov     byte ptr [rdi+4Ch], 0
0x180011f07  mov     ecx, eax; int
0x180011f09  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
