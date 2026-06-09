# Sqm::SqmSession::~SqmSession(void)

- ea: `0x180002df0`
- end: `0x180002e68`
- name: `??1SqmSession@Sqm@@AEAA@XZ`
- size: `120`
- prototype: `void __fastcall(Sqm::SqmSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007a90`

## callees

- `0x180002d8c`
- `0x180002df0`
- `0x180003cd0`
- `0x180005c54`
- `0x180005d14`
- `0x180005dd4`
- `0x180005e94`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002e23`
- `KERNEL32!DeleteCriticalSection` at `0x180002e23`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Sqm::SqmSession::~SqmSession(Sqm::SqmSession *this)
{
  Sqm::SqmSession *v1; // rbx

  try
  {
    v1 = this;
    if ( *((_BYTE *)this + 144) && *((_BYTE *)this + 145) )
      Sqm::SqmSession::EndSession(this);
  }
  catch ( ... )
  {
    v1 = this;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 344));
  ATL::CAtlMap<unsigned long,Sqm::SqmSession::AverageItem,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAll((char *)v1 + 272);
  ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::~CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>((char *)v1 + 224);
  ATL::CAtlMap<unsigned long,Sqm::SqmSession::SMedianData,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAll((char *)v1 + 152);
  ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::RemoveAll((char *)v1 + 72);
  ATL::CAtlMap<unsigned long,Base::Stopwatch,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<Base::Stopwatch>>::RemoveAll(v1);
}

```

## disassembly

```asm
0x180002df0  mov     [rsp+arg_0], rcx
0x180002df5  push    rbx
0x180002df6  sub     rsp, 20h
0x180002dfa  mov     rbx, rcx
0x180002dfd  cmp     byte ptr [rcx+90h], 0
0x180002e04  jz      short loc_180002E15
0x180002e06  cmp     byte ptr [rcx+91h], 0
0x180002e0d  jz      short loc_180002E15
0x180002e0f  call    ?EndSession@SqmSession@Sqm@@AEAAXXZ; Sqm::SqmSession::EndSession(void)
0x180002e14  nop
0x180002e15  jmp     short loc_180002E1C
0x180002e17  mov     rbx, [rsp+28h+arg_0]
0x180002e1c  lea     rcx, [rbx+158h]; lpCriticalSection
0x180002e23  call    cs:__imp_DeleteCriticalSection
0x180002e29  nop
0x180002e2a  lea     rcx, [rbx+110h]
0x180002e31  call    ?RemoveAll@?$CAtlMap@KUAverageItem@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UAverageItem@SqmSession@Sqm@@@5@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,Sqm::SqmSession::AverageItem,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::AverageItem>>::RemoveAll(void)
0x180002e36  nop
0x180002e37  lea     rcx, [rbx+0E0h]
0x180002e3e  call    ??1?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA@XZ; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::~CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>(void)
0x180002e43  nop
0x180002e44  lea     rcx, [rbx+98h]
0x180002e4b  call    ?RemoveAll@?$CAtlMap@KUSMedianData@SqmSession@Sqm@@V?$CElementTraits@K@ATL@@V?$CElementTraits@USMedianData@SqmSession@Sqm@@@5@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,Sqm::SqmSession::SMedianData,ATL::CElementTraits<ulong>,ATL::CElementTraits<Sqm::SqmSession::SMedianData>>::RemoveAll(void)
0x180002e50  nop
0x180002e51  lea     rcx, [rbx+48h]
0x180002e55  call    ?RemoveAll@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::RemoveAll(void)
0x180002e5a  nop
0x180002e5b  mov     rcx, rbx
0x180002e5e  add     rsp, 20h
0x180002e62  pop     rbx
0x180002e63  jmp     ?RemoveAll@?$CAtlMap@KVStopwatch@Base@@V?$CElementTraits@K@ATL@@V?$CElementTraits@VStopwatch@Base@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,Base::Stopwatch,ATL::CElementTraits<ulong>,ATL::CElementTraits<Base::Stopwatch>>::RemoveAll(void)
```
