# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAtPos(__POSITION *)

- ea: `0x18000613c`
- end: `0x1800061a0`
- name: `?RemoveAtPos@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000792c`

## callees

- `0x180002420`
- `0x18000408c`
- `0x18000613c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAtPos(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467259);
  v4 = (unsigned int)(*(_DWORD *)(a2 + 72) % *((_DWORD *)a1 + 4));
  v5 = *a1;
  v6 = *(_QWORD *)(*a1 + 8 * v4);
  if ( a2 == v6 )
  {
    v6 = 0;
  }
  else
  {
    while ( *(_QWORD *)(v6 + 64) != a2 )
      v6 = *(_QWORD *)(v6 + 64);
  }
  v7 = *(_QWORD *)(a2 + 64);
  if ( v6 )
    *(_QWORD *)(v6 + 64) = v7;
  else
    *(_QWORD *)(v5 + 8 * v4) = v7;
  return ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(
           a1,
           a2);
}

```

## disassembly

```asm
0x18000613c  sub     rsp, 28h
0x180006140  mov     r8, rdx
0x180006143  mov     r9, rcx
0x180006146  test    rdx, rdx
0x180006149  jz      short loc_180006195
0x18000614b  xor     edx, edx
0x18000614d  mov     eax, [r8+48h]
0x180006151  div     dword ptr [rcx+10h]
0x180006154  mov     r10d, edx
0x180006157  mov     rdx, [rcx]
0x18000615a  mov     rax, [rdx+r10*8]
0x18000615e  cmp     r8, rax
0x180006161  jnz     short loc_18000616B
0x180006163  xor     eax, eax
0x180006165  jmp     short loc_180006171
0x180006167  mov     rax, [rax+40h]
0x18000616b  cmp     [rax+40h], r8
0x18000616f  jnz     short loc_180006167
0x180006171  mov     rcx, [r8+40h]
0x180006175  test    rax, rax
0x180006178  jnz     short loc_180006180
0x18000617a  mov     [rdx+r10*8], rcx
0x18000617e  jmp     short loc_180006184
0x180006180  mov     [rax+40h], rcx
0x180006184  mov     rdx, r8
0x180006187  mov     rcx, r9
0x18000618a  call    ?FreeNode@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::CNode *)
0x18000618f  nop
0x180006190  add     rsp, 28h
0x180006194  retn
0x180006195  mov     ecx, 80004005h; int
0x18000619a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
