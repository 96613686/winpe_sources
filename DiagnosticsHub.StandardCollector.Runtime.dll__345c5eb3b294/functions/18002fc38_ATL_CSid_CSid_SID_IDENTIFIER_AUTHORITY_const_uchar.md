# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x18002fc38`
- end: `0x18002fe26`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `494`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002da4c`
- `0x18002dfd0`
- `0x18002eb3c`

## callees

- `0x180002604`
- `0x18000288c`
- `0x18002fc38`
- `0x180031264`
- `0x18003151c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18002fd8d`
- `ADVAPI32!GetLengthSid` at `0x18002fd8d`
- `ADVAPI32!CopySid` at `0x18002fda9`
- `ADVAPI32!CopySid` at `0x18002fda9`
- `ADVAPI32!IsValidSid` at `0x18002fd7f`
- `ADVAPI32!IsValidSid` at `0x18002fd7f`
- `ADVAPI32!GetSidSubAuthority` at `0x18002fd69`
- `ADVAPI32!GetSidSubAuthority` at `0x18002fd69`
- `ADVAPI32!InitializeSid` at `0x18002fd3e`
- `ADVAPI32!InitializeSid` at `0x18002fd3e`
- `ADVAPI32!GetSidLengthRequired` at `0x18002fd24`
- `ADVAPI32!GetSidLengthRequired` at `0x18002fd24`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18002fc38  mov     [rsp-8+nSubAuthorityCount], r8b
0x18002fc3d  mov     [rsp-8+arg_18], r9
0x18002fc42  push    rbp
0x18002fc43  push    rbx
0x18002fc44  push    rsi
0x18002fc45  push    rdi
0x18002fc46  push    r14
0x18002fc48  lea     rbp, [rsp-37h]
0x18002fc4d  sub     rsp, 90h
0x18002fc54  mov     rax, cs:__security_cookie
0x18002fc5b  xor     rax, rsp
0x18002fc5e  mov     [rbp+57h+var_30], rax
0x18002fc62  mov     rbx, rdx
0x18002fc65  mov     rdi, rcx
0x18002fc68  mov     [rbp+57h+var_90], rcx
0x18002fc6c  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18002fc73  mov     [rcx], rax
0x18002fc76  mov     byte ptr [rcx+4Ch], 0
0x18002fc7a  mov     dword ptr [rcx+50h], 7
0x18002fc81  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002fc86  mov     rcx, rax
0x18002fc89  test    rax, rax
0x18002fc8c  jz      loc_18002FDF4
0x18002fc92  mov     rax, [rax]
0x18002fc95  mov     rax, [rax+18h]
0x18002fc99  call    cs:__guard_dispatch_icall_fptr
0x18002fc9f  add     rax, 18h
0x18002fca3  mov     [rdi+58h], rax
0x18002fca7  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002fcac  mov     rcx, rax
0x18002fcaf  test    rax, rax
0x18002fcb2  jz      loc_18002FDFF
0x18002fcb8  mov     rax, [rax]
0x18002fcbb  mov     rax, [rax+18h]
0x18002fcbf  call    cs:__guard_dispatch_icall_fptr
0x18002fcc5  add     rax, 18h
0x18002fcc9  mov     [rdi+60h], rax
0x18002fccd  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002fcd2  mov     rcx, rax
0x18002fcd5  test    rax, rax
0x18002fcd8  jz      loc_18002FE0A
0x18002fcde  mov     rax, [rax]
0x18002fce1  mov     rax, [rax+18h]
0x18002fce5  call    cs:__guard_dispatch_icall_fptr
0x18002fceb  add     rax, 18h
0x18002fcef  mov     [rdi+68h], rax
0x18002fcf3  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002fcf8  mov     rcx, rax
0x18002fcfb  test    rax, rax
0x18002fcfe  jz      loc_18002FE15
0x18002fd04  mov     rax, [rax]
0x18002fd07  mov     rax, [rax+18h]
0x18002fd0b  call    cs:__guard_dispatch_icall_fptr
0x18002fd11  add     rax, 18h
0x18002fd15  mov     [rdi+70h], rax
0x18002fd19  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x18002fd1c  test    cl, cl
0x18002fd1e  jz      loc_18002FDE9
0x18002fd24  call    cs:__imp_GetSidLengthRequired
0x18002fd2a  cmp     eax, 44h ; 'D'
0x18002fd2d  ja      loc_18002FDE9
0x18002fd33  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x18002fd37  mov     rdx, rbx; pIdentifierAuthority
0x18002fd3a  lea     rcx, [rbp+57h+Sid]; Sid
0x18002fd3e  call    cs:__imp_InitializeSid
0x18002fd44  test    eax, eax
0x18002fd46  jz      loc_18002FE20
0x18002fd4c  lea     r14, [rbp+57h+arg_18]
0x18002fd50  xor     esi, esi
0x18002fd52  cmp     [rbp+57h+nSubAuthorityCount], sil
0x18002fd56  jbe     short loc_18002FD7B
0x18002fd58  add     r14, 0FFFFFFFFFFFFFFF8h
0x18002fd5c  lea     r14, [r14+8]
0x18002fd60  mov     ebx, [r14]
0x18002fd63  mov     edx, esi; nSubAuthority
0x18002fd65  lea     rcx, [rbp+57h+Sid]; pSid
0x18002fd69  call    cs:__imp_GetSidSubAuthority
0x18002fd6f  mov     [rax], ebx
0x18002fd71  inc     esi
0x18002fd73  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x18002fd77  cmp     esi, eax
0x18002fd79  jb      short loc_18002FD5C
0x18002fd7b  lea     rcx, [rbp+57h+Sid]; pSid
0x18002fd7f  call    cs:__imp_IsValidSid
0x18002fd85  test    eax, eax
0x18002fd87  jz      short loc_18002FDE9
0x18002fd89  lea     rcx, [rbp+57h+Sid]; pSid
0x18002fd8d  call    cs:__imp_GetLengthSid
0x18002fd93  cmp     eax, 44h ; 'D'
0x18002fd96  ja      short loc_18002FDE9
0x18002fd98  lfence
0x18002fd9b  mov     byte ptr [rdi+4Ch], 1
0x18002fd9f  lea     rdx, [rdi+8]; pDestinationSid
0x18002fda3  lea     r8, [rbp+57h+Sid]; pSourceSid
0x18002fda7  mov     ecx, eax; nDestinationSidLength
0x18002fda9  call    cs:__imp_CopySid
0x18002fdaf  test    eax, eax
0x18002fdb1  jz      short loc_18002FDD7
0x18002fdb3  mov     dword ptr [rdi+50h], 8
0x18002fdba  mov     rax, rdi
0x18002fdbd  mov     rcx, [rbp+57h+var_30]
0x18002fdc1  xor     rcx, rsp; StackCookie
0x18002fdc4  call    __security_check_cookie
0x18002fdc9  add     rsp, 90h
0x18002fdd0  pop     r14
0x18002fdd2  pop     rdi
0x18002fdd3  pop     rsi
0x18002fdd4  pop     rbx
0x18002fdd5  pop     rbp
0x18002fdd6  retn
0x18002fdd7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002fddc  nop
0x18002fddd  mov     byte ptr [rdi+4Ch], 0
0x18002fde1  mov     ecx, eax; int
0x18002fde3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fde9  mov     ecx, 80070057h; int
0x18002fdee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fdf4  mov     ecx, 80004005h; int
0x18002fdf9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fdff  mov     ecx, 80004005h; int
0x18002fe04  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fe0a  mov     ecx, 80004005h; int
0x18002fe0f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fe15  mov     ecx, 80004005h; int
0x18002fe1a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002fe20  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
