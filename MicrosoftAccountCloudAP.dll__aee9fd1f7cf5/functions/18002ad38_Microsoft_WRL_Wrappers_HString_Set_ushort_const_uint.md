# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18002ad38`
- end: `0x18002ad7e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002a974`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ad77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad53`

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
0x18002ad38  mov     [rsp+arg_0], rbx
0x18002ad3d  mov     [rsp+arg_8], rsi
0x18002ad42  push    rdi
0x18002ad43  sub     rsp, 20h
0x18002ad47  mov     rbx, rcx
0x18002ad4a  mov     edi, r8d
0x18002ad4d  mov     rcx, [rcx]; string
0x18002ad50  mov     rsi, rdx
0x18002ad53  call    cs:__imp_WindowsDeleteString
0x18002ad59  mov     r8, rbx
0x18002ad5c  mov     qword ptr [rbx], 0
0x18002ad63  mov     edx, edi
0x18002ad65  mov     rcx, rsi
0x18002ad68  mov     rbx, [rsp+28h+arg_0]
0x18002ad6d  mov     rsi, [rsp+28h+arg_8]
0x18002ad72  add     rsp, 20h
0x18002ad76  pop     rdi
0x18002ad77  jmp     cs:__imp_WindowsCreateString
```
