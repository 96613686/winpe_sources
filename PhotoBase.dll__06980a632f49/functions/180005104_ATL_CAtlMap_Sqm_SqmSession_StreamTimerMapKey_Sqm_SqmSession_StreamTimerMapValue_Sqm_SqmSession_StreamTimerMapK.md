# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)

- ea: `0x180005104`
- end: `0x180005199`
- name: `?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z`
- size: `149`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180004000`
- `0x18000408c`
- `0x180004128`
- `0x1800041b4`
- `0x1800049f0`
- `0x180004b14`
- `0x180004c6c`
- `0x180004dd8`
- `0x180005744`
- `0x180005874`
- `0x1800059a4`
- `0x180005ad4`
- `0x180005c54`
- `0x180005d14`
- `0x180005dd4`
- `0x180005e94`

## callees

- `0x180005104`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
        __int64 a1,
        __int64 a2)
{
  double v2; // xmm1_8
  float v3; // xmm0_4
  unsigned __int64 v4; // rcx
  double v5; // xmm1_8
  int v6; // edx
  unsigned __int64 result; // rax

  if ( a2 < 0 )
    v2 = (double)(int)(a2 & 1 | ((unsigned __int64)a2 >> 1)) + (double)(int)(a2 & 1 | ((unsigned __int64)a2 >> 1));
  else
    v2 = (double)(int)a2;
  v3 = *(float *)(a1 + 20);
  v4 = 0;
  v5 = v2 / v3;
  if ( v5 >= 9.223372036854776e18 )
  {
    v5 = v5 - 9.223372036854776e18;
    if ( v5 < 9.223372036854776e18 )
      v4 = 0x8000000000000000uLL;
  }
  v6 = 0;
  result = v4 + (unsigned int)(int)v5;
  if ( result > 0xFFFFFFFF )
  {
    result = 0xFFFFFFFFLL;
    goto LABEL_10;
  }
  if ( (unsigned int)result > 0x11 )
  {
    do
LABEL_10:
      ++v6;
    while ( (unsigned int)result > *((_DWORD *)`ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize'::`2'::s_anPrimes
                                   + v6) );
  }
  if ( *((_DWORD *)`ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize'::`2'::s_anPrimes
       + v6) != -1 )
    return *((unsigned int *)`ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize'::`2'::s_anPrimes
           + v6);
  return result;
}

```

## disassembly

```asm
0x180005104  xorps   xmm1, xmm1
0x180005107  test    rdx, rdx
0x18000510a  js      short loc_180005113
0x18000510c  cvtsi2sd xmm1, rdx
0x180005111  jmp     short loc_180005128
0x180005113  mov     rax, rdx
0x180005116  and     edx, 1
0x180005119  shr     rax, 1
0x18000511c  or      rax, rdx
0x18000511f  cvtsi2sd xmm1, rax
0x180005124  addsd   xmm1, xmm1
0x180005128  movss   xmm0, dword ptr [rcx+14h]
0x18000512d  xor     ecx, ecx
0x18000512f  cvtps2pd xmm0, xmm0
0x180005132  divsd   xmm1, xmm0
0x180005136  movsd   xmm0, cs:__real@43e0000000000000
0x18000513e  comisd  xmm1, xmm0
0x180005142  jb      short loc_18000515B
0x180005144  subsd   xmm1, xmm0
0x180005148  comisd  xmm1, xmm0
0x18000514c  jnb     short loc_18000515B
0x18000514e  mov     rax, 8000000000000000h
0x180005158  mov     rcx, rax
0x18000515b  cvttsd2si rax, xmm1
0x180005160  mov     r8d, 0FFFFFFFFh
0x180005166  lea     r9, ?s_anPrimes@?1??PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z@4QBIB; uint const near * const `ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)'::`2'::s_anPrimes
0x18000516d  xor     edx, edx
0x18000516f  add     rax, rcx
0x180005172  cmp     rax, r8
0x180005175  jbe     short loc_18000517C
0x180005177  mov     eax, r8d
0x18000517a  jmp     short loc_180005181
0x18000517c  cmp     eax, 11h
0x18000517f  jbe     short loc_18000518C
0x180005181  inc     edx
0x180005183  movsxd  rcx, edx
0x180005186  cmp     eax, [r9+rcx*4]
0x18000518a  ja      short loc_180005181
0x18000518c  movsxd  rcx, edx
0x18000518f  cmp     [r9+rcx*4], r8d
0x180005193  cmovnz  eax, [r9+rcx*4]
0x180005198  retn
```
