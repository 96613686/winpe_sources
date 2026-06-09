# HCreateBitmapSurfaceWithOemPlugin

- ea: `0x18004a10c`
- end: `0x18004a28b`
- name: `HCreateBitmapSurfaceWithOemPlugin`
- size: `383`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180049c74`

## callees

- `0x18004a10c`
- `0x180075010`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x18004a221`
- `GDI32!EngCreateBitmap` at `0x18004a221`

## pseudocode

```c
__int64 __fastcall HCreateBitmapSurfaceWithOemPlugin(
        __int64 a1,
        ULONG a2,
        unsigned int a3,
        HBITMAP *a4,
        SIZEL *a5,
        int *a6)
{
  int v6; // ebx
  unsigned int *v7; // rdi
  int v8; // r8d
  int v12; // ebx
  int v13; // r8d
  _QWORD *v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // r11
  __int64 v17; // rax
  unsigned int v18; // edi
  __int64 result; // rax
  HBITMAP Bitmap; // rax
  int *v21; // r8
  int v22; // ecx
  SIZEL sizl; // [rsp+60h] [rbp+8h]
  unsigned int v24; // [rsp+70h] [rbp+18h] BYREF

  v24 = a3;
  v6 = *(_DWORD *)(a1 + 112);
  v7 = (unsigned int *)(a1 + 4076);
  v8 = *(__int16 *)(a1 + 2600);
  v24 = 0;
  sizl = *(SIZEL *)(a1 + 4076);
  v12 = v6 & 0x80;
  if ( v12 )
  {
    v13 = *(_DWORD *)(a1 + 4080) * v8;
  }
  else
  {
    v13 = *v7 * v8;
    v7 = (unsigned int *)(a1 + 4080);
  }
  v14 = *(_QWORD **)(a1 + 1888);
  v15 = (v13 + 7) / 8;
  if ( !v14 )
    return 2147500033LL;
  v16 = v14[9];
  if ( !v16 )
    return 2147500033LL;
  v17 = v14[10] - *(_QWORD *)&IID_IPrintOemUni3.Data1;
  if ( !v17 )
    v17 = v14[11] - *(_QWORD *)IID_IPrintOemUni3.Data4;
  if ( v17 )
    return 2147500034LL;
  v18 = *v7;
  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int *))(*(_QWORD *)v16 + 232LL))(
             v16,
             a1,
             a2,
             v15,
             v18,
             v18,
             &v24);
  if ( !(_DWORD)result )
  {
    if ( v24
      && v24 <= v18
      && (!v12 ? (sizl.cy = v24) : (sizl.cx = v24), Bitmap = EngCreateBitmap(sizl, v15, a2, 0xBu, 0),
                                                    (*a4 = Bitmap) != 0) )
    {
      v21 = a6;
      v22 = v18 / v24;
      *a6 = v18 / v24;
      if ( v18 % v24 )
        *v21 = v22 + 1;
      *a5 = sizl;
      return 0;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004a10c  mov     rax, rsp
0x18004a10f  mov     [rax+10h], rbx
0x18004a113  mov     [rax+20h], rbp
0x18004a117  mov     [rax+18h], r8d
0x18004a11b  push    rsi
0x18004a11c  push    rdi
0x18004a11d  push    r14
0x18004a11f  sub     rsp, 40h
0x18004a123  mov     ebx, [rcx+70h]
0x18004a126  lea     rdi, [rcx+0FECh]
0x18004a12d  movsx   r8d, word ptr [rcx+0A28h]
0x18004a135  mov     r10, rcx
0x18004a138  mov     dword ptr [rax+18h], 0
0x18004a13f  lea     r11, [rcx+0FF0h]
0x18004a146  mov     rax, [rdi]
0x18004a149  mov     r14, r9
0x18004a14c  mov     qword ptr [rsp+58h+sizl.cx], rax
0x18004a151  mov     ebp, edx
0x18004a153  mov     ecx, 8
0x18004a158  and     ebx, 80h
0x18004a15e  jz      short loc_18004A166
0x18004a160  imul    r8d, [r11]
0x18004a164  jmp     short loc_18004A16D
0x18004a166  imul    r8d, [rdi]
0x18004a16a  mov     rdi, r11
0x18004a16d  lea     eax, [r8+7]
0x18004a171  cdq
0x18004a172  idiv    ecx
0x18004a174  mov     rcx, [r10+760h]
0x18004a17b  mov     esi, eax
0x18004a17d  test    rcx, rcx
0x18004a180  jz      loc_18004A273
0x18004a186  mov     r11, [rcx+48h]
0x18004a18a  test    r11, r11
0x18004a18d  jz      loc_18004A273
0x18004a193  mov     rax, [rcx+50h]
0x18004a197  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x18004a19e  jnz     short loc_18004A1AB
0x18004a1a0  mov     rax, [rcx+58h]
0x18004a1a4  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x18004a1ab  test    rax, rax
0x18004a1ae  jnz     loc_18004A26C
0x18004a1b4  mov     edi, [rdi]
0x18004a1b6  lea     rcx, [rsp+58h+arg_10]
0x18004a1bb  mov     rax, [r11]
0x18004a1be  mov     r9d, esi
0x18004a1c1  mov     [rsp+58h+var_28], rcx
0x18004a1c6  mov     r8d, ebp
0x18004a1c9  mov     [rsp+58h+var_30], edi
0x18004a1cd  mov     rdx, r10
0x18004a1d0  mov     rcx, r11
0x18004a1d3  mov     dword ptr [rsp+58h+pvBits], edi
0x18004a1d7  mov     rax, [rax+0E8h]
0x18004a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1e3  test    eax, eax
0x18004a1e5  jnz     loc_18004A278
0x18004a1eb  mov     eax, [rsp+58h+arg_10]
0x18004a1ef  test    eax, eax
0x18004a1f1  jz      short loc_18004A265
0x18004a1f3  cmp     eax, edi
0x18004a1f5  ja      short loc_18004A265
0x18004a1f7  test    ebx, ebx
0x18004a1f9  jz      short loc_18004A201
0x18004a1fb  mov     [rsp+58h+sizl.cx], eax
0x18004a1ff  jmp     short loc_18004A205
0x18004a201  mov     [rsp+58h+sizl.cy], eax
0x18004a205  mov     rbx, qword ptr [rsp+58h+sizl.cx]
0x18004a20a  mov     r9d, 0Bh; fl
0x18004a210  mov     rcx, rbx; sizl
0x18004a213  mov     [rsp+58h+pvBits], 0; pvBits
0x18004a21c  mov     r8d, ebp; iFormat
0x18004a21f  mov     edx, esi; lWidth
0x18004a221  call    cs:__imp_EngCreateBitmap
0x18004a227  mov     [r14], rax
0x18004a22a  test    rax, rax
0x18004a22d  jz      short loc_18004A265
0x18004a22f  mov     r8, [rsp+58h+arg_28]
0x18004a237  xor     edx, edx
0x18004a239  mov     eax, edi
0x18004a23b  div     [rsp+58h+arg_10]
0x18004a23f  xor     edx, edx
0x18004a241  mov     ecx, eax
0x18004a243  mov     [r8], eax
0x18004a246  mov     eax, edi
0x18004a248  div     [rsp+58h+arg_10]
0x18004a24c  test    edx, edx
0x18004a24e  jz      short loc_18004A256
0x18004a250  lea     eax, [rcx+1]
0x18004a253  mov     [r8], eax
0x18004a256  mov     rax, [rsp+58h+arg_20]
0x18004a25e  mov     [rax], rbx
0x18004a261  xor     eax, eax
0x18004a263  jmp     short loc_18004A278
0x18004a265  mov     eax, 80004005h
0x18004a26a  jmp     short loc_18004A278
0x18004a26c  mov     eax, 80004002h
0x18004a271  jmp     short loc_18004A278
0x18004a273  mov     eax, 80004001h
0x18004a278  mov     rbx, [rsp+58h+arg_8]
0x18004a27d  mov     rbp, [rsp+58h+arg_18]
0x18004a282  add     rsp, 40h
0x18004a286  pop     r14
0x18004a288  pop     rdi
0x18004a289  pop     rsi
0x18004a28a  retn
```
