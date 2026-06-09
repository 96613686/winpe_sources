# NotifyServiceStatusChangeCallback(void *)

- ea: `0x140008960`
- end: `0x14000896b`
- name: `?NotifyServiceStatusChangeCallback@@YAXPEAX@Z`
- size: `11`
- prototype: `void __fastcall(_DWORD **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall NotifyServiceStatusChangeCallback(_DWORD **a1)
{
  *a1[2] = 1;
}

```

## disassembly

```asm
0x140008960  mov     rax, [rcx+10h]
0x140008964  mov     dword ptr [rax], 1
0x14000896a  retn
```
