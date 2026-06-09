# StartIISService(ushort const *)

- ea: `0x1800271e4`
- end: `0x18002728c`
- name: `?StartIISService@@YAJPEBG@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180015200`
- `0x1800194dc`

## callees

- `0x1800271e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027253`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027226`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027226`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002723c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002723c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002726b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027274`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002726b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027274`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002720e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002720e`

## pseudocode

```c
__int64 __fastcall StartIISService(LPCWSTR lpServiceName)
{
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  signed int LastError; // eax

  if ( lpServiceName )
  {
    v2 = 0;
    v3 = OpenSCManagerW(0, 0, 0xF003Fu);
    v4 = v3;
    if ( v3 )
    {
      v5 = OpenServiceW(v3, lpServiceName, 0x10u);
      v6 = v5;
      if ( v5 )
      {
        if ( !StartServiceW(v5, 0, 0) && GetLastError() != 1056 )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseServiceHandle(v6);
      }
      CloseServiceHandle(v4);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x1800271e4  mov     [rsp+arg_0], rbx
0x1800271e9  mov     [rsp+arg_8], rsi
0x1800271ee  push    rdi
0x1800271ef  sub     rsp, 20h
0x1800271f3  mov     rdi, rcx
0x1800271f6  test    rcx, rcx
0x1800271f9  jnz     short loc_180027202
0x1800271fb  mov     ebx, 80070057h
0x180027200  jmp     short loc_18002727A
0x180027202  xor     edx, edx; lpDatabaseName
0x180027204  xor     ecx, ecx; lpMachineName
0x180027206  mov     r8d, 0F003Fh; dwDesiredAccess
0x18002720c  xor     ebx, ebx
0x18002720e  call    cs:__imp_OpenSCManagerW
0x180027214  mov     rsi, rax
0x180027217  test    rax, rax
0x18002721a  jz      short loc_18002727A
0x18002721c  lea     r8d, [rbx+10h]; dwDesiredAccess
0x180027220  mov     rdx, rdi; lpServiceName
0x180027223  mov     rcx, rax; hSCManager
0x180027226  call    cs:__imp_OpenServiceW
0x18002722c  mov     rdi, rax
0x18002722f  test    rax, rax
0x180027232  jz      short loc_180027271
0x180027234  xor     r8d, r8d; lpServiceArgVectors
0x180027237  xor     edx, edx; dwNumServiceArgs
0x180027239  mov     rcx, rax; hService
0x18002723c  call    cs:__imp_StartServiceW
0x180027242  test    eax, eax
0x180027244  jnz     short loc_180027268
0x180027246  call    cs:__imp_GetLastError
0x18002724c  cmp     eax, 420h
0x180027251  jz      short loc_180027268
0x180027253  call    cs:__imp_GetLastError
0x180027259  mov     ebx, eax
0x18002725b  test    eax, eax
0x18002725d  jle     short loc_180027268
0x18002725f  movzx   ebx, ax
0x180027262  or      ebx, 80070000h
0x180027268  mov     rcx, rdi; hSCObject
0x18002726b  call    cs:__imp_CloseServiceHandle
0x180027271  mov     rcx, rsi; hSCObject
0x180027274  call    cs:__imp_CloseServiceHandle
0x18002727a  mov     rsi, [rsp+28h+arg_8]
0x18002727f  mov     eax, ebx
0x180027281  mov     rbx, [rsp+28h+arg_0]
0x180027286  add     rsp, 20h
0x18002728a  pop     rdi
0x18002728b  retn
```
