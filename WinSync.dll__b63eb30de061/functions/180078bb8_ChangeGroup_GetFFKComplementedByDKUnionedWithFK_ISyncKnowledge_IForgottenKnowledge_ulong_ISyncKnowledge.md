# ChangeGroup::GetFFKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ulong,ISyncKnowledge * *)

- ea: `0x180078bb8`
- end: `0x180078cec`
- name: `?GetFFKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@KPEAPEAU2@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ChangeGroup *this, struct ISyncKnowledge *, struct IForgottenKnowledge *, unsigned int, struct ISyncKnowledge **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005022c`
- `0x180058560`

## callees

- `0x180077fe4`
- `0x180078bb8`
- `0x180079770`
- `0x180079878`
- `0x180079928`
- `0x1800799cc`
- `0x180079da0`
- `0x18007a03c`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::GetFFKComplementedByDKUnionedWithFK(
        ChangeGroup *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5)
{
  unsigned int v8; // ebx
  __int64 v9; // r15
  unsigned int IsDestinationKnowledgeSpecificCacheValid; // eax
  unsigned int IsSourceForgottenKnowledgeSpecificCacheValid; // eax
  struct ISyncKnowledge *v12; // rcx

  if ( !a2 || !a3 || !a5 )
    return (unsigned int)-2147467261;
  if ( a4 >= *((_DWORD *)this + 20) )
    return (unsigned int)-2147024809;
  v9 = a4;
  if ( !*(_QWORD *)(*((_QWORD *)this + 11) + 8LL * a4) )
    return (unsigned int)-2147217367;
  IsDestinationKnowledgeSpecificCacheValid = ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(this, a2, 1);
  v8 = IsDestinationKnowledgeSpecificCacheValid;
  if ( IsDestinationKnowledgeSpecificCacheValid == 1 )
  {
    ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(this);
  }
  else
  {
    if ( IsDestinationKnowledgeSpecificCacheValid )
      return v8;
    IsSourceForgottenKnowledgeSpecificCacheValid = ChangeGroup::IsSourceForgottenKnowledgeSpecificCacheValid(this, a3);
    v8 = IsSourceForgottenKnowledgeSpecificCacheValid;
    if ( IsSourceForgottenKnowledgeSpecificCacheValid != 1 )
    {
      if ( IsSourceForgottenKnowledgeSpecificCacheValid )
        return v8;
      goto LABEL_14;
    }
  }
  v8 = 0;
  ChangeGroup::InvalidateSourceForgottenKnowledgeSpecificCache(this);
LABEL_14:
  if ( (*((_QWORD *)this + 21) || (v8 = ChangeGroup::CalculateFFKComplementedByDKUnionedWithFKImpl(this, a2, a3)) == 0)
    && (*((_QWORD *)this + 7) || (v8 = ChangeGroup::SetDestinationKnowledgeCookie(this, a2)) == 0)
    && (*((_QWORD *)this + 22)
     || (v8 = ChangeGroup::SetSourceForgottenKnowledgeCookie(this, (struct ISyncKnowledge *)a3)) == 0) )
  {
    v12 = *(struct ISyncKnowledge **)(*((_QWORD *)this + 21) + 8 * v9);
    *a5 = v12;
    if ( v12 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v12->lpVtbl->AddRef)(v12);
    else
      return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x180078bb8  push    rbx
0x180078bba  push    rbp
0x180078bbb  push    rsi
0x180078bbc  push    rdi
0x180078bbd  push    r14
0x180078bbf  push    r15
0x180078bc1  sub     rsp, 28h
0x180078bc5  mov     rsi, r8
0x180078bc8  mov     rbp, rdx
0x180078bcb  mov     rdi, rcx
0x180078bce  test    rdx, rdx
0x180078bd1  jz      loc_180078CD8
0x180078bd7  test    r8, r8
0x180078bda  jz      loc_180078CD8
0x180078be0  mov     r14, [rsp+58h+arg_20]
0x180078be8  test    r14, r14
0x180078beb  jz      loc_180078CD8
0x180078bf1  cmp     r9d, [rcx+50h]
0x180078bf5  jb      short loc_180078C01
0x180078bf7  mov     ebx, 80070057h
0x180078bfc  jmp     loc_180078CDD
0x180078c01  mov     rax, [rcx+58h]
0x180078c05  mov     r15d, r9d
0x180078c08  cmp     qword ptr [rax+r15*8], 0
0x180078c0d  jnz     short loc_180078C19
0x180078c0f  mov     ebx, 80041029h
0x180078c14  jmp     loc_180078CDD
0x180078c19  mov     r8d, 1; int
0x180078c1f  call    ?IsDestinationKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUISyncKnowledge@@H@Z; ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(ISyncKnowledge *,int)
0x180078c24  mov     ebx, eax
0x180078c26  cmp     eax, 1
0x180078c29  jnz     short loc_180078C35
0x180078c2b  mov     rcx, rdi; this
0x180078c2e  call    ?InvalidateDestinationKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(void)
0x180078c33  jmp     short loc_180078C4F
0x180078c35  test    eax, eax
0x180078c37  jnz     loc_180078CDD
0x180078c3d  mov     rdx, rsi; struct IForgottenKnowledge *
0x180078c40  mov     rcx, rdi; this
0x180078c43  call    ?IsSourceForgottenKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUIForgottenKnowledge@@@Z; ChangeGroup::IsSourceForgottenKnowledgeSpecificCacheValid(IForgottenKnowledge *)
0x180078c48  mov     ebx, eax
0x180078c4a  cmp     eax, 1
0x180078c4d  jnz     short loc_180078C5B
0x180078c4f  xor     ebx, ebx
0x180078c51  mov     rcx, rdi; this
0x180078c54  call    ?InvalidateSourceForgottenKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateSourceForgottenKnowledgeSpecificCache(void)
0x180078c59  jmp     short loc_180078C5F
0x180078c5b  test    eax, eax
0x180078c5d  jnz     short loc_180078CDD
0x180078c5f  cmp     qword ptr [rdi+0A8h], 0
0x180078c67  jnz     short loc_180078C7D
0x180078c69  mov     r8, rsi; struct IForgottenKnowledge *
0x180078c6c  mov     rdx, rbp; struct ISyncKnowledge *
0x180078c6f  mov     rcx, rdi; this
0x180078c72  call    ?CalculateFFKComplementedByDKUnionedWithFKImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@@Z; ChangeGroup::CalculateFFKComplementedByDKUnionedWithFKImpl(ISyncKnowledge *,IForgottenKnowledge *)
0x180078c77  mov     ebx, eax
0x180078c79  test    eax, eax
0x180078c7b  jnz     short loc_180078CDD
0x180078c7d  cmp     qword ptr [rdi+38h], 0
0x180078c82  jnz     short loc_180078C95
0x180078c84  mov     rdx, rbp; struct ISyncKnowledge *
0x180078c87  mov     rcx, rdi; this
0x180078c8a  call    ?SetDestinationKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetDestinationKnowledgeCookie(ISyncKnowledge *)
0x180078c8f  mov     ebx, eax
0x180078c91  test    eax, eax
0x180078c93  jnz     short loc_180078CDD
0x180078c95  cmp     qword ptr [rdi+0B0h], 0
0x180078c9d  jnz     short loc_180078CB0
0x180078c9f  mov     rdx, rsi; struct ISyncKnowledge *
0x180078ca2  mov     rcx, rdi; this
0x180078ca5  call    ?SetSourceForgottenKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetSourceForgottenKnowledgeCookie(ISyncKnowledge *)
0x180078caa  mov     ebx, eax
0x180078cac  test    eax, eax
0x180078cae  jnz     short loc_180078CDD
0x180078cb0  mov     rax, [rdi+0A8h]
0x180078cb7  mov     rcx, [rax+r15*8]
0x180078cbb  mov     [r14], rcx
0x180078cbe  test    rcx, rcx
0x180078cc1  jz      short loc_180078CD1
0x180078cc3  mov     rax, [rcx]
0x180078cc6  mov     rax, [rax+8]
0x180078cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ccf  jmp     short loc_180078CDD
0x180078cd1  mov     ebx, 1
0x180078cd6  jmp     short loc_180078CDD
0x180078cd8  mov     ebx, 80004003h
0x180078cdd  mov     eax, ebx
0x180078cdf  add     rsp, 28h
0x180078ce3  pop     r15
0x180078ce5  pop     r14
0x180078ce7  pop     rdi
0x180078ce8  pop     rsi
0x180078ce9  pop     rbp
0x180078cea  pop     rbx
0x180078ceb  retn
```
