# CPrintCoreConfig::GetUIInfo(void)

- ea: `0x180034384`
- end: `0x1800343c2`
- name: `?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ`
- size: `62`
- prototype: `struct _UIINFO *__fastcall(CPrintCoreConfig *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d8a4`
- `0x18002e0c0`
- `0x18002e640`
- `0x1800327c4`
- `0x180032d10`
- `0x180032e50`
- `0x180033100`
- `0x1800338b0`
- `0x180033d58`

## callees

- `0x180034358`
- `0x180034384`

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
0x180034384  mov     [rsp+arg_0], rbx
0x180034389  push    rdi
0x18003438a  sub     rsp, 20h
0x18003438e  mov     rdi, rcx
0x180034391  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x180034396  cmp     dword ptr [rax+38h], 0
0x18003439a  jz      short loc_1800343B4
0x18003439c  mov     rcx, rdi; this
0x18003439f  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x1800343a4  mov     rcx, rdi; this
0x1800343a7  mov     ebx, [rax+38h]
0x1800343aa  call    ?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ; CPrintCoreConfig::GetInfoHeader(void)
0x1800343af  add     rax, rbx
0x1800343b2  jmp     short loc_1800343B6
0x1800343b4  xor     eax, eax
0x1800343b6  mov     rbx, [rsp+28h+arg_0]
0x1800343bb  add     rsp, 20h
0x1800343bf  pop     rdi
0x1800343c0  retn
```
