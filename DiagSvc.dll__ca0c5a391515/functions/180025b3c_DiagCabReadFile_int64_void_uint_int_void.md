# DiagCabReadFile(__int64,void *,uint,int *,void *)

- ea: `0x180025b3c`
- end: `0x180025b6d`
- name: `?DiagCabReadFile@@YAI_JPEAXIPEAH1@Z`
- size: `49`
- prototype: `__int64 __fastcall(int, void *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800256e0`

## callees

- `0x180025b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__read` at `0x180025b49`
- `api-ms-win-crt-private-l1-1-0!_o__read` at `0x180025b49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025b56`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025b56`

## pseudocode

```c
__int64 __fastcall DiagCabReadFile(int a1, void *a2, unsigned int a3, int *a4)
{
  unsigned int v5; // ebx

  v5 = _read(a1, a2, a3);
  if ( v5 == -1 )
    *a4 = *(_DWORD *)_o__errno();
  return v5;
}

```

## disassembly

```asm
0x180025b3c  mov     [rsp+arg_0], rbx
0x180025b41  push    rdi
0x180025b42  sub     rsp, 20h
0x180025b46  mov     rdi, r9
0x180025b49  call    cs:__imp__read
0x180025b4f  mov     ebx, eax
0x180025b51  cmp     eax, 0FFFFFFFFh
0x180025b54  jnz     short loc_180025B60
0x180025b56  call    cs:__imp__o__errno
0x180025b5c  mov     ecx, [rax]
0x180025b5e  mov     [rdi], ecx
0x180025b60  mov     eax, ebx
0x180025b62  mov     rbx, [rsp+28h+arg_0]
0x180025b67  add     rsp, 20h
0x180025b6b  pop     rdi
0x180025b6c  retn
```
