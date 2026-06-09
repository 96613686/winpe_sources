# std::_Func_impl_no_alloc__lambda_e40c150deeab14f20632ebcbf49da901__void_::_Do_call

- ea: `0x18003b9b0`
- end: `0x18003ba02`
- name: `std::_Func_impl_no_alloc__lambda_e40c150deeab14f20632ebcbf49da901__void_::_Do_call`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18002a2a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall std::_Func_impl_no_alloc__lambda_e40c150deeab14f20632ebcbf49da901__void_::_Do_call(__int64 a1)
{
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF
  HSTRING v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  string = 0;
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    a1 + 8,
    1,
    &string,
    &v3);
  WindowsDeleteString(string);
  string = 0;
  return WindowsDeleteString(v3);
}

```

## disassembly

```asm
0x18003b9b0  mov     rax, rsp
0x18003b9b3  sub     rsp, 28h
0x18003b9b7  mov     qword ptr [rax+10h], 0
0x18003b9bf  mov     qword ptr [rax+8], 0
0x18003b9c7  add     rcx, 8
0x18003b9cb  lea     r9, [rax+10h]
0x18003b9cf  lea     r8, [rax+8]
0x18003b9d3  mov     edx, 1
0x18003b9d8  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18003b9dd  nop
0x18003b9de  mov     rcx, [rsp+28h+string]; string
0x18003b9e3  call    cs:__imp_WindowsDeleteString
0x18003b9e9  mov     [rsp+28h+string], 0
0x18003b9f2  mov     rcx, [rsp+28h+arg_8]; string
0x18003b9f7  call    cs:__imp_WindowsDeleteString
0x18003b9fd  add     rsp, 28h
0x18003ba01  retn
```
