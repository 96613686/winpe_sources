# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x140011cb0`
- end: `0x140011de1`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `305`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011b04`

## callees

- `0x140002e74`
- `0x14000916c`
- `0x140011cb0`
- `0x1400137e0`
- `0x14001473e`
- `0x140014bc0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorControl` at `0x140011cfe`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140011cfe`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140011cd2`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140011cd2`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011d66`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140011d66`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140011dc4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140011dc4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140011dd0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140011dd0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011cde`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140011cde`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140011d7b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140011da7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140011d7b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140011da7`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Init(ATL::CSecurityDesc *this, struct _SECURITY_DESCRIPTOR *a2)
{
  void *v4; // rax
  void *v5; // rcx
  int v6; // ebx
  int Error; // ebx
  DWORD Size; // [rsp+20h] [rbp-28h] BYREF
  __int16 Size_4; // [rsp+24h] [rbp-24h] BYREF
  DWORD dwRevision; // [rsp+28h] [rbp-20h] BYREF

  Size = GetSecurityDescriptorLength(a2);
  v4 = malloc(Size);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !GetSecurityDescriptorControl(a2, (PSECURITY_DESCRIPTOR_CONTROL)&Size_4, &dwRevision) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(Error);
  }
  if ( Size_4 < 0 )
  {
    if ( !Size )
      return;
    if ( *((_QWORD *)this + 1) )
    {
      v5 = (void *)*((_QWORD *)this + 1);
      if ( a2 )
      {
        memcpy_0(v5, a2, Size);
        return;
      }
      memset_0(v5, 0, Size);
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
    ATL::AtlThrowImpl(-2147024809);
  }
  if ( !MakeSelfRelativeSD(a2, *((PSECURITY_DESCRIPTOR *)this + 1), &Size) )
  {
    v6 = ATL::AtlHresultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(v6);
  }
}

```

## disassembly

```asm
0x140011cb0  mov     [rsp+arg_10], rbx
0x140011cb5  push    rdi
0x140011cb6  sub     rsp, 40h
0x140011cba  mov     rax, cs:__security_cookie
0x140011cc1  xor     rax, rsp
0x140011cc4  mov     [rsp+48h+var_18], rax
0x140011cc9  mov     rdi, rcx
0x140011ccc  mov     rbx, rdx
0x140011ccf  mov     rcx, rdx; pSecurityDescriptor
0x140011cd2  call    cs:__imp_GetSecurityDescriptorLength
0x140011cd8  mov     ecx, eax; Size
0x140011cda  mov     dword ptr [rsp+48h+Size], ecx
0x140011cde  call    cs:__imp_malloc
0x140011ce4  mov     [rdi+8], rax
0x140011ce8  test    rax, rax
0x140011ceb  jz      loc_140011D91
0x140011cf1  lea     r8, [rsp+48h+dwRevision]; lpdwRevision
0x140011cf6  mov     rcx, rbx; pSecurityDescriptor
0x140011cf9  lea     rdx, [rsp+48h+Size+4]; pControl
0x140011cfe  call    cs:__imp_GetSecurityDescriptorControl
0x140011d04  test    eax, eax
0x140011d06  jz      loc_140011D9C
0x140011d0c  mov     rax, [rdi+8]
0x140011d10  mov     ecx, 8000h
0x140011d15  test    word ptr [rsp+48h+Size+4], cx
0x140011d1a  jz      short loc_140011D5B
0x140011d1c  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x140011d21  test    r8, r8
0x140011d24  jz      short loc_140011D43
0x140011d26  test    rax, rax
0x140011d29  jz      loc_140011DC4
0x140011d2f  mov     rcx, rax; void *
0x140011d32  test    rbx, rbx
0x140011d35  jz      loc_140011DBD
0x140011d3b  mov     rdx, rbx; Src
0x140011d3e  call    memcpy_0
0x140011d43  mov     rcx, [rsp+48h+var_18]
0x140011d48  xor     rcx, rsp; StackCookie
0x140011d4b  call    __security_check_cookie
0x140011d50  mov     rbx, [rsp+48h+arg_10]
0x140011d55  add     rsp, 40h
0x140011d59  pop     rdi
0x140011d5a  retn
0x140011d5b  lea     r8, [rsp+48h+Size]; lpdwBufferLength
0x140011d60  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x140011d63  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x140011d66  call    cs:__imp_MakeSelfRelativeSD
0x140011d6c  test    eax, eax
0x140011d6e  jnz     short loc_140011D43
0x140011d70  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140011d75  mov     rcx, [rdi+8]; Block
0x140011d79  mov     ebx, eax
0x140011d7b  call    cs:__imp_free
0x140011d81  mov     ecx, ebx; int
0x140011d83  mov     qword ptr [rdi+8], 0
0x140011d8b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011d91  mov     ecx, 8007000Eh; int
0x140011d96  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011d9c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140011da1  mov     rcx, [rdi+8]; Block
0x140011da5  mov     ebx, eax
0x140011da7  call    cs:__imp_free
0x140011dad  mov     ecx, ebx; int
0x140011daf  mov     qword ptr [rdi+8], 0
0x140011db7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011dbd  xor     edx, edx; Val
0x140011dbf  call    memset_0
0x140011dc4  call    cs:__imp__errno
0x140011dca  mov     dword ptr [rax], 16h
0x140011dd0  call    cs:__imp__invalid_parameter_noinfo
0x140011dd6  mov     ecx, 80070057h; int
0x140011ddb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
