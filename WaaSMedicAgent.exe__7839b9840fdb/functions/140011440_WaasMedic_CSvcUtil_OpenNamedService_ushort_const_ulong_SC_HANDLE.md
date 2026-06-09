# WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)

- ea: `0x140011440`
- end: `0x140011502`
- name: `?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD, struct SC_HANDLE__ **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x140011244`
- `0x140011508`

## callees

- `0x140006424`
- `0x14000644c`
- `0x140011440`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400114ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400114ea`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400114bd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400114bd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001148a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14001148a`

## string_xrefs

- `0x140011481`: `ServicesActive`

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
0x140011440  mov     [rsp+arg_0], rbx
0x140011445  mov     [rsp+arg_8], rsi
0x14001144a  push    rdi; int
0x14001144b  sub     rsp, 20h
0x14001144f  mov     rdi, r8
0x140011452  mov     esi, edx
0x140011454  test    r8, r8
0x140011457  jnz     short loc_14001147B
0x140011459  mov     rcx, [rsp+28h]; this
0x14001145e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x140011465  mov     ebx, 80004003h
0x14001146a  mov     edx, 1E5h; void *
0x14001146f  mov     r9d, ebx; char *
0x140011472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011477  mov     eax, ebx
0x140011479  jmp     short loc_1400114F2
0x14001147b  mov     r8d, 1; dwDesiredAccess
0x140011481  lea     rdx, DatabaseName; "ServicesActive"
0x140011488  xor     ecx, ecx; lpMachineName
0x14001148a  call    cs:__imp_OpenSCManagerW
0x140011490  mov     rbx, rax
0x140011493  test    rax, rax
0x140011496  jnz     short loc_1400114B0
0x140011498  mov     rcx, [rsp+28h]; this
0x14001149d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1400114a4  mov     edx, 1E8h; void *
0x1400114a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400114ae  jmp     short loc_1400114F2
0x1400114b0  mov     r8d, esi; dwDesiredAccess
0x1400114b3  lea     rdx, ServiceName; "w32time"
0x1400114ba  mov     rcx, rbx; hSCManager
0x1400114bd  call    cs:__imp_OpenServiceW
0x1400114c3  test    rax, rax
0x1400114c6  jnz     short loc_1400114E2
0x1400114c8  mov     rcx, [rsp+28h]; this
0x1400114cd  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1400114d4  mov     edx, 1EBh; void *
0x1400114d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400114de  mov     edi, eax
0x1400114e0  jmp     short loc_1400114E7
0x1400114e2  mov     [rdi], rax
0x1400114e5  xor     edi, edi
0x1400114e7  mov     rcx, rbx; hSCObject
0x1400114ea  call    cs:__imp_CloseServiceHandle
0x1400114f0  mov     eax, edi
0x1400114f2  mov     rbx, [rsp+28h+arg_0]
0x1400114f7  mov     rsi, [rsp+28h+arg_8]
0x1400114fc  add     rsp, 20h
0x140011500  pop     rdi
0x140011501  retn
```
