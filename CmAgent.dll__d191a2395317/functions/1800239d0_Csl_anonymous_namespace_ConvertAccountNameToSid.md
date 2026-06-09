# Csl::_anonymous_namespace_::ConvertAccountNameToSid

- ea: `0x1800239d0`
- end: `0x180023b13`
- name: `Csl::_anonymous_namespace_::ConvertAccountNameToSid`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023844`
- `0x180024080`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b2c`
- `0x1800239d0`
- `0x180023b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023aa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ac0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ae0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023a4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023a4e`

## string_xrefs

- `0x180023a0a`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180023a62`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::_anonymous_namespace_::ConvertAccountNameToSid(__int64 a1, PSID *a2)
{
  int v3; // eax
  unsigned int LastError; // ebx
  const char *v6; // r9
  PSID v7; // rsi
  PSID v8; // r14
  DWORD v9; // ebx
  PSID v10; // rcx
  PSID Sid; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR StringSid[2]; // [rsp+28h] [rbp-28h] BYREF
  _WORD v13[12]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  StringSid[0] = v13;
  StringSid[1] = v13;
  v13[0] = 0;
  v3 = Csl::_anonymous_namespace_::ConvertAccountNameToStringSid(a1, (__int64)StringSid);
  LastError = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v3);
LABEL_3:
    if ( StringSid[0] != v13 )
      operator delete((void *)StringSid[0], (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(StringSid[0], &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x106,
                  (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  v6);
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_3;
  }
  if ( a2 == &Sid )
  {
    v10 = Sid;
  }
  else
  {
    v7 = *a2;
    v8 = Sid;
    if ( *a2 )
    {
      v9 = GetLastError();
      LocalFree(v7);
      SetLastError(v9);
    }
    v10 = 0;
    *a2 = v8;
    Sid = 0;
  }
  if ( v10 )
    LocalFree(v10);
  if ( StringSid[0] != v13 )
    operator delete((void *)StringSid[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1800239d0  push    rbp
0x1800239d2  push    rbx
0x1800239d3  push    rsi
0x1800239d4  push    rdi
0x1800239d5  push    r14
0x1800239d7  mov     rbp, rsp
0x1800239da  sub     rsp, 50h
0x1800239de  lea     rax, [rbp+var_18]
0x1800239e2  mov     rdi, rdx
0x1800239e5  mov     [rbp+StringSid], rax
0x1800239e9  lea     rdx, [rbp+StringSid]
0x1800239ed  lea     rax, [rbp+var_18]
0x1800239f1  mov     [rbp+var_20], rax
0x1800239f5  xor     eax, eax
0x1800239f7  mov     [rbp+var_18], ax
0x1800239fb  call    Csl___anonymous_namespace___ConvertAccountNameToStringSid
0x180023a00  mov     ebx, eax
0x180023a02  test    eax, eax
0x180023a04  jns     short loc_180023A3E
0x180023a06  mov     rcx, [rbp+28h]; this
0x180023a0a  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023a11  mov     r9d, eax; char *
0x180023a14  mov     edx, 103h; void *
0x180023a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a1e  mov     rcx, [rbp+StringSid]; void *
0x180023a22  lea     rax, [rbp+var_18]
0x180023a26  cmp     rcx, rax
0x180023a29  jz      short loc_180023A37
0x180023a2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023a32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023a37  mov     eax, ebx
0x180023a39  jmp     loc_180023B07
0x180023a3e  mov     rcx, [rbp+StringSid]; StringSid
0x180023a42  lea     rdx, [rbp+Sid]; Sid
0x180023a46  mov     [rbp+Sid], 0
0x180023a4e  call    cs:__imp_ConvertStringSidToSidW
0x180023a55  nop     dword ptr [rax+rax+00h]
0x180023a5a  test    eax, eax
0x180023a5c  jnz     short loc_180023A8C
0x180023a5e  mov     rcx, [rbp+28h]; this
0x180023a62  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023a69  mov     edx, 106h; void *
0x180023a6e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023a73  mov     rcx, [rbp+Sid]; hMem
0x180023a77  mov     ebx, eax
0x180023a79  test    rcx, rcx
0x180023a7c  jz      short loc_180023A1E
0x180023a7e  call    cs:__imp_LocalFree
0x180023a85  nop     dword ptr [rax+rax+00h]
0x180023a8a  jmp     short loc_180023A1E
0x180023a8c  lea     rax, [rbp+Sid]
0x180023a90  cmp     rdi, rax
0x180023a93  jz      short loc_180023AD7
0x180023a95  mov     rsi, [rdi]
0x180023a98  mov     r14, [rbp+Sid]
0x180023a9c  test    rsi, rsi
0x180023a9f  jz      short loc_180023ACC
0x180023aa1  call    cs:__imp_GetLastError
0x180023aa8  nop     dword ptr [rax+rax+00h]
0x180023aad  mov     rcx, rsi; hMem
0x180023ab0  mov     ebx, eax
0x180023ab2  call    cs:__imp_LocalFree
0x180023ab9  nop     dword ptr [rax+rax+00h]
0x180023abe  mov     ecx, ebx; dwErrCode
0x180023ac0  call    cs:__imp_SetLastError
0x180023ac7  nop     dword ptr [rax+rax+00h]
0x180023acc  xor     ecx, ecx
0x180023ace  mov     [rdi], r14
0x180023ad1  mov     [rbp+Sid], rcx
0x180023ad5  jmp     short loc_180023ADB
0x180023ad7  mov     rcx, [rbp+Sid]; hMem
0x180023adb  test    rcx, rcx
0x180023ade  jz      short loc_180023AEC
0x180023ae0  call    cs:__imp_LocalFree
0x180023ae7  nop     dword ptr [rax+rax+00h]
0x180023aec  mov     rcx, [rbp+StringSid]; void *
0x180023af0  lea     rax, [rbp+var_18]
0x180023af4  cmp     rcx, rax
0x180023af7  jz      short loc_180023B05
0x180023af9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023b00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023b05  xor     eax, eax
0x180023b07  add     rsp, 50h
0x180023b0b  pop     r14
0x180023b0d  pop     rdi
0x180023b0e  pop     rsi
0x180023b0f  pop     rbx
0x180023b10  pop     rbp
0x180023b11  retn
```
