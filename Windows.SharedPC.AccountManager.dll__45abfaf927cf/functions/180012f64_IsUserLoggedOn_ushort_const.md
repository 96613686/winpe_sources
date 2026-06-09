# IsUserLoggedOn(ushort const *)

- ea: `0x180012f64`
- end: `0x180013037`
- name: `?IsUserLoggedOn@@YA_NPEBG@Z`
- size: `211`
- prototype: `bool __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d110`

## callees

- `0x180003530`
- `0x18000a104`
- `0x18000cd50`
- `0x180012784`
- `0x18001295c`
- `0x180012f64`
- `0x180013dcc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012fd9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012fd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IsUserLoggedOn(LPCWCH lpString1)
{
  char v2; // di
  __int128 *v3; // rbx
  __int128 *v4; // rsi
  const WCHAR *v5; // rax
  _QWORD *v7[4]; // [rsp+30h] [rbp-88h] BYREF
  __int128 v8; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-58h] BYREF

  v2 = 0;
  LogonTrigger::GetCurrentSessionUsers(v7);
  v3 = (__int128 *)v7[0];
  v4 = (__int128 *)v7[1];
  while ( v3 != v4 )
  {
    v8 = *v3;
    LogonTrigger::GetStringSidFromSessionUser((__int64)v9, (__int64)&v8);
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    if ( CompareStringOrdinal(lpString1, -1, v5, -1, 1) == 2 )
    {
      v2 = 1;
      std::wstring::_Tidy_deallocate((__int64)v9);
      break;
    }
    std::wstring::_Tidy_deallocate((__int64)v9);
    ++v3;
  }
  if ( v7[0] )
    std::_Deallocate<16>(v7[0], ((char *)v7[2] - (char *)v7[0]) & 0xFFFFFFFFFFFFFFF0uLL);
  return v2;
}

```

## disassembly

```asm
0x180012f64  push    rbx
0x180012f66  push    rbp
0x180012f67  push    rsi
0x180012f68  push    rdi
0x180012f69  sub     rsp, 98h
0x180012f70  mov     rax, cs:__security_cookie
0x180012f77  xor     rax, rsp
0x180012f7a  mov     [rsp+0B8h+var_38], rax
0x180012f82  mov     rbp, rcx
0x180012f85  xor     dil, dil
0x180012f88  lea     rcx, [rsp+0B8h+var_88]
0x180012f8d  call    ?GetCurrentSessionUsers@LogonTrigger@@SA?AV?$vector@U_SESSION_USER_CONTEXT@@V?$allocator@U_SESSION_USER_CONTEXT@@@std@@@std@@XZ; LogonTrigger::GetCurrentSessionUsers(void)
0x180012f92  nop
0x180012f93  mov     rbx, [rsp+0B8h+var_88]
0x180012f98  mov     rsi, [rsp+0B8h+var_80]
0x180012f9d  cmp     rbx, rsi
0x180012fa0  jz      short loc_180012FFD
0x180012fa2  movups  xmm0, xmmword ptr [rbx]
0x180012fa5  movdqu  [rsp+0B8h+var_68], xmm0
0x180012fab  lea     rdx, [rsp+0B8h+var_68]
0x180012fb0  lea     rcx, [rsp+0B8h+var_58]
0x180012fb5  call    ?GetStringSidFromSessionUser@LogonTrigger@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SESSION_USER_CONTEXT@@@Z; LogonTrigger::GetStringSidFromSessionUser(_SESSION_USER_CONTEXT)
0x180012fba  lea     rcx, [rsp+0B8h+var_58]
0x180012fbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012fc4  mov     r8, rax; lpString2
0x180012fc7  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x180012fcf  or      r9d, 0FFFFFFFFh; cchCount2
0x180012fd3  or      edx, r9d; cchCount1
0x180012fd6  mov     rcx, rbp; lpString1
0x180012fd9  call    cs:__imp_CompareStringOrdinal
0x180012fdf  lea     rcx, [rsp+0B8h+var_58]
0x180012fe4  cmp     eax, 2
0x180012fe7  jz      short loc_180012FF4
0x180012fe9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012fee  add     rbx, 10h
0x180012ff2  jmp     short loc_180012F9D
0x180012ff4  mov     dil, 1
0x180012ff7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ffc  nop
0x180012ffd  mov     rcx, [rsp+0B8h+var_88]
0x180013002  test    rcx, rcx
0x180013005  jz      short loc_180013018
0x180013007  mov     rdx, [rsp+0B8h+var_78]
0x18001300c  sub     rdx, rcx
0x18001300f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180013013  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013018  mov     al, dil
0x18001301b  mov     rcx, [rsp+0B8h+var_38]
0x180013023  xor     rcx, rsp; StackCookie
0x180013026  call    __security_check_cookie
0x18001302b  add     rsp, 98h
0x180013032  pop     rdi
0x180013033  pop     rsi
0x180013034  pop     rbp
0x180013035  pop     rbx
0x180013036  retn
```
