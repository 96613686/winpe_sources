# _GetValidSIDs(void)

- ea: `0x18004c480`
- end: `0x18004c6a1`
- name: `?_GetValidSIDs@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b1bc`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e428`
- `0x18001067c`
- `0x18001163c`
- `0x180047190`
- `0x18004c480`
- `0x1800543c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c55c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c55c`
- `KERNEL32!LocalFree` at `0x18004c57f`
- `KERNEL32!LocalFree` at `0x18004c5f7`
- `KERNEL32!LocalFree` at `0x18004c57f`
- `KERNEL32!LocalFree` at `0x18004c5f7`
- `KERNEL32!GetLastError` at `0x18004c574`
- `KERNEL32!GetLastError` at `0x18004c5a6`
- `KERNEL32!GetLastError` at `0x18004c574`
- `KERNEL32!GetLastError` at `0x18004c5a6`
- `KERNEL32!SetLastError` at `0x18004c587`
- `KERNEL32!SetLastError` at `0x18004c587`
- `ADVAPI32!IsWellKnownSid` at `0x18004c5d8`
- `ADVAPI32!IsWellKnownSid` at `0x18004c5d8`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18004c59c`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18004c59c`

## string_xrefs

- `0x18004c5b0`: `ConvertStringSidToSidW failed [%#x]`
- `0x18004c5bd`: `_IsWellKnownSid`
- `0x18004c640`: `Valid SID: %ws`
- `0x18004c64d`: `_GetValidSIDs`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall _GetValidSIDs(_QWORD *a1)
{
  const WCHAR *i; // rdi
  const WCHAR *v3; // r14
  char v4; // r12
  HLOCAL v5; // r15
  DWORD LastError; // ebx
  WELL_KNOWN_SID_TYPE v7; // ebx
  __int64 *v8; // rax
  DWORD v10; // [rsp+28h] [rbp-39h]
  HLOCAL hMem; // [rsp+38h] [rbp-29h] BYREF
  int v12; // [rsp+40h] [rbp-21h]
  _QWORD v13[5]; // [rsp+48h] [rbp-19h] BYREF
  _OWORD v14[2]; // [rsp+70h] [rbp+Fh] BYREF

  v13[3] = -2;
  v13[4] = a1;
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,unsigned short const *>(
    v14,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
    56);
  AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(v13, -2147483646, v14);
  std::wstring::~wstring(v14);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v12 = 1;
  for ( i = (const WCHAR *)v13[0]; i != (const WCHAR *)v13[1]; i += 16 )
  {
    if ( *((_QWORD *)i + 3) <= 7u )
      v3 = i;
    else
      v3 = *(const WCHAR **)i;
    hMem = 0;
    v4 = 0;
    if ( *v3 == 83 && !wcsstr(v3, L"Classes") )
    {
      v5 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v5);
        SetLastError(LastError);
      }
      hMem = 0;
      if ( ConvertStringSidToSidW(v3, &hMem) )
      {
        v7 = WinNullSid;
        while ( !IsWellKnownSid(hMem, v7) )
        {
          if ( (unsigned int)++v7 > (WinAuthenticationAuthorityAssertedSid|WinSelfSid) )
            goto LABEL_16;
        }
        v4 = 1;
      }
      else
      {
        v10 = GetLastError();
        AslLogCallPrintf(1, "_IsWellKnownSid", 318, "ConvertStringSidToSidW failed [%#x]", v10);
      }
    }
LABEL_16:
    if ( hMem )
      LocalFree(hMem);
    if ( !v4 )
    {
      if ( a1[1] == a1[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], i);
      }
      else
      {
        std::wstring::wstring(a1[1], i);
        a1[1] += 32LL;
      }
      if ( *((_QWORD *)i + 3) <= 7u )
        v8 = (__int64 *)i;
      else
        v8 = *(__int64 **)i;
      AslLogCallPrintf(3, "_GetValidSIDs", 349, "Valid SID: %ws", v8);
    }
  }
  std::vector<std::wstring>::_Tidy(v13);
  return a1;
}

```

## disassembly

```asm
0x18004c480  mov     rax, rsp
0x18004c483  push    rbp
0x18004c484  push    rdi
0x18004c485  push    r12
0x18004c487  push    r14
0x18004c489  push    r15
0x18004c48b  lea     rbp, [rax-5Fh]
0x18004c48f  sub     rsp, 90h
0x18004c496  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18004c49e  mov     [rax+10h], rbx
0x18004c4a2  mov     [rax+18h], rsi
0x18004c4a6  mov     rax, cs:__security_cookie
0x18004c4ad  xor     rax, rsp
0x18004c4b0  mov     [rbp+57h+var_28], rax
0x18004c4b4  mov     rsi, rcx
0x18004c4b7  mov     [rbp+57h+var_50], rcx
0x18004c4bb  mov     [rbp+57h+var_78], 0
0x18004c4c2  xorps   xmm0, xmm0
0x18004c4c5  movups  [rbp+57h+var_48], xmm0
0x18004c4c9  xorps   xmm1, xmm1
0x18004c4cc  movdqu  [rbp+57h+var_38], xmm1
0x18004c4d1  mov     r8d, 38h ; '8'
0x18004c4d7  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004c4de  lea     rcx, [rbp+57h+var_48]
0x18004c4e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004c4e7  nop
0x18004c4e8  lea     r8, [rbp+57h+var_48]
0x18004c4ec  mov     rdx, 0FFFFFFFF80000002h
0x18004c4f3  lea     rcx, [rbp+57h+var_70]
0x18004c4f7  call    ?GetSubkeyNamesOrDefault@RegOperations@AppCompatUtility@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(HKEY__ *,std::wstring const &)
0x18004c4fc  nop
0x18004c4fd  lea     rcx, [rbp+57h+var_48]; void *
0x18004c501  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c506  mov     qword ptr [rsi], 0
0x18004c50d  mov     qword ptr [rsi+8], 0
0x18004c515  mov     qword ptr [rsi+10h], 0
0x18004c51d  mov     [rbp+57h+var_78], 1
0x18004c524  mov     rdi, [rbp+57h+var_70]
0x18004c528  jmp     loc_18004C662
0x18004c52d  cmp     qword ptr [rdi+18h], 7
0x18004c532  jbe     short loc_18004C539
0x18004c534  mov     r14, [rdi]
0x18004c537  jmp     short loc_18004C53C
0x18004c539  mov     r14, rdi
0x18004c53c  mov     [rbp+57h+hMem], 0
0x18004c544  xor     r12b, r12b
0x18004c547  cmp     word ptr [r14], 53h ; 'S'
0x18004c54c  jnz     loc_18004C5EE
0x18004c552  lea     rdx, aClasses; "Classes"
0x18004c559  mov     rcx, r14; Str
0x18004c55c  call    cs:__imp_wcsstr
0x18004c562  test    rax, rax
0x18004c565  jnz     loc_18004C5EE
0x18004c56b  mov     r15, [rbp+57h+hMem]
0x18004c56f  test    r15, r15
0x18004c572  jz      short loc_18004C58D
0x18004c574  call    cs:__imp_GetLastError
0x18004c57a  mov     ebx, eax
0x18004c57c  mov     rcx, r15; hMem
0x18004c57f  call    cs:__imp_LocalFree
0x18004c585  mov     ecx, ebx; dwErrCode
0x18004c587  call    cs:__imp_SetLastError
0x18004c58d  mov     [rbp+57h+hMem], 0
0x18004c595  lea     rdx, [rbp+57h+hMem]; Sid
0x18004c599  mov     rcx, r14; StringSid
0x18004c59c  call    cs:__imp_ConvertStringSidToSidW
0x18004c5a2  test    eax, eax
0x18004c5a4  jnz     short loc_18004C5D0
0x18004c5a6  call    cs:__imp_GetLastError
0x18004c5ac  mov     [rsp+0B0h+var_90], eax
0x18004c5b0  lea     r9, aConvertstrings; "ConvertStringSidToSidW failed [%#x]"
0x18004c5b7  mov     r8d, 13Eh
0x18004c5bd  lea     rdx, aIswellknownsid; "_IsWellKnownSid"
0x18004c5c4  mov     ecx, 1
0x18004c5c9  call    AslLogCallPrintf
0x18004c5ce  jmp     short loc_18004C5EE
0x18004c5d0  xor     ebx, ebx
0x18004c5d2  mov     edx, ebx; WellKnownSidType
0x18004c5d4  mov     rcx, [rbp+57h+hMem]; pSid
0x18004c5d8  call    cs:__imp_IsWellKnownSid
0x18004c5de  test    eax, eax
0x18004c5e0  jnz     short loc_18004C5EB
0x18004c5e2  inc     ebx
0x18004c5e4  cmp     ebx, 77h ; 'w'
0x18004c5e7  jbe     short loc_18004C5D2
0x18004c5e9  jmp     short loc_18004C5EE
0x18004c5eb  mov     r12b, 1
0x18004c5ee  mov     rcx, [rbp+57h+hMem]; hMem
0x18004c5f2  test    rcx, rcx
0x18004c5f5  jz      short loc_18004C5FD
0x18004c5f7  call    cs:__imp_LocalFree
0x18004c5fd  test    r12b, r12b
0x18004c600  jnz     short loc_18004C65E
0x18004c602  mov     rax, [rsi+8]
0x18004c606  cmp     rax, [rsi+10h]
0x18004c60a  jz      short loc_18004C61E
0x18004c60c  mov     rdx, rdi
0x18004c60f  mov     rcx, rax
0x18004c612  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c617  add     qword ptr [rsi+8], 20h ; ' '
0x18004c61c  jmp     short loc_18004C62C
0x18004c61e  mov     r8, rdi
0x18004c621  mov     rdx, rax
0x18004c624  mov     rcx, rsi
0x18004c627  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18004c62c  cmp     qword ptr [rdi+18h], 7
0x18004c631  jbe     short loc_18004C638
0x18004c633  mov     rax, [rdi]
0x18004c636  jmp     short loc_18004C63B
0x18004c638  mov     rax, rdi
0x18004c63b  mov     qword ptr [rsp+0B0h+var_90], rax
0x18004c640  lea     r9, aValidSidWs; "Valid SID: %ws"
0x18004c647  mov     r8d, 15Dh
0x18004c64d  lea     rdx, aGetvalidsids; "_GetValidSIDs"
0x18004c654  mov     ecx, 3
0x18004c659  call    AslLogCallPrintf
0x18004c65e  add     rdi, 20h ; ' '
0x18004c662  cmp     rdi, [rbp+57h+var_68]
0x18004c666  jnz     loc_18004C52D
0x18004c66c  lea     rcx, [rbp+57h+var_70]
0x18004c670  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004c675  mov     rax, rsi
0x18004c678  mov     rcx, [rbp+57h+var_28]
0x18004c67c  xor     rcx, rsp; StackCookie
0x18004c67f  call    __security_check_cookie
0x18004c684  lea     r11, [rsp+0B0h+var_20]
0x18004c68c  mov     rbx, [r11+38h]
0x18004c690  mov     rsi, [r11+40h]
0x18004c694  mov     rsp, r11
0x18004c697  pop     r15
0x18004c699  pop     r14
0x18004c69b  pop     r12
0x18004c69d  pop     rdi
0x18004c69e  pop     rbp
0x18004c69f  retn
```
