# ATL::CSecurityDescriptor::Initialize(void)

- ea: `0x18000c3d8`
- end: `0x18000c49f`
- name: `?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c4a8`

## callees

- `0x180001744`
- `0x18000177c`
- `0x180009df4`
- `0x18000c3d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c411`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c423`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c435`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c411`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c423`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c435`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000c465`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000c465`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CSecurityDescriptor::Initialize(void **this)
{
  void **v1; // rdi
  unsigned int Error; // ebx

  v1 = this;
  operator delete(*this);
  *v1 = 0;
  free(v1[1]);
  v1[1] = 0;
  free(v1[2]);
  v1[2] = 0;
  free(v1[3]);
  v1[3] = 0;
  free(v1[4]);
  try
  {
    v1[4] = 0;
    *v1 = operator new(0x28u);
  }
  catch ( ... )
  {
    v1 = this;
  }
  if ( !*v1 )
    return 2147942414LL;
  if ( InitializeSecurityDescriptor(*v1, 1u) )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  operator delete(*v1);
  *v1 = 0;
  return Error;
}

```

## disassembly

```asm
0x18000c3d8  mov     [rsp+arg_8], rbx
0x18000c3dd  mov     [rsp+arg_0], rcx
0x18000c3e2  push    rdi
0x18000c3e3  sub     rsp, 20h
0x18000c3e7  mov     rdi, rcx
0x18000c3ea  xor     edx, edx
0x18000c3ec  mov     rcx, [rcx]; Block
0x18000c3ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c3f4  mov     qword ptr [rdi], 0
0x18000c3fb  mov     rcx, [rdi+8]; Block
0x18000c3ff  call    cs:__imp_free
0x18000c405  mov     qword ptr [rdi+8], 0
0x18000c40d  mov     rcx, [rdi+10h]; Block
0x18000c411  call    cs:__imp_free
0x18000c417  mov     qword ptr [rdi+10h], 0
0x18000c41f  mov     rcx, [rdi+18h]; Block
0x18000c423  call    cs:__imp_free
0x18000c429  mov     qword ptr [rdi+18h], 0
0x18000c431  mov     rcx, [rdi+20h]; Block
0x18000c435  call    cs:__imp_free
0x18000c43b  mov     qword ptr [rdi+20h], 0
0x18000c443  mov     ecx, 28h ; '('; Size
0x18000c448  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c44d  mov     [rdi], rax
0x18000c450  jmp     short loc_18000C457
0x18000c452  mov     rdi, [rsp+28h+arg_0]
0x18000c457  cmp     qword ptr [rdi], 0
0x18000c45b  jz      short loc_18000C48F
0x18000c45d  mov     edx, 1; dwRevision
0x18000c462  mov     rcx, [rdi]; pSecurityDescriptor
0x18000c465  call    cs:__imp_InitializeSecurityDescriptor
0x18000c46b  test    eax, eax
0x18000c46d  jz      short loc_18000C473
0x18000c46f  xor     eax, eax
0x18000c471  jmp     short loc_18000C494
0x18000c473  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c478  mov     ebx, eax
0x18000c47a  xor     edx, edx
0x18000c47c  mov     rcx, [rdi]; Block
0x18000c47f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c484  mov     qword ptr [rdi], 0
0x18000c48b  mov     eax, ebx
0x18000c48d  jmp     short loc_18000C494
0x18000c48f  mov     eax, 8007000Eh
0x18000c494  mov     rbx, [rsp+28h+arg_8]
0x18000c499  add     rsp, 20h
0x18000c49d  pop     rdi
0x18000c49e  retn
```
