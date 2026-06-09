# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(void)

- ea: `0x180006ce8`
- end: `0x180006d5f`
- name: `?UpdateRehashThresholds@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXXZ`
- size: `119`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002a24`
- `0x180004554`
- `0x180005744`
- `0x180005874`
- `0x1800059a4`
- `0x180005ad4`

## callees

- `0x180006ce8`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::UpdateRehashThresholds(
        __int64 a1)
{
  unsigned __int64 v1; // rdx
  float v2; // xmm0_4
  float v3; // xmm1_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 result; // rax

  v1 = 0;
  v2 = (float)*(int *)(a1 + 16);
  v3 = v2 * *(float *)(a1 + 28);
  if ( v3 >= 9.223372e18 )
  {
    v3 = v3 - 9.223372e18;
    if ( v3 < 9.223372e18 )
      v1 = 0x8000000000000000uLL;
  }
  v4 = v2 * *(float *)(a1 + 24);
  v5 = v1 + (unsigned int)(int)v3;
  v6 = 0;
  *(_QWORD *)(a1 + 32) = v5;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v6 = 0x8000000000000000uLL;
  }
  result = v6 + (unsigned int)(int)v4;
  *(_QWORD *)(a1 + 40) = result;
  if ( result < 0x11 )
    *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180006ce8  mov     eax, [rcx+10h]
0x180006ceb  xorps   xmm0, xmm0
0x180006cee  movss   xmm2, cs:__real@5f000000
0x180006cf6  xor     edx, edx
0x180006cf8  mov     r8, 8000000000000000h
0x180006d02  cvtsi2ss xmm0, rax
0x180006d07  movaps  xmm1, xmm0
0x180006d0a  mulss   xmm1, dword ptr [rcx+1Ch]
0x180006d0f  comiss  xmm1, xmm2
0x180006d12  jb      short loc_180006D20
0x180006d14  subss   xmm1, xmm2
0x180006d18  comiss  xmm1, xmm2
0x180006d1b  jnb     short loc_180006D20
0x180006d1d  mov     rdx, r8
0x180006d20  mulss   xmm0, dword ptr [rcx+18h]
0x180006d25  cvttss2si rax, xmm1
0x180006d2a  add     rax, rdx
0x180006d2d  xor     edx, edx
0x180006d2f  comiss  xmm0, xmm2
0x180006d32  mov     [rcx+20h], rax
0x180006d36  jb      short loc_180006D44
0x180006d38  subss   xmm0, xmm2
0x180006d3c  comiss  xmm0, xmm2
0x180006d3f  jnb     short loc_180006D44
0x180006d41  mov     rdx, r8
0x180006d44  cvttss2si rax, xmm0
0x180006d49  add     rax, rdx
0x180006d4c  mov     [rcx+28h], rax
0x180006d50  cmp     rax, 11h
0x180006d54  jnb     short locret_180006D5E
0x180006d56  mov     qword ptr [rcx+28h], 0
0x180006d5e  retn
```
