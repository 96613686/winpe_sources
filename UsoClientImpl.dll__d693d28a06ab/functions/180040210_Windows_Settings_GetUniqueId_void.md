# Windows::Settings::GetUniqueId(void)

- ea: `0x180040210`
- end: `0x1800403ec`
- name: `?GetUniqueId@Settings@Windows@@UEAA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@XZ`
- size: `476`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ef00`

## callees

- `0x180009380`
- `0x180033b00`
- `0x180033f14`
- `0x180034304`
- `0x180036b10`
- `0x180036d78`
- `0x180036ed8`
- `0x180040210`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040384`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040384`

## string_xrefs

- `0x1800403bf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Settings::GetUniqueId(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  void (__fastcall *v5)(__int64, _BYTE *, _QWORD *, _QWORD *, _QWORD *); // rsi
  __int16 *traits_2_unsigned_short; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD v14[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v16[3]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v17[32]; // [rsp+78h] [rbp-1h] BYREF
  char v18; // [rsp+98h] [rbp+1Fh]
  char v19; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a1 + 8;
  if ( (unsigned int)mtx_do_lock(a1 + 8) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD *, _QWORD *, _QWORD *))(**(_QWORD **)(a1 + 88) + 56LL);
  traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"WOSCUniqueId",
                                         word_18008C8FA,
                                         0);
  if ( traits_2_unsigned_short == word_18008C8FA
    || (v9 = ((char *)traits_2_unsigned_short - (char *)L"WOSCUniqueId") >> 1, v9 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  }
  v14[0] = L"WOSCUniqueId";
  v14[1] = v9;
  v10 = -1;
  do
    ++v10;
  while ( Windows::Settings::c_settingsRegistryRoot[v10] );
  v15[0] = Windows::Settings::c_settingsRegistryRoot;
  v15[1] = v10;
  v16[0] = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v11 = -1;
  do
    ++v11;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v11] );
  v16[1] = v11;
  v5(v8, v17, v16, v15, v14);
  if ( v19 )
  {
    if ( v18 != 2 )
      std::_Throw_bad_variant_access();
    std::wstring::wstring(a2, v17);
    *(_BYTE *)(a2 + 32) = 1;
    if ( v19 && v18 != -1 && v18 && v18 != 1 )
      std::wstring::~wstring(v17);
  }
  else
  {
    *(_BYTE *)(a2 + 32) = 0;
  }
  if ( (*(_DWORD *)(v4 + 76))-- == 1 )
  {
    *(_DWORD *)(v4 + 72) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 16));
  }
  return a2;
}

```

## disassembly

```asm
0x180040210  mov     [rsp-8+arg_10], rbx
0x180040215  mov     [rsp-8+arg_18], rsi
0x18004021a  push    rbp
0x18004021b  push    rdi
0x18004021c  push    r12
0x18004021e  push    r14
0x180040220  push    r15
0x180040222  lea     rbp, [rsp-37h]
0x180040227  sub     rsp, 0B0h
0x18004022e  mov     rax, cs:__security_cookie
0x180040235  xor     rax, rsp
0x180040238  mov     [rbp+57h+var_28], rax
0x18004023c  mov     rdi, rdx
0x18004023f  mov     rsi, rcx
0x180040242  mov     [rbp+57h+var_A0], rdx
0x180040246  xor     r15d, r15d
0x180040249  lea     rbx, [rcx+8]
0x18004024d  mov     [rbp+57h+var_A0], rbx
0x180040251  mov     rcx, rbx
0x180040254  call    mtx_do_lock
0x180040259  test    eax, eax
0x18004025b  jnz     loc_1800403D1
0x180040261  mov     eax, [rbx+4Ch]
0x180040264  cmp     eax, 7FFFFFFFh
0x180040269  jz      loc_1800403DC
0x18004026f  mov     r11, [rsi+58h]
0x180040273  mov     rax, [r11]
0x180040276  mov     rsi, [rax+38h]
0x18004027a  xor     r8d, r8d
0x18004027d  lea     r14, word_18008C8FA
0x180040284  mov     rdx, r14
0x180040287  lea     r12, aWoscuniqueid; "WOSCUniqueId"
0x18004028e  mov     rcx, r12
0x180040291  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180040296  cmp     rax, r14
0x180040299  jz      loc_1800403BB
0x18004029f  sub     rax, r12
0x1800402a2  sar     rax, 1
0x1800402a5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800402a9  cmp     rax, r14
0x1800402ac  jz      loc_1800403BB
0x1800402b2  mov     qword ptr [rbp+57h+var_90], r12
0x1800402b6  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800402ba  mov     rcx, cs:?c_settingsRegistryRoot@Settings@Windows@@0QEB_WEB; wchar_t const * const Windows::Settings::c_settingsRegistryRoot
0x1800402c1  mov     rax, r14
0x1800402c4  inc     rax
0x1800402c7  cmp     [rcx+rax*2], r15w
0x1800402cc  jnz     short loc_1800402C4
0x1800402ce  mov     qword ptr [rbp+57h+var_80], rcx
0x1800402d2  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800402d6  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x1800402dd  mov     [rbp+57h+var_70], rcx
0x1800402e1  mov     rax, r14
0x1800402e4  inc     rax
0x1800402e7  cmp     [rcx+rax*2], r15w
0x1800402ec  jnz     short loc_1800402E4
0x1800402ee  mov     [rbp+57h+var_70+8], rax
0x1800402f2  movups  xmm0, [rbp+57h+var_90]
0x1800402f6  movdqu  [rbp+57h+var_90], xmm0
0x1800402fb  movups  xmm1, [rbp+57h+var_80]
0x1800402ff  movdqu  [rbp+57h+var_80], xmm1
0x180040304  movaps  xmm0, xmmword ptr [rbp+57h+var_70]
0x180040308  movdqa  xmmword ptr [rbp+57h+var_70], xmm0
0x18004030d  lea     rax, [rbp+57h+var_90]
0x180040311  mov     [rsp+0D0h+var_B0], rax
0x180040316  lea     r9, [rbp+57h+var_80]
0x18004031a  lea     r8, [rbp+57h+var_70]
0x18004031e  lea     rdx, [rbp+57h+var_58]
0x180040322  mov     rcx, r11
0x180040325  mov     rax, rsi
0x180040328  call    _guard_dispatch_icall
0x18004032d  nop
0x18004032e  cmp     [rbp+57h+var_30], r15b
0x180040332  jz      short loc_180040372
0x180040334  cmp     [rbp+57h+var_38], 2
0x180040338  jnz     short loc_1800403B5
0x18004033a  lea     rdx, [rbp+57h+var_58]
0x18004033e  mov     rcx, rdi
0x180040341  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040346  mov     byte ptr [rdi+20h], 1
0x18004034a  cmp     [rbp+57h+var_30], r15b
0x18004034e  jz      short loc_180040376
0x180040350  movsx   rax, [rbp+57h+var_38]
0x180040355  add     rax, 1
0x180040359  jz      short loc_180040376
0x18004035b  sub     rax, 1
0x18004035f  jz      short loc_180040376
0x180040361  cmp     rax, 1
0x180040365  jz      short loc_180040376
0x180040367  lea     rcx, [rbp+57h+var_58]; void *
0x18004036b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040370  jmp     short loc_180040376
0x180040372  mov     [rdi+20h], r15b
0x180040376  add     [rbx+4Ch], r14d
0x18004037a  jnz     short loc_18004038A
0x18004037c  mov     [rbx+48h], r14d
0x180040380  lea     rcx, [rbx+10h]; SRWLock
0x180040384  call    cs:__imp_ReleaseSRWLockExclusive
0x18004038a  mov     rax, rdi
0x18004038d  mov     rcx, [rbp+57h+var_28]
0x180040391  xor     rcx, rsp; StackCookie
0x180040394  call    __security_check_cookie
0x180040399  lea     r11, [rsp+0D0h+var_20]
0x1800403a1  mov     rbx, [r11+40h]
0x1800403a5  mov     rsi, [r11+48h]
0x1800403a9  mov     rsp, r11
0x1800403ac  pop     r15
0x1800403ae  pop     r14
0x1800403b0  pop     r12
0x1800403b2  pop     rdi
0x1800403b3  pop     rbp
0x1800403b4  retn
0x1800403b5  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x1800403bb  mov     rcx, [rbp+5Fh]; this
0x1800403bf  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800403c6  mov     edx, 0C9h; void *
0x1800403cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800403d1  mov     ecx, 5; int
0x1800403d6  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800403dc  dec     eax
0x1800403de  mov     [rbx+4Ch], eax
0x1800403e1  mov     ecx, 6; int
0x1800403e6  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
