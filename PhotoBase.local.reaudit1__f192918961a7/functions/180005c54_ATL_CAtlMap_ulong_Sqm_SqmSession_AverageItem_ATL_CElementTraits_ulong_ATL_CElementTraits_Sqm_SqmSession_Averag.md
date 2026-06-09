# ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAll(void)

- ea: `0x180005c54`
- end: `0x180005d0d`
- name: `?RemoveAll@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@QEAAXXZ`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d50`
- `0x180002df0`
- `0x180003cd0`

## callees

- `0x180004000`
- `0x180004554`
- `0x180005104`
- `0x180005c54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ca2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ce8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ca2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ce8`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 24);
        ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(
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
0x180005c54  mov     [rsp+arg_0], rbx
0x180005c59  mov     [rsp+arg_8], rsi
0x180005c5e  push    rdi
0x180005c5f  sub     rsp, 20h
0x180005c63  mov     rdi, rcx
0x180005c66  inc     dword ptr [rcx+30h]
0x180005c69  cmp     qword ptr [rcx], 0
0x180005c6d  jz      short loc_180005C9A
0x180005c6f  xor     ebx, ebx
0x180005c71  cmp     [rcx+10h], ebx
0x180005c74  jbe     short loc_180005C9A
0x180005c76  mov     rax, [rdi]
0x180005c79  mov     rsi, [rax+rbx*8]
0x180005c7d  jmp     short loc_180005C8E
0x180005c7f  mov     rdx, rsi
0x180005c82  mov     rsi, [rsi+18h]
0x180005c86  mov     rcx, rdi
0x180005c89  call    ?FreeNode@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::FreeNode(ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::CNode *)
0x180005c8e  test    rsi, rsi
0x180005c91  jnz     short loc_180005C7F
0x180005c93  inc     ebx
0x180005c95  cmp     ebx, [rdi+10h]
0x180005c98  jb      short loc_180005C76
0x180005c9a  mov     rcx, [rdi]; Block
0x180005c9d  test    rcx, rcx
0x180005ca0  jz      short loc_180005CA8
0x180005ca2  call    cs:__imp_free
0x180005ca8  mov     qword ptr [rdi], 0
0x180005caf  mov     qword ptr [rdi+8], 0
0x180005cb7  cmp     dword ptr [rdi+30h], 0
0x180005cbb  jnz     short loc_180005CD4
0x180005cbd  xor     edx, edx
0x180005cbf  mov     rcx, rdi
0x180005cc2  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180005cc7  mov     edx, eax
0x180005cc9  xor     r8d, r8d
0x180005ccc  mov     rcx, rdi
0x180005ccf  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x180005cd4  mov     qword ptr [rdi+40h], 0
0x180005cdc  mov     rcx, [rdi+38h]; Block
0x180005ce0  test    rcx, rcx
0x180005ce3  jz      short loc_180005CFA
0x180005ce5  mov     rbx, [rcx]
0x180005ce8  call    cs:__imp_free
0x180005cee  mov     rcx, rbx
0x180005cf1  test    rbx, rbx
0x180005cf4  jnz     short loc_180005CE5
0x180005cf6  mov     [rdi+38h], rbx
0x180005cfa  dec     dword ptr [rdi+30h]
0x180005cfd  mov     rbx, [rsp+28h+arg_0]
0x180005d02  mov     rsi, [rsp+28h+arg_8]
0x180005d07  add     rsp, 20h
0x180005d0b  pop     rdi
0x180005d0c  retn
```
