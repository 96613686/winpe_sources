# WinStoreAuth::_unnamed_type_g_rgSlsData_::~_unnamed_type_g_rgSlsData_(void)

- ea: `0x1800399c0`
- end: `0x1800399e1`
- name: `??1_unnamed_type_g_rgSlsData_@WinStoreAuth@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399cd`

## pseudocode

```c
void __fastcall WinStoreAuth::_unnamed_type_g_rgSlsData_::~_unnamed_type_g_rgSlsData_(HSTRING *this)
{
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x1800399c0  push    rbx
0x1800399c2  sub     rsp, 20h
0x1800399c6  mov     rbx, rcx
0x1800399c9  mov     rcx, [rcx+8]; string
0x1800399cd  call    cs:__imp_WindowsDeleteString
0x1800399d3  mov     qword ptr [rbx+8], 0
0x1800399db  add     rsp, 20h
0x1800399df  pop     rbx
0x1800399e0  retn
```
