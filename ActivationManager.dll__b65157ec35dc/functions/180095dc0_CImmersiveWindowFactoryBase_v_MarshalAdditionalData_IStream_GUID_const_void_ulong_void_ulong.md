# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180095dc0`
- end: `0x180095f1a`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180095a04`
- `0x180095dc0`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095de5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e02`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e22`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e5e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e9a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095ebc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095ee4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095efd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095de5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e02`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e22`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e5e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095e9a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095ebc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095ee4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180095efd`

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
0x180095dc0  mov     [rsp+arg_8], rbx
0x180095dc5  mov     [rsp+arg_10], rbp
0x180095dca  push    rsi
0x180095dcb  push    rdi
0x180095dcc  push    r15
0x180095dce  sub     rsp, 20h
0x180095dd2  mov     rdi, rdx
0x180095dd5  mov     rsi, rcx
0x180095dd8  lea     rdx, [rcx+6Ch]; pv
0x180095ddc  mov     r8d, 10h; cb
0x180095de2  mov     rcx, rdi; pstm
0x180095de5  call    cs:__imp_IStream_Write
0x180095deb  mov     ebx, eax
0x180095ded  test    eax, eax
0x180095def  js      loc_180095F05
0x180095df5  lea     rdx, [rsi+7Ch]; pv
0x180095df9  mov     r8d, 4; cb
0x180095dff  mov     rcx, rdi; pstm
0x180095e02  call    cs:__imp_IStream_Write
0x180095e08  mov     ebx, eax
0x180095e0a  test    eax, eax
0x180095e0c  js      loc_180095F05
0x180095e12  mov     r15d, 1
0x180095e18  lea     rdx, [rsi+61h]; pv
0x180095e1c  mov     r8d, r15d; cb
0x180095e1f  mov     rcx, rdi; pstm
0x180095e22  call    cs:__imp_IStream_Write
0x180095e28  mov     ebx, eax
0x180095e2a  test    eax, eax
0x180095e2c  js      loc_180095F05
0x180095e32  mov     r8d, r15d; cb
0x180095e35  mov     [rsp+38h+pv], 0
0x180095e3a  lea     rdx, [rsp+38h+pv]; pv
0x180095e3f  mov     rcx, rdi; pstm
0x180095e42  call    cs:__imp_IStream_Write
0x180095e48  mov     ebx, eax
0x180095e4a  test    eax, eax
0x180095e4c  js      short loc_180095EC4
0x180095e4e  lea     rbp, [rsi+88h]
0x180095e55  mov     r8d, r15d; cb
0x180095e58  mov     rdx, rbp; pv
0x180095e5b  mov     rcx, rdi; pstm
0x180095e5e  call    cs:__imp_IStream_Write
0x180095e64  mov     ebx, eax
0x180095e66  test    eax, eax
0x180095e68  js      short loc_180095EC4
0x180095e6a  cmp     byte ptr [rbp+0], 0
0x180095e6e  jz      short loc_180095E8A
0x180095e70  lea     rdx, [rsi+8Ch]; pv
0x180095e77  mov     rcx, rdi; pstm
0x180095e7a  lea     r8d, [r15+3]; cb
0x180095e7e  call    cs:__imp_IStream_Write
0x180095e84  mov     ebx, eax
0x180095e86  test    eax, eax
0x180095e88  js      short loc_180095EC4
0x180095e8a  lea     rbp, [rsi+90h]
0x180095e91  mov     r8d, r15d; cb
0x180095e94  mov     rdx, rbp; pv
0x180095e97  mov     rcx, rdi; pstm
0x180095e9a  call    cs:__imp_IStream_Write
0x180095ea0  mov     ebx, eax
0x180095ea2  test    eax, eax
0x180095ea4  js      short loc_180095EC4
0x180095ea6  cmp     byte ptr [rbp+0], 0
0x180095eaa  jz      short loc_180095EC4
0x180095eac  lea     rdx, [rsi+94h]; pv
0x180095eb3  mov     r8d, 4; cb
0x180095eb9  mov     rcx, rdi; pstm
0x180095ebc  call    cs:__imp_IStream_Write
0x180095ec2  mov     ebx, eax
0x180095ec4  mov     dl, r15b
0x180095ec7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x180095ece  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180095ed3  test    ebx, ebx
0x180095ed5  js      short loc_180095F05
0x180095ed7  lea     rdx, [rsi+68h]; pv
0x180095edb  mov     r8d, 4; cb
0x180095ee1  mov     rcx, rdi; pstm
0x180095ee4  call    cs:__imp_IStream_Write
0x180095eea  mov     ebx, eax
0x180095eec  test    eax, eax
0x180095eee  js      short loc_180095F05
0x180095ef0  lea     rdx, [rsi+0A0h]; pv
0x180095ef7  mov     r8d, r15d; cb
0x180095efa  mov     rcx, rdi; pstm
0x180095efd  call    cs:__imp_IStream_Write
0x180095f03  mov     ebx, eax
0x180095f05  mov     rbp, [rsp+38h+arg_10]
0x180095f0a  mov     eax, ebx
0x180095f0c  mov     rbx, [rsp+38h+arg_8]
0x180095f11  add     rsp, 20h
0x180095f15  pop     r15
0x180095f17  pop     rdi
0x180095f18  pop     rsi
0x180095f19  retn
```
