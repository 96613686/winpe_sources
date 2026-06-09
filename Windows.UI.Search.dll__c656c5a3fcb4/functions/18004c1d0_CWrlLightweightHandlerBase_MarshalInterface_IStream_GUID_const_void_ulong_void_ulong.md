# CWrlLightweightHandlerBase::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18004c1d0`
- end: `0x18004c3cb`
- name: `?MarshalInterface@CWrlLightweightHandlerBase@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `507`
- prototype: `__int64 __usercall@<rax>(CWrlLightweightHandlerBase *__hidden this@<rcx>, struct IStream *pstm@<rdx>, const struct _GUID *@<r8>, void *@<r9>, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180011724`
- `0x180012f44`
- `0x180015ab8`
- `0x18003e3a8`
- `0x18004c1d0`
- `0x18004c4cc`
- `0x18007b010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x18004c296`
- `SHCORE!IStream_Write` at `0x18004c39e`
- `SHCORE!IStream_Write` at `0x18004c296`
- `SHCORE!IStream_Write` at `0x18004c39e`

## pseudocode

```c
__int64 __fastcall CWrlLightweightHandlerBase::MarshalInterface(
        CWrlLightweightHandlerBase *this,
        struct IStream *pstm,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  const struct _GUID *v11; // rdx
  HRESULT StdMarshaler; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  void *v16; // rcx
  ULONG cb; // [rsp+40h] [rbp-38h] BYREF
  void *v19; // [rsp+48h] [rbp-30h] BYREF
  void *pv; // [rsp+50h] [rbp-28h] BYREF
  __int64 v21; // [rsp+58h] [rbp-20h] BYREF
  __int64 v22; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-10h] BYREF

  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
  StdMarshaler = CWrlLightweightHandlerBase::_GetStdMarshaler(this, v11, &v19);
  if ( StdMarshaler >= 0 )
  {
    StdMarshaler = (*(__int64 (__fastcall **)(void *, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int))(*(_QWORD *)v19 + 40LL))(
                     v19,
                     pstm,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7);
    if ( StdMarshaler >= 0 )
    {
      StdMarshaler = (*(__int64 (__fastcall **)(CWrlLightweightHandlerBase *, const struct _GUID *, void *, _QWORD, void *, unsigned int, char *))(*(_QWORD *)this + 80LL))(
                       this,
                       a3,
                       a4,
                       a5,
                       a6,
                       a7,
                       (char *)this + 16);
      if ( StdMarshaler >= 0 )
      {
        StdMarshaler = IStream_Write(pstm, (char *)this + 16, 4u);
        if ( StdMarshaler >= 0 )
        {
          v13 = *(_QWORD *)pstm;
          v22 = 0;
          StdMarshaler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(v13 + 40))(
                           pstm,
                           0,
                           1,
                           &v22);
          if ( StdMarshaler >= 0 )
          {
            StdMarshaler = (*(__int64 (__fastcall **)(CWrlLightweightHandlerBase *, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int))(*(_QWORD *)this + 88LL))(
                             this,
                             pstm,
                             a3,
                             a4,
                             a5,
                             a6,
                             a7);
            if ( StdMarshaler >= 0 )
            {
              v14 = *(_QWORD *)pstm;
              v21 = 0;
              StdMarshaler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(v14 + 40))(
                               pstm,
                               0,
                               1,
                               &v21);
              if ( StdMarshaler >= 0 )
              {
                v15 = *((unsigned int *)this + 4);
                if ( v21 - v22 <= v15 )
                {
                  if ( v21 - v22 < v15 )
                  {
                    cb = 0;
                    StdMarshaler = ULongLongToULong(v15 - (v21 - v22), &cb);
                    if ( StdMarshaler >= 0 )
                    {
                      pv = 0;
                      v23 = 0;
                      StdMarshaler = ULongLongMult(cb, 1u, &v23);
                      if ( StdMarshaler >= 0 )
                      {
                        StdMarshaler = CTCoAllocPolicy::Alloc(v16, 1u, v23, &pv);
                        if ( StdMarshaler >= 0 )
                          StdMarshaler = IStream_Write(pstm, pv, cb);
                      }
                      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pv);
                    }
                  }
                }
                else
                {
                  StdMarshaler = -2147467259;
                }
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v19);
  return (unsigned int)StdMarshaler;
}

```

## disassembly

```asm
0x18004c1d0  push    rbp
0x18004c1d2  push    rbx
0x18004c1d3  push    rsi
0x18004c1d4  push    rdi
0x18004c1d5  push    r12
0x18004c1d7  push    r13
0x18004c1d9  push    r14
0x18004c1db  push    r15
0x18004c1dd  mov     rbp, rsp
0x18004c1e0  sub     rsp, 78h
0x18004c1e4  mov     r14, rcx
0x18004c1e7  mov     [rbp+var_30], 0
0x18004c1ef  lea     rcx, [rbp+var_30]
0x18004c1f3  mov     r12, r9
0x18004c1f6  mov     r13, r8
0x18004c1f9  mov     rsi, rdx
0x18004c1fc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004c201  lea     r8, [rbp+var_30]; void **
0x18004c205  mov     rcx, r14; this
0x18004c208  call    ?_GetStdMarshaler@CWrlLightweightHandlerBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CWrlLightweightHandlerBase::_GetStdMarshaler(_GUID const &,void * *)
0x18004c20d  mov     edi, eax
0x18004c20f  test    eax, eax
0x18004c211  js      loc_18004C3AF
0x18004c217  mov     rdx, [rbp+arg_28]
0x18004c21b  mov     r9, r12
0x18004c21e  mov     rcx, [rbp+var_30]
0x18004c222  mov     r8, r13
0x18004c225  mov     ebx, [rbp+arg_30]
0x18004c228  mov     dword ptr [rsp+78h+var_48], ebx
0x18004c22c  mov     [rsp+78h+var_50], rdx
0x18004c231  mov     rax, [rcx]
0x18004c234  mov     edx, [rbp+arg_20]
0x18004c237  mov     dword ptr [rsp+78h+var_58], edx
0x18004c23b  mov     rdx, rsi
0x18004c23e  mov     rax, [rax+28h]
0x18004c242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c247  mov     edi, eax
0x18004c249  test    eax, eax
0x18004c24b  js      loc_18004C3AF
0x18004c251  mov     rax, [r14]
0x18004c254  lea     r15, [r14+10h]
0x18004c258  mov     rcx, [rbp+arg_28]
0x18004c25c  mov     r8, r12
0x18004c25f  mov     r9d, [rbp+arg_20]
0x18004c263  mov     rdx, r13
0x18004c266  mov     [rsp+78h+var_48], r15
0x18004c26b  mov     rax, [rax+50h]
0x18004c26f  mov     dword ptr [rsp+78h+var_50], ebx
0x18004c273  mov     [rsp+78h+var_58], rcx
0x18004c278  mov     rcx, r14
0x18004c27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c280  mov     edi, eax
0x18004c282  test    eax, eax
0x18004c284  js      loc_18004C3AF
0x18004c28a  mov     r8d, 4; cb
0x18004c290  mov     rdx, r15; pv
0x18004c293  mov     rcx, rsi; pstm
0x18004c296  call    cs:__imp_IStream_Write
0x18004c29c  mov     edi, eax
0x18004c29e  test    eax, eax
0x18004c2a0  js      loc_18004C3AF
0x18004c2a6  mov     rax, [rsi]
0x18004c2a9  lea     r9, [rbp+var_18]
0x18004c2ad  xor     ebx, ebx
0x18004c2af  mov     rcx, rsi
0x18004c2b2  mov     edx, ebx
0x18004c2b4  mov     [rbp+var_18], rbx
0x18004c2b8  mov     rax, [rax+28h]
0x18004c2bc  lea     r8d, [rbx+1]
0x18004c2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2c5  mov     edi, eax
0x18004c2c7  test    eax, eax
0x18004c2c9  js      loc_18004C3AF
0x18004c2cf  mov     ecx, [rbp+arg_30]
0x18004c2d2  mov     r9, r12
0x18004c2d5  mov     rax, [r14]
0x18004c2d8  mov     r8, r13
0x18004c2db  mov     dword ptr [rsp+78h+var_48], ecx
0x18004c2df  mov     rdx, rsi
0x18004c2e2  mov     rcx, [rbp+arg_28]
0x18004c2e6  mov     [rsp+78h+var_50], rcx
0x18004c2eb  mov     ecx, [rbp+arg_20]
0x18004c2ee  mov     rax, [rax+58h]
0x18004c2f2  mov     dword ptr [rsp+78h+var_58], ecx
0x18004c2f6  mov     rcx, r14
0x18004c2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2fe  xor     r14d, r14d
0x18004c301  mov     edi, eax
0x18004c303  test    eax, eax
0x18004c305  js      loc_18004C3AF
0x18004c30b  mov     rax, [rsi]
0x18004c30e  lea     r12d, [rbx+1]
0x18004c312  lea     r9, [rbp+var_20]
0x18004c316  mov     [rbp+var_20], r14
0x18004c31a  mov     r8d, r12d
0x18004c31d  mov     edx, ebx
0x18004c31f  mov     rcx, rsi
0x18004c322  mov     rax, [rax+28h]
0x18004c326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c32b  mov     edi, eax
0x18004c32d  test    eax, eax
0x18004c32f  js      short loc_18004C3AF
0x18004c331  mov     rax, [rbp+var_20]
0x18004c335  sub     rax, [rbp+var_18]
0x18004c339  mov     ecx, [r15]
0x18004c33c  cmp     rax, rcx
0x18004c33f  jbe     short loc_18004C348
0x18004c341  mov     edi, 80004005h
0x18004c346  jmp     short loc_18004C3AF
0x18004c348  jnb     short loc_18004C3AF
0x18004c34a  sub     rcx, rax; unsigned __int64
0x18004c34d  mov     [rbp+cb], r14d
0x18004c351  lea     rdx, [rbp+cb]; unsigned int *
0x18004c355  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004c35a  mov     edi, eax
0x18004c35c  test    eax, eax
0x18004c35e  js      short loc_18004C3AF
0x18004c360  mov     ecx, [rbp+cb]; unsigned __int64
0x18004c363  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18004c367  mov     rdx, r12; unsigned __int64
0x18004c36a  mov     [rbp+pv], r14
0x18004c36e  mov     [rbp+var_10], r14
0x18004c372  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004c377  mov     edi, eax
0x18004c379  test    eax, eax
0x18004c37b  js      short loc_18004C3A6
0x18004c37d  mov     r8, [rbp+var_10]; unsigned __int64
0x18004c381  lea     r9, [rbp+pv]; void **
0x18004c385  mov     edx, r12d; unsigned int
0x18004c388  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004c38d  mov     edi, eax
0x18004c38f  test    eax, eax
0x18004c391  js      short loc_18004C3A6
0x18004c393  mov     r8d, [rbp+cb]; cb
0x18004c397  mov     rcx, rsi; pstm
0x18004c39a  mov     rdx, [rbp+pv]; pv
0x18004c39e  call    cs:__imp_IStream_Write
0x18004c3a4  mov     edi, eax
0x18004c3a6  lea     rcx, [rbp+pv]
0x18004c3aa  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18004c3af  lea     rcx, [rbp+var_30]
0x18004c3b3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004c3b8  mov     eax, edi
0x18004c3ba  add     rsp, 78h
0x18004c3be  pop     r15
0x18004c3c0  pop     r14
0x18004c3c2  pop     r13
0x18004c3c4  pop     r12
0x18004c3c6  pop     rdi
0x18004c3c7  pop     rsi
0x18004c3c8  pop     rbx
0x18004c3c9  pop     rbp
0x18004c3ca  retn
```
