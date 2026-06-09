# ATL::CSecurityDescriptor::Allow(void *,ulong)

- ea: `0x180009c88`
- end: `0x180009cda`
- name: `?Allow@CSecurityDescriptor@ATL@@QEAAJPEAXK@Z`
- size: `82`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c5ec`

## callees

- `0x180009420`
- `0x180009c88`
- `0x180009df4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009cb7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180009cb7`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::Allow(struct _ACL **this, void *a2)
{
  int v3; // ebx

  v3 = ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(this + 3, a2);
  if ( v3 >= 0 && !SetSecurityDescriptorDacl(*this, 1, this[3], 0) )
    return (unsigned int)ATL::AtlHresultFromLastError();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009c88  mov     [rsp+arg_0], rbx
0x180009c8d  mov     [rsp+arg_8], rsi
0x180009c92  push    rdi
0x180009c93  sub     rsp, 20h
0x180009c97  mov     rdi, rcx
0x180009c9a  add     rcx, 18h; struct _ACL **
0x180009c9e  call    ?AddAccessAllowedACEToACL@CSecurityDescriptor@ATL@@SAJPEAPEAU_ACL@@PEAXK@Z; ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong)
0x180009ca3  mov     ebx, eax
0x180009ca5  test    eax, eax
0x180009ca7  js      short loc_180009CC8
0x180009ca9  mov     r8, [rdi+18h]; pDacl
0x180009cad  xor     r9d, r9d; bDaclDefaulted
0x180009cb0  mov     rcx, [rdi]; pSecurityDescriptor
0x180009cb3  lea     edx, [r9+1]; bDaclPresent
0x180009cb7  call    cs:__imp_SetSecurityDescriptorDacl
0x180009cbd  test    eax, eax
0x180009cbf  jnz     short loc_180009CC8
0x180009cc1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009cc6  mov     ebx, eax
0x180009cc8  mov     rsi, [rsp+28h+arg_8]
0x180009ccd  mov     eax, ebx
0x180009ccf  mov     rbx, [rsp+28h+arg_0]
0x180009cd4  add     rsp, 20h
0x180009cd8  pop     rdi
0x180009cd9  retn
```
