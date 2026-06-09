# McGenEventRegister_EtwRegister

- ea: `0x140001488`
- end: `0x1400014c1`
- name: `McGenEventRegister_EtwRegister`
- size: `57`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000c614`

## callees

- `0x140001488`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x1400014af`
- `ntoskrnl!EtwRegister` at `0x1400014af`

## pseudocode

```c
NTSTATUS McGenEventRegister_EtwRegister()
{
  NTSTATUS result; // eax

  result = 0;
  if ( !UevAgentDriver_Context )
    return EtwRegister(&UevAgentDriver, McGenControlCallbackV2, &UevAgentDriver_Context, &UevAgentDriver_Context);
  return result;
}

```

## disassembly

```asm
0x140001488  sub     rsp, 28h
0x14000148c  xor     eax, eax
0x14000148e  cmp     cs:UevAgentDriver_Context, rax
0x140001495  jnz     short loc_1400014BB
0x140001497  lea     r8, UevAgentDriver_Context; CallbackContext
0x14000149e  mov     r9, r8; RegHandle
0x1400014a1  lea     rdx, McGenControlCallbackV2; EnableCallback
0x1400014a8  lea     rcx, UevAgentDriver; ProviderId
0x1400014af  call    cs:__imp_EtwRegister
0x1400014b6  nop     dword ptr [rax+rax+00h]
0x1400014bb  add     rsp, 28h
0x1400014bf  retn
```
