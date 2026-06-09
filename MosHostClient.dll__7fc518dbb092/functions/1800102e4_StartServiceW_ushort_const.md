# StartServiceW(ushort const *)

- ea: `0x1800102e4`
- end: `0x180010435`
- name: `?StartServiceW@@YAJPEBG@Z`
- size: `337`
- prototype: `signed int __fastcall(LPCWSTR lpServiceName)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000b8e8`
- `0x18000dad8`
- `0x18000f1e4`
- `0x180010038`

## callees

- `0x1800102e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001030c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001030c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103fc`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180010391`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180010391`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800102fe`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800102fe`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001036a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001036a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180010333`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180010333`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103e7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180010414`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001041d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103e7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800103f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180010414`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001041d`

## pseudocode

```c
signed int __fastcall StartServiceW(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  signed int result; // eax
  SC_HANDLE v5; // rbx
  signed int v6; // eax
  unsigned int v7; // ebx
  char v8; // si
  int v9; // eax
  signed int v10; // eax
  unsigned int v11; // esi
  signed int LastError; // eax
  unsigned int v13; // esi

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, lpServiceName, 0x14u);
    if ( v5 )
    {
      v8 = 0;
      while ( StartServiceW(v5, 0, 0) || GetLastError() == 1056 )
      {
        v9 = WaitServiceState(v5, 9, 30000);
        if ( !v9 )
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
          CloseServiceHandle(v5);
          CloseServiceHandle(v3);
          return v13;
        }
        if ( v9 == 4 )
        {
          CloseServiceHandle(v5);
          v7 = 0;
          goto LABEL_18;
        }
        if ( (unsigned __int8)++v8 >= 2u )
        {
          CloseServiceHandle(v5);
          CloseServiceHandle(v3);
          return -2147023819;
        }
      }
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      CloseServiceHandle(v5);
      v7 = v11;
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
    }
LABEL_18:
    CloseServiceHandle(v3);
    return v7;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800102e4  mov     [rsp+arg_0], rbx
0x1800102e9  mov     [rsp+arg_8], rsi
0x1800102ee  push    rdi
0x1800102ef  sub     rsp, 20h
0x1800102f3  xor     edx, edx; lpDatabaseName
0x1800102f5  mov     rbx, rcx
0x1800102f8  xor     ecx, ecx; lpMachineName
0x1800102fa  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800102fe  call    cs:__imp_OpenSCManagerW
0x180010304  mov     rdi, rax
0x180010307  test    rax, rax
0x18001030a  jnz     short loc_180010327
0x18001030c  call    cs:__imp_GetLastError
0x180010312  test    eax, eax
0x180010314  jle     loc_180010425
0x18001031a  movzx   eax, ax
0x18001031d  or      eax, 80070000h
0x180010322  jmp     loc_180010425
0x180010327  mov     r8d, 14h; dwDesiredAccess
0x18001032d  mov     rdx, rbx; lpServiceName
0x180010330  mov     rcx, rdi; hSCManager
0x180010333  call    cs:__imp_OpenServiceW
0x180010339  mov     rbx, rax
0x18001033c  test    rax, rax
0x18001033f  jnz     short loc_18001035F
0x180010341  call    cs:__imp_GetLastError
0x180010347  mov     ebx, eax
0x180010349  test    eax, eax
0x18001034b  jle     loc_1800103EF
0x180010351  movzx   ebx, ax
0x180010354  or      ebx, 80070000h
0x18001035a  jmp     loc_1800103EF
0x18001035f  xor     sil, sil
0x180010362  xor     r8d, r8d; lpServiceArgVectors
0x180010365  xor     edx, edx; dwNumServiceArgs
0x180010367  mov     rcx, rbx; hService
0x18001036a  call    cs:__imp_StartServiceW
0x180010370  test    eax, eax
0x180010372  jnz     short loc_180010381
0x180010374  call    cs:__imp_GetLastError
0x18001037a  cmp     eax, 420h
0x18001037f  jnz     short loc_1800103C2
0x180010381  xor     r9d, r9d
0x180010384  mov     r8d, 7530h
0x18001038a  mov     rcx, rbx
0x18001038d  lea     edx, [r9+9]
0x180010391  call    cs:__imp_WaitServiceState
0x180010397  test    eax, eax
0x180010399  jz      short loc_1800103FC
0x18001039b  cmp     eax, 4
0x18001039e  jz      short loc_1800103E4
0x1800103a0  inc     sil
0x1800103a3  cmp     sil, 2
0x1800103a7  jb      short loc_180010362
0x1800103a9  mov     rcx, rbx; hSCObject
0x1800103ac  call    cs:__imp_CloseServiceHandle
0x1800103b2  mov     rcx, rdi; hSCObject
0x1800103b5  call    cs:__imp_CloseServiceHandle
0x1800103bb  mov     eax, 80070435h
0x1800103c0  jmp     short loc_180010425
0x1800103c2  call    cs:__imp_GetLastError
0x1800103c8  mov     esi, eax
0x1800103ca  test    eax, eax
0x1800103cc  jle     short loc_1800103D7
0x1800103ce  movzx   esi, ax
0x1800103d1  or      esi, 80070000h
0x1800103d7  mov     rcx, rbx; hSCObject
0x1800103da  call    cs:__imp_CloseServiceHandle
0x1800103e0  mov     ebx, esi
0x1800103e2  jmp     short loc_1800103EF
0x1800103e4  mov     rcx, rbx; hSCObject
0x1800103e7  call    cs:__imp_CloseServiceHandle
0x1800103ed  xor     ebx, ebx
0x1800103ef  mov     rcx, rdi; hSCObject
0x1800103f2  call    cs:__imp_CloseServiceHandle
0x1800103f8  mov     eax, ebx
0x1800103fa  jmp     short loc_180010425
0x1800103fc  call    cs:__imp_GetLastError
0x180010402  mov     esi, eax
0x180010404  test    eax, eax
0x180010406  jle     short loc_180010411
0x180010408  movzx   esi, ax
0x18001040b  or      esi, 80070000h
0x180010411  mov     rcx, rbx; hSCObject
0x180010414  call    cs:__imp_CloseServiceHandle
0x18001041a  mov     rcx, rdi; hSCObject
0x18001041d  call    cs:__imp_CloseServiceHandle
0x180010423  mov     eax, esi
0x180010425  mov     rbx, [rsp+28h+arg_0]
0x18001042a  mov     rsi, [rsp+28h+arg_8]
0x18001042f  add     rsp, 20h
0x180010433  pop     rdi
0x180010434  retn
```
