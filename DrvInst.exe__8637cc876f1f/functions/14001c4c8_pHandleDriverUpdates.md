# pHandleDriverUpdates

- ea: `0x14001c4c8`
- end: `0x14001c531`
- name: `pHandleDriverUpdates`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140009820`

## callees

- `0x14001ae4c`
- `0x14001c4c8`
- `0x140020f3c`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x14001c504`
- `ntdll!DbgPrintEx` at `0x14001c504`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001c4e2`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001c4e2`

## string_xrefs

- `0x14001c4e8`: `DebugUpdate`
- `0x14001c4fa`: `\nDRVINST.EXE: Entering debugger while installing driver updates.`

## pseudocode

```c
__int64 __fastcall pHandleDriverUpdates(int a1, __int64 a2, __int64 a3, int a4)
{
  DevRtlSetThreadLogToken(a3);
  if ( (unsigned int)DoDebugBreak(L"DebugUpdate") )
  {
    DbgPrintEx(0x23u, 0, "\nDRVINST.EXE: Entering debugger while installing driver updates.");
    __debugbreak();
  }
  if ( a1 == 7 )
    return InstallDeviceDriverUpdates(a2, a4);
  else
    return 87;
}

```

## disassembly

```asm
0x14001c4c8  mov     [rsp+arg_0], rbx
0x14001c4cd  mov     [rsp+arg_8], rsi
0x14001c4d2  push    rdi
0x14001c4d3  sub     rsp, 20h
0x14001c4d7  mov     ebx, ecx
0x14001c4d9  mov     edi, r9d
0x14001c4dc  mov     rcx, r8
0x14001c4df  mov     rsi, rdx
0x14001c4e2  call    cs:__imp_DevRtlSetThreadLogToken
0x14001c4e8  lea     rcx, aDebugupdate; "DebugUpdate"
0x14001c4ef  call    DoDebugBreak
0x14001c4f4  test    eax, eax
0x14001c4f6  jz      short loc_14001C50B
0x14001c4f8  xor     edx, edx; Level
0x14001c4fa  lea     r8, aDrvinstExeEnte_0; "\nDRVINST.EXE: Entering debugger while "...
0x14001c501  lea     ecx, [rdx+23h]; ComponentId
0x14001c504  call    cs:__imp_DbgPrintEx
0x14001c50a  int     3; Trap to Debugger
0x14001c50b  cmp     ebx, 7
0x14001c50e  jz      short loc_14001C517
0x14001c510  mov     eax, 57h ; 'W'
0x14001c515  jmp     short loc_14001C521
0x14001c517  mov     edx, edi
0x14001c519  mov     rcx, rsi
0x14001c51c  call    InstallDeviceDriverUpdates
0x14001c521  mov     rbx, [rsp+28h+arg_0]
0x14001c526  mov     rsi, [rsp+28h+arg_8]
0x14001c52b  add     rsp, 20h
0x14001c52f  pop     rdi
0x14001c530  retn
```
