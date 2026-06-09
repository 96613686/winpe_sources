# FwRuleSerializeFlag(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,_tag_FW_RULE *)

- ea: `0x18000e964`
- end: `0x18000eb55`
- name: `?FwRuleSerializeFlag@@YAJPEAG_KPEAPEAGPEA_KPEAU_tag_FW_RULE@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a328`

## callees

- `0x18000cff0`
- `0x18000e964`
- `0x18001e9ac`

## string_xrefs

- `0x18000e998`: `Security=`
- `0x18000e9e8`: `Security=`
- `0x18000eab2`: `Security2_9=`
- `0x18000ea62`: `Security2=`

## pseudocode

```c
__int64 __fastcall FwRuleSerializeFlag(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        struct _tag_FW_RULE *a5)
{
  struct _tag_FW_RULE *v5; // rdi
  int v6; // ebx
  STRSAFE_LPWSTR pszDest; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v11; // [rsp+98h] [rbp+48h] BYREF

  v5 = a5;
  v6 = 0;
  pszDest = a1;
  v11 = a2;
  if ( (*((_BYTE *)a5 + 292) & 2) != 0 )
  {
    v6 = StringCchPrintfExW(a1, a2, &pszDest, &v11, 0x800u, L"%s%s%s", L"Security=", L"Authenticate", L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_BYTE *)v5 + 292) & 4) != 0 )
  {
    v6 = StringCchPrintfExW(pszDest, v11, &pszDest, &v11, 0x800u, L"%s%s%s", L"Security=", L"AuthenticateEncrypt", L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_BYTE *)v5 + 292) & 0x40) != 0 )
  {
    v6 = StringCchPrintfExW(pszDest, v11, &pszDest, &v11, 0x800u, L"%s%s%s", L"Security2=", L"AnE-Nego", L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_BYTE *)v5 + 292) & 0x20) != 0 )
  {
    v6 = StringCchPrintfExW(pszDest, v11, &pszDest, &v11, 0x800u, L"%s%s%s", L"Security2_9=", L"An-NoEncap", L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_WORD *)v5 + 146) & 0x200) != 0 )
  {
    v6 = StringCchPrintfExW(pszDest, v11, &pszDest, &v11, 0x800u, L"%s%s%s", L"AuthByPassOut=", L"TRUE", L"|");
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a3 = pszDest;
  *a4 = v11;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e964  mov     r11, rsp
0x18000e967  mov     [r11+18h], rbx
0x18000e96b  push    rbp
0x18000e96c  push    rsi
0x18000e96d  push    rdi
0x18000e96e  push    r12
0x18000e970  push    r13
0x18000e972  push    r14
0x18000e974  push    r15
0x18000e976  mov     rbp, rsp
0x18000e979  sub     rsp, 50h
0x18000e97d  mov     rdi, [rbp+arg_20]
0x18000e981  lea     r12, asc_18003D4F8; "|"
0x18000e988  xor     ebx, ebx
0x18000e98a  mov     [rbp+pszDest], rcx
0x18000e98e  mov     r14, r8
0x18000e991  mov     [rbp+arg_8], rdx
0x18000e995  mov     rsi, r9
0x18000e998  lea     r8, aSecurity; "Security="
0x18000e99f  test    byte ptr [rdi+124h], 2
0x18000e9a6  lea     r13, aSSS_2; "%s%s%s"
0x18000e9ad  mov     r15d, 800h
0x18000e9b3  jz      short loc_18000E9EF
0x18000e9b5  mov     [r11-48h], r12
0x18000e9b9  lea     rax, aAuthenticate; "Authenticate"
0x18000e9c0  mov     [r11-50h], rax
0x18000e9c4  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000e9c8  mov     [r11-58h], r8
0x18000e9cc  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18000e9d0  mov     [r11-60h], r13
0x18000e9d4  mov     [r11-68h], r15d
0x18000e9d8  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e9dd  mov     ebx, eax
0x18000e9df  test    eax, eax
0x18000e9e1  jns     short loc_18000E9E8
0x18000e9e3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e9e8  lea     r8, aSecurity; "Security="
0x18000e9ef  test    byte ptr [rdi+124h], 4
0x18000e9f6  jz      short loc_18000EA38
0x18000e9f8  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000e9fc  lea     rax, aAuthenticateen; "AuthenticateEncrypt"
0x18000ea03  mov     rcx, [rbp+pszDest]; pszDest
0x18000ea07  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000ea0b  mov     [rsp+50h+var_10], r12
0x18000ea10  mov     [rsp+50h+var_18], rax
0x18000ea15  mov     [rsp+50h+var_20], r8
0x18000ea1a  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18000ea1e  mov     [rsp+50h+var_28], r13; unsigned __int16 *
0x18000ea23  mov     [rsp+50h+var_30], r15d; unsigned int
0x18000ea28  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000ea2d  mov     ebx, eax
0x18000ea2f  test    eax, eax
0x18000ea31  jns     short loc_18000EA38
0x18000ea33  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ea38  test    byte ptr [rdi+124h], 40h
0x18000ea3f  jz      short loc_18000EA88
0x18000ea41  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000ea45  lea     rax, aAneNego; "AnE-Nego"
0x18000ea4c  mov     rcx, [rbp+pszDest]; pszDest
0x18000ea50  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000ea54  mov     [rsp+50h+var_10], r12
0x18000ea59  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18000ea5d  mov     [rsp+50h+var_18], rax
0x18000ea62  lea     rax, aSecurity2; "Security2="
0x18000ea69  mov     [rsp+50h+var_20], rax
0x18000ea6e  mov     [rsp+50h+var_28], r13; unsigned __int16 *
0x18000ea73  mov     [rsp+50h+var_30], r15d; unsigned int
0x18000ea78  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000ea7d  mov     ebx, eax
0x18000ea7f  test    eax, eax
0x18000ea81  jns     short loc_18000EA88
0x18000ea83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ea88  test    byte ptr [rdi+124h], 20h
0x18000ea8f  jz      short loc_18000EAD8
0x18000ea91  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000ea95  lea     rax, aAnNoencap; "An-NoEncap"
0x18000ea9c  mov     rcx, [rbp+pszDest]; pszDest
0x18000eaa0  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000eaa4  mov     [rsp+50h+var_10], r12
0x18000eaa9  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18000eaad  mov     [rsp+50h+var_18], rax
0x18000eab2  lea     rax, aSecurity29; "Security2_9="
0x18000eab9  mov     [rsp+50h+var_20], rax
0x18000eabe  mov     [rsp+50h+var_28], r13; unsigned __int16 *
0x18000eac3  mov     [rsp+50h+var_30], r15d; unsigned int
0x18000eac8  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000eacd  mov     ebx, eax
0x18000eacf  test    eax, eax
0x18000ead1  jns     short loc_18000EAD8
0x18000ead3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ead8  mov     eax, 200h
0x18000eadd  test    [rdi+124h], ax
0x18000eae4  jz      short loc_18000EB2D
0x18000eae6  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000eaea  lea     rax, String2; "TRUE"
0x18000eaf1  mov     rcx, [rbp+pszDest]; pszDest
0x18000eaf5  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000eaf9  mov     [rsp+50h+var_10], r12
0x18000eafe  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18000eb02  mov     [rsp+50h+var_18], rax
0x18000eb07  lea     rax, aAuthbypassout; "AuthByPassOut="
0x18000eb0e  mov     [rsp+50h+var_20], rax
0x18000eb13  mov     [rsp+50h+var_28], r13; unsigned __int16 *
0x18000eb18  mov     [rsp+50h+var_30], r15d; unsigned int
0x18000eb1d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000eb22  mov     ebx, eax
0x18000eb24  test    eax, eax
0x18000eb26  jns     short loc_18000EB2D
0x18000eb28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000eb2d  mov     rax, [rbp+pszDest]
0x18000eb31  mov     [r14], rax
0x18000eb34  mov     rax, [rbp+arg_8]
0x18000eb38  mov     [rsi], rax
0x18000eb3b  mov     eax, ebx
0x18000eb3d  mov     rbx, [rsp+50h+arg_10]
0x18000eb45  add     rsp, 50h
0x18000eb49  pop     r15
0x18000eb4b  pop     r14
0x18000eb4d  pop     r13
0x18000eb4f  pop     r12
0x18000eb51  pop     rdi
0x18000eb52  pop     rsi
0x18000eb53  pop     rbp
0x18000eb54  retn
```
