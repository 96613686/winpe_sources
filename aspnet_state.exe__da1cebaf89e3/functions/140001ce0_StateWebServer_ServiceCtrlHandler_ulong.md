# StateWebServer::ServiceCtrlHandler(ulong)

- ea: `0x140001ce0`
- end: `0x140001cee`
- name: `?ServiceCtrlHandler@StateWebServer@@CAXK@Z`
- size: `14`
- prototype: `void __fastcall(int dwControl)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140001994`

## pseudocode

```c
void __fastcall StateWebServer::ServiceCtrlHandler(int dwControl)
{
  StateWebServer::DoServiceCtrlHandler(StateWebServer::s_pstweb, dwControl);
}

```

## disassembly

```asm
0x140001ce0  mov     edx, ecx; unsigned int
0x140001ce2  mov     rcx, cs:?s_pstweb@StateWebServer@@0PEAV1@EA; this
0x140001ce9  jmp     ?DoServiceCtrlHandler@StateWebServer@@AEAAXK@Z; StateWebServer::DoServiceCtrlHandler(ulong)
```
