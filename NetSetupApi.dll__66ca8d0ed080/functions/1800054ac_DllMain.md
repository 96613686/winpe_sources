# DllMain

- ea: `0x1800054ac`
- end: `0x180005520`
- name: `DllMain`
- size: `116`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800085a4`

## callees

- `0x1800010c4`
- `0x1800054ac`
- `0x180005528`
- `0x1800057e0`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x1800054f3`
- `ntdll!EtwUnregisterTraceGuids` at `0x1800054f3`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _QWORD *v3; // rbx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
      DllInitialize(hinstDLL);
  }
  else if ( !lpvReserved )
  {
    TraceLoggingUnregister_EventUnregister(hinstDLL);
    McGenEventUnregister_EventUnregister();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v3 )
      {
        if ( v3[1] )
        {
          EtwUnregisterTraceGuids();
          v3[1] = 0;
        }
        v3 = (_QWORD *)*v3;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800054ac  mov     [rsp+arg_0], rbx
0x1800054b1  push    rdi
0x1800054b2  sub     rsp, 20h
0x1800054b6  test    edx, edx
0x1800054b8  jz      short loc_1800054C6
0x1800054ba  cmp     edx, 1
0x1800054bd  jnz     short loc_180005510
0x1800054bf  call    DllInitialize
0x1800054c4  jmp     short loc_180005510
0x1800054c6  test    r8, r8
0x1800054c9  jnz     short loc_180005510
0x1800054cb  call    TraceLoggingUnregister_EventUnregister
0x1800054d0  call    McGenEventUnregister_EventUnregister
0x1800054d5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800054dc  lea     rdi, WPP_GLOBAL_Control
0x1800054e3  cmp     rbx, rdi
0x1800054e6  jz      short loc_180005510
0x1800054e8  jmp     short loc_180005504
0x1800054ea  mov     rcx, [rbx+8]
0x1800054ee  test    rcx, rcx
0x1800054f1  jz      short loc_180005501
0x1800054f3  call    cs:__imp_EtwUnregisterTraceGuids
0x1800054f9  mov     qword ptr [rbx+8], 0
0x180005501  mov     rbx, [rbx]
0x180005504  test    rbx, rbx
0x180005507  jnz     short loc_1800054EA
0x180005509  mov     cs:WPP_GLOBAL_Control, rdi
0x180005510  mov     rbx, [rsp+28h+arg_0]
0x180005515  mov     eax, 1
0x18000551a  add     rsp, 20h
0x18000551e  pop     rdi
0x18000551f  retn
```
