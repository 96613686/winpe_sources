# ATL::CAtlExeModuleT<CRAServerModule>::CAtlExeModuleT<CRAServerModule>(void)

- ea: `0x14000ca6c`
- end: `0x14000cb61`
- name: `??0?$CAtlExeModuleT@VCRAServerModule@@@ATL@@QEAA@XZ`
- size: `245`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011f0`

## callees

- `0x1400072dc`
- `0x14000ca6c`
- `0x14000d4e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000cae1`
- `KERNEL32!GetCurrentThreadId` at `0x14000cae1`
- `KERNEL32!GetModuleHandleW` at `0x14000cb36`
- `KERNEL32!GetModuleHandleW` at `0x14000cb36`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000cb1e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000cb1e`

## string_xrefs

- `0x14000cb2f`: `Mscoree.dll`

## pseudocode

```c
__int64 *ATL::CAtlExeModuleT<CRAServerModule>::CAtlExeModuleT<CRAServerModule>()
{
  HRESULT v0; // eax
  ATL::CAtlComModule *v1; // rcx

  xmmword_140021D98 = 0;
  xmmword_140021DA8 = 0;
  qword_140021DB8 = 0;
  qword_140021D88 = 0;
  qword_140021D90 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_140021DC0 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_140021D98) >= 0 )
    LODWORD(qword_140021D88) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_RAServerLib;
  dword_140021DC8 = GetCurrentThreadId();
  hEvent = 0;
  dword_140021DD8 = 5000;
  dwMilliseconds = 1000;
  byte_140021DE0 = 1;
  byte_140021DE2 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    byte_140021DE2 = 1;
LABEL_9:
    ATL::CAtlComModule::ExecuteObjectMain(v1, 1);
    return &_AtlModule;
  }
  if ( v0 == -2147417850 && GetModuleHandleW(L"Mscoree.dll") )
    goto LABEL_9;
  ATL::CAtlBaseModule::m_bInitFailed = 1;
  return &_AtlModule;
}

```

## disassembly

```asm
0x14000ca6c  push    rdi
0x14000ca6e  sub     rsp, 20h
0x14000ca72  xorps   xmm0, xmm0
0x14000ca75  xor     eax, eax
0x14000ca77  movups  cs:xmmword_140021D98, xmm0
0x14000ca7e  movups  cs:xmmword_140021DA8, xmm0
0x14000ca85  mov     cs:qword_140021DB8, rax
0x14000ca8c  mov     cs:qword_140021D88, rax
0x14000ca93  mov     cs:qword_140021D90, rax
0x14000ca9a  lea     rdi, ?_AtlModule@@3VCRAServerModule@@A; CRAServerModule _AtlModule
0x14000caa1  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x14000caa8  mov     cs:qword_140021DC0, rax
0x14000caaf  lea     rcx, xmmword_140021D98; this
0x14000cab6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000cabb  test    eax, eax
0x14000cabd  jns     short loc_14000CAC8
0x14000cabf  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000cac6  jmp     short loc_14000CAD2
0x14000cac8  mov     dword ptr cs:qword_140021D88, 38h ; '8'
0x14000cad2  movups  xmm0, xmmword ptr cs:LIBID_RAServerLib.Data1
0x14000cad9  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x14000cae1  call    cs:__imp_GetCurrentThreadId
0x14000cae7  mov     cs:dword_140021DC8, eax
0x14000caed  mov     cs:hEvent, 0
0x14000caf8  mov     cs:dword_140021DD8, 1388h
0x14000cb02  mov     cs:dwMilliseconds, 3E8h
0x14000cb0c  mov     cs:byte_140021DE0, 1
0x14000cb13  mov     cs:byte_140021DE2, 0
0x14000cb1a  xor     edx, edx; dwCoInit
0x14000cb1c  xor     ecx, ecx; pvReserved
0x14000cb1e  call    cs:__imp_CoInitializeEx
0x14000cb24  test    eax, eax
0x14000cb26  jns     short loc_14000CB4A
0x14000cb28  cmp     eax, 80010106h
0x14000cb2d  jnz     short loc_14000CB41
0x14000cb2f  lea     rcx, aMscoreeDll; "Mscoree.dll"
0x14000cb36  call    cs:__imp_GetModuleHandleW
0x14000cb3c  test    rax, rax
0x14000cb3f  jnz     short loc_14000CB51
0x14000cb41  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000cb48  jmp     short loc_14000CB58
0x14000cb4a  mov     cs:byte_140021DE2, 1
0x14000cb51  mov     dl, 1; bool
0x14000cb53  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x14000cb58  mov     rax, rdi
0x14000cb5b  add     rsp, 20h
0x14000cb5f  pop     rdi
0x14000cb60  retn
```
