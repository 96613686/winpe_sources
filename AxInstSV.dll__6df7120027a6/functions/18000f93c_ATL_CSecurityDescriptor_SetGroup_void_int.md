# ATL::CSecurityDescriptor::SetGroup(void *,int)

- ea: `0x18000f93c`
- end: `0x18000f9d6`
- name: `?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `154`
- prototype: `__int64 __fastcall(void **this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4a8`

## callees

- `0x180009df4`
- `0x18000a104`
- `0x18000f93c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f96a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9ae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f96a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f9ae`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000f959`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000f99a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000f959`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000f99a`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::SetGroup(void **this, void *a2)
{
  void **v4; // rbx
  int Error; // edi

  if ( SetSecurityDescriptorGroup(*this, 0, 0) )
  {
    v4 = this + 2;
    free(this[2]);
    this[2] = 0;
    if ( !a2 )
      return 0;
    Error = ATL::CSecurityDescriptor::CloneSID(this + 2, a2);
    if ( Error >= 0 && !SetSecurityDescriptorGroup(*this, *v4, 0) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*v4);
      *v4 = 0;
    }
  }
  else
  {
    return (unsigned int)ATL::AtlHresultFromLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000f93c  mov     [rsp+arg_0], rbx
0x18000f941  mov     [rsp+arg_8], rsi
0x18000f946  push    rdi
0x18000f947  sub     rsp, 20h
0x18000f94b  mov     rdi, rdx
0x18000f94e  mov     rsi, rcx
0x18000f951  mov     rcx, [rcx]; pSecurityDescriptor
0x18000f954  xor     edx, edx; pGroup
0x18000f956  xor     r8d, r8d; bGroupDefaulted
0x18000f959  call    cs:__imp_SetSecurityDescriptorGroup
0x18000f95f  test    eax, eax
0x18000f961  jz      short loc_18000F9BD
0x18000f963  lea     rbx, [rsi+10h]
0x18000f967  mov     rcx, [rbx]; Block
0x18000f96a  call    cs:__imp_free
0x18000f970  mov     qword ptr [rbx], 0
0x18000f977  test    rdi, rdi
0x18000f97a  jnz     short loc_18000F980
0x18000f97c  xor     eax, eax
0x18000f97e  jmp     short loc_18000F9C6
0x18000f980  mov     rdx, rdi; void *
0x18000f983  mov     rcx, rbx; void **
0x18000f986  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x18000f98b  mov     edi, eax
0x18000f98d  test    eax, eax
0x18000f98f  js      short loc_18000F9C4
0x18000f991  mov     rdx, [rbx]; pGroup
0x18000f994  xor     r8d, r8d; bGroupDefaulted
0x18000f997  mov     rcx, [rsi]; pSecurityDescriptor
0x18000f99a  call    cs:__imp_SetSecurityDescriptorGroup
0x18000f9a0  test    eax, eax
0x18000f9a2  jnz     short loc_18000F9C4
0x18000f9a4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000f9a9  mov     rcx, [rbx]; Block
0x18000f9ac  mov     edi, eax
0x18000f9ae  call    cs:__imp_free
0x18000f9b4  mov     qword ptr [rbx], 0
0x18000f9bb  jmp     short loc_18000F9C4
0x18000f9bd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000f9c2  mov     edi, eax
0x18000f9c4  mov     eax, edi
0x18000f9c6  mov     rbx, [rsp+28h+arg_0]
0x18000f9cb  mov     rsi, [rsp+28h+arg_8]
0x18000f9d0  add     rsp, 20h
0x18000f9d4  pop     rdi
0x18000f9d5  retn
```
