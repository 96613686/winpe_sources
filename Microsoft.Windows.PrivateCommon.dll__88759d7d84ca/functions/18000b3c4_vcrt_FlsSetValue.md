# __vcrt_FlsSetValue

- ea: `0x18000b3c4`
- end: `0x18000b415`
- name: `__vcrt_FlsSetValue`
- size: `81`
- prototype: `int __fastcall(DWORD dwTlsIndex, LPVOID lpTlsValue)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f80`
- `0x180008fe4`
- `0x1800090b0`

## callees

- `0x18000b19c`
- `0x18000b3c4`
- `0x18000b930`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18000b404`
- `KERNEL32!TlsSetValue` at `0x18000b404`

## pseudocode

```c
int __fastcall _vcrt_FlsSetValue(DWORD dwTlsIndex, LPVOID lpTlsValue)
{
  __int64 (__fastcall *function)(_QWORD, LPVOID); // rax

  function = (__int64 (__fastcall *)(_QWORD, LPVOID))try_get_function(3, "FlsSetValue", &qword_18000E5B8, "FlsSetValue");
  if ( function )
    return function(dwTlsIndex, lpTlsValue);
  else
    return TlsSetValue(dwTlsIndex, lpTlsValue);
}

```

## disassembly

```asm
0x18000b3c4  mov     [rsp+arg_0], rbx
0x18000b3c9  push    rdi
0x18000b3ca  sub     rsp, 20h
0x18000b3ce  mov     rbx, rdx
0x18000b3d1  lea     r9, aFlssetvalue; "FlsSetValue"
0x18000b3d8  mov     edi, ecx
0x18000b3da  lea     rdx, aFlssetvalue; "FlsSetValue"
0x18000b3e1  mov     ecx, 3
0x18000b3e6  lea     r8, qword_18000E5B8
0x18000b3ed  call    try_get_function
0x18000b3f2  mov     rdx, rbx; lpTlsValue
0x18000b3f5  mov     ecx, edi; dwTlsIndex
0x18000b3f7  test    rax, rax
0x18000b3fa  jz      short loc_18000B404
0x18000b3fc  call    cs:__guard_dispatch_icall_fptr
0x18000b402  jmp     short loc_18000B40A
0x18000b404  call    cs:__imp_TlsSetValue
0x18000b40a  mov     rbx, [rsp+28h+arg_0]
0x18000b40f  add     rsp, 20h
0x18000b413  pop     rdi
0x18000b414  retn
```
