# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180037d00`
- end: `0x180037e4f`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `335`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800378b0`

## callees

- `0x180034d10`
- `0x180037d00`
- `0x1800b3620`
- `0x1800b365c`
- `0x1800cf8c0`
- `0x1800d60d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180037dc8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180037dc8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037e05`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037e05`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180037dec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180037dec`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037d7c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037d7c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180037d96`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180037d96`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180037dde`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180037dde`

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
    goto LABEL_12;
  if ( !InitializeSid(Sid, a2, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_12:
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
0x180037d00  mov     [rsp-8+nSubAuthorityCount], r8b
0x180037d05  mov     [rsp-8+arg_18], r9
0x180037d0a  push    rbp
0x180037d0b  push    rbx
0x180037d0c  push    rsi
0x180037d0d  push    rdi
0x180037d0e  push    r14
0x180037d10  lea     rbp, [rsp-37h]
0x180037d15  sub     rsp, 90h
0x180037d1c  mov     rax, cs:__security_cookie
0x180037d23  xor     rax, rsp
0x180037d26  mov     [rbp+57h+var_30], rax
0x180037d2a  mov     rbx, rdx
0x180037d2d  mov     rdi, rcx
0x180037d30  mov     [rbp+57h+var_90], rcx
0x180037d34  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180037d3b  mov     [rcx], rax
0x180037d3e  mov     byte ptr [rcx+4Ch], 0
0x180037d42  mov     dword ptr [rcx+50h], 7
0x180037d49  add     rcx, 58h ; 'X'
0x180037d4d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037d52  nop
0x180037d53  lea     rcx, [rdi+60h]
0x180037d57  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037d5c  nop
0x180037d5d  lea     rcx, [rdi+68h]
0x180037d61  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037d66  nop
0x180037d67  lea     rcx, [rdi+70h]
0x180037d6b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037d70  nop
0x180037d71  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180037d74  test    cl, cl
0x180037d76  jz      loc_180037E44
0x180037d7c  call    cs:__imp_GetSidLengthRequired
0x180037d82  cmp     eax, 44h ; 'D'
0x180037d85  ja      loc_180037E44
0x180037d8b  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180037d8f  mov     rdx, rbx; pIdentifierAuthority
0x180037d92  lea     rcx, [rbp+57h+Sid]; Sid
0x180037d96  call    cs:__imp_InitializeSid
0x180037d9c  test    eax, eax
0x180037d9e  jnz     short loc_180037DA6
0x180037da0  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180037da6  mov     [rbp+57h+var_88], 0
0x180037dae  lea     r14, [rbp+57h+arg_18]
0x180037db2  xor     esi, esi
0x180037db4  cmp     [rbp+57h+nSubAuthorityCount], sil
0x180037db8  jbe     short loc_180037DDA
0x180037dba  lea     r14, [r14+8]
0x180037dbe  mov     ebx, [r14-8]
0x180037dc2  mov     edx, esi; nSubAuthority
0x180037dc4  lea     rcx, [rbp+57h+Sid]; pSid
0x180037dc8  call    cs:__imp_GetSidSubAuthority
0x180037dce  mov     [rax], ebx
0x180037dd0  inc     esi
0x180037dd2  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x180037dd6  cmp     esi, eax
0x180037dd8  jb      short loc_180037DBA
0x180037dda  lea     rcx, [rbp+57h+Sid]; pSid
0x180037dde  call    cs:__imp_IsValidSid
0x180037de4  test    eax, eax
0x180037de6  jz      short loc_180037E44
0x180037de8  lea     rcx, [rbp+57h+Sid]; pSid
0x180037dec  call    cs:__imp_GetLengthSid
0x180037df2  cmp     eax, 44h ; 'D'
0x180037df5  ja      short loc_180037E44
0x180037df7  mov     byte ptr [rdi+4Ch], 1
0x180037dfb  lea     rdx, [rdi+8]; pDestinationSid
0x180037dff  lea     r8, [rbp+57h+Sid]; pSourceSid
0x180037e03  mov     ecx, eax; nDestinationSidLength
0x180037e05  call    cs:__imp_CopySid
0x180037e0b  test    eax, eax
0x180037e0d  jnz     short loc_180037E20
0x180037e0f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180037e14  mov     byte ptr [rdi+4Ch], 0
0x180037e18  mov     ecx, eax; int
0x180037e1a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180037e20  mov     dword ptr [rdi+50h], 8
0x180037e27  mov     rax, rdi
0x180037e2a  mov     rcx, [rbp+57h+var_30]
0x180037e2e  xor     rcx, rsp; StackCookie
0x180037e31  call    __security_check_cookie
0x180037e36  add     rsp, 90h
0x180037e3d  pop     r14
0x180037e3f  pop     rdi
0x180037e40  pop     rsi
0x180037e41  pop     rbx
0x180037e42  pop     rbp
0x180037e43  retn
0x180037e44  mov     ecx, 80070057h; int
0x180037e49  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
