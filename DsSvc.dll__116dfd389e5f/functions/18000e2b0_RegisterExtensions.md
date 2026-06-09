# RegisterExtensions

- ea: `0x18000e2b0`
- end: `0x18000e34a`
- name: `RegisterExtensions`
- size: `154`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d21c`

## callees

- `0x180003054`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c864`
- `0x18000c9f4`
- `0x18000e2b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e332`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e30b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e30b`
- `ext-ms-win-appmodel-datasharingservice-extensions-l1-1-0!RegisterDataSharingServiceExtensions` at `0x18000e2cb`
- `ext-ms-win-appmodel-datasharingservice-extensions-l1-1-0!RegisterDataSharingServiceExtensions` at `0x18000e2cb`

## string_xrefs

- `0x18000e2f3`: `RegisterExtensions`

## pseudocode

```c
__int64 RegisterExtensions()
{
  int v0; // ebx
  int v1; // eax
  DSLogger *v2; // rax
  int v4; // [rsp+20h] [rbp-18h]
  struct IUnknown *v5; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v5 = 0;
  if ( !(unsigned __int8)IsRegisterDataSharingServiceExtensionsPresent() )
    goto LABEL_6;
  v1 = RegisterDataSharingServiceExtensions(&v5);
  if ( v1 != -2147024769 )
    v0 = v1;
  if ( v0 < 0 )
  {
    v2 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v4 = v0;
    DSLogger::LogError(v2, L"RegisterExtensions", 0x69u, L"hr=0x%x.", v4);
  }
  else
  {
LABEL_6:
    AcquireSRWLockExclusive(&g_extensionLock);
    if ( g_ExtensionRegistrationCookie != v5 )
      ATL::AtlComPtrAssign(&g_ExtensionRegistrationCookie, v5);
    ReleaseSRWLockExclusive(&g_extensionLock);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000e2b0  push    rbx
0x18000e2b2  sub     rsp, 30h
0x18000e2b6  xor     ebx, ebx
0x18000e2b8  mov     [rsp+38h+arg_0], rbx
0x18000e2bd  call    IsRegisterDataSharingServiceExtensionsPresent
0x18000e2c2  test    al, al
0x18000e2c4  jz      short loc_18000E304
0x18000e2c6  lea     rcx, [rsp+38h+arg_0]
0x18000e2cb  call    cs:__imp_RegisterDataSharingServiceExtensions
0x18000e2d1  cmp     eax, 8007007Fh
0x18000e2d6  cmovnz  ebx, eax
0x18000e2d9  test    ebx, ebx
0x18000e2db  jns     short loc_18000E304
0x18000e2dd  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000e2e2  lea     r9, aHr0xX; "hr=0x%x."
0x18000e2e9  mov     [rsp+38h+var_18], ebx
0x18000e2ed  mov     r8d, 69h ; 'i'; unsigned int
0x18000e2f3  lea     rdx, aRegisterextens; "RegisterExtensions"
0x18000e2fa  mov     rcx, rax; this
0x18000e2fd  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000e302  jmp     short loc_18000E338
0x18000e304  lea     rcx, ?g_extensionLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000e30b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e311  mov     rdx, [rsp+38h+arg_0]; struct IUnknown *
0x18000e316  cmp     cs:?g_ExtensionRegistrationCookie@@3V?$CComPtr@UIUnknown@@@ATL@@A, rdx; ATL::CComPtr<IUnknown> g_ExtensionRegistrationCookie
0x18000e31d  jz      short loc_18000E32B
0x18000e31f  lea     rcx, ?g_ExtensionRegistrationCookie@@3V?$CComPtr@UIUnknown@@@ATL@@A; struct IUnknown **
0x18000e326  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000e32b  lea     rcx, ?g_extensionLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000e332  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e338  lea     rcx, [rsp+38h+arg_0]
0x18000e33d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e342  mov     eax, ebx
0x18000e344  add     rsp, 30h
0x18000e348  pop     rbx
0x18000e349  retn
```
