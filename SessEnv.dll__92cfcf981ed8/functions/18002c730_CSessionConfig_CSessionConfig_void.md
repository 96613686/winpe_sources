# CSessionConfig::~CSessionConfig(void)

- ea: `0x18002c730`
- end: `0x18002c824`
- name: `??1CSessionConfig@@UEAA@XZ`
- size: `244`
- prototype: `void __fastcall(CSessionConfig *this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002c830`

## callees

- `0x180001a24`
- `0x1800219b8`
- `0x18002c730`
- `0x18002c868`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c78f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c7e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c78f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c7e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c753`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c753`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c778`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c778`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002c782`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002c782`

## pseudocode

```c
void __fastcall CSessionConfig::~CSessionConfig(CSessionConfig *this, unsigned int a2)
{
  void *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  unsigned __int64 i; // rdi
  CSessionConfigTaskThread *v7; // rcx
  void *v8; // rcx

  *(_QWORD *)this = &CSessionConfig::`vftable';
  v3 = (void *)*((_QWORD *)this + 199);
  if ( v3 )
  {
    SetEvent(v3);
    v4 = *((_QWORD *)this + 199);
  }
  else
  {
    v4 = 0;
  }
  v5 = (void *)*((_QWORD *)this + 200);
  if ( v5 )
  {
    if ( v4 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    else
      TerminateThread(v5, 0);
    CloseHandle(*((HANDLE *)this + 200));
    *((_QWORD *)this + 200) = 0;
  }
  for ( i = 0; i < *((_QWORD *)this + 203); ++i )
  {
    v7 = *(CSessionConfigTaskThread **)(*((_QWORD *)this + 202) + 8 * i);
    if ( v7 )
    {
      CSessionConfigTaskThread::`scalar deleting destructor'(v7, a2);
      *(_QWORD *)(*((_QWORD *)this + 202) + 8 * i) = 0;
    }
  }
  v8 = (void *)*((_QWORD *)this + 199);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 199) = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_180084288);
  *(_QWORD *)this = &CTSPrivateObject<IWLNotificationSubscriber>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x18002c730  mov     [rsp+arg_0], rbx
0x18002c735  push    rdi
0x18002c736  sub     rsp, 20h
0x18002c73a  lea     rax, ??_7CSessionConfig@@6B@; const CSessionConfig::`vftable'
0x18002c741  mov     rbx, rcx
0x18002c744  mov     [rcx], rax
0x18002c747  mov     rcx, [rcx+638h]; hEvent
0x18002c74e  test    rcx, rcx
0x18002c751  jz      short loc_18002C762
0x18002c753  call    cs:__imp_SetEvent
0x18002c759  mov     rax, [rbx+638h]
0x18002c760  jmp     short loc_18002C764
0x18002c762  xor     eax, eax
0x18002c764  mov     rcx, [rbx+640h]; hThread
0x18002c76b  test    rcx, rcx
0x18002c76e  jz      short loc_18002C7A0
0x18002c770  test    rax, rax
0x18002c773  jz      short loc_18002C780
0x18002c775  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c778  call    cs:__imp_WaitForSingleObject
0x18002c77e  jmp     short loc_18002C788
0x18002c780  xor     edx, edx; dwExitCode
0x18002c782  call    cs:__imp_TerminateThread
0x18002c788  mov     rcx, [rbx+640h]; hObject
0x18002c78f  call    cs:__imp_CloseHandle
0x18002c795  mov     qword ptr [rbx+640h], 0
0x18002c7a0  xor     edi, edi
0x18002c7a2  cmp     [rbx+658h], rdi
0x18002c7a9  jbe     short loc_18002C7DB
0x18002c7ab  mov     rax, [rbx+650h]
0x18002c7b2  mov     rcx, [rax+rdi*8]; this
0x18002c7b6  test    rcx, rcx
0x18002c7b9  jz      short loc_18002C7CF
0x18002c7bb  call    ??_GCSessionConfigTaskThread@@QEAAPEAXI@Z; CSessionConfigTaskThread::`scalar deleting destructor'(uint)
0x18002c7c0  mov     rax, [rbx+650h]
0x18002c7c7  mov     qword ptr [rax+rdi*8], 0
0x18002c7cf  inc     rdi
0x18002c7d2  cmp     rdi, [rbx+658h]
0x18002c7d9  jb      short loc_18002C7AB
0x18002c7db  mov     rcx, [rbx+638h]; hObject
0x18002c7e2  test    rcx, rcx
0x18002c7e5  jz      short loc_18002C7F8
0x18002c7e7  call    cs:__imp_CloseHandle
0x18002c7ed  mov     qword ptr [rbx+638h], 0
0x18002c7f8  lea     rcx, dword_180084288
0x18002c7ff  call    TraceLoggingUnregister_EventUnregister
0x18002c804  lea     rax, ??_7?$CTSPrivateObject@VIWLNotificationSubscriber@@@@6B@; const CTSPrivateObject<IWLNotificationSubscriber>::`vftable'
0x18002c80b  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x18002c812  mov     [rbx], rax
0x18002c815  mov     rbx, [rsp+28h+arg_0]
0x18002c81a  add     rsp, 20h
0x18002c81e  pop     rdi
0x18002c81f  jmp     ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
```
