# COleObject::CreateDib(HDC__ *)

- ea: `0x1801f7650`
- end: `0x1801f77c5`
- name: `?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z`
- size: `373`
- prototype: `void(COleObject *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801f77cc`

## callees

- `0x18013c90a`
- `0x1801f7650`
- `0x180205240`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801f77ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801f77ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801f768a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801f768a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801f7711`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801f7711`

## pseudocode

```c
void __fastcall COleObject::CreateDib(void **this, HDC a2)
{
  unsigned int v4; // esi
  void *v5; // rcx
  BITMAPINFO *v6; // rax
  BITMAPINFO *v7; // rbx
  unsigned int biBitCount; // eax
  int v9; // r14d
  unsigned int biWidth; // ebp
  int v11; // esi
  LONG biHeight; // r15d
  HBITMAP v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // ecx
  void *ppvBits; // [rsp+80h] [rbp+8h] BYREF

  v4 = CW32System::GlobalSize(this[14]);
  if ( v4 >= 0x2C )
  {
    v5 = this[14];
    ppvBits = 0;
    v6 = (BITMAPINFO *)GlobalLock(v5);
    v7 = v6;
    if ( v6 )
    {
      biBitCount = v6->bmiHeader.biBitCount;
      if ( (unsigned __int16)biBitCount > 8u )
      {
        biWidth = v7->bmiHeader.biWidth;
        v9 = 0;
      }
      else
      {
        if ( !(_WORD)biBitCount )
        {
LABEL_19:
          GlobalUnlock(v7);
          return;
        }
        v9 = 1 << biBitCount;
        biWidth = 8 / biBitCount * ((((v7->bmiHeader.biWidth * biBitCount + 7) >> 3) + 3) & 0xFFFFFFFC);
      }
      v11 = v4 - (4 * v9 + 40);
      if ( v11 > 0 )
      {
        biHeight = v7->bmiHeader.biHeight;
        v13 = CreateDIBSection(a2, v7, 0, &ppvBits, 0, 0);
        this[15] = v13;
        if ( v13 )
        {
          v16 = v7->bmiHeader.biBitCount;
          v17 = biWidth * biHeight;
          if ( v9 )
            v18 = v17 / (8 / v16);
          else
            v18 = v17 * (v16 >> 3);
          if ( v18 <= v11 )
            memmove_0(ppvBits, &v7->bmiColors[v9], (int)v18);
        }
        else
        {
          v14 = (unsigned __int64)this[6] & -(__int64)(*((_WORD *)this[6] + 28) != 0);
          if ( (-(__int64)(v14 != 0) & (v14 + 48)) != 0 )
          {
            v15 = v14 + 60;
            if ( !v14 )
              v15 = 12;
            *(_DWORD *)v15 |= 0x40u;
          }
          *((_WORD *)this + 77) &= ~0x20u;
        }
      }
      goto LABEL_19;
    }
  }
}

```

## disassembly

```asm
0x1801f7650  push    rbx
0x1801f7652  push    rbp
0x1801f7653  push    rsi
0x1801f7654  push    rdi
0x1801f7655  push    r12
0x1801f7657  push    r13
0x1801f7659  push    r14
0x1801f765b  push    r15
0x1801f765d  sub     rsp, 38h
0x1801f7661  mov     rdi, rcx
0x1801f7664  mov     r12, rdx
0x1801f7667  mov     rcx, [rcx+70h]; void *
0x1801f766b  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x1801f7670  mov     esi, eax
0x1801f7672  cmp     eax, 2Ch ; ','
0x1801f7675  jb      loc_1801F77B4
0x1801f767b  mov     rcx, [rdi+70h]; hMem
0x1801f767f  xor     r13d, r13d
0x1801f7682  mov     [rsp+78h+ppvBits], r13
0x1801f768a  call    cs:__imp_GlobalLock
0x1801f7690  mov     rbx, rax
0x1801f7693  test    rax, rax
0x1801f7696  jz      loc_1801F77B4
0x1801f769c  movzx   eax, word ptr [rax+0Eh]
0x1801f76a0  lea     r8d, [r13+8]
0x1801f76a4  cmp     ax, r8w
0x1801f76a8  ja      short loc_1801F76DA
0x1801f76aa  test    ax, ax
0x1801f76ad  jz      loc_1801F77AB
0x1801f76b3  mov     ecx, eax
0x1801f76b5  lea     r14d, [r13+1]
0x1801f76b9  mov     ebp, eax
0x1801f76bb  shl     r14d, cl
0x1801f76be  imul    ebp, [rbx+4]
0x1801f76c2  xor     edx, edx
0x1801f76c4  mov     eax, r8d
0x1801f76c7  div     ecx
0x1801f76c9  add     ebp, 7
0x1801f76cc  shr     ebp, 3
0x1801f76cf  add     ebp, 3
0x1801f76d2  and     ebp, 0FFFFFFFCh
0x1801f76d5  imul    ebp, eax
0x1801f76d8  jmp     short loc_1801F76E0
0x1801f76da  mov     ebp, [rbx+4]
0x1801f76dd  mov     r14d, r13d
0x1801f76e0  lea     eax, ds:28h[r14*4]
0x1801f76e8  sub     esi, eax
0x1801f76ea  test    esi, esi
0x1801f76ec  jle     loc_1801F77AB
0x1801f76f2  mov     r15d, [rbx+8]
0x1801f76f6  lea     r9, [rsp+78h+ppvBits]; ppvBits
0x1801f76fe  mov     [rsp+78h+offset], r13d; offset
0x1801f7703  xor     r8d, r8d; usage
0x1801f7706  mov     rdx, rbx; pbmi
0x1801f7709  mov     [rsp+78h+hSection], r13; hSection
0x1801f770e  mov     rcx, r12; hdc
0x1801f7711  call    cs:__imp_CreateDIBSection
0x1801f7717  mov     [rdi+78h], rax
0x1801f771b  test    rax, rax
0x1801f771e  jnz     short loc_1801F7764
0x1801f7720  mov     rcx, [rdi+30h]
0x1801f7724  movzx   eax, word ptr [rcx+38h]
0x1801f7728  neg     ax
0x1801f772b  sbb     rdx, rdx
0x1801f772e  and     rdx, rcx
0x1801f7731  mov     rax, rdx
0x1801f7734  neg     rax
0x1801f7737  sbb     rax, rax
0x1801f773a  lea     rcx, [rdx+30h]
0x1801f773e  test    rcx, rax
0x1801f7741  jz      short loc_1801F7756
0x1801f7743  test    rdx, rdx
0x1801f7746  lea     rax, [rdx+3Ch]
0x1801f774a  mov     ecx, 0Ch
0x1801f774f  cmovz   rax, rcx
0x1801f7753  or      dword ptr [rax], 40h
0x1801f7756  mov     eax, 0FFDFh
0x1801f775b  and     [rdi+9Ah], ax
0x1801f7762  jmp     short loc_1801F77AB
0x1801f7764  movzx   ecx, word ptr [rbx+0Eh]
0x1801f7768  imul    r15d, ebp
0x1801f776c  test    r14d, r14d
0x1801f776f  jz      short loc_1801F7785
0x1801f7771  xor     edx, edx
0x1801f7773  lea     eax, [rdx+8]
0x1801f7776  div     ecx
0x1801f7778  xor     edx, edx
0x1801f777a  mov     ecx, eax
0x1801f777c  mov     eax, r15d
0x1801f777f  div     ecx
0x1801f7781  mov     ecx, eax
0x1801f7783  jmp     short loc_1801F778C
0x1801f7785  shr     ecx, 3
0x1801f7788  imul    ecx, r15d
0x1801f778c  cmp     ecx, esi
0x1801f778e  ja      short loc_1801F77AB
0x1801f7790  movsxd  r8, ecx; Size
0x1801f7793  mov     rcx, [rsp+78h+ppvBits]; void *
0x1801f779b  movsxd  rax, r14d
0x1801f779e  add     rax, 0Ah
0x1801f77a2  lea     rdx, [rbx+rax*4]; Src
0x1801f77a6  call    memmove_0
0x1801f77ab  mov     rcx, rbx; hMem
0x1801f77ae  call    cs:__imp_GlobalUnlock
0x1801f77b4  add     rsp, 38h
0x1801f77b8  pop     r15
0x1801f77ba  pop     r14
0x1801f77bc  pop     r13
0x1801f77be  pop     r12
0x1801f77c0  pop     rdi
0x1801f77c1  pop     rsi
0x1801f77c2  pop     rbp
0x1801f77c3  pop     rbx
0x1801f77c4  retn
```
