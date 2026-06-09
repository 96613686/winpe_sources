# _anonymous_namespace_::WriteJsonToFile

- ea: `0x180007050`
- end: `0x1800070d7`
- name: `_anonymous_namespace_::WriteJsonToFile`
- size: `135`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800070d8`

## callees

- `0x180007050`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800070a6`
- `KERNEL32!GetLastError` at `0x1800070a6`
- `KERNEL32!WriteFile` at `0x18000709c`
- `KERNEL32!WriteFile` at `0x18000709c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180007073`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180007073`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::WriteJsonToFile(HANDLE hFile, __int64 a2)
{
  const wchar_t *v2; // rbx
  int v4; // eax
  __int64 result; // rax
  signed int LastError; // ecx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  v2 = *(const wchar_t **)(a2 + 8);
  v4 = wcslen(v2);
  if ( !v4 )
    return 1;
  if ( WriteFile(hFile, v2, 2 * v4, &NumberOfBytesWritten, 0) )
    return 0;
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180007050  mov     [rsp+arg_8], rbx
0x180007055  push    rdi
0x180007056  sub     rsp, 40h
0x18000705a  mov     rax, cs:__security_cookie
0x180007061  xor     rax, rsp
0x180007064  mov     [rsp+48h+var_10], rax
0x180007069  mov     rbx, [rdx+8]
0x18000706d  mov     rdi, rcx
0x180007070  mov     rcx, rbx; String
0x180007073  call    cs:__imp_wcslen
0x180007079  test    eax, eax
0x18000707b  jnz     short loc_180007084
0x18000707d  mov     eax, 1
0x180007082  jmp     short loc_1800070BF
0x180007084  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180007088  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180007091  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180007096  mov     rdx, rbx; lpBuffer
0x180007099  mov     rcx, rdi; hFile
0x18000709c  call    cs:__imp_WriteFile
0x1800070a2  test    eax, eax
0x1800070a4  jnz     short loc_1800070BD
0x1800070a6  call    cs:__imp_GetLastError
0x1800070ac  mov     ecx, eax
0x1800070ae  movzx   eax, ax
0x1800070b1  or      eax, 80070000h
0x1800070b6  test    ecx, ecx
0x1800070b8  cmovle  eax, ecx
0x1800070bb  jmp     short loc_1800070BF
0x1800070bd  xor     eax, eax
0x1800070bf  mov     rcx, [rsp+48h+var_10]
0x1800070c4  xor     rcx, rsp; StackCookie
0x1800070c7  call    __security_check_cookie
0x1800070cc  mov     rbx, [rsp+48h+arg_8]
0x1800070d1  add     rsp, 40h
0x1800070d5  pop     rdi
0x1800070d6  retn
```
