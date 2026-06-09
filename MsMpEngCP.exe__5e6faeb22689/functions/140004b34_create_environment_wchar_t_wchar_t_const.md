# create_environment<wchar_t>(wchar_t * const)

- ea: `0x140004b34`
- end: `0x140004c52`
- name: `??$create_environment@_W@@YAQEAPEA_WQEA_W@Z`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004ac4`

## callees

- `0x140004b34`
- `0x140004c54`
- `0x140006564`
- `0x1400065b0`
- `0x1400068c0`
- `0x140006940`

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
    if ( (unsigned int)sub_1400065B0(v13, v12, a1) )
      invoke_watson(0, 0, 0, 0, 0);
    *v10++ = v14;
    free_base(0);
    goto LABEL_17;
  }
  unknown_libname_11(v8);
  free_base(0);
LABEL_9:
  free_base(0);
  return 0;
}

```

## disassembly

```asm
0x140004b34  mov     [rsp+arg_0], rbx
0x140004b39  mov     [rsp+arg_8], rbp
0x140004b3e  mov     [rsp+arg_10], rsi
0x140004b43  push    rdi
0x140004b44  push    r14
0x140004b46  push    r15
0x140004b48  sub     rsp, 30h
0x140004b4c  mov     r14, rcx
0x140004b4f  xor     ebp, ebp
0x140004b51  mov     ecx, ebp
0x140004b53  mov     r8, r14
0x140004b56  movzx   edx, word ptr [r14]
0x140004b5a  jmp     short loc_140004B85
0x140004b5c  cmp     dx, 3Dh ; '='
0x140004b60  lea     rax, [rcx+1]
0x140004b64  cmovz   rax, rcx
0x140004b68  mov     rcx, rax
0x140004b6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004b6f  inc     rax
0x140004b72  cmp     [r8+rax*2], bp
0x140004b77  jnz     short loc_140004B6F
0x140004b79  lea     r8, [r8+rax*2]
0x140004b7d  add     r8, 2
0x140004b81  movzx   edx, word ptr [r8]
0x140004b85  test    dx, dx
0x140004b88  jnz     short loc_140004B5C
0x140004b8a  inc     rcx; Count
0x140004b8d  mov     edx, 8; Size
0x140004b92  call    _calloc_base
0x140004b97  mov     rbx, rax
0x140004b9a  test    rax, rax
0x140004b9d  jnz     short loc_140004BAA
0x140004b9f  xor     ecx, ecx; Block
0x140004ba1  call    _free_base
0x140004ba6  xor     eax, eax
0x140004ba8  jmp     short loc_140004C12
0x140004baa  mov     r15, rbx
0x140004bad  jmp     short loc_140004BFF
0x140004baf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140004bb3  inc     rsi
0x140004bb6  cmp     [r14+rsi*2], bp
0x140004bbb  jnz     short loc_140004BB3
0x140004bbd  inc     rsi
0x140004bc0  cmp     ax, 3Dh ; '='
0x140004bc4  jz      short loc_140004BFB
0x140004bc6  mov     edx, 2; Size
0x140004bcb  mov     rcx, rsi; Count
0x140004bce  call    _calloc_base
0x140004bd3  mov     rdi, rax
0x140004bd6  test    rax, rax
0x140004bd9  jz      short loc_140004C2B
0x140004bdb  mov     r8, r14
0x140004bde  mov     rdx, rsi
0x140004be1  mov     rcx, rax
0x140004be4  call    sub_1400065B0
0x140004be9  xor     ecx, ecx; Block
0x140004beb  test    eax, eax
0x140004bed  jnz     short loc_140004C3F
0x140004bef  mov     [r15], rdi
0x140004bf2  add     r15, 8
0x140004bf6  call    _free_base
0x140004bfb  lea     r14, [r14+rsi*2]
0x140004bff  movzx   eax, word ptr [r14]
0x140004c03  test    ax, ax
0x140004c06  jnz     short loc_140004BAF
0x140004c08  xor     ecx, ecx; Block
0x140004c0a  call    _free_base
0x140004c0f  mov     rax, rbx
0x140004c12  mov     rbx, [rsp+48h+arg_0]
0x140004c17  mov     rbp, [rsp+48h+arg_8]
0x140004c1c  mov     rsi, [rsp+48h+arg_10]
0x140004c21  add     rsp, 30h
0x140004c25  pop     r15
0x140004c27  pop     r14
0x140004c29  pop     rdi
0x140004c2a  retn
0x140004c2b  mov     rcx, rbx; Block
0x140004c2e  call    unknown_libname_11; Microsoft VisualC 64bit universal runtime
0x140004c33  xor     ecx, ecx; Block
0x140004c35  call    _free_base
0x140004c3a  jmp     loc_140004B9F
0x140004c3f  xor     r9d, r9d; LineNo
0x140004c42  mov     [rsp+48h+Reserved], rbp; Reserved
0x140004c47  xor     r8d, r8d; FileName
0x140004c4a  xor     edx, edx; FunctionName
0x140004c4c  call    _invoke_watson
```
