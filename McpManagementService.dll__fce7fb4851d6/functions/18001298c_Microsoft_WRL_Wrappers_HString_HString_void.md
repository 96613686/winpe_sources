# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001298c`
- end: `0x1800129ab`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002895e`
- `0x180028982`
- `0x1800289a6`
- `0x1800289b8`
- `0x1800289ca`
- `0x180028b52`
- `0x180028be2`
- `0x1800292fd`
- `0x18002930f`
- `0x180029321`
- `0x1800293b1`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012998`

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
0x18001298c  push    rbx
0x18001298e  sub     rsp, 20h
0x180012992  mov     rbx, rcx
0x180012995  mov     rcx, [rcx]; string
0x180012998  call    cs:__imp_WindowsDeleteString
0x18001299e  mov     qword ptr [rbx], 0
0x1800129a5  add     rsp, 20h
0x1800129a9  pop     rbx
0x1800129aa  retn
```
