# BaseSrvCopyCommand

- ea: `0x1800094cc`
- end: `0x180009965`
- name: `BaseSrvCopyCommand`
- size: `1177`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008938`
- `0x18000905c`

## callees

- `0x1800094cc`
- `0x18000a9b4`
- `0x18000db11`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800094fa`
- `ntdll!RtlAllocateHeap` at `0x180009535`
- `ntdll!RtlAllocateHeap` at `0x18000956d`
- `ntdll!RtlAllocateHeap` at `0x1800095aa`
- `ntdll!RtlAllocateHeap` at `0x1800095e7`
- `ntdll!RtlAllocateHeap` at `0x18000961e`
- `ntdll!RtlAllocateHeap` at `0x180009659`
- `ntdll!RtlAllocateHeap` at `0x180009697`
- `ntdll!RtlAllocateHeap` at `0x1800096d5`
- `ntdll!RtlAllocateHeap` at `0x1800094fa`
- `ntdll!RtlAllocateHeap` at `0x180009535`
- `ntdll!RtlAllocateHeap` at `0x18000956d`
- `ntdll!RtlAllocateHeap` at `0x1800095aa`
- `ntdll!RtlAllocateHeap` at `0x1800095e7`
- `ntdll!RtlAllocateHeap` at `0x18000961e`
- `ntdll!RtlAllocateHeap` at `0x180009659`
- `ntdll!RtlAllocateHeap` at `0x180009697`
- `ntdll!RtlAllocateHeap` at `0x1800096d5`

## pseudocode

```c
__int64 __fastcall BaseSrvCopyCommand(__int64 a1, __int64 a2)
{
  char *Heap; // rbx
  PVOID v5; // rax
  PVOID v6; // rax
  PVOID v7; // rax
  PVOID v8; // rax
  unsigned int v9; // eax
  PVOID v10; // rax
  unsigned int v11; // eax
  PVOID v12; // rax
  unsigned int v13; // eax
  PVOID v14; // rax
  void *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  const void *v19; // rdx
  __int16 v20; // ax
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
0x1800094cc  push    rbx
0x1800094ce  push    rbp
0x1800094cf  push    rsi
0x1800094d0  push    rdi
0x1800094d1  sub     rsp, 28h
0x1800094d5  mov     rdi, rcx
0x1800094d8  mov     rsi, rdx
0x1800094db  mov     rcx, gs:60h
0x1800094e4  mov     r8d, 100h; Size
0x1800094ea  mov     edx, cs:BaseSrvTag
0x1800094f0  add     edx, 40000h; Flags
0x1800094f6  mov     rcx, [rcx+30h]; HeapHandle
0x1800094fa  call    cs:__imp_RtlAllocateHeap
0x180009501  nop     dword ptr [rax+rax+00h]
0x180009506  xor     ebp, ebp
0x180009508  mov     rbx, rax
0x18000950b  test    rax, rax
0x18000950e  jz      loc_180009959
0x180009514  mov     rcx, gs:60h
0x18000951d  mov     edx, cs:BaseSrvTag
0x180009523  movzx   r8d, word ptr [rdi+0A4h]; Size
0x18000952b  add     edx, 40000h; Flags
0x180009531  mov     rcx, [rcx+30h]; HeapHandle
0x180009535  call    cs:__imp_RtlAllocateHeap
0x18000953c  nop     dword ptr [rax+rax+00h]
0x180009541  mov     [rbx+28h], rax
0x180009545  movzx   eax, word ptr [rdi+0A6h]
0x18000954c  test    ax, ax
0x18000954f  jz      short loc_18000957B
0x180009551  mov     rcx, gs:60h
0x18000955a  mov     r8d, eax; Size
0x18000955d  mov     edx, cs:BaseSrvTag
0x180009563  add     edx, 40000h; Flags
0x180009569  mov     rcx, [rcx+30h]; HeapHandle
0x18000956d  call    cs:__imp_RtlAllocateHeap
0x180009574  nop     dword ptr [rax+rax+00h]
0x180009579  jmp     short loc_18000957E
0x18000957b  mov     rax, rbp
0x18000957e  mov     [rbx+30h], rax
0x180009582  movzx   eax, word ptr [rdi+0A8h]
0x180009589  test    ax, ax
0x18000958c  jz      short loc_1800095B8
0x18000958e  mov     rcx, gs:60h
0x180009597  mov     r8d, eax; Size
0x18000959a  mov     edx, cs:BaseSrvTag
0x1800095a0  add     edx, 40000h; Flags
0x1800095a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800095aa  call    cs:__imp_RtlAllocateHeap
0x1800095b1  nop     dword ptr [rax+rax+00h]
0x1800095b6  jmp     short loc_1800095BB
0x1800095b8  mov     rax, rbp
0x1800095bb  mov     [rbx+38h], rax
0x1800095bf  movzx   eax, word ptr [rdi+0AAh]
0x1800095c6  test    ax, ax
0x1800095c9  jz      short loc_1800095F5
0x1800095cb  mov     rcx, gs:60h
0x1800095d4  mov     r8d, eax; Size
0x1800095d7  mov     edx, cs:BaseSrvTag
0x1800095dd  add     edx, 40000h; Flags
0x1800095e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800095e7  call    cs:__imp_RtlAllocateHeap
0x1800095ee  nop     dword ptr [rax+rax+00h]
0x1800095f3  jmp     short loc_1800095F8
0x1800095f5  mov     rax, rbp
0x1800095f8  mov     [rbx+40h], rax
0x1800095fc  cmp     [rdi+68h], ebp
0x1800095ff  jz      short loc_18000962C
0x180009601  mov     rcx, gs:60h
0x18000960a  mov     edx, cs:BaseSrvTag
0x180009610  mov     r8d, [rdi+68h]; Size
0x180009614  add     edx, 40000h; Flags
0x18000961a  mov     rcx, [rcx+30h]; HeapHandle
0x18000961e  call    cs:__imp_RtlAllocateHeap
0x180009625  nop     dword ptr [rax+rax+00h]
0x18000962a  jmp     short loc_18000962F
0x18000962c  mov     rax, rbp
0x18000962f  mov     [rbx+48h], rax
0x180009633  mov     eax, [rdi+80h]
0x180009639  test    eax, eax
0x18000963b  jz      short loc_180009667
0x18000963d  mov     rcx, gs:60h
0x180009646  mov     r8d, eax; Size
0x180009649  mov     edx, cs:BaseSrvTag
0x18000964f  add     edx, 40000h; Flags
0x180009655  mov     rcx, [rcx+30h]; HeapHandle
0x180009659  call    cs:__imp_RtlAllocateHeap
0x180009660  nop     dword ptr [rax+rax+00h]
0x180009665  jmp     short loc_18000966A
0x180009667  mov     rax, rbp
0x18000966a  mov     [rbx+0C0h], rax
0x180009671  mov     eax, [rdi+90h]
0x180009677  test    eax, eax
0x180009679  jz      short loc_1800096A5
0x18000967b  mov     rcx, gs:60h
0x180009684  mov     r8d, eax; Size
0x180009687  mov     edx, cs:BaseSrvTag
0x18000968d  add     edx, 40000h; Flags
0x180009693  mov     rcx, [rcx+30h]; HeapHandle
0x180009697  call    cs:__imp_RtlAllocateHeap
0x18000969e  nop     dword ptr [rax+rax+00h]
0x1800096a3  jmp     short loc_1800096A8
0x1800096a5  mov     rax, rbp
0x1800096a8  mov     [rbx+0D0h], rax
0x1800096af  mov     eax, [rdi+0A0h]
0x1800096b5  test    eax, eax
0x1800096b7  jz      short loc_1800096E3
0x1800096b9  mov     rcx, gs:60h
0x1800096c2  mov     r8d, eax; Size
0x1800096c5  mov     edx, cs:BaseSrvTag
0x1800096cb  add     edx, 40000h; Flags
0x1800096d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800096d5  call    cs:__imp_RtlAllocateHeap
0x1800096dc  nop     dword ptr [rax+rax+00h]
0x1800096e1  jmp     short loc_1800096E6
0x1800096e3  mov     rax, rbp
0x1800096e6  mov     [rbx+0E0h], rax
0x1800096ed  mov     rcx, [rbx+28h]; void *
0x1800096f1  test    rcx, rcx
0x1800096f4  jz      loc_180009951
0x1800096fa  cmp     [rdi+0A6h], bp
0x180009701  jz      short loc_18000970D
0x180009703  cmp     [rbx+30h], rbp
0x180009707  jz      loc_180009951
0x18000970d  cmp     [rdi+0A8h], bp
0x180009714  jz      short loc_180009720
0x180009716  cmp     [rbx+38h], rbp
0x18000971a  jz      loc_180009951
0x180009720  cmp     [rdi+0AAh], bp
0x180009727  jz      short loc_180009733
0x180009729  cmp     [rbx+40h], rbp
0x18000972d  jz      loc_180009951
0x180009733  cmp     [rdi+68h], ebp
0x180009736  jz      short loc_180009742
0x180009738  cmp     [rbx+48h], rbp
0x18000973c  jz      loc_180009951
0x180009742  cmp     [rdi+80h], ebp
0x180009748  jz      short loc_180009757
0x18000974a  cmp     [rbx+0C0h], rbp
0x180009751  jz      loc_180009951
0x180009757  cmp     [rdi+0A0h], ebp
0x18000975d  jz      short loc_180009768
0x18000975f  test    rax, rax
0x180009762  jz      loc_180009951
0x180009768  cmp     [rdi+90h], ebp
0x18000976e  jz      short loc_18000977D
0x180009770  cmp     [rbx+0D0h], rbp
0x180009777  jz      loc_180009951
0x18000977d  movzx   r8d, word ptr [rdi+0A4h]; Size
0x180009785  mov     rdx, [rdi+40h]; Src
0x180009789  call    memmove_0
0x18000978e  movzx   eax, word ptr [rdi+0A4h]
0x180009795  mov     [rbx+0ECh], ax
0x18000979c  movzx   eax, word ptr [rdi+0A6h]
0x1800097a3  test    ax, ax
0x1800097a6  jz      short loc_1800097B8
0x1800097a8  mov     rdx, [rdi+48h]; Src
0x1800097ac  mov     r8d, eax; Size
0x1800097af  mov     rcx, [rbx+30h]; void *
0x1800097b3  call    memmove_0
0x1800097b8  movzx   eax, word ptr [rdi+0A6h]
0x1800097bf  mov     [rbx+0EEh], ax
0x1800097c6  movzx   eax, word ptr [rdi+0A8h]
0x1800097cd  test    ax, ax
0x1800097d0  jz      short loc_1800097E2
0x1800097d2  mov     rdx, [rdi+50h]; Src
0x1800097d6  mov     r8d, eax; Size
0x1800097d9  mov     rcx, [rbx+38h]; void *
0x1800097dd  call    memmove_0
0x1800097e2  movzx   eax, word ptr [rdi+0A8h]
0x1800097e9  mov     [rbx+0F0h], ax
0x1800097f0  movzx   eax, word ptr [rdi+0AAh]
0x1800097f7  test    ax, ax
0x1800097fa  jz      short loc_18000980C
0x1800097fc  mov     rdx, [rdi+58h]; Src
0x180009800  mov     r8d, eax; Size
0x180009803  mov     rcx, [rbx+40h]; void *
0x180009807  call    memmove_0
0x18000980c  movzx   eax, word ptr [rdi+0AAh]
0x180009813  mov     [rbx+0F2h], ax
0x18000981a  cmp     [rdi+68h], ebp
0x18000981d  jz      short loc_180009830
0x18000981f  mov     r8d, [rdi+68h]; Size
0x180009823  mov     rdx, [rdi+60h]; Src
0x180009827  mov     rcx, [rbx+48h]; void *
0x18000982b  call    memmove_0
0x180009830  mov     eax, [rdi+68h]
0x180009833  mov     [rbx+50h], eax
0x180009836  mov     eax, [rdi+80h]
0x18000983c  test    eax, eax
0x18000983e  jz      short loc_180009853
0x180009840  mov     rdx, [rdi+78h]; Src
0x180009844  mov     r8d, eax; Size
0x180009847  mov     rcx, [rbx+0C0h]; void *
0x18000984e  call    memmove_0
0x180009853  mov     eax, [rdi+80h]
0x180009859  mov     [rbx+0C8h], eax
0x18000985f  mov     eax, [rdi+90h]
0x180009865  test    eax, eax
0x180009867  jz      short loc_18000987F
0x180009869  mov     rdx, [rdi+88h]; Src
0x180009870  mov     r8d, eax; Size
0x180009873  mov     rcx, [rbx+0D0h]; void *
0x18000987a  call    memmove_0
0x18000987f  mov     eax, [rdi+90h]
0x180009885  mov     [rbx+0D8h], eax
0x18000988b  mov     eax, [rdi+0A0h]
0x180009891  test    eax, eax
0x180009893  jz      short loc_1800098AB
0x180009895  mov     rdx, [rdi+98h]; Src
0x18000989c  mov     r8d, eax; Size
0x18000989f  mov     rcx, [rbx+0E0h]; void *
0x1800098a6  call    memmove_0
0x1800098ab  mov     eax, [rdi+0A0h]
0x1800098b1  mov     [rbx+0E8h], eax
0x1800098b7  mov     rdx, [rdi+70h]; Src
0x1800098bb  test    rdx, rdx
0x1800098be  jz      short loc_1800098D6
0x1800098c0  lea     rcx, [rbx+58h]; void *
0x1800098c4  mov     r8d, 68h ; 'h'; Size
0x1800098ca  call    memmove_0
0x1800098cf  mov     eax, 200h
0x1800098d4  jmp     short loc_1800098D8
0x1800098d6  mov     eax, ebp
0x1800098d8  mov     [rbx+0F4h], ax
0x1800098df  mov     eax, [rdi+3Ch]
0x1800098e2  mov     [rbx+4], eax
0x1800098e5  movzx   eax, word ptr [rdi+0ACh]
0x1800098ec  mov     [rbx+0F6h], ax
0x1800098f3  mov     eax, [rdi+38h]
0x1800098f6  mov     [rbx+0Ch], eax
0x1800098f9  cmp     dword ptr [rsi], 20h ; ' '
0x1800098fc  mov     rax, [rsi+8]
0x180009900  jnz     short loc_180009908
0x180009902  mov     [rax+18h], rbx
0x180009906  jmp     short loc_18000990C
0x180009908  mov     [rax+20h], rbx
0x18000990c  mov     [rbx+20h], rbp
0x180009910  mov     [rbx+18h], rbp
0x180009914  mov     [rbx+10h], rbp
0x180009918  mov     [rbx+0F9h], bpl
0x18000991f  cmp     dword ptr [rsi], 10h
0x180009922  jnz     short loc_18000993E
0x180009924  mov     rax, [rdi+20h]
0x180009928  mov     [rbx+10h], rax
0x18000992c  mov     rax, [rdi+28h]
0x180009930  mov     [rbx+18h], rax
0x180009934  mov     rax, [rdi+30h]
0x180009938  mov     [rbx+20h], rax
0x18000993c  jmp     short loc_18000994A
0x18000993e  cmp     dword ptr [rsi], 20h ; ' '
0x180009941  jnz     short loc_18000994A
0x180009943  mov     rax, [rsi+8]
0x180009947  mov     [rax+4], ebp
0x18000994a  mov     eax, 1
0x18000994f  jmp     short loc_18000995B
0x180009951  mov     rcx, rbx; P
0x180009954  call    BaseSrvFreeVDMInfo
0x180009959  xor     eax, eax
0x18000995b  add     rsp, 28h
0x18000995f  pop     rdi
0x180009960  pop     rsi
0x180009961  pop     rbp
0x180009962  pop     rbx
0x180009963  retn
```
