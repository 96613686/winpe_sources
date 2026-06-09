# GetTokenUserSid

- ea: `0x180010304`
- end: `0x1800104ee`
- name: `GetTokenUserSid`
- size: `490`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010500`

## callees

- `0x180001630`
- `0x180010304`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010477`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001046d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001046d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001034b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800103e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001034b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800103e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010437`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010437`

## string_xrefs

- `0x18001037b`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x1800103b6`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x1800103fc`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x180010483`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall GetTokenUserSid(HANDLE TokenHandle, _QWORD *a2)
{
  signed int v4; // eax
  DWORD LastError; // ebx
  PSID *v6; // rdi
  unsigned int v7; // r9d
  const char *v8; // rdx
  unsigned int v9; // ecx
  DWORD v10; // eax
  signed int v11; // eax
  DWORD LengthSid; // ebx
  void *v13; // rax
  void *v14; // rsi
  DWORD TokenInformationLength[4]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE TokenInformation[256]; // [rsp+40h] [rbp-128h] BYREF

  TokenInformationLength[0] = 256;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, TokenInformationLength) )
  {
    v6 = (PSID *)TokenInformation;
LABEL_14:
    LengthSid = GetLengthSid(*v6);
    v13 = SIDKeyProvAlloc(LengthSid);
    v14 = v13;
    if ( v13 )
    {
      if ( CopySid(LengthSid, v13, *v6) )
      {
        *a2 = v14;
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        SidKeyDebugTraceError(
          LastError,
          "dwReturn",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
          0xE7u);
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        SIDKeyProvFree(v14);
      }
      goto LABEL_21;
    }
    v7 = 224;
    v8 = "hr";
    v9 = -2147024882;
    goto LABEL_9;
  }
  v4 = GetLastError();
  if ( v4 > 0 )
    LastError = (unsigned __int16)v4 | 0x80070000;
  else
    LastError = v4;
  if ( v4 != 122 )
  {
    SidKeyDebugTraceError(v4, "dwReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0xBCu);
    return LastError;
  }
  v6 = (PSID *)SIDKeyProvAlloc(TokenInformationLength[0]);
  if ( v6 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength[0], TokenInformationLength) )
    {
      v10 = GetLastError();
      SidKeyDebugTraceError(v10, "dwReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0xD4u);
      v11 = GetLastError();
      LastError = v11;
      if ( v11 > 0 )
        LastError = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_21;
    }
    goto LABEL_14;
  }
  v7 = 199;
  v8 = "dwReturn";
  v9 = 122;
LABEL_9:
  LastError = -2147024882;
  SidKeyDebugTraceError(v9, v8, "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v7);
LABEL_21:
  if ( v6 != (PSID *)TokenInformation )
    SIDKeyProvFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x180010304  mov     [rsp+arg_10], rbx
0x180010309  push    rsi
0x18001030a  push    rdi
0x18001030b  push    r14
0x18001030d  sub     rsp, 150h
0x180010314  mov     rax, cs:__security_cookie
0x18001031b  xor     rax, rsp
0x18001031e  mov     [rsp+168h+var_28], rax
0x180010326  mov     r14, rdx
0x180010329  lea     rax, [rsp+168h+TokenInformationLength]
0x18001032e  mov     r9d, 100h; TokenInformationLength
0x180010334  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x180010339  mov     edx, 1; TokenInformationClass
0x18001033e  mov     [rsp+168h+TokenInformationLength], r9d
0x180010343  lea     r8, [rsp+168h+TokenInformation]; TokenInformation
0x180010348  mov     rsi, rcx
0x18001034b  call    cs:__imp_GetTokenInformation
0x180010351  test    eax, eax
0x180010353  jnz     loc_18001042F
0x180010359  call    cs:__imp_GetLastError
0x18001035f  test    eax, eax
0x180010361  jg      short loc_180010367
0x180010363  mov     ebx, eax
0x180010365  jmp     short loc_180010370
0x180010367  movzx   ebx, ax
0x18001036a  or      ebx, 80070000h
0x180010370  cmp     eax, 7Ah ; 'z'
0x180010373  jz      short loc_180010395
0x180010375  mov     r9d, 0BCh; unsigned int
0x18001037b  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010382  lea     rdx, aDwreturn; "dwReturn"
0x180010389  mov     ecx, eax; unsigned int
0x18001038b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010390  jmp     loc_1800104C8
0x180010395  mov     ecx, [rsp+168h+TokenInformationLength]; unsigned __int64
0x180010399  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18001039e  mov     rdi, rax
0x1800103a1  test    rax, rax
0x1800103a4  jnz     short loc_1800103CC
0x1800103a6  mov     r9d, 0C7h; unsigned int
0x1800103ac  lea     rdx, aDwreturn; "dwReturn"
0x1800103b3  lea     ecx, [rax+7Ah]; unsigned int
0x1800103b6  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800103bd  mov     ebx, 8007000Eh
0x1800103c2  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800103c7  jmp     loc_1800104B6
0x1800103cc  mov     r9d, [rsp+168h+TokenInformationLength]; TokenInformationLength
0x1800103d1  lea     rax, [rsp+168h+TokenInformationLength]
0x1800103d6  mov     r8, rdi; TokenInformation
0x1800103d9  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x1800103de  mov     edx, 1; TokenInformationClass
0x1800103e3  mov     rcx, rsi; TokenHandle
0x1800103e6  call    cs:__imp_GetTokenInformation
0x1800103ec  test    eax, eax
0x1800103ee  jnz     short loc_180010434
0x1800103f0  call    cs:__imp_GetLastError
0x1800103f6  mov     r9d, 0D4h; unsigned int
0x1800103fc  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010403  mov     ecx, eax; unsigned int
0x180010405  lea     rdx, aDwreturn; "dwReturn"
0x18001040c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010411  call    cs:__imp_GetLastError
0x180010417  mov     ebx, eax
0x180010419  test    eax, eax
0x18001041b  jle     loc_1800104B6
0x180010421  movzx   ebx, ax
0x180010424  or      ebx, 80070000h
0x18001042a  jmp     loc_1800104B6
0x18001042f  lea     rdi, [rsp+168h+TokenInformation]
0x180010434  mov     rcx, [rdi]; pSid
0x180010437  call    cs:__imp_GetLengthSid
0x18001043d  mov     ecx, eax; unsigned __int64
0x18001043f  mov     ebx, eax
0x180010441  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180010446  mov     rsi, rax
0x180010449  test    rax, rax
0x18001044c  jnz     short loc_180010465
0x18001044e  mov     r9d, 0E0h
0x180010454  lea     rdx, aHr; "hr"
0x18001045b  mov     ecx, 8007000Eh
0x180010460  jmp     loc_1800103B6
0x180010465  mov     r8, [rdi]; pSourceSid
0x180010468  mov     rdx, rsi; pDestinationSid
0x18001046b  mov     ecx, ebx; nDestinationSidLength
0x18001046d  call    cs:__imp_CopySid
0x180010473  test    eax, eax
0x180010475  jnz     short loc_1800104B1
0x180010477  call    cs:__imp_GetLastError
0x18001047d  mov     r9d, 0E7h; unsigned int
0x180010483  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001048a  mov     ecx, eax; unsigned int
0x18001048c  lea     rdx, aDwreturn; "dwReturn"
0x180010493  mov     ebx, eax
0x180010495  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001049a  test    ebx, ebx
0x18001049c  jle     short loc_1800104A7
0x18001049e  movzx   ebx, bx
0x1800104a1  or      ebx, 80070000h
0x1800104a7  mov     rcx, rsi; lpMem
0x1800104aa  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800104af  jmp     short loc_1800104B6
0x1800104b1  mov     [r14], rsi
0x1800104b4  xor     ebx, ebx
0x1800104b6  lea     rax, [rsp+168h+TokenInformation]
0x1800104bb  cmp     rdi, rax
0x1800104be  jz      short loc_1800104C8
0x1800104c0  mov     rcx, rdi; lpMem
0x1800104c3  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800104c8  mov     eax, ebx
0x1800104ca  mov     rcx, [rsp+168h+var_28]
0x1800104d2  xor     rcx, rsp; StackCookie
0x1800104d5  call    __security_check_cookie
0x1800104da  mov     rbx, [rsp+168h+arg_10]
0x1800104e2  add     rsp, 150h
0x1800104e9  pop     r14
0x1800104eb  pop     rdi
0x1800104ec  pop     rsi
0x1800104ed  retn
```
