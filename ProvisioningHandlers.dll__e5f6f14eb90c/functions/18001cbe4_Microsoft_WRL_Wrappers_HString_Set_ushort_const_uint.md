# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18001cbe4`
- end: `0x18001cc35`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e7a8`
- `0x180021020`
- `0x180021110`
- `0x1800211b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001cc29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cbff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cbff`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  WindowsDeleteString(*this);
  *this = 0;
  return WindowsCreateString(a2, a3, this);
}

```

## disassembly

```asm
0x18001cbe4  mov     [rsp+arg_0], rbx
0x18001cbe9  mov     [rsp+arg_8], rsi
0x18001cbee  push    rdi
0x18001cbef  sub     rsp, 20h
0x18001cbf3  mov     rbx, rcx
0x18001cbf6  mov     edi, r8d
0x18001cbf9  mov     rcx, [rcx]; string
0x18001cbfc  mov     rsi, rdx
0x18001cbff  call    cs:__imp_WindowsDeleteString
0x18001cc06  nop     dword ptr [rax+rax+00h]
0x18001cc0b  mov     r8, rbx
0x18001cc0e  mov     qword ptr [rbx], 0
0x18001cc15  mov     edx, edi
0x18001cc17  mov     rcx, rsi
0x18001cc1a  mov     rbx, [rsp+28h+arg_0]
0x18001cc1f  mov     rsi, [rsp+28h+arg_8]
0x18001cc24  add     rsp, 20h
0x18001cc28  pop     rdi
0x18001cc29  jmp     cs:__imp_WindowsCreateString
```
