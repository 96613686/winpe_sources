# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180044930`
- end: `0x180044a8a`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180044544`
- `0x180044930`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044955`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044972`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044992`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449b2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449ce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449ee`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a0a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a2c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a54`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a6d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044955`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044972`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044992`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449b2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449ce`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800449ee`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a0a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a2c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a54`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180044a6d`

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
0x180044930  mov     [rsp+arg_8], rbx
0x180044935  mov     [rsp+arg_10], rbp
0x18004493a  push    rsi
0x18004493b  push    rdi
0x18004493c  push    r15
0x18004493e  sub     rsp, 20h
0x180044942  mov     rdi, rdx
0x180044945  mov     rsi, rcx
0x180044948  lea     rdx, [rcx+6Ch]; pv
0x18004494c  mov     r8d, 10h; cb
0x180044952  mov     rcx, rdi; pstm
0x180044955  call    cs:__imp_IStream_Write
0x18004495b  mov     ebx, eax
0x18004495d  test    eax, eax
0x18004495f  js      loc_180044A75
0x180044965  lea     rdx, [rsi+7Ch]; pv
0x180044969  mov     r8d, 4; cb
0x18004496f  mov     rcx, rdi; pstm
0x180044972  call    cs:__imp_IStream_Write
0x180044978  mov     ebx, eax
0x18004497a  test    eax, eax
0x18004497c  js      loc_180044A75
0x180044982  mov     r15d, 1
0x180044988  lea     rdx, [rsi+61h]; pv
0x18004498c  mov     r8d, r15d; cb
0x18004498f  mov     rcx, rdi; pstm
0x180044992  call    cs:__imp_IStream_Write
0x180044998  mov     ebx, eax
0x18004499a  test    eax, eax
0x18004499c  js      loc_180044A75
0x1800449a2  mov     r8d, r15d; cb
0x1800449a5  mov     [rsp+38h+pv], 0
0x1800449aa  lea     rdx, [rsp+38h+pv]; pv
0x1800449af  mov     rcx, rdi; pstm
0x1800449b2  call    cs:__imp_IStream_Write
0x1800449b8  mov     ebx, eax
0x1800449ba  test    eax, eax
0x1800449bc  js      short loc_180044A34
0x1800449be  lea     rbp, [rsi+88h]
0x1800449c5  mov     r8d, r15d; cb
0x1800449c8  mov     rdx, rbp; pv
0x1800449cb  mov     rcx, rdi; pstm
0x1800449ce  call    cs:__imp_IStream_Write
0x1800449d4  mov     ebx, eax
0x1800449d6  test    eax, eax
0x1800449d8  js      short loc_180044A34
0x1800449da  cmp     byte ptr [rbp+0], 0
0x1800449de  jz      short loc_1800449FA
0x1800449e0  lea     rdx, [rsi+8Ch]; pv
0x1800449e7  mov     rcx, rdi; pstm
0x1800449ea  lea     r8d, [r15+3]; cb
0x1800449ee  call    cs:__imp_IStream_Write
0x1800449f4  mov     ebx, eax
0x1800449f6  test    eax, eax
0x1800449f8  js      short loc_180044A34
0x1800449fa  lea     rbp, [rsi+90h]
0x180044a01  mov     r8d, r15d; cb
0x180044a04  mov     rdx, rbp; pv
0x180044a07  mov     rcx, rdi; pstm
0x180044a0a  call    cs:__imp_IStream_Write
0x180044a10  mov     ebx, eax
0x180044a12  test    eax, eax
0x180044a14  js      short loc_180044A34
0x180044a16  cmp     byte ptr [rbp+0], 0
0x180044a1a  jz      short loc_180044A34
0x180044a1c  lea     rdx, [rsi+94h]; pv
0x180044a23  mov     r8d, 4; cb
0x180044a29  mov     rcx, rdi; pstm
0x180044a2c  call    cs:__imp_IStream_Write
0x180044a32  mov     ebx, eax
0x180044a34  mov     dl, r15b
0x180044a37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x180044a3e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044a43  test    ebx, ebx
0x180044a45  js      short loc_180044A75
0x180044a47  lea     rdx, [rsi+68h]; pv
0x180044a4b  mov     r8d, 4; cb
0x180044a51  mov     rcx, rdi; pstm
0x180044a54  call    cs:__imp_IStream_Write
0x180044a5a  mov     ebx, eax
0x180044a5c  test    eax, eax
0x180044a5e  js      short loc_180044A75
0x180044a60  lea     rdx, [rsi+0A0h]; pv
0x180044a67  mov     r8d, r15d; cb
0x180044a6a  mov     rcx, rdi; pstm
0x180044a6d  call    cs:__imp_IStream_Write
0x180044a73  mov     ebx, eax
0x180044a75  mov     rbp, [rsp+38h+arg_10]
0x180044a7a  mov     eax, ebx
0x180044a7c  mov     rbx, [rsp+38h+arg_8]
0x180044a81  add     rsp, 20h
0x180044a85  pop     r15
0x180044a87  pop     rdi
0x180044a88  pop     rsi
0x180044a89  retn
```
