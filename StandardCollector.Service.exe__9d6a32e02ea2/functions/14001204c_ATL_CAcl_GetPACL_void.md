# ATL::CAcl::GetPACL(void)

- ea: `0x14001204c`
- end: `0x1400121de`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `402`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400121e0`

## callees

- `0x140002e74`
- `0x14000916c`
- `0x14001204c`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x1400120ea`
- `ADVAPI32!InitializeAcl` at `0x1400120ea`
- `ADVAPI32!AddAce` at `0x14001215f`
- `ADVAPI32!AddAce` at `0x14001215f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400120ce`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400120ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001219c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400121c8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001219c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400121c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14001204c  mov     rax, rsp
0x14001204f  mov     [rax+8], rbx
0x140012053  mov     [rax+10h], rbp
0x140012057  mov     [rax+18h], rsi
0x14001205b  mov     [rax+20h], rdi
0x14001205f  push    r14
0x140012061  sub     rsp, 30h
0x140012065  cmp     qword ptr [rcx+8], 0
0x14001206a  mov     rdi, rcx
0x14001206d  jnz     loc_14001216F
0x140012073  cmp     byte ptr [rcx+10h], 0
0x140012077  jnz     loc_14001216F
0x14001207d  mov     rax, [rcx]
0x140012080  mov     esi, 8
0x140012085  mov     rax, [rax+8]
0x140012089  call    cs:__guard_dispatch_icall_fptr
0x14001208f  xor     ebx, ebx
0x140012091  mov     ebp, eax
0x140012093  test    eax, eax
0x140012095  jz      short loc_1400120CC
0x140012097  lfence
0x14001209a  mov     rcx, [rdi]
0x14001209d  mov     edx, ebx
0x14001209f  mov     rax, [rcx+20h]
0x1400120a3  mov     rcx, rdi
0x1400120a6  call    cs:__guard_dispatch_icall_fptr
0x1400120ac  mov     rdx, rax
0x1400120af  test    rax, rax
0x1400120b2  jz      short loc_1400120C6
0x1400120b4  mov     rcx, [rax]
0x1400120b7  mov     rax, [rcx+10h]
0x1400120bb  mov     rcx, rdx
0x1400120be  call    cs:__guard_dispatch_icall_fptr
0x1400120c4  add     esi, eax
0x1400120c6  inc     ebx
0x1400120c8  cmp     ebx, ebp
0x1400120ca  jb      short loc_14001209A
0x1400120cc  mov     ecx, esi; Size
0x1400120ce  call    cs:__imp_malloc
0x1400120d4  mov     [rdi+8], rax
0x1400120d8  test    rax, rax
0x1400120db  jz      loc_1400121B2
0x1400120e1  mov     r8d, [rdi+14h]; dwAclRevision
0x1400120e5  mov     edx, esi; nAclLength
0x1400120e7  mov     rcx, rax; pAcl
0x1400120ea  call    cs:__imp_InitializeAcl
0x1400120f0  test    eax, eax
0x1400120f2  jz      loc_1400121BD
0x1400120f8  mov     rax, [rdi]
0x1400120fb  mov     rcx, rdi
0x1400120fe  mov     rax, [rax+28h]
0x140012102  call    cs:__guard_dispatch_icall_fptr
0x140012108  xor     esi, esi
0x14001210a  test    ebp, ebp
0x14001210c  jz      short loc_14001216F
0x14001210e  lfence
0x140012111  mov     rax, [rdi]
0x140012114  mov     edx, esi
0x140012116  mov     rcx, rdi
0x140012119  mov     rax, [rax+20h]
0x14001211d  call    cs:__guard_dispatch_icall_fptr
0x140012123  mov     r14, rax
0x140012126  test    rax, rax
0x140012129  jz      short loc_14001218E
0x14001212b  mov     rcx, [rax]
0x14001212e  mov     rax, [rcx+10h]
0x140012132  mov     rcx, r14
0x140012135  call    cs:__guard_dispatch_icall_fptr
0x14001213b  mov     rcx, [r14]
0x14001213e  mov     ebx, eax
0x140012140  mov     rax, [rcx+8]
0x140012144  mov     rcx, r14
0x140012147  call    cs:__guard_dispatch_icall_fptr
0x14001214d  mov     edx, [rdi+14h]; dwAceRevision
0x140012150  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140012154  mov     rcx, [rdi+8]; pAcl
0x140012158  mov     r9, rax; pAceList
0x14001215b  mov     [rsp+38h+nAceListLength], ebx; nAceListLength
0x14001215f  call    cs:__imp_AddAce
0x140012165  test    eax, eax
0x140012167  jz      short loc_14001218E
0x140012169  inc     esi
0x14001216b  cmp     esi, ebp
0x14001216d  jb      short loc_140012111
0x14001216f  mov     rax, [rdi+8]
0x140012173  mov     rdi, [rsp+38h+arg_18]
0x140012178  mov     rbx, [rsp+38h+arg_0]
0x14001217d  mov     rbp, [rsp+38h+arg_8]
0x140012182  mov     rsi, [rsp+38h+arg_10]
0x140012187  add     rsp, 30h
0x14001218b  pop     r14
0x14001218d  retn
0x14001218e  lfence
0x140012191  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140012196  mov     rcx, [rdi+8]; Block
0x14001219a  mov     ebx, eax
0x14001219c  call    cs:__imp_free
0x1400121a2  mov     ecx, ebx; int
0x1400121a4  mov     qword ptr [rdi+8], 0
0x1400121ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400121b2  mov     ecx, 8007000Eh; int
0x1400121b7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400121bd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400121c2  mov     rcx, [rdi+8]; Block
0x1400121c6  mov     ebx, eax
0x1400121c8  call    cs:__imp_free
0x1400121ce  mov     ecx, ebx; int
0x1400121d0  mov     qword ptr [rdi+8], 0
0x1400121d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
