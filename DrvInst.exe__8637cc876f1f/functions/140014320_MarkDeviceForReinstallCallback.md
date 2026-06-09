# MarkDeviceForReinstallCallback

- ea: `0x140014320`
- end: `0x1400143af`
- name: `MarkDeviceForReinstallCallback`
- size: `143`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x140014320`
- `0x140027124`
- `0x1400276f8`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140014354`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140014354`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001439c`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001439c`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001433d`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001433d`

## pseudocode

```c
__int64 __fastcall MarkDeviceForReinstallCallback(DEVINSTID_W pDeviceID)
{
  __int64 ThreadLogToken; // rdi
  int v4; // [rsp+40h] [rbp+18h] BYREF
  DEVNODE pdnDevInst; // [rsp+48h] [rbp+20h] BYREF

  v4 = 0;
  pdnDevInst = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( !CM_Locate_DevNodeW(&pdnDevInst, pDeviceID, 1u)
    && (unsigned int)DevUtilsGetConfigFlags(pdnDevInst, &v4)
    && (v4 & 0x40) != 0 )
  {
    v4 |= 0x20u;
    DevUtilsSetConfigFlags(pdnDevInst);
    DevRtlWriteTextLog(ThreadLogToken, 1, 5, "Found device that matches new INF.");
  }
  return 0;
}

```

## disassembly

```asm
0x140014320  mov     [rsp+arg_0], rbx
0x140014325  push    rdi
0x140014326  sub     rsp, 20h
0x14001432a  mov     rbx, rcx
0x14001432d  mov     [rsp+28h+arg_10], 0
0x140014335  mov     [rsp+28h+pdnDevInst], 0
0x14001433d  call    cs:__imp_DevRtlGetThreadLogToken
0x140014343  mov     r8d, 1; ulFlags
0x140014349  lea     rcx, [rsp+28h+pdnDevInst]; pdnDevInst
0x14001434e  mov     rdx, rbx; pDeviceID
0x140014351  mov     rdi, rax
0x140014354  call    cs:__imp_CM_Locate_DevNodeW
0x14001435a  test    eax, eax
0x14001435c  jnz     short loc_1400143A2
0x14001435e  mov     ecx, [rsp+28h+pdnDevInst]
0x140014362  lea     rdx, [rsp+28h+arg_10]
0x140014367  call    DevUtilsGetConfigFlags
0x14001436c  test    eax, eax
0x14001436e  jz      short loc_1400143A2
0x140014370  mov     edx, [rsp+28h+arg_10]
0x140014374  test    dl, 40h
0x140014377  jz      short loc_1400143A2
0x140014379  mov     ecx, [rsp+28h+pdnDevInst]
0x14001437d  or      edx, 20h
0x140014380  mov     [rsp+28h+arg_10], edx
0x140014384  call    DevUtilsSetConfigFlags
0x140014389  mov     edx, 1
0x14001438e  lea     r9, aFoundDeviceTha; "Found device that matches new INF."
0x140014395  mov     rcx, rdi
0x140014398  lea     r8d, [rdx+4]
0x14001439c  call    cs:__imp_DevRtlWriteTextLog
0x1400143a2  mov     rbx, [rsp+28h+arg_0]
0x1400143a7  xor     eax, eax
0x1400143a9  add     rsp, 20h
0x1400143ad  pop     rdi
0x1400143ae  retn
```
