# AspUndoRevertHack(void * *)

- ea: `0x1800033e8`
- end: `0x18000341e`
- name: `?AspUndoRevertHack@@YAXPEAPEAX@Z`
- size: `54`
- prototype: `void __fastcall(void **)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001400`
- `0x180002ae8`
- `0x180003314`
- `0x180003e78`
- `0x1800041e8`
- `0x1800054e8`
- `0x180010630`
- `0x18001650c`
- `0x18004367c`
- `0x180043738`
- `0x180043974`
- `0x180060094`

## callees

- `0x1800033e8`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180003406`
- `ADVAPI32!SetThreadToken` at `0x180003406`
- `KERNEL32!CloseHandle` at `0x18000340f`
- `KERNEL32!CloseHandle` at `0x18000340f`

## pseudocode

```c
void __fastcall AspUndoRevertHack(void **a1)
{
  if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    SetThreadToken(0, *a1);
    CloseHandle(*a1);
    *a1 = (void *)-1LL;
  }
}

```

## disassembly

```asm
0x1800033e8  push    rbx
0x1800033ea  sub     rsp, 20h
0x1800033ee  mov     rdx, [rcx]; Token
0x1800033f1  mov     rbx, rcx
0x1800033f4  lea     rax, [rdx-1]
0x1800033f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800033fc  jbe     short loc_180003404
0x1800033fe  add     rsp, 20h
0x180003402  pop     rbx
0x180003403  retn
0x180003404  xor     ecx, ecx; Thread
0x180003406  call    cs:__imp_SetThreadToken
0x18000340c  mov     rcx, [rbx]; hObject
0x18000340f  call    cs:__imp_CloseHandle
0x180003415  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000341c  jmp     short loc_1800033FE
```
