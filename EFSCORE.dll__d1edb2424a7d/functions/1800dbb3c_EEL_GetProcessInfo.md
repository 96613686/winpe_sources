# EEL_GetProcessInfo

- ea: `0x1800dbb3c`
- end: `0x1800dbccc`
- name: `EEL_GetProcessInfo`
- size: `400`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800da2a0`
- `0x1800da860`
- `0x1800dacd8`
- `0x1800db1d8`
- `0x1800db688`

## callees

- `0x180005045`
- `0x1800d94b4`
- `0x1800dbb3c`
- `0x1800dbcd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dbc43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dbc43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dbc32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dbc32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dbbaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dbbaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dbb58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dbb58`
- `ntdll!ZwOpenThreadTokenEx` at `0x1800dbb80`
- `ntdll!ZwOpenThreadTokenEx` at `0x1800dbb80`
- `ntdll!ZwClose` at `0x1800dbba9`
- `ntdll!ZwClose` at `0x1800dbbf4`
- `ntdll!ZwClose` at `0x1800dbba9`
- `ntdll!ZwClose` at `0x1800dbbf4`
- `ntdll!ZwOpenProcessTokenEx` at `0x1800dbbcb`
- `ntdll!ZwOpenProcessTokenEx` at `0x1800dbbcb`
- `ntdll!ZwQueryInformationProcess` at `0x1800dbc14`
- `ntdll!ZwQueryInformationProcess` at `0x1800dbc65`
- `ntdll!ZwQueryInformationProcess` at `0x1800dbc14`
- `ntdll!ZwQueryInformationProcess` at `0x1800dbc65`

## pseudocode

```c
__int64 *__fastcall EEL_GetProcessInfo(__int64 *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v4; // rsi
  ULONG v5; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  __int64 v8; // r9
  __int16 v9; // cx
  unsigned __int16 i; // dx
  __int64 v11; // r8
  __int16 v12; // cx
  ULONG ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+38h] BYREF
  HANDLE v16; // [rsp+70h] [rbp+40h] BYREF

  memset_0(a1, 0, 0x48u);
  CurrentThread = GetCurrentThread();
  Handle = 0;
  ZwOpenThreadTokenEx(CurrentThread, 8u, 1u, 0x200u, &Handle);
  if ( Handle )
  {
    SrpGetEnterpriseContextToken(Handle, a1 + 4);
    EEL_GetUserSidStringForToken(Handle, a1 + 7);
    ZwClose(Handle);
  }
  CurrentProcess = GetCurrentProcess();
  v16 = 0;
  v4 = CurrentProcess;
  ZwOpenProcessTokenEx(CurrentProcess, 8u, 0x200u, &v16);
  if ( v16 )
  {
    SrpGetEnterpriseContextToken(v16, a1 + 3);
    EEL_GetUserSidStringForToken(v16, a1 + 5);
    ZwClose(v16);
  }
  ReturnLength = 0;
  if ( ZwQueryInformationProcess(v4, ProcessImageFileName, 0, 0, &ReturnLength) == -1073741820 && ReturnLength > 0x10 )
  {
    v5 = ReturnLength;
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 8u, v5);
    *a1 = (__int64)v7;
    if ( v7 )
    {
      ZwQueryInformationProcess(v4, ProcessImageFileName, v7, ReturnLength, 0);
      v8 = *a1;
      a1[2] = 0;
      *((_WORD *)a1 + 4) = 0;
      v9 = *(_WORD *)v8 >> 1;
      if ( v9 )
      {
        for ( i = v9 - 1; i; --i )
        {
          v11 = *(_QWORD *)(v8 + 8);
          if ( *(_WORD *)(v11 + 2LL * i) == 92 )
          {
            v12 = 2 * (v9 - i) - 2;
            *((_WORD *)a1 + 5) = v12;
            *((_WORD *)a1 + 4) = v12;
            a1[2] = v11 + 2 * (i + 1LL);
            return a1;
          }
        }
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800dbb3c  push    rbp
0x1800dbb3e  push    rbx
0x1800dbb3f  push    rsi
0x1800dbb40  push    rdi
0x1800dbb41  push    r14
0x1800dbb43  mov     rbp, rsp
0x1800dbb46  sub     rsp, 30h
0x1800dbb4a  xor     edx, edx; Val
0x1800dbb4c  mov     rdi, rcx
0x1800dbb4f  lea     r8d, [rdx+48h]; Size
0x1800dbb53  call    memset_0
0x1800dbb58  call    cs:__imp_GetCurrentThread
0x1800dbb5e  xor     r14d, r14d
0x1800dbb61  lea     rcx, [rbp+Handle]
0x1800dbb65  mov     [rsp+30h+TokenHandle], rcx; TokenHandle
0x1800dbb6a  mov     ebx, 200h
0x1800dbb6f  mov     r9d, ebx; HandleAttributes
0x1800dbb72  mov     [rbp+Handle], r14
0x1800dbb76  mov     r8b, 1; OpenAsSelf
0x1800dbb79  mov     rcx, rax; ThreadHandle
0x1800dbb7c  lea     edx, [r14+8]; DesiredAccess
0x1800dbb80  call    cs:__imp_ZwOpenThreadTokenEx
0x1800dbb86  mov     rcx, [rbp+Handle]
0x1800dbb8a  test    rcx, rcx
0x1800dbb8d  jz      short loc_1800DBBAF
0x1800dbb8f  lea     rdx, [rdi+20h]
0x1800dbb93  call    SrpGetEnterpriseContextToken
0x1800dbb98  mov     rcx, [rbp+Handle]
0x1800dbb9c  lea     rdx, [rdi+38h]
0x1800dbba0  call    EEL_GetUserSidStringForToken
0x1800dbba5  mov     rcx, [rbp+Handle]; Handle
0x1800dbba9  call    cs:__imp_ZwClose
0x1800dbbaf  call    cs:__imp_GetCurrentProcess
0x1800dbbb5  lea     r9, [rbp+arg_10]; TokenHandle
0x1800dbbb9  mov     [rbp+arg_10], r14
0x1800dbbbd  mov     rcx, rax; ProcessHandle
0x1800dbbc0  mov     r8d, ebx; HandleAttributes
0x1800dbbc3  mov     edx, 8; DesiredAccess
0x1800dbbc8  mov     rsi, rax
0x1800dbbcb  call    cs:__imp_ZwOpenProcessTokenEx
0x1800dbbd1  mov     rcx, [rbp+arg_10]
0x1800dbbd5  test    rcx, rcx
0x1800dbbd8  jz      short loc_1800DBBFA
0x1800dbbda  lea     rdx, [rdi+18h]
0x1800dbbde  call    SrpGetEnterpriseContextToken
0x1800dbbe3  mov     rcx, [rbp+arg_10]
0x1800dbbe7  lea     rdx, [rdi+28h]
0x1800dbbeb  call    EEL_GetUserSidStringForToken
0x1800dbbf0  mov     rcx, [rbp+arg_10]; Handle
0x1800dbbf4  call    cs:__imp_ZwClose
0x1800dbbfa  xor     r9d, r9d; ProcessInformationLength
0x1800dbbfd  mov     [rbp+ReturnLength], r14d
0x1800dbc01  lea     rax, [rbp+ReturnLength]
0x1800dbc05  xor     r8d, r8d; ProcessInformation
0x1800dbc08  mov     rcx, rsi; ProcessHandle
0x1800dbc0b  mov     [rsp+30h+TokenHandle], rax; ReturnLength
0x1800dbc10  lea     edx, [r9+1Bh]; ProcessInformationClass
0x1800dbc14  call    cs:__imp_ZwQueryInformationProcess
0x1800dbc1a  cmp     eax, 0C0000004h
0x1800dbc1f  jnz     loc_1800DBCBE
0x1800dbc25  cmp     [rbp+ReturnLength], 10h
0x1800dbc29  jbe     loc_1800DBCBE
0x1800dbc2f  mov     ebx, [rbp+ReturnLength]
0x1800dbc32  call    cs:__imp_GetProcessHeap
0x1800dbc38  mov     r8d, ebx; dwBytes
0x1800dbc3b  mov     edx, 8; dwFlags
0x1800dbc40  mov     rcx, rax; hHeap
0x1800dbc43  call    cs:__imp_HeapAlloc
0x1800dbc49  mov     [rdi], rax
0x1800dbc4c  test    rax, rax
0x1800dbc4f  jz      short loc_1800DBCBE
0x1800dbc51  mov     r9d, [rbp+ReturnLength]; ProcessInformationLength
0x1800dbc55  mov     r8, rax; ProcessInformation
0x1800dbc58  mov     edx, 1Bh; ProcessInformationClass
0x1800dbc5d  mov     [rsp+30h+TokenHandle], r14; ReturnLength
0x1800dbc62  mov     rcx, rsi; ProcessHandle
0x1800dbc65  call    cs:__imp_ZwQueryInformationProcess
0x1800dbc6b  mov     r9, [rdi]
0x1800dbc6e  mov     [rdi+10h], r14
0x1800dbc72  mov     [rdi+8], r14w
0x1800dbc77  movzx   ecx, word ptr [r9]
0x1800dbc7b  shr     cx, 1
0x1800dbc7e  jz      short loc_1800DBCBE
0x1800dbc80  lea     edx, [rcx-1]
0x1800dbc83  test    dx, dx
0x1800dbc86  jz      short loc_1800DBCBE
0x1800dbc88  mov     r8, [r9+8]
0x1800dbc8c  movzx   eax, dx
0x1800dbc8f  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1800dbc95  jz      short loc_1800DBCA1
0x1800dbc97  mov     eax, 0FFFFh
0x1800dbc9c  add     dx, ax
0x1800dbc9f  jmp     short loc_1800DBC83
0x1800dbca1  inc     rax
0x1800dbca4  sub     cx, dx
0x1800dbca7  add     cx, cx
0x1800dbcaa  sub     cx, 2
0x1800dbcae  mov     [rdi+0Ah], cx
0x1800dbcb2  lea     rax, [r8+rax*2]
0x1800dbcb6  mov     [rdi+8], cx
0x1800dbcba  mov     [rdi+10h], rax
0x1800dbcbe  mov     rax, rdi
0x1800dbcc1  add     rsp, 30h
0x1800dbcc5  pop     r14
0x1800dbcc7  pop     rdi
0x1800dbcc8  pop     rsi
0x1800dbcc9  pop     rbx
0x1800dbcca  pop     rbp
0x1800dbccb  retn
```
