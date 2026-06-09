# SID_MAPPER::QueryInterface(_GUID const &,void * *)

- ea: `0x1800026e0`
- end: `0x18000274f`
- name: `?QueryInterface@SID_MAPPER@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `111`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800026e0`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000272b`
- `iisutil!PuDbgPrintError` at `0x18000272b`

## string_xrefs

- `0x180002724`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\sid_mapper.cxx`
- `0x180002703`: `QueryInterface on CONFIG_HISTORY object failed, bad pointer\n`
- `0x18000270f`: `SID_MAPPER::QueryInterface`

## pseudocode

```c
__int64 __fastcall SID_MAPPER::QueryInterface(SID_MAPPER *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    *a3 = this;
    v3 = 0;
    (*(void (__fastcall **)(SID_MAPPER *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    v3 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\sid_mapper.cxx",
        321,
        "SID_MAPPER::QueryInterface",
        -2147024809,
        "QueryInterface on CONFIG_HISTORY object failed, bad pointer\n");
  }
  return v3;
}

```

## disassembly

```asm
0x1800026e0  push    rbx
0x1800026e2  sub     rsp, 30h
0x1800026e6  mov     rdx, rcx
0x1800026e9  test    r8, r8
0x1800026ec  jnz     short loc_180002733
0x1800026ee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800026f5  mov     ebx, 80070057h
0x1800026fa  jz      short loc_180002747
0x1800026fc  mov     rcx, cs:g_pDebug
0x180002703  lea     rax, aQueryinterface; "QueryInterface on CONFIG_HISTORY object"...
0x18000270a  mov     [rsp+38h+var_10], rax
0x18000270f  lea     r9, aSidMapperQuery; "SID_MAPPER::QueryInterface"
0x180002716  mov     r8d, 141h
0x18000271c  mov     [rsp+38h+var_18], 80070057h
0x180002724  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000272b  call    cs:__imp_PuDbgPrintError
0x180002731  jmp     short loc_180002747
0x180002733  mov     [r8], rdx
0x180002736  xor     ebx, ebx
0x180002738  mov     rcx, [rcx]
0x18000273b  mov     rax, [rcx+8]
0x18000273f  mov     rcx, rdx
0x180002742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002747  mov     eax, ebx
0x180002749  add     rsp, 30h
0x18000274d  pop     rbx
0x18000274e  retn
```
