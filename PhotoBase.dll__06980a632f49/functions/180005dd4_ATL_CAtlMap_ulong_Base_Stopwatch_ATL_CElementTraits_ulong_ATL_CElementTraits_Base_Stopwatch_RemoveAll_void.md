# ATL::CAtlMap<ulong,Base::Stopwatch,ATL::CElementTraits<ulong>,ATL::CElementTraits<Base::Stopwatch>>::RemoveAll(void)

- ea: `0x180005dd4`
- end: `0x180005e8d`
- name: `?RemoveAll@?$CAtlMap@KVStopwatch@Base@@V?$CElementTraits@K@ATL@@V?$CElementTraits@VStopwatch@Base@@@4@@ATL@@QEAAXXZ`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d68`
- `0x180002df0`
- `0x180003cd0`

## callees

- `0x180004128`
- `0x180004554`
- `0x180005104`
- `0x180005dd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005e22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005e68`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005e22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005e68`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Base::Stopwatch,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Base::Stopwatch>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rbx
  __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = *(_QWORD *)(v3 + 40);
        ATL::CAtlMap<unsigned long,Base::Stopwatch,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Base::Stopwatch>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  if ( *(_QWORD *)a1 )
    free(*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(
      a1,
      v5,
      0);
  }
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
  --*(_DWORD *)(a1 + 48);
}

```

## disassembly

```asm
0x180005dd4  mov     [rsp+arg_0], rbx
0x180005dd9  mov     [rsp+arg_8], rsi
0x180005dde  push    rdi
0x180005ddf  sub     rsp, 20h
0x180005de3  mov     rdi, rcx
0x180005de6  inc     dword ptr [rcx+30h]
0x180005de9  cmp     qword ptr [rcx], 0
0x180005ded  jz      short loc_180005E1A
0x180005def  xor     ebx, ebx
0x180005df1  cmp     [rcx+10h], ebx
0x180005df4  jbe     short loc_180005E1A
0x180005df6  mov     rax, [rdi]
0x180005df9  mov     rsi, [rax+rbx*8]
0x180005dfd  jmp     short loc_180005E0E
0x180005dff  mov     rdx, rsi
0x180005e02  mov     rsi, [rsi+28h]
0x180005e06  mov     rcx, rdi
0x180005e09  call    ?FreeNode@?$CAtlMap@KVStopwatch@Base@@V?$CElementTraits@K@ATL@@V?$CElementTraits@VStopwatch@Base@@@4@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,Base::Stopwatch,ATL::CElementTraits<ulong>,ATL::CElementTraits<Base::Stopwatch>>::FreeNode(ATL::CAtlMap<ulong,Base::Stopwatch,ATL::CElementTraits<ulong>,ATL::CElementTraits<Base::Stopwatch>>::CNode *)
0x180005e0e  test    rsi, rsi
0x180005e11  jnz     short loc_180005DFF
0x180005e13  inc     ebx
0x180005e15  cmp     ebx, [rdi+10h]
0x180005e18  jb      short loc_180005DF6
0x180005e1a  mov     rcx, [rdi]; Block
0x180005e1d  test    rcx, rcx
0x180005e20  jz      short loc_180005E28
0x180005e22  call    cs:__imp_free
0x180005e28  mov     qword ptr [rdi], 0
0x180005e2f  mov     qword ptr [rdi+8], 0
0x180005e37  cmp     dword ptr [rdi+30h], 0
0x180005e3b  jnz     short loc_180005E54
0x180005e3d  xor     edx, edx
0x180005e3f  mov     rcx, rdi
0x180005e42  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180005e47  mov     edx, eax
0x180005e49  xor     r8d, r8d
0x180005e4c  mov     rcx, rdi
0x180005e4f  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x180005e54  mov     qword ptr [rdi+40h], 0
0x180005e5c  mov     rcx, [rdi+38h]; Block
0x180005e60  test    rcx, rcx
0x180005e63  jz      short loc_180005E7A
0x180005e65  mov     rbx, [rcx]
0x180005e68  call    cs:__imp_free
0x180005e6e  mov     rcx, rbx
0x180005e71  test    rbx, rbx
0x180005e74  jnz     short loc_180005E65
0x180005e76  mov     [rdi+38h], rbx
0x180005e7a  dec     dword ptr [rdi+30h]
0x180005e7d  mov     rbx, [rsp+28h+arg_0]
0x180005e82  mov     rsi, [rsp+28h+arg_8]
0x180005e87  add     rsp, 20h
0x180005e8b  pop     rdi
0x180005e8c  retn
```
