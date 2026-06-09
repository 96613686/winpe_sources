# GSCopyGraphicsState

- ea: `0x180011fa4`
- end: `0x180012083`
- name: `GSCopyGraphicsState`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f24`
- `0x18001597c`
- `0x18001ad28`

## callees

- `0x180011fa4`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180012029`
- `KERNEL32!LocalAlloc` at `0x180012029`

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
0x180011fa4  push    rbx
0x180011fa6  push    rbp
0x180011fa7  push    rsi
0x180011fa8  push    rdi
0x180011fa9  sub     rsp, 28h
0x180011fad  mov     rax, [rcx+2F0h]
0x180011fb4  mov     rbx, rdx
0x180011fb7  mov     rbp, rcx
0x180011fba  movups  xmm0, xmmword ptr [rax]
0x180011fbd  movups  xmmword ptr [rdx], xmm0
0x180011fc0  movups  xmm1, xmmword ptr [rax+10h]
0x180011fc4  movups  xmmword ptr [rdx+10h], xmm1
0x180011fc8  movups  xmm0, xmmword ptr [rax+20h]
0x180011fcc  movups  xmmword ptr [rdx+20h], xmm0
0x180011fd0  movups  xmm1, xmmword ptr [rax+30h]
0x180011fd4  movups  xmmword ptr [rdx+30h], xmm1
0x180011fd8  movups  xmm0, xmmword ptr [rax+40h]
0x180011fdc  movups  xmmword ptr [rdx+40h], xmm0
0x180011fe0  movups  xmm1, xmmword ptr [rax+50h]
0x180011fe4  movups  xmmword ptr [rdx+50h], xmm1
0x180011fe8  movups  xmm0, xmmword ptr [rax+60h]
0x180011fec  movups  xmmword ptr [rdx+60h], xmm0
0x180011ff0  movups  xmm1, xmmword ptr [rax+70h]
0x180011ff4  movups  xmmword ptr [rdx+70h], xmm1
0x180011ff8  mov     rax, [rax+80h]
0x180011fff  mov     [rdx+80h], rax
0x180012006  mov     rax, [rcx+2F0h]
0x18001200d  cmp     qword ptr [rax+28h], 0
0x180012012  jz      short loc_180012057
0x180012014  mov     edi, [rax+20h]
0x180012017  mov     eax, 0FFFFFFFFh
0x18001201c  shl     rdi, 2
0x180012020  cmp     rdi, rax
0x180012023  ja      short loc_180012066
0x180012025  mov     edx, edi; uBytes
0x180012027  xor     ecx, ecx; uFlags
0x180012029  call    cs:__imp_LocalAlloc
0x180012030  nop     dword ptr [rax+rax+00h]
0x180012035  mov     rsi, rax
0x180012038  test    rax, rax
0x18001203b  jz      short loc_180012066
0x18001203d  mov     rdx, [rbp+2F0h]
0x180012044  mov     r8, rdi; Size
0x180012047  mov     rcx, rax; void *
0x18001204a  mov     rdx, [rdx+28h]; Src
0x18001204e  call    memcpy_0
0x180012053  mov     [rbx+28h], rsi
0x180012057  mov     eax, 1
0x18001205c  add     rsp, 28h
0x180012060  pop     rdi
0x180012061  pop     rsi
0x180012062  pop     rbp
0x180012063  pop     rbx
0x180012064  retn
0x180012066  mov     qword ptr [rbx+28h], 0
0x18001206e  xor     eax, eax
0x180012070  mov     dword ptr [rbx+20h], 0
0x180012077  mov     dword ptr [rbp+0D70h], 1
0x180012081  jmp     short loc_18001205C
```
