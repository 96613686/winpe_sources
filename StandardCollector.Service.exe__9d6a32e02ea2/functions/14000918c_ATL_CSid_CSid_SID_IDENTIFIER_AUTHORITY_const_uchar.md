# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x14000918c`
- end: `0x14000937a`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `494`
- prototype: `ATL::CSid *(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *, UCHAR, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400086fc`
- `0x140011b04`

## callees

- `0x140002b4c`
- `0x140002e74`
- `0x14000914c`
- `0x14000916c`
- `0x14000918c`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x140009278`
- `ADVAPI32!GetSidLengthRequired` at `0x140009278`
- `ADVAPI32!InitializeSid` at `0x140009292`
- `ADVAPI32!InitializeSid` at `0x140009292`
- `ADVAPI32!GetSidSubAuthority` at `0x1400092bd`
- `ADVAPI32!GetSidSubAuthority` at `0x1400092bd`
- `ADVAPI32!IsValidSid` at `0x1400092d3`
- `ADVAPI32!IsValidSid` at `0x1400092d3`
- `ADVAPI32!GetLengthSid` at `0x1400092e1`
- `ADVAPI32!GetLengthSid` at `0x1400092e1`
- `ADVAPI32!CopySid` at `0x1400092fd`
- `ADVAPI32!CopySid` at `0x1400092fd`

## pseudocode

```c
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v6; // rax
  struct ATL::IAtlStringMgr *v7; // rax
  struct ATL::IAtlStringMgr *v8; // rax
  DWORD v9; // esi
  UCHAR *p_nSubAuthorityCount; // r14
  DWORD v11; // ebx
  DWORD LengthSid; // eax
  int Error; // eax
  _BYTE Sid[80]; // [rsp+30h] [rbp-29h] BYREF
  UCHAR nSubAuthorityCount; // [rsp+D0h] [rbp+77h] BYREF

  nSubAuthorityCount = a3;
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = 0;
  *((_DWORD *)this + 20) = 7;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 11) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                         + 24;
  v6 = ATL::CAtlStringMgr::GetInstance();
  if ( !v6 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 12) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v6 + 24LL))(v6) + 24;
  v7 = ATL::CAtlStringMgr::GetInstance();
  if ( !v7 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 13) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v7 + 24LL))(v7) + 24;
  v8 = ATL::CAtlStringMgr::GetInstance();
  if ( !v8 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 14) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v8 + 24LL))(v8) + 24;
  if ( !nSubAuthorityCount || GetSidLengthRequired(nSubAuthorityCount) > 0x44 )
    goto LABEL_16;
  if ( !InitializeSid(Sid, a2, nSubAuthorityCount) )
    ATL::AtlThrowLastWin32();
  v9 = 0;
  if ( nSubAuthorityCount )
  {
    p_nSubAuthorityCount = &nSubAuthorityCount;
    do
    {
      p_nSubAuthorityCount += 8;
      v11 = *(_DWORD *)p_nSubAuthorityCount;
      *GetSidSubAuthority(Sid, v9++) = v11;
    }
    while ( v9 < nSubAuthorityCount );
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_16:
    ATL::AtlThrowImpl(-2147024809);
  _mm_lfence();
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
0x14000918c  mov     [rsp-8+nSubAuthorityCount], r8b
0x140009191  mov     [rsp-8+arg_18], r9
0x140009196  push    rbp
0x140009197  push    rbx
0x140009198  push    rsi
0x140009199  push    rdi
0x14000919a  push    r14
0x14000919c  lea     rbp, [rsp-37h]
0x1400091a1  sub     rsp, 90h
0x1400091a8  mov     rax, cs:__security_cookie
0x1400091af  xor     rax, rsp
0x1400091b2  mov     [rbp+57h+var_30], rax
0x1400091b6  mov     rbx, rdx
0x1400091b9  mov     rdi, rcx
0x1400091bc  mov     [rbp+57h+var_90], rcx
0x1400091c0  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1400091c7  mov     [rcx], rax
0x1400091ca  mov     byte ptr [rcx+4Ch], 0
0x1400091ce  mov     dword ptr [rcx+50h], 7
0x1400091d5  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400091da  mov     rcx, rax
0x1400091dd  test    rax, rax
0x1400091e0  jz      loc_140009348
0x1400091e6  mov     rax, [rax]
0x1400091e9  mov     rax, [rax+18h]
0x1400091ed  call    cs:__guard_dispatch_icall_fptr
0x1400091f3  add     rax, 18h
0x1400091f7  mov     [rdi+58h], rax
0x1400091fb  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140009200  mov     rcx, rax
0x140009203  test    rax, rax
0x140009206  jz      loc_140009353
0x14000920c  mov     rax, [rax]
0x14000920f  mov     rax, [rax+18h]
0x140009213  call    cs:__guard_dispatch_icall_fptr
0x140009219  add     rax, 18h
0x14000921d  mov     [rdi+60h], rax
0x140009221  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140009226  mov     rcx, rax
0x140009229  test    rax, rax
0x14000922c  jz      loc_14000935E
0x140009232  mov     rax, [rax]
0x140009235  mov     rax, [rax+18h]
0x140009239  call    cs:__guard_dispatch_icall_fptr
0x14000923f  add     rax, 18h
0x140009243  mov     [rdi+68h], rax
0x140009247  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000924c  mov     rcx, rax
0x14000924f  test    rax, rax
0x140009252  jz      loc_140009369
0x140009258  mov     rax, [rax]
0x14000925b  mov     rax, [rax+18h]
0x14000925f  call    cs:__guard_dispatch_icall_fptr
0x140009265  add     rax, 18h
0x140009269  mov     [rdi+70h], rax
0x14000926d  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x140009270  test    cl, cl
0x140009272  jz      loc_14000933D
0x140009278  call    cs:__imp_GetSidLengthRequired
0x14000927e  cmp     eax, 44h ; 'D'
0x140009281  ja      loc_14000933D
0x140009287  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x14000928b  mov     rdx, rbx; pIdentifierAuthority
0x14000928e  lea     rcx, [rbp+57h+Sid]; Sid
0x140009292  call    cs:__imp_InitializeSid
0x140009298  test    eax, eax
0x14000929a  jz      loc_140009374
0x1400092a0  lea     r14, [rbp+57h+arg_18]
0x1400092a4  xor     esi, esi
0x1400092a6  cmp     [rbp+57h+nSubAuthorityCount], sil
0x1400092aa  jbe     short loc_1400092CF
0x1400092ac  add     r14, 0FFFFFFFFFFFFFFF8h
0x1400092b0  lea     r14, [r14+8]
0x1400092b4  mov     ebx, [r14]
0x1400092b7  mov     edx, esi; nSubAuthority
0x1400092b9  lea     rcx, [rbp+57h+Sid]; pSid
0x1400092bd  call    cs:__imp_GetSidSubAuthority
0x1400092c3  mov     [rax], ebx
0x1400092c5  inc     esi
0x1400092c7  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x1400092cb  cmp     esi, eax
0x1400092cd  jb      short loc_1400092B0
0x1400092cf  lea     rcx, [rbp+57h+Sid]; pSid
0x1400092d3  call    cs:__imp_IsValidSid
0x1400092d9  test    eax, eax
0x1400092db  jz      short loc_14000933D
0x1400092dd  lea     rcx, [rbp+57h+Sid]; pSid
0x1400092e1  call    cs:__imp_GetLengthSid
0x1400092e7  cmp     eax, 44h ; 'D'
0x1400092ea  ja      short loc_14000933D
0x1400092ec  lfence
0x1400092ef  mov     byte ptr [rdi+4Ch], 1
0x1400092f3  lea     rdx, [rdi+8]; pDestinationSid
0x1400092f7  lea     r8, [rbp+57h+Sid]; pSourceSid
0x1400092fb  mov     ecx, eax; nDestinationSidLength
0x1400092fd  call    cs:__imp_CopySid
0x140009303  test    eax, eax
0x140009305  jz      short loc_14000932B
0x140009307  mov     dword ptr [rdi+50h], 8
0x14000930e  mov     rax, rdi
0x140009311  mov     rcx, [rbp+57h+var_30]
0x140009315  xor     rcx, rsp; StackCookie
0x140009318  call    __security_check_cookie
0x14000931d  add     rsp, 90h
0x140009324  pop     r14
0x140009326  pop     rdi
0x140009327  pop     rsi
0x140009328  pop     rbx
0x140009329  pop     rbp
0x14000932a  retn
0x14000932b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140009330  nop
0x140009331  mov     byte ptr [rdi+4Ch], 0
0x140009335  mov     ecx, eax; int
0x140009337  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000933d  mov     ecx, 80070057h; int
0x140009342  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009348  mov     ecx, 80004005h; int
0x14000934d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009353  mov     ecx, 80004005h; int
0x140009358  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000935e  mov     ecx, 80004005h; int
0x140009363  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009369  mov     ecx, 80004005h; int
0x14000936e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009374  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
