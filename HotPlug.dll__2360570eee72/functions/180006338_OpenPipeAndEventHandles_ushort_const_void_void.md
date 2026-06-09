# OpenPipeAndEventHandles(ushort const *,void * *,void * *)

- ea: `0x180006338`
- end: `0x18000650c`
- name: `?OpenPipeAndEventHandles@@YAHPEBGPEAPEAX1@Z`
- size: `468`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void **, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004aec`
- `0x180004c20`
- `0x180004e60`
- `0x180005430`

## callees

- `0x180006338`
- `0x180008760`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800063e3`
- `KERNEL32!CreateFileW` at `0x1800063e3`
- `KERNEL32!OpenEventW` at `0x18000645f`
- `KERNEL32!OpenEventW` at `0x18000645f`
- `KERNEL32!GetLastError` at `0x18000647f`
- `KERNEL32!GetLastError` at `0x18000647f`
- `KERNEL32!WaitNamedPipeW` at `0x1800063b6`
- `KERNEL32!WaitNamedPipeW` at `0x1800063b6`
- `KERNEL32!CloseHandle` at `0x1800064d2`
- `KERNEL32!CloseHandle` at `0x1800064e0`
- `KERNEL32!CloseHandle` at `0x1800064d2`
- `KERNEL32!CloseHandle` at `0x1800064e0`
- `KERNEL32!ReadFile` at `0x180006415`
- `KERNEL32!ReadFile` at `0x180006449`
- `KERNEL32!ReadFile` at `0x180006415`
- `KERNEL32!ReadFile` at `0x180006449`

## pseudocode

```c
BOOL __fastcall OpenPipeAndEventHandles(LPCWSTR lpFileName, void **a2, void **a3)
{
  int v6; // r14d
  HANDLE v7; // rsi
  BOOL result; // eax
  HANDLE FileW; // rax
  __int64 v10; // rdi
  DWORD Buffer; // [rsp+40h] [rbp-288h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-284h] BYREF
  int v13; // [rsp+48h] [rbp-280h]
  __int64 v14; // [rsp+50h] [rbp-278h]
  HANDLE v15; // [rsp+58h] [rbp-270h]
  void **v16; // [rsp+60h] [rbp-268h]
  void **v17; // [rsp+68h] [rbp-260h]
  WCHAR Name[264]; // [rsp+70h] [rbp-258h] BYREF

  v16 = a2;
  v17 = a3;
  v6 = 0;
  v14 = -1;
  v7 = 0;
  v15 = 0;
  Buffer = 0;
  NumberOfBytesRead = 0;
  if ( !a2 || !a3 )
    return 0;
  if ( !lpFileName || !*lpFileName )
    return 0;
  result = WaitNamedPipeW(lpFileName, 0x2BF20u);
  if ( result )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0, 0);
    v10 = (__int64)FileW;
    v14 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      return 0;
    }
    else
    {
      if ( ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
      {
        if ( Buffer - 1 <= 0x103 )
        {
          Name[259] = 0;
          if ( ReadFile((HANDLE)v10, Name, Buffer, &NumberOfBytesRead, 0) )
          {
            v7 = OpenEventW(0x100002u, 0, Name);
            v15 = v7;
            if ( v7 )
            {
              v6 = 1;
              v13 = 1;
            }
          }
        }
      }
      else
      {
        if ( GetLastError() == 6 )
          v10 = -1;
        v14 = v10;
      }
      if ( v6 )
      {
        *a2 = (void *)v10;
        *a3 = v7;
      }
      else
      {
        if ( v10 != -1 )
          CloseHandle((HANDLE)v10);
        if ( v7 )
          CloseHandle(v7);
      }
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006338  push    rbx
0x18000633a  push    rsi
0x18000633b  push    rdi
0x18000633c  push    r12
0x18000633e  push    r13
0x180006340  push    r14
0x180006342  push    r15
0x180006344  sub     rsp, 290h
0x18000634b  mov     rax, cs:__security_cookie
0x180006352  xor     rax, rsp
0x180006355  mov     [rsp+2C8h+var_48], rax
0x18000635d  mov     r13, r8
0x180006360  mov     r12, rdx
0x180006363  mov     rdi, rcx
0x180006366  mov     [rsp+2C8h+var_268], rdx
0x18000636b  mov     [rsp+2C8h+var_260], r8
0x180006370  xor     ebx, ebx
0x180006372  mov     r14d, ebx
0x180006375  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006379  mov     [rsp+2C8h+var_278], r15
0x18000637e  mov     esi, ebx
0x180006380  mov     [rsp+2C8h+var_270], rbx
0x180006385  mov     [rsp+2C8h+Buffer], ebx
0x180006389  mov     [rsp+2C8h+NumberOfBytesRead], ebx
0x18000638d  test    rdx, rdx
0x180006390  jz      loc_180006497
0x180006396  test    r8, r8
0x180006399  jz      loc_180006497
0x18000639f  test    rcx, rcx
0x1800063a2  jz      loc_180006493
0x1800063a8  cmp     [rcx], bx
0x1800063ab  jz      loc_180006493
0x1800063b1  mov     edx, 2BF20h; nTimeOut
0x1800063b6  call    cs:__imp_WaitNamedPipeW
0x1800063bc  test    eax, eax
0x1800063be  jz      loc_1800064E9
0x1800063c4  mov     [rsp+2C8h+hTemplateFile], rbx; hTemplateFile
0x1800063c9  mov     [rsp+2C8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800063cd  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800063d5  xor     r9d, r9d; lpSecurityAttributes
0x1800063d8  xor     r8d, r8d; dwShareMode
0x1800063db  mov     edx, 80000000h; dwDesiredAccess
0x1800063e0  mov     rcx, rdi; lpFileName
0x1800063e3  call    cs:__imp_CreateFileW
0x1800063e9  mov     rdi, rax
0x1800063ec  mov     [rsp+2C8h+var_278], rax
0x1800063f1  cmp     rax, r15
0x1800063f4  jnz     short loc_1800063FD
0x1800063f6  xor     eax, eax
0x1800063f8  jmp     loc_1800064E9
0x1800063fd  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rbx; lpOverlapped
0x180006402  lea     r9, [rsp+2C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006407  mov     r8d, 4; nNumberOfBytesToRead
0x18000640d  lea     rdx, [rsp+2C8h+Buffer]; lpBuffer
0x180006412  mov     rcx, rdi; hFile
0x180006415  call    cs:__imp_ReadFile
0x18000641b  test    eax, eax
0x18000641d  jz      short loc_18000647F
0x18000641f  mov     r8d, [rsp+2C8h+Buffer]; nNumberOfBytesToRead
0x180006424  lea     eax, [r8-1]
0x180006428  cmp     eax, 103h
0x18000642d  ja      short loc_180006491
0x18000642f  mov     [rsp+2C8h+var_52], bx
0x180006437  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rbx; lpOverlapped
0x18000643c  lea     r9, [rsp+2C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006441  lea     rdx, [rsp+2C8h+Name]; lpBuffer
0x180006446  mov     rcx, rdi; hFile
0x180006449  call    cs:__imp_ReadFile
0x18000644f  test    eax, eax
0x180006451  jz      short loc_180006491
0x180006453  lea     r8, [rsp+2C8h+Name]; lpName
0x180006458  xor     edx, edx; bInheritHandle
0x18000645a  mov     ecx, 100002h; dwDesiredAccess
0x18000645f  call    cs:__imp_OpenEventW
0x180006465  mov     rsi, rax
0x180006468  mov     [rsp+2C8h+var_270], rax
0x18000646d  test    rax, rax
0x180006470  jz      short loc_180006491
0x180006472  mov     r14d, 1
0x180006478  mov     [rsp+2C8h+var_280], r14d
0x18000647d  jmp     short loc_180006491
0x18000647f  call    cs:__imp_GetLastError
0x180006485  cmp     eax, 6
0x180006488  cmovz   rdi, r15
0x18000648c  mov     [rsp+2C8h+var_278], rdi
0x180006491  jmp     short loc_1800064BB
0x180006493  xor     eax, eax
0x180006495  jmp     short loc_1800064E9
0x180006497  xor     eax, eax
0x180006499  jmp     short loc_1800064E9
0x18000649b  xor     r14d, r14d
0x18000649e  mov     [rsp+2C8h+var_280], r14d
0x1800064a3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800064a7  mov     rdi, [rsp+2C8h+var_278]
0x1800064ac  mov     rsi, [rsp+2C8h+var_270]
0x1800064b1  mov     r12, [rsp+2C8h+var_268]
0x1800064b6  mov     r13, [rsp+2C8h+var_260]
0x1800064bb  test    r14d, r14d
0x1800064be  jz      short loc_1800064CA
0x1800064c0  mov     [r12], rdi
0x1800064c4  mov     [r13+0], rsi
0x1800064c8  jmp     short loc_1800064E6
0x1800064ca  cmp     rdi, r15
0x1800064cd  jz      short loc_1800064D8
0x1800064cf  mov     rcx, rdi; hObject
0x1800064d2  call    cs:__imp_CloseHandle
0x1800064d8  test    rsi, rsi
0x1800064db  jz      short loc_1800064E6
0x1800064dd  mov     rcx, rsi; hObject
0x1800064e0  call    cs:__imp_CloseHandle
0x1800064e6  mov     eax, r14d
0x1800064e9  mov     rcx, [rsp+2C8h+var_48]
0x1800064f1  xor     rcx, rsp; StackCookie
0x1800064f4  call    __security_check_cookie
0x1800064f9  add     rsp, 290h
0x180006500  pop     r15
0x180006502  pop     r14
0x180006504  pop     r13
0x180006506  pop     r12
0x180006508  pop     rdi
0x180006509  pop     rsi
0x18000650a  pop     rbx
0x18000650b  retn
```
