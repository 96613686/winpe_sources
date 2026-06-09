# HampUtilCreateVolatileUserRegKey(void *,ulong,HKEY__ * *)

- ea: `0x18000c768`
- end: `0x18000c9ba`
- name: `?HampUtilCreateVolatileUserRegKey@@YAJPEAXKPEAPEAUHKEY__@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(PSID Sid, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c65c`

## callees

- `0x18000c768`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c8e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c93b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c8e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c93b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c967`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c967`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9af`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000c7cd`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000c7cd`

## pseudocode

```c
__int64 __fastcall HampUtilCreateVolatileUserRegKey(PSID Sid, __int64 a2, HKEY *a3)
{
  signed int v4; // ebx
  WCHAR *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  HKEY v8; // rdi
  __int64 v9; // rax
  WCHAR *v10; // r8
  const wchar_t *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[256]; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)&UnicodeString.Length = 33292288;
  UnicodeString.Buffer = SubKey;
  hKey = 0;
  phkResult = 0;
  v4 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 0);
  if ( v4 < 0 )
    goto LABEL_6;
  v5 = SubKey;
  v6 = 254;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v4 = v6 == 0 ? 0xC000000D : 0;
  v7 = (254 - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_6;
  v9 = 66;
  v10 = &SubKey[v7];
  v11 = L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\HostActivityManager";
  v12 = 254 - v7;
  if ( 254 != v7 )
  {
    do
    {
      if ( !v9 )
        break;
      if ( !*v11 )
        break;
      *v10++ = *v11++;
      --v9;
      --v12;
    }
    while ( v12 );
  }
  v13 = v10 - 1;
  v4 = v12 == 0 ? 0x80000005 : 0;
  if ( v12 )
    v13 = v10;
  *v13 = 0;
  if ( !v12 )
    goto LABEL_6;
  v14 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 1u, 0, &phkResult, 0);
  v4 = v14;
  if ( v14 > 0 )
    v4 = (unsigned __int16)v14 | 0xC0070000;
  if ( v4 >= 0 )
  {
    v8 = phkResult;
    phkResult = 0;
  }
  else
  {
LABEL_6:
    v8 = 0;
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v4 < 0 )
      goto LABEL_9;
  }
  v15 = RegCreateKeyExW(v8, L"Volatile", 0, 0, 1u, 1u, 0, &hKey, 0);
  v4 = v15;
  if ( v15 > 0 )
    v4 = (unsigned __int16)v15 | 0xC0070000;
  if ( v4 >= 0 )
  {
    v4 = 0;
    *a3 = hKey;
    hKey = 0;
    goto LABEL_26;
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_26:
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c768  mov     [rsp-8+arg_8], rbx
0x18000c76d  mov     [rsp-8+arg_18], rsi
0x18000c772  push    rbp
0x18000c773  push    rdi
0x18000c774  push    r14
0x18000c776  lea     rbp, [rsp-180h]
0x18000c77e  sub     rsp, 280h
0x18000c785  mov     rax, cs:__security_cookie
0x18000c78c  xor     rax, rsp
0x18000c78f  mov     [rbp+190h+var_20], rax
0x18000c796  xorps   xmm0, xmm0
0x18000c799  mov     eax, 1FCh
0x18000c79e  movups  xmmword ptr [rsp+290h+UnicodeString.Length], xmm0
0x18000c7a3  mov     [rsp+290h+UnicodeString.MaximumLength], ax
0x18000c7a8  mov     rsi, r8
0x18000c7ab  lea     rax, [rsp+290h+SubKey]
0x18000c7b0  xor     r14d, r14d
0x18000c7b3  mov     rdx, rcx; Sid
0x18000c7b6  mov     [rsp+290h+UnicodeString.Buffer], rax
0x18000c7bb  xor     r8d, r8d; AllocateDestinationString
0x18000c7be  mov     [rsp+290h+hKey], r14
0x18000c7c3  lea     rcx, [rsp+290h+UnicodeString]; UnicodeString
0x18000c7c8  mov     [rsp+290h+var_240], r14
0x18000c7cd  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000c7d3  mov     ebx, eax
0x18000c7d5  test    eax, eax
0x18000c7d7  js      short loc_18000C81D
0x18000c7d9  mov     edx, 0FEh
0x18000c7de  lea     rax, [rsp+290h+SubKey]
0x18000c7e3  mov     r8d, edx
0x18000c7e6  cmp     [rax], r14w
0x18000c7ea  jz      short loc_18000C7F6
0x18000c7ec  add     rax, 2
0x18000c7f0  sub     r8, 1
0x18000c7f4  jnz     short loc_18000C7E6
0x18000c7f6  mov     rax, r8
0x18000c7f9  mov     rcx, rdx
0x18000c7fc  neg     rax
0x18000c7ff  mov     rax, r8
0x18000c802  sbb     ebx, ebx
0x18000c804  sub     rcx, r8
0x18000c807  not     ebx
0x18000c809  and     ebx, 0C000000Dh
0x18000c80f  neg     rax
0x18000c812  sbb     r9, r9
0x18000c815  and     r9, rcx
0x18000c818  test    r8, r8
0x18000c81b  jnz     short loc_18000C84F
0x18000c81d  mov     rcx, [rsp+290h+var_240]; hKey
0x18000c822  mov     rdi, r14
0x18000c825  test    rcx, rcx
0x18000c828  jnz     loc_18000C9AF
0x18000c82e  test    ebx, ebx
0x18000c830  jns     loc_18000C907
0x18000c836  mov     rcx, [rsp+290h+hKey]; hKey
0x18000c83b  test    rcx, rcx
0x18000c83e  jz      loc_18000C95F
0x18000c844  call    cs:__imp_RegCloseKey
0x18000c84a  jmp     loc_18000C95F
0x18000c84f  lea     r8, [rsp+290h+SubKey]
0x18000c854  mov     eax, 42h ; 'B'
0x18000c859  lea     r8, [r8+r9*2]
0x18000c85d  lea     rcx, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x18000c864  sub     rdx, r9
0x18000c867  jz      short loc_18000C88D
0x18000c869  test    rax, rax
0x18000c86c  jz      short loc_18000C88D
0x18000c86e  movzx   r9d, word ptr [rcx]
0x18000c872  test    r9w, r9w
0x18000c876  jz      short loc_18000C88D
0x18000c878  mov     [r8], r9w
0x18000c87c  add     rcx, 2
0x18000c880  add     r8, 2
0x18000c884  dec     rax
0x18000c887  sub     rdx, 1
0x18000c88b  jnz     short loc_18000C869
0x18000c88d  mov     rax, rdx
0x18000c890  lea     rcx, [r8-2]
0x18000c894  neg     rax
0x18000c897  sbb     ebx, ebx
0x18000c899  not     ebx
0x18000c89b  and     ebx, 80000005h
0x18000c8a1  test    rdx, rdx
0x18000c8a4  cmovnz  rcx, r8
0x18000c8a8  mov     [rcx], r14w
0x18000c8ac  jz      loc_18000C81D
0x18000c8b2  mov     [rsp+290h+lpdwDisposition], r14; lpdwDisposition
0x18000c8b7  lea     rax, [rsp+290h+var_240]
0x18000c8bc  mov     [rsp+290h+phkResult], rax; phkResult
0x18000c8c1  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18000c8c6  mov     [rsp+290h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000c8cb  xor     r9d, r9d; lpClass
0x18000c8ce  mov     [rsp+290h+samDesired], 1; samDesired
0x18000c8d6  xor     r8d, r8d; Reserved
0x18000c8d9  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000c8e0  mov     [rsp+290h+dwOptions], r14d; dwOptions
0x18000c8e5  call    cs:__imp_RegCreateKeyExW
0x18000c8eb  mov     ebx, eax
0x18000c8ed  test    eax, eax
0x18000c8ef  jg      loc_18000C996
0x18000c8f5  test    ebx, ebx
0x18000c8f7  js      loc_18000C81D
0x18000c8fd  mov     rdi, [rsp+290h+var_240]
0x18000c902  mov     [rsp+290h+var_240], r14
0x18000c907  mov     [rsp+290h+lpdwDisposition], r14; lpdwDisposition
0x18000c90c  lea     rax, [rsp+290h+hKey]
0x18000c911  mov     [rsp+290h+phkResult], rax; phkResult
0x18000c916  lea     rdx, SubKey; "Volatile"
0x18000c91d  mov     [rsp+290h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000c922  xor     r9d, r9d; lpClass
0x18000c925  mov     [rsp+290h+samDesired], 1; samDesired
0x18000c92d  xor     r8d, r8d; Reserved
0x18000c930  mov     rcx, rdi; hKey
0x18000c933  mov     [rsp+290h+dwOptions], 1; dwOptions
0x18000c93b  call    cs:__imp_RegCreateKeyExW
0x18000c941  mov     ebx, eax
0x18000c943  test    eax, eax
0x18000c945  jg      short loc_18000C9A4
0x18000c947  test    ebx, ebx
0x18000c949  js      loc_18000C836
0x18000c94f  mov     rax, [rsp+290h+hKey]
0x18000c954  mov     ebx, r14d
0x18000c957  mov     [rsi], rax
0x18000c95a  mov     [rsp+290h+hKey], r14
0x18000c95f  test    rdi, rdi
0x18000c962  jz      short loc_18000C96D
0x18000c964  mov     rcx, rdi; hKey
0x18000c967  call    cs:__imp_RegCloseKey
0x18000c96d  mov     eax, ebx
0x18000c96f  mov     rcx, [rbp+190h+var_20]
0x18000c976  xor     rcx, rsp; StackCookie
0x18000c979  call    __security_check_cookie
0x18000c97e  lea     r11, [rsp+290h+var_10]
0x18000c986  mov     rbx, [r11+28h]
0x18000c98a  mov     rsi, [r11+38h]
0x18000c98e  mov     rsp, r11
0x18000c991  pop     r14
0x18000c993  pop     rdi
0x18000c994  pop     rbp
0x18000c995  retn
0x18000c996  movzx   ebx, ax
0x18000c999  or      ebx, 0C0070000h
0x18000c99f  jmp     loc_18000C8F5
0x18000c9a4  movzx   ebx, ax
0x18000c9a7  or      ebx, 0C0070000h
0x18000c9ad  jmp     short loc_18000C947
0x18000c9af  call    cs:__imp_RegCloseKey
0x18000c9b5  jmp     loc_18000C82E
```
