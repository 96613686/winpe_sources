# AipSetVersionInfoInCache

- ea: `0x14002b084`
- end: `0x14002b1d2`
- name: `AipSetVersionInfoInCache`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002a840`

## callees

- `0x140006c40`
- `0x140006f40`
- `0x14002b084`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x14002b1a4`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x14002b1a4`

## pseudocode

```c
__int64 __fastcall AipSetVersionInfoInCache(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        const void **a6,
        const void **a7)
{
  unsigned int v9; // ebp
  char *v10; // rbx
  unsigned int v11; // edi
  char *v12; // rax

  v9 = *(unsigned __int16 *)a6 + *(unsigned __int16 *)a7 + 64;
  if ( v9 <= 0x2000 )
  {
    v12 = (char *)AiAlloc(v9);
    v10 = v12;
    if ( v12 )
    {
      memset(v12, 0, v9);
      *((_WORD *)v10 + 3) = v9 - 40;
      v10[5] = 31;
      strcpy(v10 + 8, "$KERNEL.PURGE.APPID.VERSIONINFO");
      *((_DWORD *)v10 + 11) = a2;
      *((_DWORD *)v10 + 12) = a3;
      *((_DWORD *)v10 + 14) = a5;
      *((_DWORD *)v10 + 10) = 826558785;
      *((_DWORD *)v10 + 13) = a4;
      *((_WORD *)v10 + 30) = *(_WORD *)a6;
      *((_WORD *)v10 + 31) = *(_WORD *)a7;
      if ( *(_WORD *)a6 )
        memmove(v10 + 64, a6[1], *(unsigned __int16 *)a6);
      if ( *(_WORD *)a7 )
        memmove(&v10[*(unsigned __int16 *)a6 + 64], a7[1], *(unsigned __int16 *)a7);
      v11 = FsRtlSetKernelEaFile(a1, v10, *((unsigned __int16 *)v10 + 3) + 9 + (unsigned int)(unsigned __int8)v10[5]);
    }
    else
    {
      v11 = -1073741801;
    }
  }
  else
  {
    v10 = 0;
    v11 = -1073741562;
  }
  AiFree(v10);
  return v11;
}

```

## disassembly

```asm
0x14002b084  mov     [rsp+arg_0], rbx
0x14002b089  mov     [rsp+arg_10], r8d
0x14002b08e  mov     [rsp+arg_8], edx
0x14002b092  push    rbp
0x14002b093  push    rsi
0x14002b094  push    rdi
0x14002b095  push    r12
0x14002b097  push    r13
0x14002b099  push    r14
0x14002b09b  push    r15
0x14002b09d  sub     rsp, 20h
0x14002b0a1  mov     r14, [rsp+58h+arg_30]
0x14002b0a9  mov     r13d, r9d
0x14002b0ac  mov     rsi, [rsp+58h+arg_28]
0x14002b0b4  mov     r12, rcx
0x14002b0b7  movzx   ebp, word ptr [r14]
0x14002b0bb  movzx   r10d, word ptr [rsi]
0x14002b0bf  add     ebp, 40h ; '@'
0x14002b0c2  add     ebp, r10d
0x14002b0c5  cmp     ebp, 2000h
0x14002b0cb  jbe     short loc_14002B0DB
0x14002b0cd  xor     edi, edi
0x14002b0cf  mov     ebx, edi
0x14002b0d1  mov     edi, 0C0000106h
0x14002b0d6  jmp     loc_14002B1B2
0x14002b0db  mov     ecx, ebp
0x14002b0dd  mov     r15d, ebp
0x14002b0e0  call    AiAlloc
0x14002b0e5  mov     rbx, rax
0x14002b0e8  test    rax, rax
0x14002b0eb  jnz     short loc_14002B0F7
0x14002b0ed  mov     edi, 0C0000017h
0x14002b0f2  jmp     loc_14002B1B2
0x14002b0f7  mov     r8, r15; Size
0x14002b0fa  xor     edx, edx; Val
0x14002b0fc  mov     rcx, rbx; void *
0x14002b0ff  call    memset
0x14002b104  mov     eax, [rsp+58h+arg_8]
0x14002b108  sub     bp, 28h ; '('
0x14002b10c  mov     [rbx+6], bp
0x14002b110  mov     byte ptr [rbx+5], 1Fh
0x14002b114  movups  xmm0, xmmword ptr cs:aKernelPurgeApp_0; "$KERNEL.PURGE.APPID.VERSIONINFO"
0x14002b11b  movups  xmmword ptr [rbx+8], xmm0
0x14002b11f  movups  xmm1, xmmword ptr cs:aKernelPurgeApp_0+10h; "PID.VERSIONINFO"
0x14002b126  mov     [rbx+2Ch], eax
0x14002b129  mov     eax, [rsp+58h+arg_10]
0x14002b12d  mov     [rbx+30h], eax
0x14002b130  mov     eax, [rsp+58h+arg_20]
0x14002b137  mov     [rbx+38h], eax
0x14002b13a  movups  xmmword ptr [rbx+18h], xmm1
0x14002b13e  mov     dword ptr [rbx+28h], 31444941h
0x14002b145  mov     [rbx+34h], r13d
0x14002b149  movzx   eax, word ptr [rsi]
0x14002b14c  mov     [rbx+3Ch], ax
0x14002b150  movzx   eax, word ptr [r14]
0x14002b154  mov     [rbx+3Eh], ax
0x14002b158  movzx   eax, word ptr [rsi]
0x14002b15b  test    ax, ax
0x14002b15e  jz      short loc_14002B170
0x14002b160  mov     rdx, [rsi+8]; Src
0x14002b164  lea     rcx, [rbx+40h]; void *
0x14002b168  mov     r8d, eax; Size
0x14002b16b  call    memmove
0x14002b170  movzx   eax, word ptr [r14]
0x14002b174  test    ax, ax
0x14002b177  jz      short loc_14002B18F
0x14002b179  movzx   ecx, word ptr [rsi]
0x14002b17c  mov     r8d, eax; Size
0x14002b17f  mov     rdx, [r14+8]; Src
0x14002b183  add     rcx, 40h ; '@'
0x14002b187  add     rcx, rbx; void *
0x14002b18a  call    memmove
0x14002b18f  movzx   edx, word ptr [rbx+6]
0x14002b193  mov     rcx, r12
0x14002b196  movzx   r8d, byte ptr [rbx+5]
0x14002b19b  add     edx, 9
0x14002b19e  add     r8d, edx
0x14002b1a1  mov     rdx, rbx
0x14002b1a4  call    cs:__imp_FsRtlSetKernelEaFile
0x14002b1ab  nop     dword ptr [rax+rax+00h]
0x14002b1b0  mov     edi, eax
0x14002b1b2  mov     rcx, rbx
0x14002b1b5  call    AiFree
0x14002b1ba  mov     rbx, [rsp+58h+arg_0]
0x14002b1bf  mov     eax, edi
0x14002b1c1  add     rsp, 20h
0x14002b1c5  pop     r15
0x14002b1c7  pop     r14
0x14002b1c9  pop     r13
0x14002b1cb  pop     r12
0x14002b1cd  pop     rdi
0x14002b1ce  pop     rsi
0x14002b1cf  pop     rbp
0x14002b1d0  retn
```
