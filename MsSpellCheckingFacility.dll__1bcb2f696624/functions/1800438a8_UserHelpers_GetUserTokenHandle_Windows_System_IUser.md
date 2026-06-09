# UserHelpers::GetUserTokenHandle(Windows::System::IUser *)

- ea: `0x1800438a8`
- end: `0x180043a00`
- name: `?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180043568`
- `0x1800437d8`

## callees

- `0x1800438a8`
- `0x180044a24`
- `0x180044a88`
- `0x180044d14`
- `0x180064ce8`
- `0x180070530`
- `0x18009b4e8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800438ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800438ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439a9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180043924`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180043924`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall UserHelpers::GetUserTokenHandle(void **a1, UserHelpers *a2)
{
  struct Windows::System::IUser *v4; // rdx
  void *v5; // rdi
  unsigned __int64 UserContextToken; // rax
  int UserToken; // eax
  void *v8; // rdi
  signed int v9; // eax
  __int64 v10; // rdx
  void *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v14; // [rsp+50h] [rbp+18h] BYREF

  *a1 = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent() && a2 )
  {
    v5 = *a1;
    if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
      CloseHandle(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
    }
    *a1 = 0;
    UserContextToken = UserHelpers::GetUserContextToken(a2, v4);
    UserToken = UMgrQueryUserToken(UserContextToken, a1);
    if ( UserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
        (const char *)(unsigned int)UserToken,
        1);
  }
  else
  {
    v8 = *a1;
    if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
      CloseHandle(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
    }
    *a1 = 0;
    v9 = wil::open_current_access_token_nothrow(a1, (__int64)v4, 0);
    if ( v9 == -2147023888 )
    {
      v11 = *a1;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        CloseHandle(v11);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      *a1 = 0;
      v9 = wil::open_current_access_token_nothrow(a1, v10, 1);
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
        (const char *)(unsigned int)v9,
        1);
  }
  return a1;
}

```

## disassembly

```asm
0x1800438a8  mov     rax, rsp
0x1800438ab  mov     [rax+10h], rbx
0x1800438af  mov     [rax+20h], rsi
0x1800438b3  mov     [rax+8], rcx
0x1800438b7  push    rdi
0x1800438b8  sub     rsp, 30h
0x1800438bc  mov     rsi, rdx
0x1800438bf  mov     rbx, rcx
0x1800438c2  mov     dword ptr [rax-18h], 0
0x1800438c9  mov     qword ptr [rcx], 0
0x1800438d0  mov     dword ptr [rax-18h], 1
0x1800438d7  call    IsUMgrQueryUserContextPresent
0x1800438dc  test    al, al
0x1800438de  jz      short loc_18004394C
0x1800438e0  test    rsi, rsi
0x1800438e3  jz      short loc_18004394C
0x1800438e5  mov     rdi, [rbx]
0x1800438e8  lea     rax, [rdi-1]
0x1800438ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800438f0  ja      short loc_18004390F
0x1800438f2  lea     rcx, [rsp+38h+arg_10]; this
0x1800438f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800438fc  mov     rcx, rdi; hObject
0x1800438ff  call    cs:__imp_CloseHandle
0x180043905  lea     rcx, [rsp+38h+arg_10]; this
0x18004390a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004390f  mov     qword ptr [rbx], 0
0x180043916  mov     rcx, rsi; this
0x180043919  call    ?GetUserContextToken@UserHelpers@@YA_KPEAUIUser@System@Windows@@@Z; UserHelpers::GetUserContextToken(Windows::System::IUser *)
0x18004391e  mov     rdx, rbx
0x180043921  mov     rcx, rax
0x180043924  call    cs:__imp_UMgrQueryUserToken
0x18004392a  test    eax, eax
0x18004392c  jns     loc_1800439EC
0x180043932  mov     rcx, [rsp+38h]; this
0x180043937  mov     r9d, eax; char *
0x18004393a  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180043941  mov     edx, 60h ; '`'; void *
0x180043946  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004394c  mov     rdi, [rbx]
0x18004394f  lea     rax, [rdi-1]
0x180043953  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043957  ja      short loc_180043976
0x180043959  lea     rcx, [rsp+38h+arg_10]; this
0x18004395e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180043963  mov     rcx, rdi; hObject
0x180043966  call    cs:__imp_CloseHandle
0x18004396c  lea     rcx, [rsp+38h+arg_10]; this
0x180043971  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180043976  mov     qword ptr [rbx], 0
0x18004397d  xor     r8d, r8d
0x180043980  mov     rcx, rbx
0x180043983  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x180043988  cmp     eax, 800703F0h
0x18004398d  jnz     short loc_1800439CE
0x18004398f  mov     rdi, [rbx]
0x180043992  lea     rax, [rdi-1]
0x180043996  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004399a  ja      short loc_1800439B9
0x18004399c  lea     rcx, [rsp+38h+arg_10]; this
0x1800439a1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800439a6  mov     rcx, rdi; hObject
0x1800439a9  call    cs:__imp_CloseHandle
0x1800439af  lea     rcx, [rsp+38h+arg_10]; this
0x1800439b4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800439b9  mov     qword ptr [rbx], 0
0x1800439c0  mov     r8d, 1
0x1800439c6  mov     rcx, rbx
0x1800439c9  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1800439ce  test    eax, eax
0x1800439d0  jns     short loc_1800439EC
0x1800439d2  mov     rcx, [rsp+38h]; this
0x1800439d7  mov     r9d, eax; char *
0x1800439da  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800439e1  mov     edx, 5Bh ; '['; void *
0x1800439e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800439ec  mov     rax, rbx
0x1800439ef  mov     rbx, [rsp+38h+arg_8]
0x1800439f4  mov     rsi, [rsp+38h+arg_18]
0x1800439f9  add     rsp, 30h
0x1800439fd  pop     rdi
0x1800439fe  retn
```
