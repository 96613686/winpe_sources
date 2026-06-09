# ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::GetNode(ulong,uint &,uint &,ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::CNode * &)

- ea: `0x180004250`
- end: `0x1800042a7`
- name: `?GetNode@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@AEBAPEAVCNode@12@KAEAI0AEAPEAV312@@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003420`
- `0x1800036c4`
- `0x1800062bc`

## callees

- `0x180004250`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::GetNode(
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
  while ( *(_DWORD *)(result + 32) != *a4 || *(_DWORD *)result != a2 )
  {
    v6 = result;
    result = *(_QWORD *)(result + 24);
    if ( !result )
      return 0;
  }
  *a5 = v6;
  return result;
}

```

## disassembly

```asm
0x180004250  mov     [r9], edx
0x180004253  mov     r10d, edx
0x180004256  xor     edx, edx
0x180004258  mov     eax, r10d
0x18000425b  div     dword ptr [rcx+10h]
0x18000425e  mov     r11, r9
0x180004261  mov     [r8], edx
0x180004264  cmp     qword ptr [rcx], 0
0x180004268  jz      short loc_1800042A0
0x18000426a  mov     r9, [rsp+arg_20]
0x18000426f  mov     qword ptr [r9], 0
0x180004276  mov     edx, [r8]
0x180004279  mov     rax, [rcx]
0x18000427c  mov     rax, [rax+rdx*8]
0x180004280  test    rax, rax
0x180004283  jz      short loc_1800042A0
0x180004285  mov     edx, [r11]
0x180004288  xor     ecx, ecx
0x18000428a  cmp     [rax+20h], edx
0x18000428d  jnz     short loc_180004294
0x18000428f  cmp     [rax], r10d
0x180004292  jz      short loc_1800042A3
0x180004294  mov     rcx, rax
0x180004297  mov     rax, [rax+18h]
0x18000429b  test    rax, rax
0x18000429e  jnz     short loc_18000428A
0x1800042a0  xor     eax, eax
0x1800042a2  retn
0x1800042a3  mov     [r9], rcx
0x1800042a6  retn
```
