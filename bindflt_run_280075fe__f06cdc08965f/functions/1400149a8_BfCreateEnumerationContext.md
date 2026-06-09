# BfCreateEnumerationContext

- ea: `0x1400149a8`
- end: `0x140014a67`
- name: `BfCreateEnumerationContext`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140014324`
- `0x140024e40`

## callees

- `0x140004fc0`
- `0x1400149a8`
- `0x140020c70`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400149c6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400149ef`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400149c6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400149ef`

## pseudocode

```c
__int64 __fastcall BfCreateEnumerationContext(__int64 a1, __int64 a2, __int64 a3, char a4, int a5, __int64 a6)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  PVOID v12; // rax
  _QWORD *v13; // rdx
  __int64 result; // rax

  v10 = ExAllocateFromPagedLookasideList(&Lookaside);
  v11 = v10;
  if ( !v10 )
    return 3221225626LL;
  memset(v10, 0, 0x48u);
  v12 = ExAllocateFromPagedLookasideList(&stru_14000B480);
  v11[8] = v12;
  if ( !v12 )
  {
    BfDeleteEnumerationContext(v11);
    return 3221225626LL;
  }
  v11[3] = a3;
  v11[4] = a2;
  v11[5] = a1;
  *((_BYTE *)v11 + 16) = a4;
  *((_DWORD *)v11 + 14) = a5;
  v11[6] = 0;
  v13 = *(_QWORD **)(a6 + 104);
  if ( *v13 != a6 + 96 )
    __fastfail(3u);
  *v11 = a6 + 96;
  result = 0;
  v11[1] = v13;
  *v13 = v11;
  *(_QWORD *)(a6 + 104) = v11;
  return result;
}

```

## disassembly

```asm
0x1400149a8  push    rbx
0x1400149aa  push    rbp
0x1400149ab  push    rsi
0x1400149ac  push    rdi
0x1400149ad  push    r14
0x1400149af  sub     rsp, 20h
0x1400149b3  mov     r14, rcx
0x1400149b6  mov     dil, r9b
0x1400149b9  lea     rcx, Lookaside; Lookaside
0x1400149c0  mov     rsi, r8
0x1400149c3  mov     rbp, rdx
0x1400149c6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400149cd  nop     dword ptr [rax+rax+00h]
0x1400149d2  mov     rbx, rax
0x1400149d5  test    rax, rax
0x1400149d8  jz      short loc_140014A59
0x1400149da  xor     edx, edx; Val
0x1400149dc  mov     rcx, rax; void *
0x1400149df  lea     r8d, [rdx+48h]; Size
0x1400149e3  call    memset
0x1400149e8  lea     rcx, stru_14000B480; Lookaside
0x1400149ef  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400149f6  nop     dword ptr [rax+rax+00h]
0x1400149fb  mov     [rbx+40h], rax
0x1400149ff  test    rax, rax
0x140014a02  jz      short loc_140014A51
0x140014a04  mov     rcx, [rsp+48h+arg_28]
0x140014a09  mov     eax, [rsp+48h+arg_20]
0x140014a0d  add     rcx, 60h ; '`'
0x140014a11  mov     [rbx+18h], rsi
0x140014a15  mov     [rbx+20h], rbp
0x140014a19  mov     [rbx+28h], r14
0x140014a1d  mov     [rbx+10h], dil
0x140014a21  mov     [rbx+38h], eax
0x140014a24  mov     qword ptr [rbx+30h], 0
0x140014a2c  mov     rdx, [rcx+8]
0x140014a30  cmp     [rdx], rcx
0x140014a33  jnz     short loc_140014A60
0x140014a35  mov     [rbx], rcx
0x140014a38  xor     eax, eax
0x140014a3a  mov     [rbx+8], rdx
0x140014a3e  mov     [rdx], rbx
0x140014a41  mov     [rcx+8], rbx
0x140014a45  add     rsp, 20h
0x140014a49  pop     r14
0x140014a4b  pop     rdi
0x140014a4c  pop     rsi
0x140014a4d  pop     rbp
0x140014a4e  pop     rbx
0x140014a4f  retn
0x140014a51  mov     rcx, rbx; Entry
0x140014a54  call    BfDeleteEnumerationContext
0x140014a59  mov     eax, 0C000009Ah
0x140014a5e  jmp     short loc_140014A45
0x140014a60  mov     ecx, 3
0x140014a65  int     29h; Win8: RtlFailFast(ecx)
```
