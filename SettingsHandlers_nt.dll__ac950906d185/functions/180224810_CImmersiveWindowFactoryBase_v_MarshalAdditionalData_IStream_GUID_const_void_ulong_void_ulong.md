# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180224810`
- end: `0x1802249ab`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `411`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180224414`
- `0x180224810`

## import_xrefs

- `SHLWAPI!__imp_IStream_Write` at `0x180224835`
- `SHLWAPI!__imp_IStream_Write` at `0x180224858`
- `SHLWAPI!__imp_IStream_Write` at `0x18022487e`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248a4`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248ca`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248f0`
- `SHLWAPI!__imp_IStream_Write` at `0x180224912`
- `SHLWAPI!__imp_IStream_Write` at `0x18022493a`
- `SHLWAPI!__imp_IStream_Write` at `0x180224968`
- `SHLWAPI!__imp_IStream_Write` at `0x180224987`
- `SHLWAPI!__imp_IStream_Write` at `0x180224835`
- `SHLWAPI!__imp_IStream_Write` at `0x180224858`
- `SHLWAPI!__imp_IStream_Write` at `0x18022487e`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248a4`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248ca`
- `SHLWAPI!__imp_IStream_Write` at `0x1802248f0`
- `SHLWAPI!__imp_IStream_Write` at `0x180224912`
- `SHLWAPI!__imp_IStream_Write` at `0x18022493a`
- `SHLWAPI!__imp_IStream_Write` at `0x180224968`
- `SHLWAPI!__imp_IStream_Write` at `0x180224987`

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
0x180224810  mov     [rsp+arg_8], rbx
0x180224815  mov     [rsp+arg_10], rbp
0x18022481a  push    rsi
0x18022481b  push    rdi
0x18022481c  push    r15
0x18022481e  sub     rsp, 20h
0x180224822  mov     rdi, rdx
0x180224825  mov     rsi, rcx
0x180224828  lea     rdx, [rcx+6Ch]; pv
0x18022482c  mov     r8d, 10h; cb
0x180224832  mov     rcx, rdi; pstm
0x180224835  call    cs:__imp_IStream_Write
0x18022483c  nop     dword ptr [rax+rax+00h]
0x180224841  mov     ebx, eax
0x180224843  test    eax, eax
0x180224845  js      loc_180224995
0x18022484b  lea     rdx, [rsi+7Ch]; pv
0x18022484f  mov     r8d, 4; cb
0x180224855  mov     rcx, rdi; pstm
0x180224858  call    cs:__imp_IStream_Write
0x18022485f  nop     dword ptr [rax+rax+00h]
0x180224864  mov     ebx, eax
0x180224866  test    eax, eax
0x180224868  js      loc_180224995
0x18022486e  mov     r15d, 1
0x180224874  lea     rdx, [rsi+61h]; pv
0x180224878  mov     r8d, r15d; cb
0x18022487b  mov     rcx, rdi; pstm
0x18022487e  call    cs:__imp_IStream_Write
0x180224885  nop     dword ptr [rax+rax+00h]
0x18022488a  mov     ebx, eax
0x18022488c  test    eax, eax
0x18022488e  js      loc_180224995
0x180224894  mov     r8d, r15d; cb
0x180224897  mov     [rsp+38h+pv], 0
0x18022489c  lea     rdx, [rsp+38h+pv]; pv
0x1802248a1  mov     rcx, rdi; pstm
0x1802248a4  call    cs:__imp_IStream_Write
0x1802248ab  nop     dword ptr [rax+rax+00h]
0x1802248b0  mov     ebx, eax
0x1802248b2  test    eax, eax
0x1802248b4  js      loc_180224948
0x1802248ba  lea     rbp, [rsi+88h]
0x1802248c1  mov     r8d, r15d; cb
0x1802248c4  mov     rdx, rbp; pv
0x1802248c7  mov     rcx, rdi; pstm
0x1802248ca  call    cs:__imp_IStream_Write
0x1802248d1  nop     dword ptr [rax+rax+00h]
0x1802248d6  mov     ebx, eax
0x1802248d8  test    eax, eax
0x1802248da  js      short loc_180224948
0x1802248dc  cmp     byte ptr [rbp+0], 0
0x1802248e0  jz      short loc_180224902
0x1802248e2  lea     rdx, [rsi+8Ch]; pv
0x1802248e9  mov     rcx, rdi; pstm
0x1802248ec  lea     r8d, [r15+3]; cb
0x1802248f0  call    cs:__imp_IStream_Write
0x1802248f7  nop     dword ptr [rax+rax+00h]
0x1802248fc  mov     ebx, eax
0x1802248fe  test    eax, eax
0x180224900  js      short loc_180224948
0x180224902  lea     rbp, [rsi+90h]
0x180224909  mov     r8d, r15d; cb
0x18022490c  mov     rdx, rbp; pv
0x18022490f  mov     rcx, rdi; pstm
0x180224912  call    cs:__imp_IStream_Write
0x180224919  nop     dword ptr [rax+rax+00h]
0x18022491e  mov     ebx, eax
0x180224920  test    eax, eax
0x180224922  js      short loc_180224948
0x180224924  cmp     byte ptr [rbp+0], 0
0x180224928  jz      short loc_180224948
0x18022492a  lea     rdx, [rsi+94h]; pv
0x180224931  mov     r8d, 4; cb
0x180224937  mov     rcx, rdi; pstm
0x18022493a  call    cs:__imp_IStream_Write
0x180224941  nop     dword ptr [rax+rax+00h]
0x180224946  mov     ebx, eax
0x180224948  mov     dl, r15b
0x18022494b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x180224952  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180224957  test    ebx, ebx
0x180224959  js      short loc_180224995
0x18022495b  lea     rdx, [rsi+68h]; pv
0x18022495f  mov     r8d, 4; cb
0x180224965  mov     rcx, rdi; pstm
0x180224968  call    cs:__imp_IStream_Write
0x18022496f  nop     dword ptr [rax+rax+00h]
0x180224974  mov     ebx, eax
0x180224976  test    eax, eax
0x180224978  js      short loc_180224995
0x18022497a  lea     rdx, [rsi+0A0h]; pv
0x180224981  mov     r8d, r15d; cb
0x180224984  mov     rcx, rdi; pstm
0x180224987  call    cs:__imp_IStream_Write
0x18022498e  nop     dword ptr [rax+rax+00h]
0x180224993  mov     ebx, eax
0x180224995  mov     rbp, [rsp+38h+arg_10]
0x18022499a  mov     eax, ebx
0x18022499c  mov     rbx, [rsp+38h+arg_8]
0x1802249a1  add     rsp, 20h
0x1802249a5  pop     r15
0x1802249a7  pop     rdi
0x1802249a8  pop     rsi
0x1802249a9  retn
```
