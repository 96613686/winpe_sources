# details::MakeAsyncWorkerBase::~MakeAsyncWorkerBase(void)

- ea: `0x180007698`
- end: `0x1800076fd`
- name: `??1MakeAsyncWorkerBase@details@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(details::MakeAsyncWorkerBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007cb0`
- `0x180007d20`

## callees

- `0x180007698`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800076b4`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800076b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800076cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800076cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800076f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800076f1`

## pseudocode

```c
void __fastcall details::MakeAsyncWorkerBase::~MakeAsyncWorkerBase(details::MakeAsyncWorkerBase *this)
{
  __int64 v2; // rcx
  HMODULE v3; // rcx
  void *v4; // rcx
  struct _TP_WORK *v5; // rcx

  *(_QWORD *)this = &details::MakeAsyncWorkerBase::`vftable';
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    CoDecrementMTAUsage(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (HMODULE)*((_QWORD *)this + 5);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    CloseHandle(v4);
  v5 = (struct _TP_WORK *)*((_QWORD *)this + 2);
  if ( v5 )
    CloseThreadpoolWork(v5);
}

```

## disassembly

```asm
0x180007698  push    rbx
0x18000769a  sub     rsp, 20h
0x18000769e  lea     rax, ??_7MakeAsyncWorkerBase@details@@6B@; const details::MakeAsyncWorkerBase::`vftable'
0x1800076a5  mov     rbx, rcx
0x1800076a8  mov     [rcx], rax
0x1800076ab  mov     rcx, [rcx+20h]
0x1800076af  test    rcx, rcx
0x1800076b2  jz      short loc_1800076C2
0x1800076b4  call    cs:__imp_CoDecrementMTAUsage
0x1800076ba  mov     qword ptr [rbx+20h], 0
0x1800076c2  mov     rcx, [rbx+28h]; hLibModule
0x1800076c6  test    rcx, rcx
0x1800076c9  jz      short loc_1800076D9
0x1800076cb  call    cs:__imp_FreeLibrary
0x1800076d1  mov     qword ptr [rbx+28h], 0
0x1800076d9  mov     rcx, [rbx+18h]; hObject
0x1800076dd  test    rcx, rcx
0x1800076e0  jz      short loc_1800076E8
0x1800076e2  call    cs:__imp_CloseHandle
0x1800076e8  mov     rcx, [rbx+10h]; pwk
0x1800076ec  test    rcx, rcx
0x1800076ef  jz      short loc_1800076F7
0x1800076f1  call    cs:__imp_CloseThreadpoolWork
0x1800076f7  add     rsp, 20h
0x1800076fb  pop     rbx
0x1800076fc  retn
```
