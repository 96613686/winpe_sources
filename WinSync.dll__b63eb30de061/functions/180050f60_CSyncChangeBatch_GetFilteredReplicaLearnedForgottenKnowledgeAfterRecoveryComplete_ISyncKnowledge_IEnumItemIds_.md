# CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)

- ea: `0x180050f60`
- end: `0x180051055`
- name: `?GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z`
- size: `245`
- prototype: `__int64 __fastcall(CSyncChangeBatch *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005022c`
- `0x180050f60`

## string_xrefs

- `0x180050f9a`: `CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`
- `0x18005102c`: `CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeBatch *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        struct ISyncKnowledge **a4)
{
  PVOID *v8; // rcx
  unsigned int BatchLearnedKnowledgeAfterRecoveryComplete; // eax
  unsigned int v10; // ebx

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      126,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a4 )
  {
    if ( *((_DWORD *)this + 39) && !*((_QWORD *)this + 7) && *((_DWORD *)this + 41) == 1 && *((_QWORD *)this + 24) )
    {
      BatchLearnedKnowledgeAfterRecoveryComplete = CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(
                                                     (__int64)this - 56,
                                                     2,
                                                     a2,
                                                     (__int64)a3,
                                                     0,
                                                     a4);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      v10 = BatchLearnedKnowledgeAfterRecoveryComplete;
    }
    else
    {
      v10 = -2147217407;
    }
  }
  else
  {
    v10 = -2147467261;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      127,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete",
      v10);
  return v10;
}

```

## disassembly

```asm
0x180050f60  push    rbx
0x180050f62  push    rbp
0x180050f63  push    rsi
0x180050f64  push    rdi
0x180050f65  push    r14
0x180050f67  sub     rsp, 30h
0x180050f6b  mov     rdi, r9
0x180050f6e  mov     rbp, r8
0x180050f71  mov     rsi, rdx
0x180050f74  mov     rbx, rcx
0x180050f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f7e  lea     r14, WPP_GLOBAL_Control
0x180050f85  cmp     rcx, r14
0x180050f88  jz      short loc_180050FB9
0x180050f8a  test    byte ptr [rcx+1Ch], 10h
0x180050f8e  jz      short loc_180050FB9
0x180050f90  cmp     byte ptr [rcx+19h], 5
0x180050f94  jb      short loc_180050FB9
0x180050f96  mov     rcx, [rcx+10h]
0x180050f9a  lea     r9, aCsyncchangebat_44; "CSyncChangeBatch::GetFilteredReplicaLea"...
0x180050fa1  mov     edx, 7Eh ; '~'
0x180050fa6  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x180050fad  call    WPP_SF_s
0x180050fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180050fb9  xor     eax, eax
0x180050fbb  test    rsi, rsi
0x180050fbe  jz      short loc_180051012
0x180050fc0  test    rdi, rdi
0x180050fc3  jz      short loc_180051012
0x180050fc5  cmp     [rbx+9Ch], eax
0x180050fcb  jz      short loc_18005100B
0x180050fcd  cmp     [rbx+38h], rax
0x180050fd1  jnz     short loc_18005100B
0x180050fd3  cmp     dword ptr [rbx+0A4h], 1
0x180050fda  jnz     short loc_18005100B
0x180050fdc  cmp     [rbx+0C0h], rax
0x180050fe3  jz      short loc_18005100B
0x180050fe5  lea     rcx, [rbx-38h]
0x180050fe9  mov     [rsp+58h+var_30], rdi
0x180050fee  mov     r9, rbp
0x180050ff1  mov     [rsp+58h+var_38], eax
0x180050ff5  mov     r8, rsi
0x180050ff8  lea     edx, [rax+2]
0x180050ffb  call    ?GetBatchLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@AEAAJW4LK_AFTER_RECOVERY_TYPE@@PEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU3@@Z; CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(LK_AFTER_RECOVERY_TYPE,ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)
0x180051000  mov     rcx, cs:WPP_GLOBAL_Control
0x180051007  mov     ebx, eax
0x180051009  jmp     short loc_180051017
0x18005100b  mov     ebx, 80041001h
0x180051010  jmp     short loc_180051017
0x180051012  mov     ebx, 80004003h
0x180051017  cmp     rcx, r14
0x18005101a  jz      short loc_180051048
0x18005101c  test    byte ptr [rcx+1Ch], 10h
0x180051020  jz      short loc_180051048
0x180051022  cmp     byte ptr [rcx+19h], 5
0x180051026  jb      short loc_180051048
0x180051028  mov     rcx, [rcx+10h]
0x18005102c  lea     r9, aCsyncchangebat_44; "CSyncChangeBatch::GetFilteredReplicaLea"...
0x180051033  mov     edx, 7Fh
0x180051038  mov     [rsp+58h+var_38], ebx
0x18005103c  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x180051043  call    WPP_SF_sD
0x180051048  mov     eax, ebx
0x18005104a  add     rsp, 30h
0x18005104e  pop     r14
0x180051050  pop     rdi
0x180051051  pop     rsi
0x180051052  pop     rbp
0x180051053  pop     rbx
0x180051054  retn
```
