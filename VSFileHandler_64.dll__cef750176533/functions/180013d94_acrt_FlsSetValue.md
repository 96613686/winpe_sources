# __acrt_FlsSetValue

- ea: `0x180013d94`
- end: `0x180013de5`
- name: `__acrt_FlsSetValue`
- size: `81`
- prototype: `int __fastcall(DWORD dwTlsIndex, LPVOID lpTlsValue)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010260`
- `0x1800102a4`
- `0x180010378`
- `0x180010420`

## callees

- `0x180013a58`
- `0x180013d94`
- `0x1800241c0`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180013dd4`
- `KERNEL32!TlsSetValue` at `0x180013dd4`

## pseudocode

```c
int __fastcall _acrt_FlsSetValue(DWORD dwTlsIndex, LPVOID lpTlsValue)
{
  __int64 (__fastcall *function_0)(_QWORD, LPVOID); // rax

  function_0 = (__int64 (__fastcall *)(_QWORD, LPVOID))try_get_function_0(
                                                         6,
                                                         "FlsSetValue",
                                                         &qword_180028C88,
                                                         &qword_180028C90);
  if ( function_0 )
    return function_0(dwTlsIndex, lpTlsValue);
  else
    return TlsSetValue(dwTlsIndex, lpTlsValue);
}

```

## disassembly

```asm
0x180013d94  mov     [rsp+arg_0], rbx
0x180013d99  push    rdi
0x180013d9a  sub     rsp, 20h
0x180013d9e  mov     rbx, rdx
0x180013da1  lea     r9, qword_180028C90
0x180013da8  mov     edi, ecx
0x180013daa  lea     rdx, aFlssetvalue; "FlsSetValue"
0x180013db1  mov     ecx, 6
0x180013db6  lea     r8, qword_180028C88
0x180013dbd  call    try_get_function_0
0x180013dc2  mov     rdx, rbx; lpTlsValue
0x180013dc5  mov     ecx, edi; dwTlsIndex
0x180013dc7  test    rax, rax
0x180013dca  jz      short loc_180013DD4
0x180013dcc  call    cs:__guard_dispatch_icall_fptr
0x180013dd2  jmp     short loc_180013DDA
0x180013dd4  call    cs:__imp_TlsSetValue
0x180013dda  mov     rbx, [rsp+28h+arg_0]
0x180013ddf  add     rsp, 20h
0x180013de3  pop     rdi
0x180013de4  retn
```
