# GetUserTokenFromSid(ushort const *,ulong,void * *)

- ea: `0x180008830`
- end: `0x180008990`
- name: `?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(wchar_t *String2, ULONG SessionId, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001c54c`

## callees

- `0x180008830`
- `0x18000a3c0`
- `0x18001f3da`
- `0x18001f420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800088fd`
- `msvcrt!_wcsicmp` at `0x1800088fd`
- `ADVAPI32!GetTokenInformation` at `0x1800088c0`
- `ADVAPI32!GetTokenInformation` at `0x1800088c0`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800088e3`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800088e3`
- `KERNEL32!GetLastError` at `0x180008917`
- `KERNEL32!GetLastError` at `0x180008917`
- `WTSAPI32!WTSQueryUserToken` at `0x180008891`
- `WTSAPI32!WTSQueryUserToken` at `0x180008891`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSid(wchar_t *String2, ULONG SessionId, void **a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE phToken; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[128]; // [rsp+50h] [rbp-B0h] BYREF

  phToken = 0;
  ReturnLength = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  *a3 = 0;
  if ( WTSQueryUserToken(SessionId, &phToken)
    && GetTokenInformation(phToken, TokenUser, TokenInformation, 0x400u, &ReturnLength)
    && (StringSid = 0, ConvertSidToStringSidW(TokenInformation[0], &StringSid)) )
  {
    v6 = 0;
    if ( !_wcsicmp(StringSid, String2) )
      *a3 = phToken;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids,
        (_DWORD)String2,
        v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180008830  mov     [rsp-8+arg_18], rbx
0x180008835  push    rbp
0x180008836  push    rsi
0x180008837  push    rdi
0x180008838  lea     rbp, [rsp-360h]
0x180008840  sub     rsp, 460h
0x180008847  mov     rax, cs:__security_cookie
0x18000884e  xor     rax, rsp
0x180008851  mov     [rbp+370h+var_20], rax
0x180008858  mov     rdi, r8
0x18000885b  mov     [rsp+470h+phToken], 0
0x180008864  mov     ebx, edx
0x180008866  mov     [rsp+470h+var_440], 0
0x18000886e  mov     rsi, rcx
0x180008871  xor     edx, edx; Val
0x180008873  mov     r8d, 400h; Size
0x180008879  lea     rcx, [rsp+470h+TokenInformation]; void *
0x18000887e  call    memset_0
0x180008883  lea     rdx, [rsp+470h+phToken]; phToken
0x180008888  mov     qword ptr [rdi], 0
0x18000888f  mov     ecx, ebx; SessionId
0x180008891  call    cs:__imp_WTSQueryUserToken
0x180008898  nop     dword ptr [rax+rax+00h]
0x18000889d  test    eax, eax
0x18000889f  jz      short loc_180008917
0x1800088a1  mov     rcx, [rsp+470h+phToken]; TokenHandle
0x1800088a6  lea     rax, [rsp+470h+var_440]
0x1800088ab  mov     r9d, 400h; TokenInformationLength
0x1800088b1  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x1800088b6  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x1800088bb  mov     edx, 1; TokenInformationClass
0x1800088c0  call    cs:__imp_GetTokenInformation
0x1800088c7  nop     dword ptr [rax+rax+00h]
0x1800088cc  test    eax, eax
0x1800088ce  jz      short loc_180008917
0x1800088d0  mov     rcx, [rsp+470h+TokenInformation]; Sid
0x1800088d5  lea     rdx, [rsp+470h+StringSid]; StringSid
0x1800088da  mov     [rsp+470h+StringSid], 0
0x1800088e3  call    cs:__imp_ConvertSidToStringSidW
0x1800088ea  nop     dword ptr [rax+rax+00h]
0x1800088ef  test    eax, eax
0x1800088f1  jz      short loc_180008917
0x1800088f3  mov     rcx, [rsp+470h+StringSid]; String1
0x1800088f8  mov     rdx, rsi; String2
0x1800088fb  xor     ebx, ebx
0x1800088fd  call    cs:__imp__wcsicmp
0x180008904  nop     dword ptr [rax+rax+00h]
0x180008909  test    eax, eax
0x18000890b  jnz     short loc_18000896B
0x18000890d  mov     rax, [rsp+470h+phToken]
0x180008912  mov     [rdi], rax
0x180008915  jmp     short loc_18000896B
0x180008917  call    cs:__imp_GetLastError
0x18000891e  nop     dword ptr [rax+rax+00h]
0x180008923  mov     ebx, eax
0x180008925  test    eax, eax
0x180008927  jle     short loc_180008932
0x180008929  movzx   ebx, ax
0x18000892c  or      ebx, 80070000h
0x180008932  test    ebx, ebx
0x180008934  jz      short loc_18000896B
0x180008936  mov     rcx, cs:WPP_GLOBAL_Control
0x18000893d  lea     rax, WPP_GLOBAL_Control
0x180008944  cmp     rcx, rax
0x180008947  jz      short loc_18000896B
0x180008949  test    byte ptr [rcx+1Ch], 4
0x18000894d  jz      short loc_18000896B
0x18000894f  mov     rcx, [rcx+10h]
0x180008953  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x18000895a  mov     edx, 6Eh ; 'n'
0x18000895f  mov     dword ptr [rsp+470h+ReturnLength], ebx
0x180008963  mov     r9, rsi
0x180008966  call    WPP_SF_Sd
0x18000896b  mov     eax, ebx
0x18000896d  mov     rcx, [rbp+370h+var_20]
0x180008974  xor     rcx, rsp; StackCookie
0x180008977  call    __security_check_cookie
0x18000897c  mov     rbx, [rsp+470h+arg_18]
0x180008984  add     rsp, 460h
0x18000898b  pop     rdi
0x18000898c  pop     rsi
0x18000898d  pop     rbp
0x18000898e  retn
```
