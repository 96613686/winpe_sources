# ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::CNode *)

- ea: `0x180004000`
- end: `0x180004084`
- name: `?FreeNode@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800036c4`
- `0x180005c54`
- `0x1800060d0`

## callees

- `0x180002420`
- `0x180004000`
- `0x180005104`
- `0x180005744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000405c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000405c`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  unsigned int v4; // eax
  bool v5; // r8
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  if ( !a2 )
    ATL::BaseAtlThrow((BasePrivate *)0x80004005LL, 0);
  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = a2;
  v3 = --*(_QWORD *)(a1 + 8);
  if ( v3 < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
  {
    v4 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           v3);
    ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::Rehash(
      a1,
      v4,
      v5);
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 64) = 0;
    v6 = *(_QWORD **)(a1 + 56);
    if ( v6 )
    {
      do
      {
        v7 = (_QWORD *)*v6;
        free(v6);
        v6 = v7;
      }
      while ( v7 );
      *(_QWORD *)(a1 + 56) = 0;
    }
  }
}

```

## disassembly

```asm
0x180004000  mov     [rsp+arg_0], rbx
0x180004005  push    rdi
0x180004006  sub     rsp, 20h
0x18000400a  mov     rdi, rcx
0x18000400d  test    rdx, rdx
0x180004010  jz      short loc_180004079
0x180004012  mov     rax, [rcx+40h]
0x180004016  mov     [rdx+18h], rax
0x18000401a  mov     [rcx+40h], rdx
0x18000401e  dec     qword ptr [rcx+8]
0x180004022  mov     rdx, [rcx+8]
0x180004026  cmp     rdx, [rcx+28h]
0x18000402a  jnb     short loc_180004041
0x18000402c  cmp     dword ptr [rcx+30h], 0
0x180004030  jnz     short loc_180004041
0x180004032  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180004037  mov     edx, eax
0x180004039  mov     rcx, rdi
0x18000403c  call    ?Rehash@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@QEAAXI@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::Rehash(uint)
0x180004041  cmp     qword ptr [rdi+8], 0
0x180004046  jnz     short loc_18000406E
0x180004048  mov     qword ptr [rdi+40h], 0
0x180004050  mov     rcx, [rdi+38h]; Block
0x180004054  test    rcx, rcx
0x180004057  jz      short loc_18000406E
0x180004059  mov     rbx, [rcx]
0x18000405c  call    cs:__imp_free
0x180004062  mov     rcx, rbx
0x180004065  test    rbx, rbx
0x180004068  jnz     short loc_180004059
0x18000406a  mov     [rdi+38h], rbx
0x18000406e  mov     rbx, [rsp+28h+arg_0]
0x180004073  add     rsp, 20h
0x180004077  pop     rdi
0x180004078  retn
0x180004079  mov     ecx, 80004005h; int
0x18000407e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
