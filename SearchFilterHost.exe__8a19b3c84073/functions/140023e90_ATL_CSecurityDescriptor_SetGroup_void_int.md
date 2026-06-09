# ATL::CSecurityDescriptor::SetGroup(void *,int)

- ea: `0x140023e90`
- end: `0x140023f2a`
- name: `?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `154`
- prototype: `int(ATL::CSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400218d0`

## callees

- `0x14001d4e8`
- `0x14001d874`
- `0x140023e90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023ebe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023f02`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023ebe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023f02`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140023ead`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140023eee`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140023ead`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140023eee`

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
      Error = ResultFromLastError();
      free(*v4);
      *v4 = 0;
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140023e90  mov     [rsp+arg_0], rbx
0x140023e95  mov     [rsp+arg_8], rsi
0x140023e9a  push    rdi
0x140023e9b  sub     rsp, 20h
0x140023e9f  mov     rdi, rdx
0x140023ea2  mov     rsi, rcx
0x140023ea5  mov     rcx, [rcx]; pSecurityDescriptor
0x140023ea8  xor     edx, edx; pGroup
0x140023eaa  xor     r8d, r8d; bGroupDefaulted
0x140023ead  call    cs:__imp_SetSecurityDescriptorGroup
0x140023eb3  test    eax, eax
0x140023eb5  jz      short loc_140023F11
0x140023eb7  lea     rbx, [rsi+10h]
0x140023ebb  mov     rcx, [rbx]; Block
0x140023ebe  call    cs:__imp_free
0x140023ec4  mov     qword ptr [rbx], 0
0x140023ecb  test    rdi, rdi
0x140023ece  jnz     short loc_140023ED4
0x140023ed0  xor     eax, eax
0x140023ed2  jmp     short loc_140023F1A
0x140023ed4  mov     rdx, rdi; void *
0x140023ed7  mov     rcx, rbx; void **
0x140023eda  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x140023edf  mov     edi, eax
0x140023ee1  test    eax, eax
0x140023ee3  js      short loc_140023F18
0x140023ee5  mov     rdx, [rbx]; pGroup
0x140023ee8  xor     r8d, r8d; bGroupDefaulted
0x140023eeb  mov     rcx, [rsi]; pSecurityDescriptor
0x140023eee  call    cs:__imp_SetSecurityDescriptorGroup
0x140023ef4  test    eax, eax
0x140023ef6  jnz     short loc_140023F18
0x140023ef8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140023efd  mov     rcx, [rbx]; Block
0x140023f00  mov     edi, eax
0x140023f02  call    cs:__imp_free
0x140023f08  mov     qword ptr [rbx], 0
0x140023f0f  jmp     short loc_140023F18
0x140023f11  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140023f16  mov     edi, eax
0x140023f18  mov     eax, edi
0x140023f1a  mov     rbx, [rsp+28h+arg_0]
0x140023f1f  mov     rsi, [rsp+28h+arg_8]
0x140023f24  add     rsp, 20h
0x140023f28  pop     rdi
0x140023f29  retn
```
