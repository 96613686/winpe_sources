# ATL::CSecurityDescriptor::Initialize(void)

- ea: `0x1400217f8`
- end: `0x1400218c8`
- name: `?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400218d0`

## callees

- `0x1400030c4`
- `0x140003448`
- `0x14001d4e8`
- `0x1400217f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002183a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002184c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002185e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002183a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002184c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002185e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002188e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002188e`

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
0x1400217f8  mov     [rsp+arg_0], rcx
0x1400217fd  push    rdi
0x1400217fe  sub     rsp, 30h
0x140021802  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14002180b  mov     [rsp+38h+arg_8], rbx
0x140021810  mov     rdi, rcx
0x140021813  xor     edx, edx
0x140021815  mov     rcx, [rcx]; Block
0x140021818  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002181d  mov     qword ptr [rdi], 0
0x140021824  mov     rcx, [rdi+8]; Block
0x140021828  call    cs:__imp_free
0x14002182e  mov     qword ptr [rdi+8], 0
0x140021836  mov     rcx, [rdi+10h]; Block
0x14002183a  call    cs:__imp_free
0x140021840  mov     qword ptr [rdi+10h], 0
0x140021848  mov     rcx, [rdi+18h]; Block
0x14002184c  call    cs:__imp_free
0x140021852  mov     qword ptr [rdi+18h], 0
0x14002185a  mov     rcx, [rdi+20h]; Block
0x14002185e  call    cs:__imp_free
0x140021864  mov     qword ptr [rdi+20h], 0
0x14002186c  mov     ecx, 28h ; '('; Size
0x140021871  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140021876  mov     [rdi], rax
0x140021879  jmp     short loc_140021880
0x14002187b  mov     rdi, [rsp+38h+arg_0]
0x140021880  cmp     qword ptr [rdi], 0
0x140021884  jz      short loc_1400218B8
0x140021886  mov     edx, 1; dwRevision
0x14002188b  mov     rcx, [rdi]; pSecurityDescriptor
0x14002188e  call    cs:__imp_InitializeSecurityDescriptor
0x140021894  test    eax, eax
0x140021896  jz      short loc_14002189C
0x140021898  xor     eax, eax
0x14002189a  jmp     short loc_1400218BD
0x14002189c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400218a1  mov     ebx, eax
0x1400218a3  xor     edx, edx
0x1400218a5  mov     rcx, [rdi]; Block
0x1400218a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400218ad  mov     qword ptr [rdi], 0
0x1400218b4  mov     eax, ebx
0x1400218b6  jmp     short loc_1400218BD
0x1400218b8  mov     eax, 8007000Eh
0x1400218bd  mov     rbx, [rsp+38h+arg_8]
0x1400218c2  add     rsp, 30h
0x1400218c6  pop     rdi
0x1400218c7  retn
```
