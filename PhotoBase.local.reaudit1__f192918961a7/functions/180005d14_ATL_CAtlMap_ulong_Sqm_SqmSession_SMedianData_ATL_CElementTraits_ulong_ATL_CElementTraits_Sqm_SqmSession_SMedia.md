# ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAll(void)

- ea: `0x180005d14`
- end: `0x180005dcd`
- name: `?RemoveAll@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAAXXZ`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d5c`
- `0x180002df0`
- `0x180003cd0`

## callees

- `0x18000408c`
- `0x180004554`
- `0x180005104`
- `0x180005d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005d62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005da8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005d62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005da8`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 64);
        ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(
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
0x180005d14  mov     [rsp+arg_0], rbx
0x180005d19  mov     [rsp+arg_8], rsi
0x180005d1e  push    rdi
0x180005d1f  sub     rsp, 20h
0x180005d23  mov     rdi, rcx
0x180005d26  inc     dword ptr [rcx+30h]
0x180005d29  cmp     qword ptr [rcx], 0
0x180005d2d  jz      short loc_180005D5A
0x180005d2f  xor     ebx, ebx
0x180005d31  cmp     [rcx+10h], ebx
0x180005d34  jbe     short loc_180005D5A
0x180005d36  mov     rax, [rdi]
0x180005d39  mov     rsi, [rax+rbx*8]
0x180005d3d  jmp     short loc_180005D4E
0x180005d3f  mov     rdx, rsi
0x180005d42  mov     rsi, [rsi+40h]
0x180005d46  mov     rcx, rdi
0x180005d49  call    ?FreeNode@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::CNode *)
0x180005d4e  test    rsi, rsi
0x180005d51  jnz     short loc_180005D3F
0x180005d53  inc     ebx
0x180005d55  cmp     ebx, [rdi+10h]
0x180005d58  jb      short loc_180005D36
0x180005d5a  mov     rcx, [rdi]; Block
0x180005d5d  test    rcx, rcx
0x180005d60  jz      short loc_180005D68
0x180005d62  call    cs:__imp_free
0x180005d68  mov     qword ptr [rdi], 0
0x180005d6f  mov     qword ptr [rdi+8], 0
0x180005d77  cmp     dword ptr [rdi+30h], 0
0x180005d7b  jnz     short loc_180005D94
0x180005d7d  xor     edx, edx
0x180005d7f  mov     rcx, rdi
0x180005d82  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180005d87  mov     edx, eax
0x180005d89  xor     r8d, r8d
0x180005d8c  mov     rcx, rdi
0x180005d8f  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x180005d94  mov     qword ptr [rdi+40h], 0
0x180005d9c  mov     rcx, [rdi+38h]; Block
0x180005da0  test    rcx, rcx
0x180005da3  jz      short loc_180005DBA
0x180005da5  mov     rbx, [rcx]
0x180005da8  call    cs:__imp_free
0x180005dae  mov     rcx, rbx
0x180005db1  test    rbx, rbx
0x180005db4  jnz     short loc_180005DA5
0x180005db6  mov     [rdi+38h], rbx
0x180005dba  dec     dword ptr [rdi+30h]
0x180005dbd  mov     rbx, [rsp+28h+arg_0]
0x180005dc2  mov     rsi, [rsp+28h+arg_8]
0x180005dc7  add     rsp, 20h
0x180005dcb  pop     rdi
0x180005dcc  retn
```
