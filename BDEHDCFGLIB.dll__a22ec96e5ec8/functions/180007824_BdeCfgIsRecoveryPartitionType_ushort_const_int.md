# BdeCfgIsRecoveryPartitionType(ushort const *,int *)

- ea: `0x180007824`
- end: `0x18000795d`
- name: `?BdeCfgIsRecoveryPartitionType@@YAJPEBGPEAH@Z`
- size: `313`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003240`
- `0x18000fb40`
- `0x180010070`

## callees

- `0x180007824`
- `0x18001358e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000789c`
- `KERNEL32!GetLastError` at `0x1800078fa`
- `KERNEL32!GetLastError` at `0x18000789c`
- `KERNEL32!GetLastError` at `0x1800078fa`
- `KERNEL32!CreateFileW` at `0x18000788d`
- `KERNEL32!CreateFileW` at `0x18000788d`
- `KERNEL32!DeviceIoControl` at `0x1800078f0`
- `KERNEL32!DeviceIoControl` at `0x1800078f0`
- `KERNEL32!CloseHandle` at `0x180007912`
- `KERNEL32!CloseHandle` at `0x18000791d`
- `KERNEL32!CloseHandle` at `0x180007912`
- `KERNEL32!CloseHandle` at `0x18000791d`

## pseudocode

```c
__int64 __fastcall BdeCfgIsRecoveryPartitionType(LPCWSTR lpFileName, int *a2)
{
  HANDLE FileW; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  _DWORD OutBuffer[8]; // [rsp+40h] [rbp-98h] BYREF
  char v10; // [rsp+60h] [rbp-78h]
  DWORD BytesReturned; // [rsp+E0h] [rbp+8h] BYREF

  BytesReturned = 0;
  memset_0(OutBuffer, 0, 0x90u);
  if ( !lpFileName || !a2 )
    return 2147500035LL;
  FileW = CreateFileW(lpFileName, 0, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else if ( DeviceIoControl(FileW, 0x70048u, 0, 0, OutBuffer, 0x90u, &BytesReturned, 0) )
  {
    CloseHandle(FileW);
    if ( OutBuffer[0] )
    {
      return (unsigned int)-1063256060;
    }
    else
    {
      v6 = 0;
      *a2 = v10 == 39;
    }
  }
  else
  {
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    CloseHandle(FileW);
  }
  return v6;
}

```

## disassembly

```asm
0x180007824  mov     rax, rsp
0x180007827  mov     [rax+10h], rbx
0x18000782b  mov     [rax+18h], rsi
0x18000782f  push    rdi
0x180007830  sub     rsp, 0D0h
0x180007837  mov     rsi, rdx
0x18000783a  mov     dword ptr [rax+8], 0
0x180007841  mov     rbx, rcx
0x180007844  xor     edx, edx; Val
0x180007846  lea     rcx, [rsp+0D8h+OutBuffer]; void *
0x18000784b  mov     r8d, 90h; Size
0x180007851  call    memset_0
0x180007856  test    rbx, rbx
0x180007859  jz      loc_180007943
0x18000785f  test    rsi, rsi
0x180007862  jz      loc_180007943
0x180007868  xor     r9d, r9d; lpSecurityAttributes
0x18000786b  mov     [rsp+0D8h+hTemplateFile], 0; hTemplateFile
0x180007874  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000787c  xor     edx, edx; dwDesiredAccess
0x18000787e  mov     rcx, rbx; lpFileName
0x180007881  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180007889  lea     r8d, [r9+1]; dwShareMode
0x18000788d  call    cs:__imp_CreateFileW
0x180007893  mov     rdi, rax
0x180007896  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000789a  jnz     short loc_1800078BA
0x18000789c  call    cs:__imp_GetLastError
0x1800078a2  mov     ebx, eax
0x1800078a4  test    eax, eax
0x1800078a6  jle     loc_18000793F
0x1800078ac  movzx   ebx, ax
0x1800078af  or      ebx, 80070000h
0x1800078b5  jmp     loc_18000793F
0x1800078ba  mov     [rsp+0D8h+lpOverlapped], 0; lpOverlapped
0x1800078c3  lea     rax, [rsp+0D8h+BytesReturned]
0x1800078cb  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x1800078d0  xor     r9d, r9d; nInBufferSize
0x1800078d3  lea     rax, [rsp+0D8h+OutBuffer]
0x1800078d8  mov     [rsp+0D8h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x1800078e0  xor     r8d, r8d; lpInBuffer
0x1800078e3  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax; lpOutBuffer
0x1800078e8  mov     edx, 70048h; dwIoControlCode
0x1800078ed  mov     rcx, rdi; hDevice
0x1800078f0  call    cs:__imp_DeviceIoControl
0x1800078f6  test    eax, eax
0x1800078f8  jnz     short loc_18000791A
0x1800078fa  call    cs:__imp_GetLastError
0x180007900  mov     ebx, eax
0x180007902  test    eax, eax
0x180007904  jle     short loc_18000790F
0x180007906  movzx   ebx, ax
0x180007909  or      ebx, 80070000h
0x18000790f  mov     rcx, rdi; hObject
0x180007912  call    cs:__imp_CloseHandle
0x180007918  jmp     short loc_18000793F
0x18000791a  mov     rcx, rdi; hObject
0x18000791d  call    cs:__imp_CloseHandle
0x180007923  cmp     [rsp+0D8h+OutBuffer], 0
0x180007928  jz      short loc_180007931
0x18000792a  mov     ebx, 0C0A00004h
0x18000792f  jmp     short loc_18000793F
0x180007931  xor     ecx, ecx
0x180007933  xor     ebx, ebx
0x180007935  cmp     [rsp+0D8h+var_78], 27h ; '''
0x18000793a  setz    cl
0x18000793d  mov     [rsi], ecx
0x18000793f  mov     eax, ebx
0x180007941  jmp     short loc_180007948
0x180007943  mov     eax, 80004003h
0x180007948  lea     r11, [rsp+0D8h+var_8]
0x180007950  mov     rbx, [r11+18h]
0x180007954  mov     rsi, [r11+20h]
0x180007958  mov     rsp, r11
0x18000795b  pop     rdi
0x18000795c  retn
```
