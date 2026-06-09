# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x140008554`
- end: `0x1400086f3`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `415`
- prototype: `ATL::CSid *(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, ...)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000a5a0`
- `0x140039e78`
- `0x140039f30`
- `0x140039fac`

## callees

- `0x140004280`
- `0x140008554`
- `0x14000a220`
- `0x14000a2e8`
- `0x14000a310`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140008689`
- `ADVAPI32!GetLengthSid` at `0x140008689`
- `ADVAPI32!IsValidSid` at `0x14000867b`
- `ADVAPI32!IsValidSid` at `0x14000867b`
- `ADVAPI32!InitializeSid` at `0x140008635`
- `ADVAPI32!InitializeSid` at `0x140008635`
- `ADVAPI32!CopySid` at `0x1400086a2`
- `ADVAPI32!CopySid` at `0x1400086a2`
- `ADVAPI32!GetSidLengthRequired` at `0x14000861b`
- `ADVAPI32!GetSidLengthRequired` at `0x14000861b`
- `ADVAPI32!GetSidSubAuthority` at `0x140008665`
- `ADVAPI32!GetSidSubAuthority` at `0x140008665`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
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
0x140008554  mov     [rsp-8+nSubAuthorityCount], r8b
0x140008559  mov     [rsp-8+arg_18], r9
0x14000855e  push    rbp
0x14000855f  push    rbx
0x140008560  push    rsi
0x140008561  push    rdi
0x140008562  push    r14
0x140008564  lea     rbp, [rsp-37h]
0x140008569  sub     rsp, 90h
0x140008570  mov     rax, cs:__security_cookie
0x140008577  xor     rax, rsp
0x14000857a  mov     [rbp+57h+var_30], rax
0x14000857e  mov     rbx, rdx
0x140008581  mov     rdi, rcx
0x140008584  mov     [rbp+57h+var_90], rcx
0x140008588  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x14000858f  mov     [rcx], rax
0x140008592  mov     byte ptr [rcx+4Ch], 0
0x140008596  mov     dword ptr [rcx+50h], 7
0x14000859d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400085a4  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400085ab  mov     rcx, rsi
0x1400085ae  mov     rax, [rax+18h]
0x1400085b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085b7  add     rax, 18h
0x1400085bb  mov     [rdi+58h], rax
0x1400085bf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400085c6  mov     rcx, rsi
0x1400085c9  mov     rax, [rax+18h]
0x1400085cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085d2  add     rax, 18h
0x1400085d6  mov     [rdi+60h], rax
0x1400085da  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400085e1  mov     rcx, rsi
0x1400085e4  mov     rax, [rax+18h]
0x1400085e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085ed  add     rax, 18h
0x1400085f1  mov     [rdi+68h], rax
0x1400085f5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400085fc  mov     rcx, rsi
0x1400085ff  mov     rax, [rax+18h]
0x140008603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008608  add     rax, 18h
0x14000860c  mov     [rdi+70h], rax
0x140008610  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x140008613  test    cl, cl
0x140008615  jz      loc_1400086E2
0x14000861b  call    cs:__imp_GetSidLengthRequired
0x140008621  cmp     eax, 44h ; 'D'
0x140008624  ja      loc_1400086E2
0x14000862a  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x14000862e  mov     rdx, rbx; pIdentifierAuthority
0x140008631  lea     rcx, [rbp+57h+Sid]; Sid
0x140008635  call    cs:__imp_InitializeSid
0x14000863b  test    eax, eax
0x14000863d  jz      loc_1400086ED
0x140008643  mov     [rbp+57h+var_88], 0
0x14000864b  lea     r14, [rbp+57h+arg_18]
0x14000864f  xor     esi, esi
0x140008651  cmp     [rbp+57h+nSubAuthorityCount], sil
0x140008655  jbe     short loc_140008677
0x140008657  lea     r14, [r14+8]
0x14000865b  mov     ebx, [r14-8]
0x14000865f  mov     edx, esi; nSubAuthority
0x140008661  lea     rcx, [rbp+57h+Sid]; pSid
0x140008665  call    cs:__imp_GetSidSubAuthority
0x14000866b  mov     [rax], ebx
0x14000866d  inc     esi
0x14000866f  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x140008673  cmp     esi, eax
0x140008675  jb      short loc_140008657
0x140008677  lea     rcx, [rbp+57h+Sid]; pSid
0x14000867b  call    cs:__imp_IsValidSid
0x140008681  test    eax, eax
0x140008683  jz      short loc_1400086E2
0x140008685  lea     rcx, [rbp+57h+Sid]; pSid
0x140008689  call    cs:__imp_GetLengthSid
0x14000868f  cmp     eax, 44h ; 'D'
0x140008692  ja      short loc_1400086E2
0x140008694  mov     byte ptr [rdi+4Ch], 1
0x140008698  lea     rdx, [rdi+8]; pDestinationSid
0x14000869c  lea     r8, [rbp+57h+Sid]; pSourceSid
0x1400086a0  mov     ecx, eax; nDestinationSidLength
0x1400086a2  call    cs:__imp_CopySid
0x1400086a8  test    eax, eax
0x1400086aa  jz      short loc_1400086D0
0x1400086ac  mov     dword ptr [rdi+50h], 8
0x1400086b3  mov     rax, rdi
0x1400086b6  mov     rcx, [rbp+57h+var_30]
0x1400086ba  xor     rcx, rsp; StackCookie
0x1400086bd  call    __security_check_cookie
0x1400086c2  add     rsp, 90h
0x1400086c9  pop     r14
0x1400086cb  pop     rdi
0x1400086cc  pop     rsi
0x1400086cd  pop     rbx
0x1400086ce  pop     rbp
0x1400086cf  retn
0x1400086d0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400086d5  nop
0x1400086d6  mov     byte ptr [rdi+4Ch], 0
0x1400086da  mov     ecx, eax; int
0x1400086dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400086e2  mov     ecx, 80070057h; int
0x1400086e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400086ed  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
