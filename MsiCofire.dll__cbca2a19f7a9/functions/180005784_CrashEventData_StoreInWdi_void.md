# CrashEventData::StoreInWdi(void *)

- ea: `0x180005784`
- end: `0x180005956`
- name: `?StoreInWdi@CrashEventData@@QEAAJPEAX@Z`
- size: `466`
- prototype: `__int64 __fastcall(CrashEventData *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800038cc`

## callees

- `0x180002590`
- `0x180005784`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800058b0`
- `KERNEL32!GetLastError` at `0x1800058b0`
- `ADVAPI32!IsValidSid` at `0x1800058a6`
- `ADVAPI32!IsValidSid` at `0x1800058a6`
- `ADVAPI32!GetLengthSid` at `0x1800058d8`
- `ADVAPI32!GetLengthSid` at `0x1800058d8`
- `wdi!WdiAddParameter` at `0x1800057e4`
- `wdi!WdiAddParameter` at `0x180005828`
- `wdi!WdiAddParameter` at `0x18000585c`
- `wdi!WdiAddParameter` at `0x18000588b`
- `wdi!WdiAddParameter` at `0x1800058f2`
- `wdi!WdiAddParameter` at `0x18000591e`
- `wdi!WdiAddParameter` at `0x1800057e4`
- `wdi!WdiAddParameter` at `0x180005828`
- `wdi!WdiAddParameter` at `0x18000585c`
- `wdi!WdiAddParameter` at `0x18000588b`
- `wdi!WdiAddParameter` at `0x1800058f2`
- `wdi!WdiAddParameter` at `0x18000591e`

## string_xrefs

- `0x18000593d`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x1800057d8`: `CorruptedFilePath`
- `0x1800058de`: `UserSID`

## pseudocode

```c
__int64 __fastcall CrashEventData::StoreInWdi(CrashEventData *this, void *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r9
  int v9; // eax
  int v10; // r9d
  __int64 v11; // rax
  __int64 v12; // r9
  signed int LastError; // eax
  void *v14; // rbx
  DWORD LengthSid; // eax

  if ( !a2 )
  {
    v4 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::StoreInWdi", 128, -2147024809);
    return v4;
  }
  v5 = *(_QWORD *)this;
  v6 = -1;
  if ( v5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v5 + 2 * v7) );
    v8 = (unsigned int)(2 * v7);
  }
  else
  {
    v8 = 0;
  }
  v9 = WdiAddParameter(a2, 0, L"CorruptedFilePath", v8, v5);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 136;
    goto LABEL_28;
  }
  v11 = *((_QWORD *)this + 1);
  if ( v11 )
  {
    do
      ++v6;
    while ( *(_WORD *)(v11 + 2 * v6) );
    v12 = (unsigned int)(2 * v6);
  }
  else
  {
    v12 = 0;
  }
  v9 = WdiAddParameter(a2, 0, L"CrashedAppName", v12, *((_QWORD *)this + 1));
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 144;
    goto LABEL_28;
  }
  v9 = WdiAddParameter(a2, 0, L"ExceptionCode", 4, (char *)this + 16);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 152;
    goto LABEL_28;
  }
  v9 = WdiAddParameter(a2, 0, L"ExceptionStatusCode", 4, (char *)this + 20);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 160;
    goto LABEL_28;
  }
  if ( IsValidSid(*((PSID *)this + 3)) )
  {
    v14 = (void *)*((_QWORD *)this + 3);
    LengthSid = GetLengthSid(v14);
    v9 = WdiAddParameter(a2, 0, L"UserSID", LengthSid, v14);
    v4 = v9;
    if ( v9 >= 0 )
    {
      v9 = WdiAddParameter(a2, 0, L"SessionID", 4, (char *)this + 32);
      v4 = v9;
      if ( v9 >= 0 )
        return v4;
      v10 = 177;
    }
    else
    {
      v10 = 169;
    }
LABEL_28:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::StoreInWdi", v10, v9);
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "CrashEventData::StoreInWdi", 162, v4);
  return v4;
}

```

## disassembly

```asm
0x180005784  push    rbx
0x180005786  push    rbp
0x180005787  push    rsi
0x180005788  push    rdi
0x180005789  push    r14
0x18000578b  sub     rsp, 30h
0x18000578f  xor     r14d, r14d
0x180005792  mov     rbp, rdx
0x180005795  mov     rdi, rcx
0x180005798  test    rdx, rdx
0x18000579b  jnz     short loc_1800057B1
0x18000579d  mov     ebx, 80070057h
0x1800057a2  mov     r9d, 80h
0x1800057a8  mov     dword ptr [rsp+58h+var_38], ebx
0x1800057ac  jmp     loc_180005934
0x1800057b1  mov     rcx, [rcx]
0x1800057b4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800057b8  test    rcx, rcx
0x1800057bb  jz      short loc_1800057D0
0x1800057bd  mov     rax, rsi
0x1800057c0  inc     rax
0x1800057c3  cmp     [rcx+rax*2], r14w
0x1800057c8  jnz     short loc_1800057C0
0x1800057ca  lea     r9d, [rax+rax]
0x1800057ce  jmp     short loc_1800057D3
0x1800057d0  mov     r9d, r14d
0x1800057d3  mov     [rsp+58h+var_38], rcx
0x1800057d8  lea     r8, aCorruptedfilep; "CorruptedFilePath"
0x1800057df  mov     rcx, rbp
0x1800057e2  xor     edx, edx
0x1800057e4  call    cs:__imp_WdiAddParameter
0x1800057ea  mov     ebx, eax
0x1800057ec  test    eax, eax
0x1800057ee  jns     short loc_1800057FB
0x1800057f0  mov     r9d, 88h
0x1800057f6  jmp     loc_180005930
0x1800057fb  mov     rax, [rdi+8]
0x1800057ff  test    rax, rax
0x180005802  jz      short loc_180005814
0x180005804  inc     rsi
0x180005807  cmp     [rax+rsi*2], r14w
0x18000580c  jnz     short loc_180005804
0x18000580e  lea     r9d, [rsi+rsi]
0x180005812  jmp     short loc_180005817
0x180005814  mov     r9d, r14d
0x180005817  lea     r8, aCrashedappname; "CrashedAppName"
0x18000581e  mov     [rsp+58h+var_38], rax
0x180005823  xor     edx, edx
0x180005825  mov     rcx, rbp
0x180005828  call    cs:__imp_WdiAddParameter
0x18000582e  mov     ebx, eax
0x180005830  test    eax, eax
0x180005832  jns     short loc_18000583F
0x180005834  mov     r9d, 90h
0x18000583a  jmp     loc_180005930
0x18000583f  lea     rax, [rdi+10h]
0x180005843  mov     esi, 4
0x180005848  mov     r9d, esi
0x18000584b  mov     [rsp+58h+var_38], rax
0x180005850  lea     r8, aExceptioncode; "ExceptionCode"
0x180005857  xor     edx, edx
0x180005859  mov     rcx, rbp
0x18000585c  call    cs:__imp_WdiAddParameter
0x180005862  mov     ebx, eax
0x180005864  test    eax, eax
0x180005866  jns     short loc_180005873
0x180005868  mov     r9d, 98h
0x18000586e  jmp     loc_180005930
0x180005873  lea     rax, [rdi+14h]
0x180005877  mov     r9d, esi
0x18000587a  lea     r8, aExceptionstatu; "ExceptionStatusCode"
0x180005881  mov     [rsp+58h+var_38], rax
0x180005886  xor     edx, edx
0x180005888  mov     rcx, rbp
0x18000588b  call    cs:__imp_WdiAddParameter
0x180005891  mov     ebx, eax
0x180005893  test    eax, eax
0x180005895  jns     short loc_1800058A2
0x180005897  mov     r9d, 0A0h
0x18000589d  jmp     loc_180005930
0x1800058a2  mov     rcx, [rdi+18h]; pSid
0x1800058a6  call    cs:__imp_IsValidSid
0x1800058ac  test    eax, eax
0x1800058ae  jnz     short loc_1800058D1
0x1800058b0  call    cs:__imp_GetLastError
0x1800058b6  mov     ebx, eax
0x1800058b8  test    eax, eax
0x1800058ba  jle     short loc_1800058C5
0x1800058bc  movzx   ebx, ax
0x1800058bf  or      ebx, 80070000h
0x1800058c5  mov     dword ptr [rsp+58h+var_38], ebx
0x1800058c9  mov     r9d, 0A2h
0x1800058cf  jmp     short loc_180005934
0x1800058d1  mov     rbx, [rdi+18h]
0x1800058d5  mov     rcx, rbx; pSid
0x1800058d8  call    cs:__imp_GetLengthSid
0x1800058de  lea     r8, aUsersid; "UserSID"
0x1800058e5  mov     [rsp+58h+var_38], rbx
0x1800058ea  mov     r9d, eax
0x1800058ed  xor     edx, edx
0x1800058ef  mov     rcx, rbp
0x1800058f2  call    cs:__imp_WdiAddParameter
0x1800058f8  mov     ebx, eax
0x1800058fa  test    eax, eax
0x1800058fc  jns     short loc_180005906
0x1800058fe  mov     r9d, 0A9h
0x180005904  jmp     short loc_180005930
0x180005906  lea     rax, [rdi+20h]
0x18000590a  mov     r9d, esi
0x18000590d  lea     r8, aSessionid; "SessionID"
0x180005914  mov     [rsp+58h+var_38], rax
0x180005919  xor     edx, edx
0x18000591b  mov     rcx, rbp
0x18000591e  call    cs:__imp_WdiAddParameter
0x180005924  mov     ebx, eax
0x180005926  test    eax, eax
0x180005928  jns     short loc_180005949
0x18000592a  mov     r9d, 0B1h
0x180005930  mov     dword ptr [rsp+58h+var_38], eax
0x180005934  lea     r8, aCrasheventdata_0; "CrashEventData::StoreInWdi"
0x18000593b  xor     ecx, ecx; Level
0x18000593d  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180005944  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005949  mov     eax, ebx
0x18000594b  add     rsp, 30h
0x18000594f  pop     r14
0x180005951  pop     rdi
0x180005952  pop     rsi
0x180005953  pop     rbp
0x180005954  pop     rbx
0x180005955  retn
```
