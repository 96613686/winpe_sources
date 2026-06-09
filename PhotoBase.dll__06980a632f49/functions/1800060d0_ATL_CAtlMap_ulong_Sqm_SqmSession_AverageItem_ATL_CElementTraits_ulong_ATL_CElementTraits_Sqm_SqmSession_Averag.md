# ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAtPos(__POSITION *)

- ea: `0x1800060d0`
- end: `0x180006134`
- name: `?RemoveAtPos@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007902`

## callees

- `0x180002420`
- `0x180004000`
- `0x1800060d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAtPos(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467259);
  v4 = (unsigned int)(*(_DWORD *)(a2 + 32) % *((_DWORD *)a1 + 4));
  v5 = *a1;
  v6 = *(_QWORD *)(*a1 + 8 * v4);
  if ( a2 == v6 )
  {
    v6 = 0;
  }
  else
  {
    while ( *(_QWORD *)(v6 + 24) != a2 )
      v6 = *(_QWORD *)(v6 + 24);
  }
  v7 = *(_QWORD *)(a2 + 24);
  if ( v6 )
    *(_QWORD *)(v6 + 24) = v7;
  else
    *(_QWORD *)(v5 + 8 * v4) = v7;
  return ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(
           a1,
           a2);
}

```

## disassembly

```asm
0x1800060d0  sub     rsp, 28h
0x1800060d4  mov     r8, rdx
0x1800060d7  mov     r9, rcx
0x1800060da  test    rdx, rdx
0x1800060dd  jz      short loc_180006129
0x1800060df  xor     edx, edx
0x1800060e1  mov     eax, [r8+20h]
0x1800060e5  div     dword ptr [rcx+10h]
0x1800060e8  mov     r10d, edx
0x1800060eb  mov     rdx, [rcx]
0x1800060ee  mov     rax, [rdx+r10*8]
0x1800060f2  cmp     r8, rax
0x1800060f5  jnz     short loc_1800060FF
0x1800060f7  xor     eax, eax
0x1800060f9  jmp     short loc_180006105
0x1800060fb  mov     rax, [rax+18h]
0x1800060ff  cmp     [rax+18h], r8
0x180006103  jnz     short loc_1800060FB
0x180006105  mov     rcx, [r8+18h]
0x180006109  test    rax, rax
0x18000610c  jnz     short loc_180006114
0x18000610e  mov     [rdx+r10*8], rcx
0x180006112  jmp     short loc_180006118
0x180006114  mov     [rax+18h], rcx
0x180006118  mov     rdx, r8
0x18000611b  mov     rcx, r9
0x18000611e  call    ?FreeNode@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::CNode *)
0x180006123  nop
0x180006124  add     rsp, 28h
0x180006128  retn
0x180006129  mov     ecx, 80004005h; int
0x18000612e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
