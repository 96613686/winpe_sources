# DriverInitialize

- ea: `0x140008100`
- end: `0x14000831a`
- name: `DriverInitialize`
- size: `538`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140027078`

## callees

- `0x140005704`
- `0x140008100`
- `0x140008428`
- `0x14000848c`
- `0x1400129b4`
- `0x140012acc`
- `0x140014000`
- `0x140024008`
- `0x14002438c`
- `0x14002709c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x140008193`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400081c6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400081f9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000822c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140008193`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400081c6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400081f9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000822c`
- `FLTMGR!FltStartFiltering` at `0x1400082b9`
- `FLTMGR!FltStartFiltering` at `0x1400082b9`
- `FLTMGR!FltRegisterFilter` at `0x14000829c`
- `FLTMGR!FltRegisterFilter` at `0x14000829c`

## pseudocode

```c
__int64 __fastcall DriverInitialize(PDRIVER_OBJECT DriverObject)
{
  __int64 v2; // rdx
  NTSTATUS ControlDevice; // ebx

  LogInitialize();
  McGenEventRegister_EtwRegister(
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS,
    v2,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
  memset(&VfsData, 0, 0x740u);
  VfsInitializeLookasideLists(&stru_14001F500);
  PrefixTreeContext::referenceCallback = (void (*)(void *))VfsPrefixTreeReferenceMapping;
  PrefixTreeContext::releaseCallback = (void (*)(void *))VfsPrefixTreeReleaseMapping;
  ExInitializePagedLookasideList(&PrefixTreeAllocator::PrefixTreeLookasideList, 0, 0, 0, 0x10u, 0x31704656u, 0);
  ExInitializePagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, 0, 0, 0, 0x68u, 0x32704656u, 0);
  ExInitializePagedLookasideList(&PrefixTreeAllocator::PrefixEntryLookasideList, 0, 0, 0, 0xD0u, 0x33704656u, 0);
  ExInitializePagedLookasideList(
    &PrefixTreeAllocator::PrefixShortNameEntryLookasideList,
    0,
    0,
    0,
    0x50u,
    0x34704656u,
    0);
  PrefixTreeAllocator::LookasideInited = 1;
  ControlDevice = VfsCtxTableInitialize(&Table);
  if ( ControlDevice >= 0 )
  {
    ControlDevice = VfsCtxTableInitialize(&stru_14001F470);
    if ( ControlDevice >= 0 )
    {
      ControlDevice = VfsCreateControlDevice(DriverObject);
      if ( ControlDevice >= 0 )
      {
        ControlDevice = FltRegisterFilter(DriverObject, &FilterRegistration, &VfsData);
        if ( ControlDevice >= 0 )
        {
          ControlDevice = FltStartFiltering(VfsData);
          if ( ControlDevice >= 0 )
            DriverObject->DriverUnload = 0;
        }
      }
    }
  }
  if ( ControlDevice >= 0 )
  {
    LogWrite(3, 0, L"DriverInitialize() - VFS filter load succeeded");
  }
  else
  {
    VfsDriverCleanup();
    LogWrite(1, 0, L"DriverInitialize() - VFS failed to load filter, Status: 0x%08X", (unsigned int)ControlDevice);
    LogUninitialize();
  }
  return (unsigned int)ControlDevice;
}

```

## disassembly

```asm
0x140008100  mov     [rsp+arg_0], rbx
0x140008105  push    rdi
0x140008106  sub     rsp, 50h
0x14000810a  mov     rdi, rcx
0x14000810d  mov     [rsp+58h+var_18], 0
0x140008115  call    LogInitialize
0x14000811a  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140008121  mov     r9, r8
0x140008124  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS
0x14000812b  call    McGenEventRegister_EtwRegister
0x140008130  xor     edx, edx; Val
0x140008132  mov     r8d, 740h; Size
0x140008138  lea     rcx, VfsData; void *
0x14000813f  call    memset
0x140008144  lea     rcx, stru_14001F500
0x14000814b  call    VfsInitializeLookasideLists
0x140008150  lea     rax, VfsPrefixTreeReferenceMapping
0x140008157  mov     cs:?referenceCallback@PrefixTreeContext@@2P6AXPEAX@ZEA, rax; void (*PrefixTreeContext::referenceCallback)(void *)
0x14000815e  lea     rax, VfsPrefixTreeReleaseMapping
0x140008165  mov     cs:?releaseCallback@PrefixTreeContext@@2P6AXPEAX@ZEA, rax; void (*PrefixTreeContext::releaseCallback)(void *)
0x14000816c  xor     eax, eax
0x14000816e  mov     [rsp+58h+Depth], ax; Depth
0x140008173  mov     [rsp+58h+Tag], 31704656h; Tag
0x14000817b  mov     [rsp+58h+Size], 10h; Size
0x140008184  xor     r9d, r9d; Flags
0x140008187  xor     r8d, r8d; Free
0x14000818a  xor     edx, edx; Allocate
0x14000818c  lea     rcx, ?PrefixTreeLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140008193  call    cs:__imp_ExInitializePagedLookasideList
0x14000819a  nop     dword ptr [rax+rax+00h]
0x14000819f  xor     eax, eax
0x1400081a1  mov     [rsp+58h+Depth], ax; Depth
0x1400081a6  mov     [rsp+58h+Tag], 32704656h; Tag
0x1400081ae  mov     [rsp+58h+Size], 68h ; 'h'; Size
0x1400081b7  xor     r9d, r9d; Flags
0x1400081ba  xor     r8d, r8d; Free
0x1400081bd  xor     edx, edx; Allocate
0x1400081bf  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400081c6  call    cs:__imp_ExInitializePagedLookasideList
0x1400081cd  nop     dword ptr [rax+rax+00h]
0x1400081d2  xor     eax, eax
0x1400081d4  mov     [rsp+58h+Depth], ax; Depth
0x1400081d9  mov     [rsp+58h+Tag], 33704656h; Tag
0x1400081e1  mov     [rsp+58h+Size], 0D0h; Size
0x1400081ea  xor     r9d, r9d; Flags
0x1400081ed  xor     r8d, r8d; Free
0x1400081f0  xor     edx, edx; Allocate
0x1400081f2  lea     rcx, ?PrefixEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400081f9  call    cs:__imp_ExInitializePagedLookasideList
0x140008200  nop     dword ptr [rax+rax+00h]
0x140008205  xor     eax, eax
0x140008207  mov     [rsp+58h+Depth], ax; Depth
0x14000820c  mov     [rsp+58h+Tag], 34704656h; Tag
0x140008214  mov     [rsp+58h+Size], 50h ; 'P'; Size
0x14000821d  xor     r9d, r9d; Flags
0x140008220  xor     r8d, r8d; Free
0x140008223  xor     edx, edx; Allocate
0x140008225  lea     rcx, ?PrefixShortNameEntryLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14000822c  call    cs:__imp_ExInitializePagedLookasideList
0x140008233  nop     dword ptr [rax+rax+00h]
0x140008238  mov     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 1; bool PrefixTreeAllocator::LookasideInited
0x14000823f  xor     edx, edx
0x140008241  lea     r8d, [rdx+1]
0x140008245  lea     rcx, Table; Table
0x14000824c  call    VfsCtxTableInitialize
0x140008251  mov     ebx, eax
0x140008253  mov     [rsp+58h+var_18], eax
0x140008257  test    eax, eax
0x140008259  js      short loc_1400082D7
0x14000825b  mov     edx, 1
0x140008260  mov     r8d, edx
0x140008263  lea     rcx, stru_14001F470; Table
0x14000826a  call    VfsCtxTableInitialize
0x14000826f  mov     ebx, eax
0x140008271  mov     [rsp+58h+var_18], eax
0x140008275  test    eax, eax
0x140008277  js      short loc_1400082D7
0x140008279  mov     rcx, rdi; DriverObject
0x14000827c  call    VfsCreateControlDevice
0x140008281  mov     ebx, eax
0x140008283  mov     [rsp+58h+var_18], eax
0x140008287  test    eax, eax
0x140008289  js      short loc_1400082D7
0x14000828b  lea     r8, VfsData; RetFilter
0x140008292  lea     rdx, FilterRegistration; Registration
0x140008299  mov     rcx, rdi; Driver
0x14000829c  call    cs:__imp_FltRegisterFilter
0x1400082a3  nop     dword ptr [rax+rax+00h]
0x1400082a8  mov     ebx, eax
0x1400082aa  mov     [rsp+58h+var_18], eax
0x1400082ae  test    eax, eax
0x1400082b0  js      short loc_1400082D7
0x1400082b2  mov     rcx, cs:VfsData; Filter
0x1400082b9  call    cs:__imp_FltStartFiltering
0x1400082c0  nop     dword ptr [rax+rax+00h]
0x1400082c5  mov     ebx, eax
0x1400082c7  mov     [rsp+58h+var_18], eax
0x1400082cb  test    eax, eax
0x1400082cd  js      short loc_1400082D7
0x1400082cf  mov     qword ptr [rdi+68h], 0
0x1400082d7  test    ebx, ebx
0x1400082d9  jns     short loc_1400082FB
0x1400082db  call    VfsDriverCleanup
0x1400082e0  mov     r9d, ebx
0x1400082e3  lea     r8, aDriverinitiali_0; "DriverInitialize() - VFS failed to load"...
0x1400082ea  xor     edx, edx
0x1400082ec  lea     ecx, [rdx+1]
0x1400082ef  call    LogWrite
0x1400082f4  call    LogUninitialize
0x1400082f9  jmp     short loc_14000830C
0x1400082fb  lea     r8, aDriverinitiali; "DriverInitialize() - VFS filter load su"...
0x140008302  xor     edx, edx
0x140008304  lea     ecx, [rdx+3]
0x140008307  call    LogWrite
0x14000830c  mov     eax, ebx
0x14000830e  mov     rbx, [rsp+58h+arg_0]
0x140008313  add     rsp, 50h
0x140008317  pop     rdi
0x140008318  retn
0x140014c9e  push    rbx
0x140014ca0  push    rbp
0x140014ca1  sub     rsp, 48h
0x140014ca5  mov     rbp, rdx
0x140014ca8  mov     ebx, [rbp+40h]
0x140014cab  test    ebx, ebx
0x140014cad  jns     short loc_140014CCF
0x140014caf  call    VfsDriverCleanup
0x140014cb4  mov     r9d, ebx
0x140014cb7  lea     r8, aDriverinitiali_0; "DriverInitialize() - VFS failed to load"...
0x140014cbe  xor     edx, edx
0x140014cc0  lea     ecx, [rdx+1]
0x140014cc3  call    LogWrite
0x140014cc8  call    LogUninitialize
0x140014ccd  jmp     short loc_140014CE1
0x140014ccf  lea     r8, aDriverinitiali; "DriverInitialize() - VFS filter load su"...
0x140014cd6  xor     edx, edx
0x140014cd8  lea     ecx, [rdx+3]
0x140014cdb  call    LogWrite
0x140014ce0  nop
0x140014ce1  add     rsp, 48h
0x140014ce5  pop     rbp
0x140014ce6  pop     rbx
0x140014ce7  retn
```
