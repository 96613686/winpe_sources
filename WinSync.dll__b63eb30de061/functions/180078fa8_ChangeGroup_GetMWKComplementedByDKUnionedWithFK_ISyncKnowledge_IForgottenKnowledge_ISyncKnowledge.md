# ChangeGroup::GetMWKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge * *)

- ea: `0x180078fa8`
- end: `0x1800790ee`
- name: `?GetMWKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAU2@@Z`
- size: `326`
- prototype: `__int64 __fastcall(ChangeGroup *__hidden this, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncKnowledge **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005022c`
- `0x180057920`

## callees

- `0x180078570`
- `0x180078fa8`
- `0x180079770`
- `0x180079878`
- `0x180079928`
- `0x1800799cc`
- `0x180079da0`
- `0x18007a03c`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::GetMWKComplementedByDKUnionedWithFK(
        ChangeGroup *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge *a3,
        struct ISyncKnowledge **a4)
{
  unsigned int v8; // ebx
  unsigned int IsDestinationKnowledgeSpecificCacheValid; // eax
  unsigned int IsSourceForgottenKnowledgeSpecificCacheValid; // eax
  _QWORD *v11; // rsi
  __int64 v12; // rcx

  if ( !a2 || !a3 || !a4 )
    return (unsigned int)-2147467261;
  if ( !*((_QWORD *)this + 5) )
    return (unsigned int)-2147217399;
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
      goto LABEL_12;
    }
  }
  v8 = 0;
  ChangeGroup::InvalidateSourceForgottenKnowledgeSpecificCache(this);
LABEL_12:
  v11 = (_QWORD *)((char *)this + 160);
  if ( *((_QWORD *)this + 20) )
    goto LABEL_27;
  if ( *((_QWORD *)this + 16) || (v8 = ChangeGroup::CalculateMWKComplementedByDKImpl(this, a2)) == 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 80LL))(
           *((_QWORD *)this + 16),
           (char *)this + 160);
    if ( !v8 )
      v8 = (*(__int64 (__fastcall **)(_QWORD, struct IForgottenKnowledge *))(*(_QWORD *)*v11 + 104LL))(*v11, a3);
  }
  if ( !v8 )
  {
LABEL_27:
    if ( (*((_QWORD *)this + 7) || (v8 = ChangeGroup::SetDestinationKnowledgeCookie(this, a2)) == 0)
      && (*((_QWORD *)this + 22)
       || (v8 = ChangeGroup::SetSourceForgottenKnowledgeCookie(this, (struct ISyncKnowledge *)a3)) == 0) )
    {
      v12 = *v11;
      *a4 = (struct ISyncKnowledge *)*v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180078fa8  push    rbx
0x180078faa  push    rbp
0x180078fab  push    rsi
0x180078fac  push    rdi
0x180078fad  push    r14
0x180078faf  push    r15
0x180078fb1  sub     rsp, 28h
0x180078fb5  mov     r15, r9
0x180078fb8  mov     rbp, r8
0x180078fbb  mov     r14, rdx
0x180078fbe  mov     rdi, rcx
0x180078fc1  test    rdx, rdx
0x180078fc4  jz      loc_1800790DA
0x180078fca  test    r8, r8
0x180078fcd  jz      loc_1800790DA
0x180078fd3  test    r9, r9
0x180078fd6  jz      loc_1800790DA
0x180078fdc  cmp     qword ptr [rcx+28h], 0
0x180078fe1  jnz     short loc_180078FED
0x180078fe3  mov     ebx, 80041009h
0x180078fe8  jmp     loc_1800790DF
0x180078fed  mov     r8d, 1; int
0x180078ff3  call    ?IsDestinationKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUISyncKnowledge@@H@Z; ChangeGroup::IsDestinationKnowledgeSpecificCacheValid(ISyncKnowledge *,int)
0x180078ff8  mov     ebx, eax
0x180078ffa  cmp     eax, 1
0x180078ffd  jnz     short loc_180079009
0x180078fff  mov     rcx, rdi; this
0x180079002  call    ?InvalidateDestinationKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateDestinationKnowledgeSpecificCache(void)
0x180079007  jmp     short loc_180079023
0x180079009  test    eax, eax
0x18007900b  jnz     loc_1800790DF
0x180079011  mov     rdx, rbp; struct IForgottenKnowledge *
0x180079014  mov     rcx, rdi; this
0x180079017  call    ?IsSourceForgottenKnowledgeSpecificCacheValid@ChangeGroup@@AEAAJPEAUIForgottenKnowledge@@@Z; ChangeGroup::IsSourceForgottenKnowledgeSpecificCacheValid(IForgottenKnowledge *)
0x18007901c  mov     ebx, eax
0x18007901e  cmp     eax, 1
0x180079021  jnz     short loc_18007902F
0x180079023  xor     ebx, ebx
0x180079025  mov     rcx, rdi; this
0x180079028  call    ?InvalidateSourceForgottenKnowledgeSpecificCache@ChangeGroup@@AEAAXXZ; ChangeGroup::InvalidateSourceForgottenKnowledgeSpecificCache(void)
0x18007902d  jmp     short loc_180079037
0x18007902f  test    eax, eax
0x180079031  jnz     loc_1800790DF
0x180079037  lea     rsi, [rdi+0A0h]
0x18007903e  cmp     qword ptr [rsi], 0
0x180079042  jnz     short loc_180079093
0x180079044  cmp     qword ptr [rdi+80h], 0
0x18007904c  jnz     short loc_18007905F
0x18007904e  mov     rdx, r14; struct ISyncKnowledge *
0x180079051  mov     rcx, rdi; this
0x180079054  call    ?CalculateMWKComplementedByDKImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::CalculateMWKComplementedByDKImpl(ISyncKnowledge *)
0x180079059  mov     ebx, eax
0x18007905b  test    eax, eax
0x18007905d  jnz     short loc_18007908F
0x18007905f  mov     rcx, [rdi+80h]
0x180079066  mov     rdx, rsi
0x180079069  mov     rax, [rcx]
0x18007906c  mov     rax, [rax+50h]
0x180079070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079075  mov     ebx, eax
0x180079077  test    eax, eax
0x180079079  jnz     short loc_18007908F
0x18007907b  mov     rcx, [rsi]
0x18007907e  mov     rdx, rbp
0x180079081  mov     rax, [rcx]
0x180079084  mov     rax, [rax+68h]
0x180079088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007908d  mov     ebx, eax
0x18007908f  test    ebx, ebx
0x180079091  jnz     short loc_1800790DF
0x180079093  cmp     qword ptr [rdi+38h], 0
0x180079098  jnz     short loc_1800790AB
0x18007909a  mov     rdx, r14; struct ISyncKnowledge *
0x18007909d  mov     rcx, rdi; this
0x1800790a0  call    ?SetDestinationKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetDestinationKnowledgeCookie(ISyncKnowledge *)
0x1800790a5  mov     ebx, eax
0x1800790a7  test    eax, eax
0x1800790a9  jnz     short loc_1800790DF
0x1800790ab  cmp     qword ptr [rdi+0B0h], 0
0x1800790b3  jnz     short loc_1800790C6
0x1800790b5  mov     rdx, rbp; struct ISyncKnowledge *
0x1800790b8  mov     rcx, rdi; this
0x1800790bb  call    ?SetSourceForgottenKnowledgeCookie@ChangeGroup@@AEAAJPEAUISyncKnowledge@@@Z; ChangeGroup::SetSourceForgottenKnowledgeCookie(ISyncKnowledge *)
0x1800790c0  mov     ebx, eax
0x1800790c2  test    eax, eax
0x1800790c4  jnz     short loc_1800790DF
0x1800790c6  mov     rcx, [rsi]
0x1800790c9  mov     [r15], rcx
0x1800790cc  mov     rax, [rcx]
0x1800790cf  mov     rax, [rax+8]
0x1800790d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790d8  jmp     short loc_1800790DF
0x1800790da  mov     ebx, 80004003h
0x1800790df  mov     eax, ebx
0x1800790e1  add     rsp, 28h
0x1800790e5  pop     r15
0x1800790e7  pop     r14
0x1800790e9  pop     rdi
0x1800790ea  pop     rsi
0x1800790eb  pop     rbp
0x1800790ec  pop     rbx
0x1800790ed  retn
```
