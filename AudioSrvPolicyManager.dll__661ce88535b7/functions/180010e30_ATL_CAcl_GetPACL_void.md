# ATL::CAcl::GetPACL(void)

- ea: `0x180010e30`
- end: `0x180010f9b`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `363`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f744`
- `0x18001039c`

## callees

- `0x180010e30`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010f85`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010e9e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010e9e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180010f31`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180010f31`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180010eba`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180010eba`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // edi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  unsigned int i; // ebx
  __int64 v8; // rax
  __int64 v9; // r14
  DWORD nAceListLength; // edi
  void *v11; // rax
  int Error; // ebx
  int v14; // ebx

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
      v8 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v9 = v8;
      if ( v8 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v11, nAceListLength) )
          continue;
      }
      v14 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v14);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180010e30  push    rbx
0x180010e32  push    rbp
0x180010e33  push    rsi
0x180010e34  push    rdi
0x180010e35  push    r14
0x180010e37  sub     rsp, 30h
0x180010e3b  cmp     qword ptr [rcx+8], 0
0x180010e40  mov     rsi, rcx
0x180010e43  jnz     loc_180010F3F
0x180010e49  cmp     byte ptr [rcx+10h], 0
0x180010e4d  jnz     loc_180010F3F
0x180010e53  mov     rax, [rcx]
0x180010e56  mov     edi, 8
0x180010e5b  mov     rax, [rax+8]
0x180010e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e64  xor     ebx, ebx
0x180010e66  mov     ebp, eax
0x180010e68  test    eax, eax
0x180010e6a  jz      short loc_180010E9C
0x180010e6c  mov     rcx, [rsi]
0x180010e6f  mov     edx, ebx
0x180010e71  mov     rax, [rcx+20h]
0x180010e75  mov     rcx, rsi
0x180010e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e7d  mov     rdx, rax
0x180010e80  test    rax, rax
0x180010e83  jz      short loc_180010E96
0x180010e85  mov     rcx, [rax]
0x180010e88  mov     rax, [rcx+10h]
0x180010e8c  mov     rcx, rdx
0x180010e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e94  add     edi, eax
0x180010e96  inc     ebx
0x180010e98  cmp     ebx, ebp
0x180010e9a  jb      short loc_180010E6C
0x180010e9c  mov     ecx, edi; Size
0x180010e9e  call    cs:__imp_malloc
0x180010ea4  mov     [rsi+8], rax
0x180010ea8  test    rax, rax
0x180010eab  jz      loc_180010F6F
0x180010eb1  mov     r8d, [rsi+14h]; dwAclRevision
0x180010eb5  mov     edx, edi; nAclLength
0x180010eb7  mov     rcx, rax; pAcl
0x180010eba  call    cs:__imp_InitializeAcl
0x180010ec0  test    eax, eax
0x180010ec2  jz      loc_180010F4E
0x180010ec8  mov     rax, [rsi]
0x180010ecb  mov     rcx, rsi
0x180010ece  mov     rax, [rax+28h]
0x180010ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ed7  xor     ebx, ebx
0x180010ed9  nop     dword ptr [rax+00000000h]
0x180010ee0  cmp     ebx, ebp
0x180010ee2  jnb     short loc_180010F3F
0x180010ee4  mov     rax, [rsi]
0x180010ee7  mov     edx, ebx
0x180010ee9  mov     rcx, rsi
0x180010eec  mov     rax, [rax+20h]
0x180010ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef5  mov     r14, rax
0x180010ef8  test    rax, rax
0x180010efb  jz      short loc_180010F7A
0x180010efd  mov     rcx, [rax]
0x180010f00  mov     rax, [rcx+10h]
0x180010f04  mov     rcx, r14
0x180010f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0c  mov     rcx, [r14]
0x180010f0f  mov     edi, eax
0x180010f11  mov     rax, [rcx+8]
0x180010f15  mov     rcx, r14
0x180010f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f1d  mov     edx, [rsi+14h]; dwAceRevision
0x180010f20  mov     r9, rax; pAceList
0x180010f23  mov     rcx, [rsi+8]; pAcl
0x180010f27  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180010f2d  mov     [rsp+58h+nAceListLength], edi; nAceListLength
0x180010f31  call    cs:__imp_AddAce
0x180010f37  test    eax, eax
0x180010f39  jz      short loc_180010F7A
0x180010f3b  inc     ebx
0x180010f3d  jmp     short loc_180010EE0
0x180010f3f  mov     rax, [rsi+8]
0x180010f43  add     rsp, 30h
0x180010f47  pop     r14
0x180010f49  pop     rdi
0x180010f4a  pop     rsi
0x180010f4b  pop     rbp
0x180010f4c  pop     rbx
0x180010f4d  retn
0x180010f4e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010f53  mov     rcx, [rsi+8]; Block
0x180010f57  mov     ebx, eax
0x180010f59  call    cs:__imp_free
0x180010f5f  mov     ecx, ebx; int
0x180010f61  mov     qword ptr [rsi+8], 0
0x180010f69  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010f6f  mov     ecx, 8007000Eh; int
0x180010f74  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010f7a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010f7f  mov     rcx, [rsi+8]; Block
0x180010f83  mov     ebx, eax
0x180010f85  call    cs:__imp_free
0x180010f8b  mov     ecx, ebx; int
0x180010f8d  mov     qword ptr [rsi+8], 0
0x180010f95  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
