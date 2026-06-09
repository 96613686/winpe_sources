# DuplicateHandleForMarshaling(ulong,void *,ulong,ulong,ulong,void * *)

- ea: `0x18002ae4c`
- end: `0x18002af45`
- name: `?DuplicateHandleForMarshaling@@YAJKPEAXKKKPEAPEAX@Z`
- size: `249`
- prototype: `__int64 __usercall@<rax>(DWORD dwProcessId@<ecx>, HANDLE hObject@<rdx>, DWORD@<r8d>, unsigned int@<r9d>, unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800287c0`

## callees

- `0x18002ae4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af32`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002aec1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002aec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af1a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ae76`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ae8f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ae76`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ae8f`

## pseudocode

```c
__int64 __fastcall DuplicateHandleForMarshaling(
        DWORD dwProcessId,
        HANDLE hObject,
        DWORD a3,
        __int64 a4,
        unsigned int a5,
        void **lpTargetHandle)
{
  HANDLE v8; // rbp
  HANDLE v9; // rax
  void *v10; // rsi
  unsigned int v11; // ebx
  signed int v12; // eax
  char v13; // di
  signed int v14; // eax
  signed int LastError; // eax

  *lpTargetHandle = 0;
  v8 = OpenProcess(0x40u, 0, dwProcessId);
  if ( !v8 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_14;
  }
  v9 = OpenProcess(0x40u, 0, a3);
  v10 = v9;
  if ( v9 )
  {
    if ( DuplicateHandle(v8, hObject, v9, lpTargetHandle, 0, 0, 3u) )
    {
      v11 = 0;
    }
    else
    {
      v12 = GetLastError();
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
    }
    v13 = 1;
    CloseHandle(v10);
  }
  else
  {
    v13 = 0;
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
  }
  CloseHandle(v8);
  if ( !v13 )
LABEL_14:
    CloseHandle(hObject);
  return v11;
}

```

## disassembly

```asm
0x18002ae4c  push    rbx
0x18002ae4e  push    rbp
0x18002ae4f  push    rsi
0x18002ae50  push    rdi
0x18002ae51  push    r14
0x18002ae53  sub     rsp, 40h
0x18002ae57  mov     rbx, [rsp+68h+lpTargetHandle]
0x18002ae5f  mov     r14, rdx
0x18002ae62  xor     edx, edx; bInheritHandle
0x18002ae64  mov     edi, r8d
0x18002ae67  mov     r8d, ecx; dwProcessId
0x18002ae6a  mov     qword ptr [rbx], 0
0x18002ae71  lea     esi, [rdx+40h]
0x18002ae74  mov     ecx, esi; dwDesiredAccess
0x18002ae76  call    cs:__imp_OpenProcess
0x18002ae7c  mov     rbp, rax
0x18002ae7f  test    rax, rax
0x18002ae82  jz      loc_18002AF1A
0x18002ae88  mov     r8d, edi; dwProcessId
0x18002ae8b  xor     edx, edx; bInheritHandle
0x18002ae8d  mov     ecx, esi; dwDesiredAccess
0x18002ae8f  call    cs:__imp_OpenProcess
0x18002ae95  mov     rsi, rax
0x18002ae98  test    rax, rax
0x18002ae9b  jz      short loc_18002AEF2
0x18002ae9d  mov     [rsp+68h+dwOptions], 3; dwOptions
0x18002aea5  mov     r9, rbx; lpTargetHandle
0x18002aea8  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18002aeb0  mov     r8, rax; hTargetProcessHandle
0x18002aeb3  mov     rdx, r14; hSourceHandle
0x18002aeb6  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18002aebe  mov     rcx, rbp; hSourceProcessHandle
0x18002aec1  call    cs:__imp_DuplicateHandle
0x18002aec7  test    eax, eax
0x18002aec9  jz      short loc_18002AECF
0x18002aecb  xor     ebx, ebx
0x18002aecd  jmp     short loc_18002AEE4
0x18002aecf  call    cs:__imp_GetLastError
0x18002aed5  mov     ebx, eax
0x18002aed7  test    eax, eax
0x18002aed9  jle     short loc_18002AEE4
0x18002aedb  movzx   ebx, ax
0x18002aede  or      ebx, 80070000h
0x18002aee4  mov     rcx, rsi; hObject
0x18002aee7  mov     dil, 1
0x18002aeea  call    cs:__imp_CloseHandle
0x18002aef0  jmp     short loc_18002AF0A
0x18002aef2  xor     dil, dil
0x18002aef5  call    cs:__imp_GetLastError
0x18002aefb  mov     ebx, eax
0x18002aefd  test    eax, eax
0x18002aeff  jle     short loc_18002AF0A
0x18002af01  movzx   ebx, ax
0x18002af04  or      ebx, 80070000h
0x18002af0a  mov     rcx, rbp; hObject
0x18002af0d  call    cs:__imp_CloseHandle
0x18002af13  test    dil, dil
0x18002af16  jnz     short loc_18002AF38
0x18002af18  jmp     short loc_18002AF2F
0x18002af1a  call    cs:__imp_GetLastError
0x18002af20  mov     ebx, eax
0x18002af22  test    eax, eax
0x18002af24  jle     short loc_18002AF2F
0x18002af26  movzx   ebx, ax
0x18002af29  or      ebx, 80070000h
0x18002af2f  mov     rcx, r14; hObject
0x18002af32  call    cs:__imp_CloseHandle
0x18002af38  mov     eax, ebx
0x18002af3a  add     rsp, 40h
0x18002af3e  pop     r14
0x18002af40  pop     rdi
0x18002af41  pop     rsi
0x18002af42  pop     rbp
0x18002af43  pop     rbx
0x18002af44  retn
```
