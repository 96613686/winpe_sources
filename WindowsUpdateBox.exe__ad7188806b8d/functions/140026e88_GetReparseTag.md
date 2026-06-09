# GetReparseTag

- ea: `0x140026e88`
- end: `0x140027022`
- name: `GetReparseTag`
- size: `410`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x140026684`
- `0x1400273e4`

## callees

- `0x140022c14`
- `0x140026e88`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140026fad`
- `KERNEL32!CloseHandle` at `0x140026fad`
- `KERNEL32!HeapFree` at `0x140026f97`
- `KERNEL32!HeapFree` at `0x140026fcd`
- `KERNEL32!HeapFree` at `0x140026f97`
- `KERNEL32!HeapFree` at `0x140026fcd`
- `KERNEL32!HeapAlloc` at `0x140026f16`
- `KERNEL32!HeapAlloc` at `0x140026f16`
- `KERNEL32!GetProcessHeap` at `0x140026efe`
- `KERNEL32!GetProcessHeap` at `0x140026f83`
- `KERNEL32!GetProcessHeap` at `0x140026fb9`
- `KERNEL32!GetProcessHeap` at `0x140026efe`
- `KERNEL32!GetProcessHeap` at `0x140026f83`
- `KERNEL32!GetProcessHeap` at `0x140026fb9`
- `KERNEL32!DeviceIoControl` at `0x140026f54`
- `KERNEL32!DeviceIoControl` at `0x140026f54`
- `KERNEL32!GetLastError` at `0x140026f6b`
- `KERNEL32!GetLastError` at `0x140026fdb`
- `KERNEL32!GetLastError` at `0x140026f6b`
- `KERNEL32!GetLastError` at `0x140026fdb`
- `KERNEL32!CreateFileW` at `0x140026ee1`
- `KERNEL32!CreateFileW` at `0x140026ee1`
- `KERNEL32!SetLastError` at `0x140026ff5`
- `KERNEL32!SetLastError` at `0x140026ff5`

## pseudocode

```c
__int64 __fastcall GetReparseTag(unsigned __int16 *lpFileName, _DWORD *a2)
{
  unsigned int v3; // ebx
  DWORD LastError; // edi
  void *v6; // r15
  HANDLE FileW; // rbp
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rsi
  HANDLE v10; // rax
  HANDLE v11; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  LastError = 0;
  v6 = (void *)PrepareUnicodePathEx(lpFileName);
  if ( v6 )
  {
    *a2 = 0;
    FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      BytesReturned = 0;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 8u, 0x4000u);
      if ( v9 )
      {
        if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v9, 0x4000u, &BytesReturned, 0) )
        {
          *a2 = *v9;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v9);
      }
      else
      {
        LastError = 14;
      }
      CloseHandle(FileW);
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v6);
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  LOBYTE(v3) = LastError == 0;
  return v3;
}

```

## disassembly

```asm
0x140026e88  mov     [rsp+arg_0], rbx
0x140026e8d  mov     [rsp+arg_8], rbp
0x140026e92  mov     [rsp+arg_18], rsi
0x140026e97  push    rdi
0x140026e98  push    r14
0x140026e9a  push    r15
0x140026e9c  sub     rsp, 40h
0x140026ea0  mov     r14, rdx
0x140026ea3  xor     ebx, ebx
0x140026ea5  xor     edx, edx
0x140026ea7  mov     edi, ebx
0x140026ea9  mov     rsi, rcx
0x140026eac  call    PrepareUnicodePathEx
0x140026eb1  mov     r15, rax
0x140026eb4  test    rax, rax
0x140026eb7  jz      loc_140026FDB
0x140026ebd  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x140026ec2  lea     r8d, [rbx+7]; dwShareMode
0x140026ec6  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140026ece  xor     r9d, r9d; lpSecurityAttributes
0x140026ed1  xor     edx, edx; dwDesiredAccess
0x140026ed3  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x140026edb  mov     rcx, rsi; lpFileName
0x140026ede  mov     [r14], ebx
0x140026ee1  call    cs:__imp_CreateFileW
0x140026ee8  nop     dword ptr [rax+rax+00h]
0x140026eed  mov     rbp, rax
0x140026ef0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140026ef4  jz      loc_140026FB9
0x140026efa  mov     [rsp+58h+BytesReturned], ebx
0x140026efe  call    cs:__imp_GetProcessHeap
0x140026f05  nop     dword ptr [rax+rax+00h]
0x140026f0a  lea     edx, [rbx+8]; dwFlags
0x140026f0d  mov     r8d, 4000h; dwBytes
0x140026f13  mov     rcx, rax; hHeap
0x140026f16  call    cs:__imp_HeapAlloc
0x140026f1d  nop     dword ptr [rax+rax+00h]
0x140026f22  mov     rsi, rax
0x140026f25  test    rax, rax
0x140026f28  jz      short loc_140026FA5
0x140026f2a  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x140026f2f  lea     rax, [rsp+58h+BytesReturned]
0x140026f34  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x140026f39  xor     r9d, r9d; nInBufferSize
0x140026f3c  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x140026f44  xor     r8d, r8d; lpInBuffer
0x140026f47  mov     edx, 900A8h; dwIoControlCode
0x140026f4c  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOutBuffer
0x140026f51  mov     rcx, rbp; hDevice
0x140026f54  call    cs:__imp_DeviceIoControl
0x140026f5b  nop     dword ptr [rax+rax+00h]
0x140026f60  test    eax, eax
0x140026f62  jz      short loc_140026F6B
0x140026f64  mov     eax, [rsi]
0x140026f66  mov     [r14], eax
0x140026f69  jmp     short loc_140026F83
0x140026f6b  call    cs:__imp_GetLastError
0x140026f72  nop     dword ptr [rax+rax+00h]
0x140026f77  mov     edi, eax
0x140026f79  mov     eax, 1Fh
0x140026f7e  test    edi, edi
0x140026f80  cmovz   edi, eax
0x140026f83  call    cs:__imp_GetProcessHeap
0x140026f8a  nop     dword ptr [rax+rax+00h]
0x140026f8f  mov     r8, rsi; lpMem
0x140026f92  xor     edx, edx; dwFlags
0x140026f94  mov     rcx, rax; hHeap
0x140026f97  call    cs:__imp_HeapFree
0x140026f9e  nop     dword ptr [rax+rax+00h]
0x140026fa3  jmp     short loc_140026FAA
0x140026fa5  mov     edi, 0Eh
0x140026faa  mov     rcx, rbp; hObject
0x140026fad  call    cs:__imp_CloseHandle
0x140026fb4  nop     dword ptr [rax+rax+00h]
0x140026fb9  call    cs:__imp_GetProcessHeap
0x140026fc0  nop     dword ptr [rax+rax+00h]
0x140026fc5  mov     r8, r15; lpMem
0x140026fc8  xor     edx, edx; dwFlags
0x140026fca  mov     rcx, rax; hHeap
0x140026fcd  call    cs:__imp_HeapFree
0x140026fd4  nop     dword ptr [rax+rax+00h]
0x140026fd9  jmp     short loc_140026FF3
0x140026fdb  call    cs:__imp_GetLastError
0x140026fe2  nop     dword ptr [rax+rax+00h]
0x140026fe7  mov     edi, eax
0x140026fe9  mov     eax, 1Fh
0x140026fee  test    edi, edi
0x140026ff0  cmovz   edi, eax
0x140026ff3  mov     ecx, edi; dwErrCode
0x140026ff5  call    cs:__imp_SetLastError
0x140026ffc  nop     dword ptr [rax+rax+00h]
0x140027001  mov     rbp, [rsp+58h+arg_8]
0x140027006  test    edi, edi
0x140027008  mov     rsi, [rsp+58h+arg_18]
0x14002700d  setz    bl
0x140027010  mov     eax, ebx
0x140027012  mov     rbx, [rsp+58h+arg_0]
0x140027017  add     rsp, 40h
0x14002701b  pop     r15
0x14002701d  pop     r14
0x14002701f  pop     rdi
0x140027020  retn
```
