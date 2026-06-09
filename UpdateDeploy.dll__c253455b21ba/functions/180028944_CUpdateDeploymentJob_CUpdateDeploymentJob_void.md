# CUpdateDeploymentJob::~CUpdateDeploymentJob(void)

- ea: `0x180028944`
- end: `0x180028c2e`
- name: `??1CUpdateDeploymentJob@@UEAA@XZ`
- size: `746`
- prototype: `void __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180037fe0`

## callees

- `0x180007b6c`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011b44`
- `0x180017248`
- `0x180028944`
- `0x180031dcc`
- `0x180038214`
- `0x180038258`
- `0x180061d54`
- `0x180062150`
- `0x18006215c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800289e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800289e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028acc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028ae0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028acc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800289fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800289fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b49`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180028a72`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180028a72`

## string_xrefs

- `0x1800289c2`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUpdateDeploymentJob::~CUpdateDeploymentJob(CUpdateDeploymentJob *this)
{
  int v2; // eax
  HANDLE *i; // rbx
  unsigned int j; // ebx
  __int64 v5; // rcx
  void *v6; // rcx
  char *v7; // rcx
  char *v8; // rbx
  void *v9; // rcx
  void *v10; // rcx
  const struct std::nothrow_t *v11; // rdx
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  int v20; // [rsp+20h] [rbp-88h]
  char v21[80]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *(_QWORD *)this = &CUpdateDeploymentJob::`vftable'{for `IUpdateDeploymentJob'};
  *((_QWORD *)this + 1) = &CUpdateDeploymentJob::`vftable'{for `IUpdateDeploymentCallback'};
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v21, (const struct _GUID *)this + 1);
  WUTrace(0, 0, 0x1000000, 4, 0, L"Deployment job Id %ws : Destructor invoked for deployment job.");
  v2 = CUpdateDeploymentJob::EndInternal(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v2,
      v20);
  if ( this != (CUpdateDeploymentJob *)-880LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  for ( i = (HANDLE *)*((_QWORD *)this + 94); i != *((HANDLE **)this + 95); ++i )
  {
    if ( *i )
      CloseHandle(*i);
  }
  for ( j = 0; j < *((_DWORD *)this + 172); ++j )
  {
    v5 = *(_QWORD *)(*((_QWORD *)this + 87) + 8LL * j);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *(_QWORD *)(*((_QWORD *)this + 87) + 8LL * j) = 0;
  }
  if ( this != (CUpdateDeploymentJob *)-880LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v6 = (void *)*((_QWORD *)this + 123);
  if ( v6 && v6 != (void *)-1LL )
    ClosePrivateNamespace(v6, 1u);
  v7 = (char *)*((_QWORD *)this + 122);
  if ( v7 )
  {
    v8 = v7 - 8;
    `eh vector destructor iterator'(
      v7,
      8u,
      *((_QWORD *)v7 - 1),
      WuSmartPtr::XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy>::~XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy>);
    operator delete[](v8, (const struct std::nothrow_t *)(8LL * *(_QWORD *)v8 + 8));
    *((_QWORD *)this + 122) = 0;
  }
  *((_QWORD *)this + 116) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
  *((_QWORD *)this + 110) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v9 = (void *)*((_QWORD *)this + 98);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 98) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 97);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 97) = 0;
  }
  std::vector<void *>::~vector<void *>((char *)this + 752);
  v12 = (void *)*((_QWORD *)this + 93);
  if ( v12 )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 93) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 92);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 92) = 0;
  }
  v14 = *((_QWORD *)this + 91);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 91) = 0;
  }
  v15 = *((_QWORD *)this + 90);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 90) = 0;
  }
  v16 = *((_QWORD *)this + 89);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 89) = 0;
  }
  v17 = *((_QWORD *)this + 88);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 88) = 0;
  }
  v18 = (void *)*((_QWORD *)this + 87);
  if ( v18 )
  {
    operator delete(v18, v11);
    *((_QWORD *)this + 87) = 0;
  }
  v19 = (void *)*((_QWORD *)this + 85);
  if ( v19 )
  {
    SusFree(v19);
    *((_QWORD *)this + 85) = 0;
  }
  CSusArrayList<CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::_tagMapEntry,CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::_tagMapEntry,CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::CMapEntryOps>((char *)this + 640);
  CUHHandlerManager::~CUHHandlerManager((CUpdateDeploymentJob *)((char *)this + 48));
}

```

## disassembly

```asm
0x180028944  mov     [rsp+arg_8], rbx
0x180028949  mov     [rsp+arg_10], rbp
0x18002894e  push    rsi
0x18002894f  push    rdi
0x180028950  push    r14
0x180028952  sub     rsp, 90h
0x180028959  mov     rsi, rcx
0x18002895c  lea     rax, ??_7CUpdateDeploymentJob@@6BIUpdateDeploymentJob@@@; const CUpdateDeploymentJob::`vftable'{for `IUpdateDeploymentJob'}
0x180028963  mov     [rcx], rax
0x180028966  lea     rax, ??_7CUpdateDeploymentJob@@6BIUpdateDeploymentCallback@@@; const CUpdateDeploymentJob::`vftable'{for `IUpdateDeploymentCallback'}
0x18002896d  mov     [rcx+8], rax
0x180028971  lea     rdx, [rcx+10h]; struct _GUID *
0x180028975  lea     rcx, [rsp+0A8h+var_68]; this
0x18002897a  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002897f  mov     [rsp+0A8h+var_78], rax
0x180028984  lea     rax, aDeploymentJobI_63; "Deployment job Id %ws : Destructor invo"...
0x18002898b  mov     [rsp+0A8h+var_80], rax
0x180028990  xor     r14d, r14d
0x180028993  mov     qword ptr [rsp+0A8h+var_88], r14; int
0x180028998  xor     edx, edx
0x18002899a  xor     ecx, ecx
0x18002899c  lea     r9d, [r14+4]
0x1800289a0  mov     r8d, 1000000h
0x1800289a6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800289ab  mov     rcx, rsi; this
0x1800289ae  call    ?EndInternal@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::EndInternal(void)
0x1800289b3  mov     rcx, [rsp+0A8h]; this
0x1800289bb  test    eax, eax
0x1800289bd  jns     short loc_1800289D3
0x1800289bf  mov     r9d, eax; char *
0x1800289c2  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800289c9  mov     edx, 161h; void *
0x1800289ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800289d3  lea     rdi, [rsi+370h]
0x1800289da  test    rdi, rdi
0x1800289dd  jz      short loc_1800289E9
0x1800289df  lea     rcx, [rdi+8]; lpCriticalSection
0x1800289e3  call    cs:__imp_EnterCriticalSection
0x1800289e9  mov     rbx, [rsi+2F0h]
0x1800289f0  jmp     short loc_180028A04
0x1800289f2  mov     rcx, [rbx]; hObject
0x1800289f5  test    rcx, rcx
0x1800289f8  jz      short loc_180028A00
0x1800289fa  call    cs:__imp_CloseHandle
0x180028a00  add     rbx, 8
0x180028a04  cmp     rbx, [rsi+2F8h]
0x180028a0b  jnz     short loc_1800289F2
0x180028a0d  mov     ebx, r14d
0x180028a10  cmp     [rsi+2B0h], r14d
0x180028a17  jbe     short loc_180028A4C
0x180028a19  mov     ebp, ebx
0x180028a1b  mov     rax, [rsi+2B8h]
0x180028a22  mov     rcx, [rax+rbp*8]
0x180028a26  test    rcx, rcx
0x180028a29  jz      short loc_180028A37
0x180028a2b  mov     rax, [rcx]
0x180028a2e  mov     rax, [rax+10h]
0x180028a32  call    _guard_dispatch_icall
0x180028a37  mov     rax, [rsi+2B8h]
0x180028a3e  mov     [rax+rbp*8], r14
0x180028a42  inc     ebx
0x180028a44  cmp     ebx, [rsi+2B0h]
0x180028a4a  jb      short loc_180028A19
0x180028a4c  test    rdi, rdi
0x180028a4f  jz      short loc_180028A5B
0x180028a51  lea     rcx, [rdi+8]; lpCriticalSection
0x180028a55  call    cs:__imp_LeaveCriticalSection
0x180028a5b  mov     rcx, [rsi+3D8h]; Handle
0x180028a62  test    rcx, rcx
0x180028a65  jz      short loc_180028A78
0x180028a67  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180028a6b  jz      short loc_180028A78
0x180028a6d  mov     edx, 1; Flags
0x180028a72  call    cs:__imp_ClosePrivateNamespace
0x180028a78  mov     rcx, [rsi+3D0h]; void *
0x180028a7f  test    rcx, rcx
0x180028a82  jz      short loc_180028AB7
0x180028a84  lea     rbx, [rcx-8]
0x180028a88  lea     r9, ??1?$XHandleBase@PEAXUNullHandlePolicy@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; void (*)(void *)
0x180028a8f  mov     r8, [rbx]; unsigned __int64
0x180028a92  mov     edx, 8; unsigned __int64
0x180028a97  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180028a9c  mov     rdx, [rbx]
0x180028a9f  lea     rdx, ds:8[rdx*8]; struct std::nothrow_t *
0x180028aa7  mov     rcx, rbx; void *
0x180028aaa  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x180028aaf  nop
0x180028ab0  mov     [rsi+3D0h], r14
0x180028ab7  lea     rbx, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180028abe  mov     [rsi+3A0h], rbx
0x180028ac5  lea     rcx, [rsi+3A8h]; lpCriticalSection
0x180028acc  call    cs:__imp_DeleteCriticalSection
0x180028ad2  mov     [rsi+370h], rbx
0x180028ad9  lea     rcx, [rsi+378h]; lpCriticalSection
0x180028ae0  call    cs:__imp_DeleteCriticalSection
0x180028ae6  mov     rcx, [rsi+310h]; hObject
0x180028aed  test    rcx, rcx
0x180028af0  jz      short loc_180028AFF
0x180028af2  call    cs:__imp_CloseHandle
0x180028af8  mov     [rsi+310h], r14
0x180028aff  mov     rcx, [rsi+308h]; hObject
0x180028b06  test    rcx, rcx
0x180028b09  jz      short loc_180028B18
0x180028b0b  call    cs:__imp_CloseHandle
0x180028b11  mov     [rsi+308h], r14
0x180028b18  lea     rcx, [rsi+2F0h]
0x180028b1f  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180028b24  mov     rcx, [rsi+2E8h]; hObject
0x180028b2b  test    rcx, rcx
0x180028b2e  jz      short loc_180028B3D
0x180028b30  call    cs:__imp_CloseHandle
0x180028b36  mov     [rsi+2E8h], r14
0x180028b3d  mov     rcx, [rsi+2E0h]; hObject
0x180028b44  test    rcx, rcx
0x180028b47  jz      short loc_180028B56
0x180028b49  call    cs:__imp_CloseHandle
0x180028b4f  mov     [rsi+2E0h], r14
0x180028b56  mov     rcx, [rsi+2D8h]
0x180028b5d  test    rcx, rcx
0x180028b60  jz      short loc_180028B75
0x180028b62  mov     rax, [rcx]
0x180028b65  mov     rax, [rax+10h]
0x180028b69  call    _guard_dispatch_icall
0x180028b6e  mov     [rsi+2D8h], r14
0x180028b75  mov     rcx, [rsi+2D0h]
0x180028b7c  test    rcx, rcx
0x180028b7f  jz      short loc_180028B94
0x180028b81  mov     rax, [rcx]
0x180028b84  mov     rax, [rax+10h]
0x180028b88  call    _guard_dispatch_icall
0x180028b8d  mov     [rsi+2D0h], r14
0x180028b94  mov     rcx, [rsi+2C8h]
0x180028b9b  test    rcx, rcx
0x180028b9e  jz      short loc_180028BB3
0x180028ba0  mov     rax, [rcx]
0x180028ba3  mov     rax, [rax+10h]
0x180028ba7  call    _guard_dispatch_icall
0x180028bac  mov     [rsi+2C8h], r14
0x180028bb3  mov     rcx, [rsi+2C0h]
0x180028bba  test    rcx, rcx
0x180028bbd  jz      short loc_180028BD2
0x180028bbf  mov     rax, [rcx]
0x180028bc2  mov     rax, [rax+10h]
0x180028bc6  call    _guard_dispatch_icall
0x180028bcb  mov     [rsi+2C0h], r14
0x180028bd2  mov     rcx, [rsi+2B8h]; void *
0x180028bd9  test    rcx, rcx
0x180028bdc  jz      short loc_180028BEA
0x180028bde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028be3  mov     [rsi+2B8h], r14
0x180028bea  mov     rcx, [rsi+2A8h]; lpMem
0x180028bf1  test    rcx, rcx
0x180028bf4  jz      short loc_180028C02
0x180028bf6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180028bfb  mov     [rsi+2A8h], r14
0x180028c02  lea     rcx, [rsi+280h]
0x180028c09  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@UtagDPProcessedUpdate@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpNoop@UtagDPProcessedUpdate@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::_tagMapEntry,CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::_tagMapEntry,CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::CMapEntryOps>(void)
0x180028c0e  lea     rcx, [rsi+30h]; this
0x180028c12  lea     r11, [rsp+0A8h+var_18]
0x180028c1a  mov     rbx, [r11+28h]
0x180028c1e  mov     rbp, [r11+30h]
0x180028c22  mov     rsp, r11
0x180028c25  pop     r14
0x180028c27  pop     rdi
0x180028c28  pop     rsi
0x180028c29  jmp     ??1CUHHandlerManager@@UEAA@XZ; CUHHandlerManager::~CUHHandlerManager(void)
```
