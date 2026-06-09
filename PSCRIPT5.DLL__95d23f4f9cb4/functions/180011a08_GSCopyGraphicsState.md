# GSCopyGraphicsState

- ea: `0x180011a08`
- end: `0x180011ae0`
- name: `GSCopyGraphicsState`
- size: `216`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011990`
- `0x180015264`
- `0x18001a404`

## callees

- `0x180011a08`
- `0x18005c434`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180011a8d`
- `KERNEL32!LocalAlloc` at `0x180011a8d`

## pseudocode

```c
__int64 __fastcall GSCopyGraphicsState(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v5; // rax
  size_t v6; // rdi
  HLOCAL v7; // rax
  HLOCAL v8; // rsi
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 752);
  *(_OWORD *)a2 = *(_OWORD *)v2;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(v2 + 16);
  *(_OWORD *)(a2 + 32) = *(_OWORD *)(v2 + 32);
  *(_OWORD *)(a2 + 48) = *(_OWORD *)(v2 + 48);
  *(_OWORD *)(a2 + 64) = *(_OWORD *)(v2 + 64);
  *(_OWORD *)(a2 + 80) = *(_OWORD *)(v2 + 80);
  *(_OWORD *)(a2 + 96) = *(_OWORD *)(v2 + 96);
  *(_OWORD *)(a2 + 112) = *(_OWORD *)(v2 + 112);
  *(_QWORD *)(a2 + 128) = *(_QWORD *)(v2 + 128);
  v5 = *(_QWORD *)(a1 + 752);
  if ( !*(_QWORD *)(v5 + 40) )
    return 1;
  v6 = 4LL * *(unsigned int *)(v5 + 32);
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = LocalAlloc(0, (unsigned int)v6);
    v8 = v7;
    if ( v7 )
    {
      memcpy_0(v7, *(const void **)(*(_QWORD *)(a1 + 752) + 40LL), v6);
      *(_QWORD *)(a2 + 40) = v8;
      return 1;
    }
  }
  *(_QWORD *)(a2 + 40) = 0;
  result = 0;
  *(_DWORD *)(a2 + 32) = 0;
  *(_DWORD *)(a1 + 3440) = 1;
  return result;
}

```

## disassembly

```asm
0x180011a08  push    rbx
0x180011a0a  push    rbp
0x180011a0b  push    rsi
0x180011a0c  push    rdi
0x180011a0d  sub     rsp, 28h
0x180011a11  mov     rax, [rcx+2F0h]
0x180011a18  mov     rbx, rdx
0x180011a1b  mov     rbp, rcx
0x180011a1e  movups  xmm0, xmmword ptr [rax]
0x180011a21  movups  xmmword ptr [rdx], xmm0
0x180011a24  movups  xmm1, xmmword ptr [rax+10h]
0x180011a28  movups  xmmword ptr [rdx+10h], xmm1
0x180011a2c  movups  xmm0, xmmword ptr [rax+20h]
0x180011a30  movups  xmmword ptr [rdx+20h], xmm0
0x180011a34  movups  xmm1, xmmword ptr [rax+30h]
0x180011a38  movups  xmmword ptr [rdx+30h], xmm1
0x180011a3c  movups  xmm0, xmmword ptr [rax+40h]
0x180011a40  movups  xmmword ptr [rdx+40h], xmm0
0x180011a44  movups  xmm1, xmmword ptr [rax+50h]
0x180011a48  movups  xmmword ptr [rdx+50h], xmm1
0x180011a4c  movups  xmm0, xmmword ptr [rax+60h]
0x180011a50  movups  xmmword ptr [rdx+60h], xmm0
0x180011a54  movups  xmm1, xmmword ptr [rax+70h]
0x180011a58  movups  xmmword ptr [rdx+70h], xmm1
0x180011a5c  mov     rax, [rax+80h]
0x180011a63  mov     [rdx+80h], rax
0x180011a6a  mov     rax, [rcx+2F0h]
0x180011a71  cmp     qword ptr [rax+28h], 0
0x180011a76  jz      short loc_180011AB5
0x180011a78  mov     edi, [rax+20h]
0x180011a7b  mov     eax, 0FFFFFFFFh
0x180011a80  shl     rdi, 2
0x180011a84  cmp     rdi, rax
0x180011a87  ja      short loc_180011AC3
0x180011a89  mov     edx, edi; uBytes
0x180011a8b  xor     ecx, ecx; uFlags
0x180011a8d  call    cs:__imp_LocalAlloc
0x180011a93  mov     rsi, rax
0x180011a96  test    rax, rax
0x180011a99  jz      short loc_180011AC3
0x180011a9b  mov     rdx, [rbp+2F0h]
0x180011aa2  mov     r8, rdi; Size
0x180011aa5  mov     rcx, rax; void *
0x180011aa8  mov     rdx, [rdx+28h]; Src
0x180011aac  call    memcpy_0
0x180011ab1  mov     [rbx+28h], rsi
0x180011ab5  mov     eax, 1
0x180011aba  add     rsp, 28h
0x180011abe  pop     rdi
0x180011abf  pop     rsi
0x180011ac0  pop     rbp
0x180011ac1  pop     rbx
0x180011ac2  retn
0x180011ac3  mov     qword ptr [rbx+28h], 0
0x180011acb  xor     eax, eax
0x180011acd  mov     dword ptr [rbx+20h], 0
0x180011ad4  mov     dword ptr [rbp+0D70h], 1
0x180011ade  jmp     short loc_180011ABA
```
