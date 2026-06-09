# ATL::CAcl::GetPACL(void)

- ea: `0x14000cc28`
- end: `0x14000cd8c`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `356`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140012754`

## callees

- `0x14000a220`
- `0x14000a2e8`
- `0x14000cc28`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x14000ccb2`
- `ADVAPI32!InitializeAcl` at `0x14000ccb2`
- `ADVAPI32!AddAce` at `0x14000cd20`
- `ADVAPI32!AddAce` at `0x14000cd20`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cd4a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cd76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cd4a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cd76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000cc96`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000cc96`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  ACL *v6; // rax
  unsigned int i; // esi
  __int64 v8; // rax
  __int64 v9; // r14
  DWORD nAceListLength; // ebx
  void *v11; // rax
  int v13; // ebx
  int Error; // ebx

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
    v6 = (ACL *)malloc(v2);
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
      v8 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v9 = v8;
      if ( v8 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v11, nAceListLength) )
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
0x14000cc28  push    rbx
0x14000cc2a  push    rbp
0x14000cc2b  push    rsi
0x14000cc2c  push    rdi
0x14000cc2d  push    r14
0x14000cc2f  sub     rsp, 30h
0x14000cc33  cmp     qword ptr [rcx+8], 0
0x14000cc38  mov     rdi, rcx
0x14000cc3b  jnz     loc_14000CD30
0x14000cc41  cmp     byte ptr [rcx+10h], 0
0x14000cc45  jnz     loc_14000CD30
0x14000cc4b  mov     rax, [rcx]
0x14000cc4e  mov     esi, 8
0x14000cc53  mov     rax, [rax+8]
0x14000cc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc5c  xor     ebx, ebx
0x14000cc5e  mov     ebp, eax
0x14000cc60  test    eax, eax
0x14000cc62  jz      short loc_14000CC94
0x14000cc64  mov     rcx, [rdi]
0x14000cc67  mov     edx, ebx
0x14000cc69  mov     rax, [rcx+20h]
0x14000cc6d  mov     rcx, rdi
0x14000cc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc75  mov     rdx, rax
0x14000cc78  test    rax, rax
0x14000cc7b  jz      short loc_14000CC8E
0x14000cc7d  mov     rcx, [rax]
0x14000cc80  mov     rax, [rcx+10h]
0x14000cc84  mov     rcx, rdx
0x14000cc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc8c  add     esi, eax
0x14000cc8e  inc     ebx
0x14000cc90  cmp     ebx, ebp
0x14000cc92  jb      short loc_14000CC64
0x14000cc94  mov     ecx, esi; Size
0x14000cc96  call    cs:__imp_malloc
0x14000cc9c  mov     [rdi+8], rax
0x14000cca0  test    rax, rax
0x14000cca3  jz      loc_14000CD60
0x14000cca9  mov     r8d, [rdi+14h]; dwAclRevision
0x14000ccad  mov     edx, esi; nAclLength
0x14000ccaf  mov     rcx, rax; pAcl
0x14000ccb2  call    cs:__imp_InitializeAcl
0x14000ccb8  test    eax, eax
0x14000ccba  jz      loc_14000CD6B
0x14000ccc0  mov     rax, [rdi]
0x14000ccc3  mov     rcx, rdi
0x14000ccc6  mov     rax, [rax+28h]
0x14000ccca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cccf  xor     esi, esi
0x14000ccd1  test    ebp, ebp
0x14000ccd3  jz      short loc_14000CD30
0x14000ccd5  mov     rax, [rdi]
0x14000ccd8  mov     edx, esi
0x14000ccda  mov     rcx, rdi
0x14000ccdd  mov     rax, [rax+20h]
0x14000cce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cce6  mov     r14, rax
0x14000cce9  test    rax, rax
0x14000ccec  jz      short loc_14000CD3F
0x14000ccee  mov     rcx, [rax]
0x14000ccf1  mov     rax, [rcx+10h]
0x14000ccf5  mov     rcx, r14
0x14000ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccfd  mov     rcx, [r14]
0x14000cd00  mov     ebx, eax
0x14000cd02  mov     rax, [rcx+8]
0x14000cd06  mov     rcx, r14
0x14000cd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd0e  mov     edx, [rdi+14h]; dwAceRevision
0x14000cd11  mov     r9, rax; pAceList
0x14000cd14  mov     rcx, [rdi+8]; pAcl
0x14000cd18  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14000cd1c  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x14000cd20  call    cs:__imp_AddAce
0x14000cd26  test    eax, eax
0x14000cd28  jz      short loc_14000CD3F
0x14000cd2a  inc     esi
0x14000cd2c  cmp     esi, ebp
0x14000cd2e  jb      short loc_14000CCD5
0x14000cd30  mov     rax, [rdi+8]
0x14000cd34  add     rsp, 30h
0x14000cd38  pop     r14
0x14000cd3a  pop     rdi
0x14000cd3b  pop     rsi
0x14000cd3c  pop     rbp
0x14000cd3d  pop     rbx
0x14000cd3e  retn
0x14000cd3f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000cd44  mov     rcx, [rdi+8]; Block
0x14000cd48  mov     ebx, eax
0x14000cd4a  call    cs:__imp_free
0x14000cd50  mov     ecx, ebx; int
0x14000cd52  mov     qword ptr [rdi+8], 0
0x14000cd5a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000cd60  mov     ecx, 8007000Eh; int
0x14000cd65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000cd6b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000cd70  mov     rcx, [rdi+8]; Block
0x14000cd74  mov     ebx, eax
0x14000cd76  call    cs:__imp_free
0x14000cd7c  mov     ecx, ebx; int
0x14000cd7e  mov     qword ptr [rdi+8], 0
0x14000cd86  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
