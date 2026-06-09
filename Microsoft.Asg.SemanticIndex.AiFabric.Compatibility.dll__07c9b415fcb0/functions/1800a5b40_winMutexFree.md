# winMutexFree

- ea: `0x1800a5b40`
- end: `0x1800a5bf6`
- name: `winMutexFree`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800a5b40`
- `0x180156260`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800a5b85`
- `KERNEL32!DeleteCriticalSection` at `0x1800a5b85`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  __int64 result; // rax
  int v3; // eax

  if ( *(_DWORD *)(a1 + 40) >= 2u )
    return sqlite3_log(
             21,
             "%s at line %d of [%.10s]",
             "misuse",
             30171,
             "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  if ( !dword_1803379C0 )
    return (*((__int64 (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(a1);
  if ( (_QWORD)xmmword_1803DC8D0 )
    xmmword_180337A40(xmmword_1803DC8D0);
  v3 = (*((__int64 (__fastcall **)(__int64))&xmmword_1803379F0 + 1))(a1);
  --qword_1803DC858;
  qword_1803DC810 -= v3;
  result = (*((__int64 (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(a1);
  if ( (_QWORD)xmmword_1803DC8D0 )
    return xmmword_180337A50(xmmword_1803DC8D0);
  return result;
}

```

## disassembly

```asm
0x1800a5b40  push    rbx
0x1800a5b42  sub     rsp, 30h
0x1800a5b46  mov     eax, [rcx+28h]
0x1800a5b49  mov     rbx, rcx
0x1800a5b4c  test    eax, eax
0x1800a5b4e  jz      short loc_1800A5B85
0x1800a5b50  cmp     eax, 1
0x1800a5b53  jz      short loc_1800A5B85
0x1800a5b55  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x1800a5b5c  mov     r9d, 75DBh
0x1800a5b62  lea     r8, aMisuse; "misuse"
0x1800a5b69  mov     [rsp+38h+var_18], rax
0x1800a5b6e  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x1800a5b75  mov     ecx, 15h
0x1800a5b7a  call    sqlite3_log
0x1800a5b7f  add     rsp, 30h
0x1800a5b83  pop     rbx
0x1800a5b84  retn
0x1800a5b85  call    cs:__imp_DeleteCriticalSection
0x1800a5b8b  cmp     cs:dword_1803379C0, 0
0x1800a5b92  jz      short loc_1800A5BE1
0x1800a5b94  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x1800a5b9b  test    rcx, rcx
0x1800a5b9e  jz      short loc_1800A5BA6
0x1800a5ba0  call    qword ptr cs:xmmword_180337A40
0x1800a5ba6  mov     rcx, rbx
0x1800a5ba9  call    qword ptr cs:xmmword_1803379F0+8
0x1800a5baf  dec     cs:qword_1803DC858
0x1800a5bb6  movsxd  rcx, eax
0x1800a5bb9  sub     cs:qword_1803DC810, rcx
0x1800a5bc0  mov     rcx, rbx
0x1800a5bc3  call    qword ptr cs:xmmword_1803379E0+8
0x1800a5bc9  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x1800a5bd0  test    rcx, rcx
0x1800a5bd3  jz      short loc_1800A5BF0
0x1800a5bd5  add     rsp, 30h
0x1800a5bd9  pop     rbx
0x1800a5bda  jmp     qword ptr cs:xmmword_180337A50
0x1800a5be1  mov     rcx, rbx
0x1800a5be4  add     rsp, 30h
0x1800a5be8  pop     rbx
0x1800a5be9  jmp     qword ptr cs:xmmword_1803379E0+8
0x1800a5bf0  add     rsp, 30h
0x1800a5bf4  pop     rbx
0x1800a5bf5  retn
```
