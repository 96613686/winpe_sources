# Gdiplus::PathGradientBrush::SetSurroundColors(Gdiplus::Color const *,int *)

- ea: `0x18006e6d0`
- end: `0x18006e7de`
- name: `?SetSurroundColors@PathGradientBrush@Gdiplus@@QEAA?AW4Status@2@PEBVColor@2@PEAH@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18006df00`

## callees

- `0x18006e6d0`

## import_xrefs

- `gdiplus!GdipGetPathGradientPointCount` at `0x18006e70e`
- `gdiplus!GdipGetPathGradientPointCount` at `0x18006e70e`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18006e794`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18006e794`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18006e7af`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18006e7af`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18006e751`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18006e751`

## pseudocode

```c
__int64 __fastcall Gdiplus::PathGradientBrush::SetSurroundColors(__int64 a1, __int64 a2, int *a3)
{
  __int64 v6; // rcx
  unsigned int PathGradientPointCount; // eax
  bool v8; // r8
  unsigned int *v9; // rbx
  unsigned __int64 v10; // rcx
  unsigned __int128 v11; // rax
  BasePrivate *v12; // r15
  __int64 result; // rax
  int v14; // edx
  __int64 v15; // rcx
  _DWORD *v16; // rsi
  int v17; // eax
  void *v18; // rdx
  int v19; // [rsp+48h] [rbp+10h] BYREF
  int v20; // [rsp+58h] [rbp+20h] BYREF

  if ( a2 && a3 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    v20 = 0;
    PathGradientPointCount = GdipGetPathGradientPointCount(v6, &v20);
    v9 = (unsigned int *)(a1 + 16);
    if ( PathGradientPointCount )
      *v9 = PathGradientPointCount;
    v10 = *a3;
    if ( (int)v10 > v20 || v20 <= 0 )
    {
      result = 2;
      goto LABEL_21;
    }
    v19 = *a3;
    v11 = v10 * (unsigned __int128)4uLL;
    BYTE8(v11) = 1;
    if ( !is_mul_ok(v10, 4u) )
      *(_QWORD *)&v11 = -1;
    v12 = (BasePrivate *)BasePrivate::New((BasePrivate *)v11, *((unsigned __int64 *)&v11 + 1), v8);
    if ( !v12 )
    {
      result = 3;
LABEL_21:
      *v9 = result;
      return result;
    }
    v14 = 0;
    if ( v19 <= 0 )
    {
      v16 = (_DWORD *)(a1 + 16);
    }
    else
    {
      do
      {
        v15 = v14++;
        *((_DWORD *)v12 + v15) = *(_DWORD *)(a2 + 4 * v15);
      }
      while ( v14 < v19 );
      v16 = (_DWORD *)(a1 + 16);
    }
    v17 = GdipSetPathGradientSurroundColorsWithCount(*(_QWORD *)(a1 + 8), v12, &v19);
    if ( v17 )
      *v16 = v17;
    if ( !*v16 )
      *a3 = v19;
    BasePrivate::Delete(v12, v18);
    return *v9;
  }
  else
  {
    result = 2;
    *(_DWORD *)(a1 + 16) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x18006e6d0  mov     rax, rsp
0x18006e6d3  mov     [rax+8], rbx
0x18006e6d7  mov     [rax+18h], rsi
0x18006e6db  push    rdi
0x18006e6dc  push    r14
0x18006e6de  push    r15
0x18006e6e0  sub     rsp, 20h
0x18006e6e4  mov     r14, r8
0x18006e6e7  mov     rsi, rdx
0x18006e6ea  mov     rdi, rcx
0x18006e6ed  test    rdx, rdx
0x18006e6f0  jz      loc_18006E7C2
0x18006e6f6  test    r8, r8
0x18006e6f9  jz      loc_18006E7C2
0x18006e6ff  mov     rcx, [rcx+8]
0x18006e703  lea     rdx, [rax+20h]
0x18006e707  mov     dword ptr [rax+20h], 0
0x18006e70e  call    cs:__imp_GdipGetPathGradientPointCount
0x18006e714  lea     rbx, [rdi+10h]
0x18006e718  test    eax, eax
0x18006e71a  jz      short loc_18006E71E
0x18006e71c  mov     [rbx], eax
0x18006e71e  movsxd  rcx, dword ptr [r14]
0x18006e721  mov     eax, [rsp+38h+arg_18]
0x18006e725  cmp     ecx, eax
0x18006e727  jg      loc_18006E7B9
0x18006e72d  test    eax, eax
0x18006e72f  jle     loc_18006E7B9
0x18006e735  mov     [rsp+38h+arg_8], ecx
0x18006e739  mov     eax, 4
0x18006e73e  mul     rcx
0x18006e741  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006e748  mov     dl, 1
0x18006e74a  cmovb   rax, rcx
0x18006e74e  mov     rcx, rax
0x18006e751  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18006e757  mov     r15, rax
0x18006e75a  test    rax, rax
0x18006e75d  jnz     short loc_18006E765
0x18006e75f  lea     eax, [r15+3]
0x18006e763  jmp     short loc_18006E7BE
0x18006e765  xor     edx, edx
0x18006e767  cmp     [rsp+38h+arg_8], edx
0x18006e76b  jle     short loc_18006E785
0x18006e76d  movsxd  rcx, edx
0x18006e770  inc     edx
0x18006e772  mov     eax, [rsi+rcx*4]
0x18006e775  mov     [r15+rcx*4], eax
0x18006e779  cmp     edx, [rsp+38h+arg_8]
0x18006e77d  jl      short loc_18006E76D
0x18006e77f  lea     rsi, [rdi+10h]
0x18006e783  jmp     short loc_18006E788
0x18006e785  mov     rsi, rbx
0x18006e788  mov     rcx, [rdi+8]
0x18006e78c  lea     r8, [rsp+38h+arg_8]
0x18006e791  mov     rdx, r15
0x18006e794  call    cs:__imp_GdipSetPathGradientSurroundColorsWithCount
0x18006e79a  test    eax, eax
0x18006e79c  jz      short loc_18006E7A0
0x18006e79e  mov     [rsi], eax
0x18006e7a0  cmp     dword ptr [rsi], 0
0x18006e7a3  jnz     short loc_18006E7AC
0x18006e7a5  mov     ecx, [rsp+38h+arg_8]
0x18006e7a9  mov     [r14], ecx
0x18006e7ac  mov     rcx, r15
0x18006e7af  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18006e7b5  mov     eax, [rbx]
0x18006e7b7  jmp     short loc_18006E7CA
0x18006e7b9  mov     eax, 2
0x18006e7be  mov     [rbx], eax
0x18006e7c0  jmp     short loc_18006E7CA
0x18006e7c2  mov     eax, 2
0x18006e7c7  mov     [rcx+10h], eax
0x18006e7ca  mov     rbx, [rsp+38h+arg_0]
0x18006e7cf  mov     rsi, [rsp+38h+arg_10]
0x18006e7d4  add     rsp, 20h
0x18006e7d8  pop     r15
0x18006e7da  pop     r14
0x18006e7dc  pop     rdi
0x18006e7dd  retn
```
