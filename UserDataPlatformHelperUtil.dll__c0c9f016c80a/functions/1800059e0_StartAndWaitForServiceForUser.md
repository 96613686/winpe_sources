# StartAndWaitForServiceForUser

- ea: `0x1800059e0`
- end: `0x180005bdd`
- name: `StartAndWaitForServiceForUser`
- size: `509`
- prototype: `signed int __fastcall(_WORD *, SC_HANDLE, __int64, unsigned int, DWORD dwNumServiceArgs, LPCWSTR *lpServiceArgVectors, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800059a0`

## callees

- `0x1800054b0`
- `0x1800059e0`
- `0x18000a190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005a2d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005a2d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005a62`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ac3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b54`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b62`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b92`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ba5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005bb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005a62`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ac3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b54`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b62`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005b92`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ba5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005bb3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005a98`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005a98`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180005ae2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180005ae2`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005b06`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005b06`

## pseudocode

```c
signed int __fastcall StartAndWaitForServiceForUser(
        _WORD *a1,
        SC_HANDLE a2,
        __int64 a3,
        unsigned int a4,
        DWORD dwNumServiceArgs,
        LPCWSTR *lpServiceArgVectors,
        int *a7)
{
  SC_HANDLE v7; // rbx
  SC_HANDLE v10; // rdi
  SC_HANDLE v12; // rax
  int UserModeServiceName; // esi
  signed int result; // eax
  SC_HANDLE v15; // rdi
  signed int v16; // eax
  unsigned int v17; // edi
  int v18; // esi
  char v19; // bp
  int v20; // eax
  signed int LastError; // eax
  WCHAR ServiceName[264]; // [rsp+20h] [rbp-258h] BYREF

  v7 = 0;
  v10 = a2;
  if ( !a2 )
  {
    v12 = OpenSCManagerW(0, 0, 1u);
    v10 = v12;
    if ( !v12 )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v7 = v12;
  }
  UserModeServiceName = GenerateUserModeServiceName(a1, ServiceName, 0x104u, a3);
  if ( UserModeServiceName < 0 )
  {
LABEL_5:
    if ( v7 )
      CloseServiceHandle(v7);
    return UserModeServiceName;
  }
  v15 = OpenServiceW(v10, ServiceName, 0x14u);
  if ( v15 )
  {
    v18 = 0;
    v19 = 0;
    while ( 1 )
    {
      if ( !StartServiceW(v15, dwNumServiceArgs, lpServiceArgVectors) && GetLastError() != 1056 )
        goto LABEL_23;
      v20 = WaitServiceState(v15, 9, a4);
      if ( !v20 )
        break;
      if ( v20 == 4 )
      {
        v18 = 1;
LABEL_27:
        if ( !a7 )
        {
          if ( !v18 )
          {
            CloseServiceHandle(v15);
            if ( v7 )
              CloseServiceHandle(v7);
            return -2147023819;
          }
          goto LABEL_38;
        }
LABEL_37:
        *a7 = v18;
LABEL_38:
        CloseServiceHandle(v15);
        if ( v7 )
          CloseServiceHandle(v7);
        return 0;
      }
      if ( (unsigned __int8)++v19 >= 2u )
        goto LABEL_27;
    }
    if ( GetLastError() != 1460 )
    {
LABEL_23:
      LastError = GetLastError();
      UserModeServiceName = LastError;
      if ( LastError > 0 )
        UserModeServiceName = (unsigned __int16)LastError | 0x80070000;
      CloseServiceHandle(v15);
      goto LABEL_5;
    }
    if ( a7 )
      goto LABEL_37;
    CloseServiceHandle(v15);
    if ( v7 )
      CloseServiceHandle(v7);
    return -2147023826;
  }
  else
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v7 )
      CloseServiceHandle(v7);
    return v17;
  }
}

```

## disassembly

```asm
0x1800059e0  push    rbx
0x1800059e2  push    rbp
0x1800059e3  push    rsi
0x1800059e4  push    rdi
0x1800059e5  push    r12
0x1800059e7  push    r14
0x1800059e9  push    r15
0x1800059eb  sub     rsp, 240h
0x1800059f2  mov     rax, cs:__security_cookie
0x1800059f9  xor     rax, rsp
0x1800059fc  mov     [rsp+278h+var_48], rax
0x180005a04  mov     r15, [rsp+278h+lpServiceArgVectors]
0x180005a0c  xor     ebx, ebx
0x180005a0e  mov     r14, [rsp+278h+arg_30]
0x180005a16  mov     r12d, r9d
0x180005a19  mov     rbp, r8
0x180005a1c  mov     rdi, rdx
0x180005a1f  mov     rsi, rcx
0x180005a22  test    rdx, rdx
0x180005a25  jnz     short loc_180005A3E
0x180005a27  xor     ecx, ecx; lpMachineName
0x180005a29  lea     r8d, [rbx+1]; dwDesiredAccess
0x180005a2d  call    cs:__imp_OpenSCManagerW
0x180005a33  mov     rdi, rax
0x180005a36  test    rax, rax
0x180005a39  jz      short loc_180005A6F
0x180005a3b  mov     rbx, rax
0x180005a3e  mov     r9, rbp
0x180005a41  lea     rdx, [rsp+278h+ServiceName]
0x180005a46  mov     r8d, 104h
0x180005a4c  mov     rcx, rsi
0x180005a4f  call    GenerateUserModeServiceName
0x180005a54  mov     esi, eax
0x180005a56  test    eax, eax
0x180005a58  jns     short loc_180005A8A
0x180005a5a  test    rbx, rbx
0x180005a5d  jz      short loc_180005A68
0x180005a5f  mov     rcx, rbx; hSCObject
0x180005a62  call    cs:__imp_CloseServiceHandle
0x180005a68  mov     eax, esi
0x180005a6a  jmp     loc_180005BBB
0x180005a6f  call    cs:__imp_GetLastError
0x180005a75  test    eax, eax
0x180005a77  jle     loc_180005BBB
0x180005a7d  movzx   eax, ax
0x180005a80  or      eax, 80070000h
0x180005a85  jmp     loc_180005BBB
0x180005a8a  mov     r8d, 14h; dwDesiredAccess
0x180005a90  lea     rdx, [rsp+278h+ServiceName]; lpServiceName
0x180005a95  mov     rcx, rdi; hSCManager
0x180005a98  call    cs:__imp_OpenServiceW
0x180005a9e  mov     rdi, rax
0x180005aa1  test    rax, rax
0x180005aa4  jnz     short loc_180005AD0
0x180005aa6  call    cs:__imp_GetLastError
0x180005aac  mov     edi, eax
0x180005aae  test    eax, eax
0x180005ab0  jle     short loc_180005ABB
0x180005ab2  movzx   edi, ax
0x180005ab5  or      edi, 80070000h
0x180005abb  test    rbx, rbx
0x180005abe  jz      short loc_180005AC9
0x180005ac0  mov     rcx, rbx; hSCObject
0x180005ac3  call    cs:__imp_CloseServiceHandle
0x180005ac9  mov     eax, edi
0x180005acb  jmp     loc_180005BBB
0x180005ad0  xor     esi, esi
0x180005ad2  xor     bpl, bpl
0x180005ad5  mov     edx, [rsp+278h+dwNumServiceArgs]; dwNumServiceArgs
0x180005adc  mov     r8, r15; lpServiceArgVectors
0x180005adf  mov     rcx, rdi; hService
0x180005ae2  call    cs:__imp_StartServiceW
0x180005ae8  test    eax, eax
0x180005aea  jnz     short loc_180005AF9
0x180005aec  call    cs:__imp_GetLastError
0x180005af2  cmp     eax, 420h
0x180005af7  jnz     short loc_180005B20
0x180005af9  xor     r9d, r9d
0x180005afc  mov     r8d, r12d
0x180005aff  mov     rcx, rdi
0x180005b02  lea     edx, [r9+9]
0x180005b06  call    cs:__imp_WaitServiceState
0x180005b0c  test    eax, eax
0x180005b0e  jz      short loc_180005B6F
0x180005b10  cmp     eax, 4
0x180005b13  jz      short loc_180005B43
0x180005b15  inc     bpl
0x180005b18  cmp     bpl, 2
0x180005b1c  jb      short loc_180005AD5
0x180005b1e  jmp     short loc_180005B48
0x180005b20  call    cs:__imp_GetLastError
0x180005b26  mov     esi, eax
0x180005b28  test    eax, eax
0x180005b2a  jle     short loc_180005B35
0x180005b2c  movzx   esi, ax
0x180005b2f  or      esi, 80070000h
0x180005b35  mov     rcx, rdi; hSCObject
0x180005b38  call    cs:__imp_CloseServiceHandle
0x180005b3e  jmp     loc_180005A5A
0x180005b43  mov     esi, 1
0x180005b48  test    r14, r14
0x180005b4b  jnz     short loc_180005B9F
0x180005b4d  test    esi, esi
0x180005b4f  jnz     short loc_180005BA2
0x180005b51  mov     rcx, rdi; hSCObject
0x180005b54  call    cs:__imp_CloseServiceHandle
0x180005b5a  test    rbx, rbx
0x180005b5d  jz      short loc_180005B68
0x180005b5f  mov     rcx, rbx; hSCObject
0x180005b62  call    cs:__imp_CloseServiceHandle
0x180005b68  mov     eax, 80070435h
0x180005b6d  jmp     short loc_180005BBB
0x180005b6f  call    cs:__imp_GetLastError
0x180005b75  cmp     eax, 5B4h
0x180005b7a  jnz     short loc_180005B20
0x180005b7c  test    r14, r14
0x180005b7f  jnz     short loc_180005B9F
0x180005b81  mov     rcx, rdi; hSCObject
0x180005b84  call    cs:__imp_CloseServiceHandle
0x180005b8a  test    rbx, rbx
0x180005b8d  jz      short loc_180005B98
0x180005b8f  mov     rcx, rbx; hSCObject
0x180005b92  call    cs:__imp_CloseServiceHandle
0x180005b98  mov     eax, 8007042Eh
0x180005b9d  jmp     short loc_180005BBB
0x180005b9f  mov     [r14], esi
0x180005ba2  mov     rcx, rdi; hSCObject
0x180005ba5  call    cs:__imp_CloseServiceHandle
0x180005bab  test    rbx, rbx
0x180005bae  jz      short loc_180005BB9
0x180005bb0  mov     rcx, rbx; hSCObject
0x180005bb3  call    cs:__imp_CloseServiceHandle
0x180005bb9  xor     eax, eax
0x180005bbb  mov     rcx, [rsp+278h+var_48]
0x180005bc3  xor     rcx, rsp; StackCookie
0x180005bc6  call    __security_check_cookie
0x180005bcb  add     rsp, 240h
0x180005bd2  pop     r15
0x180005bd4  pop     r14
0x180005bd6  pop     r12
0x180005bd8  pop     rdi
0x180005bd9  pop     rsi
0x180005bda  pop     rbp
0x180005bdb  pop     rbx
0x180005bdc  retn
```
