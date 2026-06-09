# CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge * *)

- ea: `0x180069b20`
- end: `0x180069c06`
- name: `?GetLearnedKnowledgeAfterRecoveryComplete@CSyncChangeWrapper@@UEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180069b20`
- `0x180094010`

## string_xrefs

- `0x180069b52`: `CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete`
- `0x180069bdf`: `CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete(
        CSyncChangeWrapper *this,
        struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 7);
    if ( v6 )
      v7 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v6 + 24LL))(v6, a2);
    else
      v7 = (*(__int64 (__fastcall **)(char *, struct ISyncKnowledge **))(*((_QWORD *)this - 2) + 88LL))(
             (char *)this - 16,
             a2);
    v5 = v7;
    if ( v7 >= 0 && *((_QWORD *)this + 49) )
      v5 = ((__int64 (__fastcall *)(_QWORD))(*a2)->lpVtbl->Union)(*a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      60,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::GetLearnedKnowledgeAfterRecoveryComplete",
      v5);
  return v5;
}

```

## disassembly

```asm
0x180069b20  push    rbx
0x180069b22  push    rbp
0x180069b23  push    rsi
0x180069b24  push    rdi
0x180069b25  sub     rsp, 38h
0x180069b29  mov     rsi, rdx
0x180069b2c  mov     rdi, rcx
0x180069b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069b36  lea     rbp, WPP_GLOBAL_Control
0x180069b3d  cmp     rcx, rbp
0x180069b40  jz      short loc_180069B71
0x180069b42  test    byte ptr [rcx+1Ch], 8
0x180069b46  jz      short loc_180069B71
0x180069b48  cmp     byte ptr [rcx+19h], 5
0x180069b4c  jb      short loc_180069B71
0x180069b4e  mov     rcx, [rcx+10h]
0x180069b52  lea     r9, aCsyncchangewra_19; "CSyncChangeWrapper::GetLearnedKnowledge"...
0x180069b59  mov     edx, 3Bh ; ';'
0x180069b5e  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180069b65  call    WPP_SF_s
0x180069b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180069b71  mov     ebx, 80004003h
0x180069b76  test    rsi, rsi
0x180069b79  jz      short loc_180069BCA
0x180069b7b  mov     rcx, [rdi+38h]
0x180069b7f  mov     rdx, rsi
0x180069b82  test    rcx, rcx
0x180069b85  jz      short loc_180069B90
0x180069b87  mov     rax, [rcx]
0x180069b8a  mov     rax, [rax+18h]
0x180069b8e  jmp     short loc_180069B9B
0x180069b90  lea     rcx, [rdi-10h]
0x180069b94  mov     rax, [rcx]
0x180069b97  mov     rax, [rax+58h]
0x180069b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ba0  mov     ebx, eax
0x180069ba2  test    eax, eax
0x180069ba4  js      short loc_180069BC3
0x180069ba6  mov     rdx, [rdi+188h]
0x180069bad  test    rdx, rdx
0x180069bb0  jz      short loc_180069BC3
0x180069bb2  mov     rcx, [rsi]
0x180069bb5  mov     rax, [rcx]
0x180069bb8  mov     rax, [rax+68h]
0x180069bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bc1  mov     ebx, eax
0x180069bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180069bca  cmp     rcx, rbp
0x180069bcd  jz      short loc_180069BFB
0x180069bcf  test    byte ptr [rcx+1Ch], 8
0x180069bd3  jz      short loc_180069BFB
0x180069bd5  cmp     byte ptr [rcx+19h], 5
0x180069bd9  jb      short loc_180069BFB
0x180069bdb  mov     rcx, [rcx+10h]
0x180069bdf  lea     r9, aCsyncchangewra_19; "CSyncChangeWrapper::GetLearnedKnowledge"...
0x180069be6  mov     edx, 3Ch ; '<'
0x180069beb  mov     [rsp+58h+var_38], ebx
0x180069bef  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180069bf6  call    WPP_SF_sD
0x180069bfb  mov     eax, ebx
0x180069bfd  add     rsp, 38h
0x180069c01  pop     rdi
0x180069c02  pop     rsi
0x180069c03  pop     rbp
0x180069c04  pop     rbx
0x180069c05  retn
```
