# DpspRaiseServiceStartEvent

- ea: `0x180007800`
- end: `0x180007880`
- name: `DpspRaiseServiceStartEvent`
- size: `128`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001e88`
- `0x180016200`

## callees

- `0x180007800`
- `0x180009090`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007819`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180007819`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007833`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007833`

## string_xrefs

- `0x18000785a`: `DpspRaiseServiceStartEvent`

## pseudocode

```c
__int64 __fastcall DpspRaiseServiceStartEvent(PCEVENT_DESCRIPTOR EventDescriptor)
{
  signed int Args; // ebx
  signed int v3; // eax

  Args = 0;
  if ( EventEnabled(g_hETW, EventDescriptor) )
  {
    v3 = EventWrite(g_hETW, EventDescriptor, 0, 0);
    Args = v3;
    if ( v3 > 0 )
      Args = (unsigned __int16)v3 | 0x80070000;
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
        (int)L"DpspRaiseServiceStartEvent",
        46,
        (int)L"Error = %d",
        Args);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180007800  mov     [rsp+arg_0], rbx
0x180007805  push    rdi
0x180007806  sub     rsp, 30h
0x18000780a  mov     rdi, rcx
0x18000780d  mov     rdx, rcx; EventDescriptor
0x180007810  mov     rcx, cs:g_hETW; RegHandle
0x180007817  xor     ebx, ebx
0x180007819  call    cs:__imp_EventEnabled
0x18000781f  test    al, al
0x180007821  jz      short loc_180007873
0x180007823  mov     rcx, cs:g_hETW; RegHandle
0x18000782a  xor     r9d, r9d; UserData
0x18000782d  xor     r8d, r8d; UserDataCount
0x180007830  mov     rdx, rdi; EventDescriptor
0x180007833  call    cs:__imp_EventWrite
0x180007839  mov     ebx, eax
0x18000783b  test    eax, eax
0x18000783d  jle     short loc_180007848
0x18000783f  movzx   ebx, ax
0x180007842  or      ebx, 80070000h
0x180007848  test    ebx, ebx
0x18000784a  jns     short loc_180007873
0x18000784c  movzx   ecx, bx
0x18000784f  lea     r9, aErrorD; "Error = %d"
0x180007856  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000785a  lea     rdx, aDpspraiseservi; "DpspRaiseServiceStartEvent"
0x180007861  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007868  mov     r8d, 2Eh ; '.'; int
0x18000786e  call    WdipTraceError
0x180007873  mov     eax, ebx
0x180007875  mov     rbx, [rsp+38h+arg_0]
0x18000787a  add     rsp, 30h
0x18000787e  pop     rdi
0x18000787f  retn
```
