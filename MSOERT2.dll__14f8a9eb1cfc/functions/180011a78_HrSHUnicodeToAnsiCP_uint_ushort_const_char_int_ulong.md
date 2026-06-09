# HrSHUnicodeToAnsiCP(uint,ushort const *,char *,int,ulong *)

- ea: `0x180011a78`
- end: `0x180011b63`
- name: `?HrSHUnicodeToAnsiCP@@YAJIPEBGPEADHPEAK@Z`
- size: `235`
- prototype: `int(unsigned int, const unsigned __int16 *, char *, int, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180003f80`
- `0x180006ac0`
- `0x180009a50`
- `0x18001232c`

## callees

- `0x180011a78`
- `0x180012554`
- `0x180012650`
- `0x180012f8e`

## pseudocode

```c
__int64 __fastcall HrSHUnicodeToAnsiCP(DWORD a1, const unsigned __int16 *a2, char *a3, int a4, unsigned int *a5)
{
  size_t v5; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // eax

  v5 = a4;
  v7 = -2147024809;
  if ( !a2 || !a3 || !a4 || !a5 )
    return v7;
  v8 = -1;
  *a5 = 0;
  v9 = -1;
  *a3 = 0;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  if ( a1 == 1200 )
  {
    a1 = 65001;
LABEL_12:
    v11 = OESHUnicodeToAnsiInetCP(a1, a2, v10, a3, a4);
    goto LABEL_13;
  }
  if ( a1 == 50000 || a1 - 65000 < 2 )
    goto LABEL_12;
  v11 = OESHUnicodeToAnsiNativeCP(a1, a2, v10, a3, a4);
LABEL_13:
  if ( !v11 )
  {
    v7 = -2147467259;
    goto LABEL_19;
  }
  do
    ++v8;
  while ( a3[v8] );
  if ( (int)v8 + 10 > (int)v5 )
  {
    v7 = -2147024774;
LABEL_19:
    memset_0(a3, 0, v5);
    return v7;
  }
  memset_0(&a3[(unsigned int)v8], 0, (unsigned int)(v5 - v8));
  *a5 = v8;
  return 0;
}

```

## disassembly

```asm
0x180011a78  push    rbx
0x180011a7a  push    rbp
0x180011a7b  push    rsi
0x180011a7c  push    rdi
0x180011a7d  push    r14
0x180011a7f  sub     rsp, 30h
0x180011a83  xor     ebp, ebp
0x180011a85  movsxd  rdi, r9d
0x180011a88  mov     rsi, r8
0x180011a8b  mov     ebx, 80070057h
0x180011a90  test    rdx, rdx
0x180011a93  jz      loc_180011B56
0x180011a99  test    r8, r8
0x180011a9c  jz      loc_180011B56
0x180011aa2  test    r9d, r9d
0x180011aa5  jz      loc_180011B56
0x180011aab  mov     r14, [rsp+58h+arg_20]
0x180011ab3  test    r14, r14
0x180011ab6  jz      loc_180011B56
0x180011abc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011ac0  mov     [r14], ebp
0x180011ac3  mov     rax, rbx
0x180011ac6  mov     [r8], bpl
0x180011ac9  inc     rax
0x180011acc  cmp     [rdx+rax*2], bp
0x180011ad0  jnz     short loc_180011AC9
0x180011ad2  lea     r8d, [rax+1]; int
0x180011ad6  mov     eax, ecx
0x180011ad8  sub     eax, 4B0h
0x180011add  jz      short loc_180011B00
0x180011adf  sub     eax, 0BEA0h
0x180011ae4  jz      short loc_180011B05
0x180011ae6  sub     eax, 3A98h
0x180011aeb  jz      short loc_180011B05
0x180011aed  cmp     eax, 1
0x180011af0  jz      short loc_180011B05
0x180011af2  mov     r9, rsi; char *
0x180011af5  mov     [rsp+58h+var_38], edi; int
0x180011af9  call    ?OESHUnicodeToAnsiNativeCP@@YAHIPEBGHPEADH@Z; OESHUnicodeToAnsiNativeCP(uint,ushort const *,int,char *,int)
0x180011afe  jmp     short loc_180011B11
0x180011b00  mov     ecx, 0FDE9h; dwEncoding
0x180011b05  mov     r9, rsi; char *
0x180011b08  mov     [rsp+58h+var_38], edi; int
0x180011b0c  call    ?OESHUnicodeToAnsiInetCP@@YAHIPEBGHPEADH@Z; OESHUnicodeToAnsiInetCP(uint,ushort const *,int,char *,int)
0x180011b11  test    eax, eax
0x180011b13  jz      short loc_180011B44
0x180011b15  inc     rbx
0x180011b18  cmp     [rsi+rbx], bpl
0x180011b1c  jnz     short loc_180011B15
0x180011b1e  lea     eax, [rbx+0Ah]
0x180011b21  cmp     eax, edi
0x180011b23  jle     short loc_180011B2C
0x180011b25  mov     ebx, 8007007Ah
0x180011b2a  jmp     short loc_180011B49
0x180011b2c  sub     edi, ebx
0x180011b2e  mov     ecx, ebx
0x180011b30  mov     r8d, edi; Size
0x180011b33  add     rcx, rsi; void *
0x180011b36  xor     edx, edx; Val
0x180011b38  call    memset_0
0x180011b3d  mov     [r14], ebx
0x180011b40  mov     ebx, ebp
0x180011b42  jmp     short loc_180011B56
0x180011b44  mov     ebx, 80004005h
0x180011b49  mov     r8, rdi; Size
0x180011b4c  xor     edx, edx; Val
0x180011b4e  mov     rcx, rsi; void *
0x180011b51  call    memset_0
0x180011b56  mov     eax, ebx
0x180011b58  add     rsp, 30h
0x180011b5c  pop     r14
0x180011b5e  pop     rdi
0x180011b5f  pop     rsi
0x180011b60  pop     rbp
0x180011b61  pop     rbx
0x180011b62  retn
```
