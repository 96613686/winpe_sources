# winrt::Windows::UI::Shell::implementation::FocusSessionManager::GetSession(winrt::hstring const &)

- ea: `0x180027e6c`
- end: `0x180027f35`
- name: `?GetSession@FocusSessionManager@implementation@Shell@UI@Windows@winrt@@QEAA?AUFocusSession@3456@AEBUhstring@6@@Z`
- size: `201`
- prototype: `struct winrt::Windows::UI::Shell::FocusSession __high(const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180027e10`

## callees

- `0x180003980`
- `0x18000cf94`
- `0x180024c10`
- `0x180026f64`
- `0x180027e6c`
- `0x1800286dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180027eb7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180027eb7`

## string_xrefs

- `0x180027ec9`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.shell.focussessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::UI::Shell::implementation::FocusSessionManager::GetSession(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const OLECHAR *v5; // rcx
  HRESULT v6; // eax
  __int64 strong; // rax
  int v9[4]; // [rsp+20h] [rbp-48h] BYREF
  GUID iid; // [rsp+30h] [rbp-38h] BYREF
  GUID v11; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)v9 = a2;
  iid = GUID_NULL;
  if ( *(_QWORD *)a3 )
    v5 = *(const OLECHAR **)(*(_QWORD *)a3 + 16LL);
  else
    v5 = &sz;
  v6 = IIDFromString(v5, &iid);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.shell.focussessionmanager.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
  v11 = iid;
  strong = winrt::implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_strong(
             a1,
             v9);
  winrt::make<winrt::Windows::UI::Shell::implementation::FocusSession,winrt::guid &,winrt::com_ptr<winrt::Windows::UI::Shell::implementation::FocusSessionManager>>(
    a2,
    &v11,
    strong);
  if ( *(_QWORD *)v9 )
    winrt::com_ptr<winrt::Windows::UI::Shell::implementation::FocusSessionManager>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x180027e6c  mov     [rsp+arg_18], rbx
0x180027e71  push    rdi
0x180027e72  sub     rsp, 60h
0x180027e76  mov     rax, cs:__security_cookie
0x180027e7d  xor     rax, rsp
0x180027e80  mov     [rsp+68h+var_18], rax
0x180027e85  mov     rbx, rdx
0x180027e88  mov     rdi, rcx
0x180027e8b  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180027e90  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180027e97  movdqu  xmmword ptr [rsp+68h+iid.Data1], xmm0
0x180027e9d  mov     rcx, [r8]
0x180027ea0  test    rcx, rcx
0x180027ea3  jz      short loc_180027EAB
0x180027ea5  mov     rcx, [rcx+10h]
0x180027ea9  jmp     short loc_180027EB2
0x180027eab  lea     rcx, sz; lpsz
0x180027eb2  lea     rdx, [rsp+68h+iid]; lpiid
0x180027eb7  call    cs:__imp_IIDFromString
0x180027ebd  mov     rcx, [rsp+68h]; this
0x180027ec2  test    eax, eax
0x180027ec4  jns     short loc_180027EDB
0x180027ec6  mov     r9d, eax; char *
0x180027ec9  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\accessibletech\\ex"...
0x180027ed0  mov     edx, 0BDh; void *
0x180027ed5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027edb  movaps  xmm0, xmmword ptr [rsp+68h+iid.Data1]
0x180027ee0  movdqa  [rsp+68h+var_28], xmm0
0x180027ee6  lea     rdx, [rsp+68h+var_48]
0x180027eeb  mov     rcx, rdi
0x180027eee  call    ?get_strong@?$implements@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@U13456@@winrt@@QEAA?AU?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_strong(void)
0x180027ef3  nop
0x180027ef4  mov     r8, rax
0x180027ef7  lea     rdx, [rsp+68h+var_28]
0x180027efc  mov     rcx, rbx
0x180027eff  call    ??$make@UFocusSession@implementation@Shell@UI@Windows@winrt@@AEAUguid@6@U?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@6@@winrt@@YA?A_PAEAUguid@0@$$QEAU?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@0@@Z
0x180027f04  nop
0x180027f05  cmp     qword ptr [rsp+68h+var_48], 0
0x180027f0b  jz      short loc_180027F17
0x180027f0d  lea     rcx, [rsp+68h+var_48]
0x180027f12  call    ?unconditional_release_ref@?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::UI::Shell::implementation::FocusSessionManager>::unconditional_release_ref(void)
0x180027f17  mov     rax, rbx
0x180027f1a  mov     rcx, [rsp+68h+var_18]
0x180027f1f  xor     rcx, rsp; StackCookie
0x180027f22  call    __security_check_cookie
0x180027f27  mov     rbx, [rsp+68h+arg_18]
0x180027f2f  add     rsp, 60h
0x180027f33  pop     rdi
0x180027f34  retn
```
