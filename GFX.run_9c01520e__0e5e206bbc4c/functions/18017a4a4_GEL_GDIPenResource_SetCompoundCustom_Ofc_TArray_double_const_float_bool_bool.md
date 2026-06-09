# GEL::GDIPenResource::SetCompoundCustom(Ofc::TArray<double> const &,float,bool,bool)

- ea: `0x18017a4a4`
- end: `0x18017a5e8`
- name: `?SetCompoundCustom@GDIPenResource@GEL@@AEAAXAEBV?$TArray@N@Ofc@@M_N1@Z`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18012e318`

## callees

- `0x180020198`
- `0x18002b410`
- `0x180064814`
- `0x18011d248`
- `0x18012ea28`
- `0x18017a4a4`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18017a5c8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18017a5c8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017a550`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017a550`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18017a5b1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18017a5b1`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017a541`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017a5a2`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017a541`
- `gdiplus!GdipSetPenCompoundArray` at `0x18017a5a2`

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
0x18017a4a4  mov     [rsp-18h+arg_0], rbx
0x18017a4a9  mov     [rsp-18h+arg_10], rsi
0x18017a4ae  push    rbp
0x18017a4af  push    rdi
0x18017a4b0  push    r14
0x18017a4b2  mov     rbp, rsp
0x18017a4b5  sub     rsp, 60h
0x18017a4b9  movaps  [rsp+60h+var_10], xmm6
0x18017a4be  mov     r14b, r9b
0x18017a4c1  movaps  xmm6, xmm2
0x18017a4c4  mov     rdi, rdx
0x18017a4c7  mov     rsi, rcx
0x18017a4ca  mov     edx, [rdx+8]
0x18017a4cd  test    edx, edx
0x18017a4cf  jz      loc_18017A5C3
0x18017a4d5  test    dl, 1
0x18017a4d8  jnz     loc_18017A5C3
0x18017a4de  lea     rcx, [rbp+var_30]
0x18017a4e2  call    ??0?$TArray@M@Ofc@@QEAA@K@Z; Ofc::TArray<float>::TArray<float>(ulong)
0x18017a4e7  xor     ebx, ebx
0x18017a4e9  cmp     [rdi+8], ebx
0x18017a4ec  jbe     short loc_18017A515
0x18017a4ee  mov     edx, ebx
0x18017a4f0  mov     rcx, rdi
0x18017a4f3  call    ??A?$TArray@V?$TSharedPtr@V?$TDag@VShapeExtents@Scene3DClusterizer@Gfx@@@Ofc@@@Ofc@@@Ofc@@QEBAAEBV?$TSharedPtr@V?$TDag@VShapeExtents@Scene3DClusterizer@Gfx@@@Ofc@@@1@K@Z; Ofc::TArray<Ofc::TSharedPtr<Ofc::TDag<Gfx::Scene3DClusterizer::ShapeExtents>>>::operator[](ulong)
0x18017a4f8  movsd   xmm0, qword ptr [rax]
0x18017a4fc  cvtpd2ps xmm0, xmm0
0x18017a500  cmp     ebx, [rbp+var_28]
0x18017a503  jnb     short loc_18017A549
0x18017a505  mov     rax, [rbp+var_30]
0x18017a509  movss   dword ptr [rax+rbx*4], xmm0
0x18017a50e  inc     ebx
0x18017a510  cmp     ebx, [rdi+8]
0x18017a513  jb      short loc_18017A4EE
0x18017a515  mov     r9b, [rbp+arg_20]
0x18017a519  comiss  xmm6, cs:__real@00000000
0x18017a520  ja      short loc_18017A557
0x18017a522  test    r9b, r9b
0x18017a525  jnz     short loc_18017A557
0x18017a527  mov     eax, [rbp+var_28]
0x18017a52a  mov     [rbp+arg_8], eax
0x18017a52d  lea     rcx, [rbp+arg_8]
0x18017a531  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x18017a536  mov     r8d, eax
0x18017a539  mov     rdx, [rbp+var_30]
0x18017a53d  mov     rcx, [rsi+8]
0x18017a541  call    cs:__imp_GdipSetPenCompoundArray
0x18017a547  jmp     short loc_18017A5B8
0x18017a549  xor     edx, edx
0x18017a54b  mov     ecx, 1E892496h
0x18017a550  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18017a556  nop
0x18017a557  mov     [rbp+var_20], 0
0x18017a55f  mov     [rbp+var_18], 0
0x18017a566  mov     [rbp+var_14], 80000000h
0x18017a56d  lea     rax, [rbp+var_20]
0x18017a571  mov     [rsp+60h+var_40], rax; Ofc::CArrayImpl *
0x18017a576  mov     r8b, r14b
0x18017a579  movaps  xmm1, xmm6
0x18017a57c  lea     rcx, [rbp+var_30]; struct Ofc::CArrayImpl *
0x18017a580  call    ?AdjustCompoundsForSplitAndInset@IPenResource@GEL@@SAXAEBV?$TArray@M@Ofc@@M_N1AEAV34@@Z; GEL::IPenResource::AdjustCompoundsForSplitAndInset(Ofc::TArray<float> const &,float,bool,bool,Ofc::TArray<float> &)
0x18017a585  mov     eax, [rbp+var_18]
0x18017a588  mov     [rbp+arg_8], eax
0x18017a58b  lea     rcx, [rbp+arg_8]
0x18017a58f  call    ??$SafeCast@HK@Math@@YAHAEBK@Z; Math::SafeCast<int,ulong>(ulong const &)
0x18017a594  mov     r8d, eax
0x18017a597  mov     rbx, [rbp+var_20]
0x18017a59b  mov     rdx, rbx
0x18017a59e  mov     rcx, [rsi+8]
0x18017a5a2  call    cs:__imp_GdipSetPenCompoundArray
0x18017a5a8  nop
0x18017a5a9  test    rbx, rbx
0x18017a5ac  jz      short loc_18017A5B8
0x18017a5ae  mov     rcx, rbx
0x18017a5b1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18017a5b7  nop
0x18017a5b8  mov     rcx, [rbp+var_30]; void *
0x18017a5bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017a5c1  jmp     short loc_18017A5CE
0x18017a5c3  mov     ecx, 281654h
0x18017a5c8  call    cs:__imp_MsoShipAssertTagProc
0x18017a5ce  lea     r11, [rsp+60h+var_s0]
0x18017a5d3  mov     rbx, [r11+20h]
0x18017a5d7  mov     rsi, [r11+30h]
0x18017a5db  movaps  xmm6, [rsp+60h+var_10]
0x18017a5e0  mov     rsp, r11
0x18017a5e3  pop     r14
0x18017a5e5  pop     rdi
0x18017a5e6  pop     rbp
0x18017a5e7  retn
```
