# AiSetUninstallStringEa

- ea: `0x140021634`
- end: `0x1400216d6`
- name: `AiSetUninstallStringEa`
- size: `162`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140020db4`

## callees

- `0x140006c40`
- `0x140021634`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!FsRtlSetKernelEaFile` at `0x1400216b4`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x1400216b4`

## pseudocode

```c
__int64 __fastcall AiSetUninstallStringEa(__int64 a1, const void *a2, unsigned int a3)
{
  size_t v3; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  unsigned int v9; // ebx

  v3 = a3;
  v6 = AiAlloc(a3 + 45);
  v7 = v6;
  if ( !v6 )
    return 3221225495LL;
  *(_DWORD *)v6 = 0;
  *(_WORD *)(v6 + 4) = 9216;
  *(_WORD *)(v6 + 6) = v3;
  strcpy((char *)(v6 + 8), "$Kernel.Smartlocker.UninstallStrings");
  memmove((void *)(v6 + 45), a2, v3);
  v9 = FsRtlSetKernelEaFile(a1, v7, *(unsigned __int8 *)(v7 + 5) + 9 + (unsigned int)*(unsigned __int16 *)(v7 + 6));
  AiFree((void *)v7);
  return v9;
}

```

## disassembly

```asm
0x140021634  push    rbx
0x140021636  push    rbp
0x140021637  push    rsi
0x140021638  push    rdi
0x140021639  sub     rsp, 28h
0x14002163d  mov     ebx, r8d
0x140021640  mov     rbp, rcx
0x140021643  mov     rsi, rdx
0x140021646  lea     ecx, [rbx+2Dh]
0x140021649  call    AiAlloc
0x14002164e  mov     rdi, rax
0x140021651  test    rax, rax
0x140021654  jnz     short loc_14002165D
0x140021656  mov     eax, 0C0000017h
0x14002165b  jmp     short loc_1400216CC
0x14002165d  mov     dword ptr [rax], 0
0x140021663  lea     rcx, [rax+2Dh]; void *
0x140021667  mov     word ptr [rax+4], 2400h
0x14002166d  mov     r8, rbx; Size
0x140021670  mov     [rax+6], bx
0x140021674  mov     rdx, rsi; Src
0x140021677  movups  xmm0, cs:xmmword_14000AC80
0x14002167e  movups  xmmword ptr [rax+8], xmm0
0x140021682  movups  xmm1, cs:xmmword_14000AC90
0x140021689  movups  xmmword ptr [rax+18h], xmm1
0x14002168d  movsd   xmm0, qword ptr cs:xmmword_14000AC90+0Dh
0x140021695  movsd   qword ptr [rax+25h], xmm0
0x14002169a  call    memmove
0x14002169f  movzx   ecx, byte ptr [rdi+5]
0x1400216a3  mov     rdx, rdi
0x1400216a6  movzx   r8d, word ptr [rdi+6]
0x1400216ab  add     ecx, 9
0x1400216ae  add     r8d, ecx
0x1400216b1  mov     rcx, rbp
0x1400216b4  call    cs:__imp_FsRtlSetKernelEaFile
0x1400216bb  nop     dword ptr [rax+rax+00h]
0x1400216c0  mov     ebx, eax
0x1400216c2  mov     rcx, rdi
0x1400216c5  call    AiFree
0x1400216ca  mov     eax, ebx
0x1400216cc  add     rsp, 28h
0x1400216d0  pop     rdi
0x1400216d1  pop     rsi
0x1400216d2  pop     rbp
0x1400216d3  pop     rbx
0x1400216d4  retn
```
