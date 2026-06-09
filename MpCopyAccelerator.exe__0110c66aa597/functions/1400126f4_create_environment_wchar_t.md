# create_environment_wchar_t_

- ea: `0x1400126f4`
- end: `0x140012812`
- name: `create_environment_wchar_t_`
- size: `286`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012684`

## callees

- `0x14000bf7c`
- `0x1400126f4`
- `0x140012814`
- `0x140013e10`
- `0x140013ed0`
- `0x140013fe0`

## pseudocode

```c
void *__fastcall create_environment_wchar_t_(wchar_t *Source)
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
  if ( !v7 )
    goto LABEL_9;
  v10 = (wchar_t **)v7;
  while ( 1 )
  {
    if ( !*Source )
    {
      free_base(0);
      return v8;
    }
    v11 = -1;
    do
      ++v11;
    while ( Source[v11] );
    v12 = v11 + 1;
    if ( *Source != 61 )
      break;
LABEL_17:
    Source += v12;
  }
  v13 = (wchar_t *)calloc_base(v12, 2u);
  v14 = v13;
  if ( v13 )
  {
    if ( wcscpy_s(v13, v12, Source) )
      invoke_watson(0, 0, 0, 0, 0);
    *v10++ = v14;
    free_base(0);
    goto LABEL_17;
  }
  free_environment_wchar_t_(v8);
  free_base(0);
LABEL_9:
  free_base(0);
  return 0;
}

```

## disassembly

```asm
0x1400126f4  mov     [rsp+arg_0], rbx
0x1400126f9  mov     [rsp+arg_8], rbp
0x1400126fe  mov     [rsp+arg_10], rsi
0x140012703  push    rdi
0x140012704  push    r14
0x140012706  push    r15
0x140012708  sub     rsp, 30h
0x14001270c  mov     r14, rcx
0x14001270f  xor     ebp, ebp
0x140012711  mov     ecx, ebp
0x140012713  mov     r8, r14
0x140012716  movzx   edx, word ptr [r14]
0x14001271a  jmp     short loc_140012745
0x14001271c  cmp     dx, 3Dh ; '='
0x140012720  lea     rax, [rcx+1]
0x140012724  cmovz   rax, rcx
0x140012728  mov     rcx, rax
0x14001272b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001272f  inc     rax
0x140012732  cmp     [r8+rax*2], bp
0x140012737  jnz     short loc_14001272F
0x140012739  lea     r8, [r8+rax*2]
0x14001273d  add     r8, 2
0x140012741  movzx   edx, word ptr [r8]
0x140012745  test    dx, dx
0x140012748  jnz     short loc_14001271C
0x14001274a  inc     rcx; Count
0x14001274d  mov     edx, 8; Size
0x140012752  call    _calloc_base
0x140012757  mov     rbx, rax
0x14001275a  test    rax, rax
0x14001275d  jnz     short loc_14001276A
0x14001275f  xor     ecx, ecx; Block
0x140012761  call    _free_base
0x140012766  xor     eax, eax
0x140012768  jmp     short loc_1400127D2
0x14001276a  mov     r15, rbx
0x14001276d  jmp     short loc_1400127BF
0x14001276f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140012773  inc     rsi
0x140012776  cmp     [r14+rsi*2], bp
0x14001277b  jnz     short loc_140012773
0x14001277d  inc     rsi
0x140012780  cmp     ax, 3Dh ; '='
0x140012784  jz      short loc_1400127BB
0x140012786  mov     edx, 2; Size
0x14001278b  mov     rcx, rsi; Count
0x14001278e  call    _calloc_base
0x140012793  mov     rdi, rax
0x140012796  test    rax, rax
0x140012799  jz      short loc_1400127EB
0x14001279b  mov     r8, r14; Source
0x14001279e  mov     rdx, rsi; SizeInWords
0x1400127a1  mov     rcx, rax; Destination
0x1400127a4  call    wcscpy_s
0x1400127a9  xor     ecx, ecx; Expression
0x1400127ab  test    eax, eax
0x1400127ad  jnz     short loc_1400127FF
0x1400127af  mov     [r15], rdi
0x1400127b2  add     r15, 8
0x1400127b6  call    _free_base
0x1400127bb  lea     r14, [r14+rsi*2]
0x1400127bf  movzx   eax, word ptr [r14]
0x1400127c3  test    ax, ax
0x1400127c6  jnz     short loc_14001276F
0x1400127c8  xor     ecx, ecx; Block
0x1400127ca  call    _free_base
0x1400127cf  mov     rax, rbx
0x1400127d2  mov     rbx, [rsp+48h+arg_0]
0x1400127d7  mov     rbp, [rsp+48h+arg_8]
0x1400127dc  mov     rsi, [rsp+48h+arg_10]
0x1400127e1  add     rsp, 30h
0x1400127e5  pop     r15
0x1400127e7  pop     r14
0x1400127e9  pop     rdi
0x1400127ea  retn
0x1400127eb  mov     rcx, rbx; Block
0x1400127ee  call    free_environment_wchar_t_
0x1400127f3  xor     ecx, ecx; Block
0x1400127f5  call    _free_base
0x1400127fa  jmp     loc_14001275F
0x1400127ff  xor     r9d, r9d; LineNo
0x140012802  mov     [rsp+48h+Reserved], rbp; Reserved
0x140012807  xor     r8d, r8d; FileName
0x14001280a  xor     edx, edx; FunctionName
0x14001280c  call    _invoke_watson
```
