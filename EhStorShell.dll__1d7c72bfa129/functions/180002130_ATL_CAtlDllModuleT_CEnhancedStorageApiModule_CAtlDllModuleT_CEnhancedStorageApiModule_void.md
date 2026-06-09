# ATL::CAtlDllModuleT<CEnhancedStorageApiModule>::CAtlDllModuleT<CEnhancedStorageApiModule>(void)

- ea: `0x180002130`
- end: `0x1800021b5`
- name: `??0?$CAtlDllModuleT@VCEnhancedStorageApiModule@@@ATL@@QEAA@XZ`
- size: `133`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002100`

## callees

- `0x180002130`
- `0x1800022d8`
- `0x180002320`

## pseudocode

```c
__int64 *ATL::CAtlDllModuleT<CEnhancedStorageApiModule>::CAtlDllModuleT<CEnhancedStorageApiModule>()
{
  ATL::CAtlComModule *v0; // rcx

  CriticalSection = 0;
  *(&CriticalSection + 1) = 0;
  *(&CriticalSection + 4) = 0;
  qword_180012898 = 0;
  qword_1800128A0 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_1800128D0 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection) >= 0 )
    qword_180012898 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_EnhancedStorageShellLib;
  ATL::CAtlComModule::ExecuteObjectMain(v0, 1);
  return &_AtlModule;
}

```

## disassembly

```asm
0x180002130  push    rdi
0x180002132  sub     rsp, 20h
0x180002136  xorps   xmm0, xmm0
0x180002139  xor     eax, eax
0x18000213b  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x180002142  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180002149  mov     cs:CriticalSection.SpinCount, rax
0x180002150  mov     cs:qword_180012898, rax
0x180002157  mov     cs:qword_1800128A0, rax
0x18000215e  lea     rdi, ?_AtlModule@@3VCEnhancedStorageApiModule@@A; CEnhancedStorageApiModule _AtlModule
0x180002165  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x18000216c  mov     cs:qword_1800128D0, rax
0x180002173  lea     rcx, CriticalSection; this
0x18000217a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000217f  test    eax, eax
0x180002181  jns     short loc_1800021A9
0x180002183  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000218a  movups  xmm0, xmmword ptr cs:LIBID_EnhancedStorageShellLib.Data1
0x180002191  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x180002199  mov     dl, 1; bool
0x18000219b  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x1800021a0  mov     rax, rdi
0x1800021a3  add     rsp, 20h
0x1800021a7  pop     rdi
0x1800021a8  retn
0x1800021a9  mov     dword ptr cs:qword_180012898, 38h ; '8'
0x1800021b3  jmp     short loc_18000218A
```
