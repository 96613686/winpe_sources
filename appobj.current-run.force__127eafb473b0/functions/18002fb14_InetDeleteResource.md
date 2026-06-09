# InetDeleteResource

- ea: `0x18002fb14`
- end: `0x18002fb4a`
- name: `InetDeleteResource`
- size: `54`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002020`

## callees

- `0x180034cbe`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fb1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fb1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fb31`

## pseudocode

```c
void *__fastcall InetDeleteResource(struct _RTL_CRITICAL_SECTION *a1)
{
  DeleteCriticalSection(a1);
  CloseHandle(a1[1].DebugInfo);
  CloseHandle(a1[1].OwningThread);
  return memset_0(a1, 0, 0x60u);
}

```

## disassembly

```asm
0x18002fb14  push    rbx
0x18002fb16  sub     rsp, 20h
0x18002fb1a  mov     rbx, rcx
0x18002fb1d  call    cs:__imp_DeleteCriticalSection
0x18002fb23  mov     rcx, [rbx+28h]; hObject
0x18002fb27  call    cs:__imp_CloseHandle
0x18002fb2d  mov     rcx, [rbx+38h]; hObject
0x18002fb31  call    cs:__imp_CloseHandle
0x18002fb37  xor     edx, edx; Val
0x18002fb39  mov     rcx, rbx; void *
0x18002fb3c  lea     r8d, [rdx+60h]; Size
0x18002fb40  add     rsp, 20h
0x18002fb44  pop     rbx
0x18002fb45  jmp     memset_0
```
