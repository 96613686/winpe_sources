# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180040180`
- end: `0x1800402da`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003fd94`
- `0x180040180`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1800401a5`
- `SHCORE!IStream_Write` at `0x1800401c2`
- `SHCORE!IStream_Write` at `0x1800401e2`
- `SHCORE!IStream_Write` at `0x180040202`
- `SHCORE!IStream_Write` at `0x18004021e`
- `SHCORE!IStream_Write` at `0x18004023e`
- `SHCORE!IStream_Write` at `0x18004025a`
- `SHCORE!IStream_Write` at `0x18004027c`
- `SHCORE!IStream_Write` at `0x1800402a4`
- `SHCORE!IStream_Write` at `0x1800402bd`
- `SHCORE!IStream_Write` at `0x1800401a5`
- `SHCORE!IStream_Write` at `0x1800401c2`
- `SHCORE!IStream_Write` at `0x1800401e2`
- `SHCORE!IStream_Write` at `0x180040202`
- `SHCORE!IStream_Write` at `0x18004021e`
- `SHCORE!IStream_Write` at `0x18004023e`
- `SHCORE!IStream_Write` at `0x18004025a`
- `SHCORE!IStream_Write` at `0x18004027c`
- `SHCORE!IStream_Write` at `0x1800402a4`
- `SHCORE!IStream_Write` at `0x1800402bd`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactoryBase::v_MarshalAdditionalData(
        CImmersiveWindowFactoryBase *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  char pv; // [rsp+40h] [rbp+8h] BYREF

  v6 = IStream_Write(a2, (char *)this + 108, 0x10u);
  if ( v6 >= 0 )
  {
    v6 = IStream_Write(a2, (char *)this + 124, 4u);
    if ( v6 >= 0 )
    {
      v6 = IStream_Write(a2, (char *)this + 97, 1u);
      if ( v6 >= 0 )
      {
        pv = 0;
        v6 = IStream_Write(a2, &pv, 1u);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 136, 1u);
          if ( v6 >= 0 )
          {
            if ( !*((_BYTE *)this + 136) || (v6 = IStream_Write(a2, (char *)this + 140, 4u), v6 >= 0) )
            {
              v6 = IStream_Write(a2, (char *)this + 144, 1u);
              if ( v6 >= 0 )
              {
                if ( *((_BYTE *)this + 144) )
                  v6 = IStream_Write(a2, (char *)this + 148, 4u);
              }
            }
          }
        }
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl'::`2'::impl,
          v7);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 104, 4u);
          if ( v6 >= 0 )
            return (unsigned int)IStream_Write(a2, (char *)this + 160, 1u);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180040180  mov     [rsp+arg_8], rbx
0x180040185  mov     [rsp+arg_10], rbp
0x18004018a  push    rsi
0x18004018b  push    rdi
0x18004018c  push    r15
0x18004018e  sub     rsp, 20h
0x180040192  mov     rdi, rdx
0x180040195  mov     rsi, rcx
0x180040198  lea     rdx, [rcx+6Ch]; pv
0x18004019c  mov     r8d, 10h; cb
0x1800401a2  mov     rcx, rdi; pstm
0x1800401a5  call    cs:__imp_IStream_Write
0x1800401ab  mov     ebx, eax
0x1800401ad  test    eax, eax
0x1800401af  js      loc_1800402C5
0x1800401b5  lea     rdx, [rsi+7Ch]; pv
0x1800401b9  mov     r8d, 4; cb
0x1800401bf  mov     rcx, rdi; pstm
0x1800401c2  call    cs:__imp_IStream_Write
0x1800401c8  mov     ebx, eax
0x1800401ca  test    eax, eax
0x1800401cc  js      loc_1800402C5
0x1800401d2  mov     r15d, 1
0x1800401d8  lea     rdx, [rsi+61h]; pv
0x1800401dc  mov     r8d, r15d; cb
0x1800401df  mov     rcx, rdi; pstm
0x1800401e2  call    cs:__imp_IStream_Write
0x1800401e8  mov     ebx, eax
0x1800401ea  test    eax, eax
0x1800401ec  js      loc_1800402C5
0x1800401f2  mov     r8d, r15d; cb
0x1800401f5  mov     [rsp+38h+pv], 0
0x1800401fa  lea     rdx, [rsp+38h+pv]; pv
0x1800401ff  mov     rcx, rdi; pstm
0x180040202  call    cs:__imp_IStream_Write
0x180040208  mov     ebx, eax
0x18004020a  test    eax, eax
0x18004020c  js      short loc_180040284
0x18004020e  lea     rbp, [rsi+88h]
0x180040215  mov     r8d, r15d; cb
0x180040218  mov     rdx, rbp; pv
0x18004021b  mov     rcx, rdi; pstm
0x18004021e  call    cs:__imp_IStream_Write
0x180040224  mov     ebx, eax
0x180040226  test    eax, eax
0x180040228  js      short loc_180040284
0x18004022a  cmp     byte ptr [rbp+0], 0
0x18004022e  jz      short loc_18004024A
0x180040230  lea     rdx, [rsi+8Ch]; pv
0x180040237  mov     rcx, rdi; pstm
0x18004023a  lea     r8d, [r15+3]; cb
0x18004023e  call    cs:__imp_IStream_Write
0x180040244  mov     ebx, eax
0x180040246  test    eax, eax
0x180040248  js      short loc_180040284
0x18004024a  lea     rbp, [rsi+90h]
0x180040251  mov     r8d, r15d; cb
0x180040254  mov     rdx, rbp; pv
0x180040257  mov     rcx, rdi; pstm
0x18004025a  call    cs:__imp_IStream_Write
0x180040260  mov     ebx, eax
0x180040262  test    eax, eax
0x180040264  js      short loc_180040284
0x180040266  cmp     byte ptr [rbp+0], 0
0x18004026a  jz      short loc_180040284
0x18004026c  lea     rdx, [rsi+94h]; pv
0x180040273  mov     r8d, 4; cb
0x180040279  mov     rcx, rdi; pstm
0x18004027c  call    cs:__imp_IStream_Write
0x180040282  mov     ebx, eax
0x180040284  mov     dl, r15b
0x180040287  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x18004028e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180040293  test    ebx, ebx
0x180040295  js      short loc_1800402C5
0x180040297  lea     rdx, [rsi+68h]; pv
0x18004029b  mov     r8d, 4; cb
0x1800402a1  mov     rcx, rdi; pstm
0x1800402a4  call    cs:__imp_IStream_Write
0x1800402aa  mov     ebx, eax
0x1800402ac  test    eax, eax
0x1800402ae  js      short loc_1800402C5
0x1800402b0  lea     rdx, [rsi+0A0h]; pv
0x1800402b7  mov     r8d, r15d; cb
0x1800402ba  mov     rcx, rdi; pstm
0x1800402bd  call    cs:__imp_IStream_Write
0x1800402c3  mov     ebx, eax
0x1800402c5  mov     rbp, [rsp+38h+arg_10]
0x1800402ca  mov     eax, ebx
0x1800402cc  mov     rbx, [rsp+38h+arg_8]
0x1800402d1  add     rsp, 20h
0x1800402d5  pop     r15
0x1800402d7  pop     rdi
0x1800402d8  pop     rsi
0x1800402d9  retn
```
