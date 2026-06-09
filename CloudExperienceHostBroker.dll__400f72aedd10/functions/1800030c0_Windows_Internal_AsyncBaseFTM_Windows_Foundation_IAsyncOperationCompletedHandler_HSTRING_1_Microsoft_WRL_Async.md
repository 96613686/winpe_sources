# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800030c0`
- end: `0x1800034bc`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `1020`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002ce0`
- `0x180002de0`
- `0x180002e10`
- `0x180003040`

## callees

- `0x180002a3c`
- `0x1800030c0`
- `0x1800035a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800034ad`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800034ad`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003481`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003481`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800033cb`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800033cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        signed __int32 *a1)
{
  unsigned int v2; // esi
  LPUNKNOWN v3; // rcx
  int (__fastcall *v4)(signed __int32 *, GUID *, LPUNKNOWN *); // rdi
  __int64 v5; // rcx
  int (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rcx
  LPUNKNOWN v7; // rcx
  int (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rsi
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  LPSTREAM v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  IUnknown *v17; // rdi
  signed __int32 v18[8]; // [rsp+0h] [rbp-59h] BYREF
  __int64 v19; // [rsp+40h] [rbp-19h] BYREF
  GUID v20; // [rsp+50h] [rbp-9h] BYREF
  signed __int32 *v21; // [rsp+60h] [rbp+7h]
  LPSTREAM pStm[2]; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+67h] BYREF
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+D0h] [rbp+77h] BYREF
  LPUNKNOWN pUnk; // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = 0;
  v23 = -2;
  _InterlockedCompareExchange((volatile signed __int32 *)&v23, a1[14], -2);
  if ( !v23 )
    _InterlockedCompareExchange(a1 + 14, 1, 0);
  if ( a1[34] > 0 && _InterlockedIncrement(a1 + 4) == 1 )
  {
    v21 = a1;
    if ( a1 )
      (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
    v3 = 0;
    pUnk = 0;
    if ( Microsoft::WRL::gCausality )
    {
      v23 = 0;
      _InterlockedCompareExchange((volatile signed __int32 *)&v23, a1[14], 0);
      *(GUID *)pStm = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, LPSTREAM *, signed __int32 *, unsigned int))(*(_QWORD *)Microsoft::WRL::gCausality + 56LL))(
        Microsoft::WRL::gCausality,
        0,
        2,
        pStm,
        a1,
        v23);
      v3 = pUnk;
    }
    v4 = **(int (__fastcall ***)(signed __int32 *, GUID *, LPUNKNOWN *))a1;
    if ( v3 )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v3->lpVtbl->Release)(v3);
    }
    if ( v4(a1, &GUID_3e1fe603_f897_5263_b328_0806426b8a79, &pUnk) >= 0 )
    {
      v23 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v23, a1[14], -2);
      v24 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v24 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41,
               &v24) >= 0 )
        {
          if ( Microsoft::WRL::gCausality )
          {
            v20 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, signed __int32 *, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
              Microsoft::WRL::gCausality,
              0,
              2,
              &v20,
              a1,
              0);
          }
          v19 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          v9 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
          v19 = 0;
          if ( v24 )
          {
            v25 = 0;
            v10 = **v24;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
            if ( v10(v9, &GUID_00000144_0000_0000_c000_000000000046, &v25) >= 0
              && (*(_QWORD *)&v20.Data1 = 0,
                  (*(int (__fastcall **)(__int64, int (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64, GUID *))(*(_QWORD *)v25 + 32LL))(
                    v25,
                    v9,
                    2,
                    &v20) >= 0)
              && *(_QWORD *)&v20.Data1 == 1 )
            {
              v16 = v25;
              v11 = 0;
              v25 = 0;
              v19 = v16;
            }
            else
            {
              v11 = v25;
            }
            if ( v11 )
            {
              v25 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          pStm[0] = 0;
          LODWORD(pStm[1]) = 0;
          if ( v19 && v24 )
          {
            v17 = pUnk;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pStm);
            LODWORD(pStm[1]) = CreateStreamOnHGlobal(0, 1, pStm);
            if ( SLODWORD(pStm[1]) >= 0 )
              LODWORD(pStm[1]) = CoMarshalInterface(pStm[0], &GUID_00000000_0000_0000_c000_000000000046, v17, 0, 0, 1u);
          }
          else
          {
            LODWORD(pStm[1]) = -2147467262;
          }
          v12 = (*v24)[3](v24, (GUID *)pUnk, (__int64 *)v23);
          v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
                 v12,
                 v24,
                 *((_QWORD *)a1 + 16));
          if ( _InterlockedExchangeAdd(a1 + 34, 0xFFFFFFFF) == 1 )
          {
            _InterlockedOr(v18, 0);
            v13 = *((_QWORD *)a1 + 15);
            *((_QWORD *)a1 + 15) = 0;
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          if ( Microsoft::WRL::gCausality )
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, _QWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
              Microsoft::WRL::gCausality,
              0,
              2,
              0);
          if ( SLODWORD(pStm[1]) >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)pStm[0] + 40LL))(pStm[0], 0, 0, 0);
            CoReleaseMarshalData(pStm[0]);
          }
          v14 = pStm[0];
          if ( pStm[0] )
          {
            pStm[0] = 0;
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v14 + 16LL))(v14);
          }
          v15 = v19;
          if ( v19 )
          {
            v19 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
        v6 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
      }
      else
      {
        v6 = 0;
      }
      if ( v6 )
      {
        v24 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v6)[2])(v6);
      }
    }
    v7 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v7->lpVtbl->Release)(v7);
    }
    (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x1800030c0  push    rbp
0x1800030c2  push    rbx
0x1800030c3  push    rsi
0x1800030c4  push    rdi
0x1800030c5  push    r14
0x1800030c7  push    r15
0x1800030c9  lea     rbp, [rsp-2Fh]
0x1800030ce  sub     rsp, 88h
0x1800030d5  mov     rbx, rcx
0x1800030d8  xor     r14d, r14d
0x1800030db  mov     esi, r14d
0x1800030de  mov     [rbp+57h+arg_0], 0FFFFFFFEh
0x1800030e5  mov     ecx, [rcx+38h]
0x1800030e8  mov     eax, [rbp+57h+arg_0]
0x1800030eb  lock cmpxchg [rbp+57h+arg_0], ecx
0x1800030f0  mov     r15d, 1
0x1800030f6  cmp     [rbp+57h+arg_0], r14d
0x1800030fa  jz      loc_18000340B
0x180003100  cmp     [rbx+88h], esi
0x180003106  jle     loc_180003258
0x18000310c  mov     eax, r15d
0x18000310f  lock xadd [rbx+10h], eax
0x180003114  inc     eax
0x180003116  cmp     eax, r15d
0x180003119  jnz     loc_180003258
0x18000311f  mov     [rbp+57h+var_50], rbx
0x180003123  test    rbx, rbx
0x180003126  jz      short loc_180003138
0x180003128  mov     rax, [rbx]
0x18000312b  mov     rcx, rbx
0x18000312e  mov     rax, [rax+8]
0x180003132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003137  nop
0x180003138  mov     rcx, r14
0x18000313b  mov     [rbp+57h+pUnk], rcx
0x18000313f  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, 0; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180003147  jz      short loc_180003195
0x180003149  mov     [rbp+57h+arg_0], r14d
0x18000314d  mov     ecx, [rbx+38h]
0x180003150  mov     eax, [rbp+57h+arg_0]
0x180003153  lock cmpxchg [rbp+57h+arg_0], ecx
0x180003158  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000315f  movaps  xmmword ptr [rbp+57h+pStm], xmm0
0x180003163  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000316a  mov     rax, [rcx]
0x18000316d  mov     r10, [rax+38h]
0x180003171  mov     eax, [rbp+57h+arg_0]
0x180003174  mov     [rsp+0B0h+mshlflags], eax
0x180003178  mov     [rsp+0B0h+pvDestContext], rbx
0x18000317d  lea     r9, [rbp+57h+pStm]
0x180003181  xor     edx, edx
0x180003183  mov     r8d, 2
0x180003189  mov     rax, r10
0x18000318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003191  mov     rcx, [rbp+57h+pUnk]
0x180003195  mov     rax, [rbx]
0x180003198  mov     rdi, [rax]
0x18000319b  test    rcx, rcx
0x18000319e  jz      short loc_1800031B1
0x1800031a0  mov     [rbp+57h+pUnk], r14
0x1800031a4  mov     rax, [rcx]
0x1800031a7  mov     rax, [rax+10h]
0x1800031ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b0  nop
0x1800031b1  lea     r8, [rbp+57h+pUnk]
0x1800031b5  lea     rdx, _GUID_3e1fe603_f897_5263_b328_0806426b8a79
0x1800031bc  mov     rcx, rbx
0x1800031bf  mov     rax, rdi
0x1800031c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c7  nop
0x1800031c8  test    eax, eax
0x1800031ca  js      short loc_18000322E
0x1800031cc  mov     [rbp+57h+arg_0], 0FFFFFFFEh
0x1800031d3  mov     ecx, [rbx+38h]
0x1800031d6  mov     eax, [rbp+57h+arg_0]
0x1800031d9  lock cmpxchg [rbp+57h+arg_0], ecx
0x1800031de  mov     [rbp+57h+arg_8], r14
0x1800031e2  lea     rcx, [rbp+57h+arg_8]
0x1800031e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800031eb  mov     rcx, [rbx+78h]
0x1800031ef  test    rcx, rcx
0x1800031f2  jz      short loc_18000326A
0x1800031f4  mov     [rbp+57h+arg_8], r14
0x1800031f8  mov     rax, [rcx]
0x1800031fb  lea     r8, [rbp+57h+arg_8]
0x1800031ff  lea     rdx, _GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41
0x180003206  mov     rax, [rax+18h]
0x18000320a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320f  nop
0x180003210  test    eax, eax
0x180003212  jns     short loc_18000326F
0x180003214  mov     rcx, [rbp+57h+arg_8]
0x180003218  test    rcx, rcx
0x18000321b  jz      short loc_18000322E
0x18000321d  mov     [rbp+57h+arg_8], r14
0x180003221  mov     rax, [rcx]
0x180003224  mov     rax, [rax+10h]
0x180003228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000322d  nop
0x18000322e  mov     rcx, [rbp+57h+pUnk]
0x180003232  test    rcx, rcx
0x180003235  jz      short loc_180003248
0x180003237  mov     [rbp+57h+pUnk], r14
0x18000323b  mov     rax, [rcx]
0x18000323e  mov     rax, [rax+10h]
0x180003242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003247  nop
0x180003248  mov     rax, [rbx]
0x18000324b  mov     rcx, rbx
0x18000324e  mov     rax, [rax+10h]
0x180003252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003257  nop
0x180003258  mov     eax, esi
0x18000325a  add     rsp, 88h
0x180003261  pop     r15
0x180003263  pop     r14
0x180003265  pop     rdi
0x180003266  pop     rsi
0x180003267  pop     rbx
0x180003268  pop     rbp
0x180003269  retn
0x18000326a  mov     rcx, r14
0x18000326d  jmp     short loc_180003218
0x18000326f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180003276  test    rcx, rcx
0x180003279  jz      short loc_1800032A8
0x18000327b  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180003282  movaps  [rbp+57h+var_60], xmm0
0x180003286  mov     rax, [rcx]
0x180003289  mov     [rsp+0B0h+mshlflags], r14d
0x18000328e  mov     [rsp+0B0h+pvDestContext], rbx
0x180003293  lea     r9, [rbp+57h+var_60]
0x180003297  xor     edx, edx
0x180003299  mov     r8d, 2
0x18000329f  mov     rax, [rax+48h]
0x1800032a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a8  mov     [rbp+57h+var_70], r14
0x1800032ac  lea     rcx, [rbp+57h+var_70]
0x1800032b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032b5  mov     rsi, [rbp+57h+arg_8]
0x1800032b9  mov     [rbp+57h+var_70], r14
0x1800032bd  test    rsi, rsi
0x1800032c0  jz      short loc_18000330D
0x1800032c2  mov     [rbp+57h+arg_10], r14
0x1800032c6  mov     rax, [rsi]
0x1800032c9  mov     rdi, [rax]
0x1800032cc  lea     rcx, [rbp+57h+arg_10]
0x1800032d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800032d5  lea     r8, [rbp+57h+arg_10]
0x1800032d9  lea     rdx, _GUID_00000144_0000_0000_c000_000000000046
0x1800032e0  mov     rcx, rsi
0x1800032e3  mov     rax, rdi
0x1800032e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032eb  test    eax, eax
0x1800032ed  jns     loc_180003418
0x1800032f3  mov     rcx, [rbp+57h+arg_10]
0x1800032f7  test    rcx, rcx
0x1800032fa  jz      short loc_18000330D
0x1800032fc  mov     [rbp+57h+arg_10], r14
0x180003300  mov     rax, [rcx]
0x180003303  mov     rax, [rax+10h]
0x180003307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330c  nop
0x18000330d  mov     [rbp+57h+pStm], r14
0x180003311  mov     dword ptr [rbp+57h+pStm+8], r14d
0x180003315  cmp     [rbp+57h+var_70], 0
0x18000331a  jnz     loc_180003460
0x180003320  mov     dword ptr [rbp+57h+pStm+8], 80004002h
0x180003327  mov     rcx, [rbp+57h+arg_8]
0x18000332b  mov     rax, [rcx]
0x18000332e  mov     r8d, [rbp+57h+arg_0]
0x180003332  mov     rdx, [rbp+57h+pUnk]
0x180003336  mov     rax, [rax+18h]
0x18000333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333f  mov     r8, [rbx+80h]
0x180003346  mov     rdx, [rbp+57h+arg_8]
0x18000334a  mov     ecx, eax
0x18000334c  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180003351  mov     esi, eax
0x180003353  mov     ecx, 0FFFFFFFFh
0x180003358  lock xadd [rbx+88h], ecx
0x180003360  cmp     ecx, 1
0x180003363  jnz     short loc_180003384
0x180003365  lock or [rsp+0B0h+var_B0], 0
0x18000336a  mov     rcx, [rbx+78h]
0x18000336e  mov     [rbx+78h], r14
0x180003372  test    rcx, rcx
0x180003375  jz      short loc_180003384
0x180003377  mov     rax, [rcx]
0x18000337a  mov     rax, [rax+10h]
0x18000337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003383  nop
0x180003384  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000338b  test    rcx, rcx
0x18000338e  jz      short loc_1800033A8
0x180003390  mov     rax, [rcx]
0x180003393  xor     r9d, r9d
0x180003396  xor     edx, edx
0x180003398  mov     r8d, 2
0x18000339e  mov     rax, [rax+50h]
0x1800033a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a7  nop
0x1800033a8  cmp     dword ptr [rbp+57h+pStm+8], 0
0x1800033ac  jl      short loc_1800033D2
0x1800033ae  mov     rcx, [rbp+57h+pStm]
0x1800033b2  mov     rdx, r14
0x1800033b5  mov     rax, [rcx]
0x1800033b8  xor     r9d, r9d
0x1800033bb  xor     r8d, r8d
0x1800033be  mov     rax, [rax+28h]
0x1800033c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c7  mov     rcx, [rbp+57h+pStm]; pStm
0x1800033cb  call    cs:__imp_CoReleaseMarshalData
0x1800033d1  nop
0x1800033d2  mov     rcx, [rbp+57h+pStm]
0x1800033d6  test    rcx, rcx
0x1800033d9  jz      short loc_1800033EC
0x1800033db  mov     [rbp+57h+pStm], r14
0x1800033df  mov     rax, [rcx]
0x1800033e2  mov     rax, [rax+10h]
0x1800033e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033eb  nop
0x1800033ec  mov     rcx, [rbp+57h+var_70]
0x1800033f0  test    rcx, rcx
0x1800033f3  jz      short loc_180003406
0x1800033f5  mov     [rbp+57h+var_70], r14
0x1800033f9  mov     rax, [rcx]
0x1800033fc  mov     rax, [rax+10h]
0x180003400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003405  nop
0x180003406  jmp     loc_180003214
0x18000340b  xor     eax, eax
0x18000340d  lock cmpxchg [rbx+38h], r15d
0x180003413  jmp     loc_180003100
0x180003418  mov     qword ptr [rbp+57h+var_60], r14
0x18000341c  mov     rcx, [rbp+57h+arg_10]
0x180003420  mov     rax, [rcx]
0x180003423  lea     r9, [rbp+57h+var_60]
0x180003427  mov     r8d, 2
0x18000342d  mov     rdx, rsi
0x180003430  mov     rax, [rax+20h]
0x180003434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003439  test    eax, eax
0x18000343b  js      loc_1800032F3
0x180003441  cmp     qword ptr [rbp+57h+var_60], 1
0x180003446  jnz     loc_1800032F3
0x18000344c  mov     rax, [rbp+57h+arg_10]
0x180003450  mov     rcx, r14
0x180003453  mov     [rbp+57h+arg_10], rcx
0x180003457  mov     [rbp+57h+var_70], rax
0x18000345b  jmp     loc_1800032F7
0x180003460  cmp     [rbp+57h+arg_8], 0
0x180003465  jz      loc_180003320
0x18000346b  mov     rdi, [rbp+57h+pUnk]
0x18000346f  lea     rcx, [rbp+57h+pStm]
0x180003473  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003478  lea     r8, [rbp+57h+pStm]; ppstm
0x18000347c  mov     edx, r15d; fDeleteOnRelease
0x18000347f  xor     ecx, ecx; hGlobal
0x180003481  call    cs:__imp_CreateStreamOnHGlobal
0x180003487  mov     dword ptr [rbp+57h+pStm+8], eax
0x18000348a  test    eax, eax
0x18000348c  js      loc_180003327
0x180003492  mov     [rsp+0B0h+mshlflags], r15d; mshlflags
0x180003497  mov     [rsp+0B0h+pvDestContext], r14; pvDestContext
0x18000349c  xor     r9d, r9d; dwDestContext
0x18000349f  mov     r8, rdi; pUnk
0x1800034a2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800034a9  mov     rcx, [rbp+57h+pStm]; pStm
0x1800034ad  call    cs:__imp_CoMarshalInterface
0x1800034b3  mov     dword ptr [rbp+57h+pStm+8], eax
0x1800034b6  jmp     loc_180003327
```
