# _beginthreadex

- ea: `0x140059fe0`
- end: `0x14005a0be`
- name: `_beginthreadex`
- size: `222`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140013274`
- `0x140096ab0`
- `0x140097924`
- `0x140098998`
- `0x140098c70`
- `0x1400acfa0`
- `0x1400af54c`
- `0x1400b0330`
- `0x1401010f8`

## callees

- `0x14004f7fc`
- `0x140059f7c`
- `0x140059fe0`
- `0x14005af8c`
- `0x14005affc`
- `0x140067520`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14005a074`
- `KERNEL32!CloseHandle` at `0x14005a074`
- `KERNEL32!GetLastError` at `0x14005a05e`
- `KERNEL32!GetLastError` at `0x14005a05e`
- `KERNEL32!FreeLibrary` at `0x14005a083`
- `KERNEL32!FreeLibrary` at `0x14005a083`
- `KERNEL32!CreateThread` at `0x14005a050`
- `KERNEL32!CreateThread` at `0x14005a050`

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
  uintptr_t v6; // rdi
  SIZE_T v7; // rsi
  _QWORD *thread_parameter; // rbx
  HANDLE v11; // rdx
  DWORD LastError; // eax
  void *v13; // rcx
  HMODULE v14; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v7 = StackSize;
  if ( StartAddress )
  {
    thread_parameter = (_QWORD *)create_thread_parameter((LPCWSTR)StartAddress);
    if ( thread_parameter )
    {
      ThreadId = 0;
      v11 = CreateThread(
              (LPSECURITY_ATTRIBUTES)Security,
              v7,
              thread_start_unsigned_int____cdecl___void____1_,
              thread_parameter,
              InitFlag,
              &ThreadId);
      if ( v11 )
      {
        if ( ThrdAddr )
          *ThrdAddr = ThreadId;
        return (uintptr_t)v11;
      }
      else
      {
        LastError = GetLastError();
        _acrt_errno_map_os_error(LastError);
        v13 = (void *)thread_parameter[2];
        if ( v13 )
          CloseHandle(v13);
        v14 = (HMODULE)thread_parameter[3];
        if ( v14 )
          FreeLibrary(v14);
        free_base(thread_parameter);
      }
    }
    return v6;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
}

```

## disassembly

```asm
0x140059fe0  mov     [rsp+arg_0], rbx
0x140059fe5  mov     [rsp+arg_8], rbp
0x140059fea  mov     [rsp+arg_18], rsi
0x140059fef  push    rdi
0x140059ff0  sub     rsp, 30h
0x140059ff4  xor     edi, edi
0x140059ff6  mov     esi, edx
0x140059ff8  mov     rbp, rcx
0x140059ffb  test    r8, r8
0x140059ffe  jnz     short loc_14005A017
0x14005a000  call    _errno
0x14005a005  mov     dword ptr [rax], 16h
0x14005a00b  call    _invalid_parameter_noinfo
0x14005a010  xor     eax, eax
0x14005a012  jmp     loc_14005A0A9
0x14005a017  mov     rdx, r9
0x14005a01a  mov     rcx, r8; lpModuleName
0x14005a01d  call    create_thread_parameter
0x14005a022  mov     rbx, rax
0x14005a025  test    rax, rax
0x14005a028  jz      short loc_14005A0A6
0x14005a02a  lea     rax, [rsp+38h+ThreadId]
0x14005a02f  mov     [rsp+38h+ThreadId], edi
0x14005a033  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14005a038  lea     r8, thread_start_unsigned_int____cdecl___void____1_; lpStartAddress
0x14005a03f  mov     eax, [rsp+38h+InitFlag]
0x14005a043  mov     rdx, rsi; dwStackSize
0x14005a046  mov     r9, rbx; lpParameter
0x14005a049  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x14005a04d  mov     rcx, rbp; lpThreadAttributes
0x14005a050  call    cs:__imp_CreateThread
0x14005a056  mov     rdx, rax
0x14005a059  test    rax, rax
0x14005a05c  jnz     short loc_14005A093
0x14005a05e  call    cs:__imp_GetLastError
0x14005a064  mov     ecx, eax
0x14005a066  call    __acrt_errno_map_os_error
0x14005a06b  mov     rcx, [rbx+10h]; hObject
0x14005a06f  test    rcx, rcx
0x14005a072  jz      short loc_14005A07A
0x14005a074  call    cs:__imp_CloseHandle
0x14005a07a  mov     rcx, [rbx+18h]; hLibModule
0x14005a07e  test    rcx, rcx
0x14005a081  jz      short loc_14005A089
0x14005a083  call    cs:__imp_FreeLibrary
0x14005a089  mov     rcx, rbx; Block
0x14005a08c  call    _free_base
0x14005a091  jmp     short loc_14005A0A6
0x14005a093  mov     rcx, [rsp+38h+ThrdAddr]
0x14005a098  test    rcx, rcx
0x14005a09b  jz      short loc_14005A0A3
0x14005a09d  mov     eax, [rsp+38h+ThreadId]
0x14005a0a1  mov     [rcx], eax
0x14005a0a3  mov     rdi, rdx
0x14005a0a6  mov     rax, rdi
0x14005a0a9  mov     rbx, [rsp+38h+arg_0]
0x14005a0ae  mov     rbp, [rsp+38h+arg_8]
0x14005a0b3  mov     rsi, [rsp+38h+arg_18]
0x14005a0b8  add     rsp, 30h
0x14005a0bc  pop     rdi
0x14005a0bd  retn
```
