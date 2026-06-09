# ATL::CSecurityDescriptor::SetGroup(void *,int)

- ea: `0x1400287f4`
- end: `0x14002888e`
- name: `?SetGroup@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `154`
- prototype: `int(ATL::CSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ef3c`

## callees

- `0x1400124cc`
- `0x140012ac4`
- `0x1400287f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140028822`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140028866`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140028822`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140028866`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140028811`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140028852`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140028811`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140028852`

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
0x1400287f4  mov     [rsp+arg_0], rbx
0x1400287f9  mov     [rsp+arg_8], rsi
0x1400287fe  push    rdi
0x1400287ff  sub     rsp, 20h
0x140028803  mov     rdi, rdx
0x140028806  mov     rsi, rcx
0x140028809  mov     rcx, [rcx]; pSecurityDescriptor
0x14002880c  xor     edx, edx; pGroup
0x14002880e  xor     r8d, r8d; bGroupDefaulted
0x140028811  call    cs:__imp_SetSecurityDescriptorGroup
0x140028817  test    eax, eax
0x140028819  jz      short loc_140028875
0x14002881b  lea     rbx, [rsi+10h]
0x14002881f  mov     rcx, [rbx]; Block
0x140028822  call    cs:__imp_free
0x140028828  mov     qword ptr [rbx], 0
0x14002882f  test    rdi, rdi
0x140028832  jnz     short loc_140028838
0x140028834  xor     eax, eax
0x140028836  jmp     short loc_14002887E
0x140028838  mov     rdx, rdi; void *
0x14002883b  mov     rcx, rbx; void **
0x14002883e  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x140028843  mov     edi, eax
0x140028845  test    eax, eax
0x140028847  js      short loc_14002887C
0x140028849  mov     rdx, [rbx]; pGroup
0x14002884c  xor     r8d, r8d; bGroupDefaulted
0x14002884f  mov     rcx, [rsi]; pSecurityDescriptor
0x140028852  call    cs:__imp_SetSecurityDescriptorGroup
0x140028858  test    eax, eax
0x14002885a  jnz     short loc_14002887C
0x14002885c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140028861  mov     rcx, [rbx]; Block
0x140028864  mov     edi, eax
0x140028866  call    cs:__imp_free
0x14002886c  mov     qword ptr [rbx], 0
0x140028873  jmp     short loc_14002887C
0x140028875  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14002887a  mov     edi, eax
0x14002887c  mov     eax, edi
0x14002887e  mov     rbx, [rsp+28h+arg_0]
0x140028883  mov     rsi, [rsp+28h+arg_8]
0x140028888  add     rsp, 20h
0x14002888c  pop     rdi
0x14002888d  retn
```
