# ATL::CAtlComModule::CAtlComModule(void)

- ea: `0x180001e20`
- end: `0x180001e9d`
- name: `??0CAtlComModule@ATL@@QEAA@XZ`
- size: `125`
- prototype: `int *__fastcall(ATL::CAtlComModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e00`

## callees

- `0x180001e20`
- `0x1800022d8`

## pseudocode

```c
int *__fastcall ATL::CAtlComModule::CAtlComModule(ATL::CAtlComModule *this)
{
  *(&stru_180012960 + 4) = 0;
  ATL::_AtlComModule = 0;
  qword_180012948 = 0x180000000uLL;
  qword_180012950 = (__int64)_pobjMap_CAutoplayHandler;
  qword_180012958 = (__int64)&_pobjMapEntryLast;
  stru_180012960 = 0;
  *(&stru_180012960 + 1) = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&stru_180012960) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return &ATL::_AtlComModule;
}

```

## disassembly

```asm
0x180001e20  sub     rsp, 28h
0x180001e24  xor     eax, eax
0x180001e26  lea     rcx, stru_180012960; this
0x180001e2d  mov     cs:stru_180012960.SpinCount, rax
0x180001e34  xorps   xmm0, xmm0
0x180001e37  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, eax; ATL::CAtlComModule ATL::_AtlComModule
0x180001e3d  lea     rax, cs:180000000h
0x180001e44  mov     cs:qword_180012948, rax
0x180001e4b  lea     rax, __pobjMap_CAutoplayHandler
0x180001e52  mov     cs:qword_180012950, rax
0x180001e59  lea     rax, __pobjMapEntryLast
0x180001e60  mov     cs:qword_180012958, rax
0x180001e67  movups  xmmword ptr cs:stru_180012960.DebugInfo, xmm0
0x180001e6e  movups  xmmword ptr cs:stru_180012960.OwningThread, xmm0
0x180001e75  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001e7a  test    eax, eax
0x180001e7c  jns     short loc_180001E87
0x180001e7e  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180001e85  jmp     short loc_180001E91
0x180001e87  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180001e91  lea     rax, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180001e98  add     rsp, 28h
0x180001e9c  retn
```
