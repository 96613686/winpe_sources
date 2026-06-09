# ATL::CSecurityDescriptor::Initialize(void)

- ea: `0x14001ee64`
- end: `0x14001ef34`
- name: `?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001ef3c`

## callees

- `0x140005264`
- `0x140005570`
- `0x1400124cc`
- `0x14001ee64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001ee94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eea6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eeb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eeca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001ee94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eea6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eeb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001eeca`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14001eefa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14001eefa`

## pseudocode

```c
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
  Error = ResultFromLastError();
  operator delete(*v1);
  *v1 = 0;
  return Error;
}

```

## disassembly

```asm
0x14001ee64  mov     [rsp+arg_0], rcx
0x14001ee69  push    rdi
0x14001ee6a  sub     rsp, 30h
0x14001ee6e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14001ee77  mov     [rsp+38h+arg_8], rbx
0x14001ee7c  mov     rdi, rcx
0x14001ee7f  xor     edx, edx
0x14001ee81  mov     rcx, [rcx]; Block
0x14001ee84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ee89  mov     qword ptr [rdi], 0
0x14001ee90  mov     rcx, [rdi+8]; Block
0x14001ee94  call    cs:__imp_free
0x14001ee9a  mov     qword ptr [rdi+8], 0
0x14001eea2  mov     rcx, [rdi+10h]; Block
0x14001eea6  call    cs:__imp_free
0x14001eeac  mov     qword ptr [rdi+10h], 0
0x14001eeb4  mov     rcx, [rdi+18h]; Block
0x14001eeb8  call    cs:__imp_free
0x14001eebe  mov     qword ptr [rdi+18h], 0
0x14001eec6  mov     rcx, [rdi+20h]; Block
0x14001eeca  call    cs:__imp_free
0x14001eed0  mov     qword ptr [rdi+20h], 0
0x14001eed8  mov     ecx, 28h ; '('; Size
0x14001eedd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001eee2  mov     [rdi], rax
0x14001eee5  jmp     short loc_14001EEEC
0x14001eee7  mov     rdi, [rsp+38h+arg_0]
0x14001eeec  cmp     qword ptr [rdi], 0
0x14001eef0  jz      short loc_14001EF24
0x14001eef2  mov     edx, 1; dwRevision
0x14001eef7  mov     rcx, [rdi]; pSecurityDescriptor
0x14001eefa  call    cs:__imp_InitializeSecurityDescriptor
0x14001ef00  test    eax, eax
0x14001ef02  jz      short loc_14001EF08
0x14001ef04  xor     eax, eax
0x14001ef06  jmp     short loc_14001EF29
0x14001ef08  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001ef0d  mov     ebx, eax
0x14001ef0f  xor     edx, edx
0x14001ef11  mov     rcx, [rdi]; Block
0x14001ef14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ef19  mov     qword ptr [rdi], 0
0x14001ef20  mov     eax, ebx
0x14001ef22  jmp     short loc_14001EF29
0x14001ef24  mov     eax, 8007000Eh
0x14001ef29  mov     rbx, [rsp+38h+arg_8]
0x14001ef2e  add     rsp, 30h
0x14001ef32  pop     rdi
0x14001ef33  retn
```
