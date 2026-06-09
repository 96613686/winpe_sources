# FwRuleSerializeCapabilities(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ushort const *,_INET_FIREWALL_AC_CAPABILITIES *)

- ea: `0x18000e150`
- end: `0x18000e26d`
- name: `?FwRuleSerializeCapabilities@@YAJPEAG_KPEAPEAGPEA_KPEBGPEAU_INET_FIREWALL_AC_CAPABILITIES@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int64, unsigned __int16 **, unsigned __int64 *, const unsigned __int16 *, struct _INET_FIREWALL_AC_CAPABILITIES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d290`

## callees

- `0x18000cff0`
- `0x18000e150`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e248`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e231`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e231`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e1d1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e1d1`

## pseudocode

```c
__int64 __fastcall FwRuleSerializeCapabilities(
        STRSAFE_LPWSTR pszDest,
        unsigned __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        const unsigned __int16 *a5,
        struct _INET_FIREWALL_AC_CAPABILITIES *a6)
{
  int v6; // ebx
  DWORD v7; // edi
  unsigned __int64 v10; // rbp
  STRSAFE_LPWSTR v11; // rsi
  signed int LastError; // eax
  unsigned __int16 *v14; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v15; // [rsp+58h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-48h] BYREF

  v6 = 0;
  StringSid = 0;
  v7 = 0;
  v14 = pszDest;
  v15 = a2;
  v10 = a2;
  v11 = pszDest;
  while ( 1 )
  {
    if ( v7 >= a6->count )
    {
      *a3 = v11;
      *a4 = v10;
      return (unsigned int)v6;
    }
    if ( !ConvertSidToStringSidW(a6->capabilities[v7].Sid, &StringSid) )
      break;
    v6 = StringCchPrintfExW(v11, v10, &v14, &v15, 0x800u, L"%s%s%s", L"C=", StringSid, L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LocalFree(StringSid);
    v11 = v14;
    ++v7;
    v10 = v15;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e150  push    rbx
0x18000e152  push    rbp
0x18000e153  push    rsi
0x18000e154  push    rdi
0x18000e155  push    r12
0x18000e157  push    r14
0x18000e159  push    r15
0x18000e15b  sub     rsp, 70h
0x18000e15f  mov     rax, cs:__security_cookie
0x18000e166  xor     rax, rsp
0x18000e169  mov     [rsp+0A8h+var_40], rax
0x18000e16e  mov     r14, [rsp+0A8h+arg_28]
0x18000e176  xor     ebx, ebx
0x18000e178  mov     [rsp+0A8h+StringSid], rbx
0x18000e17d  xor     edi, edi
0x18000e17f  mov     r12, r9
0x18000e182  mov     [rsp+0A8h+var_58], rcx
0x18000e187  mov     r15, r8
0x18000e18a  mov     [rsp+0A8h+var_50], rdx
0x18000e18f  mov     rbp, rdx
0x18000e192  mov     rsi, rcx
0x18000e195  cmp     edi, [r14]
0x18000e198  jb      short loc_18000E1BF
0x18000e19a  mov     [r15], rsi
0x18000e19d  mov     [r12], rbp
0x18000e1a1  mov     eax, ebx
0x18000e1a3  mov     rcx, [rsp+0A8h+var_40]
0x18000e1a8  xor     rcx, rsp; StackCookie
0x18000e1ab  call    __security_check_cookie
0x18000e1b0  add     rsp, 70h
0x18000e1b4  pop     r15
0x18000e1b6  pop     r14
0x18000e1b8  pop     r12
0x18000e1ba  pop     rdi
0x18000e1bb  pop     rsi
0x18000e1bc  pop     rbp
0x18000e1bd  pop     rbx
0x18000e1be  retn
0x18000e1bf  mov     rcx, [r14+8]
0x18000e1c3  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x18000e1c8  mov     eax, edi
0x18000e1ca  add     rax, rax
0x18000e1cd  mov     rcx, [rcx+rax*8]; Sid
0x18000e1d1  call    cs:__imp_ConvertSidToStringSidW
0x18000e1d7  test    eax, eax
0x18000e1d9  jz      short loc_18000E248
0x18000e1db  lea     rax, asc_18003D4F8; "|"
0x18000e1e2  mov     rdx, rbp; unsigned __int64
0x18000e1e5  mov     [rsp+0A8h+var_68], rax
0x18000e1ea  lea     r9, [rsp+0A8h+var_50]; unsigned __int64 *
0x18000e1ef  mov     rax, [rsp+0A8h+StringSid]
0x18000e1f4  lea     r8, [rsp+0A8h+var_58]; unsigned __int16 **
0x18000e1f9  mov     [rsp+0A8h+var_70], rax
0x18000e1fe  mov     rcx, rsi; pszDest
0x18000e201  lea     rax, aC; "C="
0x18000e208  mov     [rsp+0A8h+var_78], rax
0x18000e20d  lea     rax, aSSS_2; "%s%s%s"
0x18000e214  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18000e219  mov     [rsp+0A8h+var_88], 800h; unsigned int
0x18000e221  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e226  mov     ebx, eax
0x18000e228  test    eax, eax
0x18000e22a  js      short loc_18000E266
0x18000e22c  mov     rcx, [rsp+0A8h+StringSid]; hMem
0x18000e231  call    cs:__imp_LocalFree
0x18000e237  mov     rsi, [rsp+0A8h+var_58]
0x18000e23c  inc     edi
0x18000e23e  mov     rbp, [rsp+0A8h+var_50]
0x18000e243  jmp     loc_18000E195
0x18000e248  call    cs:__imp_GetLastError
0x18000e24e  mov     ebx, eax
0x18000e250  test    eax, eax
0x18000e252  jle     loc_18000E1A1
0x18000e258  movzx   ebx, ax
0x18000e25b  or      ebx, 80070000h
0x18000e261  jmp     loc_18000E1A1
0x18000e266  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e26b  jmp     short loc_18000E22C
```
