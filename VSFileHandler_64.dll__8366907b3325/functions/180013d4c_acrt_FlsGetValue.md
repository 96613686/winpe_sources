# __acrt_FlsGetValue

- ea: `0x180013d4c`
- end: `0x180013d92`
- name: `__acrt_FlsGetValue`
- size: `70`
- prototype: ``
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
- `0x180013d4c`
- `0x1800241c0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180013d8b`

## pseudocode

```c
LPVOID __fastcall _acrt_FlsGetValue(DWORD a1)
{
  FARPROC function_0; // rax

  function_0 = try_get_function_0(5u, "FlsGetValue", (unsigned int *)&unk_180028C80, (unsigned int *)&unk_180028C88);
  if ( function_0 )
    return (LPVOID)((__int64 (__fastcall *)(_QWORD))function_0)(a1);
  else
    return TlsGetValue(a1);
}

```

## disassembly

```asm
0x180013d4c  push    rbx
0x180013d4e  sub     rsp, 20h
0x180013d52  mov     ebx, ecx
0x180013d54  lea     r9, unk_180028C88
0x180013d5b  mov     ecx, 5
0x180013d60  lea     r8, unk_180028C80
0x180013d67  lea     rdx, aFlsgetvalue; "FlsGetValue"
0x180013d6e  call    try_get_function_0
0x180013d73  mov     ecx, ebx
0x180013d75  test    rax, rax
0x180013d78  jz      short loc_180013D86
0x180013d7a  add     rsp, 20h
0x180013d7e  pop     rbx
0x180013d7f  jmp     cs:__guard_dispatch_icall_fptr
0x180013d86  add     rsp, 20h
0x180013d8a  pop     rbx
0x180013d8b  jmp     cs:__imp_TlsGetValue
```
