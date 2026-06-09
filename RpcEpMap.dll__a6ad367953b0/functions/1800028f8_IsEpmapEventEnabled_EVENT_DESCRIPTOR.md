# IsEpmapEventEnabled(_EVENT_DESCRIPTOR *)

- ea: `0x1800028f8`
- end: `0x18000291d`
- name: `?IsEpmapEventEnabled@@YAHPEAU_EVENT_DESCRIPTOR@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(struct _EVENT_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002350`
- `0x180002864`
- `0x180005b24`
- `0x18000804c`

## callees

- `0x1800028f8`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000290b`
- `ntdll!EtwEventEnabled` at `0x18000290b`

## pseudocode

```c
__int64 __fastcall IsEpmapEventEnabled(struct _EVENT_DESCRIPTOR *a1)
{
  if ( g_EpmapEtwHandle )
    return (unsigned __int8)EtwEventEnabled(g_EpmapEtwHandle, a1);
  else
    return 0;
}

```

## disassembly

```asm
0x1800028f8  sub     rsp, 28h
0x1800028fc  mov     rdx, rcx
0x1800028ff  mov     rcx, cs:g_EpmapEtwHandle
0x180002906  test    rcx, rcx
0x180002909  jz      short loc_180002919
0x18000290b  call    cs:__imp_EtwEventEnabled
0x180002911  movzx   eax, al
0x180002914  add     rsp, 28h
0x180002918  retn
0x180002919  xor     eax, eax
0x18000291b  jmp     short loc_180002914
```
