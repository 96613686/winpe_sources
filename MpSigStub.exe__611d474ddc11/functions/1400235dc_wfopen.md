# _wfopen

- ea: `0x1400235dc`
- end: `0x1400235e7`
- name: `_wfopen`
- size: `11`
- prototype: `FILE *__cdecl(const wchar_t *Filename, const wchar_t *Mode)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400a5764`

## callees

- `0x140023510`

## pseudocode

```c
FILE *__cdecl wfopen(const wchar_t *Filename, const wchar_t *Mode)
{
  return (FILE *)common_fsopen<wchar_t>(Filename, Mode, 0x40u);
}

```

## disassembly

```asm
0x1400235dc  mov     r8d, 40h ; '@'
0x1400235e2  jmp     ??$common_fsopen@_W@@YAPEAU_iobuf@@QEB_W0H@Z
```
