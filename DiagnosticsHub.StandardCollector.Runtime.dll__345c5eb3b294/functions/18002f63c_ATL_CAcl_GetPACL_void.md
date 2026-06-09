# ATL::CAcl::GetPACL(void)

- ea: `0x18002f63c`
- end: `0x18002f7ce`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `402`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002dfd0`
- `0x18002eb3c`
- `0x18002f7d0`

## callees

- `0x180002604`
- `0x18002f63c`
- `0x18003151c`
- `0x18004b640`

## import_xrefs

- `ADVAPI32!AddAce` at `0x18002f74f`
- `ADVAPI32!AddAce` at `0x18002f74f`
- `ADVAPI32!InitializeAcl` at `0x18002f6da`
- `ADVAPI32!InitializeAcl` at `0x18002f6da`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f78c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f7b8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f78c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f7b8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f6be`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f6be`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  ACL *v6; // rax
  unsigned int v7; // esi
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
      _mm_lfence();
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
    v7 = 0;
    if ( v4 )
    {
      _mm_lfence();
      do
      {
        v8 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, v7);
        v9 = v8;
        if ( !v8
          || (nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8),
              v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9),
              !AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v11, nAceListLength)) )
        {
          _mm_lfence();
          v13 = ATL::AtlHresultFromLastError();
          free(*((void **)this + 1));
          *((_QWORD *)this + 1) = 0;
          ATL::AtlThrowImpl(v13);
        }
        ++v7;
      }
      while ( v7 < v4 );
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18002f63c  mov     rax, rsp
0x18002f63f  mov     [rax+8], rbx
0x18002f643  mov     [rax+10h], rbp
0x18002f647  mov     [rax+18h], rsi
0x18002f64b  mov     [rax+20h], rdi
0x18002f64f  push    r14
0x18002f651  sub     rsp, 30h
0x18002f655  cmp     qword ptr [rcx+8], 0
0x18002f65a  mov     rdi, rcx
0x18002f65d  jnz     loc_18002F75F
0x18002f663  cmp     byte ptr [rcx+10h], 0
0x18002f667  jnz     loc_18002F75F
0x18002f66d  mov     rax, [rcx]
0x18002f670  mov     esi, 8
0x18002f675  mov     rax, [rax+8]
0x18002f679  call    cs:__guard_dispatch_icall_fptr
0x18002f67f  xor     ebx, ebx
0x18002f681  mov     ebp, eax
0x18002f683  test    eax, eax
0x18002f685  jz      short loc_18002F6BC
0x18002f687  lfence
0x18002f68a  mov     rcx, [rdi]
0x18002f68d  mov     edx, ebx
0x18002f68f  mov     rax, [rcx+20h]
0x18002f693  mov     rcx, rdi
0x18002f696  call    cs:__guard_dispatch_icall_fptr
0x18002f69c  mov     rdx, rax
0x18002f69f  test    rax, rax
0x18002f6a2  jz      short loc_18002F6B6
0x18002f6a4  mov     rcx, [rax]
0x18002f6a7  mov     rax, [rcx+10h]
0x18002f6ab  mov     rcx, rdx
0x18002f6ae  call    cs:__guard_dispatch_icall_fptr
0x18002f6b4  add     esi, eax
0x18002f6b6  inc     ebx
0x18002f6b8  cmp     ebx, ebp
0x18002f6ba  jb      short loc_18002F68A
0x18002f6bc  mov     ecx, esi; Size
0x18002f6be  call    cs:__imp_malloc
0x18002f6c4  mov     [rdi+8], rax
0x18002f6c8  test    rax, rax
0x18002f6cb  jz      loc_18002F7A2
0x18002f6d1  mov     r8d, [rdi+14h]; dwAclRevision
0x18002f6d5  mov     edx, esi; nAclLength
0x18002f6d7  mov     rcx, rax; pAcl
0x18002f6da  call    cs:__imp_InitializeAcl
0x18002f6e0  test    eax, eax
0x18002f6e2  jz      loc_18002F7AD
0x18002f6e8  mov     rax, [rdi]
0x18002f6eb  mov     rcx, rdi
0x18002f6ee  mov     rax, [rax+28h]
0x18002f6f2  call    cs:__guard_dispatch_icall_fptr
0x18002f6f8  xor     esi, esi
0x18002f6fa  test    ebp, ebp
0x18002f6fc  jz      short loc_18002F75F
0x18002f6fe  lfence
0x18002f701  mov     rax, [rdi]
0x18002f704  mov     edx, esi
0x18002f706  mov     rcx, rdi
0x18002f709  mov     rax, [rax+20h]
0x18002f70d  call    cs:__guard_dispatch_icall_fptr
0x18002f713  mov     r14, rax
0x18002f716  test    rax, rax
0x18002f719  jz      short loc_18002F77E
0x18002f71b  mov     rcx, [rax]
0x18002f71e  mov     rax, [rcx+10h]
0x18002f722  mov     rcx, r14
0x18002f725  call    cs:__guard_dispatch_icall_fptr
0x18002f72b  mov     rcx, [r14]
0x18002f72e  mov     ebx, eax
0x18002f730  mov     rax, [rcx+8]
0x18002f734  mov     rcx, r14
0x18002f737  call    cs:__guard_dispatch_icall_fptr
0x18002f73d  mov     edx, [rdi+14h]; dwAceRevision
0x18002f740  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18002f744  mov     rcx, [rdi+8]; pAcl
0x18002f748  mov     r9, rax; pAceList
0x18002f74b  mov     [rsp+38h+nAceListLength], ebx; nAceListLength
0x18002f74f  call    cs:__imp_AddAce
0x18002f755  test    eax, eax
0x18002f757  jz      short loc_18002F77E
0x18002f759  inc     esi
0x18002f75b  cmp     esi, ebp
0x18002f75d  jb      short loc_18002F701
0x18002f75f  mov     rax, [rdi+8]
0x18002f763  mov     rdi, [rsp+38h+arg_18]
0x18002f768  mov     rbx, [rsp+38h+arg_0]
0x18002f76d  mov     rbp, [rsp+38h+arg_8]
0x18002f772  mov     rsi, [rsp+38h+arg_10]
0x18002f777  add     rsp, 30h
0x18002f77b  pop     r14
0x18002f77d  retn
0x18002f77e  lfence
0x18002f781  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f786  mov     rcx, [rdi+8]; Block
0x18002f78a  mov     ebx, eax
0x18002f78c  call    cs:__imp_free
0x18002f792  mov     ecx, ebx; int
0x18002f794  mov     qword ptr [rdi+8], 0
0x18002f79c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f7a2  mov     ecx, 8007000Eh; int
0x18002f7a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f7ad  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f7b2  mov     rcx, [rdi+8]; Block
0x18002f7b6  mov     ebx, eax
0x18002f7b8  call    cs:__imp_free
0x18002f7be  mov     ecx, ebx; int
0x18002f7c0  mov     qword ptr [rdi+8], 0
0x18002f7c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
