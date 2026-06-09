# WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::CreateTimeOverride(Sid const &,DateTime const &)

- ea: `0x180006ee0`
- end: `0x180006fca`
- name: `?CreateTimeOverride@RequestManagerDesktopDependencies@ManagerDLL@OTS@WpcDesktop@@EEBAXAEBVSid@@AEBVDateTime@@@Z`
- size: `234`
- prototype: `void __fastcall(WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies *__hidden this, const struct Sid *, const struct DateTime *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800032a0`
- `0x180005a04`
- `0x180005f9c`
- `0x180006ee0`
- `0x18000b2dc`
- `0x18001cad0`

## import_xrefs

- `Wpc!WpcTimeRestrictionsCreateLocalOverride` at `0x180006fa4`
- `Wpc!WpcTimeRestrictionsCreateLocalOverride` at `0x180006fa4`

## pseudocode

```c
void __fastcall WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::CreateTimeOverride(
        WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies *this,
        const struct Sid *a2,
        const struct DateTime *a3)
{
  char v5; // bl
  __int64 *v6; // rax
  __int64 v7; // rdi
  int v8; // edx
  int v9; // r8d
  _QWORD *v10; // r9
  _QWORD v11[4]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-40h] BYREF

  v5 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v6 = (__int64 *)DateTime::Serialize(a3, v12);
    v7 = (__int64)v6;
    v5 = 7;
    if ( (unsigned __int64)v6[3] > 7 )
      v7 = *v6;
    std::wstring::wstring(v11, (char *)a2 + 72);
    v10 = v11;
    if ( v11[3] > 7u )
      LODWORD(v10) = v11[0];
    WPP_SF_SS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v8, v9, (_DWORD)v10, v7);
  }
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    std::wstring::~wstring(v11);
  }
  if ( (v5 & 1) != 0 )
    std::wstring::~wstring(v12);
  WpcTimeRestrictionsCreateLocalOverride(a2, a3);
}

```

## disassembly

```asm
0x180006ee0  mov     [rsp+arg_0], rbx
0x180006ee5  push    rbp
0x180006ee6  push    rsi
0x180006ee7  push    rdi
0x180006ee8  sub     rsp, 80h
0x180006eef  mov     rax, cs:__security_cookie
0x180006ef6  xor     rax, rsp
0x180006ef9  mov     [rsp+98h+var_20], rax
0x180006efe  mov     rsi, r8
0x180006f01  mov     rbp, rdx
0x180006f04  xor     ebx, ebx
0x180006f06  mov     [rsp+98h+var_68], ebx
0x180006f0a  lea     rcx, WPP_GLOBAL_Control
0x180006f11  mov     rax, cs:WPP_GLOBAL_Control
0x180006f18  cmp     rax, rcx
0x180006f1b  jz      short loc_180006F7C
0x180006f1d  test    byte ptr [rax+1Ch], 4
0x180006f21  jz      short loc_180006F7C
0x180006f23  lea     rdx, [rsp+98h+var_40]
0x180006f28  mov     rcx, r8
0x180006f2b  call    ?Serialize@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DateTime::Serialize(void)
0x180006f30  mov     rdi, rax
0x180006f33  mov     [rsp+98h+var_68], 1
0x180006f3b  mov     ebx, 7
0x180006f40  cmp     [rax+18h], rbx
0x180006f44  jbe     short loc_180006F49
0x180006f46  mov     rdi, [rax]
0x180006f49  lea     rdx, [rbp+48h]
0x180006f4d  lea     rcx, [rsp+98h+var_60]
0x180006f52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180006f57  lea     r9, [rsp+98h+var_60]
0x180006f5c  cmp     [rsp+98h+var_48], rbx
0x180006f61  cmova   r9, [rsp+98h+var_60]
0x180006f67  mov     [rsp+98h+var_78], rdi
0x180006f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f73  mov     rcx, [rcx+10h]
0x180006f77  call    WPP_SF_SS
0x180006f7c  test    bl, 2
0x180006f7f  jz      short loc_180006F8F
0x180006f81  and     ebx, 0FFFFFFFDh
0x180006f84  lea     rcx, [rsp+98h+var_60]
0x180006f89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f8e  nop
0x180006f8f  test    bl, 1
0x180006f92  jz      short loc_180006F9E
0x180006f94  lea     rcx, [rsp+98h+var_40]
0x180006f99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f9e  mov     rdx, rsi
0x180006fa1  mov     rcx, rbp
0x180006fa4  call    cs:__imp_WpcTimeRestrictionsCreateLocalOverride
0x180006faa  mov     rcx, [rsp+98h+var_20]
0x180006faf  xor     rcx, rsp; StackCookie
0x180006fb2  call    __security_check_cookie
0x180006fb7  mov     rbx, [rsp+98h+arg_0]
0x180006fbf  add     rsp, 80h
0x180006fc6  pop     rdi
0x180006fc7  pop     rsi
0x180006fc8  pop     rbp
0x180006fc9  retn
```
