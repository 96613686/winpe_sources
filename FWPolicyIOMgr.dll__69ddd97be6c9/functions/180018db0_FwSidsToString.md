# FwSidsToString

- ea: `0x180018db0`
- end: `0x180018fec`
- name: `FwSidsToString`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042c4`
- `0x180018db0`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018fa9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018e15`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018ee3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018e15`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018ee3`
- `fwbase!FwFree` at `0x180018f29`
- `fwbase!FwFree` at `0x180018fbf`
- `fwbase!FwFree` at `0x180018f29`
- `fwbase!FwFree` at `0x180018fbf`
- `fwbase!FwStringCopy` at `0x180018e7a`
- `fwbase!FwStringCopy` at `0x180018e7a`
- `fwbase!FwStringBuild` at `0x180018f08`
- `fwbase!FwStringBuild` at `0x180018f08`

## pseudocode

```c
__int64 __fastcall FwSidsToString(unsigned int a1, PSID *a2, _QWORD *a3)
{
  signed int v3; // ebx
  __int64 v7; // rdi
  signed int LastError; // eax
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  unsigned int i; // esi
  signed int v12; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF

  v3 = 0;
  v15 = 0;
  StringSid = 0;
  if ( !a1 )
  {
    if ( !a2 )
      goto LABEL_19;
    goto LABEL_5;
  }
  if ( !a2 )
LABEL_5:
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a1 )
    goto LABEL_19;
  v7 = 0;
  if ( !ConvertSidToStringSidW(*a2, &StringSid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 163;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v3);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  v3 = FwStringCopy(StringSid, &v15);
  if ( v3 >= 0 )
  {
    LocalFree(StringSid);
    StringSid = 0;
LABEL_19:
    for ( i = 1; ; ++i )
    {
      if ( i >= a1 )
      {
        v7 = 0;
        *a3 = v15;
        v15 = 0;
        goto LABEL_33;
      }
      v7 = v15;
      v15 = 0;
      if ( !ConvertSidToStringSidW(a2[2 * i], &StringSid) )
        break;
      v3 = FwStringBuild(&v15, v7, &WF_ADDR_TOKEN_DELIMITER_STR, StringSid);
      if ( v3 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 166;
          goto LABEL_13;
        }
        goto LABEL_33;
      }
      LocalFree(StringSid);
      StringSid = 0;
      FwFree(v7);
    }
    v12 = GetLastError();
    v3 = v12;
    if ( v12 > 0 )
      v3 = (unsigned __int16)v12 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 165;
      goto LABEL_13;
    }
    goto LABEL_33;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v10 = 164;
    goto LABEL_13;
  }
LABEL_33:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v7 )
    FwFree(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018db0  mov     [rsp-28h+arg_0], rbx
0x180018db5  mov     [rsp-28h+arg_18], rsi
0x180018dba  push    rbp
0x180018dbb  push    rdi
0x180018dbc  push    r12
0x180018dbe  push    r14
0x180018dc0  push    r15
0x180018dc2  mov     rbp, rsp
0x180018dc5  sub     rsp, 50h
0x180018dc9  mov     rax, cs:__security_cookie
0x180018dd0  xor     rax, rsp
0x180018dd3  mov     [rbp+var_10], rax
0x180018dd7  xor     ebx, ebx
0x180018dd9  mov     r12, r8
0x180018ddc  mov     [rbp+var_18], rbx
0x180018de0  mov     r14, rdx
0x180018de3  mov     [rbp+StringSid], rbx
0x180018de7  mov     r15d, ecx
0x180018dea  test    ecx, ecx
0x180018dec  jz      short loc_180018DF5
0x180018dee  test    rdx, rdx
0x180018df1  jz      short loc_180018DFE
0x180018df3  jmp     short loc_180018E03
0x180018df5  test    r14, r14
0x180018df8  jz      loc_180018EBC
0x180018dfe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018e03  test    r15d, r15d
0x180018e06  jz      loc_180018EBC
0x180018e0c  mov     rcx, [r14]; Sid
0x180018e0f  lea     rdx, [rbp+StringSid]; StringSid
0x180018e13  xor     edi, edi
0x180018e15  call    cs:__imp_ConvertSidToStringSidW
0x180018e1b  test    eax, eax
0x180018e1d  jnz     short loc_180018E72
0x180018e1f  call    cs:__imp_GetLastError
0x180018e25  mov     ebx, eax
0x180018e27  test    eax, eax
0x180018e29  jle     short loc_180018E34
0x180018e2b  movzx   ebx, ax
0x180018e2e  or      ebx, 80070000h
0x180018e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e3b  lea     rax, WPP_GLOBAL_Control
0x180018e42  cmp     rcx, rax
0x180018e45  jz      loc_180018FA0
0x180018e4b  test    byte ptr [rcx+1Ch], 1
0x180018e4f  jz      loc_180018FA0
0x180018e55  mov     edx, 0A3h
0x180018e5a  mov     rcx, [rcx+10h]
0x180018e5e  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180018e65  mov     r9d, ebx
0x180018e68  call    WPP_SF_d
0x180018e6d  jmp     loc_180018FA0
0x180018e72  mov     rcx, [rbp+StringSid]
0x180018e76  lea     rdx, [rbp+var_18]
0x180018e7a  call    cs:__imp_FwStringCopy
0x180018e80  mov     ebx, eax
0x180018e82  test    eax, eax
0x180018e84  jns     short loc_180018EAE
0x180018e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e8d  lea     rax, WPP_GLOBAL_Control
0x180018e94  cmp     rcx, rax
0x180018e97  jz      loc_180018FA0
0x180018e9d  test    byte ptr [rcx+1Ch], 1
0x180018ea1  jz      loc_180018FA0
0x180018ea7  mov     edx, 0A4h
0x180018eac  jmp     short loc_180018E5A
0x180018eae  mov     rcx, [rbp+StringSid]; hMem
0x180018eb2  call    cs:__imp_LocalFree
0x180018eb8  mov     [rbp+StringSid], rdi
0x180018ebc  mov     esi, 1
0x180018ec1  cmp     esi, r15d
0x180018ec4  jnb     loc_180018F8E
0x180018eca  mov     rdi, [rbp+var_18]
0x180018ece  lea     rdx, [rbp+StringSid]; StringSid
0x180018ed2  mov     ecx, esi
0x180018ed4  add     rcx, rcx
0x180018ed7  mov     [rbp+var_18], 0
0x180018edf  mov     rcx, [r14+rcx*8]; Sid
0x180018ee3  call    cs:__imp_ConvertSidToStringSidW
0x180018ee9  test    eax, eax
0x180018eeb  jz      short loc_180018F56
0x180018eed  mov     r9, [rbp+StringSid]
0x180018ef1  lea     r8, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; ushort const near * const WF_ADDR_TOKEN_DELIMITER_STR
0x180018ef8  mov     rdx, rdi
0x180018efb  mov     [rsp+50h+var_30], 0
0x180018f04  lea     rcx, [rbp+var_18]
0x180018f08  call    cs:__imp_FwStringBuild
0x180018f0e  mov     ebx, eax
0x180018f10  test    eax, eax
0x180018f12  js      short loc_180018F33
0x180018f14  mov     rcx, [rbp+StringSid]; hMem
0x180018f18  call    cs:__imp_LocalFree
0x180018f1e  mov     rcx, rdi
0x180018f21  mov     [rbp+StringSid], 0
0x180018f29  call    cs:__imp_FwFree
0x180018f2f  inc     esi
0x180018f31  jmp     short loc_180018EC1
0x180018f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f3a  lea     rax, WPP_GLOBAL_Control
0x180018f41  cmp     rcx, rax
0x180018f44  jz      short loc_180018FA0
0x180018f46  test    byte ptr [rcx+1Ch], 1
0x180018f4a  jz      short loc_180018FA0
0x180018f4c  mov     edx, 0A6h
0x180018f51  jmp     loc_180018E5A
0x180018f56  call    cs:__imp_GetLastError
0x180018f5c  mov     ebx, eax
0x180018f5e  test    eax, eax
0x180018f60  jle     short loc_180018F6B
0x180018f62  movzx   ebx, ax
0x180018f65  or      ebx, 80070000h
0x180018f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f72  lea     rax, WPP_GLOBAL_Control
0x180018f79  cmp     rcx, rax
0x180018f7c  jz      short loc_180018FA0
0x180018f7e  test    byte ptr [rcx+1Ch], 1
0x180018f82  jz      short loc_180018FA0
0x180018f84  mov     edx, 0A5h
0x180018f89  jmp     loc_180018E5A
0x180018f8e  mov     rax, [rbp+var_18]
0x180018f92  xor     edi, edi
0x180018f94  mov     [r12], rax
0x180018f98  mov     [rbp+var_18], 0
0x180018fa0  mov     rcx, [rbp+StringSid]; hMem
0x180018fa4  test    rcx, rcx
0x180018fa7  jz      short loc_180018FB7
0x180018fa9  call    cs:__imp_LocalFree
0x180018faf  mov     [rbp+StringSid], 0
0x180018fb7  test    rdi, rdi
0x180018fba  jz      short loc_180018FC5
0x180018fbc  mov     rcx, rdi
0x180018fbf  call    cs:__imp_FwFree
0x180018fc5  mov     eax, ebx
0x180018fc7  mov     rcx, [rbp+var_10]
0x180018fcb  xor     rcx, rsp; StackCookie
0x180018fce  call    __security_check_cookie
0x180018fd3  lea     r11, [rsp+50h+var_s0]
0x180018fd8  mov     rbx, [r11+30h]
0x180018fdc  mov     rsi, [r11+48h]
0x180018fe0  mov     rsp, r11
0x180018fe3  pop     r15
0x180018fe5  pop     r14
0x180018fe7  pop     r12
0x180018fe9  pop     rdi
0x180018fea  pop     rbp
0x180018feb  retn
```
