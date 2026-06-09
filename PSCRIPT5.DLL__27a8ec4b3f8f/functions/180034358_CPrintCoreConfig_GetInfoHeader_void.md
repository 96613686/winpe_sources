# CPrintCoreConfig::GetInfoHeader(void)

- ea: `0x180034358`
- end: `0x18003437e`
- name: `?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ`
- size: `38`
- prototype: `struct _INFOHEADER *__fastcall(CPrintCoreConfig *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d8a4`
- `0x18002d9d0`
- `0x18002db10`
- `0x18002dbf0`
- `0x180034384`

## callees

- `0x180034358`
- `0x18005f010`

## pseudocode

```c
struct _INFOHEADER *__fastcall CPrintCoreConfig::GetInfoHeader(CPrintCoreConfig *this)
{
  struct _INFOHEADER *result; // rax

  result = (struct _INFOHEADER *)*((_QWORD *)this + 132);
  if ( !result )
    return (struct _INFOHEADER *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 1) + 24LL))(*(_QWORD *)this);
  return result;
}

```

## disassembly

```asm
0x180034358  sub     rsp, 28h
0x18003435c  mov     rax, [rcx+420h]
0x180034363  test    rax, rax
0x180034366  jnz     short loc_180034378
0x180034368  mov     rax, [rcx+8]
0x18003436c  mov     rcx, [rcx]
0x18003436f  mov     rax, [rax+18h]
0x180034373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034378  add     rsp, 28h
0x18003437c  retn
```
