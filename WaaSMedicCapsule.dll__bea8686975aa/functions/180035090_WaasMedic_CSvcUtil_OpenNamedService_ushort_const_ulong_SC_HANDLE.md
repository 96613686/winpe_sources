# WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)

- ea: `0x180035090`
- end: `0x180035150`
- name: `?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, DWORD dwDesiredAccess, struct SC_HANDLE__ **)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180033fa8`
- `0x180035efc`
- `0x18003613c`
- `0x18004ca5c`

## callees

- `0x180009a34`
- `0x180009a54`
- `0x180035090`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180035112`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180035112`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800350e3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800350e3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003513f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003513f`

## string_xrefs

- `0x1800350da`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::OpenNamedService(
        LPCWSTR lpServiceName,
        DWORD dwDesiredAccess,
        struct SC_HANDLE__ **a3)
{
  __int64 v6; // rdx
  SC_HANDLE v8; // rax
  const char *v9; // r9
  SC_HANDLE v10; // rbx
  SC_HANDLE v11; // rax
  const char *v12; // r9
  unsigned int LastError; // edi
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !lpServiceName )
  {
    v6 = 484;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      v14);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v6 = 485;
    goto LABEL_3;
  }
  v8 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v10 = v8;
  if ( !v8 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1E8,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
             v9);
  v11 = OpenServiceW(v8, lpServiceName, dwDesiredAccess);
  if ( v11 )
  {
    *a3 = v11;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1EB,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
                  v12);
  }
  CloseServiceHandle(v10);
  return LastError;
}

```

## disassembly

```asm
0x180035090  push    rbx
0x180035092  push    rbp
0x180035093  push    rsi
0x180035094  push    rdi
0x180035095  sub     rsp, 28h
0x180035099  mov     rdi, r8
0x18003509c  mov     ebp, edx
0x18003509e  mov     rsi, rcx
0x1800350a1  test    rcx, rcx
0x1800350a4  jnz     short loc_1800350C8
0x1800350a6  mov     edx, 1E4h; void *
0x1800350ab  mov     rcx, [rsp+48h]; this
0x1800350b0  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800350b7  mov     ebx, 80004003h
0x1800350bc  mov     r9d, ebx; char *
0x1800350bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800350c4  mov     eax, ebx
0x1800350c6  jmp     short loc_180035147
0x1800350c8  test    rdi, rdi
0x1800350cb  jnz     short loc_1800350D4
0x1800350cd  mov     edx, 1E5h
0x1800350d2  jmp     short loc_1800350AB
0x1800350d4  mov     r8d, 1; dwDesiredAccess
0x1800350da  lea     rdx, DatabaseName; "ServicesActive"
0x1800350e1  xor     ecx, ecx; lpMachineName
0x1800350e3  call    cs:__imp_OpenSCManagerW
0x1800350e9  mov     rbx, rax
0x1800350ec  test    rax, rax
0x1800350ef  jnz     short loc_180035109
0x1800350f1  mov     rcx, [rsp+48h]; this
0x1800350f6  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800350fd  mov     edx, 1E8h; void *
0x180035102  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035107  jmp     short loc_180035147
0x180035109  mov     r8d, ebp; dwDesiredAccess
0x18003510c  mov     rdx, rsi; lpServiceName
0x18003510f  mov     rcx, rbx; hSCManager
0x180035112  call    cs:__imp_OpenServiceW
0x180035118  test    rax, rax
0x18003511b  jnz     short loc_180035137
0x18003511d  mov     rcx, [rsp+48h]; this
0x180035122  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180035129  mov     edx, 1EBh; void *
0x18003512e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035133  mov     edi, eax
0x180035135  jmp     short loc_18003513C
0x180035137  mov     [rdi], rax
0x18003513a  xor     edi, edi
0x18003513c  mov     rcx, rbx; hSCObject
0x18003513f  call    cs:__imp_CloseServiceHandle
0x180035145  mov     eax, edi
0x180035147  add     rsp, 28h
0x18003514b  pop     rdi
0x18003514c  pop     rsi
0x18003514d  pop     rbp
0x18003514e  pop     rbx
0x18003514f  retn
```
