# CMpeg2SharedMem::CMpeg2SharedMem(ushort const *,ulong,_SECURITY_ATTRIBUTES *,long *)

- ea: `0x180010280`
- end: `0x180010375`
- name: `??0CMpeg2SharedMem@@QEAA@PEBGKPEAU_SECURITY_ATTRIBUTES@@PEAJ@Z`
- size: `245`
- prototype: `CMpeg2SharedMem *__fastcall(CMpeg2SharedMem *__hidden this, LPCWSTR lpName, DWORD dwMaximumSizeLow, LPSECURITY_ATTRIBUTES lpFileMappingAttributes, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180011d44`
- `0x180012520`

## callees

- `0x180010280`
- `0x18001186c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800102e4`
- `KERNEL32!GetLastError` at `0x180010308`
- `KERNEL32!GetLastError` at `0x18001033e`
- `KERNEL32!GetLastError` at `0x1800102e4`
- `KERNEL32!GetLastError` at `0x180010308`
- `KERNEL32!GetLastError` at `0x18001033e`
- `KERNEL32!MapViewOfFile` at `0x18001032f`
- `KERNEL32!MapViewOfFile` at `0x18001032f`
- `KERNEL32!CreateFileMappingW` at `0x1800102d5`
- `KERNEL32!CreateFileMappingW` at `0x1800102d5`
- `KERNEL32!OpenFileMappingW` at `0x1800102f9`
- `KERNEL32!OpenFileMappingW` at `0x1800102f9`

## pseudocode

```c
CMpeg2SharedMem *__fastcall CMpeg2SharedMem::CMpeg2SharedMem(
        CMpeg2SharedMem *this,
        LPCWSTR lpName,
        DWORD dwMaximumSizeLow,
        LPSECURITY_ATTRIBUTES lpFileMappingAttributes,
        int *a5)
{
  HANDLE FileMappingW; // rax
  signed int LastError; // ebx
  HANDLE v11; // rax
  bool v12; // sf
  LPVOID v13; // rax
  signed int v14; // eax

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CMpeg2SharedMem::`vftable';
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  CMpeg2SharedMem::Free_(this);
  *((_DWORD *)this + 4) = dwMaximumSizeLow;
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   lpFileMappingAttributes,
                   4u,
                   0,
                   dwMaximumSizeLow,
                   lpName);
  *((_QWORD *)this + 3) = FileMappingW;
  if ( FileMappingW )
    goto LABEL_8;
  LastError = GetLastError();
  if ( LastError == 5 )
  {
    v11 = OpenFileMappingW(4u, 0, lpName);
    *((_QWORD *)this + 3) = v11;
    if ( v11 )
      goto LABEL_8;
    LastError = GetLastError();
  }
  v12 = LastError < 0;
  if ( LastError )
  {
    if ( LastError <= 0 )
      goto LABEL_13;
    LastError = (unsigned __int16)LastError;
    goto LABEL_11;
  }
LABEL_8:
  LastError = 0;
  v13 = MapViewOfFile(*((HANDLE *)this + 3), 6u, 0, 0, 0);
  *((_QWORD *)this + 1) = v13;
  if ( v13 )
    goto LABEL_15;
  v14 = GetLastError();
  LastError = v14;
  if ( v14 <= 0 )
    goto LABEL_12;
  LastError = (unsigned __int16)v14;
LABEL_11:
  LastError |= 0x80070000;
LABEL_12:
  v12 = LastError < 0;
LABEL_13:
  if ( v12 )
    CMpeg2SharedMem::Free_(this);
LABEL_15:
  *a5 = LastError;
  return this;
}

```

## disassembly

```asm
0x180010280  push    rbx
0x180010282  push    rbp
0x180010283  push    rsi
0x180010284  push    rdi
0x180010285  sub     rsp, 38h
0x180010289  lea     rax, ??_7CMpeg2SharedMem@@6B@; const CMpeg2SharedMem::`vftable'
0x180010290  mov     qword ptr [rcx+8], 0
0x180010298  mov     [rcx], rax
0x18001029b  mov     rdi, r9
0x18001029e  mov     ebx, r8d
0x1800102a1  mov     dword ptr [rcx+10h], 0
0x1800102a8  mov     rbp, rdx
0x1800102ab  mov     qword ptr [rcx+18h], 0
0x1800102b3  mov     rsi, rcx
0x1800102b6  call    ?Free_@CMpeg2SharedMem@@AEAAXXZ; CMpeg2SharedMem::Free_(void)
0x1800102bb  xor     r9d, r9d; dwMaximumSizeHigh
0x1800102be  mov     [rsp+58h+lpName], rbp; lpName
0x1800102c3  mov     rdx, rdi; lpFileMappingAttributes
0x1800102c6  mov     [rsi+10h], ebx
0x1800102c9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800102cd  mov     [rsp+58h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800102d1  lea     r8d, [r9+4]; flProtect
0x1800102d5  call    cs:__imp_CreateFileMappingW
0x1800102db  mov     [rsi+18h], rax
0x1800102df  test    rax, rax
0x1800102e2  jnz     short loc_18001031B
0x1800102e4  call    cs:__imp_GetLastError
0x1800102ea  mov     ebx, eax
0x1800102ec  cmp     eax, 5
0x1800102ef  jnz     short loc_180010310
0x1800102f1  mov     r8, rbp; lpName
0x1800102f4  lea     ecx, [rax-1]; dwDesiredAccess
0x1800102f7  xor     edx, edx; bInheritHandle
0x1800102f9  call    cs:__imp_OpenFileMappingW
0x1800102ff  mov     [rsi+18h], rax
0x180010303  test    rax, rax
0x180010306  jnz     short loc_18001031B
0x180010308  call    cs:__imp_GetLastError
0x18001030e  mov     ebx, eax
0x180010310  test    ebx, ebx
0x180010312  jz      short loc_18001031B
0x180010314  jle     short loc_180010355
0x180010316  movzx   ebx, bx
0x180010319  jmp     short loc_18001034D
0x18001031b  mov     rcx, [rsi+18h]; hFileMappingObject
0x18001031f  xor     ebx, ebx
0x180010321  xor     r9d, r9d; dwFileOffsetLow
0x180010324  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180010329  xor     r8d, r8d; dwFileOffsetHigh
0x18001032c  lea     edx, [rbx+6]; dwDesiredAccess
0x18001032f  call    cs:__imp_MapViewOfFile
0x180010335  mov     [rsi+8], rax
0x180010339  test    rax, rax
0x18001033c  jnz     short loc_18001035F
0x18001033e  call    cs:__imp_GetLastError
0x180010344  mov     ebx, eax
0x180010346  test    eax, eax
0x180010348  jle     short loc_180010353
0x18001034a  movzx   ebx, ax
0x18001034d  or      ebx, 80070000h
0x180010353  test    ebx, ebx
0x180010355  jns     short loc_18001035F
0x180010357  mov     rcx, rsi; this
0x18001035a  call    ?Free_@CMpeg2SharedMem@@AEAAXXZ; CMpeg2SharedMem::Free_(void)
0x18001035f  mov     rax, [rsp+58h+arg_20]
0x180010367  mov     [rax], ebx
0x180010369  mov     rax, rsi
0x18001036c  add     rsp, 38h
0x180010370  pop     rdi
0x180010371  pop     rsi
0x180010372  pop     rbp
0x180010373  pop     rbx
0x180010374  retn
```
