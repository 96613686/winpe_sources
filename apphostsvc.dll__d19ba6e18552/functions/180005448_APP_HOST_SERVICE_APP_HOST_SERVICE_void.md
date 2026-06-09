# APP_HOST_SERVICE::~APP_HOST_SERVICE(void)

- ea: `0x180005448`
- end: `0x1800054d3`
- name: `??1APP_HOST_SERVICE@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800056d0`

## callees

- `0x1800022c8`
- `0x180002b4c`
- `0x180005448`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005464`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005489`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005489`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::~APP_HOST_SERVICE(APP_HOST_SERVICE *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &APP_HOST_SERVICE::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 2) = 1483960417;
  if ( *((_DWORD *)this + 37) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    *((_DWORD *)this + 37) = 0;
  }
  CONFIG_HISTORY::~CONFIG_HISTORY((APP_HOST_SERVICE *)((char *)this + 472));
  SID_MAPPER::~SID_MAPPER((APP_HOST_SERVICE *)((char *)this + 272));
  *((_DWORD *)this + 36) = 1668246648;
  *((_QWORD *)this + 3) = &MULTI_WORK_QUEUE::`vftable';
  *((_DWORD *)this + 8) = 1483896685;
}

```

## disassembly

```asm
0x180005448  push    rbx
0x18000544a  sub     rsp, 20h
0x18000544e  lea     rax, ??_7APP_HOST_SERVICE@@6B@; const APP_HOST_SERVICE::`vftable'
0x180005455  mov     rbx, rcx
0x180005458  mov     [rcx], rax
0x18000545b  mov     rcx, [rcx+10h]; hObject
0x18000545f  test    rcx, rcx
0x180005462  jz      short loc_180005472
0x180005464  call    cs:__imp_CloseHandle
0x18000546a  mov     qword ptr [rbx+10h], 0
0x180005472  mov     dword ptr [rbx+8], 58737061h
0x180005479  cmp     dword ptr [rbx+94h], 0
0x180005480  jz      short loc_180005499
0x180005482  lea     rcx, [rbx+98h]; lpCriticalSection
0x180005489  call    cs:__imp_DeleteCriticalSection
0x18000548f  mov     dword ptr [rbx+94h], 0
0x180005499  lea     rcx, [rbx+1D8h]; this
0x1800054a0  call    ??1CONFIG_HISTORY@@QEAA@XZ; CONFIG_HISTORY::~CONFIG_HISTORY(void)
0x1800054a5  lea     rcx, [rbx+110h]; this
0x1800054ac  call    ??1SID_MAPPER@@QEAA@XZ; SID_MAPPER::~SID_MAPPER(void)
0x1800054b1  lea     rax, ??_7MULTI_WORK_QUEUE@@6B@; const MULTI_WORK_QUEUE::`vftable'
0x1800054b8  mov     dword ptr [rbx+90h], 636F6C78h
0x1800054c2  mov     [rbx+18h], rax
0x1800054c6  mov     dword ptr [rbx+20h], 5872776Dh
0x1800054cd  add     rsp, 20h
0x1800054d1  pop     rbx
0x1800054d2  retn
```
