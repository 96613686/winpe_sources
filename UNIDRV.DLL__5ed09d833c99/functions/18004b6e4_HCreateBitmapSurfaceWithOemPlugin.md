# HCreateBitmapSurfaceWithOemPlugin

- ea: `0x18004b6e4`
- end: `0x18004b86a`
- name: `HCreateBitmapSurfaceWithOemPlugin`
- size: `390`
- prototype: `__int64 __fastcall(__int64, ULONG, unsigned int, HBITMAP *, SIZEL *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004b23c`

## callees

- `0x18004b6e4`
- `0x180077010`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x18004b7f9`
- `GDI32!EngCreateBitmap` at `0x18004b7f9`

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
0x18004b6e4  mov     rax, rsp
0x18004b6e7  mov     [rax+10h], rbx
0x18004b6eb  mov     [rax+20h], rbp
0x18004b6ef  mov     [rax+18h], r8d
0x18004b6f3  push    rsi
0x18004b6f4  push    rdi
0x18004b6f5  push    r14
0x18004b6f7  sub     rsp, 40h
0x18004b6fb  mov     ebx, [rcx+70h]
0x18004b6fe  lea     rdi, [rcx+0FECh]
0x18004b705  movsx   r8d, word ptr [rcx+0A28h]
0x18004b70d  mov     r10, rcx
0x18004b710  mov     dword ptr [rax+18h], 0
0x18004b717  lea     r11, [rcx+0FF0h]
0x18004b71e  mov     rax, [rdi]
0x18004b721  mov     r14, r9
0x18004b724  mov     qword ptr [rsp+58h+sizl.cx], rax
0x18004b729  mov     ebp, edx
0x18004b72b  mov     ecx, 8
0x18004b730  and     ebx, 80h
0x18004b736  jz      short loc_18004B73E
0x18004b738  imul    r8d, [r11]
0x18004b73c  jmp     short loc_18004B745
0x18004b73e  imul    r8d, [rdi]
0x18004b742  mov     rdi, r11
0x18004b745  lea     eax, [r8+7]
0x18004b749  cdq
0x18004b74a  idiv    ecx
0x18004b74c  mov     rcx, [r10+760h]
0x18004b753  mov     esi, eax
0x18004b755  test    rcx, rcx
0x18004b758  jz      loc_18004B851
0x18004b75e  mov     r11, [rcx+48h]
0x18004b762  test    r11, r11
0x18004b765  jz      loc_18004B851
0x18004b76b  mov     rax, [rcx+50h]
0x18004b76f  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x18004b776  jnz     short loc_18004B783
0x18004b778  mov     rax, [rcx+58h]
0x18004b77c  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x18004b783  test    rax, rax
0x18004b786  jnz     loc_18004B84A
0x18004b78c  mov     edi, [rdi]
0x18004b78e  lea     rcx, [rsp+58h+arg_10]
0x18004b793  mov     rax, [r11]
0x18004b796  mov     r9d, esi
0x18004b799  mov     [rsp+58h+var_28], rcx
0x18004b79e  mov     r8d, ebp
0x18004b7a1  mov     [rsp+58h+var_30], edi
0x18004b7a5  mov     rdx, r10
0x18004b7a8  mov     rcx, r11
0x18004b7ab  mov     dword ptr [rsp+58h+pvBits], edi
0x18004b7af  mov     rax, [rax+0E8h]
0x18004b7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7bb  test    eax, eax
0x18004b7bd  jnz     loc_18004B856
0x18004b7c3  mov     eax, [rsp+58h+arg_10]
0x18004b7c7  test    eax, eax
0x18004b7c9  jz      short loc_18004B843
0x18004b7cb  cmp     eax, edi
0x18004b7cd  ja      short loc_18004B843
0x18004b7cf  test    ebx, ebx
0x18004b7d1  jz      short loc_18004B7D9
0x18004b7d3  mov     [rsp+58h+sizl.cx], eax
0x18004b7d7  jmp     short loc_18004B7DD
0x18004b7d9  mov     [rsp+58h+sizl.cy], eax
0x18004b7dd  mov     rbx, qword ptr [rsp+58h+sizl.cx]
0x18004b7e2  mov     r9d, 0Bh; fl
0x18004b7e8  mov     rcx, rbx; sizl
0x18004b7eb  mov     [rsp+58h+pvBits], 0; pvBits
0x18004b7f4  mov     r8d, ebp; iFormat
0x18004b7f7  mov     edx, esi; lWidth
0x18004b7f9  call    cs:__imp_EngCreateBitmap
0x18004b800  nop     dword ptr [rax+rax+00h]
0x18004b805  mov     [r14], rax
0x18004b808  test    rax, rax
0x18004b80b  jz      short loc_18004B843
0x18004b80d  mov     r8, [rsp+58h+arg_28]
0x18004b815  xor     edx, edx
0x18004b817  mov     eax, edi
0x18004b819  div     [rsp+58h+arg_10]
0x18004b81d  xor     edx, edx
0x18004b81f  mov     ecx, eax
0x18004b821  mov     [r8], eax
0x18004b824  mov     eax, edi
0x18004b826  div     [rsp+58h+arg_10]
0x18004b82a  test    edx, edx
0x18004b82c  jz      short loc_18004B834
0x18004b82e  lea     eax, [rcx+1]
0x18004b831  mov     [r8], eax
0x18004b834  mov     rax, [rsp+58h+arg_20]
0x18004b83c  mov     [rax], rbx
0x18004b83f  xor     eax, eax
0x18004b841  jmp     short loc_18004B856
0x18004b843  mov     eax, 80004005h
0x18004b848  jmp     short loc_18004B856
0x18004b84a  mov     eax, 80004002h
0x18004b84f  jmp     short loc_18004B856
0x18004b851  mov     eax, 80004001h
0x18004b856  mov     rbx, [rsp+58h+arg_8]
0x18004b85b  mov     rbp, [rsp+58h+arg_18]
0x18004b860  add     rsp, 40h
0x18004b864  pop     r14
0x18004b866  pop     rdi
0x18004b867  pop     rsi
0x18004b868  retn
```
