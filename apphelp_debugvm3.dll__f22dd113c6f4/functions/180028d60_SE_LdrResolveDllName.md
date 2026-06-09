# SE_LdrResolveDllName

- ea: `0x180028d60`
- end: `0x180029052`
- name: `SE_LdrResolveDllName`
- size: `754`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f114`
- `0x1800280f0`
- `0x180028d60`
- `0x18002d634`
- `0x180039a5a`
- `0x180039a66`
- `0x180039a72`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x180028f75`
- `ntdll!RtlCreateUnicodeString` at `0x180029038`
- `ntdll!RtlCreateUnicodeString` at `0x180028f75`
- `ntdll!RtlCreateUnicodeString` at `0x180029038`
- `ntdll!RtlDoesFileExists_U` at `0x18002901a`
- `ntdll!RtlDoesFileExists_U` at `0x18002901a`
- `ntdll!RtlFreeUnicodeString` at `0x180028de4`
- `ntdll!RtlFreeUnicodeString` at `0x180028de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f40`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028f36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028f36`

## string_xrefs

- `0x180028df9`: `SE_LdrResolveDllName`
- `0x180028e80`: `SE_LdrResolveDllName`
- `0x180028f53`: `SE_LdrResolveDllName`
- `0x180028f7b`: `SE_LdrResolveDllName`
- `0x18002903e`: `SE_LdrResolveDllName`
- `0x180028e64`: `Failed to construct system root path`
- `0x180028e89`: `Failed to create output buffer`
- `0x180028f86`: `Failed to create output buffer`
- `0x180028f46`: `Failed to expand replacement name [%d]`
- `0x180028fe0`: `system32`
- `0x180028e73`: `Failed to construct system32 path`

## pseudocode

```c
void __fastcall SE_LdrResolveDllName(PUNICODE_STRING DestinationString, bool *a2, __int64 a3)
{
  _WORD *v6; // rax
  const char *v7; // r9
  __int64 v8; // r8
  size_t v9; // r8
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  __int64 i; // rsi
  DWORD LastError; // eax
  __int64 v14; // r8
  BOOLEAN DoesFileExists_U; // al
  wchar_t pszDest[32]; // [rsp+30h] [rbp-298h] BYREF
  WCHAR Dst[264]; // [rsp+70h] [rbp-258h] BYREF

  if ( DestinationString && a2 )
  {
    *a2 = 0;
    *DestinationString = 0;
    Dst[0] = 0;
    pszDest[0] = 0;
    if ( NtCurrentPeb()->ProcessParameters )
    {
      if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x200000) != 0 )
      {
        if ( a3 )
        {
          v6 = *(_WORD **)(a3 + 8);
          if ( v6 )
          {
            if ( *v6 )
            {
              if ( StringCchPrintfW(pszDest, 0x20u, L"%s\\", 2147352624) >= 0 )
              {
                v9 = -1;
                do
                  ++v9;
                while ( pszDest[v9] );
                if ( wcsnicmp_0(*(const wchar_t **)(a3 + 8), pszDest, v9) )
                {
                  v10 = wcsrchr_0(*(const wchar_t **)(a3 + 8), 0x5Cu);
                  v11 = v10 ? v10 + 1 : *(wchar_t **)(a3 + 8);
                  if ( *v11 )
                  {
                    for ( i = 0; !i; i = 1 )
                    {
                      if ( !wcsicmp_0(v11, L"wmvcore2.dll") )
                      {
                        if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\wmvcore.dll", Dst, 0x104u) )
                        {
                          LastError = GetLastError();
                          AslLogCallPrintf(
                            1,
                            "SE_LdrResolveDllName",
                            4159,
                            "Failed to expand replacement name [%d]",
                            LastError);
                          goto LABEL_5;
                        }
                        if ( !RtlCreateUnicodeString(DestinationString, Dst) )
                        {
                          AslLogCallPrintf(1, "SE_LdrResolveDllName", 4165, "Failed to create output buffer");
                          goto LABEL_5;
                        }
                        *a2 = 1;
                        v14 = 4171;
                        goto LABEL_35;
                      }
                    }
                    if ( (unsigned int)CompatCachepLookupCdb(v11) )
                    {
                      if ( StringCchPrintfW(
                             Dst,
                             0x104u,
                             L"%s\\%s\\%s",
                             2147352624,
                             L"system32",
                             v11,
                             *(_QWORD *)pszDest) < 0 )
                      {
                        v7 = "Failed to construct system32 path";
                        v8 = 4194;
                        goto LABEL_17;
                      }
                      DoesFileExists_U = RtlDoesFileExists_U(Dst);
                      *a2 = DoesFileExists_U != 0;
                      if ( DoesFileExists_U )
                      {
                        if ( RtlCreateUnicodeString(DestinationString, Dst) )
                        {
                          v14 = 4262;
LABEL_35:
                          AslLogCallPrintf(
                            3,
                            "SE_LdrResolveDllName",
                            v14,
                            "Resolved %S -> %S",
                            v11,
                            DestinationString->Buffer);
                          goto LABEL_5;
                        }
                        AslLogCallPrintf(1, "SE_LdrResolveDllName", 4258, "Failed to create output buffer");
                      }
                    }
                  }
                }
              }
              else
              {
                v7 = "Failed to construct system root path";
                v8 = 4126;
LABEL_17:
                AslLogCallPrintf(1, "SE_LdrResolveDllName", v8, v7);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    AslLogCallPrintf(1, "SE_LdrResolveDllName", 4080, "Invalid parameter");
    if ( !a2 )
      return;
  }
LABEL_5:
  if ( !*a2 && DestinationString )
  {
    if ( DestinationString->Buffer )
      RtlFreeUnicodeString(DestinationString);
  }
}

```

## disassembly

```asm
0x180028d60  push    rbx
0x180028d62  push    rbp
0x180028d63  push    rsi
0x180028d64  push    rdi
0x180028d65  push    r12
0x180028d67  push    r14
0x180028d69  push    r15
0x180028d6b  sub     rsp, 290h
0x180028d72  mov     rax, cs:__security_cookie
0x180028d79  xor     rax, rsp
0x180028d7c  mov     [rsp+2C8h+var_48], rax
0x180028d84  xor     ebp, ebp
0x180028d86  mov     rsi, r8
0x180028d89  mov     r14, rdx
0x180028d8c  mov     rdi, rcx
0x180028d8f  test    rcx, rcx
0x180028d92  jz      short loc_180028DEC
0x180028d94  test    rdx, rdx
0x180028d97  jz      short loc_180028DEC
0x180028d99  mov     [rdx], bpl
0x180028d9c  xorps   xmm0, xmm0
0x180028d9f  movups  xmmword ptr [rcx], xmm0
0x180028da2  mov     [rsp+2C8h+Dst], bp
0x180028da7  mov     [rsp+2C8h+pszDest], bp
0x180028dac  mov     rax, gs:60h
0x180028db5  cmp     [rax+20h], rbp
0x180028db9  jz      short loc_180028DD1
0x180028dbb  mov     rax, gs:60h
0x180028dc4  mov     rcx, [rax+20h]
0x180028dc8  test    dword ptr [rcx+8], 200000h
0x180028dcf  jnz     short loc_180028E31
0x180028dd1  cmp     [r14], bpl
0x180028dd4  jnz     short loc_180028E0F
0x180028dd6  test    rdi, rdi
0x180028dd9  jz      short loc_180028E0F
0x180028ddb  cmp     [rdi+8], rbp
0x180028ddf  jz      short loc_180028E0F
0x180028de1  mov     rcx, rdi; UnicodeString
0x180028de4  call    cs:__imp_RtlFreeUnicodeString
0x180028dea  jmp     short loc_180028E0F
0x180028dec  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x180028df3  mov     r8d, 0FF0h
0x180028df9  lea     rdx, aSeLdrresolvedl_0; "SE_LdrResolveDllName"
0x180028e00  mov     ecx, 1
0x180028e05  call    AslLogCallPrintf
0x180028e0a  test    r14, r14
0x180028e0d  jnz     short loc_180028DD1
0x180028e0f  mov     rcx, [rsp+2C8h+var_48]
0x180028e17  xor     rcx, rsp; StackCookie
0x180028e1a  call    __security_check_cookie
0x180028e1f  add     rsp, 290h
0x180028e26  pop     r15
0x180028e28  pop     r14
0x180028e2a  pop     r12
0x180028e2c  pop     rdi
0x180028e2d  pop     rsi
0x180028e2e  pop     rbp
0x180028e2f  pop     rbx
0x180028e30  retn
0x180028e31  test    rsi, rsi
0x180028e34  jz      short loc_180028DD1
0x180028e36  mov     rax, [r8+8]
0x180028e3a  test    rax, rax
0x180028e3d  jz      short loc_180028DD1
0x180028e3f  cmp     [rax], bp
0x180028e42  jz      short loc_180028DD1
0x180028e44  mov     r9d, 7FFE0030h
0x180028e4a  lea     r8, aS_0; "%s\\"
0x180028e51  mov     edx, 20h ; ' '; cchDest
0x180028e56  lea     rcx, [rsp+2C8h+pszDest]; pszDest
0x180028e5b  call    StringCchPrintfW
0x180028e60  test    eax, eax
0x180028e62  jns     short loc_180028EA5
0x180028e64  lea     r9, aFailedToConstr_1; "Failed to construct system root path"
0x180028e6b  mov     r8d, 101Eh
0x180028e71  jmp     short loc_180028E80
0x180028e73  lea     r9, aFailedToConstr_0; "Failed to construct system32 path"
0x180028e7a  mov     r8d, 1062h
0x180028e80  lea     rdx, aSeLdrresolvedl_0; "SE_LdrResolveDllName"
0x180028e87  jmp     short loc_180028E96
0x180028e89  lea     r9, aFailedToCreate_29; "Failed to create output buffer"
0x180028e90  mov     r8d, 10A2h
0x180028e96  mov     ecx, 1
0x180028e9b  call    AslLogCallPrintf
0x180028ea0  jmp     loc_180028DD1
0x180028ea5  lea     rax, [rsp+2C8h+pszDest]
0x180028eaa  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028eae  inc     r8; MaxCount
0x180028eb1  cmp     [rax+r8*2], bp
0x180028eb6  jnz     short loc_180028EAE
0x180028eb8  mov     rcx, [rsi+8]; String1
0x180028ebc  lea     rdx, [rsp+2C8h+pszDest]; String2
0x180028ec1  call    _wcsnicmp_0
0x180028ec6  test    eax, eax
0x180028ec8  jz      loc_180028DD1
0x180028ece  mov     rcx, [rsi+8]; Str
0x180028ed2  mov     edx, 5Ch ; '\'; Ch
0x180028ed7  call    wcsrchr_0
0x180028edc  mov     rbx, rax
0x180028edf  test    rax, rax
0x180028ee2  jnz     short loc_180028EEA
0x180028ee4  mov     rbx, [rsi+8]
0x180028ee8  jmp     short loc_180028EEE
0x180028eea  add     rbx, 2
0x180028eee  cmp     [rbx], bp
0x180028ef1  jz      loc_180028DD1
0x180028ef7  mov     rsi, rbp
0x180028efa  lea     r12, off_18005BE80; "wmvcore2.dll"
0x180028f01  mov     rcx, rbx; Str
0x180028f04  cmp     rsi, 1
0x180028f08  jnb     loc_180028FCE
0x180028f0e  mov     r15, rsi
0x180028f11  add     r15, r15
0x180028f14  mov     rdx, [r12+r15*8]; String2
0x180028f18  call    _wcsicmp_0
0x180028f1d  test    eax, eax
0x180028f1f  jz      short loc_180028F26
0x180028f21  inc     rsi
0x180028f24  jmp     short loc_180028F01
0x180028f26  mov     rcx, [r12+r15*8+8]; lpSrc
0x180028f2b  lea     rdx, [rsp+2C8h+Dst]; lpDst
0x180028f30  mov     r8d, 104h; nSize
0x180028f36  call    cs:__imp_ExpandEnvironmentStringsW
0x180028f3c  test    eax, eax
0x180028f3e  jnz     short loc_180028F6D
0x180028f40  call    cs:__imp_GetLastError
0x180028f46  lea     r9, aFailedToExpand_1; "Failed to expand replacement name [%d]"
0x180028f4d  mov     r8d, 103Fh
0x180028f53  lea     rdx, aSeLdrresolvedl_0; "SE_LdrResolveDllName"
0x180028f5a  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x180028f5e  mov     ecx, 1
0x180028f63  call    AslLogCallPrintf
0x180028f68  jmp     loc_180028DD1
0x180028f6d  lea     rdx, [rsp+2C8h+Dst]; SourceString
0x180028f72  mov     rcx, rdi; DestinationString
0x180028f75  call    cs:__imp_RtlCreateUnicodeString
0x180028f7b  lea     rdx, aSeLdrresolvedl_0; "SE_LdrResolveDllName"
0x180028f82  test    al, al
0x180028f84  jnz     short loc_180028F98
0x180028f86  lea     r9, aFailedToCreate_29; "Failed to create output buffer"
0x180028f8d  mov     r8d, 1045h
0x180028f93  jmp     loc_180028E96
0x180028f98  mov     byte ptr [r14], 1
0x180028f9c  mov     r8d, 104Bh
0x180028fa2  jmp     short loc_180028FAA
0x180028fa4  mov     r8d, 10A6h
0x180028faa  mov     rax, [rdi+8]
0x180028fae  lea     r9, aResolvedSS; "Resolved %S -> %S"
0x180028fb5  mov     [rsp+2C8h+var_2A0], rax
0x180028fba  mov     ecx, 3
0x180028fbf  mov     [rsp+2C8h+var_2A8], rbx
0x180028fc4  call    AslLogCallPrintf
0x180028fc9  jmp     loc_180028DD1
0x180028fce  mov     edx, 80h
0x180028fd3  call    CompatCachepLookupCdb
0x180028fd8  test    eax, eax
0x180028fda  jz      loc_180028DD1
0x180028fe0  lea     rax, aSystem32_2; "system32"
0x180028fe7  mov     [rsp+2C8h+var_2A0], rbx
0x180028fec  mov     r9d, 7FFE0030h
0x180028ff2  mov     [rsp+2C8h+var_2A8], rax
0x180028ff7  lea     r8, aSSS; "%s\\%s\\%s"
0x180028ffe  mov     edx, 104h; cchDest
0x180029003  lea     rcx, [rsp+2C8h+Dst]; pszDest
0x180029008  call    StringCchPrintfW
0x18002900d  test    eax, eax
0x18002900f  js      loc_180028E73
0x180029015  lea     rcx, [rsp+2C8h+Dst]; FileName
0x18002901a  call    cs:__imp_RtlDoesFileExists_U
0x180029020  test    al, al
0x180029022  setnz   cl
0x180029025  mov     [r14], cl
0x180029028  test    al, al
0x18002902a  jz      loc_180028DD1
0x180029030  lea     rdx, [rsp+2C8h+Dst]; SourceString
0x180029035  mov     rcx, rdi; DestinationString
0x180029038  call    cs:__imp_RtlCreateUnicodeString
0x18002903e  lea     rdx, aSeLdrresolvedl_0; "SE_LdrResolveDllName"
0x180029045  test    al, al
0x180029047  jnz     loc_180028FA4
0x18002904d  jmp     loc_180028E89
```
