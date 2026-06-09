# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x1801a9a78`
- end: `0x1801a9b62`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `234`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a7ddc`

## callees

- `0x180022710`
- `0x18005bf7c`
- `0x18005bfc8`
- `0x1800f63e4`
- `0x1801a9a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a9ae2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a9b4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a9ae2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801a9b4c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801a9a9f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801a9a9f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1801a9acd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1801a9acd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801a9a93`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801a9a93`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801a9b37`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1801a9b37`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Init(ATL::CSecurityDesc *this, struct _SECURITY_DESCRIPTOR *a2)
{
  void *v4; // rax
  int Error; // ebx
  errno_t v6; // eax
  int v7; // ebx
  WORD pControl; // [rsp+30h] [rbp+8h] BYREF
  rsize_t SourceSize; // [rsp+38h] [rbp+10h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp+18h] BYREF

  dwRevision = 0;
  LODWORD(SourceSize) = GetSecurityDescriptorLength(a2);
  v4 = malloc((unsigned int)SourceSize);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
    ATL::AtlThrowImpl(-2147024882);
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    Error = ResultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(Error);
  }
  if ( (pControl & 0x8000u) == 0 )
  {
    if ( !MakeSelfRelativeSD(a2, *((PSECURITY_DESCRIPTOR *)this + 1), (LPDWORD)&SourceSize) )
    {
      v7 = ResultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v7);
    }
  }
  else
  {
    v6 = memcpy_s(*((void *const *)this + 1), (unsigned int)SourceSize, a2, (unsigned int)SourceSize);
    ATL::AtlCrtErrorCheck(v6);
  }
}

```

## disassembly

```asm
0x1801a9a78  mov     [rsp+arg_18], rbx
0x1801a9a7d  push    rdi
0x1801a9a7e  sub     rsp, 20h
0x1801a9a82  mov     rdi, rcx
0x1801a9a85  mov     [rsp+28h+dwRevision], 0
0x1801a9a8d  mov     rcx, rdx; pSecurityDescriptor
0x1801a9a90  mov     rbx, rdx
0x1801a9a93  call    cs:__imp_GetSecurityDescriptorLength
0x1801a9a99  mov     ecx, eax; Size
0x1801a9a9b  mov     dword ptr [rsp+28h+SourceSize], ecx
0x1801a9a9f  call    cs:__imp_malloc
0x1801a9aa5  mov     [rdi+8], rax
0x1801a9aa9  test    rax, rax
0x1801a9aac  jnz     short loc_1801A9AB9
0x1801a9aae  mov     ecx, 8007000Eh; int
0x1801a9ab3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1801a9ab9  xor     eax, eax
0x1801a9abb  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x1801a9ac0  lea     rdx, [rsp+28h+pControl]; pControl
0x1801a9ac5  mov     [rsp+28h+pControl], ax
0x1801a9aca  mov     rcx, rbx; pSecurityDescriptor
0x1801a9acd  call    cs:__imp_GetSecurityDescriptorControl
0x1801a9ad3  test    eax, eax
0x1801a9ad5  jnz     short loc_1801A9AF8
0x1801a9ad7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801a9adc  mov     rcx, [rdi+8]; Block
0x1801a9ae0  mov     ebx, eax
0x1801a9ae2  call    cs:__imp_free
0x1801a9ae8  mov     ecx, ebx; int
0x1801a9aea  mov     qword ptr [rdi+8], 0
0x1801a9af2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1801a9af8  mov     rax, [rdi+8]
0x1801a9afc  mov     ecx, 8000h
0x1801a9b01  test    [rsp+28h+pControl], cx
0x1801a9b06  jz      short loc_1801A9B2C
0x1801a9b08  mov     edx, dword ptr [rsp+28h+SourceSize]; DestinationSize
0x1801a9b0c  mov     r8, rbx; Source
0x1801a9b0f  mov     r9d, edx; SourceSize
0x1801a9b12  mov     rcx, rax; Destination
0x1801a9b15  call    memcpy_s
0x1801a9b1a  mov     ecx, eax; int
0x1801a9b1c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1801a9b21  mov     rbx, [rsp+28h+arg_18]
0x1801a9b26  add     rsp, 20h
0x1801a9b2a  pop     rdi
0x1801a9b2b  retn
0x1801a9b2c  lea     r8, [rsp+28h+SourceSize]; lpdwBufferLength
0x1801a9b31  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1801a9b34  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1801a9b37  call    cs:__imp_MakeSelfRelativeSD
0x1801a9b3d  test    eax, eax
0x1801a9b3f  jnz     short loc_1801A9B21
0x1801a9b41  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801a9b46  mov     rcx, [rdi+8]; Block
0x1801a9b4a  mov     ebx, eax
0x1801a9b4c  call    cs:__imp_free
0x1801a9b52  mov     ecx, ebx; int
0x1801a9b54  mov     qword ptr [rdi+8], 0
0x1801a9b5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
