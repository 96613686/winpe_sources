# LargeHeapBucket::Rescan(RescanFlags)

- ea: `0x180008748`
- end: `0x180008994`
- name: `?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008e4c`

## callees

- `0x180008668`
- `0x180008748`
- `0x18000899c`
- `0x180008b8c`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x1800087f9`
- `KERNEL32!ResetWriteWatch` at `0x180008884`
- `KERNEL32!ResetWriteWatch` at `0x180008911`
- `KERNEL32!ResetWriteWatch` at `0x1800087f9`
- `KERNEL32!ResetWriteWatch` at `0x180008884`
- `KERNEL32!ResetWriteWatch` at `0x180008911`

## pseudocode

```c
__int64 __fastcall LargeHeapBucket::Rescan(__int64 a1, unsigned int a2)
{
  int v2; // r15d
  _QWORD *v4; // r12
  __int64 v5; // rbx
  int v6; // r14d
  struct Recycler *v7; // rsi
  int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rbx
  int v11; // edi
  int v12; // eax
  unsigned int v13; // r8d
  __int64 v14; // rbx
  int v15; // r15d
  int v16; // edi
  int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // ebx

  v2 = 0;
  v4 = (_QWORD *)a1;
  v5 = *(_QWORD *)(a1 + 24);
  v6 = a2 & 1;
  v7 = *(struct Recycler **)(*(_QWORD *)a1 + 56LL);
  while ( v5 )
  {
    *(_DWORD *)(v5 + 120) = *(_DWORD *)(v5 + 40);
    if ( v6 )
    {
      *(_BYTE *)(v5 + 132) = 0;
    }
    else if ( *(_BYTE *)(v5 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v5 + 8), 0x1000u);
      v8 = 1;
      goto LABEL_3;
    }
    if ( !*(_DWORD *)(v5 + 124) )
      goto LABEL_11;
    v9 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v5 + 32) != 1 )
    {
      if ( *(_DWORD *)v7 == 57345 || (*(_DWORD *)v7 & 0x2001) != 0x2001 )
      {
        v8 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v5, v7, v9);
        goto LABEL_3;
      }
LABEL_11:
      v8 = 0;
      goto LABEL_3;
    }
    v8 = LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v5, v7, v9);
LABEL_3:
    v5 = *(_QWORD *)(v5 + 64);
    v2 += v8;
  }
  v10 = v4[2];
  v11 = 0;
  while ( v10 )
  {
    *(_DWORD *)(v10 + 120) = *(_DWORD *)(v10 + 40);
    if ( v6 )
    {
      *(_BYTE *)(v10 + 132) = 0;
    }
    else if ( *(_BYTE *)(v10 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v10 + 8), 0x1000u);
      v12 = 1;
      goto LABEL_18;
    }
    if ( !*(_DWORD *)(v10 + 124) )
      goto LABEL_26;
    v13 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v10 + 32) != 1 )
    {
      if ( *(_DWORD *)v7 == 57345 || (*(_DWORD *)v7 & 0x2001) != 0x2001 )
      {
        v12 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v10, v7, v13);
        goto LABEL_18;
      }
LABEL_26:
      v12 = 0;
      goto LABEL_18;
    }
    v12 = LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v10, v7, v13);
LABEL_18:
    v10 = *(_QWORD *)(v10 + 64);
    v11 += v12;
  }
  v14 = v4[4];
  v15 = v11 + v2;
  v16 = 0;
  while ( v14 )
  {
    *(_DWORD *)(v14 + 120) = *(_DWORD *)(v14 + 40);
    if ( v6 )
    {
      *(_BYTE *)(v14 + 132) = 0;
    }
    else if ( *(_BYTE *)(v14 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v14 + 8), 0x1000u);
      v17 = 1;
      goto LABEL_33;
    }
    if ( !*(_DWORD *)(v14 + 124) )
      goto LABEL_41;
    v18 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v14 + 32) != 1 )
    {
      if ( *(_DWORD *)v7 == 57345 || (a1 = 8193, (*(_DWORD *)v7 & 0x2001) != 0x2001) )
      {
        v17 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v14, v7, v18);
        goto LABEL_33;
      }
LABEL_41:
      v17 = 0;
      goto LABEL_33;
    }
    v17 = LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v14, v7, v18);
LABEL_33:
    v14 = *(_QWORD *)(v14 + 64);
    v16 += v17;
  }
  v19 = v16 + v15;
  if ( *((_BYTE *)v7 + 12903) )
    return v19 + (unsigned int)LargeHeapBucket::Rescan(a1, v4[6], v7);
  else
    return v19;
}

```

## disassembly

```asm
0x180008748  mov     rax, rsp
0x18000874b  mov     [rax+18h], rbx
0x18000874f  mov     [rax+20h], rbp
0x180008753  mov     [rax+10h], edx
0x180008756  mov     [rax+8], rcx
0x18000875a  push    rsi
0x18000875b  push    rdi
0x18000875c  push    r12
0x18000875e  push    r14
0x180008760  push    r15
0x180008762  sub     rsp, 40h
0x180008766  mov     rax, [rcx]
0x180008769  xor     r15d, r15d
0x18000876c  mov     ebp, [rsp+68h+arg_8]
0x180008770  mov     r12, rcx
0x180008773  mov     rbx, [rcx+18h]
0x180008777  mov     r14d, ebp
0x18000877a  and     r14d, 1
0x18000877e  mov     rsi, [rax+38h]
0x180008782  jmp     short loc_180008796
0x180008784  mov     rdx, rsi; struct Recycler *
0x180008787  mov     rcx, rbx; this
0x18000878a  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x18000878f  mov     rbx, [rbx+40h]
0x180008793  add     r15, rax
0x180008796  test    rbx, rbx
0x180008799  jz      short loc_180008806
0x18000879b  mov     eax, [rbx+28h]
0x18000879e  mov     [rbx+78h], eax
0x1800087a1  test    r14d, r14d
0x1800087a4  jz      short loc_1800087E1
0x1800087a6  mov     byte ptr [rbx+84h], 0
0x1800087ad  cmp     dword ptr [rbx+7Ch], 0
0x1800087b1  jz      short loc_1800087DD
0x1800087b3  mov     r8d, ebp
0x1800087b6  shr     r8d, 1
0x1800087b9  and     r8d, 1; unsigned int
0x1800087bd  cmp     qword ptr [rbx+20h], 1
0x1800087c2  jz      loc_180008946
0x1800087c8  mov     eax, [rsi]
0x1800087ca  cmp     eax, 0E001h
0x1800087cf  jz      short loc_180008784
0x1800087d1  and     eax, 2001h
0x1800087d6  cmp     eax, 2001h
0x1800087db  jnz     short loc_180008784
0x1800087dd  xor     eax, eax
0x1800087df  jmp     short loc_18000878F
0x1800087e1  cmp     byte ptr [rbx+84h], 0
0x1800087e8  jz      short loc_1800087AD
0x1800087ea  test    bpl, 2
0x1800087ee  jz      short loc_1800087FF
0x1800087f0  mov     rcx, [rbx+8]; lpBaseAddress
0x1800087f4  mov     edx, 1000h; dwRegionSize
0x1800087f9  call    cs:__imp_ResetWriteWatch
0x1800087ff  mov     eax, 1
0x180008804  jmp     short loc_18000878F
0x180008806  mov     rbx, [r12+10h]
0x18000880b  xor     edi, edi
0x18000880d  jmp     short loc_180008821
0x18000880f  mov     rdx, rsi; struct Recycler *
0x180008812  mov     rcx, rbx; this
0x180008815  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x18000881a  mov     rbx, [rbx+40h]
0x18000881e  add     rdi, rax
0x180008821  test    rbx, rbx
0x180008824  jz      short loc_180008891
0x180008826  mov     eax, [rbx+28h]
0x180008829  mov     [rbx+78h], eax
0x18000882c  test    r14d, r14d
0x18000882f  jz      short loc_18000886C
0x180008831  mov     byte ptr [rbx+84h], 0
0x180008838  cmp     dword ptr [rbx+7Ch], 0
0x18000883c  jz      short loc_180008868
0x18000883e  mov     r8d, ebp
0x180008841  shr     r8d, 1
0x180008844  and     r8d, 1; unsigned int
0x180008848  cmp     qword ptr [rbx+20h], 1
0x18000884d  jz      loc_180008959
0x180008853  mov     eax, [rsi]
0x180008855  cmp     eax, 0E001h
0x18000885a  jz      short loc_18000880F
0x18000885c  and     eax, 2001h
0x180008861  cmp     eax, 2001h
0x180008866  jnz     short loc_18000880F
0x180008868  xor     eax, eax
0x18000886a  jmp     short loc_18000881A
0x18000886c  cmp     byte ptr [rbx+84h], 0
0x180008873  jz      short loc_180008838
0x180008875  test    bpl, 2
0x180008879  jz      short loc_18000888A
0x18000887b  mov     rcx, [rbx+8]; lpBaseAddress
0x18000887f  mov     edx, 1000h; dwRegionSize
0x180008884  call    cs:__imp_ResetWriteWatch
0x18000888a  mov     eax, 1
0x18000888f  jmp     short loc_18000881A
0x180008891  mov     rbx, [r12+20h]
0x180008896  add     r15d, edi
0x180008899  xor     edi, edi
0x18000889b  jmp     short loc_1800088AF
0x18000889d  mov     rdx, rsi; struct Recycler *
0x1800088a0  mov     rcx, rbx; this
0x1800088a3  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x1800088a8  mov     rbx, [rbx+40h]
0x1800088ac  add     rdi, rax
0x1800088af  test    rbx, rbx
0x1800088b2  jz      short loc_18000891E
0x1800088b4  mov     eax, [rbx+28h]
0x1800088b7  mov     [rbx+78h], eax
0x1800088ba  test    r14d, r14d
0x1800088bd  jz      short loc_1800088F9
0x1800088bf  mov     byte ptr [rbx+84h], 0
0x1800088c6  cmp     dword ptr [rbx+7Ch], 0
0x1800088ca  jz      short loc_1800088F5
0x1800088cc  mov     r8d, ebp
0x1800088cf  shr     r8d, 1
0x1800088d2  and     r8d, 1; unsigned int
0x1800088d6  cmp     qword ptr [rbx+20h], 1
0x1800088db  jz      loc_18000896C
0x1800088e1  mov     eax, [rsi]
0x1800088e3  cmp     eax, 0E001h
0x1800088e8  jz      short loc_18000889D
0x1800088ea  mov     ecx, 2001h
0x1800088ef  and     eax, ecx
0x1800088f1  cmp     eax, ecx
0x1800088f3  jnz     short loc_18000889D
0x1800088f5  xor     eax, eax
0x1800088f7  jmp     short loc_1800088A8
0x1800088f9  cmp     byte ptr [rbx+84h], 0
0x180008900  jz      short loc_1800088C6
0x180008902  test    bpl, 2
0x180008906  jz      short loc_180008917
0x180008908  mov     rcx, [rbx+8]; lpBaseAddress
0x18000890c  mov     edx, 1000h; dwRegionSize
0x180008911  call    cs:__imp_ResetWriteWatch
0x180008917  mov     eax, 1
0x18000891c  jmp     short loc_1800088A8
0x18000891e  cmp     byte ptr [rsi+3267h], 0
0x180008925  lea     ebx, [rdi+r15]
0x180008929  jnz     short loc_18000897F
0x18000892b  mov     eax, ebx
0x18000892d  lea     r11, [rsp+68h+var_28]
0x180008932  mov     rbx, [r11+40h]
0x180008936  mov     rbp, [r11+48h]
0x18000893a  mov     rsp, r11
0x18000893d  pop     r15
0x18000893f  pop     r14
0x180008941  pop     r12
0x180008943  pop     rdi
0x180008944  pop     rsi
0x180008945  retn
0x180008946  mov     rdx, rsi; struct Recycler *
0x180008949  mov     rcx, rbx; this
0x18000894c  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180008951  movzx   eax, al
0x180008954  jmp     loc_18000878F
0x180008959  mov     rdx, rsi; struct Recycler *
0x18000895c  mov     rcx, rbx; this
0x18000895f  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180008964  movzx   eax, al
0x180008967  jmp     loc_18000881A
0x18000896c  mov     rdx, rsi; struct Recycler *
0x18000896f  mov     rcx, rbx; this
0x180008972  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180008977  movzx   eax, al
0x18000897a  jmp     loc_1800088A8
0x18000897f  mov     rdx, [r12+30h]
0x180008984  mov     r8, rsi
0x180008987  mov     [rsp+68h+var_48], ebp
0x18000898b  call    ?Rescan@LargeHeapBucket@@AEAA_KPEAVLargeHeapBlock@@PEAVRecycler@@_NW4RescanFlags@@@Z; LargeHeapBucket::Rescan(LargeHeapBlock *,Recycler *,bool,RescanFlags)
0x180008990  add     eax, ebx
0x180008992  jmp     short loc_18000892D
```
