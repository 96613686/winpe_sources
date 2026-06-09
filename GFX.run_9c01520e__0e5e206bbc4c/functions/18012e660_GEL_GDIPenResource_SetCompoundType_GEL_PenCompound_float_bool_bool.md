# GEL::GDIPenResource::SetCompoundType(GEL::PenCompound,float,bool,bool)

- ea: `0x18012e660`
- end: `0x18012e7a9`
- name: `?SetCompoundType@GDIPenResource@GEL@@AEAAXW4PenCompound@2@M_N1@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18012e318`

## callees

- `0x180047bc0`
- `0x18011d248`
- `0x18012e660`
- `0x18012ea28`
- `0x180207d23`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18012e75b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18012e771`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18012e75b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18012e771`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e69f`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e749`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e7a0`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e69f`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e749`
- `gdiplus!GdipSetPenCompoundArray` at `0x18012e7a0`

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
0x18012e660  mov     [rsp-8+arg_0], rsi
0x18012e665  mov     [rsp-8+arg_10], r14
0x18012e66a  push    rbp
0x18012e66b  mov     rbp, rsp
0x18012e66e  sub     rsp, 60h
0x18012e672  movaps  [rsp+60h+var_10], xmm6
0x18012e677  mov     r14b, r9b
0x18012e67a  movaps  xmm6, xmm2
0x18012e67d  mov     al, dl
0x18012e67f  mov     rsi, rcx
0x18012e682  test    dl, dl
0x18012e684  jnz     short loc_18012E6BC
0x18012e686  ucomiss xmm6, cs:__real@00000000
0x18012e68d  jp      short loc_18012E6BC
0x18012e68f  jnz     short loc_18012E6BC
0x18012e691  cmp     [rbp+arg_20], dl
0x18012e694  jnz     short loc_18012E6BC
0x18012e696  xor     r8d, r8d
0x18012e699  xor     edx, edx
0x18012e69b  mov     rcx, [rcx+8]
0x18012e69f  call    cs:__imp_GdipSetPenCompoundArray
0x18012e6a5  lea     r11, [rsp+60h+var_s0]
0x18012e6aa  mov     rsi, [r11+10h]
0x18012e6ae  mov     r14, [r11+20h]
0x18012e6b2  movaps  xmm6, [rsp+60h+var_10]
0x18012e6b7  mov     rsp, r11
0x18012e6ba  pop     rbp
0x18012e6bb  retn
0x18012e6bc  mov     [rbp+var_30], 0
0x18012e6c4  mov     [rbp+var_28], 0
0x18012e6cb  mov     [rbp+var_24], 80000000h
0x18012e6d2  lea     rdx, [rbp+var_30]
0x18012e6d6  mov     cl, al
0x18012e6d8  call    ?GetCompoundArray@IPenResource@GEL@@SAXW4PenCompound@2@AEAV?$TArray@M@Ofc@@@Z; GEL::IPenResource::GetCompoundArray(GEL::PenCompound,Ofc::TArray<float> &)
0x18012e6dd  comiss  xmm6, cs:__real@00000000
0x18012e6e4  jbe     loc_18012E77C
0x18012e6ea  mov     [rbp+var_20], 0
0x18012e6f2  mov     [rbp+var_18], 0
0x18012e6f9  mov     [rbp+var_14], 80000000h
0x18012e700  lea     rax, [rbp+var_20]
0x18012e704  mov     [rsp+60h+var_40], rax; Ofc::CArrayImpl *
0x18012e709  mov     r9b, [rbp+arg_20]
0x18012e70d  mov     r8b, r14b
0x18012e710  movaps  xmm1, xmm6
0x18012e713  lea     rcx, [rbp+var_30]; struct Ofc::CArrayImpl *
0x18012e717  call    ?AdjustCompoundsForSplitAndInset@IPenResource@GEL@@SAXAEBV?$TArray@M@Ofc@@M_N1AEAV34@@Z; GEL::IPenResource::AdjustCompoundsForSplitAndInset(Ofc::TArray<float> const &,float,bool,bool,Ofc::TArray<float> &)
0x18012e71c  mov     r8d, [rbp+var_18]
0x18012e720  cmp     r8d, 7FFFFFFFh
0x18012e727  jbe     short loc_18012E741
0x18012e729  mov     [rbp+pExceptionObject], 0
0x18012e730  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18012e737  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18012e73b  call    _CxxThrowException_0
0x18012e741  mov     rdx, [rbp+var_20]
0x18012e745  mov     rcx, [rsi+8]
0x18012e749  call    cs:__imp_GdipSetPenCompoundArray
0x18012e74f  nop
0x18012e750  cmp     [rbp+var_20], 0
0x18012e755  jz      short loc_18012E762
0x18012e757  mov     rcx, [rbp+var_20]
0x18012e75b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18012e761  nop
0x18012e762  cmp     [rbp+var_30], 0
0x18012e767  jz      loc_18012E6A5
0x18012e76d  mov     rcx, [rbp+var_30]
0x18012e771  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18012e777  jmp     loc_18012E6A5
0x18012e77c  cmp     [rbp+arg_20], 0
0x18012e780  jnz     loc_18012E6EA
0x18012e786  mov     eax, [rbp+var_28]
0x18012e789  mov     [rbp+pExceptionObject], eax
0x18012e78c  lea     rcx, [rbp+pExceptionObject]
0x18012e790  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x18012e795  mov     r8d, eax
0x18012e798  mov     rdx, [rbp+var_30]
0x18012e79c  mov     rcx, [rsi+8]
0x18012e7a0  call    cs:__imp_GdipSetPenCompoundArray
0x18012e7a6  jmp     short loc_18012E762
```
