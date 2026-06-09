# create_environment<wchar_t>(wchar_t * const)

- ea: `0x14002289c`
- end: `0x1400229b7`
- name: `??$create_environment@_W@@YAQEAPEA_WQEA_W@Z`
- size: `283`
- prototype: `void *__fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002282c`

## callees

- `0x140003b60`
- `0x14000471c`
- `0x14001074c`
- `0x1400107c4`
- `0x14002289c`
- `0x1400229b8`

## pseudocode

```c
void *__fastcall create_environment<wchar_t>(wchar_t *Source)
{
  __int64 v2; // rcx
  wchar_t *v3; // r8
  wchar_t i; // dx
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rax
  void *v8; // rbx
  wchar_t **v10; // r15
  __int64 v11; // rsi
  size_t v12; // rsi
  wchar_t *v13; // rax
  wchar_t *v14; // rdi

  v2 = 0;
  v3 = Source;
  for ( i = *Source; i; i = *v3 )
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
  if ( v7 )
  {
    v10 = (wchar_t **)v7;
    while ( *Source )
    {
      v11 = -1;
      do
        ++v11;
      while ( Source[v11] );
      v12 = v11 + 1;
      if ( *Source != 61 )
      {
        v13 = (wchar_t *)calloc_base(v12, 2u);
        v14 = v13;
        if ( !v13 )
        {
          unknown_libname_74(v8);
          free_base(0);
          goto LABEL_9;
        }
        if ( wcscpy_s(v13, v12, Source) )
          invoke_watson(0, 0, 0, 0, 0);
        *v10++ = v14;
        free_base(0);
      }
      Source += v12;
    }
    free_base(0);
    return v8;
  }
  else
  {
LABEL_9:
    free_base(0);
    return 0;
  }
}

```

## disassembly

```asm
0x14002289c  mov     [rsp+arg_0], rbx
0x1400228a1  mov     [rsp+arg_8], rbp
0x1400228a6  mov     [rsp+arg_10], rsi
0x1400228ab  push    rdi
0x1400228ac  push    r14
0x1400228ae  push    r15
0x1400228b0  sub     rsp, 30h
0x1400228b4  mov     r14, rcx
0x1400228b7  xor     ebp, ebp
0x1400228b9  mov     ecx, ebp
0x1400228bb  mov     r8, r14
0x1400228be  movzx   edx, word ptr [r14]
0x1400228c2  jmp     short loc_1400228ED
0x1400228c4  cmp     dx, 3Dh ; '='
0x1400228c8  lea     rax, [rcx+1]
0x1400228cc  cmovz   rax, rcx
0x1400228d0  mov     rcx, rax
0x1400228d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400228d7  inc     rax
0x1400228da  cmp     [r8+rax*2], bp
0x1400228df  jnz     short loc_1400228D7
0x1400228e1  lea     r8, [r8+rax*2]
0x1400228e5  add     r8, 2
0x1400228e9  movzx   edx, word ptr [r8]
0x1400228ed  test    dx, dx
0x1400228f0  jnz     short loc_1400228C4
0x1400228f2  inc     rcx; Count
0x1400228f5  mov     edx, 8; Size
0x1400228fa  call    _calloc_base
0x1400228ff  mov     rbx, rax
0x140022902  test    rax, rax
0x140022905  jnz     short loc_140022912
0x140022907  xor     ecx, ecx; Block
0x140022909  call    _free_base
0x14002290e  xor     eax, eax
0x140022910  jmp     short loc_14002298B
0x140022912  mov     r15, rbx
0x140022915  movzx   eax, word ptr [r14]
0x140022919  test    ax, ax
0x14002291c  jz      short loc_140022981
0x14002291e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140022922  inc     rsi
0x140022925  cmp     [r14+rsi*2], bp
0x14002292a  jnz     short loc_140022922
0x14002292c  inc     rsi
0x14002292f  cmp     ax, 3Dh ; '='
0x140022933  jz      short loc_14002296A
0x140022935  mov     edx, 2; Size
0x14002293a  mov     rcx, rsi; Count
0x14002293d  call    _calloc_base
0x140022942  mov     rdi, rax
0x140022945  test    rax, rax
0x140022948  jz      short loc_140022970
0x14002294a  mov     r8, r14; Source
0x14002294d  mov     rdx, rsi; SizeInWords
0x140022950  mov     rcx, rax; Dest
0x140022953  call    wcscpy_s
0x140022958  xor     ecx, ecx; Block
0x14002295a  test    eax, eax
0x14002295c  jnz     short loc_1400229A4
0x14002295e  mov     [r15], rdi
0x140022961  add     r15, 8
0x140022965  call    _free_base
0x14002296a  lea     r14, [r14+rsi*2]
0x14002296e  jmp     short loc_140022915
0x140022970  mov     rcx, rbx; Block
0x140022973  call    unknown_libname_74; Microsoft VisualC 64bit universal runtime
0x140022978  xor     ecx, ecx; Block
0x14002297a  call    _free_base
0x14002297f  jmp     short loc_140022907
0x140022981  xor     ecx, ecx; Block
0x140022983  call    _free_base
0x140022988  mov     rax, rbx
0x14002298b  mov     rbx, [rsp+48h+arg_0]
0x140022990  mov     rbp, [rsp+48h+arg_8]
0x140022995  mov     rsi, [rsp+48h+arg_10]
0x14002299a  add     rsp, 30h
0x14002299e  pop     r15
0x1400229a0  pop     r14
0x1400229a2  pop     rdi
0x1400229a3  retn
0x1400229a4  xor     r9d, r9d; LineNo
0x1400229a7  mov     [rsp+48h+Reserved], rbp; Reserved
0x1400229ac  xor     r8d, r8d; FileName
0x1400229af  xor     edx, edx; FunctionName
0x1400229b1  call    _invoke_watson
```
