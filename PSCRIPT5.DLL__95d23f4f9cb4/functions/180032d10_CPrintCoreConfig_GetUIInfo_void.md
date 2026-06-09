# CPrintCoreConfig::GetUIInfo(void)

- ea: `0x180032d10`
- end: `0x180032d4d`
- name: `?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ`
- size: `61`
- prototype: `struct _UIINFO *__fastcall(CPrintCoreConfig *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c484`
- `0x18002cca0`
- `0x18002d220`
- `0x180031170`
- `0x1800316c0`
- `0x180031800`
- `0x180031aa0`
- `0x180032250`
- `0x1800326f8`

## callees

- `0x180032ce4`
- `0x180032d10`

## pseudocode

```c
struct _UIINFO *__fastcall CPrintCoreConfig::GetUIInfo(CPrintCoreConfig *this)
{
  __int64 v2; // rbx

  if ( !*((_DWORD *)CPrintCoreConfig::GetInfoHeader(this) + 14) )
    return 0;
  v2 = *((unsigned int *)CPrintCoreConfig::GetInfoHeader(this) + 14);
  return (struct _INFOHEADER *)((char *)CPrintCoreConfig::GetInfoHeader(this) + v2);
}

```

## disassembly

```asm
0x180032d10  mov     [rsp+arg_0], rbx
0x180032d15  push    rdi
0x180032d16  sub     rsp, 20h
0x180032d1a  mov     rdi, rcx
0x180032d1d  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x180032d22  cmp     dword ptr [rax+38h], 0
0x180032d26  jz      short loc_180032D40
0x180032d28  mov     rcx, rdi; this
0x180032d2b  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x180032d30  mov     rcx, rdi; this
0x180032d33  mov     ebx, [rax+38h]
0x180032d36  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x180032d3b  add     rax, rbx
0x180032d3e  jmp     short loc_180032D42
0x180032d40  xor     eax, eax
0x180032d42  mov     rbx, [rsp+28h+arg_0]
0x180032d47  add     rsp, 20h
0x180032d4b  pop     rdi
0x180032d4c  retn
```
