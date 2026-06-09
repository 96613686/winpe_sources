# WriteLogMsg(CLogFile *,LOGFILETYPE,char *,...)

- ea: `0x180004b34`
- end: `0x180004b8d`
- name: `?WriteLogMsg@@YAJPEAVCLogFile@@W4LOGFILETYPE@@PEADZZ`
- size: `89`
- prototype: `int __high(struct CLogFile *, enum LOGFILETYPE, char *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047f0`

## callees

- `0x180004798`
- `0x180014010`

## pseudocode

```c
__int64 WriteLogMsg(__int64 a1, unsigned int a2, size_t *a3, ...)
{
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  StringVPrintfWorkerA(pszDest, 0x800u, a3, (STRSAFE_LPCSTR)a3, va);
  return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 40LL))(a1, a2, pszDest);
}

```

## disassembly

```asm
0x180004b34  mov     r11, rsp
0x180004b37  mov     [r11+18h], r8
0x180004b3b  mov     [r11+20h], r9
0x180004b3f  push    rbx
0x180004b40  push    rdi
0x180004b41  sub     rsp, 48h
0x180004b45  mov     ebx, edx
0x180004b47  mov     qword ptr [r11-28h], 0
0x180004b4f  mov     rdi, rcx
0x180004b52  lea     rax, [r11+20h]
0x180004b56  mov     edx, 800h; cchDest
0x180004b5b  mov     [r11-38h], rax
0x180004b5f  lea     rcx, pszDest; pszDest
0x180004b66  mov     r9, r8; pszFormat
0x180004b69  call    StringVPrintfWorkerA
0x180004b6e  mov     rax, [rdi]
0x180004b71  lea     r8, pszDest
0x180004b78  mov     edx, ebx
0x180004b7a  mov     rcx, rdi
0x180004b7d  mov     rax, [rax+28h]
0x180004b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b86  add     rsp, 48h
0x180004b8a  pop     rdi
0x180004b8b  pop     rbx
0x180004b8c  retn
```
