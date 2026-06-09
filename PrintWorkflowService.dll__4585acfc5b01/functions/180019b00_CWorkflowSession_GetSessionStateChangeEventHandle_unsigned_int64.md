# CWorkflowSession::GetSessionStateChangeEventHandle(unsigned __int64 *)

- ea: `0x180019b00`
- end: `0x180019c4f`
- name: `?GetSessionStateChangeEventHandle@CWorkflowSession@@UEAAJPEA_K@Z`
- size: `335`
- prototype: `int(CWorkflowSession *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003d14`
- `0x18000b360`
- `0x180010b0c`
- `0x180018c6c`
- `0x180019b00`
- `0x180019da0`
- `0x18001a704`
- `0x180021570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019bd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019bd7`

## string_xrefs

- `0x180019b24`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x180019bfa`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x180019c3d`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkflowSession::GetSessionStateChangeEventHandle(CWorkflowSession *this, unsigned __int64 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  HANDLE *v7; // rax
  const char *v8; // r9
  HANDLE *v9; // rbx
  HANDLE **v10; // rdx
  int v11; // eax
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE *v15; // [rsp+38h] [rbp+10h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 685;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      (const char *)(unsigned int)v4,
      v13);
    return (unsigned int)v4;
  }
  v7 = (HANDLE *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v7;
  if ( v7 )
  {
    v7[1] = 0;
    v7[2] = 0;
    *v7 = &EventList::EventListNode::`vftable';
    v7[3] = 0;
  }
  else
  {
    v9 = 0;
  }
  v15 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2B2,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      v8);
  wil::AcquireSRWLockExclusive(&SRWLock, (char *)this + 248);
  v10 = (HANDLE **)*((_QWORD *)this + 21);
  if ( v10 == *((HANDLE ***)this + 22) )
  {
    std::vector<EventList::EventListNode *>::_Emplace_reallocate<EventList::EventListNode * const &>(
      (char *)this + 160,
      v10,
      &v15);
    v9 = v15;
  }
  else
  {
    *v10 = v9;
    *((_QWORD *)this + 21) += 8LL;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v11 = EventList::EventListNode::InitializeAndAddToList(
          (EventList::EventListNode *)v9,
          (CWorkflowSession *)((char *)this + 184));
  v12 = v11;
  if ( v11 >= 0 )
  {
    v4 = DuplicateHandleToClient(v9[3], a2);
    if ( v4 < 0 )
    {
      v5 = 702;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BA,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      (const char *)(unsigned int)v11,
      v13);
    return v12;
  }
}

```

## disassembly

```asm
0x180019b00  mov     [rsp+arg_0], rbx
0x180019b05  mov     [rsp+arg_18], rsi
0x180019b0a  push    rdi; int
0x180019b0b  sub     rsp, 20h
0x180019b0f  mov     rsi, rdx
0x180019b12  mov     rdi, rcx
0x180019b15  test    rdx, rdx
0x180019b18  jnz     short loc_180019B3F
0x180019b1a  mov     ebx, 80004003h
0x180019b1f  mov     edx, 2ADh; void *
0x180019b24  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x180019b2b  mov     r9d, ebx; char *
0x180019b2e  mov     rcx, [rsp+28h]; this
0x180019b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b38  mov     eax, ebx
0x180019b3a  jmp     loc_180019C2D
0x180019b3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019b46  mov     ecx, 20h ; ' '; unsigned __int64
0x180019b4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019b50  mov     rbx, rax
0x180019b53  test    rax, rax
0x180019b56  jz      short loc_180019B7C
0x180019b58  mov     qword ptr [rax+8], 0
0x180019b60  mov     qword ptr [rax+10h], 0
0x180019b68  lea     rax, ??_7EventListNode@EventList@@6B@; const EventList::EventListNode::`vftable'
0x180019b6f  mov     [rbx], rax
0x180019b72  mov     qword ptr [rbx+18h], 0
0x180019b7a  jmp     short loc_180019B7E
0x180019b7c  xor     ebx, ebx
0x180019b7e  mov     [rsp+28h+arg_8], rbx
0x180019b83  mov     rcx, [rsp+28h]; this
0x180019b88  test    rbx, rbx
0x180019b8b  jz      loc_180019C3D
0x180019b91  lea     rdx, [rdi+0F8h]
0x180019b98  lea     rcx, [rsp+28h+SRWLock]
0x180019b9d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180019ba2  nop
0x180019ba3  lea     rcx, [rdi+0A0h]
0x180019baa  mov     rdx, [rcx+8]
0x180019bae  cmp     rdx, [rcx+10h]
0x180019bb2  jz      short loc_180019BBE
0x180019bb4  mov     [rdx], rbx
0x180019bb7  add     qword ptr [rcx+8], 8
0x180019bbc  jmp     short loc_180019BCD
0x180019bbe  lea     r8, [rsp+28h+arg_8]
0x180019bc3  call    ??$_Emplace_reallocate@AEBQEAVEventListNode@EventList@@@?$vector@PEAVEventListNode@EventList@@V?$allocator@PEAVEventListNode@EventList@@@std@@@std@@AEAAPEAPEAVEventListNode@EventList@@QEAPEAV23@AEBQEAV23@@Z; std::vector<EventList::EventListNode *>::_Emplace_reallocate<EventList::EventListNode * const &>(EventList::EventListNode * * const,EventList::EventListNode * const &)
0x180019bc8  mov     rbx, [rsp+28h+arg_8]
0x180019bcd  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180019bd2  test    rcx, rcx
0x180019bd5  jz      short loc_180019BDD
0x180019bd7  call    cs:__imp_ReleaseSRWLockExclusive
0x180019bdd  lea     rdx, [rdi+0B8h]; struct EventList *
0x180019be4  mov     rcx, rbx; this
0x180019be7  call    ?InitializeAndAddToList@EventListNode@EventList@@QEAAJPEAV2@@Z; EventList::EventListNode::InitializeAndAddToList(EventList *)
0x180019bec  mov     edi, eax
0x180019bee  test    eax, eax
0x180019bf0  jns     short loc_180019C0F
0x180019bf2  mov     rcx, [rsp+28h]; this
0x180019bf7  mov     r9d, eax; char *
0x180019bfa  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x180019c01  mov     edx, 2BAh; void *
0x180019c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c0b  mov     eax, edi
0x180019c0d  jmp     short loc_180019C2D
0x180019c0f  mov     rdx, rsi; unsigned __int64 *
0x180019c12  mov     rcx, [rbx+18h]; hSourceHandle
0x180019c16  call    ?DuplicateHandleToClient@@YAJPEAXPEA_K@Z; DuplicateHandleToClient(void *,unsigned __int64 *)
0x180019c1b  mov     ebx, eax
0x180019c1d  test    eax, eax
0x180019c1f  jns     short loc_180019C2B
0x180019c21  mov     edx, 2BEh
0x180019c26  jmp     loc_180019B24
0x180019c2b  xor     eax, eax
0x180019c2d  mov     rbx, [rsp+28h+arg_0]
0x180019c32  mov     rsi, [rsp+28h+arg_18]
0x180019c37  add     rsp, 20h
0x180019c3b  pop     rdi
0x180019c3c  retn
0x180019c3d  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x180019c44  mov     edx, 2B2h; void *
0x180019c49  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
