# CBSSEntry::GetColocatedBssInfo(ulong,bool,bool,ulong *,DOT11_BSS_BAND_CHANNEL *)

- ea: `0x1400957a4`
- end: `0x1400959ca`
- name: `?GetColocatedBssInfo@CBSSEntry@@QEAAKK_N0PEAKPEAUDOT11_BSS_BAND_CHANNEL@@@Z`
- size: `550`
- prototype: `unsigned int __fastcall(CBSSEntry *__hidden this, unsigned int, bool, bool, unsigned int *, struct DOT11_BSS_BAND_CHANNEL *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140027530`
- `0x140028c50`
- `0x1400955f0`

## callees

- `0x14001c540`
- `0x1400957a4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400958e4`
- `ntoskrnl!RtlCompareMemory` at `0x1400958e4`

## pseudocode

```c
__int64 __fastcall CBSSEntry::GetColocatedBssInfo(
        CBSSEntry *this,
        unsigned int a2,
        __int64 a3,
        char a4,
        unsigned int *a5,
        struct DOT11_BSS_BAND_CHANNEL *a6)
{
  unsigned int v8; // r12d
  __int64 v9; // rbx
  int v10; // eax
  char v11; // r9
  unsigned int v12; // ecx
  __int64 v13; // r10
  int v14; // r11d
  int v15; // esi
  __int64 v16; // r8
  char v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r15
  __int64 v20; // rcx
  char v21; // dl
  __int64 v22; // rbp
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // edx
  __int64 v26; // r8
  __int64 i; // rcx
  __int128 v28; // xmm2
  __int64 v29; // xmm3_8
  __int64 result; // rax
  int v31; // [rsp+60h] [rbp+8h]
  int v32; // [rsp+70h] [rbp+18h]

  v8 = 0;
  v9 = 0;
  v10 = CWabiToDot11Converter::MapBandID(*((unsigned int *)this + 171));
  v12 = *((_DWORD *)this + 175);
  v13 = 0;
  v14 = *((_DWORD *)this + 172);
  v15 = v10;
  v32 = v10;
  v31 = v14;
  if ( v12 )
  {
    do
    {
      v16 = *((_QWORD *)this + 88);
      v17 = a4;
      if ( *(_DWORD *)(v16 + 40 * v13 + 28) != 5 )
        v17 = 0;
      if ( ((*(_BYTE *)(v16 + 40 * v13 + 8) & 4) != 0 || (*(_BYTE *)(v16 + 40 * v13 + 10) & 0x40) != 0)
        && (!v17 || *(_DWORD *)(v16 + 40 * v13 + 24) == v14) )
      {
        if ( (unsigned int)v9 < a2 )
        {
          v18 = 3 * v9;
          v9 = (unsigned int)(v9 + 1);
          *(_OWORD *)((char *)a6 + 8 * v18) = *(_OWORD *)(v16 + 40 * v13 + 16);
          *((_QWORD *)a6 + v18 + 2) = *(_QWORD *)(v16 + 40 * v13 + 32);
          v12 = *((_DWORD *)this + 175);
        }
        ++v8;
      }
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < v12 );
    v15 = v10;
    v11 = a4;
  }
  v19 = 0;
  if ( *((_DWORD *)this + 178) )
  {
    do
    {
      v20 = *((_QWORD *)this + 90);
      v21 = v11;
      if ( *(_DWORD *)(v20 + 40 * v19 + 28) != 5 )
        v21 = 0;
      if ( ((*(_BYTE *)(v20 + 40 * v19 + 8) & 4) != 0 || (*(_BYTE *)(v20 + 40 * v19 + 10) & 0x40) != 0)
        && (!v21 || *(_DWORD *)(v20 + 40 * v19 + 24) == v14) )
      {
        v22 = 0;
        if ( (_DWORD)v9 )
        {
          while ( RtlCompareMemory((char *)a6 + 24 * v22, (const void *)(*((_QWORD *)this + 90) + 16LL + 40 * v19), 6u) != 6 )
          {
            v22 = (unsigned int)(v22 + 1);
            if ( (unsigned int)v22 >= (unsigned int)v9 )
              goto LABEL_23;
          }
        }
        else
        {
LABEL_23:
          if ( (unsigned int)v9 < a2 )
          {
            v23 = *((_QWORD *)this + 90);
            v24 = 3 * v9;
            v9 = (unsigned int)(v9 + 1);
            *(_OWORD *)((char *)a6 + 8 * v24) = *(_OWORD *)(v23 + 40 * v19 + 16);
            *((_QWORD *)a6 + v24 + 2) = *(_QWORD *)(v23 + 40 * v19 + 32);
          }
          ++v8;
        }
      }
      v14 = v31;
      v19 = (unsigned int)(v19 + 1);
      v11 = a4;
    }
    while ( (unsigned int)v19 < *((_DWORD *)this + 178) );
    v15 = v32;
  }
  v25 = 0;
  if ( (_DWORD)v9 )
  {
    v26 = 0;
    do
    {
      if ( *((_DWORD *)a6 + 6 * v26 + 3) == v15 )
      {
        for ( i = (unsigned int)(v9 - 1); (unsigned int)i > v25; i = (unsigned int)(i - 1) )
        {
          if ( *((_DWORD *)a6 + 6 * i + 3) != v15 )
          {
            v28 = *(_OWORD *)((char *)a6 + 24 * i);
            v29 = *((_QWORD *)a6 + 3 * i + 2);
            *(_OWORD *)((char *)a6 + 24 * i) = *(_OWORD *)((char *)a6 + 24 * v26);
            *((_QWORD *)a6 + 3 * i + 2) = *((_QWORD *)a6 + 3 * v26 + 2);
            *(_OWORD *)((char *)a6 + 24 * v26) = v28;
            *((_QWORD *)a6 + 3 * v26 + 2) = v29;
            break;
          }
        }
      }
      ++v25;
      ++v26;
    }
    while ( v25 < (unsigned int)v9 );
  }
  result = v8;
  *a5 = v9;
  return result;
}

```

## disassembly

```asm
0x1400957a4  mov     [rsp+arg_8], rbx
0x1400957a9  mov     [rsp+arg_18], r9b
0x1400957ae  mov     byte ptr [rsp+arg_10], r8b
0x1400957b3  push    rbp
0x1400957b4  push    rsi
0x1400957b5  push    rdi
0x1400957b6  push    r12
0x1400957b8  push    r13
0x1400957ba  push    r14
0x1400957bc  push    r15
0x1400957be  sub     rsp, 20h
0x1400957c2  mov     rdi, [rsp+58h+arg_28]
0x1400957ca  mov     r14, rcx
0x1400957cd  mov     ecx, [rcx+2ACh]
0x1400957d3  mov     r13d, edx
0x1400957d6  xor     r12d, r12d
0x1400957d9  xor     ebx, ebx
0x1400957db  call    ?MapBandID@CWabiToDot11Converter@@SA?AW4_DOT11_BAND_ID@@W4_WDI_BAND_ID@@@Z; CWabiToDot11Converter::MapBandID(_WDI_BAND_ID)
0x1400957e0  mov     ecx, [r14+2BCh]
0x1400957e7  xor     r10d, r10d
0x1400957ea  mov     r11d, [r14+2B0h]
0x1400957f1  mov     esi, eax
0x1400957f3  mov     [rsp+58h+arg_10], eax
0x1400957f7  mov     [rsp+58h+arg_0], r11d
0x1400957fc  test    ecx, ecx
0x1400957fe  jz      short loc_140095878
0x140095800  movzx   esi, [rsp+58h+arg_18]
0x140095805  mov     r8, [r14+2C0h]
0x14009580c  lea     rdx, [r10+r10*4]
0x140095810  xor     eax, eax
0x140095812  mov     r9d, esi
0x140095815  cmp     dword ptr [r8+rdx*8+1Ch], 5
0x14009581b  cmovnz  r9d, eax
0x14009581f  test    byte ptr [r8+rdx*8+8], 4
0x140095825  jnz     short loc_14009582F
0x140095827  test    byte ptr [r8+rdx*8+0Ah], 40h
0x14009582d  jz      short loc_140095867
0x14009582f  test    r9b, r9b
0x140095832  jz      short loc_14009583B
0x140095834  cmp     [r8+rdx*8+18h], r11d
0x140095839  jnz     short loc_140095867
0x14009583b  cmp     ebx, r13d
0x14009583e  jnb     short loc_140095864
0x140095840  movups  xmm0, xmmword ptr [r8+rdx*8+10h]
0x140095846  lea     rcx, [rbx+rbx*2]
0x14009584a  inc     ebx
0x14009584c  movups  xmmword ptr [rdi+rcx*8], xmm0
0x140095850  movsd   xmm1, qword ptr [r8+rdx*8+20h]
0x140095857  movsd   qword ptr [rdi+rcx*8+10h], xmm1
0x14009585d  mov     ecx, [r14+2BCh]
0x140095864  inc     r12d
0x140095867  inc     r10d
0x14009586a  cmp     r10d, ecx
0x14009586d  jb      short loc_140095805
0x14009586f  mov     esi, [rsp+58h+arg_10]
0x140095873  mov     r9b, [rsp+58h+arg_18]
0x140095878  xor     r15d, r15d
0x14009587b  cmp     [r14+2C8h], r15d
0x140095882  jbe     loc_140095944
0x140095888  mov     rcx, [r14+2D0h]
0x14009588f  lea     rsi, [r15+r15*4]
0x140095893  xor     eax, eax
0x140095895  movzx   edx, r9b
0x140095899  cmp     dword ptr [rcx+rsi*8+1Ch], 5
0x14009589e  cmovnz  edx, eax
0x1400958a1  test    byte ptr [rcx+rsi*8+8], 4
0x1400958a6  jnz     short loc_1400958AF
0x1400958a8  test    byte ptr [rcx+rsi*8+0Ah], 40h
0x1400958ad  jz      short loc_140095926
0x1400958af  test    dl, dl
0x1400958b1  jz      short loc_1400958BA
0x1400958b3  cmp     [rcx+rsi*8+18h], r11d
0x1400958b8  jnz     short loc_140095926
0x1400958ba  xor     ebp, ebp
0x1400958bc  test    ebx, ebx
0x1400958be  jz      short loc_1400958FC
0x1400958c0  mov     rdx, [r14+2D0h]
0x1400958c7  lea     rcx, ds:0[rbp*2]
0x1400958cf  add     rdx, 10h
0x1400958d3  add     rcx, rbp
0x1400958d6  mov     r8d, 6; Length
0x1400958dc  lea     rdx, [rdx+rsi*8]; Source2
0x1400958e0  lea     rcx, [rdi+rcx*8]; Source1
0x1400958e4  call    cs:__imp_RtlCompareMemory
0x1400958eb  nop     dword ptr [rax+rax+00h]
0x1400958f0  cmp     rax, 6
0x1400958f4  jz      short loc_140095926
0x1400958f6  inc     ebp
0x1400958f8  cmp     ebp, ebx
0x1400958fa  jb      short loc_1400958C0
0x1400958fc  cmp     ebx, r13d
0x1400958ff  jnb     short loc_140095923
0x140095901  mov     rdx, [r14+2D0h]
0x140095908  lea     rcx, [rbx+rbx*2]
0x14009590c  inc     ebx
0x14009590e  movups  xmm0, xmmword ptr [rdx+rsi*8+10h]
0x140095913  movups  xmmword ptr [rdi+rcx*8], xmm0
0x140095917  movsd   xmm1, qword ptr [rdx+rsi*8+20h]
0x14009591d  movsd   qword ptr [rdi+rcx*8+10h], xmm1
0x140095923  inc     r12d
0x140095926  mov     r11d, [rsp+58h+arg_0]
0x14009592b  inc     r15d
0x14009592e  mov     r9b, [rsp+58h+arg_18]
0x140095933  cmp     r15d, [r14+2C8h]
0x14009593a  jb      loc_140095888
0x140095940  mov     esi, [rsp+58h+arg_10]
0x140095944  xor     edx, edx
0x140095946  test    ebx, ebx
0x140095948  jz      short loc_1400959A7
0x14009594a  xor     r8d, r8d
0x14009594d  lea     r10, [r8+r8*2]
0x140095951  cmp     [rdi+r10*8+0Ch], esi
0x140095956  jnz     short loc_14009599E
0x140095958  lea     ecx, [rbx-1]
0x14009595b  cmp     ecx, edx
0x14009595d  jbe     short loc_14009599E
0x14009595f  lea     r9, [rcx+rcx*2]
0x140095963  cmp     [rdi+r9*8+0Ch], esi
0x140095968  jnz     short loc_14009596E
0x14009596a  dec     ecx
0x14009596c  jmp     short loc_14009595B
0x14009596e  movups  xmm0, xmmword ptr [rdi+r10*8]
0x140095973  movups  xmm2, xmmword ptr [rdi+r9*8]
0x140095978  movsd   xmm3, qword ptr [rdi+r9*8+10h]
0x14009597f  movups  xmmword ptr [rdi+r9*8], xmm0
0x140095984  movsd   xmm1, qword ptr [rdi+r10*8+10h]
0x14009598b  movsd   qword ptr [rdi+r9*8+10h], xmm1
0x140095992  movups  xmmword ptr [rdi+r10*8], xmm2
0x140095997  movsd   qword ptr [rdi+r10*8+10h], xmm3
0x14009599e  inc     edx
0x1400959a0  inc     r8
0x1400959a3  cmp     edx, ebx
0x1400959a5  jb      short loc_14009594D
0x1400959a7  mov     rcx, [rsp+58h+arg_20]
0x1400959af  mov     eax, r12d
0x1400959b2  mov     [rcx], ebx
0x1400959b4  mov     rbx, [rsp+58h+arg_8]
0x1400959b9  add     rsp, 20h
0x1400959bd  pop     r15
0x1400959bf  pop     r14
0x1400959c1  pop     r13
0x1400959c3  pop     r12
0x1400959c5  pop     rdi
0x1400959c6  pop     rsi
0x1400959c7  pop     rbp
0x1400959c8  retn
```
