# DllMain

- ea: `0x18002edc0`
- end: `0x18002eed6`
- name: `DllMain`
- size: `278`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004364`

## callees

- `0x18002edc0`
- `0x18002eedc`
- `0x18002f0c0`
- `0x18002f408`

## import_xrefs

- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x18002eec0`
- `msvcrt!?set_terminate@@YAP6AXXZP6AXXZ@Z` at `0x18002eec0`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ee38`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002eeb8`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ee38`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002eeb8`
- `ADVAPI32!UnregisterTraceGuids` at `0x18002ee65`
- `ADVAPI32!UnregisterTraceGuids` at `0x18002ee65`
- `KERNEL32!CloseHandle` at `0x18002ee96`
- `KERNEL32!CloseHandle` at `0x18002eeb0`
- `KERNEL32!CloseHandle` at `0x18002ee96`
- `KERNEL32!CloseHandle` at `0x18002eeb0`
- `KERNEL32!TlsAlloc` at `0x18002edf6`
- `KERNEL32!TlsAlloc` at `0x18002ee02`
- `KERNEL32!TlsAlloc` at `0x18002edf6`
- `KERNEL32!TlsAlloc` at `0x18002ee02`
- `KERNEL32!TlsGetValue` at `0x18002ee88`
- `KERNEL32!TlsGetValue` at `0x18002eea2`
- `KERNEL32!TlsGetValue` at `0x18002ee88`
- `KERNEL32!TlsGetValue` at `0x18002eea2`
- `mqsec!MQUInitGlobalScurityVars` at `0x18002ee0e`
- `mqsec!MQUInitGlobalScurityVars` at `0x18002ee0e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  DWORD v3; // edx
  DWORD v4; // edx
  void (*v6)(void); // rcx
  _QWORD *v7; // rbx
  TRACEHANDLE v8; // rcx
  void *Value; // rax
  void *v10; // rax

  if ( !fdwReason )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v7 )
      {
        v8 = v7[1];
        if ( v8 )
        {
          UnregisterTraceGuids(v8);
          v7[1] = 0;
        }
        v7 = (_QWORD *)*v7;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
LABEL_17:
    Value = TlsGetValue(g_dwThreadEventIndex);
    if ( Value )
      CloseHandle(Value);
    v10 = TlsGetValue(g_dwThreadHandleIndex);
    if ( v10 )
      CloseHandle(v10);
    _set_se_translator(0);
    v6 = 0;
    goto LABEL_22;
  }
  v3 = fdwReason - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
        return 1;
      goto LABEL_17;
    }
  }
  else
  {
    if ( dword_18013C6A8 )
      return 0;
    g_dwThreadEventIndex = TlsAlloc();
    g_dwThreadHandleIndex = TlsAlloc();
    MQUInitGlobalScurityVars();
    WPP_INIT_CONTROL_ARRAY();
    WPP_INIT_GUID_ARRAY();
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
  }
  _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))QmpExceptionTranslator);
  v6 = (void (*)(void))QmpAbnormalTerminationHandler;
LABEL_22:
  set_terminate(v6);
  return 1;
}

```

## disassembly

```asm
0x18002edc0  mov     [rsp+arg_0], rbx
0x18002edc5  push    rdi
0x18002edc6  sub     rsp, 20h
0x18002edca  test    edx, edx
0x18002edcc  jz      short loc_18002EE47
0x18002edce  sub     edx, 1
0x18002edd1  jz      short loc_18002EDE6
0x18002edd3  sub     edx, 1
0x18002edd6  jz      short loc_18002EE31
0x18002edd8  cmp     edx, 1
0x18002eddb  jz      loc_18002EE82
0x18002ede1  jmp     loc_18002EEC6
0x18002ede6  cmp     cs:dword_18013C6A8, 0
0x18002eded  jz      short loc_18002EDF6
0x18002edef  xor     eax, eax
0x18002edf1  jmp     loc_18002EECB
0x18002edf6  call    cs:__imp_TlsAlloc
0x18002edfc  mov     cs:?g_dwThreadEventIndex@@3KA, eax; ulong g_dwThreadEventIndex
0x18002ee02  call    cs:__imp_TlsAlloc
0x18002ee08  mov     cs:?g_dwThreadHandleIndex@@3KA, eax; ulong g_dwThreadHandleIndex
0x18002ee0e  call    cs:__imp_?MQUInitGlobalScurityVars@@YAXXZ; MQUInitGlobalScurityVars(void)
0x18002ee14  call    WPP_INIT_CONTROL_ARRAY
0x18002ee19  call    WPP_INIT_GUID_ARRAY
0x18002ee1e  lea     rcx, WPP_MAIN_CB
0x18002ee25  mov     cs:WPP_GLOBAL_Control, rcx
0x18002ee2c  call    WppInitUm
0x18002ee31  lea     rcx, QmpExceptionTranslator
0x18002ee38  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002ee3e  lea     rcx, QmpAbnormalTerminationHandler
0x18002ee45  jmp     short loc_18002EEC0
0x18002ee47  mov     rbx, cs:WPP_GLOBAL_Control
0x18002ee4e  lea     rdi, WPP_GLOBAL_Control
0x18002ee55  cmp     rbx, rdi
0x18002ee58  jz      short loc_18002EE82
0x18002ee5a  jmp     short loc_18002EE76
0x18002ee5c  mov     rcx, [rbx+8]; RegistrationHandle
0x18002ee60  test    rcx, rcx
0x18002ee63  jz      short loc_18002EE73
0x18002ee65  call    cs:__imp_UnregisterTraceGuids
0x18002ee6b  mov     qword ptr [rbx+8], 0
0x18002ee73  mov     rbx, [rbx]
0x18002ee76  test    rbx, rbx
0x18002ee79  jnz     short loc_18002EE5C
0x18002ee7b  mov     cs:WPP_GLOBAL_Control, rdi
0x18002ee82  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x18002ee88  call    cs:__imp_TlsGetValue
0x18002ee8e  test    rax, rax
0x18002ee91  jz      short loc_18002EE9C
0x18002ee93  mov     rcx, rax; hObject
0x18002ee96  call    cs:__imp_CloseHandle
0x18002ee9c  mov     ecx, cs:?g_dwThreadHandleIndex@@3KA; dwTlsIndex
0x18002eea2  call    cs:__imp_TlsGetValue
0x18002eea8  test    rax, rax
0x18002eeab  jz      short loc_18002EEB6
0x18002eead  mov     rcx, rax; hObject
0x18002eeb0  call    cs:__imp_CloseHandle
0x18002eeb6  xor     ecx, ecx
0x18002eeb8  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002eebe  xor     ecx, ecx
0x18002eec0  call    cs:__imp_?set_terminate@@YAP6AXXZP6AXXZ@Z; set_terminate(void (*)(void))
0x18002eec6  mov     eax, 1
0x18002eecb  mov     rbx, [rsp+28h+arg_0]
0x18002eed0  add     rsp, 20h
0x18002eed4  pop     rdi
0x18002eed5  retn
```
