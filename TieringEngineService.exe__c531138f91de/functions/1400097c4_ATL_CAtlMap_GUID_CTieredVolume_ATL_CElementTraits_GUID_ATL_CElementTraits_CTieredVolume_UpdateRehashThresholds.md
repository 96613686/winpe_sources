# ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::UpdateRehashThresholds(void)

- ea: `0x1400097c4`
- end: `0x14000983b`
- name: `?UpdateRehashThresholds@?$CAtlMap@U_GUID@@PEAVCTieredVolume@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAVCTieredVolume@@@4@@ATL@@AEAAXXZ`
- size: `119`
- prototype: `unsigned __int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004fa0`
- `0x140006680`
- `0x140008700`
- `0x140008828`

## callees

- `0x1400097c4`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::UpdateRehashThresholds(
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
0x1400097c4  mov     eax, [rcx+10h]
0x1400097c7  xorps   xmm0, xmm0
0x1400097ca  movss   xmm2, cs:__real@5f000000
0x1400097d2  xor     edx, edx
0x1400097d4  mov     r8, 8000000000000000h
0x1400097de  cvtsi2ss xmm0, rax
0x1400097e3  movaps  xmm1, xmm0
0x1400097e6  mulss   xmm1, dword ptr [rcx+1Ch]
0x1400097eb  comiss  xmm1, xmm2
0x1400097ee  jb      short loc_1400097FC
0x1400097f0  subss   xmm1, xmm2
0x1400097f4  comiss  xmm1, xmm2
0x1400097f7  jnb     short loc_1400097FC
0x1400097f9  mov     rdx, r8
0x1400097fc  mulss   xmm0, dword ptr [rcx+18h]
0x140009801  cvttss2si rax, xmm1
0x140009806  add     rax, rdx
0x140009809  xor     edx, edx
0x14000980b  comiss  xmm0, xmm2
0x14000980e  mov     [rcx+20h], rax
0x140009812  jb      short loc_140009820
0x140009814  subss   xmm0, xmm2
0x140009818  comiss  xmm0, xmm2
0x14000981b  jnb     short loc_140009820
0x14000981d  mov     rdx, r8
0x140009820  cvttss2si rax, xmm0
0x140009825  add     rax, rdx
0x140009828  mov     [rcx+28h], rax
0x14000982c  cmp     rax, 11h
0x140009830  jnb     short locret_14000983A
0x140009832  mov     qword ptr [rcx+28h], 0
0x14000983a  retn
```
