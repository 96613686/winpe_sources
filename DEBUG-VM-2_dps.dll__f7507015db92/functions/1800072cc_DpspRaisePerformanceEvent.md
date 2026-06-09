# DpspRaisePerformanceEvent

- ea: `0x1800072cc`
- end: `0x18000734c`
- name: `DpspRaisePerformanceEvent`
- size: `128`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e88`
- `0x18000aff0`
- `0x18000b0a0`

## callees

- `0x1800072cc`
- `0x180009090`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800072e5`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800072e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800072ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800072ff`

## pseudocode

```c
__int64 __fastcall DpspRaisePerformanceEvent(PCEVENT_DESCRIPTOR EventDescriptor)
{
  signed int v2; // ebx
  signed int v3; // eax
  char Args[4]; // [rsp+20h] [rbp-18h]

  v2 = 0;
  if ( EventEnabled(g_hETW, EventDescriptor) )
  {
    v3 = EventWrite(g_hETW, EventDescriptor, 0, 0);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 < 0 )
    {
      *(_DWORD *)Args = (unsigned __int16)v2;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
        (__int64)L"DpspRaisePerformanceEvent",
        595,
        (const wchar_t *)L"Error = %d",
        *(_DWORD *)Args);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800072cc  mov     [rsp+arg_0], rbx
0x1800072d1  push    rdi
0x1800072d2  sub     rsp, 30h
0x1800072d6  mov     rdi, rcx
0x1800072d9  mov     rdx, rcx; EventDescriptor
0x1800072dc  mov     rcx, cs:g_hETW; RegHandle
0x1800072e3  xor     ebx, ebx
0x1800072e5  call    cs:__imp_EventEnabled
0x1800072eb  test    al, al
0x1800072ed  jz      short loc_18000733F
0x1800072ef  mov     rcx, cs:g_hETW; RegHandle
0x1800072f6  xor     r9d, r9d; UserData
0x1800072f9  xor     r8d, r8d; UserDataCount
0x1800072fc  mov     rdx, rdi; EventDescriptor
0x1800072ff  call    cs:__imp_EventWrite
0x180007305  mov     ebx, eax
0x180007307  test    eax, eax
0x180007309  jle     short loc_180007314
0x18000730b  movzx   ebx, ax
0x18000730e  or      ebx, 80070000h
0x180007314  test    ebx, ebx
0x180007316  jns     short loc_18000733F
0x180007318  movzx   ecx, bx
0x18000731b  lea     r9, aErrorD; "Error = %d"
0x180007322  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180007326  lea     rdx, aDpspraiseperfo; "DpspRaisePerformanceEvent"
0x18000732d  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007334  mov     r8d, 253h; int
0x18000733a  call    WdipTraceError
0x18000733f  mov     eax, ebx
0x180007341  mov     rbx, [rsp+38h+arg_0]
0x180007346  add     rsp, 30h
0x18000734a  pop     rdi
0x18000734b  retn
```
