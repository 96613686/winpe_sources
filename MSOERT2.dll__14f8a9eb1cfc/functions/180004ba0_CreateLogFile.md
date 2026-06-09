# CreateLogFile

- ea: `0x180004ba0`
- end: `0x180004c5c`
- name: `CreateLogFile`
- size: `188`
- prototype: `HANDLE __stdcall(LPCWSTR pszLogFileName, ACCESS_MASK fDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES psaLogFile, ULONG fCreateDisposition, ULONG fFlagsAndAttributes)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001f7c`
- `0x180004ba0`
- `0x180014010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004bff`
- `KERNEL32!InitializeCriticalSection` at `0x180004bff`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HANDLE __stdcall CreateLogFile(
        LPCWSTR pszLogFileName,
        ACCESS_MASK fDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES psaLogFile,
        ULONG fCreateDisposition,
        ULONG fFlagsAndAttributes)
{
  int v7; // edi
  __int64 v8; // rbp
  __int64 v9; // r14
  char *v10; // rbx
  int v11; // edi

  v7 = (int)psaLogFile;
  v8 = *(_QWORD *)&dwShareMode;
  v9 = *(_QWORD *)&fDesiredAccess;
  **(_QWORD **)&fCreateDisposition = 0;
  v10 = (char *)operator new(0x58u);
  if ( v10 )
  {
    *((_DWORD *)v10 + 2) = 1;
    *(_QWORD *)v10 = &CLogFile::`vftable';
    *((_QWORD *)v10 + 5) = 0;
    *((_QWORD *)v10 + 2) = -1;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    v11 = (*(__int64 (__fastcall **)(char *, LPCWSTR, __int64, __int64, int, ULONG))(*(_QWORD *)v10 + 24LL))(
            v10,
            pszLogFileName,
            v9,
            v8,
            v7,
            fFlagsAndAttributes);
    if ( v11 < 0 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    else
      **(_QWORD **)&fCreateDisposition = v10;
  }
  else
  {
    v11 = -2147024882;
  }
  return (HANDLE)(unsigned int)v11;
}

```

## disassembly

```asm
0x180004ba0  push    rbx
0x180004ba2  push    rbp
0x180004ba3  push    rsi
0x180004ba4  push    rdi
0x180004ba5  push    r14
0x180004ba7  push    r15
0x180004ba9  sub     rsp, 48h
0x180004bad  mov     rsi, [rsp+78h+fCreateDisposition]
0x180004bb5  mov     r15, rcx
0x180004bb8  mov     ecx, 58h ; 'X'; Size
0x180004bbd  mov     edi, r9d
0x180004bc0  mov     rbp, r8
0x180004bc3  mov     r14, rdx
0x180004bc6  mov     qword ptr [rsi], 0
0x180004bcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004bd2  mov     rbx, rax
0x180004bd5  test    rax, rax
0x180004bd8  jz      short loc_180004C48
0x180004bda  lea     rax, ??_7CLogFile@@6B@; const CLogFile::`vftable'
0x180004be1  mov     dword ptr [rbx+8], 1
0x180004be8  lea     rcx, [rbx+30h]; lpCriticalSection
0x180004bec  mov     [rbx], rax
0x180004bef  mov     qword ptr [rbx+28h], 0
0x180004bf7  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180004bff  call    cs:__imp_InitializeCriticalSection
0x180004c05  mov     rcx, [rbx]
0x180004c08  mov     r9, rbp
0x180004c0b  mov     r8, r14
0x180004c0e  mov     rdx, r15
0x180004c11  mov     rax, [rcx+18h]
0x180004c15  mov     ecx, [rsp+78h+fFlagsAndAttributes]
0x180004c1c  mov     [rsp+78h+var_50], ecx
0x180004c20  mov     rcx, rbx
0x180004c23  mov     [rsp+78h+var_58], edi
0x180004c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2c  mov     edi, eax
0x180004c2e  test    eax, eax
0x180004c30  js      short loc_180004C37
0x180004c32  mov     [rsi], rbx
0x180004c35  jmp     short loc_180004C4D
0x180004c37  mov     rax, [rbx]
0x180004c3a  mov     rcx, rbx
0x180004c3d  mov     rax, [rax+10h]
0x180004c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c46  jmp     short loc_180004C4D
0x180004c48  mov     edi, 8007000Eh
0x180004c4d  mov     eax, edi
0x180004c4f  add     rsp, 48h
0x180004c53  pop     r15
0x180004c55  pop     r14
0x180004c57  pop     rdi
0x180004c58  pop     rsi
0x180004c59  pop     rbp
0x180004c5a  pop     rbx
0x180004c5b  retn
```
