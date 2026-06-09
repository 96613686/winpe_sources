# AiAllocUninstallStringEaData

- ea: `0x140020790`
- end: `0x140020817`
- name: `AiAllocUninstallStringEaData`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140020db4`

## callees

- `0x140006c40`
- `0x140020790`
- `0x140032a50`

## pseudocode

```c
__int64 __fastcall AiAllocUninstallStringEaData(const void **a1, __int64 a2, __int64 *a3, unsigned int *a4)
{
  unsigned int v5; // esi
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned __int64 v12; // rax

  v5 = *(unsigned __int16 *)a1 + 44;
  v9 = AiAlloc(v5);
  v10 = v9;
  if ( !v9 )
    return 3221225495LL;
  *(_DWORD *)v9 = 1;
  *(_OWORD *)(v9 + 4) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(v9 + 20) = *(_OWORD *)(a2 + 32);
  memmove((void *)(v9 + 40), a1[1], *(unsigned __int16 *)a1);
  v12 = (unsigned __int64)*(unsigned __int16 *)a1 >> 1;
  *a3 = v10;
  *a4 = v5;
  *(_WORD *)(v10 + 2 * v12 + 40) = 10;
  *(_DWORD *)(v10 + 36) = *(unsigned __int16 *)a1;
  return 0;
}

```

## disassembly

```asm
0x140020790  push    rbx
0x140020792  push    rbp
0x140020793  push    rsi
0x140020794  push    rdi
0x140020795  push    r14
0x140020797  push    r15
0x140020799  sub     rsp, 28h
0x14002079d  movzx   esi, word ptr [rcx]
0x1400207a0  mov     rdi, rcx
0x1400207a3  add     esi, 2Ch ; ','
0x1400207a6  mov     r14, r9
0x1400207a9  mov     ecx, esi
0x1400207ab  mov     r15, r8
0x1400207ae  mov     rbp, rdx
0x1400207b1  call    AiAlloc
0x1400207b6  mov     rbx, rax
0x1400207b9  test    rax, rax
0x1400207bc  jnz     short loc_1400207C5
0x1400207be  mov     eax, 0C0000017h
0x1400207c3  jmp     short loc_140020809
0x1400207c5  mov     dword ptr [rax], 1
0x1400207cb  lea     rcx, [rax+28h]; void *
0x1400207cf  movups  xmm0, xmmword ptr [rbp+10h]
0x1400207d3  movdqu  xmmword ptr [rax+4], xmm0
0x1400207d8  movups  xmm1, xmmword ptr [rbp+20h]
0x1400207dc  movdqu  xmmword ptr [rax+14h], xmm1
0x1400207e1  movzx   r8d, word ptr [rdi]; Size
0x1400207e5  mov     rdx, [rdi+8]; Src
0x1400207e9  call    memmove
0x1400207ee  movzx   eax, word ptr [rdi]
0x1400207f1  shr     rax, 1
0x1400207f4  mov     [r15], rbx
0x1400207f7  mov     [r14], esi
0x1400207fa  mov     word ptr [rbx+rax*2+28h], 0Ah
0x140020801  movzx   eax, word ptr [rdi]
0x140020804  mov     [rbx+24h], eax
0x140020807  xor     eax, eax
0x140020809  add     rsp, 28h
0x14002080d  pop     r15
0x14002080f  pop     r14
0x140020811  pop     rdi
0x140020812  pop     rsi
0x140020813  pop     rbp
0x140020814  pop     rbx
0x140020815  retn
```
