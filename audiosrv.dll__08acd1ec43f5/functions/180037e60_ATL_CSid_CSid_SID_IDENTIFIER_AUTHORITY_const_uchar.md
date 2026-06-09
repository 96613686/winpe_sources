# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180037e60`
- end: `0x180037faf`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `335`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037a10`

## callees

- `0x180034e70`
- `0x180037e60`
- `0x1800b1930`
- `0x1800b196c`
- `0x1800cd8d0`
- `0x1800d40e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180037f28`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180037f28`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037f65`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037f65`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180037f4c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180037f4c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037edc`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037edc`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180037ef6`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180037ef6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180037f3e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180037f3e`

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
0x180037e60  mov     [rsp-8+nSubAuthorityCount], r8b
0x180037e65  mov     [rsp-8+arg_18], r9
0x180037e6a  push    rbp
0x180037e6b  push    rbx
0x180037e6c  push    rsi
0x180037e6d  push    rdi
0x180037e6e  push    r14
0x180037e70  lea     rbp, [rsp-37h]
0x180037e75  sub     rsp, 90h
0x180037e7c  mov     rax, cs:__security_cookie
0x180037e83  xor     rax, rsp
0x180037e86  mov     [rbp+57h+var_30], rax
0x180037e8a  mov     rbx, rdx
0x180037e8d  mov     rdi, rcx
0x180037e90  mov     [rbp+57h+var_90], rcx
0x180037e94  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180037e9b  mov     [rcx], rax
0x180037e9e  mov     byte ptr [rcx+4Ch], 0
0x180037ea2  mov     dword ptr [rcx+50h], 7
0x180037ea9  add     rcx, 58h ; 'X'
0x180037ead  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037eb2  nop
0x180037eb3  lea     rcx, [rdi+60h]
0x180037eb7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037ebc  nop
0x180037ebd  lea     rcx, [rdi+68h]
0x180037ec1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037ec6  nop
0x180037ec7  lea     rcx, [rdi+70h]
0x180037ecb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180037ed0  nop
0x180037ed1  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180037ed4  test    cl, cl
0x180037ed6  jz      loc_180037FA4
0x180037edc  call    cs:__imp_GetSidLengthRequired
0x180037ee2  cmp     eax, 44h ; 'D'
0x180037ee5  ja      loc_180037FA4
0x180037eeb  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180037eef  mov     rdx, rbx; pIdentifierAuthority
0x180037ef2  lea     rcx, [rbp+57h+Sid]; Sid
0x180037ef6  call    cs:__imp_InitializeSid
0x180037efc  test    eax, eax
0x180037efe  jnz     short loc_180037F06
0x180037f00  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180037f06  mov     [rbp+57h+var_88], 0
0x180037f0e  lea     r14, [rbp+57h+arg_18]
0x180037f12  xor     esi, esi
0x180037f14  cmp     [rbp+57h+nSubAuthorityCount], sil
0x180037f18  jbe     short loc_180037F3A
0x180037f1a  lea     r14, [r14+8]
0x180037f1e  mov     ebx, [r14-8]
0x180037f22  mov     edx, esi; nSubAuthority
0x180037f24  lea     rcx, [rbp+57h+Sid]; pSid
0x180037f28  call    cs:__imp_GetSidSubAuthority
0x180037f2e  mov     [rax], ebx
0x180037f30  inc     esi
0x180037f32  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x180037f36  cmp     esi, eax
0x180037f38  jb      short loc_180037F1A
0x180037f3a  lea     rcx, [rbp+57h+Sid]; pSid
0x180037f3e  call    cs:__imp_IsValidSid
0x180037f44  test    eax, eax
0x180037f46  jz      short loc_180037FA4
0x180037f48  lea     rcx, [rbp+57h+Sid]; pSid
0x180037f4c  call    cs:__imp_GetLengthSid
0x180037f52  cmp     eax, 44h ; 'D'
0x180037f55  ja      short loc_180037FA4
0x180037f57  mov     byte ptr [rdi+4Ch], 1
0x180037f5b  lea     rdx, [rdi+8]; pDestinationSid
0x180037f5f  lea     r8, [rbp+57h+Sid]; pSourceSid
0x180037f63  mov     ecx, eax; nDestinationSidLength
0x180037f65  call    cs:__imp_CopySid
0x180037f6b  test    eax, eax
0x180037f6d  jnz     short loc_180037F80
0x180037f6f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180037f74  mov     byte ptr [rdi+4Ch], 0
0x180037f78  mov     ecx, eax; int
0x180037f7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180037f80  mov     dword ptr [rdi+50h], 8
0x180037f87  mov     rax, rdi
0x180037f8a  mov     rcx, [rbp+57h+var_30]
0x180037f8e  xor     rcx, rsp; StackCookie
0x180037f91  call    __security_check_cookie
0x180037f96  add     rsp, 90h
0x180037f9d  pop     r14
0x180037f9f  pop     rdi
0x180037fa0  pop     rsi
0x180037fa1  pop     rbx
0x180037fa2  pop     rbp
0x180037fa3  retn
0x180037fa4  mov     ecx, 80070057h; int
0x180037fa9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
