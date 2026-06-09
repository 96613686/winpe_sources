# CTieringEngineTaskHandler::~CTieringEngineTaskHandler(void)

- ea: `0x140002ac8`
- end: `0x140002b45`
- name: `??1CTieringEngineTaskHandler@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CTieringEngineTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140002924`
- `0x140002a14`

## callees

- `0x140002ac8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002b39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002b39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140002ada`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140002ae9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140002ada`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140002ae9`

## pseudocode

```c
void __fastcall CTieringEngineTaskHandler::~CTieringEngineTaskHandler(CTieringEngineTaskHandler *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WORK *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 13);
  if ( v2 )
    CloseThreadpoolWork(v2);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 12);
  if ( v3 )
    CloseThreadpoolWork(v3);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 9);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 )
    CloseHandle(v7);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x140002ac8  push    rbx
0x140002aca  sub     rsp, 20h
0x140002ace  mov     rbx, rcx
0x140002ad1  mov     rcx, [rcx+68h]; pwk
0x140002ad5  test    rcx, rcx
0x140002ad8  jz      short loc_140002AE0
0x140002ada  call    cs:__imp_CloseThreadpoolWork
0x140002ae0  mov     rcx, [rbx+60h]; pwk
0x140002ae4  test    rcx, rcx
0x140002ae7  jz      short loc_140002AEF
0x140002ae9  call    cs:__imp_CloseThreadpoolWork
0x140002aef  mov     rcx, [rbx+58h]; hObject
0x140002af3  test    rcx, rcx
0x140002af6  jz      short loc_140002AFE
0x140002af8  call    cs:__imp_CloseHandle
0x140002afe  mov     rcx, [rbx+50h]; hObject
0x140002b02  test    rcx, rcx
0x140002b05  jz      short loc_140002B0D
0x140002b07  call    cs:__imp_CloseHandle
0x140002b0d  mov     rcx, [rbx+48h]; hObject
0x140002b11  test    rcx, rcx
0x140002b14  jz      short loc_140002B1C
0x140002b16  call    cs:__imp_CloseHandle
0x140002b1c  mov     rcx, [rbx+40h]; hObject
0x140002b20  test    rcx, rcx
0x140002b23  jz      short loc_140002B2B
0x140002b25  call    cs:__imp_CloseHandle
0x140002b2b  lea     rcx, [rbx+10h]; lpCriticalSection
0x140002b2f  cmp     byte ptr [rcx+28h], 0
0x140002b33  jz      short loc_140002B3F
0x140002b35  mov     byte ptr [rcx+28h], 0
0x140002b39  call    cs:__imp_DeleteCriticalSection
0x140002b3f  add     rsp, 20h
0x140002b43  pop     rbx
0x140002b44  retn
```
