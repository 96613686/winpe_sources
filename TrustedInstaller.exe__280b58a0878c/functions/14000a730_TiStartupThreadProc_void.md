# TiStartupThreadProc(void *)

- ea: `0x14000a730`
- end: `0x14000a7c3`
- name: `?TiStartupThreadProc@@YAKPEAX@Z`
- size: `147`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000a730`
- `0x14000d5c8`
- `0x140017658`

## string_xrefs

- `0x14000a781`: `Failed during startup processing, continuing with Trusted Installer execution`
- `0x14000a7a5`: `Startup processing complete, Trusted Installer will now wait around for a little while to see if any clients show up.`

## pseudocode

```c
__int64 __fastcall TiStartupThreadProc(PVOID Parameter, bool a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( vbStandalone )
  {
    v2 = 0;
    CBSWdsLogLight(0x4000000u, 0, 0, "Running in standalone mode, skipping any startup processing.");
    return v2;
  }
  v3 = TiCoreStartupProcessing(&v5, a2);
  v2 = v3;
  if ( v3 == -2147021886 )
  {
    CBSWdsLogLight(0x4000000u, 0, 0, "Waiting for reboot to continue processing");
    return 0;
  }
  if ( v3 < 0 )
  {
    CBSWdsLogLight(
      0x4000000u,
      (unsigned int)v3,
      (size_t *)1,
      "Failed during startup processing, continuing with Trusted Installer execution");
    return 0;
  }
  if ( v5 )
    CBSWdsLogLight(
      0x4000000u,
      0,
      0,
      "Startup processing complete, Trusted Installer will now wait around for a little while to see if any clients show up.");
  return v2;
}

```

## disassembly

```asm
0x14000a730  push    rbx
0x14000a732  sub     rsp, 20h
0x14000a736  cmp     cs:?vbStandalone@@3HA, 0; int vbStandalone
0x14000a73d  mov     [rsp+28h+arg_8], 0
0x14000a745  jz      short loc_14000A752
0x14000a747  xor     ebx, ebx
0x14000a749  lea     r9, aRunningInStand; "Running in standalone mode, skipping an"...
0x14000a750  jmp     short loc_14000A7AC
0x14000a752  lea     rcx, [rsp+28h+arg_8]
0x14000a757  call    TiCoreStartupProcessing
0x14000a75c  mov     ebx, eax
0x14000a75e  cmp     eax, 80070BC2h
0x14000a763  jnz     short loc_14000A77D
0x14000a765  lea     r9, aWaitingForRebo; "Waiting for reboot to continue processi"...
0x14000a76c  xor     r8d, r8d
0x14000a76f  xor     edx, edx
0x14000a771  mov     ecx, 4000000h
0x14000a776  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a77b  jmp     short loc_14000A79A
0x14000a77d  test    eax, eax
0x14000a77f  jns     short loc_14000A79E
0x14000a781  lea     r9, aFailedDuringSt_0; "Failed during startup processing, conti"...
0x14000a788  mov     r8d, 1
0x14000a78e  mov     edx, eax
0x14000a790  mov     ecx, 4000000h
0x14000a795  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a79a  xor     ebx, ebx
0x14000a79c  jmp     short loc_14000A7BB
0x14000a79e  cmp     [rsp+28h+arg_8], 0
0x14000a7a3  jz      short loc_14000A7BB
0x14000a7a5  lea     r9, aStartupProcess_1; "Startup processing complete, Trusted In"...
0x14000a7ac  xor     r8d, r8d
0x14000a7af  xor     edx, edx
0x14000a7b1  mov     ecx, 4000000h
0x14000a7b6  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a7bb  mov     eax, ebx
0x14000a7bd  add     rsp, 20h
0x14000a7c1  pop     rbx
0x14000a7c2  retn
```
