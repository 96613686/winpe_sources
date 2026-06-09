# AiSetSigningLevelCache

- ea: `0x140026088`
- end: `0x140026139`
- name: `AiSetSigningLevelCache`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140023934`
- `0x14002d5d4`

## callees

- `0x14000212c`
- `0x140026088`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140026117`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x140026117`

## pseudocode

```c
__int64 __fastcall AiSetSigningLevelCache(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rdi
  unsigned int v6; // ebx
  int v7; // [rsp+58h] [rbp+10h] BYREF

  v7 = 0;
  v2 = AiAlloc(4096);
  v4 = v2;
  if ( !v2 )
    return 3221225495LL;
  if ( (int)AiGetPublisherCache(a1, v3, v2, &v7) < 0 )
  {
    *(_OWORD *)v4 = 0;
    *(_OWORD *)(v4 + 16) = 0;
    *(_OWORD *)(v4 + 32) = 0;
    *(_BYTE *)(v4 + 5) = 30;
    *(_WORD *)(v4 + 6) = 9;
    strcpy((char *)(v4 + 8), "$KERNEL.PURGE.APPID.SIGNERINFO");
    *(_DWORD *)(v4 + 40) = 860113217;
  }
  *(_DWORD *)(v4 + 44) |= 1u;
  v6 = FsRtlSetKernelEaFile(a1, v4, *(unsigned __int16 *)(v4 + 6) + 9 + (unsigned int)*(unsigned __int8 *)(v4 + 5));
  AiFree(v4);
  return v6;
}

```

## disassembly

```asm
0x140026088  push    rbx
0x14002608a  push    rbp
0x14002608b  push    rsi
0x14002608c  push    rdi
0x14002608d  sub     rsp, 28h
0x140026091  mov     rbp, rcx
0x140026094  mov     [rsp+48h+arg_8], 0
0x14002609c  mov     ecx, 1000h
0x1400260a1  call    AiAlloc
0x1400260a6  mov     rdi, rax
0x1400260a9  test    rax, rax
0x1400260ac  jnz     short loc_1400260B5
0x1400260ae  mov     eax, 0C0000017h
0x1400260b3  jmp     short loc_14002612F
0x1400260b5  lea     r9, [rsp+48h+arg_8]
0x1400260ba  mov     r8, rdi
0x1400260bd  mov     rcx, rbp
0x1400260c0  call    AiGetPublisherCache
0x1400260c5  test    eax, eax
0x1400260c7  jns     short loc_1400260FE
0x1400260c9  xorps   xmm0, xmm0
0x1400260cc  movups  xmmword ptr [rdi], xmm0
0x1400260cf  movups  xmmword ptr [rdi+10h], xmm0
0x1400260d3  movups  xmmword ptr [rdi+20h], xmm0
0x1400260d7  mov     byte ptr [rdi+5], 1Eh
0x1400260db  mov     word ptr [rdi+6], 9
0x1400260e1  movups  xmm0, xmmword ptr cs:aKernelPurgeApp_1; "$KERNEL.PURGE.APPID.SIGNERINFO"
0x1400260e8  movups  xmmword ptr [rdi+8], xmm0
0x1400260ec  movups  xmm1, xmmword ptr cs:aKernelPurgeApp_1+0Fh; "PPID.SIGNERINFO"
0x1400260f3  mov     dword ptr [rdi+28h], 33444941h
0x1400260fa  movups  xmmword ptr [rdi+17h], xmm1
0x1400260fe  or      dword ptr [rdi+2Ch], 1
0x140026102  mov     rdx, rdi
0x140026105  movzx   ecx, word ptr [rdi+6]
0x140026109  movzx   r8d, byte ptr [rdi+5]
0x14002610e  add     ecx, 9
0x140026111  add     r8d, ecx
0x140026114  mov     rcx, rbp
0x140026117  call    cs:__imp_FsRtlSetKernelEaFile
0x14002611e  nop     dword ptr [rax+rax+00h]
0x140026123  mov     rcx, rdi
0x140026126  mov     ebx, eax
0x140026128  call    AiFree
0x14002612d  mov     eax, ebx
0x14002612f  add     rsp, 28h
0x140026133  pop     rdi
0x140026134  pop     rsi
0x140026135  pop     rbp
0x140026136  pop     rbx
0x140026137  retn
```
