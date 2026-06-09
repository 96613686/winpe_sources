# StateWebServer::ServiceMain(ulong,ushort * *)

- ea: `0x140001cf0`
- end: `0x140001d01`
- name: `?ServiceMain@StateWebServer@@CAXKPEAPEAG@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140001a20`

## pseudocode

```c
void __fastcall StateWebServer::ServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  StateWebServer::DoServiceMain(StateWebServer::s_pstweb, a1, a2);
}

```

## disassembly

```asm
0x140001cf0  mov     r8, rdx; unsigned __int16 **
0x140001cf3  mov     edx, ecx; unsigned int
0x140001cf5  mov     rcx, cs:?s_pstweb@StateWebServer@@0PEAV1@EA; this
0x140001cfc  jmp     ?DoServiceMain@StateWebServer@@AEAAXKPEAPEAG@Z; StateWebServer::DoServiceMain(ulong,ushort * *)
```
