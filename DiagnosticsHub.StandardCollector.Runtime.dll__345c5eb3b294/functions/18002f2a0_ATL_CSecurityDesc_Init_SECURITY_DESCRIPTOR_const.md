# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x18002f2a0`
- end: `0x18002f3d3`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `307`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dfd0`

## callees

- `0x180002604`
- `0x18002f2a0`
- `0x18003151c`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18002f32e`
- `VCRUNTIME140!memcpy` at `0x18002f32e`
- `VCRUNTIME140!memset` at `0x18002f3b0`
- `VCRUNTIME140!memset` at `0x18002f3b0`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002f2ee`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002f2ee`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002f357`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002f357`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002f2c2`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002f2c2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f3b6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f3c2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f3c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f36c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f398`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f36c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f398`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f2ce`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f2ce`

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
        memcpy(v5, a2, Size);
        return;
      }
      memset(v5, 0, Size);
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
0x18002f2a0  mov     [rsp+arg_10], rbx
0x18002f2a5  push    rdi
0x18002f2a6  sub     rsp, 40h
0x18002f2aa  mov     rax, cs:__security_cookie
0x18002f2b1  xor     rax, rsp
0x18002f2b4  mov     [rsp+48h+var_18], rax
0x18002f2b9  mov     rdi, rcx
0x18002f2bc  mov     rbx, rdx
0x18002f2bf  mov     rcx, rdx; pSecurityDescriptor
0x18002f2c2  call    cs:__imp_GetSecurityDescriptorLength
0x18002f2c8  mov     ecx, eax; Size
0x18002f2ca  mov     dword ptr [rsp+48h+Size], ecx
0x18002f2ce  call    cs:__imp_malloc
0x18002f2d4  mov     [rdi+8], rax
0x18002f2d8  test    rax, rax
0x18002f2db  jz      loc_18002F382
0x18002f2e1  lea     r8, [rsp+48h+dwRevision]; lpdwRevision
0x18002f2e6  mov     rcx, rbx; pSecurityDescriptor
0x18002f2e9  lea     rdx, [rsp+48h+Size+4]; pControl
0x18002f2ee  call    cs:__imp_GetSecurityDescriptorControl
0x18002f2f4  test    eax, eax
0x18002f2f6  jz      loc_18002F38D
0x18002f2fc  mov     rax, [rdi+8]
0x18002f300  mov     ecx, 8000h
0x18002f305  test    word ptr [rsp+48h+Size+4], cx
0x18002f30a  jz      short loc_18002F34C
0x18002f30c  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x18002f311  test    r8, r8
0x18002f314  jz      short loc_18002F334
0x18002f316  test    rax, rax
0x18002f319  jz      loc_18002F3B6
0x18002f31f  mov     rcx, rax; void *
0x18002f322  test    rbx, rbx
0x18002f325  jz      loc_18002F3AE
0x18002f32b  mov     rdx, rbx; Src
0x18002f32e  call    cs:__imp_memcpy
0x18002f334  mov     rcx, [rsp+48h+var_18]
0x18002f339  xor     rcx, rsp; StackCookie
0x18002f33c  call    __security_check_cookie
0x18002f341  mov     rbx, [rsp+48h+arg_10]
0x18002f346  add     rsp, 40h
0x18002f34a  pop     rdi
0x18002f34b  retn
0x18002f34c  lea     r8, [rsp+48h+Size]; lpdwBufferLength
0x18002f351  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18002f354  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18002f357  call    cs:__imp_MakeSelfRelativeSD
0x18002f35d  test    eax, eax
0x18002f35f  jnz     short loc_18002F334
0x18002f361  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f366  mov     rcx, [rdi+8]; Block
0x18002f36a  mov     ebx, eax
0x18002f36c  call    cs:__imp_free
0x18002f372  mov     ecx, ebx; int
0x18002f374  mov     qword ptr [rdi+8], 0
0x18002f37c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f382  mov     ecx, 8007000Eh; int
0x18002f387  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f38d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f392  mov     rcx, [rdi+8]; Block
0x18002f396  mov     ebx, eax
0x18002f398  call    cs:__imp_free
0x18002f39e  mov     ecx, ebx; int
0x18002f3a0  mov     qword ptr [rdi+8], 0
0x18002f3a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f3ae  xor     edx, edx; Val
0x18002f3b0  call    cs:__imp_memset
0x18002f3b6  call    cs:__imp__errno
0x18002f3bc  mov     dword ptr [rax], 16h
0x18002f3c2  call    cs:__imp__invalid_parameter_noinfo
0x18002f3c8  mov     ecx, 80070057h; int
0x18002f3cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
