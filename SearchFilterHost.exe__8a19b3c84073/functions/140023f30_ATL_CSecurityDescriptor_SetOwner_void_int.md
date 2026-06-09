# ATL::CSecurityDescriptor::SetOwner(void *,int)

- ea: `0x140023f30`
- end: `0x140023fca`
- name: `?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
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
- `0x140023f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023f5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023fa2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023f5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140023fa2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140023f4d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140023f8e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140023f4d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140023f8e`

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
0x140023f30  mov     [rsp+arg_0], rbx
0x140023f35  mov     [rsp+arg_8], rsi
0x140023f3a  push    rdi
0x140023f3b  sub     rsp, 20h
0x140023f3f  mov     rdi, rdx
0x140023f42  mov     rsi, rcx
0x140023f45  mov     rcx, [rcx]; pSecurityDescriptor
0x140023f48  xor     edx, edx; pOwner
0x140023f4a  xor     r8d, r8d; bOwnerDefaulted
0x140023f4d  call    cs:__imp_SetSecurityDescriptorOwner
0x140023f53  test    eax, eax
0x140023f55  jz      short loc_140023FB1
0x140023f57  lea     rbx, [rsi+8]
0x140023f5b  mov     rcx, [rbx]; Block
0x140023f5e  call    cs:__imp_free
0x140023f64  mov     qword ptr [rbx], 0
0x140023f6b  test    rdi, rdi
0x140023f6e  jnz     short loc_140023F74
0x140023f70  xor     eax, eax
0x140023f72  jmp     short loc_140023FBA
0x140023f74  mov     rdx, rdi; void *
0x140023f77  mov     rcx, rbx; void **
0x140023f7a  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x140023f7f  mov     edi, eax
0x140023f81  test    eax, eax
0x140023f83  js      short loc_140023FB8
0x140023f85  mov     rdx, [rbx]; pOwner
0x140023f88  xor     r8d, r8d; bOwnerDefaulted
0x140023f8b  mov     rcx, [rsi]; pSecurityDescriptor
0x140023f8e  call    cs:__imp_SetSecurityDescriptorOwner
0x140023f94  test    eax, eax
0x140023f96  jnz     short loc_140023FB8
0x140023f98  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140023f9d  mov     rcx, [rbx]; Block
0x140023fa0  mov     edi, eax
0x140023fa2  call    cs:__imp_free
0x140023fa8  mov     qword ptr [rbx], 0
0x140023faf  jmp     short loc_140023FB8
0x140023fb1  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140023fb6  mov     edi, eax
0x140023fb8  mov     eax, edi
0x140023fba  mov     rbx, [rsp+28h+arg_0]
0x140023fbf  mov     rsi, [rsp+28h+arg_8]
0x140023fc4  add     rsp, 20h
0x140023fc8  pop     rdi
0x140023fc9  retn
```
