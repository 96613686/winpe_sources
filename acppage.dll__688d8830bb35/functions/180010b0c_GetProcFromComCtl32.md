# _GetProcFromComCtl32

- ea: `0x180010b0c`
- end: `0x180010b54`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010864`
- `0x180010950`
- `0x1800109a0`
- `0x1800109e4`
- `0x180010a70`

## callees

- `0x180010900`
- `0x180010b0c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010b40`
- `KERNEL32!GetProcAddress` at `0x180010b40`

## pseudocode

```c
FARPROC __fastcall GetProcFromComCtl32(FARPROC *a1, const CHAR *a2)
{
  HMODULE v4; // rcx
  FARPROC result; // rax

  v4 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(), (v4 = g_hinstCC) != 0) )
    result = GetProcAddress(v4, a2);
  else
    result = 0;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180010b0c  mov     [rsp+arg_0], rbx
0x180010b11  push    rdi
0x180010b12  sub     rsp, 20h
0x180010b16  mov     rbx, rcx
0x180010b19  mov     rdi, rdx
0x180010b1c  mov     rcx, cs:g_hinstCC; hModule
0x180010b23  test    rcx, rcx
0x180010b26  jnz     short loc_180010B3D
0x180010b28  call    DelayLoadCC
0x180010b2d  mov     rcx, cs:g_hinstCC
0x180010b34  test    rcx, rcx
0x180010b37  jnz     short loc_180010B3D
0x180010b39  xor     eax, eax
0x180010b3b  jmp     short loc_180010B46
0x180010b3d  mov     rdx, rdi; lpProcName
0x180010b40  call    cs:__imp_GetProcAddress
0x180010b46  mov     [rbx], rax
0x180010b49  mov     rbx, [rsp+28h+arg_0]
0x180010b4e  add     rsp, 20h
0x180010b52  pop     rdi
0x180010b53  retn
```
