# DpspIsClientAdmin(void *,int *)

- ea: `0x1800122d4`
- end: `0x180012464`
- name: `?DpspIsClientAdmin@@YAJPEAXPEAH@Z`
- size: `400`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006eec`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x1800122d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001239f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001239f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012439`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800123f2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800123f2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001240d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001240d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012395`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012395`

## pseudocode

```c
__int64 __fastcall DpspIsClientAdmin(HANDLE TokenHandle, int *a2)
{
  int v4; // r8d
  signed int v5; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( TokenHandle )
  {
    if ( a2 )
    {
      *a2 = 0;
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
            (int)L"DpspIsClientAdmin",
            1319,
            (int)L"Error = %d",
            v5);
          goto LABEL_17;
        }
      }
      if ( !SidToCheck )
      {
        v5 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspIsClientAdmin",
          1320,
          (int)L"Error = %d",
          14);
        goto LABEL_17;
      }
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        v5 = 0;
      }
      else
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        if ( v5 < 0 )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
            (int)L"DpspIsClientAdmin",
            1326,
            (int)L"Error = %d",
            v5);
          goto LABEL_17;
        }
      }
      *a2 = IsMember;
      goto LABEL_17;
    }
    v4 = 1303;
  }
  else
  {
    v4 = 1302;
  }
  v5 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
    (int)L"DpspIsClientAdmin",
    v4,
    (int)L"Error = %d",
    87);
LABEL_17:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800122d4  mov     [rsp-18h+arg_10], rbx
0x1800122d9  mov     [rsp-18h+arg_18], rsi
0x1800122de  push    rbp
0x1800122df  push    rdi
0x1800122e0  push    r14
0x1800122e2  mov     rbp, rsp
0x1800122e5  sub     rsp, 80h
0x1800122ec  mov     rax, cs:__security_cookie
0x1800122f3  xor     rax, rsp
0x1800122f6  mov     [rbp+var_8], rax
0x1800122fa  xor     r14d, r14d
0x1800122fd  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180012303  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x180012307  mov     rdi, rdx
0x18001230a  mov     [rbp+SidToCheck], r14
0x18001230e  mov     rsi, rcx
0x180012311  mov     [rbp+IsMember], r14d
0x180012315  test    rcx, rcx
0x180012318  jnz     short loc_18001234C
0x18001231a  mov     r8d, 516h; int
0x180012320  mov     [rsp+80h+nSubAuthority2], 57h ; 'W'; Args
0x180012328  mov     ebx, 80070057h
0x18001232d  lea     r9, aErrorD; "Error = %d"
0x180012334  lea     rdx, aDpspisclientad; "DpspIsClientAdmin"
0x18001233b  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012342  call    WdipTraceError
0x180012347  jmp     loc_180012404
0x18001234c  test    rdi, rdi
0x18001234f  jnz     short loc_180012359
0x180012351  mov     r8d, 517h
0x180012357  jmp     short loc_180012320
0x180012359  lea     rax, [rbp+SidToCheck]
0x18001235d  mov     [rdx], r14d
0x180012360  mov     [rsp+80h+pSid], rax; pSid
0x180012365  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180012369  mov     [rsp+80h+nSubAuthority7], r14d; nSubAuthority7
0x18001236e  mov     r9d, 220h; nSubAuthority1
0x180012374  mov     [rsp+80h+nSubAuthority6], r14d; nSubAuthority6
0x180012379  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001237f  mov     [rsp+80h+nSubAuthority5], r14d; nSubAuthority5
0x180012384  mov     dl, 2; nSubAuthorityCount
0x180012386  mov     [rsp+80h+nSubAuthority4], r14d; nSubAuthority4
0x18001238b  mov     [rsp+80h+nSubAuthority3], r14d; nSubAuthority3
0x180012390  mov     [rsp+80h+nSubAuthority2], r14d; nSubAuthority2
0x180012395  call    cs:__imp_AllocateAndInitializeSid
0x18001239b  test    eax, eax
0x18001239d  jnz     short loc_1800123CA
0x18001239f  call    cs:__imp_GetLastError
0x1800123a5  mov     ebx, eax
0x1800123a7  test    eax, eax
0x1800123a9  jle     short loc_1800123B4
0x1800123ab  movzx   ebx, ax
0x1800123ae  or      ebx, 80070000h
0x1800123b4  test    ebx, ebx
0x1800123b6  jns     short loc_1800123CA
0x1800123b8  movzx   eax, bx
0x1800123bb  mov     r8d, 527h
0x1800123c1  mov     [rsp+80h+nSubAuthority2], eax
0x1800123c5  jmp     loc_18001232D
0x1800123ca  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800123ce  test    rdx, rdx
0x1800123d1  jnz     short loc_1800123EB
0x1800123d3  mov     ebx, 8007000Eh
0x1800123d8  mov     [rsp+80h+nSubAuthority2], 0Eh
0x1800123e0  mov     r8d, 528h
0x1800123e6  jmp     loc_18001232D
0x1800123eb  lea     r8, [rbp+IsMember]; IsMember
0x1800123ef  mov     rcx, rsi; TokenHandle
0x1800123f2  call    cs:__imp_CheckTokenMembership
0x1800123f8  test    eax, eax
0x1800123fa  jz      short loc_180012439
0x1800123fc  mov     ebx, r14d
0x1800123ff  mov     ecx, [rbp+IsMember]
0x180012402  mov     [rdi], ecx
0x180012404  mov     rcx, [rbp+SidToCheck]; pSid
0x180012408  test    rcx, rcx
0x18001240b  jz      short loc_180012413
0x18001240d  call    cs:__imp_FreeSid
0x180012413  mov     eax, ebx
0x180012415  mov     rcx, [rbp+var_8]
0x180012419  xor     rcx, rsp; StackCookie
0x18001241c  call    __security_check_cookie
0x180012421  lea     r11, [rsp+80h+var_s0]
0x180012429  mov     rbx, [r11+30h]
0x18001242d  mov     rsi, [r11+38h]
0x180012431  mov     rsp, r11
0x180012434  pop     r14
0x180012436  pop     rdi
0x180012437  pop     rbp
0x180012438  retn
0x180012439  call    cs:__imp_GetLastError
0x18001243f  mov     ebx, eax
0x180012441  test    eax, eax
0x180012443  jle     short loc_18001244E
0x180012445  movzx   ebx, ax
0x180012448  or      ebx, 80070000h
0x18001244e  test    ebx, ebx
0x180012450  jns     short loc_1800123FF
0x180012452  movzx   eax, bx
0x180012455  mov     r8d, 52Eh
0x18001245b  mov     [rsp+80h+nSubAuthority2], eax
0x18001245f  jmp     loc_18001232D
```
