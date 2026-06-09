# Windows::Globalization::Spelling::_dynamic_initializer_for___AtlModule__

- ea: `0x140001070`
- end: `0x1400011bc`
- name: `Windows::Globalization::Spelling::_dynamic_initializer_for___AtlModule__`
- size: `332`
- prototype: `int()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001070`
- `0x140001cc4`
- `0x140003dfc`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400010e4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400010e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400010a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000116e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400010a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000116e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400010fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400010fc`

## string_xrefs

- `0x1400010f5`: `Mscoree.dll`

## pseudocode

```c
int Windows::Globalization::Spelling::_dynamic_initializer_for___AtlModule__()
{
  HRESULT v0; // eax
  __int64 v1; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rax

  ATL::_pAtlModule = (struct ATL::CAtlModule *)&Windows::Globalization::Spelling::_AtlModule;
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_14001BFE8) >= 0 )
    dword_14001BFD8 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  dword_14001C018 = GetCurrentThreadId();
  hEvent = 0;
  dword_14001C028 = 5000;
  dwMilliseconds = 1000;
  byte_14001C030 = 1;
  byte_14001C032 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    byte_14001C032 = 1;
  }
  else if ( v0 != -2147417850 || !GetModuleHandleW(L"Mscoree.dll") )
  {
    ATL::CAtlBaseModule::m_bInitFailed = 1;
    goto LABEL_14;
  }
  v2 = off_14001B2E0;
  v3 = off_14001B2E8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      LOBYTE(v1) = 1;
      (*((void (__fastcall **)(__int64))*v2 + 8))(v1);
      v3 = off_14001B2E8;
    }
    ++v2;
  }
LABEL_14:
  Windows::Globalization::Spelling::_AtlModule = &Windows::Globalization::Spelling::CHostModule::`vftable';
  hMutex = 0;
  *(_OWORD *)&xmmword_14001C040 = 0;
  idThread = GetCurrentThreadId();
  qword_14001C058 = 0;
  hObject = 0;
  dword_14001C068 = 5000;
  dword_14001C06C = 1000;
  byte_14001C030 = 0;
  return atexit((void (__cdecl *)())Windows::Globalization::Spelling::_dynamic_atexit_destructor_for___AtlModule__);
}

```

## disassembly

```asm
0x140001070  push    rbx
0x140001072  sub     rsp, 20h
0x140001076  lea     rax, ?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A; Windows::Globalization::Spelling::CHostModule Windows::Globalization::Spelling::_AtlModule
0x14000107d  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x140001084  lea     rcx, qword_14001BFE8; this
0x14000108b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001090  test    eax, eax
0x140001092  jns     short loc_14000109D
0x140001094  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000109b  jmp     short loc_1400010A7
0x14000109d  mov     cs:dword_14001BFD8, 38h ; '8'
0x1400010a7  call    cs:__imp_GetCurrentThreadId
0x1400010ad  mov     cs:dword_14001C018, eax
0x1400010b3  mov     cs:hEvent, 0
0x1400010be  mov     cs:dword_14001C028, 1388h
0x1400010c8  mov     cs:dwMilliseconds, 3E8h
0x1400010d2  mov     cs:byte_14001C030, 1
0x1400010d9  mov     cs:byte_14001C032, 0
0x1400010e0  xor     edx, edx; dwCoInit
0x1400010e2  xor     ecx, ecx; pvReserved
0x1400010e4  call    cs:__imp_CoInitializeEx
0x1400010ea  test    eax, eax
0x1400010ec  jns     short loc_140001110
0x1400010ee  cmp     eax, 80010106h
0x1400010f3  jnz     short loc_140001107
0x1400010f5  lea     rcx, ModuleName; "Mscoree.dll"
0x1400010fc  call    cs:__imp_GetModuleHandleW
0x140001102  test    rax, rax
0x140001105  jnz     short loc_140001117
0x140001107  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000110e  jmp     short loc_14000114A
0x140001110  mov     cs:byte_14001C032, 1
0x140001117  mov     rbx, cs:off_14001B2E0
0x14000111e  mov     rax, cs:off_14001B2E8
0x140001125  jmp     short loc_140001145
0x140001127  mov     rdx, [rbx]
0x14000112a  test    rdx, rdx
0x14000112d  jz      short loc_140001141
0x14000112f  mov     cl, 1
0x140001131  mov     rax, [rdx+40h]
0x140001135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000113a  mov     rax, cs:off_14001B2E8
0x140001141  add     rbx, 8
0x140001145  cmp     rbx, rax
0x140001148  jb      short loc_140001127
0x14000114a  lea     rax, ??_7CHostModule@Spelling@Globalization@Windows@@6B@; const Windows::Globalization::Spelling::CHostModule::`vftable'
0x140001151  mov     cs:?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A, rax; Windows::Globalization::Spelling::CHostModule Windows::Globalization::Spelling::_AtlModule
0x140001158  mov     cs:hMutex, 0
0x140001163  xorps   xmm0, xmm0
0x140001166  movdqa  cs:xmmword_14001C040, xmm0
0x14000116e  call    cs:__imp_GetCurrentThreadId
0x140001174  mov     cs:idThread, eax
0x14000117a  mov     cs:qword_14001C058, 0
0x140001185  mov     cs:hObject, 0
0x140001190  mov     cs:dword_14001C068, 1388h
0x14000119a  mov     cs:dword_14001C06C, 3E8h
0x1400011a4  mov     cs:byte_14001C030, 0
0x1400011ab  lea     rcx, Windows__Globalization__Spelling___dynamic_atexit_destructor_for___AtlModule__
0x1400011b2  add     rsp, 20h
0x1400011b6  pop     rbx
0x1400011b7  jmp     atexit
```
