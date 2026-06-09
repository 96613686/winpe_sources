# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180007d34`
- end: `0x180007d53`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180044feb`
- `0x1800450b1`
- `0x1800450c3`
- `0x1800452c6`
- `0x1800453f2`
- `0x180045404`
- `0x180046453`
- `0x180046489`
- `0x1800467c7`
- `0x1800468b1`
- `0x180046a21`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180007d34  push    rbx
0x180007d36  sub     rsp, 20h
0x180007d3a  mov     rbx, rcx
0x180007d3d  mov     rcx, [rcx]; string
0x180007d40  call    cs:__imp_WindowsDeleteString
0x180007d46  mov     qword ptr [rbx], 0
0x180007d4d  add     rsp, 20h
0x180007d51  pop     rbx
0x180007d52  retn
```
