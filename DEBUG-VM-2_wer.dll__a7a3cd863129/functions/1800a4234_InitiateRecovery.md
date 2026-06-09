# InitiateRecovery

- ea: `0x1800a4234`
- end: `0x1800a436a`
- name: `InitiateRecovery`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a4370`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180051b64`
- `0x180051b70`
- `0x180051b7c`
- `0x180052d61`
- `0x1800a4234`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a4328`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x1800a4328`
- `ntdll!DbgPrintEx` at `0x1800a4271`
- `ntdll!DbgPrintEx` at `0x1800a42bb`
- `ntdll!DbgPrintEx` at `0x1800a42f5`
- `ntdll!DbgPrintEx` at `0x1800a4271`
- `ntdll!DbgPrintEx` at `0x1800a42bb`
- `ntdll!DbgPrintEx` at `0x1800a42f5`

## string_xrefs

- `0x1800a4281`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall InitiateRecovery(HANDLE hProcess, char *a2, __int64 a3)
{
  DWORD CurrentProcessId_0; // eax
  HMODULE ModuleHandleW_0; // rax
  DWORD v7; // ebx
  DWORD v8; // eax
  ULONG (__stdcall *WerpInitiateRemoteRecovery)(PVOID); // rax
  DWORD v10; // eax
  unsigned int v11; // ebx
  DWORD LastError_0; // eax
  char *v13; // [rsp+58h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+60h] [rbp+18h] BYREF
  int v15; // [rsp+64h] [rbp+1Ch]

  v15 = HIDWORD(a3);
  v13 = a2;
  ThreadId = 0;
  if ( !hProcess )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid process handle passed\n", CurrentProcessId_0, 189);
    return 2147942487LL;
  }
  ModuleHandleW_0 = GetModuleHandleW_0(L"kernel32.dll");
  if ( ModuleHandleW_0 )
  {
    WerpInitiateRemoteRecovery = (ULONG (__stdcall *)(PVOID))GetProcAddress_0(
                                                               ModuleHandleW_0,
                                                               "WerpInitiateRemoteRecovery");
    if ( WerpInitiateRemoteRecovery )
    {
      v13 = (char *)CreateRemoteThread(hProcess, 0, 0, WerpInitiateRemoteRecovery, 0, 0, &ThreadId);
      if ( v13 == (char *)-1LL || v13 + 1 == (char *)1 )
      {
        LastError_0 = GetLastError_0();
        v11 = ERROR_HR_FROM_WIN32(LastError_0);
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v13);
      }
      else
      {
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v13);
        return 0;
      }
      return v11;
    }
  }
  else
  {
    v7 = GetLastError_0();
    v8 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR GetModuleHandle failed for kernel32 with %u\n", v8, 4052, v7);
  }
  v10 = GetCurrentProcessId_0();
  DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR WerpGetRecoveryEntryPointInProcess returned NULL\n", v10, 219);
  return (unsigned int)-805306055;
}

```

## disassembly

```asm
0x1800a4234  mov     qword ptr [rsp+ThreadId], r8
0x1800a4239  mov     [rsp+arg_8], rdx
0x1800a423e  push    rbx
0x1800a423f  sub     rsp, 40h
0x1800a4243  mov     [rsp+48h+ThreadId], 0
0x1800a424b  mov     rbx, rcx
0x1800a424e  test    rcx, rcx
0x1800a4251  jnz     short loc_1800A4281
0x1800a4253  call    GetCurrentProcessId_0
0x1800a4258  mov     r9d, eax
0x1800a425b  mov     dword ptr [rsp+48h+lpParameter], 0BDh
0x1800a4263  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid proce"...
0x1800a426a  xor     edx, edx; Level
0x1800a426c  mov     ecx, 96h; ComponentId
0x1800a4271  call    cs:__imp_DbgPrintEx
0x1800a4277  mov     eax, 80070057h
0x1800a427c  jmp     loc_1800A4364
0x1800a4281  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800a4288  call    GetModuleHandleW_0
0x1800a428d  test    rax, rax
0x1800a4290  jnz     short loc_1800A42C3
0x1800a4292  call    GetLastError_0
0x1800a4297  mov     ebx, eax
0x1800a4299  call    GetCurrentProcessId_0
0x1800a429e  mov     r9d, eax
0x1800a42a1  mov     [rsp+48h+dwCreationFlags], ebx
0x1800a42a5  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR GetModuleHand"...
0x1800a42ac  mov     dword ptr [rsp+48h+lpParameter], 0FD4h
0x1800a42b4  xor     edx, edx; Level
0x1800a42b6  mov     ecx, 96h; ComponentId
0x1800a42bb  call    cs:__imp_DbgPrintEx
0x1800a42c1  jmp     short loc_1800A42D7
0x1800a42c3  lea     rdx, aWerpinitiatere; "WerpInitiateRemoteRecovery"
0x1800a42ca  mov     rcx, rax; hModule
0x1800a42cd  call    GetProcAddress_0
0x1800a42d2  test    rax, rax
0x1800a42d5  jnz     short loc_1800A4302
0x1800a42d7  call    GetCurrentProcessId_0
0x1800a42dc  mov     r9d, eax
0x1800a42df  mov     dword ptr [rsp+48h+lpParameter], 0DBh
0x1800a42e7  lea     r8, aWerRecoveryUUE_4; "WER/Recovery/%u:%u: ERROR WerpGetRecove"...
0x1800a42ee  xor     edx, edx; Level
0x1800a42f0  mov     ecx, 96h; ComponentId
0x1800a42f5  call    cs:__imp_DbgPrintEx
0x1800a42fb  mov     ebx, 0D0000139h
0x1800a4300  jmp     short loc_1800A4362
0x1800a4302  lea     rcx, [rsp+48h+ThreadId]
0x1800a4307  mov     r9, rax; lpStartAddress
0x1800a430a  mov     [rsp+48h+lpThreadId], rcx; lpThreadId
0x1800a430f  xor     r8d, r8d; dwStackSize
0x1800a4312  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800a431a  mov     rcx, rbx; hProcess
0x1800a431d  xor     edx, edx; lpThreadAttributes
0x1800a431f  mov     [rsp+48h+lpParameter], 0; lpParameter
0x1800a4328  call    cs:__imp_CreateRemoteThread
0x1800a432e  mov     [rsp+48h+arg_8], rax
0x1800a4333  inc     rax
0x1800a4336  cmp     rax, 1
0x1800a433a  ja      short loc_1800A4356
0x1800a433c  call    GetLastError_0
0x1800a4341  mov     ecx, eax; unsigned int
0x1800a4343  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a4348  lea     rcx, [rsp+48h+arg_8]
0x1800a434d  mov     ebx, eax
0x1800a434f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a4354  jmp     short loc_1800A4362
0x1800a4356  lea     rcx, [rsp+48h+arg_8]
0x1800a435b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a4360  xor     ebx, ebx
0x1800a4362  mov     eax, ebx
0x1800a4364  add     rsp, 40h
0x1800a4368  pop     rbx
0x1800a4369  retn
```
