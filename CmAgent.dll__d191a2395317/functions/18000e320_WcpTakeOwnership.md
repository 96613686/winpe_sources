# WcpTakeOwnership

- ea: `0x18000e320`
- end: `0x18000e425`
- name: `WcpTakeOwnership`
- size: `261`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18000d8f4`
- `0x18000e014`

## callees

- `0x18000d5d0`
- `0x18000e320`
- `0x18000edcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e36c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e36c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e354`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e37c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e40e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e40e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e3f9`

## pseudocode

```c
__int64 __fastcall WcpTakeOwnership(LPWSTR pObjectName)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v4; // ebx
  NTSTATUS v5; // ebx
  HLOCAL hMem; // [rsp+20h] [rbp-10h] BYREF
  PACL ppDacl; // [rsp+28h] [rbp-8h] BYREF
  int v9; // [rsp+58h] [rbp+28h] BYREF
  int v10; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  ppDacl = 0;
  v9 = 0;
  v10 = 0;
  TokenHandle = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v5 = WcpSetPrivilege(TokenHandle, 9, 1, &v9);
    if ( v5 < 0 || (v5 = WcpSetPrivilege(TokenHandle, 18, 1, &v10), v5 < 0) )
    {
      v4 = v5 | 0x10000000;
    }
    else
    {
      v4 = WcGrantFullAccessToAdmin(pObjectName, &ppDacl, &hMem);
      if ( v4 >= 0 )
        v4 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e320  push    rbp
0x18000e322  push    rbx
0x18000e323  push    rdi
0x18000e324  mov     rbp, rsp
0x18000e327  sub     rsp, 30h
0x18000e32b  mov     rdi, rcx
0x18000e32e  mov     [rbp+ppDacl], 0
0x18000e336  mov     [rbp+arg_8], 0
0x18000e33d  mov     [rbp+arg_10], 0
0x18000e344  mov     [rbp+TokenHandle], 0
0x18000e34c  mov     [rbp+hMem], 0
0x18000e354  call    cs:__imp_GetCurrentProcess
0x18000e35b  nop     dword ptr [rax+rax+00h]
0x18000e360  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000e364  mov     edx, 28h ; '('; DesiredAccess
0x18000e369  mov     rcx, rax; ProcessHandle
0x18000e36c  call    cs:__imp_OpenProcessToken
0x18000e373  nop     dword ptr [rax+rax+00h]
0x18000e378  test    eax, eax
0x18000e37a  jnz     short loc_18000E399
0x18000e37c  call    cs:__imp_GetLastError
0x18000e383  nop     dword ptr [rax+rax+00h]
0x18000e388  mov     ebx, eax
0x18000e38a  test    eax, eax
0x18000e38c  jle     short loc_18000E3F0
0x18000e38e  movzx   ebx, ax
0x18000e391  or      ebx, 80070000h
0x18000e397  jmp     short loc_18000E3F0
0x18000e399  mov     rcx, [rbp+TokenHandle]
0x18000e39d  lea     r9, [rbp+arg_8]
0x18000e3a1  mov     edx, 9
0x18000e3a6  lea     r8d, [rdx-8]
0x18000e3aa  call    WcpSetPrivilege
0x18000e3af  mov     ebx, eax
0x18000e3b1  test    eax, eax
0x18000e3b3  jns     short loc_18000E3BB
0x18000e3b5  bts     ebx, 1Ch
0x18000e3b9  jmp     short loc_18000E3F0
0x18000e3bb  mov     rcx, [rbp+TokenHandle]
0x18000e3bf  lea     r9, [rbp+arg_10]
0x18000e3c3  mov     edx, 12h
0x18000e3c8  lea     r8d, [rdx-11h]
0x18000e3cc  call    WcpSetPrivilege
0x18000e3d1  mov     ebx, eax
0x18000e3d3  test    eax, eax
0x18000e3d5  js      short loc_18000E3B5
0x18000e3d7  lea     r8, [rbp+hMem]; ppSecurityDescriptor
0x18000e3db  mov     rcx, rdi; pObjectName
0x18000e3de  lea     rdx, [rbp+ppDacl]; ppDacl
0x18000e3e2  call    WcGrantFullAccessToAdmin
0x18000e3e7  mov     ebx, eax
0x18000e3e9  xor     eax, eax
0x18000e3eb  test    ebx, ebx
0x18000e3ed  cmovns  ebx, eax
0x18000e3f0  mov     rcx, [rbp+hMem]; hMem
0x18000e3f4  test    rcx, rcx
0x18000e3f7  jz      short loc_18000E405
0x18000e3f9  call    cs:__imp_LocalFree
0x18000e400  nop     dword ptr [rax+rax+00h]
0x18000e405  mov     rcx, [rbp+TokenHandle]; hObject
0x18000e409  test    rcx, rcx
0x18000e40c  jz      short loc_18000E41A
0x18000e40e  call    cs:__imp_CloseHandle
0x18000e415  nop     dword ptr [rax+rax+00h]
0x18000e41a  mov     eax, ebx
0x18000e41c  add     rsp, 30h
0x18000e420  pop     rdi
0x18000e421  pop     rbx
0x18000e422  pop     rbp
0x18000e423  retn
```
