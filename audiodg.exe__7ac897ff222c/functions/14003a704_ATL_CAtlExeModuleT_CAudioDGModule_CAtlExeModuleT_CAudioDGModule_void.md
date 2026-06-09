# ATL::CAtlExeModuleT<CAudioDGModule>::CAtlExeModuleT<CAudioDGModule>(void)

- ea: `0x14003a704`
- end: `0x14003a7f9`
- name: `??0?$CAtlExeModuleT@VCAudioDGModule@@@ATL@@QEAA@XZ`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003a5a0`

## callees

- `0x14000cf6c`
- `0x140035e94`
- `0x14003a704`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003a7ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003a7ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003a779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003a779`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003a7b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003a7b6`

## string_xrefs

- `0x14003a7c7`: `Mscoree.dll`

## pseudocode

```c
__int64 *ATL::CAtlExeModuleT<CAudioDGModule>::CAtlExeModuleT<CAudioDGModule>()
{
  HRESULT v0; // eax
  ATL::CAtlComModule *v1; // rcx

  xmmword_1400E8038 = 0;
  xmmword_1400E8048 = 0;
  qword_1400E8058 = 0;
  qword_1400E8028 = 0;
  qword_1400E8030 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_1400E8060 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_1400E8038) >= 0 )
    LODWORD(qword_1400E8028) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_PolicyServerLib;
  dword_1400E8068 = GetCurrentThreadId();
  qword_1400E8070 = 0;
  dword_1400E8078 = 5000;
  dword_1400E807C = 1000;
  byte_1400E8080 = 1;
  byte_1400E8082 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    byte_1400E8082 = 1;
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
0x14003a704  push    rdi
0x14003a706  sub     rsp, 20h
0x14003a70a  xorps   xmm0, xmm0
0x14003a70d  xor     eax, eax
0x14003a70f  movups  cs:xmmword_1400E8038, xmm0
0x14003a716  movups  cs:xmmword_1400E8048, xmm0
0x14003a71d  mov     cs:qword_1400E8058, rax
0x14003a724  mov     cs:qword_1400E8028, rax
0x14003a72b  mov     cs:qword_1400E8030, rax
0x14003a732  lea     rdi, ?_AtlModule@@3VCAudioDGModule@@A; CAudioDGModule _AtlModule
0x14003a739  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x14003a740  mov     cs:qword_1400E8060, rax
0x14003a747  lea     rcx, xmmword_1400E8038; this
0x14003a74e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14003a753  test    eax, eax
0x14003a755  jns     short loc_14003A760
0x14003a757  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14003a75e  jmp     short loc_14003A76A
0x14003a760  mov     dword ptr cs:qword_1400E8028, 38h ; '8'
0x14003a76a  movups  xmm0, xmmword ptr cs:LIBID_PolicyServerLib.Data1
0x14003a771  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x14003a779  call    cs:__imp_GetCurrentThreadId
0x14003a77f  mov     cs:dword_1400E8068, eax
0x14003a785  mov     cs:qword_1400E8070, 0
0x14003a790  mov     cs:dword_1400E8078, 1388h
0x14003a79a  mov     cs:dword_1400E807C, 3E8h
0x14003a7a4  mov     cs:byte_1400E8080, 1
0x14003a7ab  mov     cs:byte_1400E8082, 0
0x14003a7b2  xor     edx, edx; dwCoInit
0x14003a7b4  xor     ecx, ecx; pvReserved
0x14003a7b6  call    cs:__imp_CoInitializeEx
0x14003a7bc  test    eax, eax
0x14003a7be  jns     short loc_14003A7E2
0x14003a7c0  cmp     eax, 80010106h
0x14003a7c5  jnz     short loc_14003A7D9
0x14003a7c7  lea     rcx, ModuleName; "Mscoree.dll"
0x14003a7ce  call    cs:__imp_GetModuleHandleW
0x14003a7d4  test    rax, rax
0x14003a7d7  jnz     short loc_14003A7E9
0x14003a7d9  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14003a7e0  jmp     short loc_14003A7F0
0x14003a7e2  mov     cs:byte_1400E8082, 1
0x14003a7e9  mov     dl, 1; bool
0x14003a7eb  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x14003a7f0  mov     rax, rdi
0x14003a7f3  add     rsp, 20h
0x14003a7f7  pop     rdi
0x14003a7f8  retn
```
