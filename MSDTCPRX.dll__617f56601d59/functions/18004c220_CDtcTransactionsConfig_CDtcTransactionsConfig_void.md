# CDtcTransactionsConfig::~CDtcTransactionsConfig(void)

- ea: `0x18004c220`
- end: `0x18004c29f`
- name: `??1CDtcTransactionsConfig@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(CDtcTransactionsConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d460`

## callees

- `0x180017f04`
- `0x18004c220`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c251`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c292`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c260`

## pseudocode

```c
void __fastcall CDtcTransactionsConfig::~CDtcTransactionsConfig(CDtcTransactionsConfig *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CDtcTransactionsConfig::`vftable'{for `IColdConnectSink'};
  *((_QWORD *)this + 1) = &CDtcTransactionsConfig::`vftable'{for `ISendReceiveSink'};
  CDtcTransactionsConfig::ReleaseConnection(this);
  CoTaskMemFree(*((LPVOID *)this + 8));
  CoTaskMemFree(*((LPVOID *)this + 9));
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  *((_QWORD *)this + 10) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x18004c220  push    rbx
0x18004c222  sub     rsp, 20h
0x18004c226  mov     rbx, rcx
0x18004c229  lea     rax, ??_7CDtcTransactionsConfig@@6BIColdConnectSink@@@; const CDtcTransactionsConfig::`vftable'{for `IColdConnectSink'}
0x18004c230  mov     [rcx], rax
0x18004c233  lea     rax, ??_7CDtcTransactionsConfig@@6BISendReceiveSink@@@; const CDtcTransactionsConfig::`vftable'{for `ISendReceiveSink'}
0x18004c23a  mov     [rcx+8], rax
0x18004c23e  call    ?ReleaseConnection@CDtcTransactionsConfig@@AEAAJXZ; CDtcTransactionsConfig::ReleaseConnection(void)
0x18004c243  mov     rcx, [rbx+40h]; pv
0x18004c247  call    cs:__imp_CoTaskMemFree
0x18004c24d  mov     rcx, [rbx+48h]; pv
0x18004c251  call    cs:__imp_CoTaskMemFree
0x18004c257  mov     rcx, [rbx+38h]; hObject
0x18004c25b  test    rcx, rcx
0x18004c25e  jz      short loc_18004C266
0x18004c260  call    cs:__imp_CloseHandle
0x18004c266  mov     rcx, [rbx+18h]
0x18004c26a  test    rcx, rcx
0x18004c26d  jz      short loc_18004C283
0x18004c26f  mov     rax, [rcx]
0x18004c272  mov     rax, [rax+10h]
0x18004c276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c27b  mov     qword ptr [rbx+18h], 0
0x18004c283  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18004c28a  mov     [rbx+50h], rax
0x18004c28e  lea     rcx, [rbx+58h]; lpCriticalSection
0x18004c292  call    cs:__imp_DeleteCriticalSection
0x18004c298  nop
0x18004c299  add     rsp, 20h
0x18004c29d  pop     rbx
0x18004c29e  retn
```
