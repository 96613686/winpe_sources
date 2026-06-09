# ATL::CAtlComModule::CAtlComModule(void)

- ea: `0x180007eb0`
- end: `0x180007f2d`
- name: `??0CAtlComModule@ATL@@QEAA@XZ`
- size: `125`
- prototype: `int *__fastcall(ATL::CAtlComModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e90`

## callees

- `0x180006230`
- `0x180007eb0`

## pseudocode

```c
int *__fastcall ATL::CAtlComModule::CAtlComModule(ATL::CAtlComModule *this)
{
  *(&CriticalSection + 4) = 0;
  ATL::_AtlComModule = 0;
  qword_180026AC8 = (__int64)&_ImageBase;
  qword_180026AD0 = (__int64)_pobjMap_CIdentityStore;
  qword_180026AD8 = (__int64)&_pobjMapEntryLast;
  CriticalSection = 0;
  *(&CriticalSection + 1) = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection) < 0 )
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  else
    ATL::_AtlComModule = 72;
  return &ATL::_AtlComModule;
}

```

## disassembly

```asm
0x180007eb0  sub     rsp, 28h
0x180007eb4  xor     eax, eax
0x180007eb6  lea     rcx, CriticalSection; this
0x180007ebd  mov     cs:CriticalSection.SpinCount, rax
0x180007ec4  xorps   xmm0, xmm0
0x180007ec7  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, eax; ATL::CAtlComModule ATL::_AtlComModule
0x180007ecd  lea     rax, __ImageBase
0x180007ed4  mov     cs:qword_180026AC8, rax
0x180007edb  lea     rax, __pobjMap_CIdentityStore
0x180007ee2  mov     cs:qword_180026AD0, rax
0x180007ee9  lea     rax, __pobjMapEntryLast
0x180007ef0  mov     cs:qword_180026AD8, rax
0x180007ef7  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x180007efe  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180007f05  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007f0a  test    eax, eax
0x180007f0c  js      short loc_180007F24
0x180007f0e  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x180007f18  lea     rax, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180007f1f  add     rsp, 28h
0x180007f23  retn
0x180007f24  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x180007f2b  jmp     short loc_180007F18
```
