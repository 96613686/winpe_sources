# _dynamic_initializer_for___AtlModule__

- ea: `0x1400017c0`
- end: `0x140001930`
- name: `_dynamic_initializer_for___AtlModule__`
- size: `368`
- prototype: `int()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400017c0`
- `0x140001fe4`
- `0x1400035bc`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001843`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001806`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400018cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400018cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000185b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000185b`

## string_xrefs

- `0x140001854`: `Mscoree.dll`

## pseudocode

```c
int dynamic_initializer_for___AtlModule__()
{
  HRESULT v0; // eax
  __int64 v1; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rax

  ATL::_pAtlModule = (CTieringEngineService *)&_AtlModule;
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)qword_14004CA68) >= 0 )
    dword_14004CA58 = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_TieringEngineServerLib;
  dword_14004CA98 = GetCurrentThreadId();
  qword_14004CAA0 = 0;
  dword_14004CAA8 = 5000;
  dword_14004CAAC = 1000;
  byte_14004CAB0 = 1;
  byte_14004CAB2 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    byte_14004CAB2 = 1;
  }
  else if ( v0 != -2147417850 || !GetModuleHandleW(L"Mscoree.dll") )
  {
    ATL::CAtlBaseModule::m_bInitFailed = 1;
    goto LABEL_14;
  }
  v2 = off_14004C200;
  v3 = off_14004C208;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      LOBYTE(v1) = 1;
      (*((void (__fastcall **)(__int64))*v2 + 8))(v1);
      v3 = off_14004C208;
    }
    ++v2;
  }
LABEL_14:
  qword_14004CCF0 = 0;
  LoadStringW(hInstance, 0x66u, &Buffer, 256);
  qword_14004CCB8 = 0;
  dword_14004CCC0 = 16;
  dword_14004CCC4 = 1;
  dword_14004CCC8 = 5;
  xmmword_14004CCCC = 0;
  hObject = 0;
  _AtlModule = &CTieringEngineService::`vftable';
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for___AtlModule__);
}

```

## disassembly

```asm
0x1400017c0  push    rbx
0x1400017c2  sub     rsp, 20h
0x1400017c6  lea     rax, ?_AtlModule@@3VCTieringEngineService@@A; CTieringEngineService _AtlModule
0x1400017cd  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x1400017d4  lea     rcx, qword_14004CA68; this
0x1400017db  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400017e0  test    eax, eax
0x1400017e2  jns     short loc_1400017ED
0x1400017e4  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400017eb  jmp     short loc_1400017F7
0x1400017ed  mov     cs:dword_14004CA58, 38h ; '8'
0x1400017f7  movups  xmm0, xmmword ptr cs:LIBID_TieringEngineServerLib.Data1
0x1400017fe  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x140001806  call    cs:__imp_GetCurrentThreadId
0x14000180c  mov     cs:dword_14004CA98, eax
0x140001812  mov     cs:qword_14004CAA0, 0
0x14000181d  mov     cs:dword_14004CAA8, 1388h
0x140001827  mov     cs:dword_14004CAAC, 3E8h
0x140001831  mov     cs:byte_14004CAB0, 1
0x140001838  mov     cs:byte_14004CAB2, 0
0x14000183f  xor     edx, edx; dwCoInit
0x140001841  xor     ecx, ecx; pvReserved
0x140001843  call    cs:__imp_CoInitializeEx
0x140001849  test    eax, eax
0x14000184b  jns     short loc_14000186F
0x14000184d  cmp     eax, 80010106h
0x140001852  jnz     short loc_140001866
0x140001854  lea     rcx, ModuleName; "Mscoree.dll"
0x14000185b  call    cs:__imp_GetModuleHandleW
0x140001861  test    rax, rax
0x140001864  jnz     short loc_140001876
0x140001866  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000186d  jmp     short loc_1400018A9
0x14000186f  mov     cs:byte_14004CAB2, 1
0x140001876  mov     rbx, cs:off_14004C200
0x14000187d  mov     rax, cs:off_14004C208
0x140001884  jmp     short loc_1400018A4
0x140001886  mov     rdx, [rbx]
0x140001889  test    rdx, rdx
0x14000188c  jz      short loc_1400018A0
0x14000188e  mov     cl, 1
0x140001890  mov     rax, [rdx+40h]
0x140001894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001899  mov     rax, cs:off_14004C208
0x1400018a0  add     rbx, 8
0x1400018a4  cmp     rbx, rax
0x1400018a7  jb      short loc_140001886
0x1400018a9  mov     cs:qword_14004CCF0, 0
0x1400018b4  mov     r9d, 100h; cchBufferMax
0x1400018ba  lea     r8, Buffer; lpBuffer
0x1400018c1  mov     edx, 66h ; 'f'; uID
0x1400018c6  mov     rcx, cs:hInstance; hInstance
0x1400018cd  call    cs:__imp_LoadStringW
0x1400018d3  mov     cs:qword_14004CCB8, 0
0x1400018de  mov     cs:dword_14004CCC0, 10h
0x1400018e8  mov     cs:dword_14004CCC4, 1
0x1400018f2  mov     cs:dword_14004CCC8, 5
0x1400018fc  xorps   xmm0, xmm0
0x1400018ff  movups  cs:xmmword_14004CCCC, xmm0
0x140001906  mov     cs:hObject, 0
0x140001911  lea     rax, ??_7CTieringEngineService@@6B@; const CTieringEngineService::`vftable'
0x140001918  mov     cs:?_AtlModule@@3VCTieringEngineService@@A, rax; CTieringEngineService _AtlModule
0x14000191f  lea     rcx, _dynamic_atexit_destructor_for___AtlModule__
0x140001926  add     rsp, 20h
0x14000192a  pop     rbx
0x14000192b  jmp     atexit
```
