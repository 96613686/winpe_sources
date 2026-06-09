# ATL::CAcl::GetPACL(void)

- ea: `0x1800130d0`
- end: `0x18001322c`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `348`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cc8c`

## callees

- `0x1800130d0`
- `0x180019e00`
- `0x18001a5e0`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013176`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013207`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013176`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013207`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001313e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001313e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800131ee`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800131ee`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180013161`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180013161`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // edi
  unsigned int v3; // ebp
  unsigned int v4; // esi
  __int64 v5; // rax
  struct _ACL *v6; // rax
  int Error; // edi
  unsigned int i; // ebp
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // edi
  void *v12; // rax
  int v13; // edi

  if ( !*((_QWORD *)this + 1) && !*((_BYTE *)this + 16) )
  {
    v2 = 8;
    v3 = 0;
    v4 = (*(__int64 (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 8LL))(this);
    if ( v4 )
    {
      do
      {
        v5 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, v3);
        if ( v5 )
          v2 += (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        ++v3;
      }
      while ( v3 < v4 );
    }
    v6 = (struct _ACL *)malloc(v2);
    *((_QWORD *)this + 1) = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !InitializeAcl(v6, v2, *((_DWORD *)this + 5)) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(Error);
    }
    (*(void (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 40LL))(this);
    for ( i = 0; i < v4; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v10 = v9;
      if ( v9 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v12 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v12, nAceListLength) )
          continue;
      }
      v13 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v13);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1800130d0  push    rbx
0x1800130d2  push    rbp
0x1800130d3  push    rsi
0x1800130d4  push    rdi
0x1800130d5  push    r14
0x1800130d7  sub     rsp, 30h
0x1800130db  cmp     qword ptr [rcx+8], 0
0x1800130e0  mov     rbx, rcx
0x1800130e3  jnz     loc_18001321D
0x1800130e9  cmp     byte ptr [rcx+10h], 0
0x1800130ed  jnz     loc_18001321D
0x1800130f3  mov     rax, [rcx]
0x1800130f6  mov     edi, 8
0x1800130fb  mov     rax, [rax+8]
0x1800130ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013104  xor     ebp, ebp
0x180013106  mov     esi, eax
0x180013108  test    eax, eax
0x18001310a  jz      short loc_18001313C
0x18001310c  mov     rcx, [rbx]
0x18001310f  mov     edx, ebp
0x180013111  mov     rax, [rcx+20h]
0x180013115  mov     rcx, rbx
0x180013118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001311d  mov     rdx, rax
0x180013120  test    rax, rax
0x180013123  jz      short loc_180013136
0x180013125  mov     rcx, [rax]
0x180013128  mov     rax, [rcx+10h]
0x18001312c  mov     rcx, rdx
0x18001312f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013134  add     edi, eax
0x180013136  inc     ebp
0x180013138  cmp     ebp, esi
0x18001313a  jb      short loc_18001310C
0x18001313c  mov     ecx, edi; Size
0x18001313e  call    cs:__imp_malloc
0x180013144  mov     [rbx+8], rax
0x180013148  test    rax, rax
0x18001314b  jnz     short loc_180013158
0x18001314d  mov     ecx, 8007000Eh; int
0x180013152  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013158  mov     r8d, [rbx+14h]; dwAclRevision
0x18001315c  mov     edx, edi; nAclLength
0x18001315e  mov     rcx, rax; pAcl
0x180013161  call    cs:__imp_InitializeAcl
0x180013167  test    eax, eax
0x180013169  jnz     short loc_18001318C
0x18001316b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013170  mov     rcx, [rbx+8]; Block
0x180013174  mov     edi, eax
0x180013176  call    cs:__imp_free
0x18001317c  mov     ecx, edi; int
0x18001317e  mov     qword ptr [rbx+8], 0
0x180013186  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001318c  mov     rax, [rbx]
0x18001318f  mov     rcx, rbx
0x180013192  mov     rax, [rax+28h]
0x180013196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001319b  xor     ebp, ebp
0x18001319d  cmp     ebp, esi
0x18001319f  jnb     short loc_18001321D
0x1800131a1  mov     rax, [rbx]
0x1800131a4  mov     edx, ebp
0x1800131a6  mov     rcx, rbx
0x1800131a9  mov     rax, [rax+20h]
0x1800131ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b2  mov     r14, rax
0x1800131b5  test    rax, rax
0x1800131b8  jz      short loc_1800131FC
0x1800131ba  mov     rcx, [rax]
0x1800131bd  mov     rax, [rcx+10h]
0x1800131c1  mov     rcx, r14
0x1800131c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131c9  mov     rcx, [r14]
0x1800131cc  mov     edi, eax
0x1800131ce  mov     rax, [rcx+8]
0x1800131d2  mov     rcx, r14
0x1800131d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131da  mov     edx, [rbx+14h]; dwAceRevision
0x1800131dd  mov     r9, rax; pAceList
0x1800131e0  mov     rcx, [rbx+8]; pAcl
0x1800131e4  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800131ea  mov     [rsp+58h+nAceListLength], edi; nAceListLength
0x1800131ee  call    cs:__imp_AddAce
0x1800131f4  test    eax, eax
0x1800131f6  jz      short loc_1800131FC
0x1800131f8  inc     ebp
0x1800131fa  jmp     short loc_18001319D
0x1800131fc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013201  mov     rcx, [rbx+8]; Block
0x180013205  mov     edi, eax
0x180013207  call    cs:__imp_free
0x18001320d  mov     ecx, edi; int
0x18001320f  mov     qword ptr [rbx+8], 0
0x180013217  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001321d  mov     rax, [rbx+8]
0x180013221  add     rsp, 30h
0x180013225  pop     r14
0x180013227  pop     rdi
0x180013228  pop     rsi
0x180013229  pop     rbp
0x18001322a  pop     rbx
0x18001322b  retn
```
