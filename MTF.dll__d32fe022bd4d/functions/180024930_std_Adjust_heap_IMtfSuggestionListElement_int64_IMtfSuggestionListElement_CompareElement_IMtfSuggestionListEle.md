# std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(IMtfSuggestionListElement * *,__int64,__int64,IMtfSuggestionListElement * &&,CompareElement)

- ea: `0x180024930`
- end: `0x180024a55`
- name: `??$_Adjust_heap@PEAPEAUIMtfSuggestionListElement@@_JPEAU1@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@_J1$$QEAPEAU1@UCompareElement@@@Z`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024b78`

## callees

- `0x180024930`
- `0x18002f010`

## pseudocode

```c
__int64 *__fastcall std::_Adjust_heap<IMtfSuggestionListElement * *,__int64,IMtfSuggestionListElement *,CompareElement>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 **a4,
        unsigned int a5)
{
  __int64 v5; // r15
  __int64 i; // rsi
  __int64 v11; // rcx
  __int64 *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 *v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 *result; // rax
  unsigned int v20; // [rsp+70h] [rbp+48h] BYREF

  v5 = 2 * a2 + 2;
  for ( i = a2; v5 < a3; i = v14 )
  {
    v11 = *(_QWORD *)(a1 + 8 * v5);
    v12 = *(__int64 **)(a1 + 8 * v5 - 8);
    v20 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 24LL))(v11, &v20);
    v13 = *v12;
    a5 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v13 + 24))(v12, &a5);
    v14 = v5 - 1;
    if ( v20 <= a5 )
      v14 = v5;
    v5 = 2 * v14 + 2;
    *(_QWORD *)(a1 + 8 * i) = *(_QWORD *)(a1 + 8 * v14);
  }
  if ( v5 == a3 )
  {
    *(_QWORD *)(a1 + 8 * i) = *(_QWORD *)(a1 + 8 * a3 - 8);
    i = a3 - 1;
  }
  if ( a2 < i )
  {
    do
    {
      v15 = i - 1;
      if ( i - 1 < 0 )
        v15 = i;
      v16 = *a4;
      v17 = v15 >> 1;
      v20 = 0;
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8 * v17) + 24LL))(
        *(_QWORD *)(a1 + 8 * v17),
        &v20);
      v18 = *v16;
      a5 = 0;
      (*(void (__fastcall **)(__int64 *, unsigned int *))(v18 + 24))(v16, &a5);
      if ( v20 <= a5 )
        break;
      *(_QWORD *)(a1 + 8 * i) = *(_QWORD *)(a1 + 8 * v17);
      i = v17;
    }
    while ( a2 < v17 );
  }
  result = *a4;
  *(_QWORD *)(a1 + 8 * i) = *a4;
  return result;
}

```

## disassembly

```asm
0x180024930  push    rbp
0x180024932  push    rbx
0x180024933  push    rsi
0x180024934  push    rdi
0x180024935  push    r12
0x180024937  push    r13
0x180024939  push    r14
0x18002493b  push    r15
0x18002493d  mov     rbp, rsp
0x180024940  sub     rsp, 28h
0x180024944  lea     r15, ds:2[rdx*2]
0x18002494c  mov     r13, r9
0x18002494f  mov     rdi, r8
0x180024952  mov     rsi, rdx
0x180024955  mov     r14, rcx
0x180024958  mov     r12, rdx
0x18002495b  cmp     r15, r8
0x18002495e  jge     short loc_1800249C5
0x180024960  mov     rcx, [r14+r15*8]
0x180024964  lea     rdx, [rbp+arg_0]
0x180024968  mov     rbx, [r14+r15*8-8]
0x18002496d  mov     [rbp+arg_0], 0
0x180024974  mov     rax, [rcx]
0x180024977  mov     rax, [rax+18h]
0x18002497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024980  mov     rax, [rbx]
0x180024983  lea     rdx, [rbp+arg_20]
0x180024987  mov     rcx, rbx
0x18002498a  mov     [rbp+arg_20], 0
0x180024991  mov     rax, [rax+18h]
0x180024995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002499a  mov     eax, [rbp+arg_20]
0x18002499d  lea     rcx, [r15-1]
0x1800249a1  cmp     [rbp+arg_0], eax
0x1800249a4  setnbe  al
0x1800249a7  test    al, al
0x1800249a9  cmovz   rcx, r15
0x1800249ad  mov     rax, [r14+rcx*8]
0x1800249b1  lea     r15, ds:2[rcx*2]
0x1800249b9  mov     [r14+rsi*8], rax
0x1800249bd  mov     rsi, rcx
0x1800249c0  cmp     r15, rdi
0x1800249c3  jl      short loc_180024960
0x1800249c5  cmp     r15, rdi
0x1800249c8  jnz     short loc_1800249D7
0x1800249ca  mov     rax, [r14+rdi*8-8]
0x1800249cf  mov     [r14+rsi*8], rax
0x1800249d3  lea     rsi, [rdi-1]
0x1800249d7  cmp     r12, rsi
0x1800249da  jge     short loc_180024A3C
0x1800249dc  lea     rdi, [rsi-1]
0x1800249e0  test    rdi, rdi
0x1800249e3  jns     short loc_1800249E8
0x1800249e5  inc     rdi
0x1800249e8  mov     rbx, [r13+0]
0x1800249ec  lea     rdx, [rbp+arg_0]
0x1800249f0  sar     rdi, 1
0x1800249f3  mov     [rbp+arg_0], 0
0x1800249fa  mov     rcx, [r14+rdi*8]
0x1800249fe  mov     rax, [rcx]
0x180024a01  mov     rax, [rax+18h]
0x180024a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a0a  mov     rax, [rbx]
0x180024a0d  lea     rdx, [rbp+arg_20]
0x180024a11  mov     rcx, rbx
0x180024a14  mov     [rbp+arg_20], 0
0x180024a1b  mov     rax, [rax+18h]
0x180024a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a24  mov     eax, [rbp+arg_20]
0x180024a27  cmp     [rbp+arg_0], eax
0x180024a2a  jbe     short loc_180024A3C
0x180024a2c  mov     rax, [r14+rdi*8]
0x180024a30  mov     [r14+rsi*8], rax
0x180024a34  mov     rsi, rdi
0x180024a37  cmp     r12, rdi
0x180024a3a  jl      short loc_1800249DC
0x180024a3c  mov     rax, [r13+0]
0x180024a40  mov     [r14+rsi*8], rax
0x180024a44  add     rsp, 28h
0x180024a48  pop     r15
0x180024a4a  pop     r14
0x180024a4c  pop     r13
0x180024a4e  pop     r12
0x180024a50  pop     rdi
0x180024a51  pop     rsi
0x180024a52  pop     rbx
0x180024a53  pop     rbp
0x180024a54  retn
```
