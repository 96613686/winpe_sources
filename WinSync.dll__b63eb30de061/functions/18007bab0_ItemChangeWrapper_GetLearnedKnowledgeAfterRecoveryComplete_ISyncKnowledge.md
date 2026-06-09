# ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge * *)

- ea: `0x18007bab0`
- end: `0x18007bb98`
- name: `?GetLearnedKnowledgeAfterRecoveryComplete@ItemChangeWrapper@@UEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(ItemChangeWrapper *__hidden this, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18007bab0`
- `0x180094010`

## string_xrefs

- `0x18007bae8`: `ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete`
- `0x18007bb6a`: `ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete(
        ItemChangeWrapper *this,
        struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  unsigned int v7; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      "ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 10);
    if ( v6 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge **))(*(_QWORD *)v6 + 24LL))(
             *((_QWORD *)this + 10),
             a2);
    }
    else
    {
      if ( !*((_DWORD *)this + 48) )
      {
        v5 = -2147217379;
        goto LABEL_13;
      }
      v7 = (*(__int64 (__fastcall **)(char *, struct ISyncKnowledge **))(*((_QWORD *)this - 2) + 88LL))(
             (char *)this - 16,
             a2);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v7;
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_13:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      53,
      (unsigned int)WPP_c46487f44df63404f221e65d0a11538d_Traceguids,
      (unsigned int)"ItemChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18007bab0  mov     [rsp+arg_0], rbx
0x18007bab5  mov     [rsp+arg_8], rsi
0x18007baba  push    rdi
0x18007babb  sub     rsp, 30h
0x18007babf  mov     rdi, rdx
0x18007bac2  mov     rbx, rcx
0x18007bac5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bacc  lea     rsi, WPP_GLOBAL_Control
0x18007bad3  cmp     rcx, rsi
0x18007bad6  jz      short loc_18007BB07
0x18007bad8  test    byte ptr [rcx+1Ch], 80h
0x18007badc  jz      short loc_18007BB07
0x18007bade  cmp     byte ptr [rcx+19h], 5
0x18007bae2  jb      short loc_18007BB07
0x18007bae4  mov     rcx, [rcx+10h]
0x18007bae8  lea     r9, aItemchangewrap_9; "ItemChangeWrapper::GetLearnedKnowledgeA"...
0x18007baef  mov     edx, 34h ; '4'
0x18007baf4  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007bafb  call    WPP_SF_s
0x18007bb00  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb07  test    rdi, rdi
0x18007bb0a  jnz     short loc_18007BB13
0x18007bb0c  mov     ebx, 80004003h
0x18007bb11  jmp     short loc_18007BB55
0x18007bb13  mov     r8, [rbx+50h]
0x18007bb17  test    r8, r8
0x18007bb1a  jz      short loc_18007BB28
0x18007bb1c  mov     rax, [r8]
0x18007bb1f  mov     rcx, r8
0x18007bb22  mov     rax, [rax+18h]
0x18007bb26  jmp     short loc_18007BB3D
0x18007bb28  cmp     dword ptr [rbx+0C0h], 0
0x18007bb2f  jz      short loc_18007BB50
0x18007bb31  mov     rax, [rbx-10h]
0x18007bb35  lea     rcx, [rbx-10h]
0x18007bb39  mov     rax, [rax+58h]
0x18007bb3d  mov     rdx, rdi
0x18007bb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb4c  mov     ebx, eax
0x18007bb4e  jmp     short loc_18007BB55
0x18007bb50  mov     ebx, 8004101Dh
0x18007bb55  cmp     rcx, rsi
0x18007bb58  jz      short loc_18007BB86
0x18007bb5a  test    byte ptr [rcx+1Ch], 80h
0x18007bb5e  jz      short loc_18007BB86
0x18007bb60  cmp     byte ptr [rcx+19h], 5
0x18007bb64  jb      short loc_18007BB86
0x18007bb66  mov     rcx, [rcx+10h]
0x18007bb6a  lea     r9, aItemchangewrap_9; "ItemChangeWrapper::GetLearnedKnowledgeA"...
0x18007bb71  mov     edx, 35h ; '5'
0x18007bb76  mov     [rsp+38h+var_18], ebx
0x18007bb7a  lea     r8, WPP_c46487f44df63404f221e65d0a11538d_Traceguids
0x18007bb81  call    WPP_SF_sD
0x18007bb86  mov     rsi, [rsp+38h+arg_8]
0x18007bb8b  mov     eax, ebx
0x18007bb8d  mov     rbx, [rsp+38h+arg_0]
0x18007bb92  add     rsp, 30h
0x18007bb96  pop     rdi
0x18007bb97  retn
```
