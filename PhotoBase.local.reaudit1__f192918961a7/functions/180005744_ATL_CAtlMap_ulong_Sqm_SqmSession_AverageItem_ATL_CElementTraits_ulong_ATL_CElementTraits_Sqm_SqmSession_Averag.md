# ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::Rehash(uint)

- ea: `0x180005744`
- end: `0x18000586e`
- name: `?Rehash@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@QEAAXI@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180004000`
- `0x1800049f0`

## callees

- `0x180002172`
- `0x180002420`
- `0x180002650`
- `0x180004554`
- `0x180005104`
- `0x180005744`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005844`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005844`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  unsigned int *v5; // rsi
  unsigned __int128 v6; // rax
  int v7; // edx
  void *v8; // r14
  __int64 i; // r9
  __int64 v10; // r10
  __int64 v11; // r8
  __int64 v12; // rdx

  v3 = a2;
  if ( !a2 )
    v3 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           *(_QWORD *)(a1 + 8));
  v5 = (unsigned int *)(a1 + 16);
  if ( v3 != *(_DWORD *)(a1 + 16) )
  {
    if ( *(_QWORD *)a1 )
    {
      v6 = v3 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v3, 8u) )
        *(_QWORD *)&v6 = -1;
      BYTE8(v6) = 1;
      v8 = BasePrivate::New(v6, *((unsigned __int64 *)&v6 + 1), a3);
      if ( !v8 )
        ATL::BaseAtlThrow((BasePrivate *)0x8007000ELL, v7);
      memset_0(v8, 0, 8LL * v3);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v10 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
        if ( v10 )
        {
          do
          {
            v11 = *(_QWORD *)(v10 + 24);
            v12 = *(_DWORD *)(v10 + 32) % v3;
            *(_QWORD *)(v10 + 24) = *((_QWORD *)v8 + v12);
            *((_QWORD *)v8 + (unsigned int)v12) = v10;
            v10 = v11;
          }
          while ( v11 );
        }
      }
      if ( *(_QWORD *)a1 )
        free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      *v5 = v3;
      ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(a1);
    }
    else
    {
      ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(
        (void **)a1,
        v3,
        0);
    }
  }
}

```

## disassembly

```asm
0x180005744  mov     [rsp+arg_8], edx
0x180005748  mov     [rsp+arg_0], rcx
0x18000574d  push    rbx
0x18000574e  push    rsi
0x18000574f  push    rdi
0x180005750  push    r14
0x180005752  push    r15
0x180005754  sub     rsp, 30h
0x180005758  mov     edi, edx
0x18000575a  mov     rbx, rcx
0x18000575d  test    edx, edx
0x18000575f  jnz     short loc_180005770
0x180005761  mov     rdx, [rcx+8]
0x180005765  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x18000576a  mov     edi, eax
0x18000576c  mov     [rsp+58h+arg_8], eax
0x180005770  lea     rsi, [rbx+10h]
0x180005774  mov     [rsp+58h+var_38], rsi
0x180005779  cmp     edi, [rsi]
0x18000577b  jz      loc_180005857
0x180005781  mov     [rsp+58h+arg_10], 0
0x18000578a  cmp     qword ptr [rbx], 0
0x18000578e  jnz     short loc_1800057A2
0x180005790  xor     r8d, r8d
0x180005793  mov     edx, edi
0x180005795  mov     rcx, rbx
0x180005798  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x18000579d  jmp     loc_180005857
0x1800057a2  mov     r15d, edi
0x1800057a5  mov     [rsp+58h+arg_18], r15
0x1800057aa  mov     eax, 8
0x1800057af  mul     r15
0x1800057b2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800057b9  cmovb   rax, rcx
0x1800057bd  mov     dl, 1; unsigned __int64
0x1800057bf  mov     rcx, rax; Size
0x1800057c2  call    ?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800057c7  mov     r14, rax
0x1800057ca  mov     [rsp+58h+arg_10], rax
0x1800057cf  jmp     short loc_1800057E9
0x1800057d1  mov     rbx, [rsp+58h+arg_0]
0x1800057d6  mov     edi, [rsp+58h+arg_8]
0x1800057da  mov     r14, [rsp+58h+arg_10]
0x1800057df  mov     r15, [rsp+58h+arg_18]
0x1800057e4  mov     rsi, [rsp+58h+var_38]
0x1800057e9  test    r14, r14
0x1800057ec  jz      short loc_180005863
0x1800057ee  lea     r8, ds:0[r15*8]; Size
0x1800057f6  xor     edx, edx; Val
0x1800057f8  mov     rcx, r14; void *
0x1800057fb  call    memset_0
0x180005800  xor     r9d, r9d
0x180005803  cmp     [rsi], r9d
0x180005806  jbe     short loc_18000583C
0x180005808  mov     rax, [rbx]
0x18000580b  mov     r10, [rax+r9*8]
0x18000580f  test    r10, r10
0x180005812  jz      short loc_180005834
0x180005814  mov     r8, [r10+18h]
0x180005818  xor     edx, edx
0x18000581a  mov     eax, [r10+20h]
0x18000581e  div     edi
0x180005820  mov     rax, [r14+rdx*8]
0x180005824  mov     [r10+18h], rax
0x180005828  mov     [r14+rdx*8], r10
0x18000582c  mov     r10, r8
0x18000582f  test    r8, r8
0x180005832  jnz     short loc_180005814
0x180005834  inc     r9d
0x180005837  cmp     r9d, [rsi]
0x18000583a  jb      short loc_180005808
0x18000583c  mov     rcx, [rbx]; Block
0x18000583f  test    rcx, rcx
0x180005842  jz      short loc_18000584A
0x180005844  call    cs:__imp_free
0x18000584a  mov     [rbx], r14
0x18000584d  mov     [rsi], edi
0x18000584f  mov     rcx, rbx
0x180005852  call    ?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)
0x180005857  add     rsp, 30h
0x18000585b  pop     r15
0x18000585d  pop     r14
0x18000585f  pop     rdi
0x180005860  pop     rsi
0x180005861  pop     rbx
0x180005862  retn
0x180005863  mov     ecx, 8007000Eh; int
0x180005868  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
