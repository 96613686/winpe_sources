# ATL::CSecurityDescriptor::SetOwner(void *,int)

- ea: `0x18000fab4`
- end: `0x18000fb4e`
- name: `?SetOwner@CSecurityDescriptor@ATL@@QEAAJPEAXH@Z`
- size: `154`
- prototype: `int(ATL::CSecurityDescriptor *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4a8`

## callees

- `0x180009df4`
- `0x18000a104`
- `0x18000fab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000fae2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000fb26`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000fae2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000fb26`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000fad1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000fb12`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000fad1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000fb12`

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
0x18000fab4  mov     [rsp+arg_0], rbx
0x18000fab9  mov     [rsp+arg_8], rsi
0x18000fabe  push    rdi
0x18000fabf  sub     rsp, 20h
0x18000fac3  mov     rdi, rdx
0x18000fac6  mov     rsi, rcx
0x18000fac9  mov     rcx, [rcx]; pSecurityDescriptor
0x18000facc  xor     edx, edx; pOwner
0x18000face  xor     r8d, r8d; bOwnerDefaulted
0x18000fad1  call    cs:__imp_SetSecurityDescriptorOwner
0x18000fad7  test    eax, eax
0x18000fad9  jz      short loc_18000FB35
0x18000fadb  lea     rbx, [rsi+8]
0x18000fadf  mov     rcx, [rbx]; Block
0x18000fae2  call    cs:__imp_free
0x18000fae8  mov     qword ptr [rbx], 0
0x18000faef  test    rdi, rdi
0x18000faf2  jnz     short loc_18000FAF8
0x18000faf4  xor     eax, eax
0x18000faf6  jmp     short loc_18000FB3E
0x18000faf8  mov     rdx, rdi; void *
0x18000fafb  mov     rcx, rbx; void **
0x18000fafe  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x18000fb03  mov     edi, eax
0x18000fb05  test    eax, eax
0x18000fb07  js      short loc_18000FB3C
0x18000fb09  mov     rdx, [rbx]; pOwner
0x18000fb0c  xor     r8d, r8d; bOwnerDefaulted
0x18000fb0f  mov     rcx, [rsi]; pSecurityDescriptor
0x18000fb12  call    cs:__imp_SetSecurityDescriptorOwner
0x18000fb18  test    eax, eax
0x18000fb1a  jnz     short loc_18000FB3C
0x18000fb1c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fb21  mov     rcx, [rbx]; Block
0x18000fb24  mov     edi, eax
0x18000fb26  call    cs:__imp_free
0x18000fb2c  mov     qword ptr [rbx], 0
0x18000fb33  jmp     short loc_18000FB3C
0x18000fb35  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fb3a  mov     edi, eax
0x18000fb3c  mov     eax, edi
0x18000fb3e  mov     rbx, [rsp+28h+arg_0]
0x18000fb43  mov     rsi, [rsp+28h+arg_8]
0x18000fb48  add     rsp, 20h
0x18000fb4c  pop     rdi
0x18000fb4d  retn
```
