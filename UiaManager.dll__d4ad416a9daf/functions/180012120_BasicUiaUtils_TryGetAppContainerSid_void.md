# BasicUiaUtils::TryGetAppContainerSid(void *)

- ea: `0x180012120`
- end: `0x180012238`
- name: `?TryGetAppContainerSid@BasicUiaUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `280`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800294d0`
- `0x18006ef3c`

## callees

- `0x180012120`
- `0x180012240`
- `0x18001227c`
- `0x18002a514`
- `0x180043680`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001217e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001217e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800121b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800121b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121f1`

## string_xrefs

- `0x180012190`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x1800121c7`: `onecore\windows\accessibletech\common\basicuiautils.cpp`

## pseudocode

```c
__int64 __fastcall BasicUiaUtils::TryGetAppContainerSid(__int64 a1, void *a2)
{
  const char *v4; // r9
  const char *v5; // r9
  LPWSTR StringSid; // [rsp+30h] [rbp-78h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-70h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  StringSid = (LPWSTR)a1;
  if ( BasicUtils::IsAppContainer(a2) )
  {
    ReturnLength = 0;
    if ( !GetTokenInformation(a2, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
        v4);
    StringSid = 0;
    if ( !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
        v5);
    std::wstring::wstring(a1, StringSid);
    if ( StringSid )
      LocalFree(StringSid);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180012120  mov     [rsp+arg_10], rbx
0x180012125  push    rdi
0x180012126  sub     rsp, 0A0h
0x18001212d  mov     rax, cs:__security_cookie
0x180012134  xor     rax, rsp
0x180012137  mov     [rsp+0A8h+var_18], rax
0x18001213f  mov     rdi, rdx
0x180012142  mov     rbx, rcx
0x180012145  mov     [rsp+0A8h+StringSid], rcx
0x18001214a  mov     rcx, rdx; void *
0x18001214d  call    ?IsAppContainer@BasicUtils@@SA_NPEAX@Z; BasicUtils::IsAppContainer(void *)
0x180012152  test    al, al
0x180012154  jz      loc_1800121F9
0x18001215a  mov     [rsp+0A8h+var_70], 0
0x180012162  lea     rax, [rsp+0A8h+var_70]
0x180012167  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18001216c  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180012172  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x180012177  lea     edx, [r9-2Dh]; TokenInformationClass
0x18001217b  mov     rcx, rdi; TokenHandle
0x18001217e  call    cs:__imp_GetTokenInformation
0x180012184  mov     rcx, [rsp+0A8h]; this
0x18001218c  test    eax, eax
0x18001218e  jnz     short loc_1800121A2
0x180012190  lea     r8, aOnecoreWindows_6; "onecore\\windows\\accessibletech\\commo"...
0x180012197  mov     edx, 0A3h; void *
0x18001219c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800121a2  mov     [rsp+0A8h+StringSid], 0
0x1800121ab  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x1800121b0  mov     rcx, [rsp+0A8h+TokenInformation]; Sid
0x1800121b5  call    cs:__imp_ConvertSidToStringSidW
0x1800121bb  mov     rcx, [rsp+0A8h]; this
0x1800121c3  test    eax, eax
0x1800121c5  jnz     short loc_1800121D9
0x1800121c7  lea     r8, aOnecoreWindows_6; "onecore\\windows\\accessibletech\\commo"...
0x1800121ce  mov     edx, 0A8h; void *
0x1800121d3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800121d9  mov     rdx, [rsp+0A8h+StringSid]
0x1800121de  mov     rcx, rbx
0x1800121e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800121e6  nop
0x1800121e7  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x1800121ec  test    rcx, rcx
0x1800121ef  jz      short loc_180012214
0x1800121f1  call    cs:__imp_LocalFree
0x1800121f7  jmp     short loc_180012214
0x1800121f9  xorps   xmm0, xmm0
0x1800121fc  movups  xmmword ptr [rbx], xmm0
0x1800121ff  mov     qword ptr [rbx+10h], 0
0x180012207  mov     qword ptr [rbx+18h], 7
0x18001220f  xor     eax, eax
0x180012211  mov     [rbx], ax
0x180012214  mov     rax, rbx
0x180012217  mov     rcx, [rsp+0A8h+var_18]
0x18001221f  xor     rcx, rsp; StackCookie
0x180012222  call    __security_check_cookie
0x180012227  mov     rbx, [rsp+0A8h+arg_10]
0x18001222f  add     rsp, 0A0h
0x180012236  pop     rdi
0x180012237  retn
```
