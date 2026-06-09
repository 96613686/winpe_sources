# CONFIG_HISTORY::QueryInterface(_GUID const &,void * *)

- ea: `0x180003db0`
- end: `0x180003e1f`
- name: `?QueryInterface@CONFIG_HISTORY@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `111`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003db0`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180003dfb`
- `iisutil!PuDbgPrintError` at `0x180003dfb`

## string_xrefs

- `0x180003dd3`: `QueryInterface on CONFIG_HISTORY object failed, bad pointer\n`
- `0x180003df4`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history.cxx`
- `0x180003ddf`: `CONFIG_HISTORY::QueryInterface`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::QueryInterface(CONFIG_HISTORY *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    *a3 = this;
    v3 = 0;
    (*(void (__fastcall **)(CONFIG_HISTORY *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    v3 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history.cxx",
        525,
        "CONFIG_HISTORY::QueryInterface",
        -2147024809,
        "QueryInterface on CONFIG_HISTORY object failed, bad pointer\n");
  }
  return v3;
}

```

## disassembly

```asm
0x180003db0  push    rbx
0x180003db2  sub     rsp, 30h
0x180003db6  mov     rdx, rcx
0x180003db9  test    r8, r8
0x180003dbc  jnz     short loc_180003E03
0x180003dbe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003dc5  mov     ebx, 80070057h
0x180003dca  jz      short loc_180003E17
0x180003dcc  mov     rcx, cs:g_pDebug
0x180003dd3  lea     rax, aQueryinterface; "QueryInterface on CONFIG_HISTORY object"...
0x180003dda  mov     [rsp+38h+var_10], rax
0x180003ddf  lea     r9, aConfigHistoryQ; "CONFIG_HISTORY::QueryInterface"
0x180003de6  mov     r8d, 20Dh
0x180003dec  mov     [rsp+38h+var_18], 80070057h
0x180003df4  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003dfb  call    cs:__imp_PuDbgPrintError
0x180003e01  jmp     short loc_180003E17
0x180003e03  mov     [r8], rdx
0x180003e06  xor     ebx, ebx
0x180003e08  mov     rcx, [rcx]
0x180003e0b  mov     rax, [rcx+8]
0x180003e0f  mov     rcx, rdx
0x180003e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e17  mov     eax, ebx
0x180003e19  add     rsp, 30h
0x180003e1d  pop     rbx
0x180003e1e  retn
```
