# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180379d40`
- end: `0x180379edb`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `411`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180379960`
- `0x180379d40`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379d65`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379d88`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dae`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dd4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dfa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e20`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e6a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e98`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379eb7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379d65`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379d88`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dae`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dd4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379dfa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e20`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e6a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379e98`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180379eb7`

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
0x180379d40  mov     [rsp+arg_8], rbx
0x180379d45  mov     [rsp+arg_10], rbp
0x180379d4a  push    rsi
0x180379d4b  push    rdi
0x180379d4c  push    r15
0x180379d4e  sub     rsp, 20h
0x180379d52  mov     rdi, rdx
0x180379d55  mov     rsi, rcx
0x180379d58  lea     rdx, [rcx+6Ch]; pv
0x180379d5c  mov     r8d, 10h; cb
0x180379d62  mov     rcx, rdi; pstm
0x180379d65  call    cs:__imp_IStream_Write
0x180379d6c  nop     dword ptr [rax+rax+00h]
0x180379d71  mov     ebx, eax
0x180379d73  test    eax, eax
0x180379d75  js      loc_180379EC5
0x180379d7b  lea     rdx, [rsi+7Ch]; pv
0x180379d7f  mov     r8d, 4; cb
0x180379d85  mov     rcx, rdi; pstm
0x180379d88  call    cs:__imp_IStream_Write
0x180379d8f  nop     dword ptr [rax+rax+00h]
0x180379d94  mov     ebx, eax
0x180379d96  test    eax, eax
0x180379d98  js      loc_180379EC5
0x180379d9e  mov     r15d, 1
0x180379da4  lea     rdx, [rsi+61h]; pv
0x180379da8  mov     r8d, r15d; cb
0x180379dab  mov     rcx, rdi; pstm
0x180379dae  call    cs:__imp_IStream_Write
0x180379db5  nop     dword ptr [rax+rax+00h]
0x180379dba  mov     ebx, eax
0x180379dbc  test    eax, eax
0x180379dbe  js      loc_180379EC5
0x180379dc4  mov     r8d, r15d; cb
0x180379dc7  mov     [rsp+38h+pv], 0
0x180379dcc  lea     rdx, [rsp+38h+pv]; pv
0x180379dd1  mov     rcx, rdi; pstm
0x180379dd4  call    cs:__imp_IStream_Write
0x180379ddb  nop     dword ptr [rax+rax+00h]
0x180379de0  mov     ebx, eax
0x180379de2  test    eax, eax
0x180379de4  js      loc_180379E78
0x180379dea  lea     rbp, [rsi+88h]
0x180379df1  mov     r8d, r15d; cb
0x180379df4  mov     rdx, rbp; pv
0x180379df7  mov     rcx, rdi; pstm
0x180379dfa  call    cs:__imp_IStream_Write
0x180379e01  nop     dword ptr [rax+rax+00h]
0x180379e06  mov     ebx, eax
0x180379e08  test    eax, eax
0x180379e0a  js      short loc_180379E78
0x180379e0c  cmp     byte ptr [rbp+0], 0
0x180379e10  jz      short loc_180379E32
0x180379e12  lea     rdx, [rsi+8Ch]; pv
0x180379e19  mov     rcx, rdi; pstm
0x180379e1c  lea     r8d, [r15+3]; cb
0x180379e20  call    cs:__imp_IStream_Write
0x180379e27  nop     dword ptr [rax+rax+00h]
0x180379e2c  mov     ebx, eax
0x180379e2e  test    eax, eax
0x180379e30  js      short loc_180379E78
0x180379e32  lea     rbp, [rsi+90h]
0x180379e39  mov     r8d, r15d; cb
0x180379e3c  mov     rdx, rbp; pv
0x180379e3f  mov     rcx, rdi; pstm
0x180379e42  call    cs:__imp_IStream_Write
0x180379e49  nop     dword ptr [rax+rax+00h]
0x180379e4e  mov     ebx, eax
0x180379e50  test    eax, eax
0x180379e52  js      short loc_180379E78
0x180379e54  cmp     byte ptr [rbp+0], 0
0x180379e58  jz      short loc_180379E78
0x180379e5a  lea     rdx, [rsi+94h]; pv
0x180379e61  mov     r8d, 4; cb
0x180379e67  mov     rcx, rdi; pstm
0x180379e6a  call    cs:__imp_IStream_Write
0x180379e71  nop     dword ptr [rax+rax+00h]
0x180379e76  mov     ebx, eax
0x180379e78  mov     dl, r15b
0x180379e7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x180379e82  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180379e87  test    ebx, ebx
0x180379e89  js      short loc_180379EC5
0x180379e8b  lea     rdx, [rsi+68h]; pv
0x180379e8f  mov     r8d, 4; cb
0x180379e95  mov     rcx, rdi; pstm
0x180379e98  call    cs:__imp_IStream_Write
0x180379e9f  nop     dword ptr [rax+rax+00h]
0x180379ea4  mov     ebx, eax
0x180379ea6  test    eax, eax
0x180379ea8  js      short loc_180379EC5
0x180379eaa  lea     rdx, [rsi+0A0h]; pv
0x180379eb1  mov     r8d, r15d; cb
0x180379eb4  mov     rcx, rdi; pstm
0x180379eb7  call    cs:__imp_IStream_Write
0x180379ebe  nop     dword ptr [rax+rax+00h]
0x180379ec3  mov     ebx, eax
0x180379ec5  mov     rbp, [rsp+38h+arg_10]
0x180379eca  mov     eax, ebx
0x180379ecc  mov     rbx, [rsp+38h+arg_8]
0x180379ed1  add     rsp, 20h
0x180379ed5  pop     r15
0x180379ed7  pop     rdi
0x180379ed8  pop     rsi
0x180379ed9  retn
```
