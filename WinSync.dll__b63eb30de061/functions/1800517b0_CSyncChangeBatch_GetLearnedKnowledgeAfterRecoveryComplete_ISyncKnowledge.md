# CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge * *)

- ea: `0x1800517b0`
- end: `0x1800518a0`
- name: `?GetLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@UEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CSyncChangeBatch *__hidden this, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005022c`
- `0x1800517b0`

## string_xrefs

- `0x1800517e8`: `CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete`
- `0x180051872`: `CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete(
        CSyncChangeBatch *this,
        struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  unsigned int BatchLearnedKnowledgeAfterRecoveryComplete; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 45) && !*((_QWORD *)this + 10) && *((_DWORD *)this + 47) == 1 && *((_QWORD *)this + 27) )
  {
    if ( a2 )
    {
      BatchLearnedKnowledgeAfterRecoveryComplete = CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(
                                                     (__int64)this - 32,
                                                     0,
                                                     0,
                                                     0,
                                                     0,
                                                     a2);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      v5 = BatchLearnedKnowledgeAfterRecoveryComplete;
    }
    else
    {
      v5 = -2147467261;
    }
  }
  else
  {
    v5 = -2147217407;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      77,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::GetLearnedKnowledgeAfterRecoveryComplete",
      v5);
  return v5;
}

```

## disassembly

```asm
0x1800517b0  mov     [rsp+arg_0], rbx
0x1800517b5  mov     [rsp+arg_8], rsi
0x1800517ba  push    rdi
0x1800517bb  sub     rsp, 30h
0x1800517bf  mov     rdi, rdx
0x1800517c2  mov     rbx, rcx
0x1800517c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800517cc  lea     rsi, WPP_GLOBAL_Control
0x1800517d3  cmp     rcx, rsi
0x1800517d6  jz      short loc_180051807
0x1800517d8  test    byte ptr [rcx+1Ch], 10h
0x1800517dc  jz      short loc_180051807
0x1800517de  cmp     byte ptr [rcx+19h], 5
0x1800517e2  jb      short loc_180051807
0x1800517e4  mov     rcx, [rcx+10h]
0x1800517e8  lea     r9, aCsyncchangebat_7; "CSyncChangeBatch::GetLearnedKnowledgeAf"...
0x1800517ef  mov     edx, 4Ch ; 'L'
0x1800517f4  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x1800517fb  call    WPP_SF_s
0x180051800  mov     rcx, cs:WPP_GLOBAL_Control
0x180051807  xor     edx, edx
0x180051809  cmp     [rbx+0B4h], edx
0x18005180f  jz      short loc_180051858
0x180051811  cmp     [rbx+50h], rdx
0x180051815  jnz     short loc_180051858
0x180051817  cmp     dword ptr [rbx+0BCh], 1
0x18005181e  jnz     short loc_180051858
0x180051820  cmp     [rbx+0D8h], rdx
0x180051827  jz      short loc_180051858
0x180051829  test    rdi, rdi
0x18005182c  jnz     short loc_180051835
0x18005182e  mov     ebx, 80004003h
0x180051833  jmp     short loc_18005185D
0x180051835  mov     [rsp+38h+var_10], rdi
0x18005183a  lea     rcx, [rbx-20h]
0x18005183e  xor     r9d, r9d
0x180051841  mov     [rsp+38h+var_18], edx
0x180051845  xor     r8d, r8d
0x180051848  call    ?GetBatchLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@AEAAJW4LK_AFTER_RECOVERY_TYPE@@PEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU3@@Z; CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(LK_AFTER_RECOVERY_TYPE,ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)
0x18005184d  mov     rcx, cs:WPP_GLOBAL_Control
0x180051854  mov     ebx, eax
0x180051856  jmp     short loc_18005185D
0x180051858  mov     ebx, 80041001h
0x18005185d  cmp     rcx, rsi
0x180051860  jz      short loc_18005188E
0x180051862  test    byte ptr [rcx+1Ch], 10h
0x180051866  jz      short loc_18005188E
0x180051868  cmp     byte ptr [rcx+19h], 5
0x18005186c  jb      short loc_18005188E
0x18005186e  mov     rcx, [rcx+10h]
0x180051872  lea     r9, aCsyncchangebat_7; "CSyncChangeBatch::GetLearnedKnowledgeAf"...
0x180051879  mov     edx, 4Dh ; 'M'
0x18005187e  mov     [rsp+38h+var_18], ebx
0x180051882  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x180051889  call    WPP_SF_sD
0x18005188e  mov     rsi, [rsp+38h+arg_8]
0x180051893  mov     eax, ebx
0x180051895  mov     rbx, [rsp+38h+arg_0]
0x18005189a  add     rsp, 30h
0x18005189e  pop     rdi
0x18005189f  retn
```
