# UlStripWhitespace

- ea: `0x180010460`
- end: `0x18001052f`
- name: `UlStripWhitespace`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fc80`
- `0x180010460`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x1800104ec`
- `KERNEL32!RtlMoveMemory` at `0x1800104ec`

## pseudocode

```c
__int64 __fastcall UlStripWhitespace(const CHAR *a1, int a2, int a3, _DWORD *a4)
{
  __int64 v4; // r10
  unsigned __int64 v8; // rbx
  const CHAR *v10; // rdi
  unsigned int v11; // ebp
  const CHAR *i; // rdi

  v4 = -1;
  if ( a4 )
  {
    v8 = (unsigned int)*a4;
    a1[v8] = 0;
    do
      ++v4;
    while ( a1[v4] );
    if ( v8 > v4 + 1 )
      LODWORD(v8) = v4;
  }
  else
  {
    do
      ++v4;
    while ( a1[v4] );
    LODWORD(v8) = v4;
  }
  if ( (_DWORD)v8 )
  {
    if ( !a2 )
      goto LABEL_18;
  }
  else if ( !a2 )
  {
    if ( !a3 )
      return 0;
    goto LABEL_19;
  }
  v10 = a1;
  if ( (unsigned int)FIsSpaceA(a1) )
  {
    do
    {
      ++v10;
      v11 = v8;
      LODWORD(v8) = v8 - 1;
    }
    while ( (unsigned int)FIsSpaceA(v10) );
    if ( v10 != a1 )
      RtlMoveMemory(a1, v10, v11);
  }
LABEL_18:
  if ( a3 )
  {
LABEL_19:
    for ( i = &a1[(unsigned int)v8]; (_DWORD)v8; LODWORD(v8) = v8 - 1 )
    {
      if ( !(unsigned int)FIsSpaceA(i - 1) )
        break;
      --i;
    }
    *i = 0;
  }
  if ( a4 )
    *a4 = v8;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010460  push    rbx
0x180010462  push    rbp
0x180010463  push    rsi
0x180010464  push    rdi
0x180010465  push    r14
0x180010467  push    r15
0x180010469  sub     rsp, 28h
0x18001046d  or      r10, 0FFFFFFFFFFFFFFFFh
0x180010471  mov     r14, r9
0x180010474  mov     r15d, r8d
0x180010477  mov     rsi, rcx
0x18001047a  test    r9, r9
0x18001047d  jz      short loc_18001049D
0x18001047f  mov     ebx, [r9]
0x180010482  mov     byte ptr [rbx+rcx], 0
0x180010486  inc     r10
0x180010489  cmp     byte ptr [rcx+r10], 0
0x18001048e  jnz     short loc_180010486
0x180010490  lea     rax, [r10+1]
0x180010494  cmp     rbx, rax
0x180010497  cmova   ebx, r10d
0x18001049b  jmp     short loc_1800104AA
0x18001049d  inc     r10
0x1800104a0  cmp     byte ptr [rcx+r10], 0
0x1800104a5  jnz     short loc_18001049D
0x1800104a7  mov     ebx, r10d
0x1800104aa  test    ebx, ebx
0x1800104ac  jnz     short loc_1800104BB
0x1800104ae  test    edx, edx
0x1800104b0  jnz     short loc_1800104BF
0x1800104b2  test    r15d, r15d
0x1800104b5  jnz     short loc_1800104F7
0x1800104b7  xor     eax, eax
0x1800104b9  jmp     short loc_180010522
0x1800104bb  test    edx, edx
0x1800104bd  jz      short loc_1800104F2
0x1800104bf  mov     rdi, rsi
0x1800104c2  call    FIsSpaceA
0x1800104c7  test    eax, eax
0x1800104c9  jz      short loc_1800104F2
0x1800104cb  inc     rdi
0x1800104ce  mov     ebp, ebx
0x1800104d0  mov     rcx, rdi; lpSrcStr
0x1800104d3  dec     ebx
0x1800104d5  call    FIsSpaceA
0x1800104da  test    eax, eax
0x1800104dc  jnz     short loc_1800104CB
0x1800104de  cmp     rdi, rsi
0x1800104e1  jz      short loc_1800104F2
0x1800104e3  mov     r8d, ebp
0x1800104e6  mov     rdx, rdi
0x1800104e9  mov     rcx, rsi
0x1800104ec  call    cs:__imp_RtlMoveMemory
0x1800104f2  test    r15d, r15d
0x1800104f5  jz      short loc_180010518
0x1800104f7  mov     edi, ebx
0x1800104f9  add     rdi, rsi
0x1800104fc  test    ebx, ebx
0x1800104fe  jz      short loc_180010515
0x180010500  lea     rcx, [rdi-1]; lpSrcStr
0x180010504  call    FIsSpaceA
0x180010509  test    eax, eax
0x18001050b  jz      short loc_180010515
0x18001050d  dec     rdi
0x180010510  add     ebx, 0FFFFFFFFh
0x180010513  jnz     short loc_180010500
0x180010515  mov     byte ptr [rdi], 0
0x180010518  test    r14, r14
0x18001051b  jz      short loc_180010520
0x18001051d  mov     [r14], ebx
0x180010520  mov     eax, ebx
0x180010522  add     rsp, 28h
0x180010526  pop     r15
0x180010528  pop     r14
0x18001052a  pop     rdi
0x18001052b  pop     rsi
0x18001052c  pop     rbp
0x18001052d  pop     rbx
0x18001052e  retn
```
