# WppCleanup(void)

- ea: `0x180005ec0`
- end: `0x180005f20`
- name: `?WppCleanup@@YAXXZ`
- size: `96`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005958`
- `0x180006040`

## callees

- `0x180005ec0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180005ef1`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180005ef1`

## pseudocode

```c
void WppCleanup(void)
{
  _QWORD *v0; // rbx
  TRACEHANDLE v1; // rcx

  if ( g_bWppEnabled )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v0 )
      {
        v1 = v0[1];
        if ( v1 )
        {
          UnregisterTraceGuids(v1);
          v0[1] = 0;
        }
        v0 = (_QWORD *)*v0;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    g_bWppEnabled = 0;
  }
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_0], rbx
0x180005ec5  push    rsi
0x180005ec6  sub     rsp, 20h
0x180005eca  cmp     cs:?g_bWppEnabled@@3_NA, 0; bool g_bWppEnabled
0x180005ed1  jz      short loc_180005F15
0x180005ed3  mov     rbx, cs:WPP_GLOBAL_Control
0x180005eda  lea     rsi, WPP_GLOBAL_Control
0x180005ee1  cmp     rbx, rsi
0x180005ee4  jz      short loc_180005F0E
0x180005ee6  jmp     short loc_180005F02
0x180005ee8  mov     rcx, [rbx+8]; RegistrationHandle
0x180005eec  test    rcx, rcx
0x180005eef  jz      short loc_180005EFF
0x180005ef1  call    cs:__imp_UnregisterTraceGuids
0x180005ef7  mov     qword ptr [rbx+8], 0
0x180005eff  mov     rbx, [rbx]
0x180005f02  test    rbx, rbx
0x180005f05  jnz     short loc_180005EE8
0x180005f07  mov     cs:WPP_GLOBAL_Control, rsi
0x180005f0e  mov     cs:?g_bWppEnabled@@3_NA, 0; bool g_bWppEnabled
0x180005f15  mov     rbx, [rsp+28h+arg_0]
0x180005f1a  add     rsp, 20h
0x180005f1e  pop     rsi
0x180005f1f  retn
```
