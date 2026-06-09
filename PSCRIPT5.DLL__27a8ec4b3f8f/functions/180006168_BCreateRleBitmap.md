# BCreateRleBitmap

- ea: `0x180006168`
- end: `0x1800062fd`
- name: `BCreateRleBitmap`
- size: `405`
- prototype: `__int64 __fastcall(__int64, SURFOBJ *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006304`

## callees

- `0x180001f20`
- `0x180006168`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800062ca`
- `KERNEL32!LocalFree` at `0x1800062ca`
- `KERNEL32!LocalAlloc` at `0x180006263`
- `KERNEL32!LocalAlloc` at `0x180006263`
- `GDI32!EngUnlockSurface` at `0x18000629a`
- `GDI32!EngUnlockSurface` at `0x18000629a`
- `GDI32!EngCopyBits` at `0x18000624d`
- `GDI32!EngCopyBits` at `0x18000624d`
- `GDI32!EngLockSurface` at `0x180006219`
- `GDI32!EngLockSurface` at `0x180006219`
- `GDI32!EngCreateBitmap` at `0x1800061e0`
- `GDI32!EngCreateBitmap` at `0x1800061e0`
- `GDI32!EngDeleteSurface` at `0x1800062a9`
- `GDI32!EngDeleteSurface` at `0x1800062a9`
- `GDI32!EngAssociateSurface` at `0x180006202`
- `GDI32!EngAssociateSurface` at `0x180006202`

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
0x180006168  push    rbx
0x18000616a  push    rbp
0x18000616b  push    rsi
0x18000616c  push    rdi
0x18000616d  push    r14
0x18000616f  sub     rsp, 50h
0x180006173  mov     rax, cs:__security_cookie
0x18000617a  xor     rax, rsp
0x18000617d  mov     [rsp+78h+var_30], rax
0x180006182  cmp     dword ptr [rdx+48h], 7
0x180006186  mov     rbx, r9
0x180006189  mov     r14, rdx
0x18000618c  mov     rsi, rcx
0x18000618f  jnz     short loc_180006199
0x180006191  mov     r8d, 2
0x180006197  jmp     short loc_1800061A9
0x180006199  cmp     dword ptr [rdx+48h], 8
0x18000619d  jnz     loc_1800062E2
0x1800061a3  mov     r8d, 3; iFormat
0x1800061a9  mov     edx, [rdx+20h]
0x1800061ac  xor     edi, edi
0x1800061ae  mov     eax, [r14+24h]
0x1800061b2  mov     [rsp+78h+prclDest.right], edx
0x1800061b6  imul    edx, [rcx]
0x1800061b9  mov     rcx, [r14+20h]; sizl
0x1800061bd  lea     r9d, [rdi+0Bh]; fl
0x1800061c1  mov     qword ptr [rsp+78h+prclDest.left], rdi
0x1800061c6  mov     [rsp+78h+prclDest.bottom], eax
0x1800061ca  mov     qword ptr [rsp+78h+var_48.x], rdi
0x1800061cf  add     edx, 7
0x1800061d2  mov     [rsp+78h+pvBits], rdi; pvBits
0x1800061d7  shr     edx, 3
0x1800061da  add     edx, 3
0x1800061dd  and     edx, 0FFFFFFFCh; lWidth
0x1800061e0  call    cs:__imp_EngCreateBitmap
0x1800061e7  nop     dword ptr [rax+rax+00h]
0x1800061ec  mov     rbp, rax
0x1800061ef  test    rax, rax
0x1800061f2  jz      loc_1800062C1
0x1800061f8  mov     rdx, [rbx+10h]; hdev
0x1800061fc  xor     r8d, r8d; flHooks
0x1800061ff  mov     rcx, rax; hsurf
0x180006202  call    cs:__imp_EngAssociateSurface
0x180006209  nop     dword ptr [rax+rax+00h]
0x18000620e  test    eax, eax
0x180006210  jz      loc_1800062A6
0x180006216  mov     rcx, rbp; hsurf
0x180006219  call    cs:__imp_EngLockSurface
0x180006220  nop     dword ptr [rax+rax+00h]
0x180006225  mov     rbx, rax
0x180006228  test    rax, rax
0x18000622b  jz      short loc_1800062A6
0x18000622d  lea     rax, [rsp+78h+var_48]
0x180006232  xor     r9d, r9d; pxlo
0x180006235  mov     [rsp+78h+pptlSrc], rax; pptlSrc
0x18000623a  xor     r8d, r8d; pco
0x18000623d  lea     rax, [rsp+78h+prclDest]
0x180006242  mov     rdx, r14; psoSrc
0x180006245  mov     rcx, rbx; psoDest
0x180006248  mov     [rsp+78h+pvBits], rax; prclDest
0x18000624d  call    cs:__imp_EngCopyBits
0x180006254  nop     dword ptr [rax+rax+00h]
0x180006259  test    eax, eax
0x18000625b  jz      short loc_180006297
0x18000625d  mov     edx, [rbx+28h]; uBytes
0x180006260  lea     ecx, [rdi+40h]; uFlags
0x180006263  call    cs:__imp_LocalAlloc
0x18000626a  nop     dword ptr [rax+rax+00h]
0x18000626f  mov     [rsi+28h], rax
0x180006273  mov     rcx, rax; void *
0x180006276  test    rax, rax
0x180006279  jz      short loc_180006297
0x18000627b  mov     [rsi+30h], rax
0x18000627f  mov     eax, [rbx+40h]
0x180006282  mov     [rsi+38h], eax
0x180006285  mov     r8d, [rbx+28h]; Size
0x180006289  mov     rdx, [rbx+30h]; Src
0x18000628d  call    memcpy_0
0x180006292  mov     edi, 1
0x180006297  mov     rcx, rbx; pso
0x18000629a  call    cs:__imp_EngUnlockSurface
0x1800062a1  nop     dword ptr [rax+rax+00h]
0x1800062a6  mov     rcx, rbp; hsurf
0x1800062a9  call    cs:__imp_EngDeleteSurface
0x1800062b0  nop     dword ptr [rax+rax+00h]
0x1800062b5  test    eax, eax
0x1800062b7  jnz     short loc_1800062BD
0x1800062b9  xor     edi, edi
0x1800062bb  jmp     short loc_1800062C1
0x1800062bd  test    edi, edi
0x1800062bf  jnz     short loc_1800062DE
0x1800062c1  mov     rcx, [rsi+28h]; hMem
0x1800062c5  test    rcx, rcx
0x1800062c8  jz      short loc_1800062D6
0x1800062ca  call    cs:__imp_LocalFree
0x1800062d1  nop     dword ptr [rax+rax+00h]
0x1800062d6  mov     qword ptr [rsi+28h], 0
0x1800062de  mov     eax, edi
0x1800062e0  jmp     short loc_1800062E4
0x1800062e2  xor     eax, eax
0x1800062e4  mov     rcx, [rsp+78h+var_30]
0x1800062e9  xor     rcx, rsp; StackCookie
0x1800062ec  call    __security_check_cookie
0x1800062f1  add     rsp, 50h
0x1800062f5  pop     r14
0x1800062f7  pop     rdi
0x1800062f8  pop     rsi
0x1800062f9  pop     rbp
0x1800062fa  pop     rbx
0x1800062fb  retn
```
