# ChangeGroup::GetMWKWithPrerequisiteComplementedByDKWithMoveinsExcluded(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *,int *)

- ea: `0x180079294`
- end: `0x180079382`
- name: `?GetMWKWithPrerequisiteComplementedByDKWithMoveinsExcluded@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@PEAH@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct ISyncKnowledge **this, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180051190`
- `0x180057700`

## callees

- `0x1800787c0`
- `0x180079294`
- `0x180079770`
- `0x180079928`
- `0x180079a70`
- `0x180079da0`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::GetMWKWithPrerequisiteComplementedByDKWithMoveinsExcluded(
        struct ISyncKnowledge **this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        struct ISyncKnowledge **a4,
        int *a5)
{
  unsigned int v9; // ebx
  unsigned int IsDestinationKnowledgeSpecificCacheValid; // eax
  struct ISyncKnowledge *v11; // rcx

  if ( !a2 || !a4 || !a5 )
    return (unsigned int)-2147467261;
  if ( this[5] )
  {
    IsDestinationKnowledgeSpecificCacheValid = ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(
                                                 (ChangeGroup *)this,
                                                 a2,
                                                 1);
    v9 = IsDestinationKnowledgeSpecificCacheValid;
    if ( IsDestinationKnowledgeSpecificCacheValid == 1 )
    {
      ChangeGroup::InvalidateDestinationKnowledgeSpecificCache((ChangeGroup *)this);
      v9 = 0;
    }
    else if ( IsDestinationKnowledgeSpecificCacheValid )
    {
      return v9;
    }
    if ( (a3 == (struct IEnumItemIds *)this[23]
       || (v9 = ChangeGroup::PopulateMovedInItemIdCache((ChangeGroup *)this, a3)) == 0)
      && (this[18]
       || (v9 = ChangeGroup::CalculateMWKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(
                  (ChangeGroup *)this,
                  a2)) == 0)
      && (this[7] || (v9 = ChangeGroup::SetDestinationKnowledgeCookie((ChangeGroup *)this, a2)) == 0) )
    {
      v11 = this[18];
      *a4 = v11;
      ((void (__fastcall *)(struct ISyncKnowledge *))v11->lpVtbl->AddRef)(v11);
      *a5 = *((_DWORD *)this + 12);
    }
  }
  else
  {
    return (unsigned int)-2147217399;
  }
  return v9;
}

```

## disassembly

```asm
0x180079294  push    rbx
0x180079296  push    rbp
0x180079297  push    rsi
0x180079298  push    rdi
0x180079299  push    r14
0x18007929b  push    r15
0x18007929d  sub     rsp, 28h
0x1800792a1  mov     r15, r9
0x1800792a4  mov     rbp, r8
0x1800792a7  mov     rsi, rdx
0x1800792aa  mov     rdi, rcx
0x1800792ad  test    rdx, rdx
0x1800792b0  jz      loc_18007936E
0x1800792b6  test    r9, r9
0x1800792b9  jz      loc_18007936E
0x1800792bf  mov     r14, [rsp+58h+arg_20]
0x1800792c7  test    r14, r14
0x1800792ca  jz      loc_18007936E
0x1800792d0  cmp     qword ptr [rcx+28h], 0
0x1800792d5  jnz     short loc_1800792E1
0x1800792d7  mov     ebx, 80041009h
0x1800792dc  jmp     loc_180079373
0x1800792e1  mov     r8d, 1; int
0x1800792e7  call    ?IsDestinationKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUISyncKnowledge@@H@Z; ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(ISyncKnowledge *,int)
0x1800792ec  mov     ebx, eax
0x1800792ee  cmp     eax, 1
0x1800792f1  jnz     short loc_1800792FF
0x1800792f3  mov     rcx, rdi; this
0x1800792f6  call    ?InvalidateDestinationKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(void)
0x1800792fb  xor     ebx, ebx
0x1800792fd  jmp     short loc_180079303
0x1800792ff  test    eax, eax
0x180079301  jnz     short loc_180079373
0x180079303  cmp     rbp, [rdi+0B8h]
0x18007930a  jz      short loc_18007931D
0x18007930c  mov     rdx, rbp; struct IEnumItemIds *
0x18007930f  mov     rcx, rdi; this
0x180079312  call    ?PopulateMovedInItemIdCache@ChangeGroup@@AEAAJPEAUIEnumItemIds@@@Z; ChangeGroup::PopulateMovedInItemIdCache(IEnumItemIds *)
0x180079317  mov     ebx, eax
0x180079319  test    eax, eax
0x18007931b  jnz     short loc_180079373
0x18007931d  cmp     qword ptr [rdi+90h], 0
0x180079325  jnz     short loc_180079338
0x180079327  mov     rdx, rsi; struct ISyncKnowledge *
0x18007932a  mov     rcx, rdi; this
0x18007932d  call    ?CalculateMWKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::CalculateMWKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(ISyncKnowledge *)
0x180079332  mov     ebx, eax
0x180079334  test    eax, eax
0x180079336  jnz     short loc_180079373
0x180079338  cmp     qword ptr [rdi+38h], 0
0x18007933d  jnz     short loc_180079350
0x18007933f  mov     rdx, rsi; struct ISyncKnowledge *
0x180079342  mov     rcx, rdi; this
0x180079345  call    ?SetDestinationKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetDestinationKnowledgeCookie(ISyncKnowledge *)
0x18007934a  mov     ebx, eax
0x18007934c  test    eax, eax
0x18007934e  jnz     short loc_180079373
0x180079350  mov     rcx, [rdi+90h]
0x180079357  mov     [r15], rcx
0x18007935a  mov     rax, [rcx]
0x18007935d  mov     rax, [rax+8]
0x180079361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079366  mov     eax, [rdi+30h]
0x180079369  mov     [r14], eax
0x18007936c  jmp     short loc_180079373
0x18007936e  mov     ebx, 80004003h
0x180079373  mov     eax, ebx
0x180079375  add     rsp, 28h
0x180079379  pop     r15
0x18007937b  pop     r14
0x18007937d  pop     rdi
0x18007937e  pop     rsi
0x18007937f  pop     rbp
0x180079380  pop     rbx
0x180079381  retn
```
