# MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)

- ea: `0x180008464`
- end: `0x180008612`
- name: `?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z`
- size: `430`
- prototype: `__int64 __fastcall(MULTI_WORK_QUEUE *__hidden this, struct MULTI_WORK_DISPATCH *, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002680`
- `0x180002e20`
- `0x180003270`
- `0x1800032f0`
- `0x180005704`
- `0x180005f90`
- `0x180006274`
- `0x180008620`

## callees

- `0x180008464`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008537`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800084be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800084be`
- `iisutil!PuDbgPrintError` at `0x1800085c2`
- `iisutil!PuDbgPrintError` at `0x180008601`
- `iisutil!PuDbgPrintError` at `0x1800085c2`
- `iisutil!PuDbgPrintError` at `0x180008601`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000848d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000848d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000851f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000851f`

## string_xrefs

- `0x1800085bb`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_queue.cxx`
- `0x1800085f6`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_queue.cxx`

## pseudocode

```c
__int64 __fastcall MULTI_WORK_QUEUE::GetAndQueueWorkItem(
        MULTI_WORK_QUEUE *this,
        struct MULTI_WORK_DISPATCH *a2,
        __int64 a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rdi
  DWORD TickCount; // eax
  __int64 v9; // rcx
  signed int LastError; // eax

  if ( *((_DWORD *)this + 3) )
  {
    v6 = -2147024726;
LABEL_20:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
        368,
        "MULTI_WORK_QUEUE::GetAndQueueWorkItem",
        v6,
        "Could not get a blank work item\n");
    return v6;
  }
  v7 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler);
  if ( !v7 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
        207,
        "MULTI_WORK_QUEUE::GetBlankWorkItem",
        -2147024888,
        "Allocating WORK_ITEM failed\n");
    v6 = -2147024888;
    goto LABEL_20;
  }
  v7[2] = 0;
  *v7 = &MULTI_WORK_ITEM::`vftable';
  v7[3] = 0;
  TickCount = GetTickCount();
  *((_DWORD *)v7 + 2) = 1414092621;
  *((_DWORD *)v7 + 8) = TickCount;
  v9 = v7[3];
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v7[3] = a2;
  (**(void (__fastcall ***)(struct MULTI_WORK_DISPATCH *))a2)(a2);
  v7[2] = a3;
  if ( *((_DWORD *)this + 3) )
  {
    v6 = -2147024726;
    goto LABEL_15;
  }
  v6 = 0;
  if ( TrySubmitThreadpoolCallback(MultiWorkQueueWorkCallback, v7, (PTP_CALLBACK_ENVIRON)((char *)this + 16)) )
    return v6;
  if ( !GetLastError() )
  {
    v6 = -2147467259;
LABEL_15:
    (*(void (__fastcall **)(_QWORD *, __int64))*v7)(v7, 1);
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_queue.cxx",
        387,
        "MULTI_WORK_QUEUE::GetAndQueueWorkItem",
        v6,
        "Could not queue work item\n");
    return v6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_15;
  return v6;
}

```

## disassembly

```asm
0x180008464  push    rbx
0x180008466  push    rbp
0x180008467  push    rsi
0x180008468  push    rdi
0x180008469  sub     rsp, 38h
0x18000846d  cmp     dword ptr [rcx+0Ch], 0
0x180008471  mov     rbp, r8
0x180008474  mov     rbx, rdx
0x180008477  mov     rsi, rcx
0x18000847a  jz      short loc_180008486
0x18000847c  mov     ebx, 800700AAh
0x180008481  jmp     loc_1800085CD
0x180008486  mov     rcx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000848d  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180008493  mov     [rsp+58h+arg_0], rax
0x180008498  mov     rdi, rax
0x18000849b  test    rax, rax
0x18000849e  jz      loc_18000858A
0x1800084a4  lea     rax, ??_7MULTI_WORK_ITEM@@6B@; const MULTI_WORK_ITEM::`vftable'
0x1800084ab  mov     qword ptr [rdi+10h], 0
0x1800084b3  mov     [rdi], rax
0x1800084b6  mov     qword ptr [rdi+18h], 0
0x1800084be  call    cs:__imp_GetTickCount
0x1800084c4  mov     dword ptr [rdi+8], 5449574Dh
0x1800084cb  mov     [rdi+20h], eax
0x1800084ce  test    rdi, rdi
0x1800084d1  jz      loc_18000858A
0x1800084d7  mov     rcx, [rdi+18h]
0x1800084db  test    rcx, rcx
0x1800084de  jz      short loc_1800084EC
0x1800084e0  mov     rax, [rcx]
0x1800084e3  mov     rax, [rax+8]
0x1800084e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ec  mov     [rdi+18h], rbx
0x1800084f0  mov     rcx, rbx
0x1800084f3  mov     rax, [rbx]
0x1800084f6  mov     rax, [rax]
0x1800084f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fe  mov     [rdi+10h], rbp
0x180008502  cmp     dword ptr [rsi+0Ch], 0
0x180008506  jz      short loc_18000850F
0x180008508  mov     ebx, 800700AAh
0x18000850d  jmp     short loc_18000855B
0x18000850f  lea     r8, [rsi+10h]; pcbe
0x180008513  mov     rdx, rdi; pv
0x180008516  lea     rcx, ?MultiWorkQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000851d  xor     ebx, ebx
0x18000851f  call    cs:__imp_TrySubmitThreadpoolCallback
0x180008525  test    eax, eax
0x180008527  jnz     loc_180008607
0x18000852d  call    cs:__imp_GetLastError
0x180008533  test    eax, eax
0x180008535  jz      short loc_180008556
0x180008537  call    cs:__imp_GetLastError
0x18000853d  mov     ebx, eax
0x18000853f  test    eax, eax
0x180008541  jle     short loc_18000854C
0x180008543  movzx   ebx, ax
0x180008546  or      ebx, 80070000h
0x18000854c  test    ebx, ebx
0x18000854e  jns     loc_180008607
0x180008554  jmp     short loc_18000855B
0x180008556  mov     ebx, 80004005h
0x18000855b  mov     rax, [rdi]
0x18000855e  mov     edx, 1
0x180008563  mov     rcx, rdi
0x180008566  mov     rax, [rax]
0x180008569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000856e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008575  jz      loc_180008607
0x18000857b  lea     rax, aCouldNotQueueW; "Could not queue work item\n"
0x180008582  mov     r8d, 183h
0x180008588  jmp     short loc_1800085E3
0x18000858a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008591  jz      short loc_1800085C8
0x180008593  mov     rcx, cs:g_pDebug
0x18000859a  lea     rax, aAllocatingWork; "Allocating WORK_ITEM failed\n"
0x1800085a1  mov     [rsp+58h+var_30], rax
0x1800085a6  lea     r9, aMultiWorkQueue_0; "MULTI_WORK_QUEUE::GetBlankWorkItem"
0x1800085ad  mov     r8d, 0CFh
0x1800085b3  mov     [rsp+58h+var_38], 80070008h
0x1800085bb  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800085c2  call    cs:__imp_PuDbgPrintError
0x1800085c8  mov     ebx, 80070008h
0x1800085cd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800085d4  jz      short loc_180008607
0x1800085d6  lea     rax, aCouldNotGetABl; "Could not get a blank work item\n"
0x1800085dd  mov     r8d, 170h
0x1800085e3  mov     rcx, cs:g_pDebug
0x1800085ea  lea     r9, aMultiWorkQueue; "MULTI_WORK_QUEUE::GetAndQueueWorkItem"
0x1800085f1  mov     [rsp+58h+var_30], rax
0x1800085f6  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800085fd  mov     [rsp+58h+var_38], ebx
0x180008601  call    cs:__imp_PuDbgPrintError
0x180008607  mov     eax, ebx
0x180008609  add     rsp, 38h
0x18000860d  pop     rdi
0x18000860e  pop     rsi
0x18000860f  pop     rbp
0x180008610  pop     rbx
0x180008611  retn
```
