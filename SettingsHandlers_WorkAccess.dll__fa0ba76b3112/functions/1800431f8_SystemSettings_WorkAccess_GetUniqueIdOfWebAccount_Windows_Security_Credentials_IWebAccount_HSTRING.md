# SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ * *)

- ea: `0x1800431f8`
- end: `0x1800433e0`
- name: `?GetUniqueIdOfWebAccount@WorkAccess@SystemSettings@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `488`
- prototype: `int(SystemSettings::WorkAccess *__hidden this, struct Windows::Security::Credentials::IWebAccount *, HSTRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bb3c`
- `0x18001fc24`
- `0x180044460`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x180042b8c`
- `0x1800431f8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800432b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800432b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800433b4`

## string_xrefs

- `0x18004324a`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x18004329c`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x1800432f3`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x18004334b`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(
        __int64 (__fastcall ***this)(SystemSettings::WorkAccess *, GUID *, __int64 *),
        struct Windows::Security::Credentials::IWebAccount *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v5)(SystemSettings::WorkAccess *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  __int64 (__fastcall *v11)(SystemSettings::WorkAccess *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  HSTRING *v16; // r9
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+30h]
  HSTRING string; // [rsp+60h] [rbp+38h] BYREF
  HSTRING string2; // [rsp+68h] [rbp+40h] BYREF
  __int64 v23; // [rsp+70h] [rbp+48h] BYREF
  __int64 v24; // [rsp+78h] [rbp+50h] BYREF

  *(_QWORD *)a2 = 0;
  v24 = 0;
  v5 = **this;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v6 = v5((SystemSettings::WorkAccess *)this, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v24);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = v24;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v23 = 0;
      v11 = (__int64 (__fastcall *)(SystemSettings::WorkAccess *, __int64 *))(*this)[6];
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      v12 = v11((SystemSettings::WorkAccess *)this, &v23);
      v7 = v12;
      if ( v12 >= 0 )
      {
        string2 = 0;
        v13 = v23;
        v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 48LL);
        WindowsDeleteString(0);
        string2 = 0;
        v15 = v14(v13, &string2);
        v7 = v15;
        if ( v15 >= 0 )
        {
          v15 = SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(string, string2, (HSTRING)a2, v16);
          v7 = v15;
          if ( v15 >= 0 )
          {
            WindowsDeleteString(string2);
            string2 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
            WindowsDeleteString(string);
            v7 = 0;
            goto LABEL_15;
          }
          v17 = 47;
        }
        else
        {
          v17 = 45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
          (const char *)(unsigned int)v15,
          v19);
        WindowsDeleteString(string2);
        string2 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
          (const char *)(unsigned int)v12,
          v19);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
        (const char *)(unsigned int)v10,
        v19);
    }
    WindowsDeleteString(string);
LABEL_15:
    string = 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
    (const char *)(unsigned int)v6,
    v19);
LABEL_16:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  return v7;
}

```

## disassembly

```asm
0x1800431f8  push    rbp
0x1800431fa  push    rbx
0x1800431fb  push    rsi
0x1800431fc  push    rdi
0x1800431fd  push    r14
0x1800431ff  push    r15
0x180043201  mov     rbp, rsp
0x180043204  sub     rsp, 28h
0x180043208  mov     r14, rdx
0x18004320b  mov     rsi, rcx
0x18004320e  xor     r15d, r15d
0x180043211  mov     [rdx], r15
0x180043214  mov     [rbp+arg_18], r15
0x180043218  mov     rax, [rcx]
0x18004321b  mov     rbx, [rax]
0x18004321e  lea     rcx, [rbp+arg_18]
0x180043222  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043227  lea     r8, [rbp+arg_18]
0x18004322b  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x180043232  mov     rcx, rsi
0x180043235  mov     rax, rbx
0x180043238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004323d  mov     ebx, eax
0x18004323f  test    eax, eax
0x180043241  jns     short loc_18004325F
0x180043243  mov     rcx, [rbp+30h]; this
0x180043247  mov     r9d, eax; char *
0x18004324a  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180043251  lea     edx, [r15+24h]; void *
0x180043255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004325a  jmp     loc_1800433C7
0x18004325f  mov     [rbp+string], r15
0x180043263  mov     rdi, [rbp+arg_18]
0x180043267  mov     rax, [rdi]
0x18004326a  mov     rbx, [rax+30h]
0x18004326e  xor     ecx, ecx; string
0x180043270  call    cs:__imp_WindowsDeleteString
0x180043277  nop     dword ptr [rax+rax+00h]
0x18004327c  mov     [rbp+string], r15
0x180043280  lea     rdx, [rbp+string]
0x180043284  mov     rcx, rdi
0x180043287  mov     rax, rbx
0x18004328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004328f  mov     ebx, eax
0x180043291  test    eax, eax
0x180043293  jns     short loc_1800432C3
0x180043295  mov     rcx, [rbp+30h]; this
0x180043299  mov     r9d, eax; char *
0x18004329c  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x1800432a3  mov     edx, 27h ; '''; void *
0x1800432a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800432ad  nop
0x1800432ae  mov     rcx, [rbp+string]; string
0x1800432b2  call    cs:__imp_WindowsDeleteString
0x1800432b9  nop     dword ptr [rax+rax+00h]
0x1800432be  jmp     loc_1800433C3
0x1800432c3  mov     [rbp+arg_10], r15
0x1800432c7  mov     rax, [rsi]
0x1800432ca  mov     rbx, [rax+30h]
0x1800432ce  lea     rcx, [rbp+arg_10]
0x1800432d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800432d7  lea     rdx, [rbp+arg_10]
0x1800432db  mov     rcx, rsi
0x1800432de  mov     rax, rbx
0x1800432e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432e6  mov     ebx, eax
0x1800432e8  test    eax, eax
0x1800432ea  jns     short loc_180043310
0x1800432ec  mov     rcx, [rbp+30h]; this
0x1800432f0  mov     r9d, eax; char *
0x1800432f3  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x1800432fa  mov     edx, 2Ah ; '*'; void *
0x1800432ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043304  nop
0x180043305  lea     rcx, [rbp+arg_10]
0x180043309  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004330e  jmp     short loc_1800432AE
0x180043310  mov     [rbp+string2], r15
0x180043314  mov     rdi, [rbp+arg_10]
0x180043318  mov     rax, [rdi]
0x18004331b  mov     rbx, [rax+30h]
0x18004331f  xor     ecx, ecx; string
0x180043321  call    cs:__imp_WindowsDeleteString
0x180043328  nop     dword ptr [rax+rax+00h]
0x18004332d  mov     [rbp+string2], r15
0x180043331  lea     rdx, [rbp+string2]
0x180043335  mov     rcx, rdi
0x180043338  mov     rax, rbx
0x18004333b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043340  mov     ebx, eax
0x180043342  test    eax, eax
0x180043344  jns     short loc_180043375
0x180043346  mov     edx, 2Dh ; '-'; void *
0x18004334b  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180043352  mov     r9d, eax; char *
0x180043355  mov     rcx, [rbp+30h]; this
0x180043359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004335e  nop
0x18004335f  mov     rcx, [rbp+string2]; string
0x180043363  call    cs:__imp_WindowsDeleteString
0x18004336a  nop     dword ptr [rax+rax+00h]
0x18004336f  mov     [rbp+string2], r15
0x180043373  jmp     short loc_180043305
0x180043375  mov     r8, r14; newString
0x180043378  mov     rdx, [rbp+string2]; string2
0x18004337c  mov     rcx, [rbp+string]; string1
0x180043380  call    ?BuildUniqueIdFromAccountAndProviderId@WorkAccess@SystemSettings@@YAJPEAUHSTRING__@@0PEAPEAU3@@Z; SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x180043385  mov     ebx, eax
0x180043387  test    eax, eax
0x180043389  jns     short loc_180043392
0x18004338b  mov     edx, 2Fh ; '/'
0x180043390  jmp     short loc_18004334B
0x180043392  mov     rcx, [rbp+string2]; string
0x180043396  call    cs:__imp_WindowsDeleteString
0x18004339d  nop     dword ptr [rax+rax+00h]
0x1800433a2  mov     [rbp+string2], r15
0x1800433a6  lea     rcx, [rbp+arg_10]
0x1800433aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800433af  nop
0x1800433b0  mov     rcx, [rbp+string]; string
0x1800433b4  call    cs:__imp_WindowsDeleteString
0x1800433bb  nop     dword ptr [rax+rax+00h]
0x1800433c0  mov     ebx, r15d
0x1800433c3  mov     [rbp+string], r15
0x1800433c7  lea     rcx, [rbp+arg_18]
0x1800433cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800433d0  mov     eax, ebx
0x1800433d2  add     rsp, 28h
0x1800433d6  pop     r15
0x1800433d8  pop     r14
0x1800433da  pop     rdi
0x1800433db  pop     rsi
0x1800433dc  pop     rbx
0x1800433dd  pop     rbp
0x1800433de  retn
```
