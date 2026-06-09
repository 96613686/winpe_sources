# BCreateRleBitmap

- ea: `0x180006058`
- end: `0x1800061b8`
- name: `BCreateRleBitmap`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061c0`

## callees

- `0x180001ee0`
- `0x180006058`
- `0x18005c434`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000618c`
- `KERNEL32!LocalFree` at `0x18000618c`
- `KERNEL32!LocalAlloc` at `0x180006137`
- `KERNEL32!LocalAlloc` at `0x180006137`
- `GDI32!EngUnlockSurface` at `0x180006168`
- `GDI32!EngUnlockSurface` at `0x180006168`
- `GDI32!EngCopyBits` at `0x180006127`
- `GDI32!EngCopyBits` at `0x180006127`
- `GDI32!EngLockSurface` at `0x1800060f9`
- `GDI32!EngLockSurface` at `0x1800060f9`
- `GDI32!EngCreateBitmap` at `0x1800060d0`
- `GDI32!EngCreateBitmap` at `0x1800060d0`
- `GDI32!EngDeleteSurface` at `0x180006171`
- `GDI32!EngDeleteSurface` at `0x180006171`
- `GDI32!EngAssociateSurface` at `0x1800060ec`
- `GDI32!EngAssociateSurface` at `0x1800060ec`

## pseudocode

```c
__int64 __fastcall BCreateRleBitmap(__int64 a1, SURFOBJ *a2, __int64 a3, __int64 a4)
{
  ULONG v7; // r8d
  unsigned int v8; // edi
  LONG cy; // eax
  int v10; // edx
  SIZEL sizlBitmap; // rcx
  HBITMAP Bitmap; // rax
  HSURF v13; // rbp
  SURFOBJ *v14; // rbx
  HLOCAL v15; // rax
  void *v16; // rcx
  POINTL pptlSrc; // [rsp+30h] [rbp-48h] BYREF
  RECTL prclDest; // [rsp+38h] [rbp-40h] BYREF

  if ( a2->iBitmapFormat == 7 )
  {
    v7 = 2;
    goto LABEL_5;
  }
  if ( a2->iBitmapFormat == 8 )
  {
    v7 = 3;
LABEL_5:
    v8 = 0;
    cy = a2->sizlBitmap.cy;
    prclDest.right = a2->sizlBitmap.cx;
    v10 = *(_DWORD *)a1 * prclDest.right;
    sizlBitmap = a2->sizlBitmap;
    *(_QWORD *)&prclDest.left = 0;
    prclDest.bottom = cy;
    pptlSrc = 0;
    Bitmap = EngCreateBitmap(sizlBitmap, (((unsigned int)(v10 + 7) >> 3) + 3) & 0xFFFFFFFC, v7, 0xBu, 0);
    v13 = (HSURF)Bitmap;
    if ( Bitmap )
    {
      if ( EngAssociateSurface((HSURF)Bitmap, *(HDEV *)(a4 + 16), 0) )
      {
        v14 = EngLockSurface(v13);
        if ( v14 )
        {
          if ( EngCopyBits(v14, a2, 0, 0, &prclDest, &pptlSrc) )
          {
            v15 = LocalAlloc(0x40u, v14->cjBits);
            *(_QWORD *)(a1 + 40) = v15;
            if ( v15 )
            {
              *(_QWORD *)(a1 + 48) = v15;
              *(_DWORD *)(a1 + 56) = v14->lDelta;
              memcpy_0(v15, v14->pvBits, v14->cjBits);
              v8 = 1;
            }
          }
          EngUnlockSurface(v14);
        }
      }
      if ( EngDeleteSurface(v13) )
      {
        if ( v8 )
          return v8;
      }
      else
      {
        v8 = 0;
      }
    }
    v16 = *(void **)(a1 + 40);
    if ( v16 )
      LocalFree(v16);
    *(_QWORD *)(a1 + 40) = 0;
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180006058  push    rbx
0x18000605a  push    rbp
0x18000605b  push    rsi
0x18000605c  push    rdi
0x18000605d  push    r14
0x18000605f  sub     rsp, 50h
0x180006063  mov     rax, cs:__security_cookie
0x18000606a  xor     rax, rsp
0x18000606d  mov     [rsp+78h+var_30], rax
0x180006072  cmp     dword ptr [rdx+48h], 7
0x180006076  mov     rbx, r9
0x180006079  mov     r14, rdx
0x18000607c  mov     rsi, rcx
0x18000607f  jnz     short loc_180006089
0x180006081  mov     r8d, 2
0x180006087  jmp     short loc_180006099
0x180006089  cmp     dword ptr [rdx+48h], 8
0x18000608d  jnz     loc_18000619E
0x180006093  mov     r8d, 3; iFormat
0x180006099  mov     edx, [rdx+20h]
0x18000609c  xor     edi, edi
0x18000609e  mov     eax, [r14+24h]
0x1800060a2  mov     [rsp+78h+prclDest.right], edx
0x1800060a6  imul    edx, [rcx]
0x1800060a9  mov     rcx, [r14+20h]; sizl
0x1800060ad  lea     r9d, [rdi+0Bh]; fl
0x1800060b1  mov     qword ptr [rsp+78h+prclDest.left], rdi
0x1800060b6  mov     [rsp+78h+prclDest.bottom], eax
0x1800060ba  mov     qword ptr [rsp+78h+var_48.x], rdi
0x1800060bf  add     edx, 7
0x1800060c2  mov     [rsp+78h+pvBits], rdi; pvBits
0x1800060c7  shr     edx, 3
0x1800060ca  add     edx, 3
0x1800060cd  and     edx, 0FFFFFFFCh; lWidth
0x1800060d0  call    cs:__imp_EngCreateBitmap
0x1800060d6  mov     rbp, rax
0x1800060d9  test    rax, rax
0x1800060dc  jz      loc_180006183
0x1800060e2  mov     rdx, [rbx+10h]; hdev
0x1800060e6  xor     r8d, r8d; flHooks
0x1800060e9  mov     rcx, rax; hsurf
0x1800060ec  call    cs:__imp_EngAssociateSurface
0x1800060f2  test    eax, eax
0x1800060f4  jz      short loc_18000616E
0x1800060f6  mov     rcx, rbp; hsurf
0x1800060f9  call    cs:__imp_EngLockSurface
0x1800060ff  mov     rbx, rax
0x180006102  test    rax, rax
0x180006105  jz      short loc_18000616E
0x180006107  lea     rax, [rsp+78h+var_48]
0x18000610c  xor     r9d, r9d; pxlo
0x18000610f  mov     [rsp+78h+pptlSrc], rax; pptlSrc
0x180006114  xor     r8d, r8d; pco
0x180006117  lea     rax, [rsp+78h+prclDest]
0x18000611c  mov     rdx, r14; psoSrc
0x18000611f  mov     rcx, rbx; psoDest
0x180006122  mov     [rsp+78h+pvBits], rax; prclDest
0x180006127  call    cs:__imp_EngCopyBits
0x18000612d  test    eax, eax
0x18000612f  jz      short loc_180006165
0x180006131  mov     edx, [rbx+28h]; uBytes
0x180006134  lea     ecx, [rdi+40h]; uFlags
0x180006137  call    cs:__imp_LocalAlloc
0x18000613d  mov     [rsi+28h], rax
0x180006141  mov     rcx, rax; void *
0x180006144  test    rax, rax
0x180006147  jz      short loc_180006165
0x180006149  mov     [rsi+30h], rax
0x18000614d  mov     eax, [rbx+40h]
0x180006150  mov     [rsi+38h], eax
0x180006153  mov     r8d, [rbx+28h]; Size
0x180006157  mov     rdx, [rbx+30h]; Src
0x18000615b  call    memcpy_0
0x180006160  mov     edi, 1
0x180006165  mov     rcx, rbx; pso
0x180006168  call    cs:__imp_EngUnlockSurface
0x18000616e  mov     rcx, rbp; hsurf
0x180006171  call    cs:__imp_EngDeleteSurface
0x180006177  test    eax, eax
0x180006179  jnz     short loc_18000617F
0x18000617b  xor     edi, edi
0x18000617d  jmp     short loc_180006183
0x18000617f  test    edi, edi
0x180006181  jnz     short loc_18000619A
0x180006183  mov     rcx, [rsi+28h]; hMem
0x180006187  test    rcx, rcx
0x18000618a  jz      short loc_180006192
0x18000618c  call    cs:__imp_LocalFree
0x180006192  mov     qword ptr [rsi+28h], 0
0x18000619a  mov     eax, edi
0x18000619c  jmp     short loc_1800061A0
0x18000619e  xor     eax, eax
0x1800061a0  mov     rcx, [rsp+78h+var_30]
0x1800061a5  xor     rcx, rsp; StackCookie
0x1800061a8  call    __security_check_cookie
0x1800061ad  add     rsp, 50h
0x1800061b1  pop     r14
0x1800061b3  pop     rdi
0x1800061b4  pop     rsi
0x1800061b5  pop     rbp
0x1800061b6  pop     rbx
0x1800061b7  retn
```
