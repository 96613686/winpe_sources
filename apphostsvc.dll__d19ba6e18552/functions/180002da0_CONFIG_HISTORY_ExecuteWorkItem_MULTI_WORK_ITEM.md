# CONFIG_HISTORY::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x180002da0`
- end: `0x180002e19`
- name: `?ExecuteWorkItem@CONFIG_HISTORY@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002da0`
- `0x1800032f0`
- `0x180004014`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180002e0b`
- `iisutil!PuDbgPrintError` at `0x180002e0b`

## string_xrefs

- `0x180002e04`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180002de7`: `Executing work item on CONFIG_HISTORY failed\n`
- `0x180002df3`: `CONFIG_HISTORY::ExecuteWorkItem`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::ExecuteWorkItem(CONFIG_HISTORY *this, struct MULTI_WORK_ITEM *a2)
{
  unsigned int v2; // ebx
  int v3; // eax

  if ( *((_QWORD *)a2 + 2) == 1 )
  {
    v3 = CONFIG_HISTORY::ProcessConfigChangeWorkItem((CONFIG_HISTORY *)((char *)this - 8));
LABEL_6:
    v2 = v3;
    if ( v3 >= 0 )
      return v2;
    goto LABEL_7;
  }
  if ( *((_QWORD *)a2 + 2) == 2 )
  {
    v3 = CONFIG_HISTORY::SnapshotConfigFilesWorkItem((CONFIG_HISTORY *)((char *)this - 8));
    goto LABEL_6;
  }
  v2 = -2147024809;
LABEL_7:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
      482,
      "CONFIG_HISTORY::ExecuteWorkItem",
      v2,
      "Executing work item on CONFIG_HISTORY failed\n");
  return v2;
}

```

## disassembly

```asm
0x180002da0  push    rbx
0x180002da2  sub     rsp, 30h
0x180002da6  mov     rax, [rdx+10h]
0x180002daa  sub     rax, 1
0x180002dae  jz      short loc_180002DC8
0x180002db0  cmp     rax, 1
0x180002db4  jz      short loc_180002DBD
0x180002db6  mov     ebx, 80070057h
0x180002dbb  jmp     short loc_180002DD7
0x180002dbd  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180002dc1  call    ?SnapshotConfigFilesWorkItem@CONFIG_HISTORY@@AEAAJXZ; CONFIG_HISTORY::SnapshotConfigFilesWorkItem(void)
0x180002dc6  jmp     short loc_180002DD1
0x180002dc8  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180002dcc  call    ?ProcessConfigChangeWorkItem@CONFIG_HISTORY@@AEAAJXZ; CONFIG_HISTORY::ProcessConfigChangeWorkItem(void)
0x180002dd1  mov     ebx, eax
0x180002dd3  test    eax, eax
0x180002dd5  jns     short loc_180002E11
0x180002dd7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002dde  jz      short loc_180002E11
0x180002de0  mov     rcx, cs:g_pDebug
0x180002de7  lea     rax, aExecutingWorkI; "Executing work item on CONFIG_HISTORY f"...
0x180002dee  mov     [rsp+38h+var_10], rax
0x180002df3  lea     r9, aConfigHistoryE; "CONFIG_HISTORY::ExecuteWorkItem"
0x180002dfa  mov     r8d, 1E2h
0x180002e00  mov     [rsp+38h+var_18], ebx
0x180002e04  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002e0b  call    cs:__imp_PuDbgPrintError
0x180002e11  mov     eax, ebx
0x180002e13  add     rsp, 30h
0x180002e17  pop     rbx
0x180002e18  retn
```
