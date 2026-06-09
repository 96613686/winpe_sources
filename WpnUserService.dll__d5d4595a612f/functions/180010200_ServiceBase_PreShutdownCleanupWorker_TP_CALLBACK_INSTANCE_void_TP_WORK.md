# ServiceBase::_PreShutdownCleanupWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180010200`
- end: `0x180010259`
- name: `?_PreShutdownCleanupWorker@ServiceBase@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `89`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_WORK Work)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000e904`

## callees

- `0x1800071a8`
- `0x18000ce58`
- `0x180010200`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010239`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010239`

## string_xrefs

- `0x180010221`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
void __fastcall ServiceBase::_PreShutdownCleanupWorker(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_WORK Work)
{
  int v4; // eax
  __int64 v5; // r8
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (*((__int64 (__fastcall **)(HANDLE *, HANDLE *, PTP_WORK))*Context + 12))(Context, Context, Work);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2BB,
      (__int64)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)(unsigned int)v4);
  if ( !SetEvent(Context[10]) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v5, v6);
}

```

## disassembly

```asm
0x180010200  push    rbx; int
0x180010202  sub     rsp, 20h
0x180010206  mov     rax, [rdx]
0x180010209  mov     rcx, rdx
0x18001020c  mov     rbx, rdx
0x18001020f  mov     rax, [rax+60h]
0x180010213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010218  test    eax, eax
0x18001021a  jns     short loc_180010235
0x18001021c  mov     rcx, [rsp+28h]; this
0x180010221  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010228  mov     r9d, eax; char *
0x18001022b  mov     edx, 2BBh; void *
0x180010230  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010235  mov     rcx, [rbx+50h]; hEvent
0x180010239  call    cs:__imp_SetEvent
0x18001023f  test    eax, eax
0x180010241  jz      short loc_180010249
0x180010243  add     rsp, 20h
0x180010247  pop     rbx
0x180010248  retn
0x180010249  mov     rcx, [rsp+28h]; this
0x18001024e  mov     edx, 0A01h; void *
0x180010253  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
