# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18001f9fc`
- end: `0x18001fa42`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f014`
- `0x18001f424`

## callees

- `0x18001f9fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001fa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001fa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fa1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fa1e`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *newString, HSTRING *a2)
{
  HRESULT result; // eax

  if ( !*a2 || (result = 0, *a2 != *newString) )
  {
    WindowsDeleteString(*newString);
    *newString = 0;
    return WindowsDuplicateString(*a2, newString);
  }
  return result;
}

```

## disassembly

```asm
0x18001f9fc  mov     [rsp+arg_0], rbx
0x18001fa01  push    rdi
0x18001fa02  sub     rsp, 20h
0x18001fa06  mov     rbx, rcx
0x18001fa09  mov     rdi, rdx
0x18001fa0c  mov     rcx, [rdx]
0x18001fa0f  test    rcx, rcx
0x18001fa12  jz      short loc_18001FA1B
0x18001fa14  xor     eax, eax
0x18001fa16  cmp     rcx, [rbx]
0x18001fa19  jz      short loc_18001FA37
0x18001fa1b  mov     rcx, [rbx]; string
0x18001fa1e  call    cs:__imp_WindowsDeleteString
0x18001fa24  mov     qword ptr [rbx], 0
0x18001fa2b  mov     rdx, rbx; newString
0x18001fa2e  mov     rcx, [rdi]; string
0x18001fa31  call    cs:__imp_WindowsDuplicateString
0x18001fa37  mov     rbx, [rsp+28h+arg_0]
0x18001fa3c  add     rsp, 20h
0x18001fa40  pop     rdi
0x18001fa41  retn
```
