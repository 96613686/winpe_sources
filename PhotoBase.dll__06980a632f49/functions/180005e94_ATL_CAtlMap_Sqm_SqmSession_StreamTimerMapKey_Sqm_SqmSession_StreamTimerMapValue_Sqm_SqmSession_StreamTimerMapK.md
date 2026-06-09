# ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::RemoveAll(void)

- ea: `0x180005e94`
- end: `0x180005f4d`
- name: `?RemoveAll@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@QEAAXXZ`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d74`
- `0x180002df0`
- `0x180003cd0`

## callees

- `0x1800041b4`
- `0x180004554`
- `0x180005104`
- `0x180005e94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ee2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005f28`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ee2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005f28`

## pseudocode

```c
void __fastcall ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 72);
        ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::FreeNode(
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
0x180005e94  mov     [rsp+arg_0], rbx
0x180005e99  mov     [rsp+arg_8], rsi
0x180005e9e  push    rdi
0x180005e9f  sub     rsp, 20h
0x180005ea3  mov     rdi, rcx
0x180005ea6  inc     dword ptr [rcx+30h]
0x180005ea9  cmp     qword ptr [rcx], 0
0x180005ead  jz      short loc_180005EDA
0x180005eaf  xor     ebx, ebx
0x180005eb1  cmp     [rcx+10h], ebx
0x180005eb4  jbe     short loc_180005EDA
0x180005eb6  mov     rax, [rdi]
0x180005eb9  mov     rsi, [rax+rbx*8]
0x180005ebd  jmp     short loc_180005ECE
0x180005ebf  mov     rdx, rsi
0x180005ec2  mov     rsi, [rsi+48h]
0x180005ec6  mov     rcx, rdi
0x180005ec9  call    ?FreeNode@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::FreeNode(ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::CNode *)
0x180005ece  test    rsi, rsi
0x180005ed1  jnz     short loc_180005EBF
0x180005ed3  inc     ebx
0x180005ed5  cmp     ebx, [rdi+10h]
0x180005ed8  jb      short loc_180005EB6
0x180005eda  mov     rcx, [rdi]; Block
0x180005edd  test    rcx, rcx
0x180005ee0  jz      short loc_180005EE8
0x180005ee2  call    cs:__imp_free
0x180005ee8  mov     qword ptr [rdi], 0
0x180005eef  mov     qword ptr [rdi+8], 0
0x180005ef7  cmp     dword ptr [rdi+30h], 0
0x180005efb  jnz     short loc_180005F14
0x180005efd  xor     edx, edx
0x180005eff  mov     rcx, rdi
0x180005f02  call    ?PickSize@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::PickSize(unsigned __int64)
0x180005f07  mov     edx, eax
0x180005f09  xor     r8d, r8d
0x180005f0c  mov     rcx, rdi
0x180005f0f  call    ?InitHashTable@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::InitHashTable(uint,bool)
0x180005f14  mov     qword ptr [rdi+40h], 0
0x180005f1c  mov     rcx, [rdi+38h]; Block
0x180005f20  test    rcx, rcx
0x180005f23  jz      short loc_180005F3A
0x180005f25  mov     rbx, [rcx]
0x180005f28  call    cs:__imp_free
0x180005f2e  mov     rcx, rbx
0x180005f31  test    rbx, rbx
0x180005f34  jnz     short loc_180005F25
0x180005f36  mov     [rdi+38h], rbx
0x180005f3a  dec     dword ptr [rdi+30h]
0x180005f3d  mov     rbx, [rsp+28h+arg_0]
0x180005f42  mov     rsi, [rsp+28h+arg_8]
0x180005f47  add     rsp, 20h
0x180005f4b  pop     rdi
0x180005f4c  retn
```
