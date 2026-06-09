# CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge * *)

- ea: `0x180058970`
- end: `0x180058a9f`
- name: `?GetLearnedKnowledgeAfterRecoveryComplete@CSyncChange@@UEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CSyncChange *this, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180056f84`
- `0x180058970`
- `0x180079388`
- `0x180094010`

## string_xrefs

- `0x1800589ab`: `CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete`
- `0x180058a6e`: `CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete(CSyncChange *this, struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  unsigned int MadeWithKnowledge; // edi
  CSyncChange *v6; // rbp
  __int64 v7; // rcx
  struct ISyncKnowledge *v8; // rbx
  struct ISyncKnowledge *v10; // [rsp+58h] [rbp+10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  MadeWithKnowledge = -2147467261;
  if ( a2 )
  {
    v6 = (CSyncChange *)((char *)this - 16);
    MadeWithKnowledge = -2147217407;
    if ( !*((_DWORD *)this + 53) )
    {
      if ( *((_DWORD *)this + 33) )
      {
        v7 = *((_QWORD *)this + 21);
        if ( v7 )
        {
          MadeWithKnowledge = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v7 + 80LL))(
                                v7,
                                a2);
        }
        else
        {
          v10 = 0;
          MadeWithKnowledge = ChangeGroup::GetMadeWithKnowledge(*((ChangeGroup **)this + 18), &v10);
          if ( !MadeWithKnowledge )
          {
            v8 = v10;
            MadeWithKnowledge = CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(v6, v10, a2);
            ((void (__fastcall *)(struct ISyncKnowledge *))v8->lpVtbl->Release)(v8);
          }
        }
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      38,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::GetLearnedKnowledgeAfterRecoveryComplete",
      MadeWithKnowledge);
  return MadeWithKnowledge;
}

```

## disassembly

```asm
0x180058970  mov     [rsp+arg_0], rbx
0x180058975  mov     [rsp+arg_10], rbp
0x18005897a  push    rsi
0x18005897b  push    rdi
0x18005897c  push    r15
0x18005897e  sub     rsp, 30h
0x180058982  mov     rsi, rdx
0x180058985  mov     rbx, rcx
0x180058988  mov     rcx, cs:WPP_GLOBAL_Control
0x18005898f  lea     r15, WPP_GLOBAL_Control
0x180058996  cmp     rcx, r15
0x180058999  jz      short loc_1800589CA
0x18005899b  test    byte ptr [rcx+1Ch], 20h
0x18005899f  jz      short loc_1800589CA
0x1800589a1  cmp     byte ptr [rcx+19h], 5
0x1800589a5  jb      short loc_1800589CA
0x1800589a7  mov     rcx, [rcx+10h]
0x1800589ab  lea     r9, aCsyncchangeGet_6; "CSyncChange::GetLearnedKnowledgeAfterRe"...
0x1800589b2  mov     edx, 25h ; '%'
0x1800589b7  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x1800589be  call    WPP_SF_s
0x1800589c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800589ca  mov     edi, 80004003h
0x1800589cf  test    rsi, rsi
0x1800589d2  jz      loc_180058A59
0x1800589d8  lea     rbp, [rbx-10h]
0x1800589dc  mov     edi, 80041001h
0x1800589e1  cmp     dword ptr [rbp+0E4h], 0
0x1800589e8  jnz     short loc_180058A59
0x1800589ea  cmp     dword ptr [rbx+84h], 0
0x1800589f1  jz      short loc_180058A59
0x1800589f3  mov     rcx, [rbx+0A8h]
0x1800589fa  test    rcx, rcx
0x1800589fd  jnz     short loc_180058A41
0x1800589ff  mov     [rsp+48h+arg_8], rcx
0x180058a04  lea     rdx, [rsp+48h+arg_8]; struct ISyncKnowledge **
0x180058a09  mov     rcx, [rbx+90h]; this
0x180058a10  call    ?GetMadeWithKnowledge@ChangeGroup@@QEAAJPEAPEAUISyncKnowledge@@@Z; ChangeGroup::GetMadeWithKnowledge(ISyncKnowledge * *)
0x180058a15  mov     edi, eax
0x180058a17  test    eax, eax
0x180058a19  jnz     short loc_180058A52
0x180058a1b  mov     rbx, [rsp+48h+arg_8]
0x180058a20  mov     r8, rsi; struct ISyncKnowledge **
0x180058a23  mov     rdx, rbx; struct ISyncKnowledge *
0x180058a26  mov     rcx, rbp; this
0x180058a29  call    ?GetChangeLearnedKnowledgeAfterRecoveryComplete@CSyncChange@@AEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge *,ISyncKnowledge * *)
0x180058a2e  mov     edi, eax
0x180058a30  mov     rcx, rbx
0x180058a33  mov     rax, [rbx]
0x180058a36  mov     rax, [rax+10h]
0x180058a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a3f  jmp     short loc_180058A52
0x180058a41  mov     rax, [rcx]
0x180058a44  mov     rdx, rsi
0x180058a47  mov     rax, [rax+50h]
0x180058a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a50  mov     edi, eax
0x180058a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180058a59  cmp     rcx, r15
0x180058a5c  jz      short loc_180058A8A
0x180058a5e  test    byte ptr [rcx+1Ch], 20h
0x180058a62  jz      short loc_180058A8A
0x180058a64  cmp     byte ptr [rcx+19h], 5
0x180058a68  jb      short loc_180058A8A
0x180058a6a  mov     rcx, [rcx+10h]
0x180058a6e  lea     r9, aCsyncchangeGet_6; "CSyncChange::GetLearnedKnowledgeAfterRe"...
0x180058a75  mov     edx, 26h ; '&'
0x180058a7a  mov     [rsp+48h+var_28], edi
0x180058a7e  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180058a85  call    WPP_SF_sD
0x180058a8a  mov     rbx, [rsp+48h+arg_0]
0x180058a8f  mov     eax, edi
0x180058a91  mov     rbp, [rsp+48h+arg_10]
0x180058a96  add     rsp, 30h
0x180058a9a  pop     r15
0x180058a9c  pop     rdi
0x180058a9d  pop     rsi
0x180058a9e  retn
```
