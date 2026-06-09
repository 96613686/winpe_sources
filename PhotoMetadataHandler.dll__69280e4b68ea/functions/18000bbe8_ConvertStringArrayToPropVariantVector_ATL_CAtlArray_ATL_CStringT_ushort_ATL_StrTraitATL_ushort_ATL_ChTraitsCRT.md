# ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)

- ea: `0x18000bbe8`
- end: `0x18000bcea`
- name: `?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, PROPVARIANT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b5e0`
- `0x18000c1cc`
- `0x18001fa00`

## callees

- `0x180008ea0`
- `0x1800096a0`
- `0x18000bbe8`
- `0x18000c578`
- `0x18000ea14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000bcb0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000bcb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bcc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bc0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000bcc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertStringArrayToPropVariantVector(__int64 a1, PROPVARIANT *a2)
{
  ULONGLONG v4; // rsi
  HRESULT v5; // ebx
  __int64 v6; // rdi
  const unsigned __int16 **v7; // rax
  PROPVARIANT pvarSrc; // [rsp+20h] [rbp-20h] BYREF
  ULONGLONG pullResult; // [rsp+70h] [rbp+30h] BYREF

  PropVariantClear(a2);
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v4 = *(int *)(a1 + 8);
  if ( (int)v4 <= 0 )
  {
LABEL_10:
    v5 = PropVariantCopy(a2, &pvarSrc);
  }
  else
  {
    pvarSrc.vt = 4127;
    pvarSrc.lVal = v4;
    pullResult = 0;
    v5 = ULongLongMult(v4, 8u, &pullResult);
    if ( v5 >= 0 )
    {
      v5 = CoTaskMemAllocWithInit(pullResult, (void **)&pvarSrc.bstrblobVal.pData);
      if ( v5 >= 0 )
      {
        pullResult = 0;
        v6 = 0;
        while ( v5 >= 0 )
        {
          v7 = (const unsigned __int16 **)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                                            a1,
                                            (unsigned int)v6);
          v5 = PIXStrDup(*v7, (unsigned __int16 **)&pullResult);
          if ( v5 >= 0 )
            *(_QWORD *)&pvarSrc.bstrblobVal.pData[8 * v6] = pullResult;
          v6 = (unsigned int)(v6 + 1);
          if ( (int)v6 >= (int)v4 )
          {
            if ( v5 < 0 )
              break;
            goto LABEL_10;
          }
        }
      }
    }
  }
  PropVariantClear(&pvarSrc);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000bbe8  mov     [rsp-28h+arg_8], rbx
0x18000bbed  mov     [rsp-28h+arg_10], rsi
0x18000bbf2  push    rbp
0x18000bbf3  push    rdi
0x18000bbf4  push    r12
0x18000bbf6  push    r14
0x18000bbf8  push    r15
0x18000bbfa  mov     rbp, rsp
0x18000bbfd  sub     rsp, 40h
0x18000bc01  mov     r14, rdx
0x18000bc04  mov     r15, rcx
0x18000bc07  mov     rcx, rdx; pvar
0x18000bc0a  call    cs:__imp_PropVariantClear
0x18000bc11  nop     dword ptr [rax+rax+00h]
0x18000bc16  xorps   xmm0, xmm0
0x18000bc19  xor     eax, eax
0x18000bc1b  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18000bc1f  mov     qword ptr [rbp+pvarSrc+10h], rax
0x18000bc23  movsxd  rsi, dword ptr [r15+8]
0x18000bc27  test    esi, esi
0x18000bc29  jle     short loc_18000BCA9
0x18000bc2b  mov     eax, 101Fh
0x18000bc30  mov     word ptr [rbp+pvarSrc], ax
0x18000bc34  mov     dword ptr [rbp+pvarSrc+8], esi
0x18000bc37  mov     [rbp+pullResult], 0
0x18000bc3f  mov     rcx, rsi; ullMultiplicand
0x18000bc42  lea     r8, [rbp+pullResult]; pullResult
0x18000bc46  mov     edx, 8; ullMultiplier
0x18000bc4b  call    ULongLongMult
0x18000bc50  mov     ebx, eax
0x18000bc52  test    eax, eax
0x18000bc54  js      short loc_18000BCBE
0x18000bc56  lea     rdx, [rbp+pvarSrc+10h]; void **
0x18000bc5a  mov     rcx, [rbp+pullResult]; Size
0x18000bc5e  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18000bc63  mov     ebx, eax
0x18000bc65  test    eax, eax
0x18000bc67  js      short loc_18000BCBE
0x18000bc69  mov     [rbp+pullResult], 0
0x18000bc71  xor     edi, edi
0x18000bc73  test    ebx, ebx
0x18000bc75  js      short loc_18000BCBE
0x18000bc77  mov     edx, edi
0x18000bc79  mov     rcx, r15
0x18000bc7c  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18000bc81  lea     rdx, [rbp+pullResult]; unsigned __int16 **
0x18000bc85  mov     rcx, [rax]; unsigned __int16 *
0x18000bc88  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x18000bc8d  mov     ebx, eax
0x18000bc8f  test    eax, eax
0x18000bc91  js      short loc_18000BC9F
0x18000bc93  mov     rcx, [rbp+pullResult]
0x18000bc97  mov     rax, qword ptr [rbp+pvarSrc+10h]
0x18000bc9b  mov     [rax+rdi*8], rcx
0x18000bc9f  inc     edi
0x18000bca1  cmp     edi, esi
0x18000bca3  jl      short loc_18000BC73
0x18000bca5  test    ebx, ebx
0x18000bca7  js      short loc_18000BCBE
0x18000bca9  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18000bcad  mov     rcx, r14; pvarDest
0x18000bcb0  call    cs:__imp_PropVariantCopy
0x18000bcb7  nop     dword ptr [rax+rax+00h]
0x18000bcbc  mov     ebx, eax
0x18000bcbe  lea     rcx, [rbp+pvarSrc]; pvar
0x18000bcc2  call    cs:__imp_PropVariantClear
0x18000bcc9  nop     dword ptr [rax+rax+00h]
0x18000bcce  mov     eax, ebx
0x18000bcd0  lea     r11, [rsp+40h+var_s0]
0x18000bcd5  mov     rbx, [r11+38h]
0x18000bcd9  mov     rsi, [r11+40h]
0x18000bcdd  mov     rsp, r11
0x18000bce0  pop     r15
0x18000bce2  pop     r14
0x18000bce4  pop     r12
0x18000bce6  pop     rdi
0x18000bce7  pop     rbp
0x18000bce8  retn
```
