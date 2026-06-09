# BaseSrvCopyCommand

- ea: `0x1800091dc`
- end: `0x180009692`
- name: `BaseSrvCopyCommand`
- size: `1206`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008644`
- `0x180008d80`

## callees

- `0x1800091dc`
- `0x18000a72c`
- `0x18000d707`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009215`
- `ntdll!RtlAllocateHeap` at `0x180009250`
- `ntdll!RtlAllocateHeap` at `0x180009288`
- `ntdll!RtlAllocateHeap` at `0x1800092c5`
- `ntdll!RtlAllocateHeap` at `0x180009302`
- `ntdll!RtlAllocateHeap` at `0x180009339`
- `ntdll!RtlAllocateHeap` at `0x180009374`
- `ntdll!RtlAllocateHeap` at `0x1800093b2`
- `ntdll!RtlAllocateHeap` at `0x1800093f0`
- `ntdll!RtlAllocateHeap` at `0x180009215`
- `ntdll!RtlAllocateHeap` at `0x180009250`
- `ntdll!RtlAllocateHeap` at `0x180009288`
- `ntdll!RtlAllocateHeap` at `0x1800092c5`
- `ntdll!RtlAllocateHeap` at `0x180009302`
- `ntdll!RtlAllocateHeap` at `0x180009339`
- `ntdll!RtlAllocateHeap` at `0x180009374`
- `ntdll!RtlAllocateHeap` at `0x1800093b2`
- `ntdll!RtlAllocateHeap` at `0x1800093f0`

## pseudocode

```c
__int64 __fastcall BaseSrvCopyCommand(__int64 a1, __int64 a2)
{
  char *Heap; // rbx
  PVOID v5; // rax
  PVOID v6; // rax
  PVOID v7; // rax
  PVOID v8; // rax
  unsigned int v9; // ecx
  PVOID v10; // rax
  unsigned int v11; // ecx
  PVOID v12; // rax
  unsigned int v13; // ecx
  PVOID v14; // rax
  void *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  const void *v19; // rdx
  __int16 v20; // cx
  __int64 v21; // rax

  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, 0x100u);
  if ( !Heap )
    return 0;
  *((_QWORD *)Heap + 5) = RtlAllocateHeap(
                            NtCurrentPeb()->ProcessHeap,
                            BaseSrvTag + 0x40000,
                            *(unsigned __int16 *)(a1 + 164));
  if ( *(_WORD *)(a1 + 166) )
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, *(unsigned __int16 *)(a1 + 166));
  else
    v5 = 0;
  *((_QWORD *)Heap + 6) = v5;
  if ( *(_WORD *)(a1 + 168) )
    v6 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, *(unsigned __int16 *)(a1 + 168));
  else
    v6 = 0;
  *((_QWORD *)Heap + 7) = v6;
  if ( *(_WORD *)(a1 + 170) )
    v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, *(unsigned __int16 *)(a1 + 170));
  else
    v7 = 0;
  *((_QWORD *)Heap + 8) = v7;
  if ( *(_DWORD *)(a1 + 104) )
    v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, *(unsigned int *)(a1 + 104));
  else
    v8 = 0;
  *((_QWORD *)Heap + 9) = v8;
  v9 = *(_DWORD *)(a1 + 128);
  if ( v9 )
    v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v9);
  else
    v10 = 0;
  *((_QWORD *)Heap + 24) = v10;
  v11 = *(_DWORD *)(a1 + 144);
  if ( v11 )
    v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v11);
  else
    v12 = 0;
  *((_QWORD *)Heap + 26) = v12;
  v13 = *(_DWORD *)(a1 + 160);
  if ( v13 )
    v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v13);
  else
    v14 = 0;
  *((_QWORD *)Heap + 28) = v14;
  v15 = (void *)*((_QWORD *)Heap + 5);
  if ( !v15
    || *(_WORD *)(a1 + 166) && !*((_QWORD *)Heap + 6)
    || *(_WORD *)(a1 + 168) && !*((_QWORD *)Heap + 7)
    || *(_WORD *)(a1 + 170) && !*((_QWORD *)Heap + 8)
    || *(_DWORD *)(a1 + 104) && !*((_QWORD *)Heap + 9)
    || *(_DWORD *)(a1 + 128) && !*((_QWORD *)Heap + 24)
    || *(_DWORD *)(a1 + 160) && !v14
    || *(_DWORD *)(a1 + 144) && !*((_QWORD *)Heap + 26) )
  {
    BaseSrvFreeVDMInfo(Heap);
    return 0;
  }
  memmove_0(v15, *(const void **)(a1 + 64), *(unsigned __int16 *)(a1 + 164));
  *((_WORD *)Heap + 118) = *(_WORD *)(a1 + 164);
  if ( *(_WORD *)(a1 + 166) )
    memmove_0(*((void **)Heap + 6), *(const void **)(a1 + 72), *(unsigned __int16 *)(a1 + 166));
  *((_WORD *)Heap + 119) = *(_WORD *)(a1 + 166);
  if ( *(_WORD *)(a1 + 168) )
    memmove_0(*((void **)Heap + 7), *(const void **)(a1 + 80), *(unsigned __int16 *)(a1 + 168));
  *((_WORD *)Heap + 120) = *(_WORD *)(a1 + 168);
  if ( *(_WORD *)(a1 + 170) )
    memmove_0(*((void **)Heap + 8), *(const void **)(a1 + 88), *(unsigned __int16 *)(a1 + 170));
  *((_WORD *)Heap + 121) = *(_WORD *)(a1 + 170);
  if ( *(_DWORD *)(a1 + 104) )
    memmove_0(*((void **)Heap + 9), *(const void **)(a1 + 96), *(unsigned int *)(a1 + 104));
  *((_DWORD *)Heap + 20) = *(_DWORD *)(a1 + 104);
  v16 = *(_DWORD *)(a1 + 128);
  if ( v16 )
    memmove_0(*((void **)Heap + 24), *(const void **)(a1 + 120), v16);
  *((_DWORD *)Heap + 50) = *(_DWORD *)(a1 + 128);
  v17 = *(_DWORD *)(a1 + 144);
  if ( v17 )
    memmove_0(*((void **)Heap + 26), *(const void **)(a1 + 136), v17);
  *((_DWORD *)Heap + 54) = *(_DWORD *)(a1 + 144);
  v18 = *(_DWORD *)(a1 + 160);
  if ( v18 )
    memmove_0(*((void **)Heap + 28), *(const void **)(a1 + 152), v18);
  *((_DWORD *)Heap + 58) = *(_DWORD *)(a1 + 160);
  v19 = *(const void **)(a1 + 112);
  if ( v19 )
  {
    memmove_0(Heap + 88, v19, 0x68u);
    v20 = 512;
  }
  else
  {
    v20 = 0;
  }
  *((_WORD *)Heap + 122) = v20;
  *((_DWORD *)Heap + 1) = *(_DWORD *)(a1 + 60);
  *((_WORD *)Heap + 123) = *(_WORD *)(a1 + 172);
  *((_DWORD *)Heap + 3) = *(_DWORD *)(a1 + 56);
  v21 = *(_QWORD *)(a2 + 8);
  if ( *(_DWORD *)a2 == 32 )
    *(_QWORD *)(v21 + 24) = Heap;
  else
    *(_QWORD *)(v21 + 32) = Heap;
  *((_QWORD *)Heap + 4) = 0;
  *((_QWORD *)Heap + 3) = 0;
  *((_QWORD *)Heap + 2) = 0;
  Heap[249] = 0;
  if ( *(_DWORD *)a2 == 16 )
  {
    *((_QWORD *)Heap + 2) = *(_QWORD *)(a1 + 32);
    *((_QWORD *)Heap + 3) = *(_QWORD *)(a1 + 40);
    *((_QWORD *)Heap + 4) = *(_QWORD *)(a1 + 48);
  }
  else if ( *(_DWORD *)a2 == 32 )
  {
    *(_DWORD *)(*(_QWORD *)(a2 + 8) + 4LL) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800091dc  mov     [rsp+arg_0], rbx
0x1800091e1  mov     [rsp+arg_8], rbp
0x1800091e6  mov     [rsp+arg_10], rsi
0x1800091eb  push    rdi
0x1800091ec  sub     rsp, 20h
0x1800091f0  mov     rdi, rcx
0x1800091f3  mov     rsi, rdx
0x1800091f6  mov     rcx, gs:60h
0x1800091ff  mov     r8d, 100h; Size
0x180009205  mov     edx, cs:BaseSrvTag
0x18000920b  add     edx, 40000h; Flags
0x180009211  mov     rcx, [rcx+30h]; HeapHandle
0x180009215  call    cs:__imp_RtlAllocateHeap
0x18000921c  nop     dword ptr [rax+rax+00h]
0x180009221  xor     ebp, ebp
0x180009223  mov     rbx, rax
0x180009226  test    rax, rax
0x180009229  jz      loc_18000967A
0x18000922f  mov     rcx, gs:60h
0x180009238  mov     edx, cs:BaseSrvTag
0x18000923e  movzx   r8d, word ptr [rdi+0A4h]; Size
0x180009246  add     edx, 40000h; Flags
0x18000924c  mov     rcx, [rcx+30h]; HeapHandle
0x180009250  call    cs:__imp_RtlAllocateHeap
0x180009257  nop     dword ptr [rax+rax+00h]
0x18000925c  mov     [rbx+28h], rax
0x180009260  movzx   ecx, word ptr [rdi+0A6h]
0x180009267  test    cx, cx
0x18000926a  jz      short loc_180009296
0x18000926c  mov     edx, cs:BaseSrvTag
0x180009272  mov     r8d, ecx; Size
0x180009275  mov     rcx, gs:60h
0x18000927e  add     edx, 40000h; Flags
0x180009284  mov     rcx, [rcx+30h]; HeapHandle
0x180009288  call    cs:__imp_RtlAllocateHeap
0x18000928f  nop     dword ptr [rax+rax+00h]
0x180009294  jmp     short loc_180009299
0x180009296  mov     rax, rbp
0x180009299  mov     [rbx+30h], rax
0x18000929d  movzx   ecx, word ptr [rdi+0A8h]
0x1800092a4  test    cx, cx
0x1800092a7  jz      short loc_1800092D3
0x1800092a9  mov     edx, cs:BaseSrvTag
0x1800092af  mov     r8d, ecx; Size
0x1800092b2  mov     rcx, gs:60h
0x1800092bb  add     edx, 40000h; Flags
0x1800092c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800092c5  call    cs:__imp_RtlAllocateHeap
0x1800092cc  nop     dword ptr [rax+rax+00h]
0x1800092d1  jmp     short loc_1800092D6
0x1800092d3  mov     rax, rbp
0x1800092d6  mov     [rbx+38h], rax
0x1800092da  movzx   ecx, word ptr [rdi+0AAh]
0x1800092e1  test    cx, cx
0x1800092e4  jz      short loc_180009310
0x1800092e6  mov     edx, cs:BaseSrvTag
0x1800092ec  mov     r8d, ecx; Size
0x1800092ef  mov     rcx, gs:60h
0x1800092f8  add     edx, 40000h; Flags
0x1800092fe  mov     rcx, [rcx+30h]; HeapHandle
0x180009302  call    cs:__imp_RtlAllocateHeap
0x180009309  nop     dword ptr [rax+rax+00h]
0x18000930e  jmp     short loc_180009313
0x180009310  mov     rax, rbp
0x180009313  mov     [rbx+40h], rax
0x180009317  cmp     [rdi+68h], ebp
0x18000931a  jz      short loc_180009347
0x18000931c  mov     rcx, gs:60h
0x180009325  mov     edx, cs:BaseSrvTag
0x18000932b  mov     r8d, [rdi+68h]; Size
0x18000932f  add     edx, 40000h; Flags
0x180009335  mov     rcx, [rcx+30h]; HeapHandle
0x180009339  call    cs:__imp_RtlAllocateHeap
0x180009340  nop     dword ptr [rax+rax+00h]
0x180009345  jmp     short loc_18000934A
0x180009347  mov     rax, rbp
0x18000934a  mov     [rbx+48h], rax
0x18000934e  mov     ecx, [rdi+80h]
0x180009354  test    ecx, ecx
0x180009356  jz      short loc_180009382
0x180009358  mov     edx, cs:BaseSrvTag
0x18000935e  mov     r8d, ecx; Size
0x180009361  mov     rcx, gs:60h
0x18000936a  add     edx, 40000h; Flags
0x180009370  mov     rcx, [rcx+30h]; HeapHandle
0x180009374  call    cs:__imp_RtlAllocateHeap
0x18000937b  nop     dword ptr [rax+rax+00h]
0x180009380  jmp     short loc_180009385
0x180009382  mov     rax, rbp
0x180009385  mov     [rbx+0C0h], rax
0x18000938c  mov     ecx, [rdi+90h]
0x180009392  test    ecx, ecx
0x180009394  jz      short loc_1800093C0
0x180009396  mov     edx, cs:BaseSrvTag
0x18000939c  mov     r8d, ecx; Size
0x18000939f  mov     rcx, gs:60h
0x1800093a8  add     edx, 40000h; Flags
0x1800093ae  mov     rcx, [rcx+30h]; HeapHandle
0x1800093b2  call    cs:__imp_RtlAllocateHeap
0x1800093b9  nop     dword ptr [rax+rax+00h]
0x1800093be  jmp     short loc_1800093C3
0x1800093c0  mov     rax, rbp
0x1800093c3  mov     [rbx+0D0h], rax
0x1800093ca  mov     ecx, [rdi+0A0h]
0x1800093d0  test    ecx, ecx
0x1800093d2  jz      short loc_1800093FE
0x1800093d4  mov     edx, cs:BaseSrvTag
0x1800093da  mov     r8d, ecx; Size
0x1800093dd  mov     rcx, gs:60h
0x1800093e6  add     edx, 40000h; Flags
0x1800093ec  mov     rcx, [rcx+30h]; HeapHandle
0x1800093f0  call    cs:__imp_RtlAllocateHeap
0x1800093f7  nop     dword ptr [rax+rax+00h]
0x1800093fc  jmp     short loc_180009401
0x1800093fe  mov     rax, rbp
0x180009401  mov     [rbx+0E0h], rax
0x180009408  mov     rcx, [rbx+28h]; void *
0x18000940c  test    rcx, rcx
0x18000940f  jz      loc_180009672
0x180009415  cmp     [rdi+0A6h], bp
0x18000941c  jz      short loc_180009428
0x18000941e  cmp     [rbx+30h], rbp
0x180009422  jz      loc_180009672
0x180009428  cmp     [rdi+0A8h], bp
0x18000942f  jz      short loc_18000943B
0x180009431  cmp     [rbx+38h], rbp
0x180009435  jz      loc_180009672
0x18000943b  cmp     [rdi+0AAh], bp
0x180009442  jz      short loc_18000944E
0x180009444  cmp     [rbx+40h], rbp
0x180009448  jz      loc_180009672
0x18000944e  cmp     [rdi+68h], ebp
0x180009451  jz      short loc_18000945D
0x180009453  cmp     [rbx+48h], rbp
0x180009457  jz      loc_180009672
0x18000945d  cmp     [rdi+80h], ebp
0x180009463  jz      short loc_180009472
0x180009465  cmp     [rbx+0C0h], rbp
0x18000946c  jz      loc_180009672
0x180009472  cmp     [rdi+0A0h], ebp
0x180009478  jz      short loc_180009483
0x18000947a  test    rax, rax
0x18000947d  jz      loc_180009672
0x180009483  cmp     [rdi+90h], ebp
0x180009489  jz      short loc_180009498
0x18000948b  cmp     [rbx+0D0h], rbp
0x180009492  jz      loc_180009672
0x180009498  movzx   r8d, word ptr [rdi+0A4h]; Size
0x1800094a0  mov     rdx, [rdi+40h]; Src
0x1800094a4  call    memmove_0
0x1800094a9  movzx   eax, word ptr [rdi+0A4h]
0x1800094b0  mov     [rbx+0ECh], ax
0x1800094b7  movzx   eax, word ptr [rdi+0A6h]
0x1800094be  test    ax, ax
0x1800094c1  jz      short loc_1800094D3
0x1800094c3  mov     rdx, [rdi+48h]; Src
0x1800094c7  mov     r8d, eax; Size
0x1800094ca  mov     rcx, [rbx+30h]; void *
0x1800094ce  call    memmove_0
0x1800094d3  movzx   eax, word ptr [rdi+0A6h]
0x1800094da  mov     [rbx+0EEh], ax
0x1800094e1  movzx   eax, word ptr [rdi+0A8h]
0x1800094e8  test    ax, ax
0x1800094eb  jz      short loc_1800094FD
0x1800094ed  mov     rdx, [rdi+50h]; Src
0x1800094f1  mov     r8d, eax; Size
0x1800094f4  mov     rcx, [rbx+38h]; void *
0x1800094f8  call    memmove_0
0x1800094fd  movzx   eax, word ptr [rdi+0A8h]
0x180009504  mov     [rbx+0F0h], ax
0x18000950b  movzx   eax, word ptr [rdi+0AAh]
0x180009512  test    ax, ax
0x180009515  jz      short loc_180009527
0x180009517  mov     rdx, [rdi+58h]; Src
0x18000951b  mov     r8d, eax; Size
0x18000951e  mov     rcx, [rbx+40h]; void *
0x180009522  call    memmove_0
0x180009527  movzx   eax, word ptr [rdi+0AAh]
0x18000952e  mov     [rbx+0F2h], ax
0x180009535  cmp     [rdi+68h], ebp
0x180009538  jz      short loc_18000954B
0x18000953a  mov     r8d, [rdi+68h]; Size
0x18000953e  mov     rdx, [rdi+60h]; Src
0x180009542  mov     rcx, [rbx+48h]; void *
0x180009546  call    memmove_0
0x18000954b  mov     eax, [rdi+68h]
0x18000954e  mov     [rbx+50h], eax
0x180009551  mov     eax, [rdi+80h]
0x180009557  test    eax, eax
0x180009559  jz      short loc_18000956E
0x18000955b  mov     rdx, [rdi+78h]; Src
0x18000955f  mov     r8d, eax; Size
0x180009562  mov     rcx, [rbx+0C0h]; void *
0x180009569  call    memmove_0
0x18000956e  mov     eax, [rdi+80h]
0x180009574  mov     [rbx+0C8h], eax
0x18000957a  mov     eax, [rdi+90h]
0x180009580  test    eax, eax
0x180009582  jz      short loc_18000959A
0x180009584  mov     rdx, [rdi+88h]; Src
0x18000958b  mov     r8d, eax; Size
0x18000958e  mov     rcx, [rbx+0D0h]; void *
0x180009595  call    memmove_0
0x18000959a  mov     eax, [rdi+90h]
0x1800095a0  mov     [rbx+0D8h], eax
0x1800095a6  mov     eax, [rdi+0A0h]
0x1800095ac  test    eax, eax
0x1800095ae  jz      short loc_1800095C6
0x1800095b0  mov     rdx, [rdi+98h]; Src
0x1800095b7  mov     r8d, eax; Size
0x1800095ba  mov     rcx, [rbx+0E0h]; void *
0x1800095c1  call    memmove_0
0x1800095c6  mov     eax, [rdi+0A0h]
0x1800095cc  mov     [rbx+0E8h], eax
0x1800095d2  mov     rdx, [rdi+70h]; Src
0x1800095d6  test    rdx, rdx
0x1800095d9  jz      short loc_1800095F1
0x1800095db  lea     rcx, [rbx+58h]; void *
0x1800095df  mov     r8d, 68h ; 'h'; Size
0x1800095e5  call    memmove_0
0x1800095ea  mov     ecx, 200h
0x1800095ef  jmp     short loc_1800095F4
0x1800095f1  movzx   ecx, bp
0x1800095f4  mov     eax, 0F4h
0x1800095f9  mov     rdx, rbx
0x1800095fc  mov     [rax+rbx], cx
0x180009600  mov     eax, [rdi+3Ch]
0x180009603  mov     [rbx+4], eax
0x180009606  movzx   eax, word ptr [rdi+0ACh]
0x18000960d  mov     [rbx+0F6h], ax
0x180009614  mov     eax, [rdi+38h]
0x180009617  mov     [rbx+0Ch], eax
0x18000961a  cmp     dword ptr [rsi], 20h ; ' '
0x18000961d  mov     rax, [rsi+8]
0x180009621  jnz     short loc_180009629
0x180009623  mov     [rax+18h], rbx
0x180009627  jmp     short loc_18000962D
0x180009629  mov     [rax+20h], rbx
0x18000962d  mov     [rbx+20h], rbp
0x180009631  mov     [rbx+18h], rbp
0x180009635  mov     [rbx+10h], rbp
0x180009639  mov     [rbx+0F9h], bpl
0x180009640  cmp     dword ptr [rsi], 10h
0x180009643  jnz     short loc_18000965F
0x180009645  mov     rax, [rdi+20h]
0x180009649  mov     [rbx+10h], rax
0x18000964d  mov     rax, [rdi+28h]
0x180009651  mov     [rbx+18h], rax
0x180009655  mov     rax, [rdi+30h]
0x180009659  mov     [rbx+20h], rax
0x18000965d  jmp     short loc_18000966B
0x18000965f  cmp     dword ptr [rsi], 20h ; ' '
0x180009662  jnz     short loc_18000966B
0x180009664  mov     rax, [rsi+8]
0x180009668  mov     [rax+4], ebp
0x18000966b  mov     eax, 1
0x180009670  jmp     short loc_18000967C
0x180009672  mov     rcx, rbx; P
0x180009675  call    BaseSrvFreeVDMInfo
0x18000967a  xor     eax, eax
0x18000967c  mov     rbx, [rsp+28h+arg_0]
0x180009681  mov     rbp, [rsp+28h+arg_8]
0x180009686  mov     rsi, [rsp+28h+arg_10]
0x18000968b  add     rsp, 20h
0x18000968f  pop     rdi
0x180009690  retn
```
