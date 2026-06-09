# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::Rehash(uint)

- ea: `0x180005874`
- end: `0x18000599e`
- name: `?Rehash@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAAXI@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000408c`
- `0x180004b14`

## callees

- `0x180002172`
- `0x180002420`
- `0x180002650`
- `0x180004554`
- `0x180005104`
- `0x180005874`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005974`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005974`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  unsigned int *v5; // rsi
  unsigned __int128 v6; // rax
  _QWORD *v7; // rax
  int v8; // edx
  _QWORD *v9; // r14
  __int64 i; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // rdx

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
      v7 = BasePrivate::New(v6, *((unsigned __int64 *)&v6 + 1), a3);
      v9 = v7;
      if ( !v7 )
        ATL::BaseAtlThrow((BasePrivate *)0x8007000ELL, v8);
      memset_0(v7, 0, 8LL * v3);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
        if ( v11 )
        {
          do
          {
            v12 = *(_QWORD *)(v11 + 64);
            v13 = *(_DWORD *)(v11 + 72) % v3;
            *(_QWORD *)(v11 + 64) = v9[v13];
            v9[(unsigned int)v13] = v11;
            v11 = v12;
          }
          while ( v12 );
        }
      }
      if ( *(_QWORD *)a1 )
        free(*(void **)a1);
      *(_QWORD *)a1 = v9;
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
0x180005874  mov     [rsp+arg_8], edx
0x180005878  mov     [rsp+arg_0], rcx
0x18000587d  push    rbx
0x18000587e  push    rsi
0x18000587f  push    rdi
0x180005880  push    r14
0x180005882  push    r15
0x180005884  sub     rsp, 30h
0x180005888  mov     edi, edx
0x18000588a  mov     rbx, rcx
0x18000588d  test    edx, edx
0x18000588f  jnz     short loc_1800058A0
0x180005891  mov     rdx, [rcx+8]
0x180005895  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x18000589a  mov     edi, eax
0x18000589c  mov     [rsp+58h+arg_8], eax
0x1800058a0  lea     rsi, [rbx+10h]
0x1800058a4  mov     [rsp+58h+var_38], rsi
0x1800058a9  cmp     edi, [rsi]
0x1800058ab  jz      loc_180005987
0x1800058b1  mov     [rsp+58h+arg_10], 0
0x1800058ba  cmp     qword ptr [rbx], 0
0x1800058be  jnz     short loc_1800058D2
0x1800058c0  xor     r8d, r8d
0x1800058c3  mov     edx, edi
0x1800058c5  mov     rcx, rbx
0x1800058c8  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x1800058cd  jmp     loc_180005987
0x1800058d2  mov     r15d, edi
0x1800058d5  mov     [rsp+58h+arg_18], r15
0x1800058da  mov     eax, 8
0x1800058df  mul     r15
0x1800058e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800058e9  cmovb   rax, rcx
0x1800058ed  mov     dl, 1; unsigned __int64
0x1800058ef  mov     rcx, rax; Size
0x1800058f2  call    ?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800058f7  mov     r14, rax
0x1800058fa  mov     [rsp+58h+arg_10], rax
0x1800058ff  jmp     short loc_180005919
0x180005901  mov     rbx, [rsp+58h+arg_0]
0x180005906  mov     edi, [rsp+58h+arg_8]
0x18000590a  mov     r14, [rsp+58h+arg_10]
0x18000590f  mov     r15, [rsp+58h+arg_18]
0x180005914  mov     rsi, [rsp+58h+var_38]
0x180005919  test    r14, r14
0x18000591c  jz      short loc_180005993
0x18000591e  lea     r8, ds:0[r15*8]; Size
0x180005926  xor     edx, edx; Val
0x180005928  mov     rcx, r14; void *
0x18000592b  call    memset_0
0x180005930  xor     r9d, r9d
0x180005933  cmp     [rsi], r9d
0x180005936  jbe     short loc_18000596C
0x180005938  mov     rax, [rbx]
0x18000593b  mov     r10, [rax+r9*8]
0x18000593f  test    r10, r10
0x180005942  jz      short loc_180005964
0x180005944  mov     r8, [r10+40h]
0x180005948  xor     edx, edx
0x18000594a  mov     eax, [r10+48h]
0x18000594e  div     edi
0x180005950  mov     rax, [r14+rdx*8]
0x180005954  mov     [r10+40h], rax
0x180005958  mov     [r14+rdx*8], r10
0x18000595c  mov     r10, r8
0x18000595f  test    r8, r8
0x180005962  jnz     short loc_180005944
0x180005964  inc     r9d
0x180005967  cmp     r9d, [rsi]
0x18000596a  jb      short loc_180005938
0x18000596c  mov     rcx, [rbx]; Block
0x18000596f  test    rcx, rcx
0x180005972  jz      short loc_18000597A
0x180005974  call    cs:__imp_free
0x18000597a  mov     [rbx], r14
0x18000597d  mov     [rsi], edi
0x18000597f  mov     rcx, rbx
0x180005982  call    ?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)
0x180005987  add     rsp, 30h
0x18000598b  pop     r15
0x18000598d  pop     r14
0x18000598f  pop     rdi
0x180005990  pop     rsi
0x180005991  pop     rbx
0x180005992  retn
0x180005993  mov     ecx, 8007000Eh; int
0x180005998  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
