# UserSigninChangeWatcher::Stop(void)

- ea: `0x180090890`
- end: `0x1800909f0`
- name: `?Stop@UserSigninChangeWatcher@@QEAAXXZ`
- size: `352`
- prototype: `void __fastcall(UserSigninChangeWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054428`
- `0x18008dd50`

## callees

- `0x180004738`
- `0x180013b50`
- `0x180061c04`
- `0x18008a17c`
- `0x180090890`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800908a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800908a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800909dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800909dd`

## string_xrefs

- `0x1800908cf`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180090925`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180090991`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800909c3`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800908b6`: `UserSigninChangeWatcher removed SignInComplete`
- `0x18009090c`: `UserSigninChangeWatcher removed SignOutComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserSigninChangeWatcher::Stop(UserSigninChangeWatcher *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // rdi
  const char *v4; // r9
  __int64 v5; // rcx
  int v6; // eax
  int v7; // edi
  int Format; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  try
  {
    if ( *((_QWORD *)this + 6) )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x2FFu,
        "UserSigninChangeWatcher::Stop",
        (wchar_t *)L"UserSigninChangeWatcher removed SignInComplete");
      v3 = (_QWORD *)((char *)this + 40);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 104LL))(
        *((_QWORD *)this + 5),
        *((_QWORD *)this + 6));
      *((_QWORD *)this + 6) = 0;
    }
    else
    {
      v3 = (_QWORD *)((char *)this + 40);
    }
    if ( *((_QWORD *)this + 7) )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x306u,
        "UserSigninChangeWatcher::Stop",
        (wchar_t *)L"UserSigninChangeWatcher removed SignOutComplete");
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 120LL))(*v3, *((_QWORD *)this + 7));
      *((_QWORD *)this + 7) = 0;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 64);
    v5 = *((_QWORD *)this + 9);
    if ( v5 )
    {
      if ( *((_QWORD *)this + 10) )
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 128LL))(v5);
        v7 = v6;
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v6,
            Format);
LABEL_14:
          if ( v7 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x30F,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              (const char *)(unsigned int)v7,
              Format);
          if ( v2 )
            LeaveCriticalSection(v2);
          return;
        }
        *((_QWORD *)this + 10) = 0;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 72);
    }
    v7 = 0;
    goto LABEL_14;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x180090890  push    rbx
0x180090892  push    rsi
0x180090893  push    rdi
0x180090894  push    r14
0x180090896  sub     rsp, 38h
0x18009089a  mov     rbx, rcx
0x18009089d  lea     rsi, [rcx+58h]
0x1800908a1  mov     rcx, rsi; lpCriticalSection
0x1800908a4  call    cs:__imp_EnterCriticalSection
0x1800908aa  mov     [rsp+58h+arg_0], rsi
0x1800908af  cmp     qword ptr [rbx+30h], 0
0x1800908b4  jz      short loc_180090901
0x1800908b6  lea     rax, aUsersigninchan_3; "UserSigninChangeWatcher removed SignInC"...
0x1800908bd  mov     qword ptr [rsp+58h+Format], rax; Format
0x1800908c2  lea     r9, aUsersigninchan_1; "UserSigninChangeWatcher::Stop"
0x1800908c9  mov     r8d, 2FFh; unsigned int
0x1800908cf  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800908d6  mov     ecx, 3; unsigned int
0x1800908db  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800908e0  lea     rdi, [rbx+28h]
0x1800908e4  mov     rcx, [rdi]
0x1800908e7  mov     rax, [rcx]
0x1800908ea  mov     rdx, [rbx+30h]
0x1800908ee  mov     rax, [rax+68h]
0x1800908f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800908f7  mov     qword ptr [rbx+30h], 0
0x1800908ff  jmp     short loc_180090905
0x180090901  lea     rdi, [rbx+28h]
0x180090905  cmp     qword ptr [rbx+38h], 0
0x18009090a  jz      short loc_180090951
0x18009090c  lea     rax, aUsersigninchan_9; "UserSigninChangeWatcher removed SignOut"...
0x180090913  mov     qword ptr [rsp+58h+Format], rax; int
0x180090918  lea     r9, aUsersigninchan_1; "UserSigninChangeWatcher::Stop"
0x18009091f  mov     r8d, 306h; unsigned int
0x180090925  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18009092c  mov     ecx, 3; unsigned int
0x180090931  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180090936  mov     rcx, [rdi]
0x180090939  mov     rax, [rcx]
0x18009093c  mov     rdx, [rbx+38h]
0x180090940  mov     rax, [rax+78h]
0x180090944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090949  mov     qword ptr [rbx+38h], 0
0x180090951  mov     rcx, rdi
0x180090954  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090959  lea     rcx, [rbx+40h]
0x18009095d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090962  mov     rcx, [rbx+48h]
0x180090966  test    rcx, rcx
0x180090969  jz      short loc_1800909B5
0x18009096b  mov     rdx, [rbx+50h]
0x18009096f  test    rdx, rdx
0x180090972  jz      short loc_1800909AC
0x180090974  mov     rax, [rcx]
0x180090977  mov     rax, [rax+80h]
0x18009097e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090983  mov     edi, eax
0x180090985  test    eax, eax
0x180090987  jns     short loc_1800909A4
0x180090989  mov     rcx, [rsp+58h]; this
0x18009098e  mov     r9d, eax; char *
0x180090991  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180090998  mov     edx, 46Fh; void *
0x18009099d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800909a2  jmp     short loc_1800909B7
0x1800909a4  mov     qword ptr [rbx+50h], 0
0x1800909ac  lea     rcx, [rbx+48h]
0x1800909b0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800909b5  xor     edi, edi
0x1800909b7  mov     rcx, [rsp+58h]; this
0x1800909bc  test    edi, edi
0x1800909be  jns     short loc_1800909D5
0x1800909c0  mov     r9d, edi; char *
0x1800909c3  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800909ca  mov     edx, 30Fh; void *
0x1800909cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800909d4  nop
0x1800909d5  test    rsi, rsi
0x1800909d8  jz      short loc_1800909E4
0x1800909da  mov     rcx, rsi; lpCriticalSection
0x1800909dd  call    cs:__imp_LeaveCriticalSection
0x1800909e3  nop
0x1800909e4  jmp     short $+2
0x1800909e6  add     rsp, 38h
0x1800909ea  pop     r14
0x1800909ec  pop     rdi
0x1800909ed  pop     rsi
0x1800909ee  pop     rbx
0x1800909ef  retn
```
