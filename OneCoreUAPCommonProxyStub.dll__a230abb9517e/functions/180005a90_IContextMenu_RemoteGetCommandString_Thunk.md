# IContextMenu_RemoteGetCommandString_Thunk

- ea: `0x180005a90`
- end: `0x180005ad1`
- name: `IContextMenu_RemoteGetCommandString_Thunk`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall IContextMenu_RemoteGetCommandString_Thunk(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  v1 = *(_QWORD **)(a1 + 136);
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)*v1 + 40LL))(
             *v1,
             v1[1],
             *((unsigned int *)v1 + 4),
             v1[3],
             v1[4],
             *((_DWORD *)v1 + 10));
  *((_DWORD *)v1 + 12) = result;
  return result;
}

```

## disassembly

```asm
0x180005a90  push    rbx
0x180005a92  sub     rsp, 40h
0x180005a96  mov     rbx, [rcx+88h]
0x180005a9d  mov     edx, [rbx+28h]
0x180005aa0  mov     rcx, [rbx]
0x180005aa3  mov     r9, [rbx+18h]
0x180005aa7  mov     r8d, [rbx+10h]
0x180005aab  mov     [rsp+48h+var_20], edx
0x180005aaf  mov     rdx, [rbx+20h]
0x180005ab3  mov     rax, [rcx]
0x180005ab6  mov     [rsp+48h+var_28], rdx
0x180005abb  mov     rdx, [rbx+8]
0x180005abf  mov     rax, [rax+28h]
0x180005ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac8  mov     [rbx+30h], eax
0x180005acb  add     rsp, 40h
0x180005acf  pop     rbx
0x180005ad0  retn
```
