# _beginthreadex

- ea: `0x18020c360`
- end: `0x18020c43e`
- name: `_beginthreadex`
- size: `222`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002d840`
- `0x180054a40`
- `0x18009e140`
- `0x18009e380`
- `0x180160b90`
- `0x180185ee0`
- `0x180186120`
- `0x180186360`
- `0x1801865a0`
- `0x180229ef0`

## callees

- `0x180206ea0`
- `0x180206fd8`
- `0x180207050`
- `0x18020c2fc`
- `0x18020c360`
- `0x180219680`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18020c3de`
- `KERNEL32!GetLastError` at `0x18020c3de`
- `KERNEL32!CloseHandle` at `0x18020c3f4`
- `KERNEL32!CloseHandle` at `0x18020c3f4`
- `KERNEL32!FreeLibrary` at `0x18020c403`
- `KERNEL32!FreeLibrary` at `0x18020c403`
- `KERNEL32!CreateThread` at `0x18020c3d0`
- `KERNEL32!CreateThread` at `0x18020c3d0`

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
0x18020c360  mov     [rsp+arg_0], rbx
0x18020c365  mov     [rsp+arg_8], rbp
0x18020c36a  mov     [rsp+arg_18], rsi
0x18020c36f  push    rdi
0x18020c370  sub     rsp, 30h
0x18020c374  xor     edi, edi
0x18020c376  mov     esi, edx
0x18020c378  mov     rbp, rcx
0x18020c37b  test    r8, r8
0x18020c37e  jnz     short loc_18020C397
0x18020c380  call    _errno
0x18020c385  mov     dword ptr [rax], 16h
0x18020c38b  call    _invalid_parameter_noinfo
0x18020c390  xor     eax, eax
0x18020c392  jmp     loc_18020C429
0x18020c397  mov     rdx, r9
0x18020c39a  mov     rcx, r8; lpModuleName
0x18020c39d  call    create_thread_parameter
0x18020c3a2  mov     rbx, rax
0x18020c3a5  test    rax, rax
0x18020c3a8  jz      short loc_18020C426
0x18020c3aa  lea     rax, [rsp+38h+ThreadId]
0x18020c3af  mov     [rsp+38h+ThreadId], edi
0x18020c3b3  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18020c3b8  lea     r8, thread_start_unsigned_int____cdecl___void____1_; lpStartAddress
0x18020c3bf  mov     eax, [rsp+38h+InitFlag]
0x18020c3c3  mov     rdx, rsi; dwStackSize
0x18020c3c6  mov     r9, rbx; lpParameter
0x18020c3c9  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x18020c3cd  mov     rcx, rbp; lpThreadAttributes
0x18020c3d0  call    cs:__imp_CreateThread
0x18020c3d6  mov     rdx, rax
0x18020c3d9  test    rax, rax
0x18020c3dc  jnz     short loc_18020C413
0x18020c3de  call    cs:__imp_GetLastError
0x18020c3e4  mov     ecx, eax
0x18020c3e6  call    __acrt_errno_map_os_error
0x18020c3eb  mov     rcx, [rbx+10h]; hObject
0x18020c3ef  test    rcx, rcx
0x18020c3f2  jz      short loc_18020C3FA
0x18020c3f4  call    cs:__imp_CloseHandle
0x18020c3fa  mov     rcx, [rbx+18h]; hLibModule
0x18020c3fe  test    rcx, rcx
0x18020c401  jz      short loc_18020C409
0x18020c403  call    cs:__imp_FreeLibrary
0x18020c409  mov     rcx, rbx; Block
0x18020c40c  call    _free_base
0x18020c411  jmp     short loc_18020C426
0x18020c413  mov     rcx, [rsp+38h+ThrdAddr]
0x18020c418  test    rcx, rcx
0x18020c41b  jz      short loc_18020C423
0x18020c41d  mov     eax, [rsp+38h+ThreadId]
0x18020c421  mov     [rcx], eax
0x18020c423  mov     rdi, rdx
0x18020c426  mov     rax, rdi
0x18020c429  mov     rbx, [rsp+38h+arg_0]
0x18020c42e  mov     rbp, [rsp+38h+arg_8]
0x18020c433  mov     rsi, [rsp+38h+arg_18]
0x18020c438  add     rsp, 30h
0x18020c43c  pop     rdi
0x18020c43d  retn
```
