# CDirMonitor::RemoveEntry(CDirMonitorEntry *)

- ea: `0x180063eb8`
- end: `0x180063f37`
- name: `?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018b30`
- `0x180063aec`

## callees

- `0x180063eb8`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180063ecd`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180063ecd`
- `iisutil!PuDbgPrint` at `0x180063f1b`
- `iisutil!PuDbgPrint` at `0x180063f1b`

## string_xrefs

- `0x180063f04`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180063eea`: `[CDirMonitor] Removed DME(%08x), directory %ws\n`
- `0x180063ef8`: `CDirMonitor::RemoveEntry`

## pseudocode

```c
__int64 __fastcall CDirMonitor::RemoveEntry(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  bool v5; // zf
  unsigned int v6; // esi

  v4 = CLKRHashTable::DeleteRecord(a1, a2);
  v5 = (g_dwDebugFlags & 3) == 0;
  v6 = v4;
  *(_QWORD *)(a2 + 96) = 0;
  if ( !v5 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      923,
      "CDirMonitor::RemoveEntry",
      "[CDirMonitor] Removed DME(%08x), directory %ws\n",
      a2,
      *(_QWORD *)(a2 + 16));
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 112));
  return v6;
}

```

## disassembly

```asm
0x180063eb8  mov     [rsp+arg_0], rbx
0x180063ebd  mov     [rsp+arg_8], rsi
0x180063ec2  push    rdi
0x180063ec3  sub     rsp, 40h
0x180063ec7  mov     rdi, rdx
0x180063eca  mov     rbx, rcx
0x180063ecd  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180063ed3  test    byte ptr cs:g_dwDebugFlags, 3
0x180063eda  mov     esi, eax
0x180063edc  mov     qword ptr [rdi+60h], 0
0x180063ee4  jz      short loc_180063F21
0x180063ee6  mov     r8, [rdi+10h]
0x180063eea  lea     rax, aCdirmonitorRem_0; "[CDirMonitor] Removed DME(%08x), direct"...
0x180063ef1  mov     rcx, cs:g_pDebug
0x180063ef8  lea     r9, aCdirmonitorRem; "CDirMonitor::RemoveEntry"
0x180063eff  mov     [rsp+48h+var_18], r8
0x180063f04  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180063f0b  mov     [rsp+48h+var_20], rdi
0x180063f10  mov     r8d, 39Bh
0x180063f16  mov     [rsp+48h+var_28], rax
0x180063f1b  call    cs:__imp_PuDbgPrint
0x180063f21  lock dec dword ptr [rbx+70h]
0x180063f25  mov     eax, esi
0x180063f27  mov     rbx, [rsp+48h+arg_0]
0x180063f2c  mov     rsi, [rsp+48h+arg_8]
0x180063f31  add     rsp, 40h
0x180063f35  pop     rdi
0x180063f36  retn
```
