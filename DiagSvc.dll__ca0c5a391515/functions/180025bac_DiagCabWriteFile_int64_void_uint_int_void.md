# DiagCabWriteFile(__int64,void *,uint,int *,void *)

- ea: `0x180025bac`
- end: `0x180025bdd`
- name: `?DiagCabWriteFile@@YAI_JPEAXIPEAH1@Z`
- size: `49`
- prototype: `__int64 __fastcall(int, void *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180025740`

## callees

- `0x180025bac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__write` at `0x180025bb9`
- `api-ms-win-crt-private-l1-1-0!_o__write` at `0x180025bb9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025bc6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025bc6`

## pseudocode

```c
__int64 __fastcall DiagCabWriteFile(int a1, void *a2, unsigned int a3, int *a4)
{
  unsigned int v5; // ebx

  v5 = _write(a1, a2, a3);
  if ( v5 == -1 )
    *a4 = *(_DWORD *)_o__errno();
  return v5;
}

```

## disassembly

```asm
0x180025bac  mov     [rsp+arg_0], rbx
0x180025bb1  push    rdi
0x180025bb2  sub     rsp, 20h
0x180025bb6  mov     rdi, r9
0x180025bb9  call    cs:__imp__write
0x180025bbf  mov     ebx, eax
0x180025bc1  cmp     eax, 0FFFFFFFFh
0x180025bc4  jnz     short loc_180025BD0
0x180025bc6  call    cs:__imp__o__errno
0x180025bcc  mov     ecx, [rax]
0x180025bce  mov     [rdi], ecx
0x180025bd0  mov     eax, ebx
0x180025bd2  mov     rbx, [rsp+28h+arg_0]
0x180025bd7  add     rsp, 20h
0x180025bdb  pop     rdi
0x180025bdc  retn
```
