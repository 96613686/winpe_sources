# Enqueue_ObjectDestruction(WmiThread<ulong> *)

- ea: `0x14001ec18`
- end: `0x14001ee0d`
- name: `?Enqueue_ObjectDestruction@@YAJPEAV?$WmiThread@K@@@Z`
- size: `501`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x14000a530`
- `0x14001ec18`
- `0x14001ee14`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001ece4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001ece4`
- `wbemcomn!GetMemLogObject` at `0x14001ecf6`
- `wbemcomn!GetMemLogObject` at `0x14001ecf6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001ed01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001ed01`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Enqueue_ObjectDestruction(struct Task_FreeLibraries *a1)
{
  struct FactoryLifeTimeThread *v1; // r14
  struct Task_ObjectDestruction *v2; // rax
  struct Task_ObjectDestruction *v3; // rbx
  unsigned int v4; // ebx
  signed int v5; // edi
  CMemoryLog *MemLogObject; // rax
  struct Task_FreeLibraries *v8; // rax
  struct Task_FreeLibraries *v9; // rsi
  struct Task_FreeLibraries *v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = a1;
  v1 = g_Thread;
  v2 = (struct Task_ObjectDestruction *)operator new(0x48u);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    WmiTask<unsigned long>::WmiTask<unsigned long>((__int64)v2, (__int64)ProviderSubSystem_Globals::s_Allocator);
    *(_QWORD *)v3 = &Task_ObjectDestruction::`vftable';
  }
  else
  {
    v3 = 0;
  }
  g_Task = v3;
  if ( !v3 )
  {
    v4 = -2147217402;
    v5 = -2147217402;
LABEL_7:
    g_Task = 0;
    goto LABEL_8;
  }
  (*(void (__fastcall **)(struct Task_ObjectDestruction *))(*(_QWORD *)v3 + 8LL))(v3);
  if ( (*(unsigned int (__fastcall **)(struct Task_ObjectDestruction *))(*(_QWORD *)g_Task + 24LL))(g_Task) )
  {
    v4 = -2147217402;
    v5 = -2147217402;
  }
  else
  {
    LODWORD(v10) = 0;
    v4 = -2147217402;
    v5 = (*(unsigned int (__fastcall **)(struct FactoryLifeTimeThread *, struct Task_FreeLibraries **, struct Task_ObjectDestruction *))(*(_QWORD *)v1 + 104LL))(
           v1,
           &v10,
           g_Task) != 0
       ? 0x80041006
       : 0;
  }
  if ( v5 < 0 )
    goto LABEL_7;
  v8 = (struct Task_FreeLibraries *)operator new(0x48u);
  v9 = v8;
  v10 = v8;
  if ( v8 )
  {
    WmiTask<unsigned long>::WmiTask<unsigned long>((__int64)v8, (__int64)ProviderSubSystem_Globals::s_Allocator);
    *(_QWORD *)v9 = &Task_FreeLibraries::`vftable';
  }
  else
  {
    v9 = 0;
  }
  g_TaskFreeLib = v9;
  if ( !v9
    || ((*(void (__fastcall **)(struct Task_FreeLibraries *))(*(_QWORD *)v9 + 8LL))(v9),
        (*(unsigned int (__fastcall **)(struct Task_FreeLibraries *))(*(_QWORD *)g_TaskFreeLib + 24LL))(g_TaskFreeLib))
    || (LODWORD(v10) = 0,
        (*(unsigned int (__fastcall **)(struct FactoryLifeTimeThread *, struct Task_FreeLibraries **, struct Task_FreeLibraries *))(*(_QWORD *)v1 + 104LL))(
          v1,
          &v10,
          g_TaskFreeLib)) )
  {
    v5 = -2147217402;
  }
LABEL_8:
  g_ShutdownEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_ShutdownEvent || (v4 = v5, v5 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001ec18  mov     [rsp+arg_0], rcx
0x14001ec1d  push    rbx
0x14001ec1e  push    rsi
0x14001ec1f  push    rdi
0x14001ec20  push    r14
0x14001ec22  sub     rsp, 28h
0x14001ec26  mov     r14, cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA; FactoryLifeTimeThread * g_Thread
0x14001ec2d  mov     esi, 48h ; 'H'
0x14001ec32  mov     ecx, esi; dwBytes
0x14001ec34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ec39  mov     rbx, rax
0x14001ec3c  mov     [rsp+48h+arg_0], rax
0x14001ec41  test    rax, rax
0x14001ec44  jz      loc_14001ED39
0x14001ec4a  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14001ec51  mov     rcx, rax
0x14001ec54  call    ??0?$WmiTask@K@@QEAA@AEAVWmiAllocator@@PEBG1@Z; WmiTask<ulong>::WmiTask<ulong>(WmiAllocator &,ushort const *,ushort const *)
0x14001ec59  lea     rax, ??_7Task_ObjectDestruction@@6B@; const Task_ObjectDestruction::`vftable'
0x14001ec60  mov     [rbx], rax
0x14001ec63  mov     cs:?g_Task@@3PEAVTask_ObjectDestruction@@EA, rbx; Task_ObjectDestruction * g_Task
0x14001ec6a  test    rbx, rbx
0x14001ec6d  jz      loc_14001ED30
0x14001ec73  mov     rax, [rbx]
0x14001ec76  mov     rcx, rbx
0x14001ec79  mov     rax, [rax+8]
0x14001ec7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ec82  mov     rcx, cs:?g_Task@@3PEAVTask_ObjectDestruction@@EA; Task_ObjectDestruction * g_Task
0x14001ec89  mov     rax, [rcx]
0x14001ec8c  mov     rax, [rax+18h]
0x14001ec90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ec95  test    eax, eax
0x14001ec97  jnz     loc_14001ED40
0x14001ec9d  mov     dword ptr [rsp+48h+arg_0], eax
0x14001eca1  mov     rax, [r14]
0x14001eca4  mov     r8, cs:?g_Task@@3PEAVTask_ObjectDestruction@@EA; Task_ObjectDestruction * g_Task
0x14001ecab  lea     rdx, [rsp+48h+arg_0]
0x14001ecb0  mov     rcx, r14
0x14001ecb3  mov     rax, [rax+68h]
0x14001ecb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ecbc  neg     eax
0x14001ecbe  sbb     edi, edi
0x14001ecc0  mov     ebx, 80041006h
0x14001ecc5  and     edi, ebx
0x14001ecc7  test    edi, edi
0x14001ecc9  jns     loc_14001ED54
0x14001eccf  mov     cs:?g_Task@@3PEAVTask_ObjectDestruction@@EA, 0; Task_ObjectDestruction * g_Task
0x14001ecda  xor     r9d, r9d; lpName
0x14001ecdd  xor     r8d, r8d; bInitialState
0x14001ece0  xor     edx, edx; bManualReset
0x14001ece2  xor     ecx, ecx; lpEventAttributes
0x14001ece4  call    cs:__imp_CreateEventW
0x14001ecea  mov     cs:?g_ShutdownEvent@@3PEAXEA, rax; void * g_ShutdownEvent
0x14001ecf1  test    rax, rax
0x14001ecf4  jnz     short loc_14001ED4C
0x14001ecf6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001ecfc  mov     edx, ebx
0x14001ecfe  mov     rcx, rax
0x14001ed01  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001ed07  lea     rax, WPP_GLOBAL_Control
0x14001ed0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ed15  cmp     rcx, rax
0x14001ed18  jz      short loc_14001ED24
0x14001ed1a  test    byte ptr [rcx+1Ch], 4
0x14001ed1e  jnz     loc_14001EDE6
0x14001ed24  mov     eax, ebx
0x14001ed26  add     rsp, 28h
0x14001ed2a  pop     r14
0x14001ed2c  pop     rdi
0x14001ed2d  pop     rsi
0x14001ed2e  pop     rbx
0x14001ed2f  retn
0x14001ed30  mov     ebx, 80041006h
0x14001ed35  mov     edi, ebx
0x14001ed37  jmp     short loc_14001ECCF
0x14001ed39  xor     ebx, ebx
0x14001ed3b  jmp     loc_14001EC63
0x14001ed40  mov     ebx, 80041006h
0x14001ed45  mov     edi, ebx
0x14001ed47  jmp     loc_14001ECC7
0x14001ed4c  mov     ebx, edi
0x14001ed4e  test    edi, edi
0x14001ed50  jns     short loc_14001ED07
0x14001ed52  jmp     short loc_14001ECF6
0x14001ed54  mov     rcx, rsi; dwBytes
0x14001ed57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ed5c  mov     rsi, rax
0x14001ed5f  mov     [rsp+48h+arg_0], rax
0x14001ed64  test    rax, rax
0x14001ed67  jz      short loc_14001EDE2
0x14001ed69  mov     rdx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14001ed70  mov     rcx, rax
0x14001ed73  call    ??0?$WmiTask@K@@QEAA@AEAVWmiAllocator@@PEBG1@Z; WmiTask<ulong>::WmiTask<ulong>(WmiAllocator &,ushort const *,ushort const *)
0x14001ed78  lea     rax, ??_7Task_FreeLibraries@@6B@; const Task_FreeLibraries::`vftable'
0x14001ed7f  mov     [rsi], rax
0x14001ed82  mov     cs:?g_TaskFreeLib@@3PEAVTask_FreeLibraries@@EA, rsi; Task_FreeLibraries * g_TaskFreeLib
0x14001ed89  test    rsi, rsi
0x14001ed8c  jz      short loc_14001EDDB
0x14001ed8e  mov     rax, [rsi]
0x14001ed91  mov     rcx, rsi
0x14001ed94  mov     rax, [rax+8]
0x14001ed98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ed9d  mov     rcx, cs:?g_TaskFreeLib@@3PEAVTask_FreeLibraries@@EA; Task_FreeLibraries * g_TaskFreeLib
0x14001eda4  mov     rax, [rcx]
0x14001eda7  mov     rax, [rax+18h]
0x14001edab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001edb0  test    eax, eax
0x14001edb2  jnz     short loc_14001EDDB
0x14001edb4  mov     dword ptr [rsp+48h+arg_0], eax
0x14001edb8  mov     rax, [r14]
0x14001edbb  mov     r8, cs:?g_TaskFreeLib@@3PEAVTask_FreeLibraries@@EA; Task_FreeLibraries * g_TaskFreeLib
0x14001edc2  lea     rdx, [rsp+48h+arg_0]
0x14001edc7  mov     rcx, r14
0x14001edca  mov     rax, [rax+68h]
0x14001edce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001edd3  test    eax, eax
0x14001edd5  jz      loc_14001ECDA
0x14001eddb  mov     edi, ebx
0x14001eddd  jmp     loc_14001ECDA
0x14001ede2  xor     esi, esi
0x14001ede4  jmp     short loc_14001ED82
0x14001ede6  cmp     byte ptr [rcx+19h], 2
0x14001edea  jb      loc_14001ED24
0x14001edf0  mov     edx, 17h
0x14001edf5  mov     r9d, ebx
0x14001edf8  lea     r8, WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids
0x14001edff  mov     rcx, [rcx+10h]
0x14001ee03  call    WPP_SF_d
0x14001ee08  jmp     loc_14001ED24
```
