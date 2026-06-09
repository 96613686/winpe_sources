# StringLenAsAnsi

- ea: `0x18000c3b4`
- end: `0x18000c400`
- name: `StringLenAsAnsi`
- size: `76`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800092c0`
- `0x180009650`
- `0x18000b87c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c3e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000c3e5`

## pseudocode

```c
__int64 __fastcall StringLenAsAnsi(LPCWCH lpWideCharStr)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0) - 1;
  result = v1;
  if ( v1 > 0x103 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000c3b4  mov     rax, rsp
0x18000c3b7  sub     rsp, 48h
0x18000c3bb  mov     qword ptr [rax-10h], 0
0x18000c3c3  mov     r8, rcx; lpWideCharStr
0x18000c3c6  mov     qword ptr [rax-18h], 0
0x18000c3ce  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000c3d2  mov     dword ptr [rax-20h], 0
0x18000c3d9  xor     edx, edx; dwFlags
0x18000c3db  xor     ecx, ecx; CodePage
0x18000c3dd  mov     qword ptr [rax-28h], 0
0x18000c3e5  call    cs:__imp_WideCharToMultiByte
0x18000c3eb  xor     ecx, ecx
0x18000c3ed  lea     edx, [rax-1]
0x18000c3f0  dec     eax
0x18000c3f2  cmp     edx, 103h
0x18000c3f8  cmova   eax, ecx
0x18000c3fb  add     rsp, 48h
0x18000c3ff  retn
```
