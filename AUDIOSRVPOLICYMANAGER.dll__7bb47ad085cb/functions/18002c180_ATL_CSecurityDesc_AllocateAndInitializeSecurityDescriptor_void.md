# ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)

- ea: `0x18002c180`
- end: `0x18002c1ea`
- name: `?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ`
- size: `106`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x18002bd9c`
- `0x18002c180`
- `0x18002ccf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c1c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c1c9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c192`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c192`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002c1b4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002c1b4`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(ATL::CSecurityDesc *this)
{
  void *v2; // rax
  int Error; // ebx

  v2 = malloc(0x28u);
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !InitializeSecurityDescriptor(v2, 1u) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::AtlThrowImpl(Error);
  }
}

```

## disassembly

```asm
0x18002c180  mov     [rsp+arg_0], rbx
0x18002c185  push    rdi
0x18002c186  sub     rsp, 20h
0x18002c18a  mov     rdi, rcx
0x18002c18d  mov     ecx, 28h ; '('; Size
0x18002c192  call    cs:__imp_malloc
0x18002c198  mov     [rdi+8], rax
0x18002c19c  test    rax, rax
0x18002c19f  jnz     short loc_18002C1AC
0x18002c1a1  mov     ecx, 8007000Eh; int
0x18002c1a6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c1ac  mov     edx, 1; dwRevision
0x18002c1b1  mov     rcx, rax; pSecurityDescriptor
0x18002c1b4  call    cs:__imp_InitializeSecurityDescriptor
0x18002c1ba  test    eax, eax
0x18002c1bc  jnz     short loc_18002C1DF
0x18002c1be  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002c1c3  mov     rcx, [rdi+8]; Block
0x18002c1c7  mov     ebx, eax
0x18002c1c9  call    cs:__imp_free
0x18002c1cf  mov     ecx, ebx; int
0x18002c1d1  mov     qword ptr [rdi+8], 0
0x18002c1d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c1df  mov     rbx, [rsp+28h+arg_0]
0x18002c1e4  add     rsp, 20h
0x18002c1e8  pop     rdi
0x18002c1e9  retn
```
