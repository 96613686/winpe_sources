# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x180018e30`
- end: `0x180018f38`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `264`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001733c`
- `0x180018dc4`

## callees

- `0x180018710`
- `0x180018d78`
- `0x180018e30`
- `0x18001e838`
- `0x18009e2e4`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018ee6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018f22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018ee6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018f22`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018e66`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018e66`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018e89`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018e89`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018e5a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018e5a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180018eae`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180018eae`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Init(ATL::CSecurityDesc *this, struct _SECURITY_DESCRIPTOR *a2)
{
  void *v4; // rax
  int LastErrorAsHResult; // ebx
  errno_t v6; // eax
  int v7; // ebx
  DWORD dwBufferLength; // [rsp+20h] [rbp-28h] BYREF
  WORD pControl; // [rsp+24h] [rbp-24h] BYREF
  DWORD dwRevision; // [rsp+28h] [rbp-20h] BYREF

  dwRevision = 0;
  dwBufferLength = GetSecurityDescriptorLength(a2);
  v4 = malloc(dwBufferLength);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
    ATL::AtlThrowImpl(-2147024882);
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(LastErrorAsHResult);
  }
  if ( (pControl & 0x8000u) != 0 )
  {
    v6 = memcpy_s(*((void *const *)this + 1), dwBufferLength, a2, dwBufferLength);
    ATL::AtlCrtErrorCheck(v6);
  }
  else if ( !MakeSelfRelativeSD(a2, *((PSECURITY_DESCRIPTOR *)this + 1), &dwBufferLength) )
  {
    v7 = LocationHelper::GetLastErrorAsHResult();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(v7);
  }
}

```

## disassembly

```asm
0x180018e30  mov     [rsp+arg_10], rbx
0x180018e35  push    rdi
0x180018e36  sub     rsp, 40h
0x180018e3a  mov     rax, cs:__security_cookie
0x180018e41  xor     rax, rsp
0x180018e44  mov     [rsp+48h+var_18], rax
0x180018e49  mov     rdi, rcx
0x180018e4c  mov     [rsp+48h+dwRevision], 0
0x180018e54  mov     rcx, rdx; pSecurityDescriptor
0x180018e57  mov     rbx, rdx
0x180018e5a  call    cs:__imp_GetSecurityDescriptorLength
0x180018e60  mov     ecx, eax; Size
0x180018e62  mov     [rsp+48h+dwBufferLength], ecx
0x180018e66  call    cs:__imp_malloc
0x180018e6c  mov     [rdi+8], rax
0x180018e70  test    rax, rax
0x180018e73  jz      short loc_180018ED0
0x180018e75  xor     eax, eax
0x180018e77  lea     r8, [rsp+48h+dwRevision]; lpdwRevision
0x180018e7c  lea     rdx, [rsp+48h+pControl]; pControl
0x180018e81  mov     [rsp+48h+pControl], ax
0x180018e86  mov     rcx, rbx; pSecurityDescriptor
0x180018e89  call    cs:__imp_GetSecurityDescriptorControl
0x180018e8f  test    eax, eax
0x180018e91  jz      short loc_180018EDB
0x180018e93  mov     rax, [rdi+8]
0x180018e97  mov     ecx, 8000h
0x180018e9c  test    [rsp+48h+pControl], cx
0x180018ea1  jnz     short loc_180018EFC
0x180018ea3  lea     r8, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x180018ea8  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180018eab  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180018eae  call    cs:__imp_MakeSelfRelativeSD
0x180018eb4  test    eax, eax
0x180018eb6  jz      short loc_180018F17
0x180018eb8  mov     rcx, [rsp+48h+var_18]
0x180018ebd  xor     rcx, rsp; StackCookie
0x180018ec0  call    __security_check_cookie
0x180018ec5  mov     rbx, [rsp+48h+arg_10]
0x180018eca  add     rsp, 40h
0x180018ece  pop     rdi
0x180018ecf  retn
0x180018ed0  mov     ecx, 8007000Eh; int
0x180018ed5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018edb  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x180018ee0  mov     rcx, [rdi+8]; Block
0x180018ee4  mov     ebx, eax
0x180018ee6  call    cs:__imp_free
0x180018eec  mov     ecx, ebx; int
0x180018eee  mov     qword ptr [rdi+8], 0
0x180018ef6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018efc  mov     edx, [rsp+48h+dwBufferLength]; DestinationSize
0x180018f00  mov     r8, rbx; Source
0x180018f03  mov     r9d, edx; SourceSize
0x180018f06  mov     rcx, rax; Destination
0x180018f09  call    memcpy_s
0x180018f0e  mov     ecx, eax; int
0x180018f10  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018f15  jmp     short loc_180018EB8
0x180018f17  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x180018f1c  mov     rcx, [rdi+8]; Block
0x180018f20  mov     ebx, eax
0x180018f22  call    cs:__imp_free
0x180018f28  mov     ecx, ebx; int
0x180018f2a  mov     qword ptr [rdi+8], 0
0x180018f32  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
