# CDlpOSInfoT<CUnknownImpl<IUnknown>>::GetBinaryMachineType(ushort const *,ushort *)

- ea: `0x14000ea18`
- end: `0x14000ebf6`
- name: `?GetBinaryMachineType@?$CDlpOSInfoT@V?$CUnknownImpl@UIUnknown@@@@@@CAJPEBGPEAG@Z`
- size: `478`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000f90c`
- `0x14000fbf0`

## callees

- `0x140002116`
- `0x1400076c8`
- `0x14000ea18`
- `0x1400135b8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000ebc0`
- `KERNEL32!CloseHandle` at `0x14000ebc0`
- `KERNEL32!SetFilePointerEx` at `0x14000eb55`
- `KERNEL32!SetFilePointerEx` at `0x14000eb55`
- `KERNEL32!GetLastError` at `0x14000ead0`
- `KERNEL32!GetLastError` at `0x14000ead0`
- `KERNEL32!ReadFile` at `0x14000eb22`
- `KERNEL32!ReadFile` at `0x14000eb91`
- `KERNEL32!ReadFile` at `0x14000eb22`
- `KERNEL32!ReadFile` at `0x14000eb91`
- `KERNEL32!CreateFileW` at `0x14000eab6`
- `KERNEL32!CreateFileW` at `0x14000eab6`

## pseudocode

```c
__int64 __fastcall CDlpOSInfoT<CUnknownImpl<IUnknown>>::GetBinaryMachineType(LPCWSTR lpFileName, _WORD *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // ecx
  HANDLE FileW; // rcx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Buffer[30]; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+8Ch] [rbp-74h]
  _BYTE v13[4]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v14; // [rsp+94h] [rbp-6Ch]

  v4 = -1;
  memset_0(Buffer, 0, 0x40u);
  memset_0(v13, 0, 0x108u);
  v5 = 0;
  NumberOfBytesRead = 0;
  if ( !lpFileName || !a2 )
  {
    v6 = -2147024809;
LABEL_3:
    v5 = v6;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_18;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    goto LABEL_7;
  v4 = (__int64)FileW;
  memset_0(Buffer, 0, 0x40u);
  if ( !ReadFile((HANDLE)v4, Buffer, 0x40u, &NumberOfBytesRead, 0) )
    goto LABEL_7;
  if ( Buffer[0] != 23117 )
  {
    v6 = -2147024883;
    goto LABEL_3;
  }
  if ( !SetFilePointerEx((HANDLE)v4, (LARGE_INTEGER)v12, 0, 0)
    || (memset_0(v13, 0, 0x108u), !ReadFile((HANDLE)v4, v13, 0x108u, &NumberOfBytesRead, 0)) )
  {
LABEL_7:
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    v5 = LastError;
    v6 = LastError;
    goto LABEL_4;
  }
  *a2 = v14;
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
  return v5;
}

```

## disassembly

```asm
0x14000ea18  mov     [rsp-8+arg_10], rbx
0x14000ea1d  mov     [rsp-8+arg_18], rsi
0x14000ea22  push    rbp
0x14000ea23  push    rdi
0x14000ea24  push    r14
0x14000ea26  lea     rbp, [rsp-0B0h]
0x14000ea2e  sub     rsp, 1B0h
0x14000ea35  mov     rax, cs:__security_cookie
0x14000ea3c  xor     rax, rsp
0x14000ea3f  mov     [rbp+0C0h+var_20], rax
0x14000ea46  mov     rsi, rdx
0x14000ea49  mov     r14, rcx
0x14000ea4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000ea50  lea     rcx, [rsp+1C0h+Buffer]; void *
0x14000ea55  xor     edx, edx; Val
0x14000ea57  lea     r8d, [rbx+41h]; Size
0x14000ea5b  call    memset_0
0x14000ea60  xor     edx, edx; Val
0x14000ea62  lea     rcx, [rbp+0C0h+var_130]; void *
0x14000ea66  mov     r8d, 108h; Size
0x14000ea6c  call    memset_0
0x14000ea71  xor     edi, edi
0x14000ea73  mov     [rsp+1C0h+NumberOfBytesRead], edi
0x14000ea77  test    r14, r14
0x14000ea7a  jnz     short loc_14000EA8D
0x14000ea7c  mov     ecx, 80070057h
0x14000ea81  mov     edi, ecx
0x14000ea83  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000ea88  jmp     loc_14000EBAC
0x14000ea8d  test    rsi, rsi
0x14000ea90  jz      short loc_14000EA7C
0x14000ea92  xor     r9d, r9d; lpSecurityAttributes
0x14000ea95  mov     [rsp+1C0h+hTemplateFile], rdi; hTemplateFile
0x14000ea9a  mov     [rsp+1C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000eaa2  mov     edx, 80000000h; dwDesiredAccess
0x14000eaa7  mov     rcx, r14; lpFileName
0x14000eaaa  mov     [rsp+1C0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000eab2  lea     r8d, [r9+1]; dwShareMode
0x14000eab6  call    cs:__imp_CreateFileW
0x14000eabd  nop     dword ptr [rax+rax+00h]
0x14000eac2  mov     rcx, rax
0x14000eac5  inc     rax
0x14000eac8  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000eace  jnz     short loc_14000EAF7
0x14000ead0  call    cs:__imp_GetLastError
0x14000ead7  nop     dword ptr [rax+rax+00h]
0x14000eadc  test    eax, eax
0x14000eade  jnz     short loc_14000EAE7
0x14000eae0  mov     eax, 80004005h
0x14000eae5  jmp     short loc_14000EAF1
0x14000eae7  jle     short loc_14000EAF1
0x14000eae9  movzx   eax, ax
0x14000eaec  or      eax, 80070000h
0x14000eaf1  mov     edi, eax
0x14000eaf3  mov     ecx, eax
0x14000eaf5  jmp     short loc_14000EA83
0x14000eaf7  xor     edx, edx; Val
0x14000eaf9  mov     rbx, rcx
0x14000eafc  lea     rcx, [rsp+1C0h+Buffer]; void *
0x14000eb01  lea     r8d, [rdx+40h]; Size
0x14000eb05  call    memset_0
0x14000eb0a  mov     rcx, rbx; hFile
0x14000eb0d  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOverlapped
0x14000eb12  lea     r9, [rsp+1C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000eb17  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x14000eb1d  lea     rdx, [rsp+1C0h+Buffer]; lpBuffer
0x14000eb22  call    cs:__imp_ReadFile
0x14000eb29  nop     dword ptr [rax+rax+00h]
0x14000eb2e  test    eax, eax
0x14000eb30  jz      short loc_14000EAD0
0x14000eb32  mov     eax, 5A4Dh
0x14000eb37  cmp     ax, [rsp+1C0h+Buffer]
0x14000eb3c  jz      short loc_14000EB48
0x14000eb3e  mov     ecx, 8007000Dh
0x14000eb43  jmp     loc_14000EA81
0x14000eb48  movsxd  rdx, [rbp+0C0h+var_134]; liDistanceToMove
0x14000eb4c  mov     rcx, rbx; hFile
0x14000eb4f  xor     r9d, r9d; dwMoveMethod
0x14000eb52  xor     r8d, r8d; lpNewFilePointer
0x14000eb55  call    cs:__imp_SetFilePointerEx
0x14000eb5c  nop     dword ptr [rax+rax+00h]
0x14000eb61  test    eax, eax
0x14000eb63  jz      loc_14000EAD0
0x14000eb69  xor     edx, edx; Val
0x14000eb6b  lea     rcx, [rbp+0C0h+var_130]; void *
0x14000eb6f  mov     r8d, 108h; Size
0x14000eb75  call    memset_0
0x14000eb7a  mov     rcx, rbx; hFile
0x14000eb7d  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOverlapped
0x14000eb82  lea     r9, [rsp+1C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000eb87  mov     r8d, 108h; nNumberOfBytesToRead
0x14000eb8d  lea     rdx, [rbp+0C0h+var_130]; lpBuffer
0x14000eb91  call    cs:__imp_ReadFile
0x14000eb98  nop     dword ptr [rax+rax+00h]
0x14000eb9d  test    eax, eax
0x14000eb9f  jz      loc_14000EAD0
0x14000eba5  movzx   ecx, [rbp+0C0h+var_12C]
0x14000eba9  mov     [rsi], cx
0x14000ebac  mov     ecx, edi
0x14000ebae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ebb3  lea     rcx, [rbx-1]
0x14000ebb7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000ebbb  ja      short loc_14000EBCC
0x14000ebbd  mov     rcx, rbx; hObject
0x14000ebc0  call    cs:__imp_CloseHandle
0x14000ebc7  nop     dword ptr [rax+rax+00h]
0x14000ebcc  mov     eax, edi
0x14000ebce  mov     rcx, [rbp+0C0h+var_20]
0x14000ebd5  xor     rcx, rsp; StackCookie
0x14000ebd8  call    __security_check_cookie
0x14000ebdd  lea     r11, [rsp+1C0h+var_10]
0x14000ebe5  mov     rbx, [r11+30h]
0x14000ebe9  mov     rsi, [r11+38h]
0x14000ebed  mov     rsp, r11
0x14000ebf0  pop     r14
0x14000ebf2  pop     rdi
0x14000ebf3  pop     rbp
0x14000ebf4  retn
```
