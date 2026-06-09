# create_environment<wchar_t>(wchar_t * const)

- ea: `0x1400180f4`
- end: `0x140018212`
- name: `??$create_environment@_W@@YAQEAPEA_WQEA_W@Z`
- size: `286`
- prototype: `void *__fastcall(__int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140018084`

## callees

- `0x1400160bc`
- `0x1400180f4`
- `0x140018214`
- `0x140019930`
- `0x14001b910`
- `0x14001d490`

## pseudocode

```c
void *__fastcall create_environment<wchar_t>(__int16 *a1)
{
  __int64 v2; // rcx
  __int16 *v3; // r8
  __int16 i; // dx
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rax
  void *v8; // rbx
  _QWORD *v10; // r15
  __int64 v11; // rsi
  size_t v12; // rsi
  void *v13; // rax
  void *v14; // rdi

  v2 = 0;
  v3 = a1;
  for ( i = *a1; i; i = *v3 )
  {
    v5 = v2 + 1;
    if ( i == 61 )
      v5 = v2;
    v2 = v5;
    v6 = -1;
    do
      ++v6;
    while ( v3[v6] );
    v3 += v6 + 1;
  }
  v7 = calloc_base(v2 + 1, 8u);
  v8 = v7;
  if ( !v7 )
    goto LABEL_9;
  v10 = v7;
  while ( 1 )
  {
    if ( !*a1 )
    {
      free_base(0);
      return v8;
    }
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    v12 = v11 + 1;
    if ( *a1 != 61 )
      break;
LABEL_17:
    a1 += v12;
  }
  v13 = calloc_base(v12, 2u);
  v14 = v13;
  if ( v13 )
  {
    if ( (unsigned int)sub_14001D490(v13, v12, a1) )
      invoke_watson(0, 0, 0, 0, 0);
    *v10++ = v14;
    free_base(0);
    goto LABEL_17;
  }
  unknown_libname_43(v8);
  free_base(0);
LABEL_9:
  free_base(0);
  return 0;
}

```

## disassembly

```asm
0x1400180f4  mov     [rsp+arg_0], rbx
0x1400180f9  mov     [rsp+arg_8], rbp
0x1400180fe  mov     [rsp+arg_10], rsi
0x140018103  push    rdi
0x140018104  push    r14
0x140018106  push    r15
0x140018108  sub     rsp, 30h
0x14001810c  mov     r14, rcx
0x14001810f  xor     ebp, ebp
0x140018111  mov     ecx, ebp
0x140018113  mov     r8, r14
0x140018116  movzx   edx, word ptr [r14]
0x14001811a  jmp     short loc_140018145
0x14001811c  cmp     dx, 3Dh ; '='
0x140018120  lea     rax, [rcx+1]
0x140018124  cmovz   rax, rcx
0x140018128  mov     rcx, rax
0x14001812b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001812f  inc     rax
0x140018132  cmp     [r8+rax*2], bp
0x140018137  jnz     short loc_14001812F
0x140018139  lea     r8, [r8+rax*2]
0x14001813d  add     r8, 2
0x140018141  movzx   edx, word ptr [r8]
0x140018145  test    dx, dx
0x140018148  jnz     short loc_14001811C
0x14001814a  inc     rcx; Count
0x14001814d  mov     edx, 8; Size
0x140018152  call    _calloc_base
0x140018157  mov     rbx, rax
0x14001815a  test    rax, rax
0x14001815d  jnz     short loc_14001816A
0x14001815f  xor     ecx, ecx; Block
0x140018161  call    _free_base
0x140018166  xor     eax, eax
0x140018168  jmp     short loc_1400181D2
0x14001816a  mov     r15, rbx
0x14001816d  jmp     short loc_1400181BF
0x14001816f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140018173  inc     rsi
0x140018176  cmp     [r14+rsi*2], bp
0x14001817b  jnz     short loc_140018173
0x14001817d  inc     rsi
0x140018180  cmp     ax, 3Dh ; '='
0x140018184  jz      short loc_1400181BB
0x140018186  mov     edx, 2; Size
0x14001818b  mov     rcx, rsi; Count
0x14001818e  call    _calloc_base
0x140018193  mov     rdi, rax
0x140018196  test    rax, rax
0x140018199  jz      short loc_1400181EB
0x14001819b  mov     r8, r14
0x14001819e  mov     rdx, rsi
0x1400181a1  mov     rcx, rax
0x1400181a4  call    sub_14001D490
0x1400181a9  xor     ecx, ecx; Block
0x1400181ab  test    eax, eax
0x1400181ad  jnz     short loc_1400181FF
0x1400181af  mov     [r15], rdi
0x1400181b2  add     r15, 8
0x1400181b6  call    _free_base
0x1400181bb  lea     r14, [r14+rsi*2]
0x1400181bf  movzx   eax, word ptr [r14]
0x1400181c3  test    ax, ax
0x1400181c6  jnz     short loc_14001816F
0x1400181c8  xor     ecx, ecx; Block
0x1400181ca  call    _free_base
0x1400181cf  mov     rax, rbx
0x1400181d2  mov     rbx, [rsp+48h+arg_0]
0x1400181d7  mov     rbp, [rsp+48h+arg_8]
0x1400181dc  mov     rsi, [rsp+48h+arg_10]
0x1400181e1  add     rsp, 30h
0x1400181e5  pop     r15
0x1400181e7  pop     r14
0x1400181e9  pop     rdi
0x1400181ea  retn
0x1400181eb  mov     rcx, rbx; Block
0x1400181ee  call    unknown_libname_43; Microsoft VisualC 64bit universal runtime
0x1400181f3  xor     ecx, ecx; Block
0x1400181f5  call    _free_base
0x1400181fa  jmp     loc_14001815F
0x1400181ff  xor     r9d, r9d; LineNo
0x140018202  mov     [rsp+48h+Reserved], rbp; Reserved
0x140018207  xor     r8d, r8d; FileName
0x14001820a  xor     edx, edx; FunctionName
0x14001820c  call    _invoke_watson
```
