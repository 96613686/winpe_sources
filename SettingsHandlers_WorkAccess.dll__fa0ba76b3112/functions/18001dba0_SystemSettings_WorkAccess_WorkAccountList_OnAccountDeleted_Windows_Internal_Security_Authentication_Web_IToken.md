# SystemSettings::WorkAccess::WorkAccountList::OnAccountDeleted(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *)

- ea: `0x18001dba0`
- end: `0x18001dcc8`
- name: `?OnAccountDeleted@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z`
- size: `296`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *, struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x18001dba0`
- `0x18001ed78`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dbc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcac`

## string_xrefs

- `0x18001dbf6`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001dc4b`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::OnAccountDeleted(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *a2,
        struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  HSTRING v15; // [rsp+58h] [rbp+38h] BYREF

  v15 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
  WindowsDeleteString(0);
  v15 = 0;
  v6 = v5(a3, &v15);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(a3, &string);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = SystemSettings::WorkAccess::WorkAccountList::RemoveAccount(this, v15, string);
      v7 = v9;
      if ( v9 >= 0 )
      {
        WindowsDeleteString(string);
        v7 = 0;
        goto LABEL_9;
      }
      v10 = 346;
    }
    else
    {
      v10 = 345;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
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
    (void *)0x156,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
    (const char *)(unsigned int)v6,
    savedregs);
LABEL_10:
  WindowsDeleteString(v15);
  return v7;
}

```

## disassembly

```asm
0x18001dba0  mov     [rsp-18h+arg_0], rbx
0x18001dba5  push    rbp
0x18001dba6  push    rsi
0x18001dba7  push    rdi; int
0x18001dba8  mov     rbp, rsp
0x18001dbab  sub     rsp, 20h
0x18001dbaf  mov     rdi, r8
0x18001dbb2  mov     rsi, rcx
0x18001dbb5  mov     [rbp+arg_18], 0
0x18001dbbd  mov     rax, [r8]
0x18001dbc0  mov     rbx, [rax+30h]
0x18001dbc4  xor     ecx, ecx; string
0x18001dbc6  call    cs:__imp_WindowsDeleteString
0x18001dbcd  nop     dword ptr [rax+rax+00h]
0x18001dbd2  mov     [rbp+arg_18], 0
0x18001dbda  lea     rdx, [rbp+arg_18]
0x18001dbde  mov     rcx, rdi
0x18001dbe1  mov     rax, rbx
0x18001dbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe9  mov     ebx, eax
0x18001dbeb  test    eax, eax
0x18001dbed  jns     short loc_18001DC0C
0x18001dbef  mov     rcx, [rbp+18h]; this
0x18001dbf3  mov     r9d, eax; char *
0x18001dbf6  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001dbfd  mov     edx, 156h; void *
0x18001dc02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc07  jmp     loc_18001DCA8
0x18001dc0c  mov     [rbp+string], 0
0x18001dc14  mov     rax, [rdi]
0x18001dc17  mov     rbx, [rax+38h]
0x18001dc1b  xor     ecx, ecx; string
0x18001dc1d  call    cs:__imp_WindowsDeleteString
0x18001dc24  nop     dword ptr [rax+rax+00h]
0x18001dc29  mov     [rbp+string], 0
0x18001dc31  lea     rdx, [rbp+string]
0x18001dc35  mov     rcx, rdi
0x18001dc38  mov     rax, rbx
0x18001dc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc40  mov     ebx, eax
0x18001dc42  test    eax, eax
0x18001dc44  jns     short loc_18001DC71
0x18001dc46  mov     edx, 159h; void *
0x18001dc4b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001dc52  mov     r9d, eax; char *
0x18001dc55  mov     rcx, [rbp+18h]; this
0x18001dc59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc5e  nop
0x18001dc5f  mov     rcx, [rbp+string]; string
0x18001dc63  call    cs:__imp_WindowsDeleteString
0x18001dc6a  nop     dword ptr [rax+rax+00h]
0x18001dc6f  jmp     short loc_18001DCA0
0x18001dc71  mov     r8, [rbp+string]; HSTRING
0x18001dc75  mov     rdx, [rbp+arg_18]; HSTRING
0x18001dc79  mov     rcx, rsi; this
0x18001dc7c  call    ?RemoveAccount@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUHSTRING__@@0@Z; SystemSettings::WorkAccess::WorkAccountList::RemoveAccount(HSTRING__ *,HSTRING__ *)
0x18001dc81  mov     ebx, eax
0x18001dc83  test    eax, eax
0x18001dc85  jns     short loc_18001DC8E
0x18001dc87  mov     edx, 15Ah
0x18001dc8c  jmp     short loc_18001DC4B
0x18001dc8e  mov     rcx, [rbp+string]; string
0x18001dc92  call    cs:__imp_WindowsDeleteString
0x18001dc99  nop     dword ptr [rax+rax+00h]
0x18001dc9e  xor     ebx, ebx
0x18001dca0  mov     [rbp+string], 0
0x18001dca8  mov     rcx, [rbp+arg_18]; string
0x18001dcac  call    cs:__imp_WindowsDeleteString
0x18001dcb3  nop     dword ptr [rax+rax+00h]
0x18001dcb8  mov     eax, ebx
0x18001dcba  mov     rbx, [rsp+20h+arg_0]
0x18001dcbf  add     rsp, 20h
0x18001dcc3  pop     rdi
0x18001dcc4  pop     rsi
0x18001dcc5  pop     rbp
0x18001dcc6  retn
```
