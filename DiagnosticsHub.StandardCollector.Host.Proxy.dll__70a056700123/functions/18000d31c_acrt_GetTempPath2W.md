# __acrt_GetTempPath2W

- ea: `0x18000d31c`
- end: `0x18000d381`
- name: `__acrt_GetTempPath2W`
- size: `101`
- prototype: `__int64 __fastcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c8f8`
- `0x18000d31c`
- `0x180060150`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x18000d370`
- `KERNEL32!GetTempPathW` at `0x18000d370`

## string_xrefs

- `0x18000d33d`: `GetTempPath2W`
- `0x18000d34b`: `GetTempPath2W`

## pseudocode

```c
DWORD __fastcall _acrt_GetTempPath2W(DWORD nBufferLength, LPWSTR lpBuffer)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_18007F030;
  if ( qword_18007F030 != -1
    && (qword_18007F030
     || (function_slow = try_get_function_slow(
                           6u,
                           "GetTempPath2W",
                           (unsigned int *)&qword_1800641A0,
                           (unsigned int *)"GetTempPath2W")) != 0) )
  {
    return ((__int64 (__fastcall *)(_QWORD, LPWSTR))function_slow)(nBufferLength, lpBuffer);
  }
  else
  {
    return GetTempPathW(nBufferLength, lpBuffer);
  }
}

```

## disassembly

```asm
0x18000d31c  mov     [rsp+arg_0], rbx
0x18000d321  push    rdi
0x18000d322  sub     rsp, 20h
0x18000d326  mov     rax, cs:qword_18007F030
0x18000d32d  mov     rbx, rdx
0x18000d330  mov     edi, ecx
0x18000d332  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d336  jz      short loc_18000D36B
0x18000d338  test    rax, rax
0x18000d33b  jnz     short loc_18000D35F
0x18000d33d  lea     r9, aGettemppath2w; "GetTempPath2W"
0x18000d344  lea     r8, qword_1800641A0
0x18000d34b  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18000d352  lea     ecx, [rax+6]
0x18000d355  call    try_get_function_slow
0x18000d35a  test    rax, rax
0x18000d35d  jz      short loc_18000D36B
0x18000d35f  mov     rdx, rbx
0x18000d362  mov     ecx, edi
0x18000d364  call    _guard_dispatch_icall
0x18000d369  jmp     short loc_18000D376
0x18000d36b  mov     rdx, rbx; lpBuffer
0x18000d36e  mov     ecx, edi; nBufferLength
0x18000d370  call    cs:__imp_GetTempPathW
0x18000d376  mov     rbx, [rsp+28h+arg_0]
0x18000d37b  add     rsp, 20h
0x18000d37f  pop     rdi
0x18000d380  retn
```
