# ChangeGroup::GetFFKWithPrerequisiteComplementedByDKWithMoveinsExcluded(ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *,int *)

- ea: `0x180078df0`
- end: `0x180078f49`
- name: `?GetFFKWithPrerequisiteComplementedByDKWithMoveinsExcluded@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU2@PEAH@Z`
- size: `345`
- prototype: `__int64 __fastcall(ChangeGroup *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, unsigned int, struct ISyncKnowledge **, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180051190`
- `0x1800582c0`

## callees

- `0x180078174`
- `0x180078354`
- `0x180078df0`
- `0x180079770`
- `0x180079928`
- `0x180079a70`
- `0x180079da0`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::GetFFKWithPrerequisiteComplementedByDKWithMoveinsExcluded(
        ChangeGroup *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5,
        int *a6)
{
  __int64 v6; // rsi
  unsigned int v10; // ebx
  BOOL v11; // r8d
  unsigned int IsDestinationKnowledgeSpecificCacheValid; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  struct ISyncKnowledge *v15; // rcx

  v6 = a4;
  if ( !a2 || !a5 || !a6 )
    return (unsigned int)-2147467261;
  if ( a4 < *((_DWORD *)this + 20) )
  {
    if ( *(_QWORD *)(*((_QWORD *)this + 11) + 8LL * a4) )
    {
      v11 = a3 || *((_DWORD *)this + 13);
      IsDestinationKnowledgeSpecificCacheValid = ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(this, a2, v11);
      v10 = IsDestinationKnowledgeSpecificCacheValid;
      if ( IsDestinationKnowledgeSpecificCacheValid == 1 )
      {
        ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(this);
        v10 = 0;
      }
      else if ( IsDestinationKnowledgeSpecificCacheValid )
      {
        return v10;
      }
      if ( (a3 == *((struct IEnumItemIds **)this + 23) || (v10 = ChangeGroup::PopulateMovedInItemIdCache(this, a3)) == 0)
        && ((v13 = *((_QWORD *)this + 13)) != 0 && *(_QWORD *)(v13 + 8 * v6)
         || (v10 = ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDK(this, a2, v6)) == 0) )
      {
        v14 = *((_QWORD *)this + 14);
        if ( (v14 && *(_QWORD *)(v14 + 8 * v6)
           || (v10 = ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(this, a2, v6)) == 0)
          && (*((_QWORD *)this + 7) || (v10 = ChangeGroup::SetDestinationKnowledgeCookie(this, a2)) == 0) )
        {
          v15 = *(struct ISyncKnowledge **)(*((_QWORD *)this + 14) + 8 * v6);
          *a5 = v15;
          ((void (__fastcall *)(struct ISyncKnowledge *))v15->lpVtbl->AddRef)(v15);
          *a6 = *((_DWORD *)this + 12);
        }
      }
    }
    else
    {
      return (unsigned int)-2147217367;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x180078df0  push    rbx
0x180078df2  push    rbp
0x180078df3  push    rsi
0x180078df4  push    rdi
0x180078df5  push    r12
0x180078df7  push    r13
0x180078df9  push    r14
0x180078dfb  push    r15
0x180078dfd  sub     rsp, 28h
0x180078e01  mov     esi, r9d
0x180078e04  mov     r14, r8
0x180078e07  mov     rbp, rdx
0x180078e0a  mov     rdi, rcx
0x180078e0d  test    rdx, rdx
0x180078e10  jz      loc_180078F31
0x180078e16  mov     r12, [rsp+68h+arg_20]
0x180078e1e  test    r12, r12
0x180078e21  jz      loc_180078F31
0x180078e27  mov     r13, [rsp+68h+arg_28]
0x180078e2f  test    r13, r13
0x180078e32  jz      loc_180078F31
0x180078e38  cmp     esi, [rcx+50h]
0x180078e3b  jb      short loc_180078E47
0x180078e3d  mov     ebx, 80070057h
0x180078e42  jmp     loc_180078F36
0x180078e47  mov     rax, [rcx+58h]
0x180078e4b  cmp     qword ptr [rax+rsi*8], 0
0x180078e50  jnz     short loc_180078E5C
0x180078e52  mov     ebx, 80041029h
0x180078e57  jmp     loc_180078F36
0x180078e5c  test    r14, r14
0x180078e5f  jnz     short loc_180078E6C
0x180078e61  cmp     [rcx+34h], r14d
0x180078e65  jnz     short loc_180078E6C
0x180078e67  xor     r8d, r8d
0x180078e6a  jmp     short loc_180078E72
0x180078e6c  mov     r8d, 1; int
0x180078e72  call    ?IsDestinationKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUISyncKnowledge@@H@Z; ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(ISyncKnowledge *,int)
0x180078e77  mov     ebx, eax
0x180078e79  cmp     eax, 1
0x180078e7c  jnz     short loc_180078E8A
0x180078e7e  mov     rcx, rdi; this
0x180078e81  call    ?InvalidateDestinationKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(void)
0x180078e86  xor     ebx, ebx
0x180078e88  jmp     short loc_180078E92
0x180078e8a  test    eax, eax
0x180078e8c  jnz     loc_180078F36
0x180078e92  cmp     r14, [rdi+0B8h]
0x180078e99  jz      short loc_180078EB0
0x180078e9b  mov     rdx, r14; struct IEnumItemIds *
0x180078e9e  mov     rcx, rdi; this
0x180078ea1  call    ?PopulateMovedInItemIdCache@ChangeGroup@@AEAAJPEAUIEnumItemIds@@@Z; ChangeGroup::PopulateMovedInItemIdCache(IEnumItemIds *)
0x180078ea6  mov     ebx, eax
0x180078ea8  test    eax, eax
0x180078eaa  jnz     loc_180078F36
0x180078eb0  mov     rax, [rdi+68h]
0x180078eb4  test    rax, rax
0x180078eb7  jz      short loc_180078EC0
0x180078eb9  cmp     qword ptr [rax+rsi*8], 0
0x180078ebe  jnz     short loc_180078ED4
0x180078ec0  mov     r8d, esi; unsigned int
0x180078ec3  mov     rdx, rbp; struct ISyncKnowledge *
0x180078ec6  mov     rcx, rdi; this
0x180078ec9  call    ?CalculateFFKWithPrerequisiteComplementedByDK@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z; ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDK(ISyncKnowledge *,ulong)
0x180078ece  mov     ebx, eax
0x180078ed0  test    eax, eax
0x180078ed2  jnz     short loc_180078F36
0x180078ed4  mov     rax, [rdi+70h]
0x180078ed8  test    rax, rax
0x180078edb  jz      short loc_180078EE4
0x180078edd  cmp     qword ptr [rax+rsi*8], 0
0x180078ee2  jnz     short loc_180078EF8
0x180078ee4  mov     r8d, esi; unsigned int
0x180078ee7  mov     rdx, rbp; struct ISyncKnowledge *
0x180078eea  mov     rcx, rdi; this
0x180078eed  call    ?CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z; ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(ISyncKnowledge *,ulong)
0x180078ef2  mov     ebx, eax
0x180078ef4  test    eax, eax
0x180078ef6  jnz     short loc_180078F36
0x180078ef8  cmp     qword ptr [rdi+38h], 0
0x180078efd  jnz     short loc_180078F10
0x180078eff  mov     rdx, rbp; struct ISyncKnowledge *
0x180078f02  mov     rcx, rdi; this
0x180078f05  call    ?SetDestinationKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetDestinationKnowledgeCookie(ISyncKnowledge *)
0x180078f0a  mov     ebx, eax
0x180078f0c  test    eax, eax
0x180078f0e  jnz     short loc_180078F36
0x180078f10  mov     rax, [rdi+70h]
0x180078f14  mov     rcx, [rax+rsi*8]
0x180078f18  mov     [r12], rcx
0x180078f1c  mov     rax, [rcx]
0x180078f1f  mov     rax, [rax+8]
0x180078f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f28  mov     eax, [rdi+30h]
0x180078f2b  mov     [r13+0], eax
0x180078f2f  jmp     short loc_180078F36
0x180078f31  mov     ebx, 80004003h
0x180078f36  mov     eax, ebx
0x180078f38  add     rsp, 28h
0x180078f3c  pop     r15
0x180078f3e  pop     r14
0x180078f40  pop     r13
0x180078f42  pop     r12
0x180078f44  pop     rdi
0x180078f45  pop     rsi
0x180078f46  pop     rbp
0x180078f47  pop     rbx
0x180078f48  retn
```
