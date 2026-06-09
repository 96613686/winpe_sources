# Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(ushort const *)

- ea: `0x180050980`
- end: `0x180050ae0`
- name: `?IsUserAdmin@UserInfoHelper@AssignedAccess@Internal@Windows@@SA_NPEBG@Z`
- size: `352`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023300`
- `0x18007f8d0`
- `0x18007fbb0`
- `0x1800801d0`
- `0x180080320`

## callees

- `0x180006640`
- `0x180010c98`
- `0x18002001c`
- `0x180020050`
- `0x18002b244`
- `0x18004ff34`
- `0x18005008c`
- `0x1800501d8`
- `0x180050658`
- `0x180050980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800509ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800509ef`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180050a4d`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180050a4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(const unsigned __int16 *a1)
{
  int v2; // eax
  PSID v3; // rbx
  HANDLE CurrentProcess; // rax
  int UserSidFromProcess; // eax
  const WCHAR *v6; // rax
  int v7; // eax
  bool v8; // bl
  int lpString2; // [rsp+20h] [rbp-29h]
  bool v11; // [rsp+50h] [rbp+7h] BYREF
  PSID SidToCheck[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v13; // [rsp+68h] [rbp+1Fh]
  _OWORD v14[2]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v11 = 0;
  *(_OWORD *)SidToCheck = 0;
  v13 = 0;
  v2 = Windows::Internal::AssignedAccess::UserInfoHelper::FillInWellKnownSid(a1, SidToCheck);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
      (const char *)(unsigned int)v2,
      lpString2);
  v3 = SidToCheck[0];
  v14[0] = 0;
  v14[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v14[0]) = 0;
  CurrentProcess = GetCurrentProcess();
  UserSidFromProcess = Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromProcess(CurrentProcess, v14);
  if ( UserSidFromProcess < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
      (const char *)(unsigned int)UserSidFromProcess,
      lpString2);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  if ( CompareStringEx(&LocaleName, 1u, v6, -1, a1, -1, 0, 0, 0) == 2 )
    v7 = Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForCurrentProcess(v3, &v11);
  else
    v7 = Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForLogonUser(a1, v3, &v11);
  v8 = v7 >= 0 && v11;
  std::wstring::_Tidy_deallocate(v14);
  std::vector<unsigned char>::_Tidy(SidToCheck);
  return v8;
}

```

## disassembly

```asm
0x180050980  mov     [rsp-8+arg_8], rbx
0x180050985  mov     [rsp-8+arg_10], rdi
0x18005098a  push    rbp
0x18005098b  lea     rbp, [rsp-57h]
0x180050990  sub     rsp, 0A0h
0x180050997  mov     rax, cs:__security_cookie
0x18005099e  xor     rax, rsp
0x1800509a1  mov     [rbp+57h+var_10], rax
0x1800509a5  mov     rdi, rcx
0x1800509a8  mov     [rbp+57h+var_50], 0
0x1800509ac  xorps   xmm0, xmm0
0x1800509af  movdqu  xmmword ptr [rbp+57h+SidToCheck], xmm0
0x1800509b4  mov     [rbp+57h+var_38], 0
0x1800509bc  lea     rdx, [rbp+57h+SidToCheck]
0x1800509c0  call    ?FillInWellKnownSid@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJW4WELL_KNOWN_SID_TYPE@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::FillInWellKnownSid(WELL_KNOWN_SID_TYPE,std::vector<uchar> &)
0x1800509c5  mov     rcx, [rbp+5Fh]; this
0x1800509c9  test    eax, eax
0x1800509cb  js      loc_180050ACB
0x1800509d1  mov     rbx, [rbp+57h+SidToCheck]
0x1800509d5  xorps   xmm0, xmm0
0x1800509d8  movups  [rbp+57h+var_30], xmm0
0x1800509dc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800509e4  movdqu  [rbp+57h+var_20], xmm1
0x1800509e9  xor     eax, eax
0x1800509eb  mov     word ptr [rbp+57h+var_30], ax
0x1800509ef  call    cs:__imp_GetCurrentProcess
0x1800509f5  mov     rcx, rax
0x1800509f8  lea     rdx, [rbp+57h+var_30]
0x1800509fc  call    ?GetUserSidFromProcess@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromProcess(void *,std::wstring &)
0x180050a01  mov     rcx, [rbp+5Fh]; this
0x180050a05  test    eax, eax
0x180050a07  js      loc_180050AB6
0x180050a0d  lea     rcx, [rbp+57h+var_30]
0x180050a11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050a16  mov     r8, rax; lpString1
0x180050a19  mov     [rsp+0A0h+lParam], 0; lParam
0x180050a22  mov     [rsp+0A0h+lpReserved], 0; lpReserved
0x180050a2b  mov     [rsp+0A0h+lpVersionInformation], 0; lpVersionInformation
0x180050a34  or      r9d, 0FFFFFFFFh; cchCount1
0x180050a38  mov     [rsp+0A0h+cchCount2], r9d; cchCount2
0x180050a3d  mov     [rsp+0A0h+lpString2], rdi; lpString2
0x180050a42  lea     edx, [r9+2]; dwCmpFlags
0x180050a46  lea     rcx, LocaleName; lpLocaleName
0x180050a4d  call    cs:__imp_CompareStringEx
0x180050a53  cmp     eax, 2
0x180050a56  jnz     short loc_180050AA1
0x180050a58  lea     rdx, [rbp+57h+var_50]; bool *
0x180050a5c  mov     rcx, rbx; SidToCheck
0x180050a5f  call    ?CheckGroupMembershipForCurrentProcess@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJPEAXAEA_N@Z; Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForCurrentProcess(void *,bool &)
0x180050a64  test    eax, eax
0x180050a66  js      short loc_180050AB2
0x180050a68  mov     bl, [rbp+57h+var_50]
0x180050a6b  lea     rcx, [rbp+57h+var_30]
0x180050a6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050a74  nop
0x180050a75  lea     rcx, [rbp+57h+SidToCheck]
0x180050a79  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180050a7e  mov     al, bl
0x180050a80  mov     rcx, [rbp+57h+var_10]
0x180050a84  xor     rcx, rsp; StackCookie
0x180050a87  call    __security_check_cookie
0x180050a8c  lea     r11, [rsp+0A0h+var_s0]
0x180050a94  mov     rbx, [r11+18h]
0x180050a98  mov     rdi, [r11+20h]
0x180050a9c  mov     rsp, r11
0x180050a9f  pop     rbp
0x180050aa0  retn
0x180050aa1  lea     r8, [rbp+57h+var_50]; bool *
0x180050aa5  mov     rdx, rbx; void *
0x180050aa8  mov     rcx, rdi; unsigned __int16 *
0x180050aab  call    ?CheckGroupMembershipForLogonUser@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJPEBGPEAXAEA_N@Z; Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForLogonUser(ushort const *,void *,bool &)
0x180050ab0  jmp     short loc_180050A64
0x180050ab2  xor     bl, bl
0x180050ab4  jmp     short loc_180050A6B
0x180050ab6  mov     r9d, eax; char *
0x180050ab9  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050ac0  mov     edx, 102h; void *
0x180050ac5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050acb  mov     r9d, eax; char *
0x180050ace  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050ad5  mov     edx, 0FEh; void *
0x180050ada  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
