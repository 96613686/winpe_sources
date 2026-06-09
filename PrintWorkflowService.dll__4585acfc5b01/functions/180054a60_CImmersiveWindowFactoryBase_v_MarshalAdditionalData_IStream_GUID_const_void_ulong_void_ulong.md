# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180054a60`
- end: `0x180054bba`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180054514`
- `0x180054a60`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054a85`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054aa2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054ac2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054ae2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054afe`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b1e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b3a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b5c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b84`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b9d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054a85`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054aa2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054ac2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054ae2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054afe`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b1e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b3a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b5c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b84`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180054b9d`

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
0x180054a60  mov     [rsp+arg_8], rbx
0x180054a65  mov     [rsp+arg_10], rbp
0x180054a6a  push    rsi
0x180054a6b  push    rdi
0x180054a6c  push    r15
0x180054a6e  sub     rsp, 20h
0x180054a72  mov     rdi, rdx
0x180054a75  mov     rsi, rcx
0x180054a78  lea     rdx, [rcx+6Ch]; pv
0x180054a7c  mov     r8d, 10h; cb
0x180054a82  mov     rcx, rdi; pstm
0x180054a85  call    cs:__imp_IStream_Write
0x180054a8b  mov     ebx, eax
0x180054a8d  test    eax, eax
0x180054a8f  js      loc_180054BA5
0x180054a95  lea     rdx, [rsi+7Ch]; pv
0x180054a99  mov     r8d, 4; cb
0x180054a9f  mov     rcx, rdi; pstm
0x180054aa2  call    cs:__imp_IStream_Write
0x180054aa8  mov     ebx, eax
0x180054aaa  test    eax, eax
0x180054aac  js      loc_180054BA5
0x180054ab2  mov     r15d, 1
0x180054ab8  lea     rdx, [rsi+61h]; pv
0x180054abc  mov     r8d, r15d; cb
0x180054abf  mov     rcx, rdi; pstm
0x180054ac2  call    cs:__imp_IStream_Write
0x180054ac8  mov     ebx, eax
0x180054aca  test    eax, eax
0x180054acc  js      loc_180054BA5
0x180054ad2  mov     r8d, r15d; cb
0x180054ad5  mov     [rsp+38h+pv], 0
0x180054ada  lea     rdx, [rsp+38h+pv]; pv
0x180054adf  mov     rcx, rdi; pstm
0x180054ae2  call    cs:__imp_IStream_Write
0x180054ae8  mov     ebx, eax
0x180054aea  test    eax, eax
0x180054aec  js      short loc_180054B64
0x180054aee  lea     rbp, [rsi+88h]
0x180054af5  mov     r8d, r15d; cb
0x180054af8  mov     rdx, rbp; pv
0x180054afb  mov     rcx, rdi; pstm
0x180054afe  call    cs:__imp_IStream_Write
0x180054b04  mov     ebx, eax
0x180054b06  test    eax, eax
0x180054b08  js      short loc_180054B64
0x180054b0a  cmp     byte ptr [rbp+0], 0
0x180054b0e  jz      short loc_180054B2A
0x180054b10  lea     rdx, [rsi+8Ch]; pv
0x180054b17  mov     rcx, rdi; pstm
0x180054b1a  lea     r8d, [r15+3]; cb
0x180054b1e  call    cs:__imp_IStream_Write
0x180054b24  mov     ebx, eax
0x180054b26  test    eax, eax
0x180054b28  js      short loc_180054B64
0x180054b2a  lea     rbp, [rsi+90h]
0x180054b31  mov     r8d, r15d; cb
0x180054b34  mov     rdx, rbp; pv
0x180054b37  mov     rcx, rdi; pstm
0x180054b3a  call    cs:__imp_IStream_Write
0x180054b40  mov     ebx, eax
0x180054b42  test    eax, eax
0x180054b44  js      short loc_180054B64
0x180054b46  cmp     byte ptr [rbp+0], 0
0x180054b4a  jz      short loc_180054B64
0x180054b4c  lea     rdx, [rsi+94h]; pv
0x180054b53  mov     r8d, 4; cb
0x180054b59  mov     rcx, rdi; pstm
0x180054b5c  call    cs:__imp_IStream_Write
0x180054b62  mov     ebx, eax
0x180054b64  mov     dl, r15b
0x180054b67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x180054b6e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180054b73  test    ebx, ebx
0x180054b75  js      short loc_180054BA5
0x180054b77  lea     rdx, [rsi+68h]; pv
0x180054b7b  mov     r8d, 4; cb
0x180054b81  mov     rcx, rdi; pstm
0x180054b84  call    cs:__imp_IStream_Write
0x180054b8a  mov     ebx, eax
0x180054b8c  test    eax, eax
0x180054b8e  js      short loc_180054BA5
0x180054b90  lea     rdx, [rsi+0A0h]; pv
0x180054b97  mov     r8d, r15d; cb
0x180054b9a  mov     rcx, rdi; pstm
0x180054b9d  call    cs:__imp_IStream_Write
0x180054ba3  mov     ebx, eax
0x180054ba5  mov     rbp, [rsp+38h+arg_10]
0x180054baa  mov     eax, ebx
0x180054bac  mov     rbx, [rsp+38h+arg_8]
0x180054bb1  add     rsp, 20h
0x180054bb5  pop     r15
0x180054bb7  pop     rdi
0x180054bb8  pop     rsi
0x180054bb9  retn
```
