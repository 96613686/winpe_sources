# File::Initialize(ushort const *,ulong,ulong,ulong,int *)

- ea: `0x1800028d8`
- end: `0x1800029b5`
- name: `?Initialize@File@@QEAAJPEBGKKKPEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(File *this, const unsigned __int16 *, DWORD, __int64, DWORD dwFlagsAndAttributes, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001e9c`
- `0x18000228c`
- `0x180002474`

## callees

- `0x1800028d8`
- `0x180005182`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180002913`
- `KERNEL32!HeapAlloc` at `0x180002913`
- `KERNEL32!GetProcessHeap` at `0x180002905`
- `KERNEL32!GetProcessHeap` at `0x180002905`
- `KERNEL32!CreateFileW` at `0x18000295b`
- `KERNEL32!CreateFileW` at `0x18000295b`
- `KERNEL32!GetLastError` at `0x18000296a`
- `KERNEL32!GetLastError` at `0x180002995`
- `KERNEL32!GetLastError` at `0x18000296a`
- `KERNEL32!GetLastError` at `0x180002995`

## pseudocode

```c
__int64 __fastcall File::Initialize(
        File *this,
        const unsigned __int16 *a2,
        DWORD a3,
        __int64 a4,
        DWORD dwFlagsAndAttributes,
        int *a6)
{
  __int64 v6; // rax
  SIZE_T v10; // rsi
  HANDLE ProcessHeap; // rax
  void *v12; // rax
  unsigned int v13; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax

  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v10 = 2 * v6 + 2;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 0, v10);
  *((_QWORD *)this + 1) = v12;
  if ( !v12 )
    return (unsigned int)-2147024882;
  memcpy_0(v12, a2, v10);
  FileW = CreateFileW(a2, a3, 1u, 0, 4u, dwFlagsAndAttributes, 0);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v13 = 0;
LABEL_11:
    if ( a6 )
      *a6 = GetLastError() == 183;
    return v13;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( !v13 )
    goto LABEL_11;
  return v13;
}

```

## disassembly

```asm
0x1800028d8  push    rbx
0x1800028da  push    rbp
0x1800028db  push    rsi
0x1800028dc  push    rdi
0x1800028dd  push    r14
0x1800028df  sub     rsp, 40h
0x1800028e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800028e7  mov     ebp, r8d
0x1800028ea  xor     r14d, r14d
0x1800028ed  mov     rbx, rdx
0x1800028f0  mov     rdi, rcx
0x1800028f3  inc     rax
0x1800028f6  cmp     [rdx+rax*2], r14w
0x1800028fb  jnz     short loc_1800028F3
0x1800028fd  lea     rsi, ds:2[rax*2]
0x180002905  call    cs:__imp_GetProcessHeap
0x18000290b  mov     r8, rsi; dwBytes
0x18000290e  xor     edx, edx; dwFlags
0x180002910  mov     rcx, rax; hHeap
0x180002913  call    cs:__imp_HeapAlloc
0x180002919  mov     [rdi+8], rax
0x18000291d  test    rax, rax
0x180002920  jnz     short loc_180002929
0x180002922  mov     ebx, 8007000Eh
0x180002927  jmp     short loc_1800029A8
0x180002929  mov     r8, rsi; Size
0x18000292c  mov     rdx, rbx; Src
0x18000292f  mov     rcx, rax; void *
0x180002932  call    memcpy_0
0x180002937  mov     eax, [rsp+68h+arg_20]
0x18000293e  xor     r9d, r9d; lpSecurityAttributes
0x180002941  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180002946  mov     edx, ebp; dwDesiredAccess
0x180002948  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000294c  mov     rcx, rbx; lpFileName
0x18000294f  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180002957  lea     r8d, [r9+1]; dwShareMode
0x18000295b  call    cs:__imp_CreateFileW
0x180002961  mov     [rdi], rax
0x180002964  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002968  jnz     short loc_180002985
0x18000296a  call    cs:__imp_GetLastError
0x180002970  mov     ebx, eax
0x180002972  test    eax, eax
0x180002974  jle     short loc_18000297F
0x180002976  movzx   ebx, ax
0x180002979  or      ebx, 80070000h
0x18000297f  test    ebx, ebx
0x180002981  jnz     short loc_1800029A8
0x180002983  jmp     short loc_180002988
0x180002985  mov     ebx, r14d
0x180002988  mov     rdi, [rsp+68h+arg_28]
0x180002990  test    rdi, rdi
0x180002993  jz      short loc_1800029A8
0x180002995  call    cs:__imp_GetLastError
0x18000299b  mov     ecx, r14d
0x18000299e  cmp     eax, 0B7h
0x1800029a3  setz    cl
0x1800029a6  mov     [rdi], ecx
0x1800029a8  mov     eax, ebx
0x1800029aa  add     rsp, 40h
0x1800029ae  pop     r14
0x1800029b0  pop     rdi
0x1800029b1  pop     rsi
0x1800029b2  pop     rbp
0x1800029b3  pop     rbx
0x1800029b4  retn
```
