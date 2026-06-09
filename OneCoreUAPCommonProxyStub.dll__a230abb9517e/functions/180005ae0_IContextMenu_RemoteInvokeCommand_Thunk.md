# IContextMenu_RemoteInvokeCommand_Thunk

- ea: `0x180005ae0`
- end: `0x180005b02`
- name: `IContextMenu_RemoteInvokeCommand_Thunk`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a418`

## pseudocode

```c
__int64 __fastcall IContextMenu_RemoteInvokeCommand_Thunk(__int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 136);
  result = IContextMenu_InvokeCommand_Stub(*(_QWORD *)v1, *(_QWORD *)(v1 + 8));
  *(_DWORD *)(v1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x180005ae0  push    rbx
0x180005ae2  sub     rsp, 20h
0x180005ae6  mov     rbx, [rcx+88h]
0x180005aed  mov     rdx, [rbx+8]
0x180005af1  mov     rcx, [rbx]
0x180005af4  call    IContextMenu_InvokeCommand_Stub
0x180005af9  mov     [rbx+10h], eax
0x180005afc  add     rsp, 20h
0x180005b00  pop     rbx
0x180005b01  retn
```
