# AipSetTrustedPublisherNameInCache

- ea: `0x1400270f4`
- end: `0x1400272a2`
- name: `AipSetTrustedPublisherNameInCache`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140025560`
- `0x140026fd0`

## callees

- `0x140006c40`
- `0x140006f40`
- `0x1400270f4`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140027271`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140027271`

## pseudocode

```c
__int64 __fastcall AipSetTrustedPublisherNameInCache(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, _QWORD *a5)
{
  char *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rsi
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  char *v13; // rax

  v8 = 0;
  v9 = **(_DWORD **)(*(_QWORD *)(a2 + 16) + 8LL);
  if ( v9 > 0xFFFF )
    goto LABEL_22;
  v10 = a4 + 16;
  if ( *a3 )
  {
    if ( **(_DWORD **)(*(_QWORD *)v10 + 8LL) > 0xFFFFu )
      goto LABEL_22;
  }
  if ( !v9 )
  {
    if ( *a5 )
    {
      v11 = 72;
      goto LABEL_8;
    }
LABEL_22:
    v12 = -1073741811;
    goto LABEL_23;
  }
  v11 = v9 + 72;
  if ( v11 < 0x48 )
    goto LABEL_12;
LABEL_8:
  if ( !*a3 )
    goto LABEL_11;
  if ( v11 + **(_DWORD **)(*(_QWORD *)(a4 + 16) + 8LL) < v11 )
  {
LABEL_12:
    v12 = -1073741675;
    goto LABEL_23;
  }
  v11 += **(_DWORD **)(*(_QWORD *)(a4 + 16) + 8LL);
LABEL_11:
  if ( v11 > 0x1000 )
    goto LABEL_12;
  v13 = (char *)AiAlloc(v11);
  v8 = v13;
  if ( v13 )
  {
    memset(v13, 0, v11);
    v8[5] = 30;
    *((_WORD *)v8 + 3) = v11 - 39;
    strcpy(v8 + 8, "$KERNEL.PURGE.APPID.SIGNERINFO");
    *((_DWORD *)v8 + 10) = 860113217;
    *((_WORD *)v8 + 24) = **(_WORD **)(*(_QWORD *)(a2 + 16) + 8LL);
    if ( *a3 )
      *((_WORD *)v8 + 25) = **(_WORD **)(*(_QWORD *)v10 + 8LL);
    *((_QWORD *)v8 + 7) = *a3;
    memmove(
      v8 + 72,
      *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 16) + 8LL) + 8LL),
      **(unsigned int **)(*(_QWORD *)(a2 + 16) + 8LL));
    if ( *((_WORD *)v8 + 25) )
      memmove(
        &v8[*((unsigned __int16 *)v8 + 24) + 72],
        *(const void **)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 8LL),
        **(unsigned int **)(*(_QWORD *)v10 + 8LL));
    if ( a5 )
      *((_QWORD *)v8 + 8) = *a5;
    v12 = FsRtlSetKernelEaFile(a1, v8, *((unsigned __int16 *)v8 + 3) + 9 + (unsigned int)(unsigned __int8)v8[5]);
  }
  else
  {
    v12 = -1073741801;
  }
LABEL_23:
  AiFree(v8);
  return v12;
}

```

## disassembly

```asm
0x1400270f4  push    rbx
0x1400270f6  push    rbp
0x1400270f7  push    rsi
0x1400270f8  push    rdi
0x1400270f9  push    r12
0x1400270fb  push    r13
0x1400270fd  push    r14
0x1400270ff  push    r15
0x140027101  sub     rsp, 28h
0x140027105  mov     r13, rdx
0x140027108  mov     r15, r8
0x14002710b  xor     edx, edx
0x14002710d  mov     r8d, 0FFFFh
0x140027113  mov     r11, r9
0x140027116  mov     r12, rcx
0x140027119  mov     edi, edx
0x14002711b  mov     rax, [r13+10h]
0x14002711f  mov     r10, [rax+8]
0x140027123  mov     ebx, [r10]
0x140027126  cmp     ebx, r8d
0x140027129  ja      loc_140027281
0x14002712f  mov     r9, [r15]
0x140027132  lea     rsi, [r11+10h]
0x140027136  test    r9, r9
0x140027139  jz      short loc_14002714B
0x14002713b  mov     rax, [rsi]
0x14002713e  mov     rcx, [rax+8]
0x140027142  cmp     [rcx], r8d
0x140027145  ja      loc_140027281
0x14002714b  mov     r14, [rsp+68h+arg_20]
0x140027153  test    ebx, ebx
0x140027155  jnz     short loc_140027167
0x140027157  cmp     [r14], rdx
0x14002715a  jz      loc_140027281
0x140027160  mov     ebx, 48h ; 'H'
0x140027165  jmp     short loc_14002716F
0x140027167  add     ebx, 48h ; 'H'
0x14002716a  cmp     ebx, 48h ; 'H'
0x14002716d  jb      short loc_14002718E
0x14002716f  test    r9, r9
0x140027172  jz      short loc_140027186
0x140027174  mov     rax, [r11+10h]
0x140027178  mov     rcx, [rax+8]
0x14002717c  mov     ecx, [rcx]
0x14002717e  add     ecx, ebx
0x140027180  cmp     ecx, ebx
0x140027182  jb      short loc_14002718E
0x140027184  mov     ebx, ecx
0x140027186  cmp     ebx, 1000h
0x14002718c  jbe     short loc_140027198
0x14002718e  mov     ebx, 0C0000095h
0x140027193  jmp     loc_140027286
0x140027198  mov     ecx, ebx
0x14002719a  mov     ebp, ebx
0x14002719c  call    AiAlloc
0x1400271a1  mov     rdi, rax
0x1400271a4  test    rax, rax
0x1400271a7  jnz     short loc_1400271B3
0x1400271a9  mov     ebx, 0C0000017h
0x1400271ae  jmp     loc_140027286
0x1400271b3  mov     r8, rbp; Size
0x1400271b6  xor     edx, edx; Val
0x1400271b8  mov     rcx, rdi; void *
0x1400271bb  call    memset
0x1400271c0  mov     byte ptr [rdi+5], 1Eh
0x1400271c4  sub     bx, 27h ; '''
0x1400271c8  mov     [rdi+6], bx
0x1400271cc  xor     ebp, ebp
0x1400271ce  movups  xmm0, xmmword ptr cs:aKernelPurgeApp_1; "$KERNEL.PURGE.APPID.SIGNERINFO"
0x1400271d5  movups  xmmword ptr [rdi+8], xmm0
0x1400271d9  movups  xmm1, xmmword ptr cs:aKernelPurgeApp_1+0Fh; "PPID.SIGNERINFO"
0x1400271e0  mov     dword ptr [rdi+28h], 33444941h
0x1400271e7  movups  xmmword ptr [rdi+17h], xmm1
0x1400271eb  mov     rax, [r13+10h]
0x1400271ef  mov     rcx, [rax+8]
0x1400271f3  movzx   eax, word ptr [rcx]
0x1400271f6  mov     [rdi+30h], ax
0x1400271fa  cmp     [r15], rbp
0x1400271fd  jz      short loc_14002720D
0x1400271ff  mov     rax, [rsi]
0x140027202  mov     rcx, [rax+8]
0x140027206  movzx   eax, word ptr [rcx]
0x140027209  mov     [rdi+32h], ax
0x14002720d  mov     rax, [r15]
0x140027210  lea     rcx, [rdi+48h]; void *
0x140027214  mov     [rdi+38h], rax
0x140027218  mov     rax, [r13+10h]
0x14002721c  mov     rdx, [rax+8]
0x140027220  mov     r8d, [rdx]; Size
0x140027223  mov     rdx, [rdx+8]; Src
0x140027227  call    memmove
0x14002722c  cmp     [rdi+32h], bp
0x140027230  jz      short loc_140027250
0x140027232  mov     rax, [rsi]
0x140027235  movzx   ecx, word ptr [rdi+30h]
0x140027239  add     rcx, 48h ; 'H'
0x14002723d  add     rcx, rdi; void *
0x140027240  mov     rdx, [rax+8]
0x140027244  mov     r8d, [rdx]; Size
0x140027247  mov     rdx, [rdx+8]; Src
0x14002724b  call    memmove
0x140027250  test    r14, r14
0x140027253  jz      short loc_14002725C
0x140027255  mov     rax, [r14]
0x140027258  mov     [rdi+40h], rax
0x14002725c  movzx   ecx, word ptr [rdi+6]
0x140027260  mov     rdx, rdi
0x140027263  movzx   r8d, byte ptr [rdi+5]
0x140027268  add     ecx, 9
0x14002726b  add     r8d, ecx
0x14002726e  mov     rcx, r12
0x140027271  call    cs:__imp_FsRtlSetKernelEaFile
0x140027278  nop     dword ptr [rax+rax+00h]
0x14002727d  mov     ebx, eax
0x14002727f  jmp     short loc_140027286
0x140027281  mov     ebx, 0C000000Dh
0x140027286  mov     rcx, rdi
0x140027289  call    AiFree
0x14002728e  mov     eax, ebx
0x140027290  add     rsp, 28h
0x140027294  pop     r15
0x140027296  pop     r14
0x140027298  pop     r13
0x14002729a  pop     r12
0x14002729c  pop     rdi
0x14002729d  pop     rsi
0x14002729e  pop     rbp
0x14002729f  pop     rbx
0x1400272a0  retn
```
