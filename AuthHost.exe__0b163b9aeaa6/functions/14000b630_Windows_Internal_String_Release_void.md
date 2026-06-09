# Windows::Internal::String::Release(void)

- ea: `0x14000b630`
- end: `0x14000b654`
- name: `?Release@String@Internal@Windows@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bb4c`

## callees

- `0x14000b630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000b641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000b641`

## pseudocode

```c
void __fastcall Windows::Internal::String::Release(HSTRING *this)
{
  HSTRING v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    WindowsDeleteString(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x14000b630  push    rbx
0x14000b632  sub     rsp, 20h
0x14000b636  mov     rbx, rcx
0x14000b639  mov     rcx, [rcx]; string
0x14000b63c  test    rcx, rcx
0x14000b63f  jz      short loc_14000B64E
0x14000b641  call    cs:__imp_WindowsDeleteString
0x14000b647  mov     qword ptr [rbx], 0
0x14000b64e  add     rsp, 20h
0x14000b652  pop     rbx
0x14000b653  retn
```
