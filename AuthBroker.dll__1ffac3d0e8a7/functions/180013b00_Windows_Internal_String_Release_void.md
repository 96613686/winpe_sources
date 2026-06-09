# Windows::Internal::String::Release(void)

- ea: `0x180013b00`
- end: `0x180013b24`
- name: `?Release@String@Internal@Windows@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(Windows::Internal::String *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012ad0`
- `0x18001ecc8`

## callees

- `0x180013b00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b11`

## pseudocode

```c
void __fastcall Windows::Internal::String::Release(Windows::Internal::String *this)
{
  HSTRING__ *hstring; // rcx

  hstring = this->_hstring;
  if ( hstring )
  {
    WindowsDeleteString(hstring);
    this->_hstring = 0;
  }
}

```

## disassembly

```asm
0x180013b00  push    rbx
0x180013b02  sub     rsp, 20h
0x180013b06  mov     rbx, this
0x180013b09  mov     this, [this]; string
0x180013b0c  test    this, this
0x180013b0f  jz      short loc_180013B1E
0x180013b11  call    cs:__imp_WindowsDeleteString
0x180013b17  mov     qword ptr [rbx], 0
0x180013b1e  add     rsp, 20h
0x180013b22  pop     rbx
0x180013b23  retn
```
