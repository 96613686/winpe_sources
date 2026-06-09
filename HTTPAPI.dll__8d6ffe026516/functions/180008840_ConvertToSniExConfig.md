# ConvertToSniExConfig

- ea: `0x180008840`
- end: `0x180008964`
- name: `ConvertToSniExConfig`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009280`

## callees

- `0x180008840`
- `0x18000a4c8`

## pseudocode

```c
__int64 __fastcall ConvertToSniExConfig(int a1, __int64 a2, unsigned int a3, _OWORD *a4)
{
  int v8; // esi
  int v9; // esi
  int v10; // esi

  memset_0(a4, 0, 0xA8u);
  v8 = a1 - 8;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
    {
LABEL_5:
      if ( a3 >= 0xA8 )
      {
        *a4 = *(_OWORD *)a2;
        a4[1] = *(_OWORD *)(a2 + 16);
        a4[2] = *(_OWORD *)(a2 + 32);
        a4[3] = *(_OWORD *)(a2 + 48);
        a4[4] = *(_OWORD *)(a2 + 64);
        a4[5] = *(_OWORD *)(a2 + 80);
        a4[6] = *(_OWORD *)(a2 + 96);
        a4[7] = *(_OWORD *)(a2 + 112);
        a4[8] = *(_OWORD *)(a2 + 128);
        a4[9] = *(_OWORD *)(a2 + 144);
        *((_QWORD *)a4 + 20) = *(_QWORD *)(a2 + 160);
        return 0;
      }
      return 87;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 2 )
        return 87;
      goto LABEL_5;
    }
  }
  if ( a3 >= 0xA0 )
  {
    *a4 = *(_OWORD *)a2;
    a4[1] = *(_OWORD *)(a2 + 16);
    a4[2] = *(_OWORD *)(a2 + 32);
    a4[3] = *(_OWORD *)(a2 + 48);
    a4[4] = *(_OWORD *)(a2 + 64);
    a4[5] = *(_OWORD *)(a2 + 80);
    a4[6] = *(_OWORD *)(a2 + 96);
    a4[7] = *(_OWORD *)(a2 + 112);
    *(_OWORD *)((char *)a4 + 136) = *(_OWORD *)(a2 + 128);
    *(_OWORD *)((char *)a4 + 152) = *(_OWORD *)(a2 + 144);
    return 0;
  }
  return 87;
}

```

## disassembly

```asm
0x180008840  push    rbx
0x180008842  push    rbp
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  sub     rsp, 28h
0x180008849  mov     ebp, r8d
0x18000884c  mov     rdi, rdx
0x18000884f  mov     esi, ecx
0x180008851  xor     edx, edx; Val
0x180008853  mov     r8d, 0A8h; Size
0x180008859  mov     rcx, r9; void *
0x18000885c  mov     rbx, r9
0x18000885f  call    memset_0
0x180008864  sub     esi, 8
0x180008867  jz      loc_1800088EE
0x18000886d  sub     esi, 1
0x180008870  jz      short loc_18000887C
0x180008872  sub     esi, 1
0x180008875  jz      short loc_1800088EE
0x180008877  cmp     esi, 2
0x18000887a  jnz     short loc_1800088F6
0x18000887c  cmp     ebp, 0A8h
0x180008882  jb      short loc_1800088F6
0x180008884  movups  xmm0, xmmword ptr [rdi]
0x180008887  movups  xmmword ptr [rbx], xmm0
0x18000888a  movups  xmm1, xmmword ptr [rdi+10h]
0x18000888e  movups  xmmword ptr [rbx+10h], xmm1
0x180008892  movups  xmm0, xmmword ptr [rdi+20h]
0x180008896  movups  xmmword ptr [rbx+20h], xmm0
0x18000889a  movups  xmm1, xmmword ptr [rdi+30h]
0x18000889e  movups  xmmword ptr [rbx+30h], xmm1
0x1800088a2  movups  xmm0, xmmword ptr [rdi+40h]
0x1800088a6  movups  xmmword ptr [rbx+40h], xmm0
0x1800088aa  movups  xmm1, xmmword ptr [rdi+50h]
0x1800088ae  movups  xmmword ptr [rbx+50h], xmm1
0x1800088b2  movups  xmm0, xmmword ptr [rdi+60h]
0x1800088b6  movups  xmmword ptr [rbx+60h], xmm0
0x1800088ba  movups  xmm1, xmmword ptr [rdi+70h]
0x1800088be  movups  xmmword ptr [rbx+70h], xmm1
0x1800088c2  movups  xmm0, xmmword ptr [rdi+80h]
0x1800088c9  movups  xmmword ptr [rbx+80h], xmm0
0x1800088d0  movups  xmm1, xmmword ptr [rdi+90h]
0x1800088d7  movups  xmmword ptr [rbx+90h], xmm1
0x1800088de  mov     rax, [rdi+0A0h]
0x1800088e5  mov     [rbx+0A0h], rax
0x1800088ec  jmp     short loc_180008957
0x1800088ee  cmp     ebp, 0A0h
0x1800088f4  jnb     short loc_1800088FD
0x1800088f6  mov     ecx, 57h ; 'W'
0x1800088fb  jmp     short loc_180008959
0x1800088fd  movups  xmm0, xmmword ptr [rdi]
0x180008900  movaps  xmmword ptr [rbx], xmm0
0x180008903  movups  xmm1, xmmword ptr [rdi+10h]
0x180008907  movaps  xmmword ptr [rbx+10h], xmm1
0x18000890b  movups  xmm0, xmmword ptr [rdi+20h]
0x18000890f  movaps  xmmword ptr [rbx+20h], xmm0
0x180008913  movups  xmm1, xmmword ptr [rdi+30h]
0x180008917  movaps  xmmword ptr [rbx+30h], xmm1
0x18000891b  movups  xmm0, xmmword ptr [rdi+40h]
0x18000891f  movaps  xmmword ptr [rbx+40h], xmm0
0x180008923  movups  xmm1, xmmword ptr [rdi+50h]
0x180008927  movaps  xmmword ptr [rbx+50h], xmm1
0x18000892b  movups  xmm0, xmmword ptr [rdi+60h]
0x18000892f  movaps  xmmword ptr [rbx+60h], xmm0
0x180008933  movups  xmm1, xmmword ptr [rdi+70h]
0x180008937  movaps  xmmword ptr [rbx+70h], xmm1
0x18000893b  movups  xmm0, xmmword ptr [rdi+80h]
0x180008942  movups  xmmword ptr [rbx+88h], xmm0
0x180008949  movups  xmm1, xmmword ptr [rdi+90h]
0x180008950  movups  xmmword ptr [rbx+98h], xmm1
0x180008957  xor     ecx, ecx
0x180008959  mov     eax, ecx
0x18000895b  add     rsp, 28h
0x18000895f  pop     rdi
0x180008960  pop     rsi
0x180008961  pop     rbp
0x180008962  pop     rbx
0x180008963  retn
```
