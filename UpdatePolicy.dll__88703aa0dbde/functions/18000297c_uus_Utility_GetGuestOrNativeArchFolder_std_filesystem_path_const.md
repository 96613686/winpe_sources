# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x18000297c`
- end: `0x180002a0d`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002db0`
- `0x180002f78`

## callees

- `0x180001fe4`
- `0x18000297c`
- `0x18000593c`
- `0x1800078ac`
- `0x18000ed40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::filesystem::path *__fastcall uus::Utility::GetGuestOrNativeArchFolder(
        std::filesystem::path *a1,
        struct std::filesystem::path *a2)
{
  __int64 v4; // r8
  __int128 v6; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+48h] [rbp-20h]

  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  v6 = 0;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v6, uus::Const::archX64, v4);
  std::filesystem::operator/(a1, a2, &v6);
  std::wstring::~wstring(&v6);
  return a1;
}

```

## disassembly

```asm
0x18000297c  mov     [rsp+arg_10], rbx
0x180002981  push    rdi
0x180002982  sub     rsp, 60h
0x180002986  mov     rax, cs:__security_cookie
0x18000298d  xor     rax, rsp
0x180002990  mov     [rsp+68h+var_18], rax
0x180002995  mov     rdi, rdx
0x180002998  mov     rbx, rcx
0x18000299b  mov     [rsp+68h+var_40], rcx
0x1800029a0  xor     ecx, ecx
0x1800029a2  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x1800029a9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800029ad  inc     r8
0x1800029b0  cmp     [rdx+r8*2], cx
0x1800029b5  jnz     short loc_1800029AD
0x1800029b7  xorps   xmm0, xmm0
0x1800029ba  movups  [rsp+68h+var_38], xmm0
0x1800029bf  mov     [rsp+68h+var_28], rcx
0x1800029c4  mov     [rsp+68h+var_20], rcx
0x1800029c9  lea     rcx, [rsp+68h+var_38]
0x1800029ce  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800029d3  nop
0x1800029d4  lea     r8, [rsp+68h+var_38]; void *
0x1800029d9  mov     rdx, rdi; struct std::filesystem::path *
0x1800029dc  mov     rcx, rbx; Src
0x1800029df  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800029e4  nop
0x1800029e5  lea     rcx, [rsp+68h+var_38]
0x1800029ea  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800029ef  mov     rax, rbx
0x1800029f2  mov     rcx, [rsp+68h+var_18]
0x1800029f7  xor     rcx, rsp; StackCookie
0x1800029fa  call    __security_check_cookie
0x1800029ff  mov     rbx, [rsp+68h+arg_10]
0x180002a07  add     rsp, 60h
0x180002a0b  pop     rdi
0x180002a0c  retn
```
