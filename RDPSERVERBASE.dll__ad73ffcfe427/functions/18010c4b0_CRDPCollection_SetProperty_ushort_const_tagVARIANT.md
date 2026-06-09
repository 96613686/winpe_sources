# CRDPCollection::SetProperty(ushort const *,tagVARIANT *)

- ea: `0x18010c4b0`
- end: `0x18010c5b8`
- name: `?SetProperty@CRDPCollection@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `264`
- prototype: `int(CRDPCollection *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180026d78`
- `0x180027fe4`
- `0x180028120`
- `0x18007f6b0`
- `0x18010c4b0`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18010c54e`
- `OLEAUT32!__imp_VariantInit` at `0x18010c54e`
- `OLEAUT32!__imp_VariantCopy` at `0x18010c4f4`
- `OLEAUT32!__imp_VariantCopy` at `0x18010c56b`
- `OLEAUT32!__imp_VariantCopy` at `0x18010c4f4`
- `OLEAUT32!__imp_VariantCopy` at `0x18010c56b`

## pseudocode

```c
__int64 __fastcall CRDPCollection::SetProperty(CRDPCollection *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  char *v5; // r14
  HRESULT v6; // ebx
  VARIANTARG *v7; // rbx
  unsigned int v8; // edx
  CRDPAPICollectionImplItem *v9; // rax
  CRDPAPICollectionImplItem *v10; // rdi
  unsigned int v11; // edx
  VARIANTARG *pvargDest; // [rsp+58h] [rbp+10h] BYREF

  pvargDest = 0;
  if ( a2 )
  {
    v5 = (char *)this + 72;
    if ( (unsigned int)CTSSimpleArray<CRDPAPICollectionImplItem *,16>::Find<unsigned short const *,&protected: static int CRDPCollection::MatchPropertyName(unsigned short const *,CRDPAPICollectionImplItem *)>(
                         (char *)this + 72,
                         a2,
                         &pvargDest) )
    {
      if ( a3 )
      {
        return (unsigned int)VariantCopy(pvargDest, a3);
      }
      else
      {
        v7 = pvargDest;
        (*(void (__fastcall **)(char *, VARIANTARG *))(*(_QWORD *)v5 + 16LL))(v5, pvargDest);
        if ( v7 )
          CRDPAPICollectionImplItem::`scalar deleting destructor'((CRDPAPICollectionImplItem *)v7, v8);
        return 0;
      }
    }
    else if ( a3 )
    {
      v9 = (CRDPAPICollectionImplItem *)operator new(0x20u);
      v10 = v9;
      if ( v9 )
      {
        *((_QWORD *)v9 + 3) = 0;
        VariantInit((VARIANTARG *)v9);
        v6 = CRDPAPICollectionImplItem::SetName(v10, a2);
        if ( v6 < 0
          || (v6 = VariantCopy((VARIANTARG *)v10, a3), v6 < 0)
          || (v6 = (*(__int64 (__fastcall **)(char *, CRDPAPICollectionImplItem *))(*(_QWORD *)v5 + 8LL))(v5, v10),
              v6 < 0) )
        {
          CRDPAPICollectionImplItem::`scalar deleting destructor'(v10, v11);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18010c4b0  push    rbx
0x18010c4b2  push    rsi
0x18010c4b3  push    rdi
0x18010c4b4  push    r14
0x18010c4b6  sub     rsp, 28h
0x18010c4ba  mov     [rsp+48h+pvargDest], 0
0x18010c4c3  mov     rsi, r8
0x18010c4c6  mov     rbx, rdx
0x18010c4c9  test    rdx, rdx
0x18010c4cc  jz      loc_18010C5A7
0x18010c4d2  lea     r14, [rcx+48h]
0x18010c4d6  mov     rcx, r14
0x18010c4d9  lea     r8, [rsp+48h+pvargDest]
0x18010c4de  call    ??$Find@PEBG$1?MatchPropertyName@CRDPCollection@@KAHPEBGPEAVCRDPAPICollectionImplItem@@@Z@?$CTSSimpleArray@PEAVCRDPAPICollectionImplItem@@$0BA@@@QEAAHPEBGPEAPEAVCRDPAPICollectionImplItem@@@Z; CTSSimpleArray<CRDPAPICollectionImplItem *,16>::Find<ushort const *,&CRDPCollection::MatchPropertyName(ushort const *,CRDPAPICollectionImplItem *)>(ushort const *,CRDPAPICollectionImplItem * *)
0x18010c4e3  test    eax, eax
0x18010c4e5  jz      short loc_18010C52C
0x18010c4e7  test    rsi, rsi
0x18010c4ea  jz      short loc_18010C501
0x18010c4ec  mov     rcx, [rsp+48h+pvargDest]; pvargDest
0x18010c4f1  mov     rdx, rsi; pvargSrc
0x18010c4f4  call    cs:__imp_VariantCopy
0x18010c4fa  mov     ebx, eax
0x18010c4fc  jmp     loc_18010C5AC
0x18010c501  mov     rax, [r14]
0x18010c504  mov     rcx, r14
0x18010c507  mov     rbx, [rsp+48h+pvargDest]
0x18010c50c  mov     rdx, rbx
0x18010c50f  mov     rax, [rax+10h]
0x18010c513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c518  test    rbx, rbx
0x18010c51b  jz      short loc_18010C525
0x18010c51d  mov     rcx, rbx; this
0x18010c520  call    ??_GCRDPAPICollectionImplItem@@QEAAPEAXI@Z; CRDPAPICollectionImplItem::`scalar deleting destructor'(uint)
0x18010c525  xor     ebx, ebx
0x18010c527  jmp     loc_18010C5AC
0x18010c52c  test    rsi, rsi
0x18010c52f  jz      short loc_18010C5A0
0x18010c531  mov     ecx, 20h ; ' '; Size
0x18010c536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010c53b  mov     rdi, rax
0x18010c53e  test    rax, rax
0x18010c541  jz      short loc_18010C599
0x18010c543  mov     rcx, rax; pvarg
0x18010c546  mov     qword ptr [rax+18h], 0
0x18010c54e  call    cs:__imp_VariantInit
0x18010c554  mov     rdx, rbx; unsigned __int16 *
0x18010c557  mov     rcx, rdi; this
0x18010c55a  call    ?SetName@CRDPAPICollectionImplItem@@QEAAJPEBG@Z; CRDPAPICollectionImplItem::SetName(ushort const *)
0x18010c55f  mov     ebx, eax
0x18010c561  test    eax, eax
0x18010c563  js      short loc_18010C58F
0x18010c565  mov     rdx, rsi; pvargSrc
0x18010c568  mov     rcx, rdi; pvargDest
0x18010c56b  call    cs:__imp_VariantCopy
0x18010c571  mov     ebx, eax
0x18010c573  test    eax, eax
0x18010c575  js      short loc_18010C58F
0x18010c577  mov     rax, [r14]
0x18010c57a  mov     rdx, rdi
0x18010c57d  mov     rcx, r14
0x18010c580  mov     rax, [rax+8]
0x18010c584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c589  mov     ebx, eax
0x18010c58b  test    eax, eax
0x18010c58d  jns     short loc_18010C5AC
0x18010c58f  mov     rcx, rdi; this
0x18010c592  call    ??_GCRDPAPICollectionImplItem@@QEAAPEAXI@Z; CRDPAPICollectionImplItem::`scalar deleting destructor'(uint)
0x18010c597  jmp     short loc_18010C5AC
0x18010c599  mov     ebx, 8007000Eh
0x18010c59e  jmp     short loc_18010C5AC
0x18010c5a0  mov     ebx, 1
0x18010c5a5  jmp     short loc_18010C5AC
0x18010c5a7  mov     ebx, 80004003h
0x18010c5ac  mov     eax, ebx
0x18010c5ae  add     rsp, 28h
0x18010c5b2  pop     r14
0x18010c5b4  pop     rdi
0x18010c5b5  pop     rsi
0x18010c5b6  pop     rbx
0x18010c5b7  retn
```
