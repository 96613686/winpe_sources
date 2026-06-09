# _GetProcFromComCtl32

- ea: `0x180012dd4`
- end: `0x180012e1c`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012d14`
- `0x180012d6c`

## callees

- `0x180012c5c`
- `0x180012dd4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180012e08`
- `KERNEL32!GetProcAddress` at `0x180012e08`

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
0x180012dd4  mov     [rsp+arg_0], rbx
0x180012dd9  push    rdi
0x180012dda  sub     rsp, 20h
0x180012dde  mov     rbx, rcx
0x180012de1  mov     rdi, rdx
0x180012de4  mov     rcx, cs:g_hinstCC; hModule
0x180012deb  test    rcx, rcx
0x180012dee  jnz     short loc_180012E05
0x180012df0  call    DelayLoadCC
0x180012df5  mov     rcx, cs:g_hinstCC
0x180012dfc  test    rcx, rcx
0x180012dff  jnz     short loc_180012E05
0x180012e01  xor     eax, eax
0x180012e03  jmp     short loc_180012E0E
0x180012e05  mov     rdx, rdi; lpProcName
0x180012e08  call    cs:__imp_GetProcAddress
0x180012e0e  mov     [rbx], rax
0x180012e11  mov     rbx, [rsp+28h+arg_0]
0x180012e16  add     rsp, 20h
0x180012e1a  pop     rdi
0x180012e1b  retn
```
