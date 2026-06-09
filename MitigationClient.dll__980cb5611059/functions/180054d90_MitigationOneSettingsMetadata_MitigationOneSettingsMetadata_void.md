# MitigationOneSettingsMetadata::~MitigationOneSettingsMetadata(void)

- ea: `0x180054d90`
- end: `0x180054e00`
- name: `??1MitigationOneSettingsMetadata@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(MitigationOneSettingsMetadata *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180054f30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054de5`

## pseudocode

```c
void __fastcall MitigationOneSettingsMetadata::~MitigationOneSettingsMetadata(HSTRING *this)
{
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180054d90  push    rbx
0x180054d92  sub     rsp, 20h
0x180054d96  mov     rbx, rcx
0x180054d99  mov     rcx, [rcx+30h]; string
0x180054d9d  call    cs:__imp_WindowsDeleteString
0x180054da3  mov     qword ptr [rbx+30h], 0
0x180054dab  mov     rcx, [rbx+28h]; string
0x180054daf  call    cs:__imp_WindowsDeleteString
0x180054db5  mov     qword ptr [rbx+28h], 0
0x180054dbd  mov     rcx, [rbx+20h]; string
0x180054dc1  call    cs:__imp_WindowsDeleteString
0x180054dc7  mov     qword ptr [rbx+20h], 0
0x180054dcf  mov     rcx, [rbx+18h]; string
0x180054dd3  call    cs:__imp_WindowsDeleteString
0x180054dd9  mov     qword ptr [rbx+18h], 0
0x180054de1  mov     rcx, [rbx+10h]; string
0x180054de5  call    cs:__imp_WindowsDeleteString
0x180054deb  mov     qword ptr [rbx+10h], 0
0x180054df3  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180054dfa  add     rsp, 20h
0x180054dfe  pop     rbx
0x180054dff  retn
```
