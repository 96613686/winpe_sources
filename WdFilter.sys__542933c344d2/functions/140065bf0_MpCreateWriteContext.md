# MpCreateWriteContext

- ea: `0x140065bf0`
- end: `0x140065d00`
- name: `MpCreateWriteContext`
- size: `272`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, PFLT_CONTEXT)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001900`

## callees

- `0x140003d20`
- `0x140011890`
- `0x140065bf0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140065c28`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140065c28`
- `FLTMGR!FltReferenceContext` at `0x140065c65`
- `FLTMGR!FltReferenceContext` at `0x140065cf2`
- `FLTMGR!FltReferenceContext` at `0x140065c65`
- `FLTMGR!FltReferenceContext` at `0x140065cf2`

## pseudocode

```c
__int64 __fastcall MpCreateWriteContext(PFLT_CONTEXT Context, PFLT_CONTEXT a2, __int64 a3, PSLIST_ENTRY *a4)
{
  ULONG_PTR v5; // rbp
  union _SLIST_HEADER *v7; // rcx
  PSLIST_ENTRY v10; // rbx
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(__int64, __int64, __int64); // rax
  __int64 v13; // r8
  __int64 v14; // rcx

  v5 = MpData + 1152;
  v7 = (union _SLIST_HEADER *)(MpData + 1152);
  ++*(_DWORD *)(MpData + 1172);
  v10 = ExpInterlockedPopEntrySList(v7);
  if ( v10
    || (v11 = *(unsigned int *)(v5 + 44),
        v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(v5 + 48),
        v13 = *(unsigned int *)(v5 + 40),
        v14 = *(unsigned int *)(v5 + 36),
        ++*(_DWORD *)(v5 + 24),
        (v10 = (PSLIST_ENTRY)v12(v14, v11, v13)) != 0) )
  {
    v10->Next = 0;
    FltReferenceContext(Context);
    v10[1].Next = (struct _SLIST_ENTRY *)Context;
    *((_QWORD *)&v10[2].Next + 1) = a3;
    v10[2].Next = (struct _SLIST_ENTRY *)*((_QWORD *)Context + 1);
    *((_QWORD *)&v10[1].Next + 1) = a2;
    if ( a2 )
      FltReferenceContext(a2);
    *a4 = v10;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids,
        KeGetCurrentThread());
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140065bf0  mov     [rsp+arg_0], rbx
0x140065bf5  mov     [rsp+arg_8], rbp
0x140065bfa  mov     [rsp+arg_10], rsi
0x140065bff  push    rdi
0x140065c00  push    r14
0x140065c02  push    r15
0x140065c04  sub     rsp, 20h
0x140065c08  mov     rbp, cs:MpData
0x140065c0f  mov     rdi, rcx
0x140065c12  add     rbp, 480h
0x140065c19  mov     r14, r9
0x140065c1c  mov     rcx, rbp; ListHead
0x140065c1f  mov     r15, r8
0x140065c22  mov     rsi, rdx
0x140065c25  inc     dword ptr [rbp+14h]
0x140065c28  call    cs:__imp_ExpInterlockedPopEntrySList
0x140065c2f  nop     dword ptr [rax+rax+00h]
0x140065c34  mov     rbx, rax
0x140065c37  test    rax, rax
0x140065c3a  jnz     short loc_140065C5B
0x140065c3c  mov     edx, [rbp+2Ch]
0x140065c3f  mov     rax, [rbp+30h]
0x140065c43  mov     r8d, [rbp+28h]
0x140065c47  mov     ecx, [rbp+24h]
0x140065c4a  inc     dword ptr [rbp+18h]
0x140065c4d  call    cs:__guard_dispatch_icall_fptr
0x140065c53  mov     rbx, rax
0x140065c56  test    rax, rax
0x140065c59  jz      short loc_140065CA9
0x140065c5b  mov     rcx, rdi; Context
0x140065c5e  mov     qword ptr [rbx], 0
0x140065c65  call    cs:__imp_FltReferenceContext
0x140065c6c  nop     dword ptr [rax+rax+00h]
0x140065c71  mov     [rbx+10h], rdi
0x140065c75  mov     [rbx+28h], r15
0x140065c79  mov     rax, [rdi+8]
0x140065c7d  mov     [rbx+20h], rax
0x140065c81  mov     [rbx+18h], rsi
0x140065c85  test    rsi, rsi
0x140065c88  jnz     short loc_140065CEF
0x140065c8a  mov     [r14], rbx
0x140065c8d  xor     eax, eax
0x140065c8f  mov     rbx, [rsp+38h+arg_0]
0x140065c94  mov     rbp, [rsp+38h+arg_8]
0x140065c99  mov     rsi, [rsp+38h+arg_10]
0x140065c9e  add     rsp, 20h
0x140065ca2  pop     r15
0x140065ca4  pop     r14
0x140065ca6  pop     rdi
0x140065ca7  retn
0x140065ca9  mov     rax, cs:WPP_GLOBAL_Control
0x140065cb0  lea     rcx, WPP_GLOBAL_Control
0x140065cb7  cmp     rax, rcx
0x140065cba  jz      short loc_140065CE8
0x140065cbc  mov     eax, [rax+2Ch]
0x140065cbf  test    al, 1
0x140065cc1  jz      short loc_140065CE8
0x140065cc3  mov     r9, gs:188h
0x140065ccc  lea     r8, WPP_bb45134bc4783ccc369f21c9f9edadb7_Traceguids
0x140065cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140065cda  mov     edx, 17h
0x140065cdf  mov     rcx, [rcx+18h]
0x140065ce3  call    WPP_SF_q
0x140065ce8  mov     eax, 0C000009Ah
0x140065ced  jmp     short loc_140065C8F
0x140065cef  mov     rcx, rsi; Context
0x140065cf2  call    cs:__imp_FltReferenceContext
0x140065cf9  nop     dword ptr [rax+rax+00h]
0x140065cfe  jmp     short loc_140065C8A
```
