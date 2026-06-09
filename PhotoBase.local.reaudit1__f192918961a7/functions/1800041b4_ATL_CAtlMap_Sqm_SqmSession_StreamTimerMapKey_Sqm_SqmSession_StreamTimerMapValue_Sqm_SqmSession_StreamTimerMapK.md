# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::FreeNode(ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::CNode *)

- ea: `0x1800041b4`
- end: `0x180004247`
- name: `?FreeNode@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005e94`
- `0x180006b20`

## callees

- `0x180002420`
- `0x180002d00`
- `0x1800041b4`
- `0x180005104`
- `0x180005ad4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000421f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000421f`

## pseudocode

```c
void __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::FreeNode(
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
  ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::~CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>(a2 + 40);
  *(_QWORD *)(a2 + 72) = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a1 + 64) = a2;
  v4 = --*(_QWORD *)(a1 + 8);
  if ( v4 < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           v4);
    ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::Rehash(
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
0x1800041b4  mov     [rsp+arg_0], rbx
0x1800041b9  push    rdi
0x1800041ba  sub     rsp, 20h
0x1800041be  mov     rbx, rdx
0x1800041c1  mov     rdi, rcx
0x1800041c4  test    rdx, rdx
0x1800041c7  jz      short loc_18000423C
0x1800041c9  lea     rcx, [rdx+28h]
0x1800041cd  call    ??1?$CAtlArray@UStreamEntryWithOwnedData@SqmSession@Sqm@@V?$CElementTraits@UStreamEntryWithOwnedData@SqmSession@Sqm@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::~CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>(void)
0x1800041d2  mov     rax, [rdi+40h]
0x1800041d6  mov     [rbx+48h], rax
0x1800041da  mov     [rdi+40h], rbx
0x1800041de  dec     qword ptr [rdi+8]
0x1800041e2  mov     rdx, [rdi+8]
0x1800041e6  cmp     rdx, [rdi+28h]
0x1800041ea  jnb     short loc_180004204
0x1800041ec  cmp     dword ptr [rdi+30h], 0
0x1800041f0  jnz     short loc_180004204
0x1800041f2  mov     rcx, rdi
0x1800041f5  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x1800041fa  mov     edx, eax
0x1800041fc  mov     rcx, rdi
0x1800041ff  call    ?Rehash@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@QEAAXI@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::Rehash(uint)
0x180004204  cmp     qword ptr [rdi+8], 0
0x180004209  jnz     short loc_180004231
0x18000420b  mov     qword ptr [rdi+40h], 0
0x180004213  mov     rcx, [rdi+38h]; Block
0x180004217  test    rcx, rcx
0x18000421a  jz      short loc_180004231
0x18000421c  mov     rbx, [rcx]
0x18000421f  call    cs:__imp_free
0x180004225  mov     rcx, rbx
0x180004228  test    rbx, rbx
0x18000422b  jnz     short loc_18000421C
0x18000422d  mov     [rdi+38h], rbx
0x180004231  mov     rbx, [rsp+28h+arg_0]
0x180004236  add     rsp, 20h
0x18000423a  pop     rdi
0x18000423b  retn
0x18000423c  mov     ecx, 80004005h; int
0x180004241  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
