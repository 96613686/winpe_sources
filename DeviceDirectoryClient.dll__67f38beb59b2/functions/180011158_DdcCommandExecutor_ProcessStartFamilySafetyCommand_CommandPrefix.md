# DdcCommandExecutor::ProcessStartFamilySafetyCommand(CommandPrefix *)

- ea: `0x180011158`
- end: `0x180011223`
- name: `?ProcessStartFamilySafetyCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct CommandPrefix *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005f5c`

## callees

- `0x1800050b8`
- `0x180005310`
- `0x180011158`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800111c2`
- `ntdll!RtlPublishWnfStateData` at `0x1800111c2`

## string_xrefs

- `0x180011194`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandExecutor::ProcessStartFamilySafetyCommand(struct CommandPrefix *a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 1;
  if ( a1 )
  {
    v6 = RtlPublishWnfStateData(WNF_WFS_SETTINGS, 0, &v8, 4, 0);
    if ( v6 )
    {
      v3 = v6 | 0x10000000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v5,
          v4,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          224,
          "CBR(ntStatus == ((NTSTATUS)0x00000000L))");
    }
    else
    {
      v3 = 0;
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        215,
        "CPR(pPrefix)");
  }
  DdcTraceHelper::TraceCommandResult(0, *(_DWORD *)a1, 8u, *((_DWORD *)a1 + 2), v3, 0, v3);
  return v3;
}

```

## disassembly

```asm
0x180011158  mov     [rsp+arg_8], rbx
0x18001115d  push    rdi
0x18001115e  sub     rsp, 40h
0x180011162  mov     [rsp+48h+arg_0], 1
0x18001116a  mov     rdi, rcx
0x18001116d  test    rcx, rcx
0x180011170  jnz     short loc_1800111A5
0x180011172  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011179  mov     ebx, 80070057h
0x18001117e  jz      short loc_1800111F3
0x180011180  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180011187  mov     qword ptr [rsp+48h+var_20], rax
0x18001118c  mov     [rsp+48h+var_28], 2D7h
0x180011194  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001119b  mov     r8d, ebx
0x18001119e  call    McTemplateU0dsqs_EventWriteTransfer
0x1800111a3  jmp     short loc_1800111F3
0x1800111a5  mov     rcx, cs:WNF_WFS_SETTINGS
0x1800111ac  lea     r8, [rsp+48h+arg_0]
0x1800111b1  mov     r9d, 4
0x1800111b7  mov     qword ptr [rsp+48h+var_28], 0
0x1800111c0  xor     edx, edx
0x1800111c2  call    cs:__imp_RtlPublishWnfStateData
0x1800111c8  mov     ebx, eax
0x1800111ca  test    eax, eax
0x1800111cc  jz      short loc_1800111F1
0x1800111ce  bts     ebx, 1Ch
0x1800111d2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800111d9  jz      short loc_1800111F3
0x1800111db  lea     rax, aCbrNtstatusNts; "CBR(ntStatus == ((NTSTATUS)0x00000000L)"...
0x1800111e2  mov     qword ptr [rsp+48h+var_20], rax
0x1800111e7  mov     [rsp+48h+var_28], 2E0h
0x1800111ef  jmp     short loc_180011194
0x1800111f1  xor     ebx, ebx
0x1800111f3  mov     r9d, [rdi+8]; unsigned int
0x1800111f7  mov     r8d, 8; unsigned int
0x1800111fd  mov     edx, [rdi]; unsigned int
0x1800111ff  xor     ecx, ecx; int
0x180011201  mov     [rsp+48h+var_18], ebx; int
0x180011205  mov     [rsp+48h+var_20], 0; unsigned int
0x18001120d  mov     [rsp+48h+var_28], ebx; int
0x180011211  call    ?TraceCommandResult@DdcTraceHelper@@SAXHKKKJKJ@Z; DdcTraceHelper::TraceCommandResult(int,ulong,ulong,ulong,long,ulong,long)
0x180011216  mov     eax, ebx
0x180011218  mov     rbx, [rsp+48h+arg_8]
0x18001121d  add     rsp, 40h
0x180011221  pop     rdi
0x180011222  retn
```
