# Tsf3OverrideUtil::IsTsf3OverrideEnabledByPolicy(ushort const *)

- ea: `0x1800352c0`
- end: `0x1800354d6`
- name: `?IsTsf3OverrideEnabledByPolicy@Tsf3OverrideUtil@@YA?AW4PolicyStatus@1@PEBG@Z`
- size: `534`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180035020`

## callees

- `0x1800352c0`
- `0x18003563c`
- `0x18006ca64`
- `0x18008ab5c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180035429`
- `KERNEL32!SetLastError` at `0x180035461`
- `KERNEL32!SetLastError` at `0x180035429`
- `KERNEL32!SetLastError` at `0x180035461`
- `KERNEL32!GetLastError` at `0x180035416`
- `KERNEL32!GetLastError` at `0x18003544e`
- `KERNEL32!GetLastError` at `0x180035416`
- `KERNEL32!GetLastError` at `0x18003544e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800353aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800353aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800354b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800354b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035459`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035407`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035459`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035364`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035364`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Tsf3OverrideUtil::IsTsf3OverrideEnabledByPolicy(const wchar_t *a1)
{
  wchar_t **i; // rbx
  __int64 result; // rax
  const WCHAR *v4; // rsi
  const WCHAR *v5; // r14
  unsigned int v6; // eax
  BOOL v7; // ebx
  unsigned int v8; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD Type; // [rsp+88h] [rbp+10h] BYREF
  int Data; // [rsp+90h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  for ( i = off_1800A0050; ; i += 4 )
  {
    if ( i == (wchar_t **)&WinlogonServerTelemetry::ReportResultActivity::`vftable' )
      return 0;
    if ( !wcsicmp(*i, a1) )
      break;
LABEL_4:
    ;
  }
  v4 = i[1];
  if ( !v4 || (v5 = i[2]) == 0 )
  {
LABEL_7:
    if ( i[3] )
    {
      result = Tsf3OverrideUtil::IsTsf3OverrideEnabledByMdm();
      if ( (_DWORD)result )
        return result;
    }
    goto LABEL_4;
  }
  phkResult = 0;
  v6 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v6 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      (const char *)v6,
      v8);
LABEL_15:
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_7;
  }
  hKey = 0;
  if ( RegOpenKeyExW(phkResult, v4, 0, 0x20019u, &hKey)
    || (Type = 0, Data = 0, cbData = 4, RegQueryValueExW(hKey, v5, 0, &Type, (LPBYTE)&Data, &cbData))
    || Type != 4 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  v7 = Data != 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)(v7 + 1);
}

```

## disassembly

```asm
0x1800352c0  mov     [rsp+arg_0], rbx
0x1800352c5  push    rbp
0x1800352c6  push    rsi
0x1800352c7  push    rdi
0x1800352c8  push    r12
0x1800352ca  push    r13
0x1800352cc  push    r14
0x1800352ce  push    r15
0x1800352d0  sub     rsp, 40h
0x1800352d4  mov     r15, rcx
0x1800352d7  lea     rbx, off_1800A0050; "{03b5835f-f03c-411b-9ce2-aa23e1171e36}"
0x1800352de  lea     r12, ??_7ReportResultActivity@WinlogonServerTelemetry@@6B@; const WinlogonServerTelemetry::ReportResultActivity::`vftable'
0x1800352e5  xor     r13d, r13d
0x1800352e8  cmp     rbx, r12
0x1800352eb  jz      short loc_180035302
0x1800352ed  mov     rdx, r15; String2
0x1800352f0  mov     rcx, [rbx]; String1
0x1800352f3  call    _wcsicmp
0x1800352f8  test    eax, eax
0x1800352fa  jz      short loc_18003531C
0x1800352fc  add     rbx, 20h ; ' '
0x180035300  jmp     short loc_1800352E8
0x180035302  xor     eax, eax
0x180035304  mov     rbx, [rsp+78h+arg_0]
0x18003530c  add     rsp, 40h
0x180035310  pop     r15
0x180035312  pop     r14
0x180035314  pop     r13
0x180035316  pop     r12
0x180035318  pop     rdi
0x180035319  pop     rsi
0x18003531a  pop     rbp
0x18003531b  retn
0x18003531c  mov     rsi, [rbx+8]
0x180035320  test    rsi, rsi
0x180035323  jnz     short loc_180035339
0x180035325  mov     rcx, [rbx+18h]
0x180035329  test    rcx, rcx
0x18003532c  jz      short loc_1800352FC
0x18003532e  call    ?IsTsf3OverrideEnabledByMdm@Tsf3OverrideUtil@@YA?AW4PolicyStatus@1@PEBG@Z; Tsf3OverrideUtil::IsTsf3OverrideEnabledByMdm(ushort const *)
0x180035333  test    eax, eax
0x180035335  jz      short loc_1800352FC
0x180035337  jmp     short loc_180035304
0x180035339  mov     r14, [rbx+10h]
0x18003533d  test    r14, r14
0x180035340  jz      short loc_180035325
0x180035342  mov     [rsp+78h+phkResult], r13
0x180035347  mov     rbp, [rsp+78h+phkResult]
0x18003534c  test    rbp, rbp
0x18003534f  jnz     loc_180035416
0x180035355  mov     [rsp+78h+phkResult], r13
0x18003535a  lea     rdx, [rsp+78h+phkResult]; phkResult
0x18003535f  mov     ecx, 20019h; samDesired
0x180035364  call    cs:__imp_RegOpenCurrentUser
0x18003536a  mov     rcx, [rsp+78h]; this
0x18003536f  test    eax, eax
0x180035371  jnz     loc_180035435
0x180035377  mov     [rsp+78h+hKey], r13
0x18003537c  mov     rbp, [rsp+78h+hKey]
0x180035381  test    rbp, rbp
0x180035384  jnz     loc_18003544E
0x18003538a  mov     [rsp+78h+hKey], r13
0x18003538f  lea     rax, [rsp+78h+hKey]
0x180035394  mov     [rsp+78h+var_58], rax; phkResult
0x180035399  mov     r9d, 20019h; samDesired
0x18003539f  xor     r8d, r8d; ulOptions
0x1800353a2  mov     rdx, rsi; lpSubKey
0x1800353a5  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800353aa  call    cs:__imp_RegOpenKeyExW
0x1800353b0  test    eax, eax
0x1800353b2  jz      loc_18003546D
0x1800353b8  mov     rcx, [rsp+78h+hKey]; hKey
0x1800353bd  test    rcx, rcx
0x1800353c0  jz      short loc_1800353C9
0x1800353c2  call    cs:__imp_RegCloseKey
0x1800353c8  nop
0x1800353c9  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800353ce  test    rcx, rcx
0x1800353d1  jz      short loc_1800353DA
0x1800353d3  call    cs:__imp_RegCloseKey
0x1800353d9  nop
0x1800353da  jmp     loc_180035325
0x1800353df  mov     ebx, r13d
0x1800353e2  cmp     [rsp+78h+Data], ebx
0x1800353e9  setnz   bl
0x1800353ec  mov     rcx, [rsp+78h+hKey]; hKey
0x1800353f1  test    rcx, rcx
0x1800353f4  jz      short loc_1800353FD
0x1800353f6  call    cs:__imp_RegCloseKey
0x1800353fc  nop
0x1800353fd  mov     rcx, [rsp+78h+phkResult]; hKey
0x180035402  test    rcx, rcx
0x180035405  jz      short loc_18003540E
0x180035407  call    cs:__imp_RegCloseKey
0x18003540d  nop
0x18003540e  lea     eax, [rbx+1]
0x180035411  jmp     loc_180035304
0x180035416  call    cs:__imp_GetLastError
0x18003541c  mov     edi, eax
0x18003541e  mov     rcx, rbp; hKey
0x180035421  call    cs:__imp_RegCloseKey
0x180035427  mov     ecx, edi; dwErrCode
0x180035429  call    cs:__imp_SetLastError
0x18003542f  nop
0x180035430  jmp     loc_180035355
0x180035435  mov     r9d, eax; char *
0x180035438  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x18003543f  mov     edx, 0FCh; void *
0x180035444  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180035449  jmp     loc_1800353C9
0x18003544e  call    cs:__imp_GetLastError
0x180035454  mov     edi, eax
0x180035456  mov     rcx, rbp; hKey
0x180035459  call    cs:__imp_RegCloseKey
0x18003545f  mov     ecx, edi; dwErrCode
0x180035461  call    cs:__imp_SetLastError
0x180035467  nop
0x180035468  jmp     loc_18003538A
0x18003546d  mov     [rsp+78h+Type], r13d
0x180035475  mov     [rsp+78h+Data], r13d
0x18003547d  mov     [rsp+78h+cbData], 4
0x180035488  lea     rax, [rsp+78h+cbData]
0x180035490  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180035495  lea     rax, [rsp+78h+Data]
0x18003549d  mov     [rsp+78h+var_58], rax; lpData
0x1800354a2  lea     r9, [rsp+78h+Type]; lpType
0x1800354aa  xor     r8d, r8d; lpReserved
0x1800354ad  mov     rdx, r14; lpValueName
0x1800354b0  mov     rcx, [rsp+78h+hKey]; hKey
0x1800354b5  call    cs:__imp_RegQueryValueExW
0x1800354bb  test    eax, eax
0x1800354bd  jnz     loc_1800353B8
0x1800354c3  cmp     [rsp+78h+Type], 4
0x1800354cb  jz      loc_1800353DF
0x1800354d1  jmp     loc_1800353B8
```
