# WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)

- ea: `0x1800378e8`
- end: `0x1800379aa`
- name: `?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z`
- size: `194`
- prototype: `static int(const unsigned __int16 *, unsigned int, struct SC_HANDLE__ **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800376ec`
- `0x1800379b0`

## callees

- `0x18000bbb4`
- `0x18000bbd4`
- `0x1800378e8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037992`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037992`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180037965`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180037965`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180037932`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180037932`

## string_xrefs

- `0x180037929`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::OpenNamedService(const unsigned __int16 *a1, DWORD a2, struct SC_HANDLE__ **a3)
{
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rbx
  SC_HANDLE v9; // rax
  const char *v10; // r9
  unsigned int LastError; // edi
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    v6 = OpenSCManagerW(0, L"ServicesActive", 1u);
    v8 = v6;
    if ( v6 )
    {
      v9 = OpenServiceW(v6, L"w32time", a2);
      if ( v9 )
      {
        *a3 = v9;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1EB,
                      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
                      v10);
      }
      CloseServiceHandle(v8);
      return LastError;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1E8,
               (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
               v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800378e8  mov     [rsp+arg_0], rbx
0x1800378ed  mov     [rsp+arg_8], rsi
0x1800378f2  push    rdi; int
0x1800378f3  sub     rsp, 20h
0x1800378f7  mov     rdi, r8
0x1800378fa  mov     esi, edx
0x1800378fc  test    r8, r8
0x1800378ff  jnz     short loc_180037923
0x180037901  mov     rcx, [rsp+28h]; this
0x180037906  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003790d  mov     ebx, 80004003h
0x180037912  mov     edx, 1E5h; void *
0x180037917  mov     r9d, ebx; char *
0x18003791a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003791f  mov     eax, ebx
0x180037921  jmp     short loc_18003799A
0x180037923  mov     r8d, 1; dwDesiredAccess
0x180037929  lea     rdx, DatabaseName; "ServicesActive"
0x180037930  xor     ecx, ecx; lpMachineName
0x180037932  call    cs:__imp_OpenSCManagerW
0x180037938  mov     rbx, rax
0x18003793b  test    rax, rax
0x18003793e  jnz     short loc_180037958
0x180037940  mov     rcx, [rsp+28h]; this
0x180037945  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003794c  mov     edx, 1E8h; void *
0x180037951  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037956  jmp     short loc_18003799A
0x180037958  mov     r8d, esi; dwDesiredAccess
0x18003795b  lea     rdx, ServiceName; "w32time"
0x180037962  mov     rcx, rbx; hSCManager
0x180037965  call    cs:__imp_OpenServiceW
0x18003796b  test    rax, rax
0x18003796e  jnz     short loc_18003798A
0x180037970  mov     rcx, [rsp+28h]; this
0x180037975  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003797c  mov     edx, 1EBh; void *
0x180037981  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037986  mov     edi, eax
0x180037988  jmp     short loc_18003798F
0x18003798a  mov     [rdi], rax
0x18003798d  xor     edi, edi
0x18003798f  mov     rcx, rbx; hSCObject
0x180037992  call    cs:__imp_CloseServiceHandle
0x180037998  mov     eax, edi
0x18003799a  mov     rbx, [rsp+28h+arg_0]
0x18003799f  mov     rsi, [rsp+28h+arg_8]
0x1800379a4  add     rsp, 20h
0x1800379a8  pop     rdi
0x1800379a9  retn
```
