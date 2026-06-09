# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::CompareAADAccounts(Windows::Security::Credentials::IWebAccount *,Windows::Security::Credentials::IWebAccount *,uchar *)

- ea: `0x18000e4f0`
- end: `0x18000e5ea`
- name: `?CompareAADAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccount@Credentials@Security@5@0PEAE@Z`
- size: `250`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccount *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc40`

## callees

- `0x180006eac`
- `0x18000e4f0`
- `0x18000e5f0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e5cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e5cf`

## string_xrefs

- `0x18000e58d`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::CompareAADAccounts(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        struct Windows::Security::Credentials::IWebAccount *a3,
        bool *a4)
{
  __int64 (__fastcall *v7)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *); // rbx
  HSTRING v12; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING v16; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF

  *a4 = 0;
  string = 0;
  v16 = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  v16 = 0;
  v8 = v7(a2, &v16);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v8 = v11(a3, &string);
    v9 = v8;
    if ( v8 >= 0 )
    {
      *a4 = (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)string,
                            v16,
                            v12) == 0;
      v9 = 0;
      goto LABEL_7;
    }
    v10 = 1240;
  }
  else
  {
    v10 = 1239;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)v8,
    savedregs);
LABEL_7:
  WindowsDeleteString(v16);
  v16 = 0;
  WindowsDeleteString(string);
  return v9;
}

```

## disassembly

```asm
0x18000e4f0  mov     [rsp-18h+arg_10], rbx
0x18000e4f5  mov     [rsp-18h+arg_18], rsi
0x18000e4fa  mov     [rsp-18h+arg_0], rcx
0x18000e4ff  push    rbp
0x18000e500  push    rdi
0x18000e501  push    r14; int
0x18000e503  mov     rbp, rsp
0x18000e506  sub     rsp, 20h
0x18000e50a  mov     r14, r9
0x18000e50d  mov     rsi, r8
0x18000e510  mov     rdi, rdx
0x18000e513  mov     byte ptr [r9], 0
0x18000e517  mov     [rbp+string], 0
0x18000e51f  mov     [rbp+arg_0], 0
0x18000e527  mov     rax, [rdx]
0x18000e52a  mov     rbx, [rax+38h]
0x18000e52e  xor     ecx, ecx; string
0x18000e530  call    cs:__imp_WindowsDeleteString
0x18000e536  mov     [rbp+arg_0], 0
0x18000e53e  lea     rdx, [rbp+arg_0]
0x18000e542  mov     rcx, rdi
0x18000e545  mov     rax, rbx
0x18000e548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54d  mov     ebx, eax
0x18000e54f  test    eax, eax
0x18000e551  jns     short loc_18000E55A
0x18000e553  mov     edx, 4D7h
0x18000e558  jmp     short loc_18000E58D
0x18000e55a  mov     rax, [rsi]
0x18000e55d  mov     rbx, [rax+38h]
0x18000e561  mov     rcx, [rbp+string]; string
0x18000e565  call    cs:__imp_WindowsDeleteString
0x18000e56b  mov     [rbp+string], 0
0x18000e573  lea     rdx, [rbp+string]
0x18000e577  mov     rcx, rsi
0x18000e57a  mov     rax, rbx
0x18000e57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e582  mov     ebx, eax
0x18000e584  test    eax, eax
0x18000e586  jns     short loc_18000E5A2
0x18000e588  mov     edx, 4D8h; void *
0x18000e58d  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000e594  mov     r9d, eax; char *
0x18000e597  mov     rcx, [rbp+18h]; this
0x18000e59b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5a0  jmp     short loc_18000E5B9
0x18000e5a2  mov     rdx, [rbp+arg_0]; HSTRING
0x18000e5a6  mov     rcx, [rbp+string]; this
0x18000e5aa  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18000e5af  test    eax, eax
0x18000e5b1  setz    al
0x18000e5b4  mov     [r14], al
0x18000e5b7  xor     ebx, ebx
0x18000e5b9  mov     rcx, [rbp+arg_0]; string
0x18000e5bd  call    cs:__imp_WindowsDeleteString
0x18000e5c3  mov     [rbp+arg_0], 0
0x18000e5cb  mov     rcx, [rbp+string]; string
0x18000e5cf  call    cs:__imp_WindowsDeleteString
0x18000e5d5  mov     eax, ebx
0x18000e5d7  mov     rbx, [rsp+20h+arg_10]
0x18000e5dc  mov     rsi, [rsp+20h+arg_18]
0x18000e5e1  add     rsp, 20h
0x18000e5e5  pop     r14
0x18000e5e7  pop     rdi
0x18000e5e8  pop     rbp
0x18000e5e9  retn
```
