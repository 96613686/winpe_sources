# CAxisServModule::Run(void)

- ea: `0x18000f170`
- end: `0x18000f45a`
- name: `?Run@CAxisServModule@@QEAAXXZ`
- size: `746`
- prototype: `void __fastcall(CAxisServModule *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011740`

## callees

- `0x180002af0`
- `0x18000725c`
- `0x180009f74`
- `0x18000c224`
- `0x18000e5cc`
- `0x18000f170`
- `0x18000fb54`
- `0x18000fd10`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x18000f410`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x18000f410`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x18000f36a`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x18000f36a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f1a8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f1a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f22c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f22c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f43f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f43f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f3fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f3fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f41d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f41d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAxisServModule::Run(CAxisServModule *this)
{
  HRESULT v1; // esi
  int v2; // eax
  DWORD v3; // ebx
  HRESULT v4; // ebx
  unsigned int v5; // edx
  ATL::_ATL_OBJMAP_ENTRY30 *v6; // rbx
  int v7; // eax
  ATL::_ATL_OBJMAP_ENTRY30 **v8; // rbx
  unsigned __int64 v9; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-38h]
  LPVOID *ppva; // [rsp+20h] [rbp-38h]
  LPVOID v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = this;
  CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 2u);
  v1 = CoInitializeEx(0, 4u);
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147417850 )
  {
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"CoInitializeEx, hr=%!HRESULT!\n", v1);
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v1;
    CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 1u);
    return;
  }
  v12 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v12) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, 5, 1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  v2 = CAxisServModule::Initialize((CAxisServModule *)&_AtlModule);
  v3 = v2;
  if ( v2 < 0 )
  {
    LODWORD(ppv) = v2;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Initialize  failed, hr=%!HRESULT!\n", ppv);
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v3;
    CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 3u);
    v4 = CAxisServModule::Cleanup((CAxisServModule *)&_AtlModule);
    LODWORD(ppva) = v4;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 5u, L"Cleanup, hr=%!HRESULT!\n", ppva);
    CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 1u);
    goto LABEL_30;
  }
  ServiceStatus.dwControlsAccepted = 5;
  CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 4u);
  v6 = qword_180021638;
  if ( qword_180021638 && (v7 = 0, *(_QWORD *)qword_180021638) )
  {
    while ( !v7 )
    {
      v7 = ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(v6, v5, 5u);
      v6 = (ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v6 + 72);
      if ( !*(_QWORD *)v6 )
      {
        if ( v7 )
          break;
        goto LABEL_13;
      }
    }
  }
  else
  {
LABEL_13:
    v7 = 1;
    v8 = (ATL::_ATL_OBJMAP_ENTRY30 **)off_1800210B0;
    v9 = *(_QWORD *)&off_1800210B8;
    while ( (unsigned __int64)v8 < v9 && v7 >= 0 )
    {
      if ( *v8 )
      {
        v7 = ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(*v8, v9, 5u);
        v9 = *(_QWORD *)&off_1800210B8;
      }
      ++v8;
    }
  }
  if ( v7 >= 0 )
  {
    v4 = CoResumeClassObjects();
    if ( v4 >= 0 )
    {
      if ( !hEvent )
        goto LABEL_32;
      if ( g_pSvchostSharedGlobals )
      {
        if ( !(*((unsigned int (__fastcall **)(__int64 *, const WCHAR *, HANDLE, void (__fastcall *)(void *, int), __int64 *, int))g_pSvchostSharedGlobals
               + 24))(
                &qword_180021AD0,
                L"AxInstSV",
                hEvent,
                CAxisServModule::StopService,
                &_AtlModule,
                8) )
          goto LABEL_27;
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Failure calling RegisterStopCallback");
      }
      else
      {
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"g_pSvchostSharedGlobals not set");
      }
      v4 = -2147467259;
LABEL_27:
      while ( WaitForSingleObject(hEvent, 0x493E0u) )
      {
        if ( !HIDWORD(qword_1800215F8) )
        {
          CoSuspendClassObjects();
          SetEvent(hEvent);
          break;
        }
      }
LABEL_30:
      if ( v4 >= 0 )
        goto LABEL_32;
    }
  }
  CAxisServModule::Stop((CAxisServModule *)&_AtlModule);
LABEL_32:
  CAxisServModule::Cleanup((CAxisServModule *)&_AtlModule);
  if ( v1 != -2147417850 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18000f170  mov     [rsp+arg_8], rbx
0x18000f175  mov     [rsp+arg_10], rsi
0x18000f17a  mov     [rsp+arg_0], rcx
0x18000f17f  push    r12
0x18000f181  push    r14
0x18000f183  push    r15
0x18000f185  sub     rsp, 40h
0x18000f189  mov     r12d, 2
0x18000f18f  mov     edx, r12d; unsigned int
0x18000f192  lea     r14, ?_AtlModule@@3VCAxisServModule@@A; CAxisServModule _AtlModule
0x18000f199  mov     rcx, r14; this
0x18000f19c  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000f1a1  lea     edx, [r12+2]; dwCoInit
0x18000f1a6  xor     ecx, ecx; pvReserved
0x18000f1a8  call    cs:__imp_CoInitializeEx
0x18000f1ae  mov     esi, eax
0x18000f1b0  mov     eax, 80000000h
0x18000f1b5  lea     ecx, [rsi+rax]
0x18000f1b8  test    eax, ecx
0x18000f1ba  jnz     short loc_18000F205
0x18000f1bc  cmp     esi, 80010106h
0x18000f1c2  jz      short loc_18000F205
0x18000f1c4  mov     dword ptr [rsp+58h+ppv], esi
0x18000f1c8  lea     r9, aCoinitializeex; "CoInitializeEx, hr=%!HRESULT!\n"
0x18000f1cf  mov     r8d, r12d; unsigned __int8
0x18000f1d2  lea     edx, [r12+6]; unsigned int
0x18000f1d7  lea     rcx, qword_180021AD8; this
0x18000f1de  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000f1e3  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000f1ed  mov     cs:ServiceStatus.dwServiceSpecificExitCode, esi
0x18000f1f3  lea     edx, [r12-1]; unsigned int
0x18000f1f8  mov     rcx, r14; this
0x18000f1fb  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000f200  jmp     loc_18000F445
0x18000f205  mov     [rsp+58h+arg_0], 0
0x18000f20e  lea     rax, [rsp+58h+arg_0]
0x18000f213  mov     [rsp+58h+ppv], rax; ppv
0x18000f218  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000f21f  xor     edx, edx; pUnkOuter
0x18000f221  lea     r8d, [rdx+1]; dwClsContext
0x18000f225  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000f22c  call    cs:__imp_CoCreateInstance
0x18000f232  mov     r15d, 5
0x18000f238  test    eax, eax
0x18000f23a  js      short loc_18000F255
0x18000f23c  mov     rcx, [rsp+58h+arg_0]
0x18000f241  mov     rax, [rcx]
0x18000f244  lea     r8d, [r15-4]
0x18000f248  mov     edx, r15d
0x18000f24b  mov     rax, [rax+18h]
0x18000f24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f254  nop
0x18000f255  lea     rcx, [rsp+58h+arg_0]
0x18000f25a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f25f  mov     rcx, r14; this
0x18000f262  call    ?Initialize@CAxisServModule@@QEAAJXZ; CAxisServModule::Initialize(void)
0x18000f267  mov     ebx, eax
0x18000f269  test    eax, eax
0x18000f26b  jns     short loc_18000F2E4
0x18000f26d  mov     dword ptr [rsp+58h+ppv], eax
0x18000f271  lea     r9, aInitializeFail; "Initialize  failed, hr=%!HRESULT!\n"
0x18000f278  mov     r8d, r12d; unsigned __int8
0x18000f27b  mov     edx, 8; unsigned int
0x18000f280  lea     rcx, qword_180021AD8; this
0x18000f287  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000f28c  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000f296  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebx
0x18000f29c  mov     edx, 3; unsigned int
0x18000f2a1  mov     rcx, r14; this
0x18000f2a4  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000f2a9  mov     rcx, r14; this
0x18000f2ac  call    ?Cleanup@CAxisServModule@@QEAAJXZ; CAxisServModule::Cleanup(void)
0x18000f2b1  mov     ebx, eax
0x18000f2b3  mov     dword ptr [rsp+58h+ppv], eax
0x18000f2b7  lea     r9, aCleanupHrHresu; "Cleanup, hr=%!HRESULT!\n"
0x18000f2be  mov     r8d, r15d; unsigned __int8
0x18000f2c1  mov     edx, 8; unsigned int
0x18000f2c6  lea     rcx, qword_180021AD8; this
0x18000f2cd  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000f2d2  mov     edx, 1; unsigned int
0x18000f2d7  mov     rcx, r14; this
0x18000f2da  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000f2df  jmp     loc_18000F423
0x18000f2e4  mov     cs:ServiceStatus.dwControlsAccepted, r15d
0x18000f2eb  mov     edx, 4; unsigned int
0x18000f2f0  mov     rcx, r14; this
0x18000f2f3  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000f2f8  nop
0x18000f2f9  mov     rbx, cs:qword_180021638
0x18000f300  test    rbx, rbx
0x18000f303  jz      short loc_18000F329
0x18000f305  xor     eax, eax
0x18000f307  cmp     [rbx], rax
0x18000f30a  jz      short loc_18000F329
0x18000f30c  test    eax, eax
0x18000f30e  jnz     short loc_18000F362
0x18000f310  mov     r8d, r15d; unsigned int
0x18000f313  mov     rcx, rbx; this
0x18000f316  call    ?RegisterClassObject@_ATL_OBJMAP_ENTRY30@ATL@@QEAAJKK@Z; ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(ulong,ulong)
0x18000f31b  add     rbx, 48h ; 'H'
0x18000f31f  cmp     qword ptr [rbx], 0
0x18000f323  jnz     short loc_18000F30C
0x18000f325  test    eax, eax
0x18000f327  jnz     short loc_18000F362
0x18000f329  mov     eax, 1
0x18000f32e  mov     rbx, cs:off_1800210B0
0x18000f335  mov     rdx, cs:off_1800210B8
0x18000f33c  jmp     short loc_18000F35D
0x18000f33e  test    eax, eax
0x18000f340  js      short loc_18000F362
0x18000f342  mov     rcx, [rbx]; this
0x18000f345  test    rcx, rcx
0x18000f348  jz      short loc_18000F359
0x18000f34a  mov     r8d, r15d; unsigned int
0x18000f34d  call    ?RegisterClassObject@_ATL_OBJMAP_ENTRY30@ATL@@QEAAJKK@Z; ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(ulong,ulong)
0x18000f352  mov     rdx, cs:off_1800210B8; unsigned int
0x18000f359  add     rbx, 8
0x18000f35d  cmp     rbx, rdx
0x18000f360  jb      short loc_18000F33E
0x18000f362  test    eax, eax
0x18000f364  js      loc_18000F427
0x18000f36a  call    cs:__imp_CoResumeClassObjects
0x18000f370  mov     ebx, eax
0x18000f372  test    eax, eax
0x18000f374  js      loc_18000F427
0x18000f37a  mov     r8, qword ptr cs:hEvent
0x18000f381  test    r8, r8
0x18000f384  jz      loc_18000F42F
0x18000f38a  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x18000f391  test    rax, rax
0x18000f394  jz      short loc_18000F3D1
0x18000f396  mov     [rsp+58h+var_30], 8
0x18000f39e  mov     [rsp+58h+ppv], r14
0x18000f3a3  lea     r9, ?StopService@CAxisServModule@@SAXPEAXH@Z; CAxisServModule::StopService(void *,int)
0x18000f3aa  lea     rdx, ServiceName; "AxInstSV"
0x18000f3b1  lea     rcx, qword_180021AD0
0x18000f3b8  mov     rax, [rax+0C0h]
0x18000f3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c4  test    eax, eax
0x18000f3c6  jz      short loc_18000F3F1
0x18000f3c8  lea     r9, aFailureCalling; "Failure calling RegisterStopCallback"
0x18000f3cf  jmp     short loc_18000F3D8
0x18000f3d1  lea     r9, aGPsvchostshare; "g_pSvchostSharedGlobals not set"
0x18000f3d8  mov     r8d, r12d; unsigned __int8
0x18000f3db  mov     edx, 8; unsigned int
0x18000f3e0  lea     rcx, qword_180021AD8; this
0x18000f3e7  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000f3ec  mov     ebx, 80004005h
0x18000f3f1  mov     edx, 493E0h; dwMilliseconds
0x18000f3f6  mov     rcx, qword ptr cs:hEvent; hHandle
0x18000f3fd  call    cs:__imp_WaitForSingleObject
0x18000f403  test    eax, eax
0x18000f405  jz      short loc_18000F423
0x18000f407  cmp     dword ptr cs:qword_1800215F8+4, 0
0x18000f40e  jnz     short loc_18000F3F1
0x18000f410  call    cs:__imp_CoSuspendClassObjects
0x18000f416  mov     rcx, qword ptr cs:hEvent; hEvent
0x18000f41d  call    cs:__imp_SetEvent
0x18000f423  test    ebx, ebx
0x18000f425  jns     short loc_18000F42F
0x18000f427  mov     rcx, r14; this
0x18000f42a  call    ?Stop@CAxisServModule@@QEAAXXZ; CAxisServModule::Stop(void)
0x18000f42f  mov     rcx, r14; this
0x18000f432  call    ?Cleanup@CAxisServModule@@QEAAJXZ; CAxisServModule::Cleanup(void)
0x18000f437  cmp     esi, 80010106h
0x18000f43d  jz      short loc_18000F445
0x18000f43f  call    cs:__imp_CoUninitialize
0x18000f445  mov     rbx, [rsp+58h+arg_8]
0x18000f44a  mov     rsi, [rsp+58h+arg_10]
0x18000f44f  add     rsp, 40h
0x18000f453  pop     r15
0x18000f455  pop     r14
0x18000f457  pop     r12
0x18000f459  retn
```
