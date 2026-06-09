# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180039e10`
- end: `0x180039e57`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `71`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString, UINT32 length)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003932c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *string, PCNZWCH sourceString, UINT32 length)
{
  WindowsDeleteString(*string);
  *string = 0;
  return WindowsCreateString(sourceString, length, string);
}

```

## disassembly

```asm
0x180039e10  mov     [rsp+arg_0], rbx
0x180039e15  mov     [rsp+arg_8], rsi
0x180039e1a  push    rdi
0x180039e1b  sub     rsp, 20h
0x180039e1f  mov     edi, r8d
0x180039e22  mov     rsi, rdx
0x180039e25  mov     rbx, rcx
0x180039e28  mov     rcx, [rcx]; string
0x180039e2b  call    cs:__imp_WindowsDeleteString
0x180039e31  mov     qword ptr [rbx], 0
0x180039e38  mov     r8, rbx; string
0x180039e3b  mov     edx, edi; length
0x180039e3d  mov     rcx, rsi; sourceString
0x180039e40  call    cs:__imp_WindowsCreateString
0x180039e46  nop
0x180039e47  mov     rbx, [rsp+28h+arg_0]
0x180039e4c  mov     rsi, [rsp+28h+arg_8]
0x180039e51  add     rsp, 20h
0x180039e55  pop     rdi
0x180039e56  retn
```
