# ATL::CAtlMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Rehash(uint)

- ea: `0x18002065c`
- end: `0x180020783`
- name: `?Rehash@?$CAtlMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAXI@Z`
- size: `295`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002055c`
- `0x18002fc38`
- `0x18002fe80`

## callees

- `0x18002065c`
- `0x18002078c`
- `0x18002fa28`
- `0x18002fee8`
- `0x180040264`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180020764`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180020764`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800206da`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800206da`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18002070c`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18002070c`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  unsigned int *v5; // rsi
  __int64 v6; // r15
  unsigned __int128 v7; // rax
  void *v8; // r14
  unsigned __int64 v9; // rdx
  __int64 i; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  unsigned int *v13; // [rsp+20h] [rbp-38h]
  unsigned int v15; // [rsp+68h] [rbp+10h]
  void *v16; // [rsp+70h] [rbp+18h]
  __int64 v17; // [rsp+78h] [rbp+20h]

  v15 = a2;
  v3 = a2;
  v4 = a1;
  if ( !a2 )
  {
    v3 = ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(
           a1,
           *(_QWORD *)(a1 + 8));
    v15 = v3;
  }
  v5 = (unsigned int *)(v4 + 16);
  v13 = (unsigned int *)(v4 + 16);
  if ( v3 != *(_DWORD *)(v4 + 16) )
  {
    if ( *(_QWORD *)v4 )
    {
      v6 = v3;
      v17 = v3;
      v7 = v3 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v3, 8u) )
        *(_QWORD *)&v7 = -1;
      try
      {
        BYTE8(v7) = 1;
        v8 = BasePrivate::New((BasePrivate *)v7, *((unsigned __int64 *)&v7 + 1), a3);
        v16 = v8;
      }
      catch ( ... )
      {
        v4 = a1;
        v3 = v15;
        v8 = v16;
        v6 = v17;
        v5 = v13;
      }
      if ( !v8 )
      {
        ATL::BaseAtlThrow(-2147024882);
        __debugbreak();
      }
      memset_0(v8, 0, 8 * v6);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(*(_QWORD *)v4 + 8 * i);
        if ( v11 )
        {
          do
          {
            v12 = *(_QWORD *)(v11 + 8);
            v9 = *(_DWORD *)(v11 + 16) % v3;
            *(_QWORD *)(v11 + 8) = *((_QWORD *)v8 + v9);
            *((_QWORD *)v8 + (unsigned int)v9) = v11;
            v11 = v12;
          }
          while ( v12 );
        }
      }
      BasePrivate::Delete(*(BasePrivate **)v4, (void *)v9);
      *(_QWORD *)v4 = v8;
      *v5 = v3;
      ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(v4);
    }
    else
    {
      ATL::CAtlMap<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::InitHashTable(
        (BasePrivate **)v4,
        (void *)v3,
        0);
    }
  }
}

```

## disassembly

```asm
0x18002065c  mov     [rsp+arg_8], edx
0x180020660  mov     [rsp+arg_0], rcx
0x180020665  push    rbx
0x180020666  push    rsi
0x180020667  push    rdi
0x180020668  push    r14
0x18002066a  push    r15
0x18002066c  sub     rsp, 30h
0x180020670  mov     edi, edx
0x180020672  mov     rbx, rcx
0x180020675  test    edx, edx
0x180020677  jnz     short loc_180020688
0x180020679  mov     rdx, [rcx+8]
0x18002067d  call    ?PickSize@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(unsigned __int64)
0x180020682  mov     edi, eax
0x180020684  mov     [rsp+58h+arg_8], eax
0x180020688  lea     rsi, [rbx+10h]
0x18002068c  mov     [rsp+58h+var_38], rsi
0x180020691  cmp     edi, [rsi]
0x180020693  jz      loc_180020777
0x180020699  mov     [rsp+58h+arg_10], 0
0x1800206a2  cmp     qword ptr [rbx], 0
0x1800206a6  jnz     short loc_1800206BA
0x1800206a8  xor     r8d, r8d
0x1800206ab  mov     edx, edi
0x1800206ad  mov     rcx, rbx
0x1800206b0  call    ?InitHashTable@?$CAtlMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::InitHashTable(uint,bool)
0x1800206b5  jmp     loc_180020777
0x1800206ba  mov     r15d, edi
0x1800206bd  mov     [rsp+58h+arg_18], r15
0x1800206c2  mov     eax, 8
0x1800206c7  mul     r15
0x1800206ca  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800206d1  cmovb   rax, rcx
0x1800206d5  mov     dl, 1
0x1800206d7  mov     rcx, rax
0x1800206da  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800206e0  mov     r14, rax
0x1800206e3  mov     [rsp+58h+arg_10], rax
0x1800206e8  jmp     short loc_180020702
0x1800206ea  mov     rbx, [rsp+58h+arg_0]
0x1800206ef  mov     edi, [rsp+58h+arg_8]
0x1800206f3  mov     r14, [rsp+58h+arg_10]
0x1800206f8  mov     r15, [rsp+58h+arg_18]
0x1800206fd  mov     rsi, [rsp+58h+var_38]
0x180020702  test    r14, r14
0x180020705  jnz     short loc_180020713
0x180020707  mov     ecx, 8007000Eh
0x18002070c  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180020712  int     3; Trap to Debugger
0x180020713  lea     r8, ds:0[r15*8]; Size
0x18002071b  xor     edx, edx; Val
0x18002071d  mov     rcx, r14; void *
0x180020720  call    memset_0
0x180020725  xor     r9d, r9d
0x180020728  cmp     [rsi], r9d
0x18002072b  jbe     short loc_180020761
0x18002072d  mov     rax, [rbx]
0x180020730  mov     r10, [rax+r9*8]
0x180020734  test    r10, r10
0x180020737  jz      short loc_180020759
0x180020739  mov     r8, [r10+8]
0x18002073d  xor     edx, edx
0x18002073f  mov     eax, [r10+10h]
0x180020743  div     edi
0x180020745  mov     rax, [r14+rdx*8]
0x180020749  mov     [r10+8], rax
0x18002074d  mov     [r14+rdx*8], r10
0x180020751  mov     r10, r8
0x180020754  test    r8, r8
0x180020757  jnz     short loc_180020739
0x180020759  inc     r9d
0x18002075c  cmp     r9d, [rsi]
0x18002075f  jb      short loc_18002072D
0x180020761  mov     rcx, [rbx]
0x180020764  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18002076a  mov     [rbx], r14
0x18002076d  mov     [rsi], edi
0x18002076f  mov     rcx, rbx
0x180020772  call    ?UpdateRehashThresholds@?$CAtlMap@PEBUIUnknown@@V?$CComQIPtr@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@ATL@@V?$CElementTraits@PEBUIUnknown@@@3@V?$CComQIPtrElementTraits@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@3@@ATL@@AEAAXXZ; ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(void)
0x180020777  add     rsp, 30h
0x18002077b  pop     r15
0x18002077d  pop     r14
0x18002077f  pop     rdi
0x180020780  pop     rsi
0x180020781  pop     rbx
0x180020782  retn
```
