# GetProcessTokenByHandle(HWND__ *,void * *)

- ea: `0x180040b1c`
- end: `0x180040bb6`
- name: `?GetProcessTokenByHandle@@YAJPEAUHWND__@@PEAPEAX@Z`
- size: `154`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, void **tokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c770`

## callees

- `0x18003f11c`
- `0x180040a6c`
- `0x180040b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040b7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040b7e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180040b44`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180040b44`
- `USER32!GetWindowThreadProcessId` at `0x180040b32`
- `USER32!GetWindowThreadProcessId` at `0x180040b32`

## string_xrefs

- `0x180040b8d`: `com\ole32\ole232\util\utils.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessTokenByHandle(HWND hwnd, void **tokenHandle)
{
  HANDLE v3; // rax
  signed int v4; // eax
  unsigned int LastError; // ebx
  void *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int processID; // [rsp+40h] [rbp+18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > processHandle; // [rsp+48h] [rbp+20h] BYREF

  processID = 0;
  GetWindowThreadProcessId(hwnd, &processID);
  v3 = OpenProcess(0x400u, 0, processID);
  processHandle.m_ptr = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( OpenProcessToken(v3, 8u, tokenHandle) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xA28u, "com\\ole32\\ole232\\util\\utils.cpp");
  }
  else
  {
    v4 = GetLastError();
    LastError = v4;
    if ( v4 > 0 )
      LastError = (unsigned __int16)v4 | 0x80070000;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&processHandle);
  return LastError;
}

```

## disassembly

```asm
0x180040b1c  push    rbx
0x180040b1e  sub     rsp, 20h
0x180040b22  mov     rbx, tokenHandle
0x180040b25  mov     [rsp+28h+processID], 0
0x180040b2d  lea     tokenHandle, [rsp+28h+processID]; lpdwProcessId
0x180040b32  call    cs:__imp_GetWindowThreadProcessId
0x180040b38  mov     r8d, [rsp+28h+processID]; dwProcessId
0x180040b3d  xor     edx, edx; bInheritHandle
0x180040b3f  mov     ecx, 400h; dwDesiredAccess
0x180040b44  call    cs:__imp_OpenProcess
0x180040b4a  mov     [rsp+28h+processHandle.m_ptr], rax
0x180040b4f  lea     hwnd, [rax+1]
0x180040b53  test    hwnd, 0FFFFFFFFFFFFFFFEh
0x180040b5a  jnz     short loc_180040B73
0x180040b5c  call    cs:__imp_GetLastError
0x180040b62  mov     ebx, eax
0x180040b64  test    eax, eax
0x180040b66  jle     short loc_180040BA4
0x180040b68  movzx   ebx, ax
0x180040b6b  or      ebx, 80070000h
0x180040b71  jmp     short loc_180040BA4
0x180040b73  mov     r8, rbx; TokenHandle
0x180040b76  mov     edx, 8; DesiredAccess
0x180040b7b  mov     hwnd, rax; ProcessHandle
0x180040b7e  call    cs:__imp_OpenProcessToken
0x180040b84  test    eax, eax
0x180040b86  jnz     short loc_180040BA2
0x180040b88  mov     hwnd, [rsp+28h]; callerReturnAddress
0x180040b8d  lea     r8, aComOle32Ole232_0; "com\\ole32\\ole232\\util\\utils.cpp"
0x180040b94  mov     edx, 0A28h; lineNumber
0x180040b99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040b9e  mov     ebx, eax
0x180040ba0  jmp     short loc_180040BA4
0x180040ba2  xor     ebx, ebx
0x180040ba4  lea     hwnd, [rsp+28h+processHandle]; this
0x180040ba9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040bae  mov     eax, ebx
0x180040bb0  add     rsp, 20h
0x180040bb4  pop     rbx
0x180040bb5  retn
```
