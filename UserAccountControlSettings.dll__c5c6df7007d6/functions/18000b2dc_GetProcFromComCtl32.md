# _GetProcFromComCtl32

- ea: `0x18000b2dc`
- end: `0x18000b324`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: `FARPROC __fastcall(FARPROC *, const CHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003a18`
- `0x180003db0`
- `0x18000b274`

## callees

- `0x18000b224`
- `0x18000b2dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b310`

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
0x18000b2dc  mov     [rsp+arg_0], rbx
0x18000b2e1  push    rdi
0x18000b2e2  sub     rsp, 20h
0x18000b2e6  mov     rbx, rcx
0x18000b2e9  mov     rdi, rdx
0x18000b2ec  mov     rcx, cs:g_hinstCC; hModule
0x18000b2f3  test    rcx, rcx
0x18000b2f6  jnz     short loc_18000B30D
0x18000b2f8  call    DelayLoadCC
0x18000b2fd  mov     rcx, cs:g_hinstCC
0x18000b304  test    rcx, rcx
0x18000b307  jnz     short loc_18000B30D
0x18000b309  xor     eax, eax
0x18000b30b  jmp     short loc_18000B316
0x18000b30d  mov     rdx, rdi; lpProcName
0x18000b310  call    cs:__imp_GetProcAddress
0x18000b316  mov     [rbx], rax
0x18000b319  mov     rbx, [rsp+28h+arg_0]
0x18000b31e  add     rsp, 20h
0x18000b322  pop     rdi
0x18000b323  retn
```
