# ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)

- ea: `0x18000b684`
- end: `0x18000b773`
- name: `?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, PROPVARIANT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b0a0`
- `0x18000bc38`
- `0x18001eb74`

## callees

- `0x180007b20`
- `0x180007d90`
- `0x18000b684`
- `0x18000bfc0`
- `0x18000e364`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b746`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b746`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b6a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b752`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b6a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b752`

## pseudocode

```c
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
0x18000b684  mov     [rsp-28h+arg_8], rbx
0x18000b689  mov     [rsp-28h+arg_10], rsi
0x18000b68e  push    rbp
0x18000b68f  push    rdi
0x18000b690  push    r12
0x18000b692  push    r14
0x18000b694  push    r15
0x18000b696  mov     rbp, rsp
0x18000b699  sub     rsp, 40h
0x18000b69d  mov     r14, rdx
0x18000b6a0  mov     r15, rcx
0x18000b6a3  mov     rcx, rdx; pvar
0x18000b6a6  call    cs:__imp_PropVariantClear
0x18000b6ac  xorps   xmm0, xmm0
0x18000b6af  xor     eax, eax
0x18000b6b1  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18000b6b5  mov     qword ptr [rbp+pvarSrc+10h], rax
0x18000b6b9  movsxd  rsi, dword ptr [r15+8]
0x18000b6bd  test    esi, esi
0x18000b6bf  jle     short loc_18000B73F
0x18000b6c1  mov     eax, 101Fh
0x18000b6c6  mov     word ptr [rbp+pvarSrc], ax
0x18000b6ca  mov     dword ptr [rbp+pvarSrc+8], esi
0x18000b6cd  mov     [rbp+pullResult], 0
0x18000b6d5  mov     rcx, rsi; ullMultiplicand
0x18000b6d8  lea     r8, [rbp+pullResult]; pullResult
0x18000b6dc  mov     edx, 8; ullMultiplier
0x18000b6e1  call    ULongLongMult
0x18000b6e6  mov     ebx, eax
0x18000b6e8  test    eax, eax
0x18000b6ea  js      short loc_18000B74E
0x18000b6ec  lea     rdx, [rbp+pvarSrc+10h]; void **
0x18000b6f0  mov     rcx, [rbp+pullResult]; Size
0x18000b6f4  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x18000b6f9  mov     ebx, eax
0x18000b6fb  test    eax, eax
0x18000b6fd  js      short loc_18000B74E
0x18000b6ff  mov     [rbp+pullResult], 0
0x18000b707  xor     edi, edi
0x18000b709  test    ebx, ebx
0x18000b70b  js      short loc_18000B74E
0x18000b70d  mov     edx, edi
0x18000b70f  mov     rcx, r15
0x18000b712  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x18000b717  lea     rdx, [rbp+pullResult]; unsigned __int16 **
0x18000b71b  mov     rcx, [rax]; unsigned __int16 *
0x18000b71e  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x18000b723  mov     ebx, eax
0x18000b725  test    eax, eax
0x18000b727  js      short loc_18000B735
0x18000b729  mov     rcx, [rbp+pullResult]
0x18000b72d  mov     rax, qword ptr [rbp+pvarSrc+10h]
0x18000b731  mov     [rax+rdi*8], rcx
0x18000b735  inc     edi
0x18000b737  cmp     edi, esi
0x18000b739  jl      short loc_18000B709
0x18000b73b  test    ebx, ebx
0x18000b73d  js      short loc_18000B74E
0x18000b73f  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18000b743  mov     rcx, r14; pvarDest
0x18000b746  call    cs:__imp_PropVariantCopy
0x18000b74c  mov     ebx, eax
0x18000b74e  lea     rcx, [rbp+pvarSrc]; pvar
0x18000b752  call    cs:__imp_PropVariantClear
0x18000b758  mov     eax, ebx
0x18000b75a  lea     r11, [rsp+40h+var_s0]
0x18000b75f  mov     rbx, [r11+38h]
0x18000b763  mov     rsi, [r11+40h]
0x18000b767  mov     rsp, r11
0x18000b76a  pop     r15
0x18000b76c  pop     r14
0x18000b76e  pop     r12
0x18000b770  pop     rdi
0x18000b771  pop     rbp
0x18000b772  retn
```
