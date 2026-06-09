# Acl::Acl(ulong,void * *,unsigned __int64)

- ea: `0x18009dd50`
- end: `0x18009de06`
- name: `??0Acl@@QEAA@KPEAPEAX_K@Z`
- size: `182`
- prototype: `Acl *__fastcall(Acl *__hidden this, unsigned int, void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18009d72c`

## callees

- `0x180042710`
- `0x18009dd50`
- `0x1800a1558`
- `0x1800aa674`
- `0x1800aaa58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009ddc3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009ddc3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009dd76`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009dd76`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009dde4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009dde4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Acl *__fastcall Acl::Acl(Acl *this, __int64 a2, void **a3)
{
  __int64 v5; // rsi
  unsigned __int64 i; // rbx
  size_t v7; // rax
  DWORD v8; // ebx
  void *v9; // rax
  void *v10; // rcx
  unsigned __int64 j; // rbx

  *(_QWORD *)this = 0;
  v5 = 8;
  for ( i = 0; i < 5; ++i )
    v5 += GetLengthSid(a3[i]) + 8LL;
  v7 = Align<unsigned __int64>(v5, 4);
  v8 = v7;
  v9 = operator new(v7);
  v10 = *(void **)this;
  *(_QWORD *)this = v9;
  operator delete(v10, 8u);
  if ( !InitializeAcl(*(PACL *)this, v8, 2u) )
LABEL_9:
    OSException::ThrowLastError();
  for ( j = 0; j < 5; ++j )
  {
    if ( !AddAccessAllowedAce(*(PACL *)this, 2u, 1u, a3[j]) )
      goto LABEL_9;
  }
  return this;
}

```

## disassembly

```asm
0x18009dd50  mov     [rsp+arg_0], rcx
0x18009dd55  push    rbx
0x18009dd56  push    rsi
0x18009dd57  push    rdi
0x18009dd58  push    r14
0x18009dd5a  sub     rsp, 28h
0x18009dd5e  mov     r14, r8
0x18009dd61  mov     rdi, rcx
0x18009dd64  mov     qword ptr [rcx], 0
0x18009dd6b  mov     esi, 8
0x18009dd70  xor     ebx, ebx
0x18009dd72  mov     rcx, [r14+rbx*8]; pSid
0x18009dd76  call    cs:__imp_GetLengthSid
0x18009dd7c  mov     eax, eax
0x18009dd7e  add     rsi, 8
0x18009dd82  add     rsi, rax
0x18009dd85  inc     rbx
0x18009dd88  cmp     rbx, 5
0x18009dd8c  jb      short loc_18009DD72
0x18009dd8e  mov     edx, 4
0x18009dd93  mov     rcx, rsi
0x18009dd96  call    ??$Align@_K@@YA_K_K0@Z; Align<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18009dd9b  mov     rbx, rax
0x18009dd9e  mov     rcx, rax; Size
0x18009dda1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009dda6  mov     rcx, [rdi]; void *
0x18009dda9  mov     [rdi], rax
0x18009ddac  mov     edx, 8; unsigned __int64
0x18009ddb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009ddb6  mov     edx, ebx; nAclLength
0x18009ddb8  mov     esi, 2
0x18009ddbd  mov     r8d, esi; dwAclRevision
0x18009ddc0  mov     rcx, [rdi]; pAcl
0x18009ddc3  call    cs:__imp_InitializeAcl
0x18009ddc9  test    eax, eax
0x18009ddcb  jz      short loc_18009DE00
0x18009ddcd  xor     ebx, ebx
0x18009ddcf  cmp     rbx, 5
0x18009ddd3  jnb     short loc_18009DDF3
0x18009ddd5  mov     r9, [r14+rbx*8]; pSid
0x18009ddd9  mov     r8d, 1; AccessMask
0x18009dddf  mov     edx, esi; dwAceRevision
0x18009dde1  mov     rcx, [rdi]; pAcl
0x18009dde4  call    cs:__imp_AddAccessAllowedAce
0x18009ddea  test    eax, eax
0x18009ddec  jz      short loc_18009DE00
0x18009ddee  inc     rbx
0x18009ddf1  jmp     short loc_18009DDCF
0x18009ddf3  mov     rax, rdi
0x18009ddf6  add     rsp, 28h
0x18009ddfa  pop     r14
0x18009ddfc  pop     rdi
0x18009ddfd  pop     rsi
0x18009ddfe  pop     rbx
0x18009ddff  retn
0x18009de00  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
