# CRDPKeyCollection::SetProperty(int,tagVARIANT *)

- ea: `0x1800c0ad0`
- end: `0x1800c0c0c`
- name: `?SetProperty@CRDPKeyCollection@@UEAAJHPEAUtagVARIANT@@@Z`
- size: `316`
- prototype: `int(CRDPKeyCollection *__hidden this, int, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c0c20`
- `0x1800c0ca0`
- `0x1800c0d30`

## callees

- `0x18003702c`
- `0x180049f60`
- `0x18007f6b0`
- `0x1800b5bc8`
- `0x1800b60a8`
- `0x1800c0ad0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800c0bbb`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0bbb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c0b10`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c0bca`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c0b10`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c0bca`

## pseudocode

```c
__int64 __fastcall CRDPKeyCollection::SetProperty(CRDPKeyCollection *this, __int64 a2, struct tagVARIANT *a3)
{
  char *v3; // rdi
  int v5; // ebp
  HRESULT v6; // ebx
  unsigned int v7; // edx
  CRDPAPIKeyCollectionImplItem *v8; // r11
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  VARIANTARG *v13; // rax
  VARIANTARG *v14; // rsi
  unsigned int v15; // edx
  unsigned int v17; // [rsp+40h] [rbp+8h] BYREF
  VARIANTARG *pvargDest; // [rsp+58h] [rbp+20h] BYREF

  v3 = (char *)this + 56;
  pvargDest = 0;
  v5 = a2;
  if ( (unsigned int)CTSSimpleArray<CRDPAPIKeyCollectionImplItem *,16>::Find<int,&protected: static int CRDPKeyCollection::MatchPropertyKey(int,CRDPAPIKeyCollectionImplItem *)>(
                       (char *)this + 56,
                       a2,
                       &pvargDest) )
  {
    if ( a3 )
    {
      return (unsigned int)VariantCopy(pvargDest, a3);
    }
    else
    {
      v17 = 0;
      if ( (unsigned int)CTSSimpleArray<CRDPMUXElement *,16>::FindElement(v3, pvargDest, &v17) )
      {
        --*((_DWORD *)v3 + 5);
        v9 = v17;
        v10 = *((_DWORD *)v3 + 5);
        if ( v17 < v10 )
        {
          do
          {
            v11 = (unsigned int)(v9 + 1);
            *(_QWORD *)(*((_QWORD *)v3 + 1) + 8 * v9) = *(_QWORD *)(*((_QWORD *)v3 + 1) + 8 * v11);
            v10 = *((_DWORD *)v3 + 5);
            v9 = v11;
          }
          while ( (unsigned int)v11 < v10 );
        }
        v7 = v10;
        *(_QWORD *)(*((_QWORD *)v3 + 1) + 8LL * v10) = 0xC3C3C3C3C3C3C3C3uLL;
        v12 = *((_DWORD *)v3 + 6);
        if ( v12 > v17 )
          *((_DWORD *)v3 + 6) = v12 - 1;
      }
      if ( v8 )
        CRDPAPIKeyCollectionImplItem::`scalar deleting destructor'(v8, v7);
      return 0;
    }
  }
  else if ( a3 )
  {
    v13 = (VARIANTARG *)operator new(0x20u);
    v14 = v13;
    if ( v13 )
    {
      *(_DWORD *)&v13[1].vt = 0;
      VariantInit(v13);
      *(_DWORD *)&v14[1].vt = v5;
      v6 = VariantCopy(v14, a3);
      if ( v6 < 0 || (v6 = CTSSimpleArray<CRDPENCVCHandler *,16>::AllocElement(v3, v14), v6 < 0) )
        CRDPAPIKeyCollectionImplItem::`scalar deleting destructor'((CRDPAPIKeyCollectionImplItem *)v14, v15);
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c0ad0  mov     [rsp+arg_8], rbx
0x1800c0ad5  push    rbp
0x1800c0ad6  push    rsi
0x1800c0ad7  push    rdi
0x1800c0ad8  sub     rsp, 20h
0x1800c0adc  lea     rdi, [rcx+38h]
0x1800c0ae0  mov     [rsp+38h+pvargDest], 0
0x1800c0ae9  mov     rbx, r8
0x1800c0aec  mov     rcx, rdi
0x1800c0aef  lea     r8, [rsp+38h+pvargDest]
0x1800c0af4  mov     ebp, edx
0x1800c0af6  call    ??$Find@H$1?MatchPropertyKey@CRDPKeyCollection@@KAHHPEAVCRDPAPIKeyCollectionImplItem@@@Z@?$CTSSimpleArray@PEAVCRDPAPIKeyCollectionImplItem@@$0BA@@@QEAAHHPEAPEAVCRDPAPIKeyCollectionImplItem@@@Z; CTSSimpleArray<CRDPAPIKeyCollectionImplItem *,16>::Find<int,&CRDPKeyCollection::MatchPropertyKey(int,CRDPAPIKeyCollectionImplItem *)>(int,CRDPAPIKeyCollectionImplItem * *)
0x1800c0afb  test    eax, eax
0x1800c0afd  jz      loc_1800C0B9A
0x1800c0b03  test    rbx, rbx
0x1800c0b06  jz      short loc_1800C0B1D
0x1800c0b08  mov     rcx, [rsp+38h+pvargDest]; pvargDest
0x1800c0b0d  mov     rdx, rbx; pvargSrc
0x1800c0b10  call    cs:__imp_VariantCopy
0x1800c0b16  mov     ebx, eax
0x1800c0b18  jmp     loc_1800C0BFD
0x1800c0b1d  mov     r11, [rsp+38h+pvargDest]
0x1800c0b22  lea     r8, [rsp+38h+arg_0]
0x1800c0b27  mov     rdx, r11
0x1800c0b2a  mov     [rsp+38h+arg_0], 0
0x1800c0b32  mov     rcx, rdi
0x1800c0b35  call    ?FindElement@?$CTSSimpleArray@PEAVCRDPMUXElement@@$0BA@@@IEBAHPEAVCRDPMUXElement@@PEAI@Z; CTSSimpleArray<CRDPMUXElement *,16>::FindElement(CRDPMUXElement *,uint *)
0x1800c0b3a  test    eax, eax
0x1800c0b3c  jz      short loc_1800C0B89
0x1800c0b3e  dec     dword ptr [rdi+14h]
0x1800c0b41  mov     ecx, [rsp+38h+arg_0]
0x1800c0b45  mov     eax, [rdi+14h]
0x1800c0b48  cmp     ecx, eax
0x1800c0b4a  jnb     short loc_1800C0B67
0x1800c0b4c  mov     rdx, [rdi+8]
0x1800c0b50  lea     r8d, [rcx+1]
0x1800c0b54  mov     rax, [rdx+r8*8]
0x1800c0b58  mov     [rdx+rcx*8], rax
0x1800c0b5c  mov     eax, [rdi+14h]
0x1800c0b5f  mov     ecx, r8d
0x1800c0b62  cmp     r8d, eax
0x1800c0b65  jb      short loc_1800C0B4C
0x1800c0b67  mov     edx, eax; unsigned int
0x1800c0b69  mov     rcx, 0C3C3C3C3C3C3C3C3h
0x1800c0b73  mov     rax, [rdi+8]
0x1800c0b77  mov     [rax+rdx*8], rcx
0x1800c0b7b  mov     eax, [rdi+18h]
0x1800c0b7e  cmp     eax, [rsp+38h+arg_0]
0x1800c0b82  jbe     short loc_1800C0B89
0x1800c0b84  dec     eax
0x1800c0b86  mov     [rdi+18h], eax
0x1800c0b89  test    r11, r11
0x1800c0b8c  jz      short loc_1800C0B96
0x1800c0b8e  mov     rcx, r11; this
0x1800c0b91  call    ??_GCRDPAPIKeyCollectionImplItem@@QEAAPEAXI@Z; CRDPAPIKeyCollectionImplItem::`scalar deleting destructor'(uint)
0x1800c0b96  xor     ebx, ebx
0x1800c0b98  jmp     short loc_1800C0BFD
0x1800c0b9a  test    rbx, rbx
0x1800c0b9d  jz      short loc_1800C0BF8
0x1800c0b9f  mov     ecx, 20h ; ' '; Size
0x1800c0ba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c0ba9  mov     rsi, rax
0x1800c0bac  test    rax, rax
0x1800c0baf  jz      short loc_1800C0BF1
0x1800c0bb1  mov     rcx, rax; pvarg
0x1800c0bb4  mov     dword ptr [rax+18h], 0
0x1800c0bbb  call    cs:__imp_VariantInit
0x1800c0bc1  mov     rdx, rbx; pvargSrc
0x1800c0bc4  mov     [rsi+18h], ebp
0x1800c0bc7  mov     rcx, rsi; pvargDest
0x1800c0bca  call    cs:__imp_VariantCopy
0x1800c0bd0  mov     ebx, eax
0x1800c0bd2  test    eax, eax
0x1800c0bd4  js      short loc_1800C0BE7
0x1800c0bd6  mov     rdx, rsi
0x1800c0bd9  mov     rcx, rdi
0x1800c0bdc  call    ?AllocElement@?$CTSSimpleArray@PEAVCRDPENCVCHandler@@$0BA@@@IEAAJPEAVCRDPENCVCHandler@@@Z; CTSSimpleArray<CRDPENCVCHandler *,16>::AllocElement(CRDPENCVCHandler *)
0x1800c0be1  mov     ebx, eax
0x1800c0be3  test    eax, eax
0x1800c0be5  jns     short loc_1800C0BFD
0x1800c0be7  mov     rcx, rsi; this
0x1800c0bea  call    ??_GCRDPAPIKeyCollectionImplItem@@QEAAPEAXI@Z; CRDPAPIKeyCollectionImplItem::`scalar deleting destructor'(uint)
0x1800c0bef  jmp     short loc_1800C0BFD
0x1800c0bf1  mov     ebx, 8007000Eh
0x1800c0bf6  jmp     short loc_1800C0BFD
0x1800c0bf8  mov     ebx, 1
0x1800c0bfd  mov     eax, ebx
0x1800c0bff  mov     rbx, [rsp+38h+arg_8]
0x1800c0c04  add     rsp, 20h
0x1800c0c08  pop     rdi
0x1800c0c09  pop     rsi
0x1800c0c0a  pop     rbp
0x1800c0c0b  retn
```
