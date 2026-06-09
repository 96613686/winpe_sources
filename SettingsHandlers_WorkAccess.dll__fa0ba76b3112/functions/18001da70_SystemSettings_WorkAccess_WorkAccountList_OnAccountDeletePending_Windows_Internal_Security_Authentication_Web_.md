# SystemSettings::WorkAccess::WorkAccountList::OnAccountDeletePending(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)

- ea: `0x18001da70`
- end: `0x18001db98`
- name: `?OnAccountDeletePending@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@56789@@Z`
- size: `296`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *, struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x18001da70`
- `0x18001f454`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001daed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001da96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001daed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db7c`

## string_xrefs

- `0x18001dac6`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001db1b`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::OnAccountDeletePending(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *a2,
        struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *, HSTRING *); // rbx
  int v9; // eax
  char v10; // r9
  __int64 v11; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  HSTRING v16; // [rsp+58h] [rbp+38h] BYREF

  v16 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
  WindowsDeleteString(0);
  v16 = 0;
  v6 = v5(a3, &v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(a3, &string);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = SystemSettings::WorkAccess::WorkAccountList::SetAccountBusy(this, v16, string, v10);
      v7 = v9;
      if ( v9 >= 0 )
      {
        WindowsDeleteString(string);
        v7 = 0;
        goto LABEL_9;
      }
      v11 = 334;
    }
    else
    {
      v11 = 333;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    WindowsDeleteString(string);
LABEL_9:
    string = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14A,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
    (const char *)(unsigned int)v6,
    savedregs);
LABEL_10:
  WindowsDeleteString(v16);
  return v7;
}

```

## disassembly

```asm
0x18001da70  mov     [rsp-18h+arg_0], rbx
0x18001da75  push    rbp
0x18001da76  push    rsi
0x18001da77  push    rdi; int
0x18001da78  mov     rbp, rsp
0x18001da7b  sub     rsp, 20h
0x18001da7f  mov     rdi, r8
0x18001da82  mov     rsi, rcx
0x18001da85  mov     [rbp+arg_18], 0
0x18001da8d  mov     rax, [r8]
0x18001da90  mov     rbx, [rax+30h]
0x18001da94  xor     ecx, ecx; string
0x18001da96  call    cs:__imp_WindowsDeleteString
0x18001da9d  nop     dword ptr [rax+rax+00h]
0x18001daa2  mov     [rbp+arg_18], 0
0x18001daaa  lea     rdx, [rbp+arg_18]
0x18001daae  mov     rcx, rdi
0x18001dab1  mov     rax, rbx
0x18001dab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dab9  mov     ebx, eax
0x18001dabb  test    eax, eax
0x18001dabd  jns     short loc_18001DADC
0x18001dabf  mov     rcx, [rbp+18h]; this
0x18001dac3  mov     r9d, eax; char *
0x18001dac6  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001dacd  mov     edx, 14Ah; void *
0x18001dad2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dad7  jmp     loc_18001DB78
0x18001dadc  mov     [rbp+string], 0
0x18001dae4  mov     rax, [rdi]
0x18001dae7  mov     rbx, [rax+38h]
0x18001daeb  xor     ecx, ecx; string
0x18001daed  call    cs:__imp_WindowsDeleteString
0x18001daf4  nop     dword ptr [rax+rax+00h]
0x18001daf9  mov     [rbp+string], 0
0x18001db01  lea     rdx, [rbp+string]
0x18001db05  mov     rcx, rdi
0x18001db08  mov     rax, rbx
0x18001db0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db10  mov     ebx, eax
0x18001db12  test    eax, eax
0x18001db14  jns     short loc_18001DB41
0x18001db16  mov     edx, 14Dh; void *
0x18001db1b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001db22  mov     r9d, eax; char *
0x18001db25  mov     rcx, [rbp+18h]; this
0x18001db29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db2e  nop
0x18001db2f  mov     rcx, [rbp+string]; string
0x18001db33  call    cs:__imp_WindowsDeleteString
0x18001db3a  nop     dword ptr [rax+rax+00h]
0x18001db3f  jmp     short loc_18001DB70
0x18001db41  mov     r8, [rbp+string]; HSTRING
0x18001db45  mov     rdx, [rbp+arg_18]; HSTRING
0x18001db49  mov     rcx, rsi; this
0x18001db4c  call    ?SetAccountBusy@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUHSTRING__@@0_N@Z; SystemSettings::WorkAccess::WorkAccountList::SetAccountBusy(HSTRING__ *,HSTRING__ *,bool)
0x18001db51  mov     ebx, eax
0x18001db53  test    eax, eax
0x18001db55  jns     short loc_18001DB5E
0x18001db57  mov     edx, 14Eh
0x18001db5c  jmp     short loc_18001DB1B
0x18001db5e  mov     rcx, [rbp+string]; string
0x18001db62  call    cs:__imp_WindowsDeleteString
0x18001db69  nop     dword ptr [rax+rax+00h]
0x18001db6e  xor     ebx, ebx
0x18001db70  mov     [rbp+string], 0
0x18001db78  mov     rcx, [rbp+arg_18]; string
0x18001db7c  call    cs:__imp_WindowsDeleteString
0x18001db83  nop     dword ptr [rax+rax+00h]
0x18001db88  mov     eax, ebx
0x18001db8a  mov     rbx, [rsp+20h+arg_0]
0x18001db8f  add     rsp, 20h
0x18001db93  pop     rdi
0x18001db94  pop     rsi
0x18001db95  pop     rbp
0x18001db96  retn
```
