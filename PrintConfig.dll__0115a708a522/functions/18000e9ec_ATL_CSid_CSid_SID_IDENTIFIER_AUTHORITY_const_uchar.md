# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x18000e9ec`
- end: `0x18000ebb8`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `460`
- prototype: `ATL::CSid *(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180015bc0`

## callees

- `0x180003400`
- `0x18000e9ec`
- `0x1800109c0`
- `0x1800109e8`
- `0x180010a10`
- `0x1801cb010`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x18000eabb`
- `ADVAPI32!GetSidLengthRequired` at `0x18000eabb`
- `ADVAPI32!InitializeSid` at `0x18000eadb`
- `ADVAPI32!InitializeSid` at `0x18000eadb`
- `ADVAPI32!GetSidSubAuthority` at `0x18000eb11`
- `ADVAPI32!GetSidSubAuthority` at `0x18000eb11`
- `ADVAPI32!CopySid` at `0x18000eb60`
- `ADVAPI32!CopySid` at `0x18000eb60`
- `ADVAPI32!GetLengthSid` at `0x18000eb41`
- `ADVAPI32!GetLengthSid` at `0x18000eb41`
- `ADVAPI32!IsValidSid` at `0x18000eb2d`
- `ADVAPI32!IsValidSid` at `0x18000eb2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  va_list v5; // r14
  DWORD i; // esi
  DWORD v7; // ebx
  DWORD LengthSid; // eax
  signed int Error; // eax
  _BYTE Sid[80]; // [rsp+40h] [rbp-29h] BYREF
  va_list va; // [rsp+E8h] [rbp+7Fh] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  *((_QWORD *)this + 11) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 12) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 13) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    goto LABEL_11;
  if ( !InitializeSid(Sid, a2, a3) )
    ATL::AtlThrowLastWin32();
  va_copy(v5, va);
  for ( i = 0; i < a3; *GetSidSubAuthority(Sid, i++) = v7 )
  {
    v5 += 8;
    v7 = *((_DWORD *)v5 - 2);
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_11:
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
0x18000e9ec  mov     [rsp-8+nSubAuthorityCount], r8b
0x18000e9f1  mov     [rsp-8+arg_18], r9
0x18000e9f6  push    rbp
0x18000e9f7  push    rbx
0x18000e9f8  push    rsi
0x18000e9f9  push    rdi
0x18000e9fa  push    r14
0x18000e9fc  lea     rbp, [rsp-37h]
0x18000ea01  sub     rsp, 0A0h
0x18000ea08  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18000ea10  mov     rax, cs:__security_cookie
0x18000ea17  xor     rax, rsp
0x18000ea1a  mov     [rbp+57h+var_30], rax
0x18000ea1e  mov     rbx, rdx
0x18000ea21  mov     rdi, rcx
0x18000ea24  mov     [rbp+57h+var_98], rcx
0x18000ea28  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000ea2f  mov     [rcx], rax
0x18000ea32  mov     byte ptr [rcx+4Ch], 0
0x18000ea36  mov     dword ptr [rcx+50h], 7
0x18000ea3d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ea44  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ea4b  mov     rcx, rsi
0x18000ea4e  mov     rax, [rax+18h]
0x18000ea52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea57  add     rax, 18h
0x18000ea5b  mov     [rdi+58h], rax
0x18000ea5f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ea66  mov     rcx, rsi
0x18000ea69  mov     rax, [rax+18h]
0x18000ea6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea72  add     rax, 18h
0x18000ea76  mov     [rdi+60h], rax
0x18000ea7a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ea81  mov     rcx, rsi
0x18000ea84  mov     rax, [rax+18h]
0x18000ea88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea8d  add     rax, 18h
0x18000ea91  mov     [rdi+68h], rax
0x18000ea95  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000ea9c  mov     rcx, rsi
0x18000ea9f  mov     rax, [rax+18h]
0x18000eaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaa8  add     rax, 18h
0x18000eaac  mov     [rdi+70h], rax
0x18000eab0  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x18000eab3  test    cl, cl
0x18000eab5  jz      loc_18000EBA7
0x18000eabb  call    cs:__imp_GetSidLengthRequired
0x18000eac2  nop     dword ptr [rax+rax+00h]
0x18000eac7  cmp     eax, 44h ; 'D'
0x18000eaca  ja      loc_18000EBA7
0x18000ead0  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x18000ead4  mov     rdx, rbx; pIdentifierAuthority
0x18000ead7  lea     rcx, [rbp+57h+Sid]; Sid
0x18000eadb  call    cs:__imp_InitializeSid
0x18000eae2  nop     dword ptr [rax+rax+00h]
0x18000eae7  test    eax, eax
0x18000eae9  jz      loc_18000EBB2
0x18000eaef  mov     [rbp+57h+var_90], 0
0x18000eaf7  lea     r14, [rbp+57h+arg_18]
0x18000eafb  xor     esi, esi
0x18000eafd  cmp     [rbp+57h+nSubAuthorityCount], sil
0x18000eb01  jbe     short loc_18000EB29
0x18000eb03  lea     r14, [r14+8]
0x18000eb07  mov     ebx, [r14-8]
0x18000eb0b  mov     edx, esi; nSubAuthority
0x18000eb0d  lea     rcx, [rbp+57h+Sid]; pSid
0x18000eb11  call    cs:__imp_GetSidSubAuthority
0x18000eb18  nop     dword ptr [rax+rax+00h]
0x18000eb1d  mov     [rax], ebx
0x18000eb1f  inc     esi
0x18000eb21  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x18000eb25  cmp     esi, eax
0x18000eb27  jb      short loc_18000EB03
0x18000eb29  lea     rcx, [rbp+57h+Sid]; pSid
0x18000eb2d  call    cs:__imp_IsValidSid
0x18000eb34  nop     dword ptr [rax+rax+00h]
0x18000eb39  test    eax, eax
0x18000eb3b  jz      short loc_18000EBA7
0x18000eb3d  lea     rcx, [rbp+57h+Sid]; pSid
0x18000eb41  call    cs:__imp_GetLengthSid
0x18000eb48  nop     dword ptr [rax+rax+00h]
0x18000eb4d  cmp     eax, 44h ; 'D'
0x18000eb50  ja      short loc_18000EBA7
0x18000eb52  mov     byte ptr [rdi+4Ch], 1
0x18000eb56  lea     rdx, [rdi+8]; pDestinationSid
0x18000eb5a  lea     r8, [rbp+57h+Sid]; pSourceSid
0x18000eb5e  mov     ecx, eax; nDestinationSidLength
0x18000eb60  call    cs:__imp_CopySid
0x18000eb67  nop     dword ptr [rax+rax+00h]
0x18000eb6c  test    eax, eax
0x18000eb6e  jz      short loc_18000EB95
0x18000eb70  mov     dword ptr [rdi+50h], 8
0x18000eb77  mov     rax, rdi
0x18000eb7a  mov     rcx, [rbp+57h+var_30]
0x18000eb7e  xor     rcx, rsp; StackCookie
0x18000eb81  call    __security_check_cookie
0x18000eb86  add     rsp, 0A0h
0x18000eb8d  pop     r14
0x18000eb8f  pop     rdi
0x18000eb90  pop     rsi
0x18000eb91  pop     rbx
0x18000eb92  pop     rbp
0x18000eb93  retn
0x18000eb95  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000eb9a  nop
0x18000eb9b  mov     byte ptr [rdi+4Ch], 0
0x18000eb9f  mov     ecx, eax; int
0x18000eba1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000eba7  mov     ecx, 80070057h; int
0x18000ebac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ebb2  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
