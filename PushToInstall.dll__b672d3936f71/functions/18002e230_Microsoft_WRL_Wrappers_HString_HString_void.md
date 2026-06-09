# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002e230`
- end: `0x18002e24f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004d21f`
- `0x18004da09`
- `0x18004dca2`
- `0x18004deae`
- `0x18004dec0`
- `0x18004ded2`
- `0x18004dee4`
- `0x18004df08`
- `0x18004df1a`
- `0x18004df2c`
- `0x18004df86`
- `0x18004df98`
- `0x18004dff2`
- `0x18004e004`
- `0x18004e0dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e23c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18002e230  push    rbx
0x18002e232  sub     rsp, 20h
0x18002e236  mov     rbx, rcx
0x18002e239  mov     rcx, [rcx]; string
0x18002e23c  call    cs:__imp_WindowsDeleteString
0x18002e242  mov     qword ptr [rbx], 0
0x18002e249  add     rsp, 20h
0x18002e24d  pop     rbx
0x18002e24e  retn
```
