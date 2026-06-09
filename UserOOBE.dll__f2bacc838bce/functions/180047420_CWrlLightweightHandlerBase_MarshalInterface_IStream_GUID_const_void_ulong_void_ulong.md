# CWrlLightweightHandlerBase::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180047420`
- end: `0x180047617`
- name: `?MarshalInterface@CWrlLightweightHandlerBase@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `503`
- prototype: `__int64 __usercall@<rax>(CWrlLightweightHandlerBase *__hidden this@<rcx>, struct IStream *pstm@<rdx>, const struct _GUID *@<r8>, void *@<r9>, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800067b0`
- `0x1800166d8`
- `0x1800231d8`
- `0x1800471a8`
- `0x180047420`
- `0x18004770c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800474e6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800475e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800474e6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800475e3`

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
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  void *v17; // rcx
  void *v19; // [rsp+40h] [rbp-38h] BYREF
  void *pv; // [rsp+48h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-28h] BYREF
  __int64 v22; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int64 v23[3]; // [rsp+60h] [rbp-18h] BYREF

  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
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
                    v16 = v15 - (v21 - v22);
                    if ( v16 > 0xFFFFFFFF )
                    {
                      StdMarshaler = -2147024362;
                    }
                    else
                    {
                      pv = 0;
                      v23[0] = 0;
                      StdMarshaler = ULongLongMult((unsigned int)v16, 1u, v23);
                      if ( StdMarshaler >= 0 )
                      {
                        StdMarshaler = CTCoAllocPolicy::Alloc(v17, 1u, v23[0], &pv);
                        if ( StdMarshaler >= 0 )
                          StdMarshaler = IStream_Write(pstm, pv, v16);
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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return (unsigned int)StdMarshaler;
}

```

## disassembly

```asm
0x180047420  push    rbp
0x180047422  push    rbx
0x180047423  push    rsi
0x180047424  push    rdi
0x180047425  push    r12
0x180047427  push    r13
0x180047429  push    r14
0x18004742b  push    r15
0x18004742d  mov     rbp, rsp
0x180047430  sub     rsp, 78h
0x180047434  mov     r14, rcx
0x180047437  mov     [rbp+var_38], 0
0x18004743f  lea     rcx, [rbp+var_38]
0x180047443  mov     r12, r9
0x180047446  mov     r13, r8
0x180047449  mov     rsi, rdx
0x18004744c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047451  lea     r8, [rbp+var_38]; void **
0x180047455  mov     rcx, r14; this
0x180047458  call    ?_GetStdMarshaler@CWrlLightweightHandlerBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CWrlLightweightHandlerBase::_GetStdMarshaler(_GUID const &,void * *)
0x18004745d  mov     edi, eax
0x18004745f  test    eax, eax
0x180047461  js      loc_1800475FB
0x180047467  mov     rdx, [rbp+arg_28]
0x18004746b  mov     r9, r12
0x18004746e  mov     rcx, [rbp+var_38]
0x180047472  mov     r8, r13
0x180047475  mov     ebx, [rbp+arg_30]
0x180047478  mov     dword ptr [rsp+78h+var_48], ebx
0x18004747c  mov     [rsp+78h+var_50], rdx
0x180047481  mov     rax, [rcx]
0x180047484  mov     edx, [rbp+arg_20]
0x180047487  mov     dword ptr [rsp+78h+var_58], edx
0x18004748b  mov     rdx, rsi
0x18004748e  mov     rax, [rax+28h]
0x180047492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047497  mov     edi, eax
0x180047499  test    eax, eax
0x18004749b  js      loc_1800475FB
0x1800474a1  mov     rax, [r14]
0x1800474a4  lea     r15, [r14+10h]
0x1800474a8  mov     rcx, [rbp+arg_28]
0x1800474ac  mov     r8, r12
0x1800474af  mov     r9d, [rbp+arg_20]
0x1800474b3  mov     rdx, r13
0x1800474b6  mov     [rsp+78h+var_48], r15
0x1800474bb  mov     rax, [rax+50h]
0x1800474bf  mov     dword ptr [rsp+78h+var_50], ebx
0x1800474c3  mov     [rsp+78h+var_58], rcx
0x1800474c8  mov     rcx, r14
0x1800474cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474d0  mov     edi, eax
0x1800474d2  test    eax, eax
0x1800474d4  js      loc_1800475FB
0x1800474da  mov     r8d, 4; cb
0x1800474e0  mov     rdx, r15; pv
0x1800474e3  mov     rcx, rsi; pstm
0x1800474e6  call    cs:__imp_IStream_Write
0x1800474ec  mov     edi, eax
0x1800474ee  test    eax, eax
0x1800474f0  js      loc_1800475FB
0x1800474f6  mov     rax, [rsi]
0x1800474f9  lea     r9, [rbp+var_20]
0x1800474fd  xor     ebx, ebx
0x1800474ff  mov     rcx, rsi
0x180047502  mov     edx, ebx
0x180047504  mov     [rbp+var_20], rbx
0x180047508  mov     rax, [rax+28h]
0x18004750c  lea     r8d, [rbx+1]
0x180047510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047515  mov     edi, eax
0x180047517  test    eax, eax
0x180047519  js      loc_1800475FB
0x18004751f  mov     ecx, [rbp+arg_30]
0x180047522  mov     r9, r12
0x180047525  mov     rax, [r14]
0x180047528  mov     r8, r13
0x18004752b  mov     dword ptr [rsp+78h+var_48], ecx
0x18004752f  mov     rdx, rsi
0x180047532  mov     rcx, [rbp+arg_28]
0x180047536  mov     [rsp+78h+var_50], rcx
0x18004753b  mov     ecx, [rbp+arg_20]
0x18004753e  mov     rax, [rax+58h]
0x180047542  mov     dword ptr [rsp+78h+var_58], ecx
0x180047546  mov     rcx, r14
0x180047549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004754e  xor     r14d, r14d
0x180047551  mov     edi, eax
0x180047553  test    eax, eax
0x180047555  js      loc_1800475FB
0x18004755b  mov     rax, [rsi]
0x18004755e  lea     r12d, [rbx+1]
0x180047562  lea     r9, [rbp+var_28]
0x180047566  mov     [rbp+var_28], r14
0x18004756a  mov     r8d, r12d
0x18004756d  mov     edx, ebx
0x18004756f  mov     rcx, rsi
0x180047572  mov     rax, [rax+28h]
0x180047576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004757b  mov     edi, eax
0x18004757d  test    eax, eax
0x18004757f  js      short loc_1800475FB
0x180047581  mov     rax, [rbp+var_28]
0x180047585  sub     rax, [rbp+var_20]
0x180047589  mov     ebx, [r15]
0x18004758c  cmp     rax, rbx
0x18004758f  jbe     short loc_180047598
0x180047591  mov     edi, 80004005h
0x180047596  jmp     short loc_1800475FB
0x180047598  jnb     short loc_1800475FB
0x18004759a  sub     rbx, rax
0x18004759d  mov     eax, 0FFFFFFFFh
0x1800475a2  cmp     rbx, rax
0x1800475a5  ja      short loc_1800475F6
0x1800475a7  mov     ecx, ebx; unsigned __int64
0x1800475a9  lea     r8, [rbp+var_18]; unsigned __int64 *
0x1800475ad  mov     rdx, r12; unsigned __int64
0x1800475b0  mov     [rbp+pv], r14
0x1800475b4  mov     [rbp+var_18], r14
0x1800475b8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800475bd  mov     edi, eax
0x1800475bf  test    eax, eax
0x1800475c1  js      short loc_1800475EB
0x1800475c3  mov     r8, [rbp+var_18]; unsigned __int64
0x1800475c7  lea     r9, [rbp+pv]; void **
0x1800475cb  mov     edx, r12d; unsigned int
0x1800475ce  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800475d3  mov     edi, eax
0x1800475d5  test    eax, eax
0x1800475d7  js      short loc_1800475EB
0x1800475d9  mov     rdx, [rbp+pv]; pv
0x1800475dd  mov     r8d, ebx; cb
0x1800475e0  mov     rcx, rsi; pstm
0x1800475e3  call    cs:__imp_IStream_Write
0x1800475e9  mov     edi, eax
0x1800475eb  lea     rcx, [rbp+pv]
0x1800475ef  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800475f4  jmp     short loc_1800475FB
0x1800475f6  mov     edi, 80070216h
0x1800475fb  lea     rcx, [rbp+var_38]
0x1800475ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047604  mov     eax, edi
0x180047606  add     rsp, 78h
0x18004760a  pop     r15
0x18004760c  pop     r14
0x18004760e  pop     r13
0x180047610  pop     r12
0x180047612  pop     rdi
0x180047613  pop     rsi
0x180047614  pop     rbx
0x180047615  pop     rbp
0x180047616  retn
```
