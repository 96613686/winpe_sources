# EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)

- ea: `0x180034a60`
- end: `0x180034ad9`
- name: `?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z`
- size: `121`
- prototype: `void __fastcall(struct _EVENT_LOG_SOURCE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034b6c`

## callees

- `0x180034218`
- `0x180034a60`
- `0x180034b28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a90`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180034a72`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180034a72`

## string_xrefs

- `0x180034aa8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

## pseudocode

```c
void __fastcall EVENT_LOG::DestroyEventLogSource(struct _EVENT_LOG_SOURCE *a1)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)a1 + 1);
  if ( v2 && !DeregisterEventSource(v2) && (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
  {
    GetLastError();
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
      0x1A5u,
      "EVENT_LOG::DestroyEventLogSource",
      "Destruction of EVENT_LOG_SOURCE[%p] failed. error %lu\n",
      (char)a1);
  }
  SMALL_STRU::Reset((struct _EVENT_LOG_SOURCE *)((char *)a1 + 16));
}

```

## disassembly

```asm
0x180034a60  push    rbx
0x180034a62  sub     rsp, 40h
0x180034a66  mov     rbx, rcx
0x180034a69  mov     rcx, [rcx+8]; hEventLog
0x180034a6d  test    rcx, rcx
0x180034a70  jz      short loc_180034ACB
0x180034a72  call    cs:__imp_DeregisterEventSource
0x180034a78  test    eax, eax
0x180034a7a  jnz     short loc_180034ACB
0x180034a7c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180034a82  test    al, 3
0x180034a84  setnz   cl
0x180034a87  test    al, 4
0x180034a89  setnz   al
0x180034a8c  test    al, cl
0x180034a8e  jz      short loc_180034ACB
0x180034a90  call    cs:__imp_GetLastError
0x180034a96  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180034a9d  lea     r9, aEventLogDestro; "EVENT_LOG::DestroyEventLogSource"
0x180034aa4  mov     [rsp+48h+var_18], eax
0x180034aa8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180034aaf  lea     rax, aDestructionOfE; "Destruction of EVENT_LOG_SOURCE[%p] fai"...
0x180034ab6  mov     qword ptr [rsp+48h+var_20], rbx; char
0x180034abb  mov     r8d, 1A5h; unsigned int
0x180034ac1  mov     [rsp+48h+var_28], rax; char *
0x180034ac6  call    PuDbgPrint
0x180034acb  lea     rcx, [rbx+10h]; this
0x180034acf  add     rsp, 40h
0x180034ad3  pop     rbx
0x180034ad4  jmp     ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
```
