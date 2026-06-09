# NgcUtils::ProcessPriorityManager::SetProcessPriorityForDuration(ulong,ulong)

- ea: `0x1800207b4`
- end: `0x1800208a9`
- name: `?SetProcessPriorityForDuration@ProcessPriorityManager@NgcUtils@@QEAAJKK@Z`
- size: `245`
- prototype: `__int64 __fastcall(NgcUtils::ProcessPriorityManager *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019a00`
- `0x180020530`

## callees

- `0x180016888`
- `0x1800207b4`
- `0x180022e68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020869`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020869`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800207d8`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800207d8`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020825`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800207c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800207c6`

## string_xrefs

- `0x18002083a`: `onecore\ds\security\ngc\utils\common\lib\processutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::ProcessPriorityManager::SetProcessPriorityForDuration(
        NgcUtils::ProcessPriorityManager *this)
{
  HANDLE CurrentProcess; // rsi
  DWORD PriorityClass; // edi
  const char *v5; // r9
  struct _TP_TIMER *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  CurrentProcess = GetCurrentProcess();
  PriorityClass = GetPriorityClass(CurrentProcess);
  if ( !PriorityClass )
  {
    if ( (unsigned int)dword_1800BE0B8 > 3 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AE1BD,
        0);
    PriorityClass = 32;
  }
  if ( *(_BYTE *)this )
    return 2147947423LL;
  if ( !SetPriorityClass(CurrentProcess, 0x8000u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4C,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\processutils.cpp",
             v5);
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 1);
  *(_BYTE *)this = 1;
  *((_DWORD *)this + 1) = PriorityClass;
  pftDueTime = (_FILETIME)-300000000LL;
  SetThreadpoolTimer(v6, &pftDueTime, 0, 0);
  if ( (unsigned int)dword_1800BE0B8 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AE1E5,
      0);
  return 0;
}

```

## disassembly

```asm
0x1800207b4  mov     [rsp+arg_8], rbx
0x1800207b9  mov     [rsp+arg_10], rsi
0x1800207be  push    rdi
0x1800207bf  sub     rsp, 20h
0x1800207c3  mov     rbx, rcx
0x1800207c6  call    cs:__imp_GetCurrentProcess
0x1800207cd  nop     dword ptr [rax+rax+00h]
0x1800207d2  mov     rcx, rax; hProcess
0x1800207d5  mov     rsi, rax
0x1800207d8  call    cs:__imp_GetPriorityClass
0x1800207df  nop     dword ptr [rax+rax+00h]
0x1800207e4  mov     edi, eax
0x1800207e6  test    eax, eax
0x1800207e8  jnz     short loc_180020810
0x1800207ea  mov     edx, cs:dword_1800BE0B8
0x1800207f0  cmp     edx, 3
0x1800207f3  jbe     short loc_18002080B
0x1800207f5  xor     r8d, r8d
0x1800207f8  lea     rdx, byte_1800AE1BD
0x1800207ff  lea     rcx, dword_1800BE0B8
0x180020806  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002080b  mov     edi, 20h ; ' '
0x180020810  mov     al, [rbx]
0x180020812  test    al, al
0x180020814  jz      short loc_18002081D
0x180020816  mov     eax, 8007139Fh
0x18002081b  jmp     short loc_180020898
0x18002081d  mov     edx, 8000h; dwPriorityClass
0x180020822  mov     rcx, rsi; hProcess
0x180020825  call    cs:__imp_SetPriorityClass
0x18002082c  nop     dword ptr [rax+rax+00h]
0x180020831  test    eax, eax
0x180020833  jnz     short loc_18002084B
0x180020835  mov     rcx, [rsp+28h]; this
0x18002083a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180020841  lea     edx, [rax+4Ch]; void *
0x180020844  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020849  jmp     short loc_180020898
0x18002084b  mov     rcx, [rbx+8]; pti
0x18002084f  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180020854  xor     r9d, r9d; msWindowLength
0x180020857  mov     byte ptr [rbx], 1
0x18002085a  xor     r8d, r8d; msPeriod
0x18002085d  mov     [rbx+4], edi
0x180020860  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180020869  call    cs:__imp_SetThreadpoolTimer
0x180020870  nop     dword ptr [rax+rax+00h]
0x180020875  mov     eax, cs:dword_1800BE0B8
0x18002087b  cmp     eax, 4
0x18002087e  jbe     short loc_180020896
0x180020880  xor     r8d, r8d
0x180020883  lea     rdx, byte_1800AE1E5
0x18002088a  lea     rcx, dword_1800BE0B8
0x180020891  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180020896  xor     eax, eax
0x180020898  mov     rbx, [rsp+28h+arg_8]
0x18002089d  mov     rsi, [rsp+28h+arg_10]
0x1800208a2  add     rsp, 20h
0x1800208a6  pop     rdi
0x1800208a7  retn
```
