# ATL::CSecurityDescriptor::SetOwner(void *,int)

- ea: `0x14002896c`
- end: `0x140028a06`
- name: `?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
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
- `0x14002896c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002899a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400289de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002899a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400289de`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140028989`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400289ca`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140028989`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400289ca`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::SetOwner(void **this, void *a2)
{
  void **v4; // rbx
  int Error; // edi

  if ( SetSecurityDescriptorOwner(*this, 0, 0) )
  {
    v4 = this + 1;
    free(this[1]);
    this[1] = 0;
    if ( !a2 )
      return 0;
    Error = ATL::CSecurityDescriptor::CloneSID(this + 1, a2);
    if ( Error >= 0 && !SetSecurityDescriptorOwner(*this, *v4, 0) )
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
0x14002896c  mov     [rsp+arg_0], rbx
0x140028971  mov     [rsp+arg_8], rsi
0x140028976  push    rdi
0x140028977  sub     rsp, 20h
0x14002897b  mov     rdi, rdx
0x14002897e  mov     rsi, rcx
0x140028981  mov     rcx, [rcx]; pSecurityDescriptor
0x140028984  xor     edx, edx; pOwner
0x140028986  xor     r8d, r8d; bOwnerDefaulted
0x140028989  call    cs:__imp_SetSecurityDescriptorOwner
0x14002898f  test    eax, eax
0x140028991  jz      short loc_1400289ED
0x140028993  lea     rbx, [rsi+8]
0x140028997  mov     rcx, [rbx]; Block
0x14002899a  call    cs:__imp_free
0x1400289a0  mov     qword ptr [rbx], 0
0x1400289a7  test    rdi, rdi
0x1400289aa  jnz     short loc_1400289B0
0x1400289ac  xor     eax, eax
0x1400289ae  jmp     short loc_1400289F6
0x1400289b0  mov     rdx, rdi; void *
0x1400289b3  mov     rcx, rbx; void **
0x1400289b6  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x1400289bb  mov     edi, eax
0x1400289bd  test    eax, eax
0x1400289bf  js      short loc_1400289F4
0x1400289c1  mov     rdx, [rbx]; pOwner
0x1400289c4  xor     r8d, r8d; bOwnerDefaulted
0x1400289c7  mov     rcx, [rsi]; pSecurityDescriptor
0x1400289ca  call    cs:__imp_SetSecurityDescriptorOwner
0x1400289d0  test    eax, eax
0x1400289d2  jnz     short loc_1400289F4
0x1400289d4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400289d9  mov     rcx, [rbx]; Block
0x1400289dc  mov     edi, eax
0x1400289de  call    cs:__imp_free
0x1400289e4  mov     qword ptr [rbx], 0
0x1400289eb  jmp     short loc_1400289F4
0x1400289ed  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400289f2  mov     edi, eax
0x1400289f4  mov     eax, edi
0x1400289f6  mov     rbx, [rsp+28h+arg_0]
0x1400289fb  mov     rsi, [rsp+28h+arg_8]
0x140028a00  add     rsp, 20h
0x140028a04  pop     rdi
0x140028a05  retn
```
