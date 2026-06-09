# QmfTransposerCreate(hbeTransposer * *,int,int,int)

- ea: `0x1800917e8`
- end: `0x180091a34`
- name: `?QmfTransposerCreate@@YA?AW4SBR_ERROR@@PEAPEAUhbeTransposer@@HHH@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b728`

## callees

- `0x180006914`
- `0x18009168c`
- `0x1800917e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091810`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091899`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800918ba`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800918cf`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18009194d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091965`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18009199e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800919c0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800919fc`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091810`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091899`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800918ba`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800918cf`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18009194d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180091965`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18009199e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800919c0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800919fc`

## pseudocode

```c
__int64 __fastcall QmfTransposerCreate(_QWORD *a1, int a2, __int64 a3, int a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  int v10; // ecx
  void *v11; // rax
  void *v12; // rax
  size_t v13; // rcx
  void *v14; // rax
  bool v15; // zf
  int i; // esi
  void *v17; // rax
  int j; // esi
  void *v19; // rax

  if ( !a1 )
    return 0;
  v7 = calloc(1u, 0xA88u);
  v8 = v7;
  if ( !v7 )
    return 4;
  v7[334] = 0x100000001LL;
  *((_DWORD *)v7 + 670) = 1;
  *((_DWORD *)v7 + 7) = a2;
  if ( a2 == 768 )
    v10 = 32;
  else
    v10 = 2 * a2 * (a4 + 1) / 64;
  *((_DWORD *)v7 + 10) = v10;
  *((_DWORD *)v7 + 8) = 13;
  *((_DWORD *)v7 + 11) = a2 / v10;
  *((_DWORD *)v7 + 9) = 2 * (v10 / 2) + 24;
  v11 = calloc(0x55u, 4u);
  v8[8] = v11;
  if ( v11 )
  {
    v12 = calloc(*((unsigned int *)v8 + 8), 8u);
    v13 = *((unsigned int *)v8 + 8);
    v8[9] = v12;
    v14 = calloc(v13, 8u);
    v15 = v8[9] == 0;
    v8[10] = v14;
    if ( !v15 )
    {
      if ( v14 )
      {
        for ( i = 0; i < *((_DWORD *)v8 + 8); ++i )
        {
          *(_QWORD *)(v8[9] + 8LL * i) = CDKaalloc_L(256);
          *(_QWORD *)(v8[10] + 8LL * i) = CDKaalloc_L(256);
          if ( !*(_QWORD *)(v8[9] + 8LL * i) || !*(_QWORD *)(v8[10] + 8LL * i) )
            goto LABEL_25;
        }
        v8[332] = calloc(0xBu, 8u);
        v17 = calloc(0xBu, 8u);
        v15 = v8[332] == 0;
        v8[333] = v17;
        if ( !v15 )
        {
          if ( v17 )
          {
            for ( j = 0; j < 11; ++j )
            {
              *(_QWORD *)(v8[332] + 8LL * j) = calloc(0x40u, 4u);
              *(_QWORD *)(v8[333] + 8LL * j) = calloc(0x40u, 4u);
              if ( !*(_QWORD *)(v8[332] + 8LL * j) || !*(_QWORD *)(v8[333] + 8LL * j) )
                goto LABEL_25;
            }
            v19 = calloc(0x20u, 4u);
            v8[11] = v19;
            if ( v19 )
            {
              *((_DWORD *)v8 + 14) = a4;
              *a1 = v8;
              return 0;
            }
          }
        }
      }
    }
  }
LABEL_25:
  QmfTransposerClose((struct hbeTransposer *)v8);
  return 4;
}

```

## disassembly

```asm
0x1800917e8  push    rbx
0x1800917ea  push    rbp
0x1800917eb  push    rsi
0x1800917ec  push    rdi
0x1800917ed  push    r14
0x1800917ef  push    r15
0x1800917f1  sub     rsp, 28h
0x1800917f5  mov     r15d, r9d
0x1800917f8  mov     edi, edx
0x1800917fa  mov     r14, rcx
0x1800917fd  test    rcx, rcx
0x180091800  jz      loc_180091A18
0x180091806  mov     edx, 0A88h; Size
0x18009180b  mov     ecx, 1; Count
0x180091810  call    cs:__imp_calloc
0x180091817  nop     dword ptr [rax+rax+00h]
0x18009181c  mov     rbx, rax
0x18009181f  test    rax, rax
0x180091822  jnz     short loc_18009182C
0x180091824  lea     eax, [rbx+4]
0x180091827  jmp     loc_180091A1A
0x18009182c  mov     rax, cs:qword_1800D2FD0
0x180091833  mov     ecx, 40h ; '@'
0x180091838  mov     [rbx+0A70h], rax
0x18009183f  mov     eax, cs:dword_1800D2FD8
0x180091845  mov     [rbx+0A78h], eax
0x18009184b  mov     [rbx+1Ch], edi
0x18009184e  cmp     edi, 300h
0x180091854  jnz     short loc_18009185D
0x180091856  mov     ecx, 20h ; ' '
0x18009185b  jmp     short loc_18009186B
0x18009185d  lea     eax, [r15+1]
0x180091861  imul    eax, edi
0x180091864  add     eax, eax
0x180091866  cdq
0x180091867  idiv    ecx
0x180091869  mov     ecx, eax
0x18009186b  mov     [rbx+28h], ecx
0x18009186e  mov     eax, edi
0x180091870  cdq
0x180091871  mov     dword ptr [rbx+20h], 0Dh
0x180091878  idiv    ecx
0x18009187a  mov     [rbx+2Ch], eax
0x18009187d  mov     eax, ecx
0x18009187f  cdq
0x180091880  mov     ecx, 2
0x180091885  idiv    ecx
0x180091887  lea     edi, [rcx+2]
0x18009188a  mov     edx, edi; Size
0x18009188c  lea     ecx, [rdi+51h]; Count
0x18009188f  lea     eax, ds:18h[rax*2]
0x180091896  mov     [rbx+24h], eax
0x180091899  call    cs:__imp_calloc
0x1800918a0  nop     dword ptr [rax+rax+00h]
0x1800918a5  mov     [rbx+40h], rax
0x1800918a9  test    rax, rax
0x1800918ac  jz      loc_180091A28
0x1800918b2  mov     ecx, [rbx+20h]; Count
0x1800918b5  lea     ebp, [rdi+4]
0x1800918b8  mov     edx, ebp; Size
0x1800918ba  call    cs:__imp_calloc
0x1800918c1  nop     dword ptr [rax+rax+00h]
0x1800918c6  mov     ecx, [rbx+20h]; Count
0x1800918c9  mov     edx, ebp; Size
0x1800918cb  mov     [rbx+48h], rax
0x1800918cf  call    cs:__imp_calloc
0x1800918d6  nop     dword ptr [rax+rax+00h]
0x1800918db  cmp     qword ptr [rbx+48h], 0
0x1800918e0  mov     [rbx+50h], rax
0x1800918e4  jz      loc_180091A28
0x1800918ea  test    rax, rax
0x1800918ed  jz      loc_180091A28
0x1800918f3  xor     esi, esi
0x1800918f5  cmp     esi, [rbx+20h]
0x1800918f8  jge     short loc_180091943
0x1800918fa  mov     ecx, 100h
0x1800918ff  call    CDKaalloc_L
0x180091904  mov     rcx, [rbx+48h]
0x180091908  movsxd  rbp, esi
0x18009190b  mov     [rcx+rbp*8], rax
0x18009190f  mov     ecx, 100h
0x180091914  call    CDKaalloc_L
0x180091919  mov     rcx, [rbx+50h]
0x18009191d  mov     [rcx+rbp*8], rax
0x180091921  mov     rax, [rbx+48h]
0x180091925  cmp     qword ptr [rax+rbp*8], 0
0x18009192a  jz      loc_180091A28
0x180091930  mov     rax, [rbx+50h]
0x180091934  cmp     qword ptr [rax+rbp*8], 0
0x180091939  jz      loc_180091A28
0x18009193f  inc     esi
0x180091941  jmp     short loc_1800918F5
0x180091943  mov     esi, 8
0x180091948  mov     edx, esi; Size
0x18009194a  lea     ecx, [rsi+3]; Count
0x18009194d  call    cs:__imp_calloc
0x180091954  nop     dword ptr [rax+rax+00h]
0x180091959  mov     edx, esi; Size
0x18009195b  lea     ecx, [rsi+3]; Count
0x18009195e  mov     [rbx+0A60h], rax
0x180091965  call    cs:__imp_calloc
0x18009196c  nop     dword ptr [rax+rax+00h]
0x180091971  cmp     qword ptr [rbx+0A60h], 0
0x180091979  mov     [rbx+0A68h], rax
0x180091980  jz      loc_180091A28
0x180091986  test    rax, rax
0x180091989  jz      loc_180091A28
0x18009198f  xor     esi, esi
0x180091991  mov     rdx, rdi; Size
0x180091994  cmp     esi, 0Bh
0x180091997  jge     short loc_1800919F7
0x180091999  mov     ecx, 40h ; '@'; Count
0x18009199e  call    cs:__imp_calloc
0x1800919a5  nop     dword ptr [rax+rax+00h]
0x1800919aa  mov     rcx, [rbx+0A60h]
0x1800919b1  mov     rdx, rdi; Size
0x1800919b4  movsxd  rbp, esi
0x1800919b7  mov     [rcx+rbp*8], rax
0x1800919bb  mov     ecx, 40h ; '@'; Count
0x1800919c0  call    cs:__imp_calloc
0x1800919c7  nop     dword ptr [rax+rax+00h]
0x1800919cc  mov     rcx, [rbx+0A68h]
0x1800919d3  mov     [rcx+rbp*8], rax
0x1800919d7  mov     rax, [rbx+0A60h]
0x1800919de  cmp     qword ptr [rax+rbp*8], 0
0x1800919e3  jz      short loc_180091A28
0x1800919e5  mov     rax, [rbx+0A68h]
0x1800919ec  cmp     qword ptr [rax+rbp*8], 0
0x1800919f1  jz      short loc_180091A28
0x1800919f3  inc     esi
0x1800919f5  jmp     short loc_180091991
0x1800919f7  mov     ecx, 20h ; ' '; Count
0x1800919fc  call    cs:__imp_calloc
0x180091a03  nop     dword ptr [rax+rax+00h]
0x180091a08  mov     [rbx+58h], rax
0x180091a0c  test    rax, rax
0x180091a0f  jz      short loc_180091A28
0x180091a11  mov     [rbx+38h], r15d
0x180091a15  mov     [r14], rbx
0x180091a18  xor     eax, eax
0x180091a1a  add     rsp, 28h
0x180091a1e  pop     r15
0x180091a20  pop     r14
0x180091a22  pop     rdi
0x180091a23  pop     rsi
0x180091a24  pop     rbp
0x180091a25  pop     rbx
0x180091a26  retn
0x180091a28  mov     rcx, rbx; Block
0x180091a2b  call    ?QmfTransposerClose@@YAXPEAUhbeTransposer@@@Z; QmfTransposerClose(hbeTransposer *)
0x180091a30  mov     eax, edi
0x180091a32  jmp     short loc_180091A1A
```
