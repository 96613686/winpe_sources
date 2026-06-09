# GEL::GDIPenResource::SetCompoundType(GEL::PenCompound,float,bool,bool)

- ea: `0x180130b30`
- end: `0x180130c79`
- name: `?SetCompoundType@GDIPenResource@GEL@@AEAAXW4PenCompound@2@M_N1@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801307e8`

## callees

- `0x180045ae8`
- `0x18011f508`
- `0x180130b30`
- `0x180130ef8`
- `0x1802049f3`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180130c2b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180130c41`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180130c2b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180130c41`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130b6f`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130c19`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130c70`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130b6f`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130c19`
- `gdiplus!GdipSetPenCompoundArray` at `0x180130c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GEL::GDIPenResource::SetCompoundType(__int64 a1, char a2, float a3, __int64 a4, char a5)
{
  __int64 v5; // rsi
  void *v6; // rdx
  unsigned int v7; // eax
  Mso::Memory *v8; // [rsp+30h] [rbp-30h] BYREF
  int v9; // [rsp+38h] [rbp-28h]
  unsigned int v10; // [rsp+3Ch] [rbp-24h]
  Mso::Memory *v11; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-18h]
  unsigned int v13; // [rsp+4Ch] [rbp-14h]
  int pExceptionObject; // [rsp+78h] [rbp+18h] BYREF

  v5 = a1;
  if ( a2 || a3 != 0.0 || a5 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0x80000000;
    LOBYTE(a1) = a2;
    GEL::IPenResource::GetCompoundArray(a1, &v8);
    if ( a3 > 0.0 || a5 )
    {
      v11 = 0;
      v12 = 0;
      v13 = 0x80000000;
      GEL::IPenResource::AdjustCompoundsForSplitAndInset((struct Ofc::CArrayImpl *)&v8, (Ofc::CArrayImpl *)&v11);
      if ( v12 > 0x7FFFFFFF )
      {
        pExceptionObject = 0;
        throw (SafeIntException *)&pExceptionObject;
      }
      GdipSetPenCompoundArray(*(_QWORD *)(v5 + 8), v11, v12);
      if ( v11 )
        Mso::Memory::Free(v11, v6);
    }
    else
    {
      pExceptionObject = v9;
      v7 = Math::SafeCast<int,unsigned long>(&pExceptionObject);
      GdipSetPenCompoundArray(*(_QWORD *)(v5 + 8), v8, v7);
    }
    if ( v8 )
      Mso::Memory::Free(v8, v6);
  }
  else
  {
    GdipSetPenCompoundArray(*(_QWORD *)(a1 + 8), 0, 0);
  }
}

```

## disassembly

```asm
0x180130b30  mov     [rsp-8+arg_0], rsi
0x180130b35  mov     [rsp-8+arg_10], r14
0x180130b3a  push    rbp
0x180130b3b  mov     rbp, rsp
0x180130b3e  sub     rsp, 60h
0x180130b42  movaps  [rsp+60h+var_10], xmm6
0x180130b47  mov     r14b, r9b
0x180130b4a  movaps  xmm6, xmm2
0x180130b4d  mov     al, dl
0x180130b4f  mov     rsi, rcx
0x180130b52  test    dl, dl
0x180130b54  jnz     short loc_180130B8C
0x180130b56  ucomiss xmm6, cs:__real@00000000
0x180130b5d  jp      short loc_180130B8C
0x180130b5f  jnz     short loc_180130B8C
0x180130b61  cmp     [rbp+arg_20], dl
0x180130b64  jnz     short loc_180130B8C
0x180130b66  xor     r8d, r8d
0x180130b69  xor     edx, edx
0x180130b6b  mov     rcx, [rcx+8]
0x180130b6f  call    cs:__imp_GdipSetPenCompoundArray
0x180130b75  lea     r11, [rsp+60h+var_s0]
0x180130b7a  mov     rsi, [r11+10h]
0x180130b7e  mov     r14, [r11+20h]
0x180130b82  movaps  xmm6, [rsp+60h+var_10]
0x180130b87  mov     rsp, r11
0x180130b8a  pop     rbp
0x180130b8b  retn
0x180130b8c  mov     [rbp+var_30], 0
0x180130b94  mov     [rbp+var_28], 0
0x180130b9b  mov     [rbp+var_24], 80000000h
0x180130ba2  lea     rdx, [rbp+var_30]
0x180130ba6  mov     cl, al
0x180130ba8  call    ?GetCompoundArray@IPenResource@GEL@@SAXW4PenCompound@2@AEAV?$TArray@M@Ofc@@@Z; GEL::IPenResource::GetCompoundArray(GEL::PenCompound,Ofc::TArray<float> &)
0x180130bad  comiss  xmm6, cs:__real@00000000
0x180130bb4  jbe     loc_180130C4C
0x180130bba  mov     [rbp+var_20], 0
0x180130bc2  mov     [rbp+var_18], 0
0x180130bc9  mov     [rbp+var_14], 80000000h
0x180130bd0  lea     rax, [rbp+var_20]
0x180130bd4  mov     [rsp+60h+var_40], rax; Ofc::CArrayImpl *
0x180130bd9  mov     r9b, [rbp+arg_20]
0x180130bdd  mov     r8b, r14b
0x180130be0  movaps  xmm1, xmm6
0x180130be3  lea     rcx, [rbp+var_30]; struct Ofc::CArrayImpl *
0x180130be7  call    ?AdjustCompoundsForSplitAndInset@IPenResource@GEL@@SAXAEBV?$TArray@M@Ofc@@M_N1AEAV34@@Z; GEL::IPenResource::AdjustCompoundsForSplitAndInset(Ofc::TArray<float> const &,float,bool,bool,Ofc::TArray<float> &)
0x180130bec  mov     r8d, [rbp+var_18]
0x180130bf0  cmp     r8d, 7FFFFFFFh
0x180130bf7  jbe     short loc_180130C11
0x180130bf9  mov     [rbp+pExceptionObject], 0
0x180130c00  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x180130c07  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180130c0b  call    _CxxThrowException_0
0x180130c11  mov     rdx, [rbp+var_20]
0x180130c15  mov     rcx, [rsi+8]
0x180130c19  call    cs:__imp_GdipSetPenCompoundArray
0x180130c1f  nop
0x180130c20  cmp     [rbp+var_20], 0
0x180130c25  jz      short loc_180130C32
0x180130c27  mov     rcx, [rbp+var_20]
0x180130c2b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180130c31  nop
0x180130c32  cmp     [rbp+var_30], 0
0x180130c37  jz      loc_180130B75
0x180130c3d  mov     rcx, [rbp+var_30]
0x180130c41  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180130c47  jmp     loc_180130B75
0x180130c4c  cmp     [rbp+arg_20], 0
0x180130c50  jnz     loc_180130BBA
0x180130c56  mov     eax, [rbp+var_28]
0x180130c59  mov     [rbp+pExceptionObject], eax
0x180130c5c  lea     rcx, [rbp+pExceptionObject]
0x180130c60  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x180130c65  mov     r8d, eax
0x180130c68  mov     rdx, [rbp+var_30]
0x180130c6c  mov     rcx, [rsi+8]
0x180130c70  call    cs:__imp_GdipSetPenCompoundArray
0x180130c76  jmp     short loc_180130C32
```
