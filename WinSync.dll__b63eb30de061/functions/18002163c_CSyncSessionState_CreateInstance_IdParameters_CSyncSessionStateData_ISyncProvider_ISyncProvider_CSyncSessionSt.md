# CSyncSessionState_CreateInstance(IdParameters *,CSyncSessionStateData *,ISyncProvider *,ISyncProvider *,CSyncSessionState * *)

- ea: `0x18002163c`
- end: `0x18002171e`
- name: `?CSyncSessionState_CreateInstance@@YAJPEAVIdParameters@@PEAVCSyncSessionStateData@@PEAUISyncProvider@@2PEAPEAVCSyncSessionState@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct IdParameters *, struct CSyncSessionStateData *, struct ISyncProvider *, struct ISyncProvider *, struct CSyncSessionState **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180020dac`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002163c`
- `0x18002d5f0`

## string_xrefs

- `0x18002167a`: `CSyncSessionState_CreateInstance`
- `0x1800216f1`: `CSyncSessionState_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncSessionState_CreateInstance(
        struct IdParameters *a1,
        struct CSyncSessionStateData *a2,
        struct ISyncProvider *a3,
        struct ISyncProvider *a4,
        struct CSyncSessionState **a5)
{
  unsigned int v9; // ebx
  CSyncSessionState *v10; // rax
  struct CSyncSessionState *v11; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      114,
      WPP_24b986413345305da18a80c41c45e189_Traceguids,
      "CSyncSessionState_CreateInstance");
  }
  v9 = -2147024882;
  *a5 = 0;
  v10 = (CSyncSessionState *)SeAlloc(0x30u);
  if ( v10 )
  {
    v11 = CSyncSessionState::CSyncSessionState(v10, a1, a2, a3, a4);
    if ( v11 )
    {
      v9 = 0;
      *a5 = v11;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      (unsigned int)WPP_24b986413345305da18a80c41c45e189_Traceguids,
      (unsigned int)"CSyncSessionState_CreateInstance",
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002163c  push    rbx
0x18002163e  push    rbp
0x18002163f  push    rsi
0x180021640  push    rdi
0x180021641  push    r12
0x180021643  push    r14
0x180021645  push    r15
0x180021647  sub     rsp, 30h
0x18002164b  mov     rsi, r9
0x18002164e  mov     rbp, r8
0x180021651  mov     r14, rdx
0x180021654  mov     r15, rcx
0x180021657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002165e  lea     r12, WPP_GLOBAL_Control
0x180021665  cmp     rcx, r12
0x180021668  jz      short loc_180021692
0x18002166a  test    byte ptr [rcx+1Ch], 4
0x18002166e  jz      short loc_180021692
0x180021670  cmp     byte ptr [rcx+19h], 5
0x180021674  jb      short loc_180021692
0x180021676  mov     rcx, [rcx+10h]
0x18002167a  lea     r9, aCsyncsessionst_16; "CSyncSessionState_CreateInstance"
0x180021681  mov     edx, 72h ; 'r'
0x180021686  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002168d  call    WPP_SF_s
0x180021692  mov     rdi, [rsp+68h+arg_20]
0x18002169a  mov     ecx, 30h ; '0'; unsigned __int64
0x18002169f  mov     ebx, 8007000Eh
0x1800216a4  mov     qword ptr [rdi], 0
0x1800216ab  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800216b0  test    rax, rax
0x1800216b3  jz      short loc_1800216D5
0x1800216b5  mov     r9, rbp; struct ISyncProvider *
0x1800216b8  mov     [rsp+68h+var_48], rsi; struct ISyncProvider *
0x1800216bd  mov     r8, r14; struct CSyncSessionStateData *
0x1800216c0  mov     rdx, r15; struct IdParameters *
0x1800216c3  mov     rcx, rax; this
0x1800216c6  call    ??0CSyncSessionState@@QEAA@PEAVIdParameters@@PEAVCSyncSessionStateData@@PEAUISyncProvider@@2@Z; CSyncSessionState::CSyncSessionState(IdParameters *,CSyncSessionStateData *,ISyncProvider *,ISyncProvider *)
0x1800216cb  test    rax, rax
0x1800216ce  jz      short loc_1800216D5
0x1800216d0  xor     ebx, ebx
0x1800216d2  mov     [rdi], rax
0x1800216d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216dc  cmp     rcx, r12
0x1800216df  jz      short loc_18002170D
0x1800216e1  test    byte ptr [rcx+1Ch], 4
0x1800216e5  jz      short loc_18002170D
0x1800216e7  cmp     byte ptr [rcx+19h], 5
0x1800216eb  jb      short loc_18002170D
0x1800216ed  mov     rcx, [rcx+10h]
0x1800216f1  lea     r9, aCsyncsessionst_16; "CSyncSessionState_CreateInstance"
0x1800216f8  mov     edx, 73h ; 's'
0x1800216fd  mov     dword ptr [rsp+68h+var_48], ebx
0x180021701  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x180021708  call    WPP_SF_sD
0x18002170d  mov     eax, ebx
0x18002170f  add     rsp, 30h
0x180021713  pop     r15
0x180021715  pop     r14
0x180021717  pop     r12
0x180021719  pop     rdi
0x18002171a  pop     rsi
0x18002171b  pop     rbp
0x18002171c  pop     rbx
0x18002171d  retn
```
