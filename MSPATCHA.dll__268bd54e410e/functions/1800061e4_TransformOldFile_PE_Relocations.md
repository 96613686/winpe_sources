# TransformOldFile_PE_Relocations

- ea: `0x1800061e4`
- end: `0x180006775`
- name: `TransformOldFile_PE_Relocations`
- size: `1425`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000541c`

## callees

- `0x180001cae`
- `0x180004cc4`
- `0x180004e48`
- `0x180004ef0`
- `0x18000526c`
- `0x180005400`
- `0x1800061e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800066b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800066b8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006290`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006290`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800066a8`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800066ca`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800066a8`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800066ca`

## pseudocode

```c
int __fastcall TransformOldFile_PE_Relocations(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v8; // rbx
  int v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r12
  _DWORD *v13; // rax
  _DWORD *v14; // r14
  unsigned int v15; // r15d
  unsigned int *v16; // r12
  int v17; // ecx
  unsigned int v18; // ebx
  unsigned __int64 v19; // r11
  unsigned __int64 v20; // r9
  int v21; // edx
  int v22; // r10d
  _WORD *v23; // rcx
  unsigned __int64 v24; // r11
  _WORD *v25; // rbx
  int v26; // eax
  unsigned __int16 v27; // cx
  _DWORD *v28; // r15
  char v29; // al
  int NewRvaFromRiftTable; // ecx
  bool v31; // zf
  __int64 v32; // rax
  __int64 v33; // r10
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rcx
  unsigned __int64 v37; // r8
  unsigned __int64 v38; // rax
  unsigned int v39; // ecx
  unsigned int v40; // r8d
  signed int v41; // edi
  unsigned int *v42; // r9
  __int64 v43; // r8
  _WORD *v44; // rdx
  _DWORD *v45; // r10
  __int64 v46; // rax
  __int64 v47; // rcx
  unsigned int v48; // r15d
  unsigned int v49; // r12d
  unsigned int *v50; // r11
  unsigned __int64 v51; // rsi
  __int64 v52; // r14
  unsigned int v53; // ebx
  unsigned int v54; // ebx
  _DWORD *v55; // r11
  unsigned int v57; // [rsp+30h] [rbp-98h]
  int v58; // [rsp+34h] [rbp-94h]
  unsigned __int64 v59; // [rsp+40h] [rbp-88h]
  int v60; // [rsp+48h] [rbp-80h]
  unsigned int v61; // [rsp+4Ch] [rbp-7Ch]
  int v62; // [rsp+60h] [rbp-68h]
  unsigned __int64 v63; // [rsp+68h] [rbp-60h]
  unsigned __int64 v64; // [rsp+78h] [rbp-50h]
  unsigned int *v65; // [rsp+80h] [rbp-48h]
  int v66; // [rsp+D0h] [rbp+8h]
  size_t Size; // [rsp+D8h] [rbp+10h] BYREF
  unsigned int v68; // [rsp+E0h] [rbp+18h]
  __int64 v69; // [rsp+E8h] [rbp+20h]

  v69 = a4;
  v68 = a3;
  LODWORD(Size) = 0;
  v8 = a2 + a3;
  v59 = v8;
  v9 = *(_DWORD *)(a1 + 52);
  v66 = v9;
  v10 = ImageDirectoryOffsetAndSize(a1, 5, (int)&Size, a2, a3);
  v61 = v10;
  if ( !v10 )
  {
LABEL_55:
    LODWORD(v13) = 332;
    if ( *(_WORD *)(a1 + 4) == 332 )
    {
      v47 = *(unsigned __int16 *)(a1 + 20);
      v48 = v9 + *(_DWORD *)(v47 + a1 + 36);
      v49 = v9 + *(_DWORD *)(a1 + 80);
      v50 = (unsigned int *)(a2 + *(unsigned int *)(v47 + a1 + 44));
      v51 = v8 - 4;
      if ( (unsigned __int64)v50 < v8 - 4 )
      {
        v52 = a5;
        do
        {
          v53 = *v50;
          if ( *v50 >= v48 && v53 < v49 )
          {
            *(unsigned int *)((char *)v50 + v52 - a2) |= 0x1010101u;
            v54 = v53 - v9;
            LODWORD(v13) = GetNewRvaFromRiftTable(v69, v54);
            if ( (_DWORD)v13 != v54 )
            {
              LODWORD(v13) = v9 + (_DWORD)v13;
              *v55 = (_DWORD)v13;
            }
            v50 = (_DWORD *)((char *)v55 + 3);
          }
          v50 = (unsigned int *)((char *)v50 + 1);
        }
        while ( (unsigned __int64)v50 < v51 );
      }
    }
    return (int)v13;
  }
  v11 = Size;
  if ( (unsigned int)Size + v10 > a3 )
  {
    v9 = v66;
    goto LABEL_55;
  }
  v12 = v10;
  memset_0((void *)(v10 + a5), 3, (unsigned int)Size);
  v13 = VirtualAlloc(0, 8 * ((unsigned __int64)v11 >> 1), 0x1000u, 4u);
  v14 = v13;
  if ( v13 )
  {
    v15 = 0;
    v58 = 0;
    v16 = (unsigned int *)(a2 + v12);
    v65 = v16;
    v17 = v11;
    v57 = v11;
    v18 = v68;
    while ( 1 )
    {
      v19 = v59;
      if ( v17 <= 0 )
        break;
      if ( (unsigned __int64)v16 > v59 - 8 )
      {
        ((void (*)(void))ThrowPeFmtException)();
LABEL_66:
        ((void (*)(void))ThrowPeFmtException)();
LABEL_67:
        ThrowPeFmtException(v36, v34, v37, v35);
        __debugbreak();
        JUMPOUT(0x180006775LL);
      }
      if ( v16[1] > v17 || v16[1] <= 8 )
        break;
      v20 = a2 + (unsigned int)ImageRvaToFileOffset(a1, *v16, a2, v18);
      v64 = v20;
      if ( v20 )
      {
        v21 = v66;
        v22 = v66 + *v16;
        v60 = v22;
        v23 = v16 + 2;
        Size = (size_t)(v16 + 2);
        v24 = ((unsigned __int64)v16[1] - 8) >> 1;
        while ( 1 )
        {
          v25 = v23;
          v26 = v24;
          LODWORD(v24) = v24 - 1;
          v62 = v24;
          if ( !v26 )
            break;
          v63 = v59 - 2;
          if ( (unsigned __int64)v23 > v59 - 2 )
            goto LABEL_66;
          v27 = *v23;
          LODWORD(Size) = v27 >> 12;
          if ( (_BYTE)Size )
          {
            v28 = (_DWORD *)((v27 & 0xFFF) + v20);
            v14[2 * v58] = GetNewRvaFromRiftTable(v69, v22 + (v27 & 0xFFFu) - v21);
            v29 = Size;
            LOBYTE(v14[2 * v58 + 1]) = Size;
            switch ( v29 )
            {
              case 1:
              case 2:
                if ( (unsigned __int64)v28 < v63 )
                  *(_WORD *)((char *)v28 + a5 - a2) |= 0x101u;
                break;
              case 3:
                if ( (unsigned __int64)v28 <= v59 - 4 )
                {
                  *(_DWORD *)((char *)v28 + a5 - a2) |= 0x1010101u;
                  NewRvaFromRiftTable = GetNewRvaFromRiftTable(v69, (unsigned int)(*v28 - v66));
                  v31 = NewRvaFromRiftTable == (_DWORD)v24;
                  LODWORD(v24) = v62;
                  if ( !v31 )
                    *v28 = NewRvaFromRiftTable + v66;
                }
                break;
              case 4:
                if ( (unsigned __int64)v28 < v63 )
                  *(_WORD *)((char *)v28 + a5 - a2) |= 0x101u;
                Size = (size_t)++v25;
                LODWORD(v24) = v24 - 1;
                HIWORD(v14[2 * v58 + 1]) = *v25;
                break;
            }
            v15 = ++v58;
            v21 = v66;
            v20 = v64;
            v22 = v60;
          }
          v23 = v25 + 1;
          Size = (size_t)(v25 + 1);
        }
        v18 = v68;
      }
      v32 = v16[1];
      v17 = v57 - v32;
      v57 -= v32;
      v16 = (unsigned int *)((char *)v16 + v32);
    }
    if ( v15 > 1 )
      RelocQsort(v14, &v14[2 * v15 - 2]);
    v33 = a1 + *(unsigned __int16 *)(a1 + 20) + 24LL;
    v34 = 0;
    v35 = v61;
    while ( (unsigned int)v34 < *(unsigned __int16 *)(a1 + 6) )
    {
      v36 = 5 * v34;
      v37 = v33 + 40 * v34;
      if ( v37 < a2 )
        goto LABEL_67;
      v34 = (unsigned int)(v34 + 1);
      v36 = 5 * v34;
      v38 = v33 + 40 * v34;
      if ( v37 > v38 || v38 > v19 )
        goto LABEL_67;
      if ( (*(_QWORD *)v37 | 0x2020202020202020LL) == 0x2020636F6C65722ELL )
      {
        v39 = *(_DWORD *)(v37 + 20);
        if ( v61 >= v39 )
        {
          v40 = v39 + *(_DWORD *)(v37 + 16);
          if ( v61 < v40 )
            v11 = v40 - v61;
        }
      }
    }
    v41 = v11 & 0xFFFFFFFE;
    v42 = v65;
    v43 = 0;
    while ( (unsigned __int64)v41 > 8 && (unsigned int)v43 < v15 )
    {
      *v42 = v14[2 * v43] & 0xFFFFF000;
      v44 = v42 + 2;
      Size = (size_t)(v42 + 2);
      v41 -= 8;
      v45 = v42 + 2;
      while ( v41 > 0 )
      {
        if ( (unsigned int)v43 >= v15 || (v14[2 * v43] & 0xFFFFF000) != *v42 )
        {
          if ( ((unsigned __int8)v45 & 2) != 0 )
          {
            *v44 = 0;
            LODWORD(v44) = (_DWORD)v45 + 2;
            Size = (size_t)v45 + 2;
            v41 -= 2;
          }
          break;
        }
        *v44 = v14[2 * v43] & 0xFFF | (LOBYTE(v14[2 * v43 + 1]) << 12);
        v44 = (_WORD *)v45 + 1;
        v45 = v44;
        Size = (size_t)v44;
        v41 -= 2;
        v43 = (unsigned int)(v43 + 1);
      }
      v46 = (unsigned int)((_DWORD)v44 - (_DWORD)v42);
      v42[1] = v46;
      v42 = (unsigned int *)((char *)v42 + v46);
    }
    LODWORD(v13) = VirtualFree(v14, 0, 0x8000u);
  }
  return (int)v13;
}

```

## disassembly

```asm
0x1800061e4  mov     rax, rsp
0x1800061e7  mov     [rax+20h], r9
0x1800061eb  mov     [rax+18h], r8d
0x1800061ef  push    rbx
0x1800061f0  push    rsi
0x1800061f1  push    rdi
0x1800061f2  push    r12
0x1800061f4  push    r13
0x1800061f6  push    r14
0x1800061f8  push    r15
0x1800061fa  sub     rsp, 90h
0x180006201  mov     r14d, r8d
0x180006204  mov     r13, rdx
0x180006207  mov     rsi, rcx
0x18000620a  mov     dword ptr [rax+10h], 0
0x180006211  mov     ebx, r8d
0x180006214  add     rbx, rdx
0x180006217  mov     [rsp+0C8h+var_88], rbx
0x18000621c  mov     edi, [rcx+34h]
0x18000621f  mov     [rsp+0C8h+arg_0], edi
0x180006226  mov     [rsp+0C8h+var_A8], r14d
0x18000622b  mov     r9, rdx
0x18000622e  lea     r8, [rax+10h]
0x180006232  mov     edx, 5
0x180006237  call    ImageDirectoryOffsetAndSize
0x18000623c  mov     [rsp+0C8h+var_7C], eax
0x180006240  test    eax, eax
0x180006242  jz      loc_1800066D9
0x180006248  mov     edi, dword ptr [rsp+0C8h+Size]
0x18000624f  lea     ecx, [rdi+rax]
0x180006252  cmp     ecx, r14d
0x180006255  ja      loc_1800066D2
0x18000625b  mov     ebx, edi
0x18000625d  mov     r12d, eax
0x180006260  mov     rcx, [rsp+0C8h+arg_20]
0x180006268  add     rcx, r12; void *
0x18000626b  mov     r8d, edi; Size
0x18000626e  mov     edx, 3; Val
0x180006273  call    memset_0
0x180006278  shr     rbx, 1
0x18000627b  shl     rbx, 3
0x18000627f  mov     r9d, 4; flProtect
0x180006285  mov     r8d, 1000h; flAllocationType
0x18000628b  mov     rdx, rbx; dwSize
0x18000628e  xor     ecx, ecx; lpAddress
0x180006290  call    cs:__imp_VirtualAlloc
0x180006296  mov     r14, rax
0x180006299  mov     [rsp+0C8h+lpAddress], rax
0x1800062a1  test    rax, rax
0x1800062a4  jz      loc_180006751
0x1800062aa  xor     r15d, r15d
0x1800062ad  mov     [rsp+0C8h+var_94], r15d
0x1800062b2  add     r12, r13
0x1800062b5  mov     [rsp+0C8h+var_48], r12
0x1800062bd  mov     [rsp+0C8h+var_70], r12
0x1800062c2  mov     ecx, edi
0x1800062c4  mov     [rsp+0C8h+var_98], ecx
0x1800062c8  mov     ebx, [rsp+0C8h+arg_10]
0x1800062cf  mov     r11, [rsp+0C8h+var_88]
0x1800062d4  test    ecx, ecx
0x1800062d6  jle     loc_180006508
0x1800062dc  lea     rax, [r11-8]
0x1800062e0  cmp     r12, rax
0x1800062e3  ja      loc_180006764
0x1800062e9  cmp     [r12+4], ecx
0x1800062ee  ja      loc_180006508
0x1800062f4  cmp     dword ptr [r12+4], 8
0x1800062fa  jbe     loc_180006508
0x180006300  mov     r9d, ebx
0x180006303  mov     r8, r13
0x180006306  mov     edx, [r12]
0x18000630a  mov     rcx, rsi
0x18000630d  call    ImageRvaToFileOffset
0x180006312  mov     r9d, eax
0x180006315  add     r9, r13
0x180006318  mov     [rsp+0C8h+var_50], r9
0x18000631d  jz      loc_1800064EC
0x180006323  mov     r10d, [r12]
0x180006327  mov     edx, [rsp+0C8h+arg_0]
0x18000632e  add     r10d, edx
0x180006331  mov     [rsp+0C8h+var_80], r10d
0x180006336  lea     rcx, [r12+8]
0x18000633b  mov     [rsp+0C8h+Size], rcx
0x180006343  mov     r11d, [r12+4]
0x180006348  sub     r11, 8
0x18000634c  shr     r11, 1
0x18000634f  mov     [rsp+0C8h+var_90], r11d
0x180006354  mov     rbx, rcx
0x180006357  mov     eax, r11d
0x18000635a  dec     r11d
0x18000635d  mov     [rsp+0C8h+var_68], r11
0x180006362  mov     [rsp+0C8h+var_90], r11d
0x180006367  test    eax, eax
0x180006369  jz      loc_1800064E5
0x18000636f  mov     rax, [rsp+0C8h+var_88]
0x180006374  add     rax, 0FFFFFFFFFFFFFFFEh
0x180006378  mov     [rsp+0C8h+var_60], rax
0x18000637d  cmp     rcx, rax
0x180006380  ja      loc_180006769
0x180006386  movzx   r8d, word ptr [rcx]
0x18000638a  mov     ecx, r8d
0x18000638d  mov     eax, r8d
0x180006390  shr     eax, 0Ch
0x180006393  mov     dword ptr [rsp+0C8h+Size], eax
0x18000639a  test    al, al
0x18000639c  jz      loc_1800064D4
0x1800063a2  and     r8d, 0FFFh
0x1800063a9  lea     r15, [r8+r9]
0x1800063ad  mov     eax, [rsp+0C8h+var_94]
0x1800063b1  mov     [rsp+0C8h+var_58], rax
0x1800063b6  and     ecx, 0FFFh
0x1800063bc  sub     ecx, edx
0x1800063be  lea     edx, [r10+rcx]
0x1800063c2  mov     rcx, [rsp+0C8h+arg_18]
0x1800063ca  call    GetNewRvaFromRiftTable
0x1800063cf  mov     rdx, [rsp+0C8h+var_58]
0x1800063d4  mov     [r14+rdx*8], eax
0x1800063d8  mov     eax, dword ptr [rsp+0C8h+Size]
0x1800063df  mov     [r14+rdx*8+4], al
0x1800063e4  movzx   ecx, al
0x1800063e7  sub     ecx, 1
0x1800063ea  jz      loc_18000649A
0x1800063f0  sub     ecx, 1
0x1800063f3  jz      loc_18000649A
0x1800063f9  sub     ecx, 1
0x1800063fc  jz      short loc_180006442
0x1800063fe  cmp     ecx, 1
0x180006401  jnz     loc_1800064B6
0x180006407  cmp     r15, [rsp+0C8h+var_60]
0x18000640c  jnb     short loc_180006423
0x18000640e  sub     r15, r13
0x180006411  mov     rax, [rsp+0C8h+arg_20]
0x180006419  mov     ecx, 101h
0x18000641e  or      [r15+rax], cx
0x180006423  add     rbx, 2
0x180006427  mov     [rsp+0C8h+Size], rbx
0x18000642f  dec     r11d
0x180006432  mov     [rsp+0C8h+var_90], r11d
0x180006437  movzx   eax, word ptr [rbx]
0x18000643a  mov     [r14+rdx*8+6], ax
0x180006440  jmp     short loc_1800064B6
0x180006442  mov     rax, [rsp+0C8h+var_88]
0x180006447  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000644b  cmp     r15, rax
0x18000644e  ja      short loc_1800064B6
0x180006450  mov     rax, r15
0x180006453  sub     rax, r13
0x180006456  mov     rcx, [rsp+0C8h+arg_20]
0x18000645e  or      dword ptr [rax+rcx], 1010101h
0x180006465  mov     r11d, [r15]
0x180006468  sub     r11d, [rsp+0C8h+arg_0]
0x180006470  mov     edx, r11d
0x180006473  mov     rcx, [rsp+0C8h+arg_18]
0x18000647b  call    GetNewRvaFromRiftTable
0x180006480  mov     ecx, eax
0x180006482  cmp     eax, r11d
0x180006485  mov     r11, [rsp+0C8h+var_68]
0x18000648a  jz      short loc_1800064B6
0x18000648c  mov     eax, [rsp+0C8h+arg_0]
0x180006493  add     eax, ecx
0x180006495  mov     [r15], eax
0x180006498  jmp     short loc_1800064B6
0x18000649a  cmp     r15, [rsp+0C8h+var_60]
0x18000649f  jnb     short loc_1800064B6
0x1800064a1  sub     r15, r13
0x1800064a4  mov     rax, [rsp+0C8h+arg_20]
0x1800064ac  mov     ecx, 101h
0x1800064b1  or      [r15+rax], cx
0x1800064b6  mov     r15d, [rsp+0C8h+var_94]
0x1800064bb  inc     r15d
0x1800064be  mov     [rsp+0C8h+var_94], r15d
0x1800064c3  mov     edx, [rsp+0C8h+arg_0]
0x1800064ca  mov     r9, [rsp+0C8h+var_50]
0x1800064cf  mov     r10d, [rsp+0C8h+var_80]
0x1800064d4  lea     rcx, [rbx+2]
0x1800064d8  mov     [rsp+0C8h+Size], rcx
0x1800064e0  jmp     loc_180006354
0x1800064e5  mov     ebx, [rsp+0C8h+arg_10]
0x1800064ec  mov     eax, [r12+4]
0x1800064f1  mov     ecx, [rsp+0C8h+var_98]
0x1800064f5  sub     ecx, eax
0x1800064f7  mov     [rsp+0C8h+var_98], ecx
0x1800064fb  add     r12, rax
0x1800064fe  mov     [rsp+0C8h+var_70], r12
0x180006503  jmp     loc_1800062CF
0x180006508  cmp     r15d, 1
0x18000650c  jbe     short loc_18000651E
0x18000650e  lea     eax, [r15-1]
0x180006512  lea     rdx, [r14+rax*8]
0x180006516  mov     rcx, r14
0x180006519  call    RelocQsort
0x18000651e  mov     [rsp+0C8h+var_98], edi
0x180006522  movzx   r10d, word ptr [rsi+14h]
0x180006527  add     r10, 18h
0x18000652b  add     r10, rsi
0x18000652e  movzx   ebx, word ptr [rsi+6]
0x180006532  xor     edx, edx
0x180006534  mov     r9d, [rsp+0C8h+var_7C]
0x180006539  mov     [rsp+0C8h+var_78], edx
0x18000653d  cmp     edx, ebx
0x18000653f  jnb     short loc_1800065AE
0x180006541  lea     rcx, [rdx+rdx*4]
0x180006545  lea     r8, [r10+rcx*8]
0x180006549  cmp     r8, r13
0x18000654c  jb      loc_18000676E
0x180006552  inc     edx
0x180006554  lea     rcx, [rdx+rdx*4]
0x180006558  lea     rax, [r10+rcx*8]
0x18000655c  cmp     r8, rax
0x18000655f  ja      loc_18000676E
0x180006565  cmp     rax, r11
0x180006568  ja      loc_18000676E
0x18000656e  mov     rcx, 2020202020202020h
0x180006578  mov     rax, [r8]
0x18000657b  or      rax, rcx
0x18000657e  mov     rcx, 2020636F6C65722Eh
0x180006588  cmp     rax, rcx
0x18000658b  jnz     short loc_1800065AC
0x18000658d  mov     ecx, [r8+14h]
0x180006591  cmp     r9d, ecx
0x180006594  jb      short loc_1800065AC
0x180006596  mov     r8d, [r8+10h]
0x18000659a  add     r8d, ecx
0x18000659d  cmp     r9d, r8d
0x1800065a0  jnb     short loc_1800065AC
0x1800065a2  mov     edi, r8d
0x1800065a5  sub     edi, r9d
0x1800065a8  mov     [rsp+0C8h+var_98], edi
0x1800065ac  jmp     short loc_180006539
0x1800065ae  and     edi, 0FFFFFFFEh
0x1800065b1  mov     [rsp+0C8h+var_98], edi
0x1800065b5  mov     r9, [rsp+0C8h+var_48]
0x1800065bd  mov     [rsp+0C8h+var_70], r9
0x1800065c2  xor     r8d, r8d
0x1800065c5  mov     [rsp+0C8h+var_74], r8d
0x1800065ca  mov     esi, 0FFFFF000h
0x1800065cf  mov     r12d, 0FFFh
0x1800065d5  movsxd  rdi, edi
0x1800065d8  cmp     rdi, 8
0x1800065dc  jbe     loc_180006691
0x1800065e2  cmp     r8d, r15d
0x1800065e5  jnb     loc_180006691
0x1800065eb  mov     ecx, [r14+r8*8]
0x1800065ef  and     ecx, esi
0x1800065f1  mov     [r9], ecx
0x1800065f4  lea     rdx, [r9+8]
0x1800065f8  mov     [rsp+0C8h+Size], rdx
0x180006600  mov     ebx, edx
0x180006602  add     edi, 0FFFFFFF8h
0x180006605  mov     [rsp+0C8h+var_98], edi
0x180006609  mov     r10, rdx
0x18000660c  test    edi, edi
0x18000660e  jle     short loc_18000667B
0x180006610  cmp     r8d, r15d
0x180006613  jnb     short loc_180006659
0x180006615  mov     eax, [r14+r8*8]
0x180006619  and     eax, esi
0x18000661b  cmp     eax, [r9]
0x18000661e  jnz     short loc_180006659
0x180006620  movzx   ecx, byte ptr [r14+r8*8+4]
0x180006626  shl     cx, 0Ch
0x18000662a  movzx   eax, word ptr [r14+r8*8]
0x18000662f  and     ax, r12w
0x180006633  or      cx, ax
0x180006636  mov     [rdx], cx
0x180006639  lea     rdx, [r10+2]
0x18000663d  mov     r10, rdx
0x180006640  mov     [rsp+0C8h+Size], rdx
0x180006648  sub     edi, 2
0x18000664b  mov     [rsp+0C8h+var_98], edi
0x18000664f  inc     r8d
0x180006652  mov     [rsp+0C8h+var_74], r8d
0x180006657  jmp     short loc_18000660C
0x180006659  test    edi, edi
0x18000665b  jle     short loc_18000667B
0x18000665d  test    r10b, 2
0x180006661  jz      short loc_18000667B
0x180006663  xor     eax, eax
0x180006665  mov     [rdx], ax
0x180006668  lea     rdx, [r10+2]
0x18000666c  mov     [rsp+0C8h+Size], rdx
0x180006674  sub     edi, 2
0x180006677  mov     [rsp+0C8h+var_98], edi
0x18000667b  sub     edx, ebx
0x18000667d  lea     eax, [rdx+8]
0x180006680  mov     [r9+4], eax
0x180006684  add     r9, rax
0x180006687  mov     [rsp+0C8h+var_70], r9
0x18000668c  jmp     loc_1800065D5
0x180006691  jmp     short loc_1800066BF
0x180006693  mov     ebx, eax
0x180006695  xor     edx, edx; dwSize
0x180006697  mov     r8d, 8000h; dwFreeType
0x18000669d  mov     r14, [rsp+0C8h+lpAddress]
0x1800066a5  mov     rcx, r14; lpAddress
0x1800066a8  call    cs:__imp_VirtualFree
0x1800066ae  mov     ecx, ebx; dwExceptionCode
0x1800066b0  xor     r9d, r9d; lpArguments
0x1800066b3  xor     r8d, r8d; nNumberOfArguments
0x1800066b6  xor     edx, edx; dwExceptionFlags
  ... truncated ...
```
