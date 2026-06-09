# GetUserNameForSid(wchar_t const *)

- ea: `0x180026368`
- end: `0x180026473`
- name: `?GetUserNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026780`

## callees

- `0x180011e18`
- `0x180014c04`
- `0x180026234`
- `0x180026368`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800263b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800263b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800263da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800263da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026451`

## string_xrefs

- `0x180026400`: `ConvertStringSidToSid failed for %s: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserNameForSid(__int64 a1)
{
  BOOL v2; // r12d
  DWORD LastError; // eax
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v6; // [rsp+38h] [rbp-8h]
  HLOCAL hMem; // [rsp+78h] [rbp+38h]

  hMem = 0;
  Sid = 0;
  v6 = 1;
  v2 = ConvertStringSidToSidW(L"S-1-5-110", &Sid);
  if ( v6 )
    hMem = Sid;
  if ( v2 )
  {
    GetUserNameForSid(a1, hMem);
  }
  else
  {
    LastError = GetLastError();
    Log(2u, L"ConvertStringSidToSid failed for %s: %#x", L"S-1-5-110", LastError);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)a1, &word_180096C4C, 0);
  }
  if ( hMem )
    LocalFree(hMem);
  return a1;
}

```

## disassembly

```asm
0x180026368  mov     [rsp-28h+arg_0], rbx
0x18002636d  mov     [rsp-28h+arg_10], rsi
0x180026372  mov     [rsp-28h+hMem], rdx
0x180026377  push    rbp
0x180026378  push    rdi
0x180026379  push    r12
0x18002637b  push    r14
0x18002637d  push    r15
0x18002637f  mov     rbp, rsp
0x180026382  sub     rsp, 40h
0x180026386  mov     rdi, rcx
0x180026389  mov     [rbp+hMem], 0
0x180026391  lea     rax, [rbp+hMem]
0x180026395  mov     [rbp+var_18], rax
0x180026399  mov     [rbp+Sid], 0
0x1800263a1  mov     [rbp+var_8], 1
0x1800263a5  lea     rdx, [rbp+Sid]; Sid
0x1800263a9  lea     rcx, StringSid; "S-1-5-110"
0x1800263b0  call    cs:__imp_ConvertStringSidToSidW
0x1800263b6  mov     r12d, eax
0x1800263b9  cmp     [rbp+var_8], 0
0x1800263bd  jz      short loc_1800263EB
0x1800263bf  mov     r15, [rbp+Sid]
0x1800263c3  mov     rsi, [rbp+var_18]
0x1800263c7  mov     r14, [rsi]
0x1800263ca  test    r14, r14
0x1800263cd  jz      short loc_1800263E8
0x1800263cf  call    cs:__imp_GetLastError
0x1800263d5  mov     ebx, eax
0x1800263d7  mov     rcx, r14; hMem
0x1800263da  call    cs:__imp_LocalFree
0x1800263e0  mov     ecx, ebx; dwErrCode
0x1800263e2  call    cs:__imp_SetLastError
0x1800263e8  mov     [rsi], r15
0x1800263eb  test    r12d, r12d
0x1800263ee  jnz     short loc_18002643B
0x1800263f0  call    cs:__imp_GetLastError
0x1800263f6  mov     r9d, eax
0x1800263f9  lea     r8, StringSid; "S-1-5-110"
0x180026400  lea     rdx, aConvertstrings; "ConvertStringSidToSid failed for %s: %#"...
0x180026407  lea     ecx, [r12+2]; unsigned __int8
0x18002640c  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180026411  xorps   xmm0, xmm0
0x180026414  movups  xmmword ptr [rdi], xmm0
0x180026417  mov     qword ptr [rdi+10h], 0
0x18002641f  mov     qword ptr [rdi+18h], 0
0x180026427  xor     r8d, r8d
0x18002642a  lea     rdx, word_180096C4C
0x180026431  mov     rcx, rdi
0x180026434  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180026439  jmp     short loc_180026448
0x18002643b  mov     rdx, [rbp+hMem]
0x18002643f  mov     rcx, rdi
0x180026442  call    ?GetUserNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z; GetUserNameForSid(void *)
0x180026447  nop
0x180026448  mov     rcx, [rbp+hMem]; hMem
0x18002644c  test    rcx, rcx
0x18002644f  jz      short loc_180026457
0x180026451  call    cs:__imp_LocalFree
0x180026457  mov     rax, rdi
0x18002645a  lea     r11, [rsp+40h+var_s0]
0x18002645f  mov     rbx, [r11+30h]
0x180026463  mov     rsi, [r11+40h]
0x180026467  mov     rsp, r11
0x18002646a  pop     r15
0x18002646c  pop     r14
0x18002646e  pop     r12
0x180026470  pop     rdi
0x180026471  pop     rbp
0x180026472  retn
```
