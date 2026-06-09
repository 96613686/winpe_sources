# CSyncChange::PostProcessKnowledgeForNewMoveIn(ISyncKnowledge *,ISyncKnowledge *)

- ea: `0x1800599ac`
- end: `0x180059aae`
- name: `?PostProcessKnowledgeForNewMoveIn@CSyncChange@@AEAAJPEAUISyncKnowledge@@0@Z`
- size: `258`
- prototype: `__int64 __fastcall(CSyncChange *__hidden this, struct ISyncKnowledge *, struct ISyncKnowledge *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180057700`
- `0x180057ac0`
- `0x1800582c0`

## callees

- `0x18001ae20`
- `0x180052630`
- `0x1800599ac`
- `0x180094010`

## string_xrefs

- `0x180059a80`: `CSyncChange::PostProcessKnowledgeForNewMoveIn`

## pseudocode

```c
__int64 __fastcall CSyncChange::PostProcessKnowledgeForNewMoveIn(
        CSyncChange *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge *a3)
{
  struct ISyncKnowledgeVtbl *lpVtbl; // rax
  __int64 v5; // rdx
  unsigned int v8; // ebx
  struct ISyncFilterInfo *v9; // r8
  struct ISyncKnowledge *v10; // rdx
  struct IdParameters *v11; // rcx
  struct ISyncKnowledge *v13; // [rsp+40h] [rbp+8h] BYREF
  struct ISyncKnowledge *v14; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v5 = *((_QWORD *)this + 15);
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64, struct ISyncKnowledge **))lpVtbl->ProjectOntoItem)(
         a2,
         v5,
         &v13);
  if ( !v8 )
  {
    v9 = (struct ISyncFilterInfo *)*((_QWORD *)this + 32);
    v10 = v13;
    if ( v9 )
    {
      v11 = (struct IdParameters *)*((_QWORD *)this + 33);
      v14 = 0;
      v8 = CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(v11, v13, v9, &v14);
      if ( v8 )
        goto LABEL_6;
      ((void (__fastcall *)(struct ISyncKnowledge *))v13->lpVtbl->Release)(v13);
      v10 = v14;
      v13 = v14;
    }
    v8 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, struct ISyncKnowledge *))a3->lpVtbl->Union)(a3, v10);
  }
LABEL_6:
  if ( v13 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v13->lpVtbl->Release)(v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::PostProcessKnowledgeForNewMoveIn",
      v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800599ac  mov     r11, rsp
0x1800599af  mov     [r11+18h], rbx
0x1800599b3  mov     [r11+20h], rsi
0x1800599b7  push    rdi
0x1800599b8  sub     rsp, 30h
0x1800599bc  mov     rax, [rdx]
0x1800599bf  mov     r9, rdx
0x1800599c2  mov     rdx, [rcx+78h]
0x1800599c6  mov     rsi, r8
0x1800599c9  mov     rdi, rcx
0x1800599cc  mov     qword ptr [r11+8], 0
0x1800599d4  lea     r8, [r11+8]
0x1800599d8  mov     rcx, r9
0x1800599db  mov     rax, [rax+70h]
0x1800599df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599e4  mov     ebx, eax
0x1800599e6  test    eax, eax
0x1800599e8  jnz     short loc_180059A47
0x1800599ea  mov     r8, [rdi+100h]; struct ISyncFilterInfo *
0x1800599f1  mov     rdx, [rsp+38h+arg_0]; struct ISyncKnowledge *
0x1800599f6  test    r8, r8
0x1800599f9  jz      short loc_180059A36
0x1800599fb  mov     rcx, [rdi+108h]; struct IdParameters *
0x180059a02  lea     r9, [rsp+38h+arg_8]; struct ISyncKnowledge **
0x180059a07  mov     [rsp+38h+arg_8], 0
0x180059a10  call    ?ProjectKnowledgeOntoColumnsIfRequired@CSyncChangeBatch@@SAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUISyncFilterInfo@@PEAPEAU3@@Z; CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(IdParameters *,ISyncKnowledge *,ISyncFilterInfo *,ISyncKnowledge * *)
0x180059a15  mov     ebx, eax
0x180059a17  test    eax, eax
0x180059a19  jnz     short loc_180059A47
0x180059a1b  mov     rcx, [rsp+38h+arg_0]
0x180059a20  mov     rax, [rcx]
0x180059a23  mov     rax, [rax+10h]
0x180059a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a2c  mov     rdx, [rsp+38h+arg_8]
0x180059a31  mov     [rsp+38h+arg_0], rdx
0x180059a36  mov     rax, [rsi]
0x180059a39  mov     rcx, rsi
0x180059a3c  mov     rax, [rax+68h]
0x180059a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a45  mov     ebx, eax
0x180059a47  mov     rcx, [rsp+38h+arg_0]
0x180059a4c  test    rcx, rcx
0x180059a4f  jz      short loc_180059A5D
0x180059a51  mov     rax, [rcx]
0x180059a54  mov     rax, [rax+10h]
0x180059a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a64  lea     rax, WPP_GLOBAL_Control
0x180059a6b  cmp     rcx, rax
0x180059a6e  jz      short loc_180059A9C
0x180059a70  test    byte ptr [rcx+1Ch], 20h
0x180059a74  jz      short loc_180059A9C
0x180059a76  cmp     byte ptr [rcx+19h], 5
0x180059a7a  jb      short loc_180059A9C
0x180059a7c  mov     rcx, [rcx+10h]
0x180059a80  lea     r9, aCsyncchangePos; "CSyncChange::PostProcessKnowledgeForNew"...
0x180059a87  mov     edx, 65h ; 'e'
0x180059a8c  mov     [rsp+38h+var_18], ebx
0x180059a90  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180059a97  call    WPP_SF_sD
0x180059a9c  mov     rsi, [rsp+38h+arg_18]
0x180059aa1  mov     eax, ebx
0x180059aa3  mov     rbx, [rsp+38h+arg_10]
0x180059aa8  add     rsp, 30h
0x180059aac  pop     rdi
0x180059aad  retn
```
