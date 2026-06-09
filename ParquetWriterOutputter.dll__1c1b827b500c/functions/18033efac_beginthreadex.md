# _beginthreadex

- ea: `0x18033efac`
- end: `0x18033f080`
- name: `_beginthreadex`
- size: `212`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1802eeae0`
- `0x18030a270`

## callees

- `0x180334620`
- `0x180334700`
- `0x180334770`
- `0x18033ef4c`
- `0x18033efac`
- `0x18034962c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033f01f`
- `KERNEL32!GetLastError` at `0x18033f01f`
- `KERNEL32!CloseHandle` at `0x18033f03c`
- `KERNEL32!CloseHandle` at `0x18033f03c`
- `KERNEL32!CreateThread` at `0x18033f011`
- `KERNEL32!CreateThread` at `0x18033f011`
- `KERNEL32!FreeLibrary` at `0x18033f04b`
- `KERNEL32!FreeLibrary` at `0x18033f04b`

## pseudocode

```c
uintptr_t __cdecl beginthreadex(
        void *Security,
        unsigned int StackSize,
        _beginthreadex_proc_type StartAddress,
        void *ArgList,
        unsigned int InitFlag,
        unsigned int *ThrdAddr)
{
  SIZE_T v6; // rdi
  _QWORD *thread_parameter; // rbx
  HANDLE v10; // rdi
  DWORD LastError; // eax
  void *v12; // rcx
  HMODULE v13; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  v6 = StackSize;
  if ( !StartAddress )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  thread_parameter = (_QWORD *)create_thread_parameter((LPCWSTR)StartAddress);
  if ( thread_parameter )
  {
    v10 = CreateThread(
            (LPSECURITY_ATTRIBUTES)Security,
            v6,
            thread_start_unsigned_int____cdecl___void_____ptr64__,
            thread_parameter,
            InitFlag,
            &ThreadId);
    if ( v10 )
    {
      if ( ThrdAddr )
        *ThrdAddr = ThreadId;
      thread_parameter = 0;
      goto LABEL_7;
    }
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
  }
  v10 = 0;
LABEL_7:
  if ( thread_parameter )
  {
    v12 = (void *)thread_parameter[2];
    if ( v12 )
      CloseHandle(v12);
    v13 = (HMODULE)thread_parameter[3];
    if ( v13 )
      FreeLibrary(v13);
    free_base(thread_parameter);
  }
  return (uintptr_t)v10;
}

```

## disassembly

```asm
0x18033efac  mov     [rsp+arg_0], rbx
0x18033efb1  mov     [rsp+arg_8], rsi
0x18033efb6  push    rdi
0x18033efb7  sub     rsp, 30h
0x18033efbb  mov     edi, edx
0x18033efbd  mov     rsi, rcx
0x18033efc0  test    r8, r8
0x18033efc3  jnz     short loc_18033EFDC
0x18033efc5  call    _errno
0x18033efca  mov     dword ptr [rax], 16h
0x18033efd0  call    _invalid_parameter_noinfo
0x18033efd5  xor     eax, eax
0x18033efd7  jmp     loc_18033F05C
0x18033efdc  mov     rdx, r9
0x18033efdf  mov     rcx, r8; lpModuleName
0x18033efe2  call    create_thread_parameter
0x18033efe7  mov     rbx, rax
0x18033efea  test    rax, rax
0x18033efed  jz      short loc_18033F02C
0x18033efef  lea     rax, [rsp+38h+ThreadId]
0x18033eff4  mov     rdx, rdi; dwStackSize
0x18033eff7  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18033effc  lea     r8, thread_start_unsigned_int____cdecl___void_____ptr64__; lpStartAddress
0x18033f003  mov     eax, [rsp+38h+InitFlag]
0x18033f007  mov     r9, rbx; lpParameter
0x18033f00a  mov     rcx, rsi; lpThreadAttributes
0x18033f00d  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x18033f011  call    cs:__imp_CreateThread
0x18033f017  mov     rdi, rax
0x18033f01a  test    rax, rax
0x18033f01d  jnz     short loc_18033F06C
0x18033f01f  call    cs:__imp_GetLastError
0x18033f025  mov     ecx, eax
0x18033f027  call    __acrt_errno_map_os_error
0x18033f02c  xor     edi, edi
0x18033f02e  test    rbx, rbx
0x18033f031  jz      short loc_18033F059
0x18033f033  mov     rcx, [rbx+10h]; hObject
0x18033f037  test    rcx, rcx
0x18033f03a  jz      short loc_18033F042
0x18033f03c  call    cs:__imp_CloseHandle
0x18033f042  mov     rcx, [rbx+18h]; hLibModule
0x18033f046  test    rcx, rcx
0x18033f049  jz      short loc_18033F051
0x18033f04b  call    cs:__imp_FreeLibrary
0x18033f051  mov     rcx, rbx; Block
0x18033f054  call    _free_base
0x18033f059  mov     rax, rdi
0x18033f05c  mov     rbx, [rsp+38h+arg_0]
0x18033f061  mov     rsi, [rsp+38h+arg_8]
0x18033f066  add     rsp, 30h
0x18033f06a  pop     rdi
0x18033f06b  retn
0x18033f06c  mov     rcx, [rsp+38h+ThrdAddr]
0x18033f071  test    rcx, rcx
0x18033f074  jz      short loc_18033F07C
0x18033f076  mov     eax, [rsp+38h+ThreadId]
0x18033f07a  mov     [rcx], eax
0x18033f07c  xor     ebx, ebx
0x18033f07e  jmp     short loc_18033F02E
```
