# SID_MAPPER::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x180002600`
- end: `0x180002665`
- name: `?ExecuteWorkItem@SID_MAPPER@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002600`
- `0x1800027c0`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180002657`
- `iisutil!PuDbgPrintError` at `0x180002657`

## string_xrefs

- `0x180002633`: `Executing work item on SID_MAPPER failed\n`
- `0x18000263f`: `SID_MAPPER::ExecuteWorkItem`
- `0x180002650`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\sid_mapper.cxx`

## pseudocode

```c
__int64 __fastcall SID_MAPPER::ExecuteWorkItem(SID_MAPPER *this, struct MULTI_WORK_ITEM *a2)
{
  int updated; // ebx

  if ( *((_QWORD *)a2 + 2) == 1 )
  {
    updated = SID_MAPPER::UpdateAppPoolSIDMap((SID_MAPPER *)((char *)this - 8));
    if ( updated >= 0 )
      return (unsigned int)updated;
  }
  else
  {
    updated = -2147024809;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\sid_mapper.cxx",
      278,
      "SID_MAPPER::ExecuteWorkItem",
      updated,
      "Executing work item on SID_MAPPER failed\n");
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180002600  push    rbx
0x180002602  sub     rsp, 30h
0x180002606  cmp     qword ptr [rdx+10h], 1
0x18000260b  jz      short loc_180002614
0x18000260d  mov     ebx, 80070057h
0x180002612  jmp     short loc_180002623
0x180002614  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180002618  call    ?UpdateAppPoolSIDMap@SID_MAPPER@@AEAAJXZ; SID_MAPPER::UpdateAppPoolSIDMap(void)
0x18000261d  mov     ebx, eax
0x18000261f  test    eax, eax
0x180002621  jns     short loc_18000265D
0x180002623  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000262a  jz      short loc_18000265D
0x18000262c  mov     rcx, cs:g_pDebug
0x180002633  lea     rax, aExecutingWorkI_1; "Executing work item on SID_MAPPER faile"...
0x18000263a  mov     [rsp+38h+var_10], rax
0x18000263f  lea     r9, aSidMapperExecu; "SID_MAPPER::ExecuteWorkItem"
0x180002646  mov     r8d, 116h
0x18000264c  mov     [rsp+38h+var_18], ebx
0x180002650  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002657  call    cs:__imp_PuDbgPrintError
0x18000265d  mov     eax, ebx
0x18000265f  add     rsp, 30h
0x180002663  pop     rbx
0x180002664  retn
```
