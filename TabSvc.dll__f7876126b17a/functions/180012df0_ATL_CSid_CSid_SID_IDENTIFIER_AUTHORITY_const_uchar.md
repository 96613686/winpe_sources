# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180012df0`
- end: `0x180012fae`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `446`
- prototype: `ATL::CSid *(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800108f0`

## callees

- `0x180012df0`
- `0x180019ddc`
- `0x180019e00`
- `0x18001a5e0`
- `0x18001bbe0`
- `0x180031010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012f62`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012f62`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012f48`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012f48`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012f39`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012f39`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180012ec3`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180012ec3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180012f1e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180012f1e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180012ee3`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180012ee3`

## pseudocode

```c
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  va_list v5; // rbp
  DWORD i; // esi
  DWORD v7; // ebx
  DWORD LengthSid; // eax
  int Error; // eax
  _BYTE Sid[80]; // [rsp+30h] [rbp-88h] BYREF
  va_list va; // [rsp+D8h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  *((_QWORD *)this + 11) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 12) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 13) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
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
0x180012df0  mov     [rsp+arg_10], r8b
0x180012df5  mov     [rsp+arg_18], r9
0x180012dfa  push    rbx
0x180012dfb  push    rbp
0x180012dfc  push    rsi
0x180012dfd  push    rdi
0x180012dfe  sub     rsp, 98h
0x180012e05  mov     rax, cs:__security_cookie
0x180012e0c  xor     rax, rsp
0x180012e0f  mov     [rsp+0B8h+var_38], rax
0x180012e17  mov     rbx, rdx
0x180012e1a  mov     rdi, rcx
0x180012e1d  mov     [rsp+0B8h+var_98], rcx
0x180012e22  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180012e29  mov     [rcx], rax
0x180012e2c  mov     byte ptr [rcx+4Ch], 0
0x180012e30  mov     dword ptr [rcx+50h], 7
0x180012e37  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e3e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e45  mov     rax, [rax+18h]
0x180012e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e4e  add     rax, 18h
0x180012e52  mov     [rdi+58h], rax
0x180012e56  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e5d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e64  mov     rax, [rax+18h]
0x180012e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e6d  add     rax, 18h
0x180012e71  mov     [rdi+60h], rax
0x180012e75  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e7c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e83  mov     rax, [rax+18h]
0x180012e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e8c  add     rax, 18h
0x180012e90  mov     [rdi+68h], rax
0x180012e94  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012e9b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012ea2  mov     rax, [rax+18h]
0x180012ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eab  add     rax, 18h
0x180012eaf  mov     [rdi+70h], rax
0x180012eb3  movzx   ecx, [rsp+0B8h+arg_10]; nSubAuthorityCount
0x180012ebb  test    cl, cl
0x180012ebd  jz      loc_180012FA3
0x180012ec3  call    cs:__imp_GetSidLengthRequired
0x180012ec9  cmp     eax, 44h ; 'D'
0x180012ecc  ja      loc_180012FA3
0x180012ed2  movzx   r8d, [rsp+0B8h+arg_10]; nSubAuthorityCount
0x180012edb  mov     rdx, rbx; pIdentifierAuthority
0x180012ede  lea     rcx, [rsp+0B8h+Sid]; Sid
0x180012ee3  call    cs:__imp_InitializeSid
0x180012ee9  test    eax, eax
0x180012eeb  jnz     short loc_180012EF3
0x180012eed  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180012ef3  mov     [rsp+0B8h+var_90], 0
0x180012efc  lea     rbp, [rsp+0B8h+arg_18]
0x180012f04  xor     esi, esi
0x180012f06  cmp     [rsp+0B8h+arg_10], sil
0x180012f0e  jbe     short loc_180012F34
0x180012f10  lea     rbp, [rbp+8]
0x180012f14  mov     ebx, [rbp-8]
0x180012f17  mov     edx, esi; nSubAuthority
0x180012f19  lea     rcx, [rsp+0B8h+Sid]; pSid
0x180012f1e  call    cs:__imp_GetSidSubAuthority
0x180012f24  mov     [rax], ebx
0x180012f26  inc     esi
0x180012f28  movzx   eax, [rsp+0B8h+arg_10]
0x180012f30  cmp     esi, eax
0x180012f32  jb      short loc_180012F10
0x180012f34  lea     rcx, [rsp+0B8h+Sid]; pSid
0x180012f39  call    cs:__imp_IsValidSid
0x180012f3f  test    eax, eax
0x180012f41  jz      short loc_180012FA3
0x180012f43  lea     rcx, [rsp+0B8h+Sid]; pSid
0x180012f48  call    cs:__imp_GetLengthSid
0x180012f4e  cmp     eax, 44h ; 'D'
0x180012f51  ja      short loc_180012FA3
0x180012f53  mov     byte ptr [rdi+4Ch], 1
0x180012f57  lea     rdx, [rdi+8]; pDestinationSid
0x180012f5b  lea     r8, [rsp+0B8h+Sid]; pSourceSid
0x180012f60  mov     ecx, eax; nDestinationSidLength
0x180012f62  call    cs:__imp_CopySid
0x180012f68  test    eax, eax
0x180012f6a  jnz     short loc_180012F7D
0x180012f6c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012f71  mov     byte ptr [rdi+4Ch], 0
0x180012f75  mov     ecx, eax; int
0x180012f77  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012f7d  mov     dword ptr [rdi+50h], 8
0x180012f84  mov     rax, rdi
0x180012f87  mov     rcx, [rsp+0B8h+var_38]
0x180012f8f  xor     rcx, rsp; StackCookie
0x180012f92  call    __security_check_cookie
0x180012f97  add     rsp, 98h
0x180012f9e  pop     rdi
0x180012f9f  pop     rsi
0x180012fa0  pop     rbp
0x180012fa1  pop     rbx
0x180012fa2  retn
0x180012fa3  mov     ecx, 80070057h; int
0x180012fa8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
