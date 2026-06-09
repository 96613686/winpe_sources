# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::CNode *)

- ea: `0x18000408c`
- end: `0x18000411f`
- name: `?FreeNode@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000387c`
- `0x180005d14`
- `0x18000613c`

## callees

- `0x180002420`
- `0x180002d8c`
- `0x18000408c`
- `0x180005104`
- `0x180005874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040f7`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v4; // rdx
  unsigned int v5; // eax
  bool v6; // r8
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx

  if ( !a2 )
    ATL::BaseAtlThrow((BasePrivate *)0x80004005LL, 0);
  ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::~CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>(a2 + 16);
  *(_QWORD *)(a2 + 64) = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = a2;
  v4 = --*(_QWORD *)(a1 + 8);
  if ( v4 < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           v4);
    ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::Rehash(
      a1,
      v5,
      v6);
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 64) = 0;
    v7 = *(_QWORD **)(a1 + 56);
    if ( v7 )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        free(v7);
        v7 = v8;
      }
      while ( v8 );
      *(_QWORD *)(a1 + 56) = 0;
    }
  }
}

```

## disassembly

```asm
0x18000408c  mov     [rsp+arg_0], rbx
0x180004091  push    rdi
0x180004092  sub     rsp, 20h
0x180004096  mov     rbx, rdx
0x180004099  mov     rdi, rcx
0x18000409c  test    rdx, rdx
0x18000409f  jz      short loc_180004114
0x1800040a1  lea     rcx, [rdx+10h]
0x1800040a5  call    ??1?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA@XZ; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::~CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>(void)
0x1800040aa  mov     rax, [rdi+40h]
0x1800040ae  mov     [rbx+40h], rax
0x1800040b2  mov     [rdi+40h], rbx
0x1800040b6  dec     qword ptr [rdi+8]
0x1800040ba  mov     rdx, [rdi+8]
0x1800040be  cmp     rdx, [rdi+28h]
0x1800040c2  jnb     short loc_1800040DC
0x1800040c4  cmp     dword ptr [rdi+30h], 0
0x1800040c8  jnz     short loc_1800040DC
0x1800040ca  mov     rcx, rdi
0x1800040cd  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x1800040d2  mov     edx, eax
0x1800040d4  mov     rcx, rdi
0x1800040d7  call    ?Rehash@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAAXI@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::Rehash(uint)
0x1800040dc  cmp     qword ptr [rdi+8], 0
0x1800040e1  jnz     short loc_180004109
0x1800040e3  mov     qword ptr [rdi+40h], 0
0x1800040eb  mov     rcx, [rdi+38h]; Block
0x1800040ef  test    rcx, rcx
0x1800040f2  jz      short loc_180004109
0x1800040f4  mov     rbx, [rcx]
0x1800040f7  call    cs:__imp_free
0x1800040fd  mov     rcx, rbx
0x180004100  test    rbx, rbx
0x180004103  jnz     short loc_1800040F4
0x180004105  mov     [rdi+38h], rbx
0x180004109  mov     rbx, [rsp+28h+arg_0]
0x18000410e  add     rsp, 20h
0x180004112  pop     rdi
0x180004113  retn
0x180004114  mov     ecx, 80004005h; int
0x180004119  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
