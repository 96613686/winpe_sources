# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::GetNode(ulong,uint &,uint &,ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::CNode * &)

- ea: `0x1800042b0`
- end: `0x180004307`
- name: `?GetNode@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@AEBAPEAVCNode@12@KAEAI0AEAPEAV312@@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003550`
- `0x18000387c`
- `0x180006388`

## callees

- `0x1800042b0`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::GetNode(
        __int64 a1,
        unsigned int a2,
        int *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  __int64 result; // rax
  __int64 v6; // rcx

  *a4 = a2;
  *a3 = a2 % *(_DWORD *)(a1 + 16);
  if ( !*(_QWORD *)a1 )
    return 0;
  *a5 = 0;
  result = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)*a3);
  if ( !result )
    return 0;
  v6 = 0;
  while ( *(_DWORD *)(result + 72) != *a4 || *(_DWORD *)result != a2 )
  {
    v6 = result;
    result = *(_QWORD *)(result + 64);
    if ( !result )
      return 0;
  }
  *a5 = v6;
  return result;
}

```

## disassembly

```asm
0x1800042b0  mov     [r9], edx
0x1800042b3  mov     r10d, edx
0x1800042b6  xor     edx, edx
0x1800042b8  mov     eax, r10d
0x1800042bb  div     dword ptr [rcx+10h]
0x1800042be  mov     r11, r9
0x1800042c1  mov     [r8], edx
0x1800042c4  cmp     qword ptr [rcx], 0
0x1800042c8  jz      short loc_180004300
0x1800042ca  mov     r9, [rsp+arg_20]
0x1800042cf  mov     qword ptr [r9], 0
0x1800042d6  mov     edx, [r8]
0x1800042d9  mov     rax, [rcx]
0x1800042dc  mov     rax, [rax+rdx*8]
0x1800042e0  test    rax, rax
0x1800042e3  jz      short loc_180004300
0x1800042e5  mov     edx, [r11]
0x1800042e8  xor     ecx, ecx
0x1800042ea  cmp     [rax+48h], edx
0x1800042ed  jnz     short loc_1800042F4
0x1800042ef  cmp     [rax], r10d
0x1800042f2  jz      short loc_180004303
0x1800042f4  mov     rcx, rax
0x1800042f7  mov     rax, [rax+40h]
0x1800042fb  test    rax, rax
0x1800042fe  jnz     short loc_1800042EA
0x180004300  xor     eax, eax
0x180004302  retn
0x180004303  mov     [r9], rcx
0x180004306  retn
```
