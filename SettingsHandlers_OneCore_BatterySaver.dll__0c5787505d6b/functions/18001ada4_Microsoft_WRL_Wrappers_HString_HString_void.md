# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001ada4`
- end: `0x18001adc3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180048482`
- `0x180048494`
- `0x180048533`
- `0x1800487d3`
- `0x180048af3`
- `0x180048d0c`
- `0x180049031`
- `0x1800492a4`
- `0x1800497f9`
- `0x180049848`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001adb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001adb0`

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
0x18001ada4  push    rbx
0x18001ada6  sub     rsp, 20h
0x18001adaa  mov     rbx, rcx
0x18001adad  mov     rcx, [rcx]; string
0x18001adb0  call    cs:__imp_WindowsDeleteString
0x18001adb6  mov     qword ptr [rbx], 0
0x18001adbd  add     rsp, 20h
0x18001adc1  pop     rbx
0x18001adc2  retn
```
