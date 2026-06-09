# GEL::GDIPenResource::SetCompoundCustom(Ofc::TArray<double> const &,float,bool,bool)

- ea: `0x1801763c0`
- end: `0x180176504`
- name: `?SetCompoundCustom@GDIPenResource@GEL@@AEAAXAEBV?$TArray@N@Ofc@@M_N1@Z`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801307e8`

## callees

- `0x18001ffb4`
- `0x18002a0a0`
- `0x18005a920`
- `0x18011f508`
- `0x180130ef8`
- `0x1801763c0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801764e4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801764e4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017646c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017646c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801764cd`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801764cd`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017645d`
- `gdiplus!GdipSetPenCompoundArray` at `0x1801764be`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017645d`
- `gdiplus!GdipSetPenCompoundArray` at `0x1801764be`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GEL::GDIPenResource::SetCompoundCustom(__int64 a1, __int64 a2, float a3, __int64 a4, char a5)
{
  int v7; // edx
  __int64 v8; // rbx
  float v9; // xmm0_4
  unsigned int v10; // eax
  unsigned int v11; // eax
  Mso::Memory *v12; // rbx
  void *v13; // rdx
  void *v14; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-28h]
  Mso::Memory *v16; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-18h]
  unsigned int v18; // [rsp+4Ch] [rbp-14h]
  unsigned int v19; // [rsp+88h] [rbp+28h] BYREF

  v7 = *(_DWORD *)(a2 + 8);
  if ( v7 && (v7 & 1) == 0 )
  {
    Ofc::TArray<float>::TArray<float>(&v14);
    v8 = 0;
    if ( *(_DWORD *)(a2 + 8) )
    {
      while ( 1 )
      {
        v9 = *(double *)Ofc::TArray<Ofc::TSharedPtr<Ofc::TDag<Gfx::Scene3DClusterizer::ShapeExtents>>>::operator[](
                          a2,
                          (unsigned int)v8);
        if ( (unsigned int)v8 >= v15 )
          break;
        *((float *)v14 + v8) = v9;
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= *(_DWORD *)(a2 + 8) )
          goto LABEL_6;
      }
      CrashWithRecovery(0x1E892496u, 0);
    }
    else
    {
LABEL_6:
      if ( a3 <= 0.0 && !a5 )
      {
        v19 = v15;
        v10 = Math::SafeCast<int,unsigned long>(&v19);
        GdipSetPenCompoundArray(*(_QWORD *)(a1 + 8), v14, v10);
LABEL_12:
        operator delete(v14);
        return;
      }
    }
    v16 = 0;
    v17 = 0;
    v18 = 0x80000000;
    GEL::IPenResource::AdjustCompoundsForSplitAndInset((struct Ofc::CArrayImpl *)&v14, (Ofc::CArrayImpl *)&v16);
    v19 = v17;
    v11 = Math::SafeCast<int,unsigned long>(&v19);
    v12 = v16;
    GdipSetPenCompoundArray(*(_QWORD *)(a1 + 8), v16, v11);
    if ( v12 )
      Mso::Memory::Free(v12, v13);
    goto LABEL_12;
  }
  MsoShipAssertTagProc(2627156);
}

```

## disassembly

```asm
0x1801763c0  mov     [rsp-18h+arg_0], rbx
0x1801763c5  mov     [rsp-18h+arg_10], rsi
0x1801763ca  push    rbp
0x1801763cb  push    rdi
0x1801763cc  push    r14
0x1801763ce  mov     rbp, rsp
0x1801763d1  sub     rsp, 60h
0x1801763d5  movaps  [rsp+60h+var_10], xmm6
0x1801763da  mov     r14b, r9b
0x1801763dd  movaps  xmm6, xmm2
0x1801763e0  mov     rdi, rdx
0x1801763e3  mov     rsi, rcx
0x1801763e6  mov     edx, [rdx+8]
0x1801763e9  test    edx, edx
0x1801763eb  jz      loc_1801764DF
0x1801763f1  test    dl, 1
0x1801763f4  jnz     loc_1801764DF
0x1801763fa  lea     rcx, [rbp+var_30]
0x1801763fe  call    ??0?$TArray@M@Ofc@@QEAA@K@Z; Ofc::TArray<float>::TArray<float>(ulong)
0x180176403  xor     ebx, ebx
0x180176405  cmp     [rdi+8], ebx
0x180176408  jbe     short loc_180176431
0x18017640a  mov     edx, ebx
0x18017640c  mov     rcx, rdi
0x18017640f  call    ??A?$TArray@V?$TSharedPtr@V?$TDag@VShapeExtents@Scene3DClusterizer@Gfx@@@Ofc@@@Ofc@@@Ofc@@QEBAAEBV?$TSharedPtr@V?$TDag@VShapeExtents@Scene3DClusterizer@Gfx@@@Ofc@@@1@K@Z; Ofc::TArray<Ofc::TSharedPtr<Ofc::TDag<Gfx::Scene3DClusterizer::ShapeExtents>>>::operator[](ulong)
0x180176414  movsd   xmm0, qword ptr [rax]
0x180176418  cvtpd2ps xmm0, xmm0
0x18017641c  cmp     ebx, [rbp+var_28]
0x18017641f  jnb     short loc_180176465
0x180176421  mov     rax, [rbp+var_30]
0x180176425  movss   dword ptr [rax+rbx*4], xmm0
0x18017642a  inc     ebx
0x18017642c  cmp     ebx, [rdi+8]
0x18017642f  jb      short loc_18017640A
0x180176431  mov     r9b, [rbp+arg_20]
0x180176435  comiss  xmm6, cs:__real@00000000
0x18017643c  ja      short loc_180176473
0x18017643e  test    r9b, r9b
0x180176441  jnz     short loc_180176473
0x180176443  mov     eax, [rbp+var_28]
0x180176446  mov     [rbp+arg_8], eax
0x180176449  lea     rcx, [rbp+arg_8]
0x18017644d  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x180176452  mov     r8d, eax
0x180176455  mov     rdx, [rbp+var_30]
0x180176459  mov     rcx, [rsi+8]
0x18017645d  call    cs:__imp_GdipSetPenCompoundArray
0x180176463  jmp     short loc_1801764D4
0x180176465  xor     edx, edx
0x180176467  mov     ecx, 1E892496h
0x18017646c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180176472  nop
0x180176473  mov     [rbp+var_20], 0
0x18017647b  mov     [rbp+var_18], 0
0x180176482  mov     [rbp+var_14], 80000000h
0x180176489  lea     rax, [rbp+var_20]
0x18017648d  mov     [rsp+60h+var_40], rax; Ofc::CArrayImpl *
0x180176492  mov     r8b, r14b
0x180176495  movaps  xmm1, xmm6
0x180176498  lea     rcx, [rbp+var_30]; struct Ofc::CArrayImpl *
0x18017649c  call    ?AdjustCompoundsForSplitAndInset@IPenResource@GEL@@SAXAEBV?$TArray@M@Ofc@@M_N1AEAV34@@Z; GEL::IPenResource::AdjustCompoundsForSplitAndInset(Ofc::TArray<float> const &,float,bool,bool,Ofc::TArray<float> &)
0x1801764a1  mov     eax, [rbp+var_18]
0x1801764a4  mov     [rbp+arg_8], eax
0x1801764a7  lea     rcx, [rbp+arg_8]
0x1801764ab  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x1801764b0  mov     r8d, eax
0x1801764b3  mov     rbx, [rbp+var_20]
0x1801764b7  mov     rdx, rbx
0x1801764ba  mov     rcx, [rsi+8]
0x1801764be  call    cs:__imp_GdipSetPenCompoundArray
0x1801764c4  nop
0x1801764c5  test    rbx, rbx
0x1801764c8  jz      short loc_1801764D4
0x1801764ca  mov     rcx, rbx
0x1801764cd  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801764d3  nop
0x1801764d4  mov     rcx, [rbp+var_30]; void *
0x1801764d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801764dd  jmp     short loc_1801764EA
0x1801764df  mov     ecx, 281654h
0x1801764e4  call    cs:__imp_MsoShipAssertTagProc
0x1801764ea  lea     r11, [rsp+60h+var_s0]
0x1801764ef  mov     rbx, [r11+20h]
0x1801764f3  mov     rsi, [r11+30h]
0x1801764f7  movaps  xmm6, [rsp+60h+var_10]
0x1801764fc  mov     rsp, r11
0x1801764ff  pop     r14
0x180176501  pop     rdi
0x180176502  pop     rbp
0x180176503  retn
```
