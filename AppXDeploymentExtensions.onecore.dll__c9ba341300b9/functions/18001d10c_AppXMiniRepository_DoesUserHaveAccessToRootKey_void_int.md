# AppXMiniRepository::DoesUserHaveAccessToRootKey(void *,int *)

- ea: `0x18001d10c`
- end: `0x18001d7b6`
- name: `?DoesUserHaveAccessToRootKey@AppXMiniRepository@@SAJPEAXPEAH@Z`
- size: `1706`
- prototype: `__int64 __fastcall(PSID pSid2, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ce24`

## callees

- `0x18000e6e0`
- `0x1800138e0`
- `0x18001d10c`
- `0x18001f430`
- `0x18005ded4`
- `0x180085638`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a5970`
- `0x1800f0700`
- `0x1800f17bc`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d703`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d751`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d703`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d751`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001d3d8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001d4f1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001d3d8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001d4f1`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001d41f`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001d41f`
- `ntdll!RtlGetAce` at `0x18001d44c`
- `ntdll!RtlGetAce` at `0x18001d44c`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001d186`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001d186`
- `ntdll!RtlFreeUnicodeString` at `0x18001d1af`
- `ntdll!RtlFreeUnicodeString` at `0x18001d1af`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d470`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d470`

## string_xrefs

- `0x18001d572`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18001d77a`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x18001d5bb`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001d5cf`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001d5ed`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001d601`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppXMiniRepository::DoesUserHaveAccessToRootKey(PSID pSid2, int *a2)
{
  NTSTATUS v4; // eax
  signed int KeySecurity; // ebx
  __int64 v6; // rsi
  __int64 v7; // r14
  wil::details::in1diag3 *v8; // rcx
  int v9; // eax
  void *v10; // rdi
  __int64 v11; // r14
  wil::details::in1diag3 *v12; // rcx
  int v13; // eax
  LPCWSTR v14; // rcx
  const WCHAR *v15; // rbx
  LSTATUS v16; // eax
  PWSTR Buffer; // rsi
  NTSTATUS DaclSecurityDescriptor; // eax
  ULONG i; // r14d
  char *v20; // rbx
  int v21; // eax
  unsigned __int64 v22; // rdx
  HKEY v23; // rcx
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  HKEY v30; // rcx
  void *v31; // rcx
  __int64 v32; // rdx
  int phkResult; // [rsp+20h] [rbp-59h]
  int phkResulta; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-41h] BYREF
  int v37; // [rsp+48h] [rbp-31h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-29h] BYREF
  int v39; // [rsp+60h] [rbp-19h]
  const int *v40; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR *v41; // [rsp+70h] [rbp-9h]
  LPCWSTR *v42; // [rsp+78h] [rbp-1h]
  PACL Dacl; // [rsp+80h] [rbp+7h] BYREF
  void *Src[2]; // [rsp+88h] [rbp+Fh] BYREF
  int v45; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned __int8 DaclDefaulted; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int8 DaclPresent; // [rsp+F0h] [rbp+77h] BYREF
  char *cbSecurityDescriptor; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_OWORD *)Src = 0;
  v45 = 0;
  *(_OWORD *)lpSubKey = 0;
  v39 = 0;
  v41 = lpSubKey;
  v40 = &Common::StringBufferBuilder::`vftable';
  v42 = lpSubKey;
  hKey = 0;
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  if ( pSid2 )
  {
    UnicodeString = 0;
    v4 = RtlConvertSidToUnicodeString(&UnicodeString, pSid2, 1u);
    if ( v4 < 0 )
    {
      KeySecurity = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x1E,
                      (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                      (const char *)(unsigned int)v4,
                      phkResult);
    }
    else
    {
      KeySecurity = Common::StringBuffer::SetValue(
                      (Common::StringBuffer *)Src,
                      UnicodeString.Buffer,
                      UnicodeString.Length >> 1);
      RtlFreeUnicodeString(&UnicodeString);
    }
  }
  else
  {
    KeySecurity = -2147024809;
  }
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResult);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v29);
    v31 = Src[1];
    if ( !Src[1] )
      return (unsigned int)KeySecurity;
LABEL_72:
    operator delete(v31, v29);
    return (unsigned int)KeySecurity;
  }
  v6 = *(unsigned int *)v41;
  v7 = LODWORD(Src[0]);
  KeySecurity = ~LODWORD(Src[0]) < (unsigned int)v6 ? 0x80070216 : 0;
  v8 = retaddr;
  if ( (unsigned int)v6 > ~LODWORD(Src[0]) )
  {
    v25 = (unsigned int)KeySecurity;
    v26 = 263;
  }
  else
  {
    if ( (unsigned int)(v6 + LODWORD(Src[0])) > 0x3FFFFFFF )
    {
      KeySecurity = -2147023613;
      goto LABEL_9;
    }
    v9 = (*(__int64 (__fastcall **)(const int **))v40)(&v40);
    KeySecurity = v9;
    v8 = retaddr;
    if ( v9 >= 0 )
    {
      KeySecurity = 0;
      goto LABEL_9;
    }
    v25 = (unsigned int)v9;
    v26 = 269;
  }
  wil::details::in1diag3::_Log_Hr(
    v8,
    (void *)v26,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v25,
    phkResult);
LABEL_9:
  v10 = Src[1];
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResult);
  }
  else
  {
    memcpy_0((void *)&v41[1][v6], Src[1], 2 * v7);
    KeySecurity = 0;
  }
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResult);
    v30 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_68;
    goto LABEL_67;
  }
  v11 = *(unsigned int *)v41;
  KeySecurity = (unsigned int)v11 > 0xFFFFFFA1 ? 0x80070216 : 0;
  v12 = retaddr;
  if ( (unsigned int)v11 > 0xFFFFFFA1 )
  {
    v27 = (unsigned int)KeySecurity;
    v28 = 263;
  }
  else
  {
    if ( (unsigned int)(v11 + 94) > 0x3FFFFFFF )
    {
      KeySecurity = -2147023613;
      goto LABEL_16;
    }
    v13 = (*(__int64 (__fastcall **)(const int **))v40)(&v40);
    KeySecurity = v13;
    v12 = retaddr;
    if ( v13 >= 0 )
    {
      KeySecurity = 0;
      goto LABEL_16;
    }
    v27 = (unsigned int)v13;
    v28 = 269;
  }
  wil::details::in1diag3::_Log_Hr(
    v12,
    (void *)v28,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v27,
    phkResult);
LABEL_16:
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResult);
  }
  else
  {
    v14 = v41[1];
    *(_OWORD *)&v14[v11] = *(_OWORD *)L"\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\"
                                       "AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 8] = *(_OWORD *)L"e\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 16] = *(_OWORD *)L"s\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 24] = *(_OWORD *)L"Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 32] = *(_OWORD *)L"\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 40] = *(_OWORD *)L"e\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 48] = *(_OWORD *)L"oft\\Windows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 56] = *(_OWORD *)L"ows\\CurrentVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 64] = *(_OWORD *)L"entVersion\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 72] = *(_OWORD *)L"on\\AppModel\\Repository";
    *(_OWORD *)&v14[v11 + 80] = *(_OWORD *)L"del\\Repository";
    *(_OWORD *)&v14[v11 + 86] = *(_OWORD *)L"pository";
    KeySecurity = 0;
  }
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResult);
    v30 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_68:
      if ( lpSubKey[1] )
        operator delete((void *)lpSubKey[1], v29);
      if ( !v10 )
        return (unsigned int)KeySecurity;
      v31 = v10;
      goto LABEL_72;
    }
LABEL_67:
    RegCloseKey(v30);
    goto LABEL_68;
  }
  v15 = lpSubKey[1];
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  hKey = 0;
  v16 = RegOpenKeyExW_0(HKEY_USERS, v15, 0, 0x20019u, &hKey);
  KeySecurity = v16;
  if ( v16 > 0 )
    KeySecurity = (unsigned __int16)v16 | 0x80070000;
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResulta);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    goto LABEL_68;
  }
  Buffer = 0;
  UnicodeString.Buffer = 0;
  *(_DWORD *)&UnicodeString.Length = 0;
  v37 = 0;
  LODWORD(cbSecurityDescriptor) = 0;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, (LPDWORD)&cbSecurityDescriptor);
  if ( KeySecurity == 122 )
  {
    v21 = Common::ByteBuffer::SetCapacity((Common::ByteBuffer *)&UnicodeString, (unsigned int)cbSecurityDescriptor);
    KeySecurity = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)(unsigned int)v21,
        phkResulta);
      goto LABEL_27;
    }
    Buffer = UnicodeString.Buffer;
    KeySecurity = RegGetKeySecurity(hKey, 4u, UnicodeString.Buffer, (LPDWORD)&cbSecurityDescriptor);
  }
  if ( !KeySecurity )
  {
    Common::ByteBuffer::SetLength((Common::ByteBuffer *)&UnicodeString, (unsigned int)cbSecurityDescriptor);
    KeySecurity = 0;
LABEL_27:
    Buffer = UnicodeString.Buffer;
    goto LABEL_28;
  }
  if ( KeySecurity > 0 )
    KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
LABEL_28:
  if ( KeySecurity < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)KeySecurity,
      phkResulta);
LABEL_65:
    operator delete(Buffer, 1u);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Src);
    return (unsigned int)KeySecurity;
  }
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(Buffer, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    v32 = 190;
LABEL_89:
    KeySecurity = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)v32,
                    (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
                    (const char *)(unsigned int)DaclSecurityDescriptor,
                    phkResulta);
    goto LABEL_65;
  }
  for ( i = 0; i < Dacl->AceCount; ++i )
  {
    cbSecurityDescriptor = 0;
    DaclSecurityDescriptor = RtlGetAce(Dacl, i, (PVOID *)&cbSecurityDescriptor);
    if ( DaclSecurityDescriptor < 0 )
    {
      v32 = 196;
      goto LABEL_89;
    }
    v20 = cbSecurityDescriptor;
    if ( !*cbSecurityDescriptor
      && (cbSecurityDescriptor[1] & 0x10) == 0
      && EqualSid(cbSecurityDescriptor + 8, pSid2)
      && (*((_DWORD *)v20 + 1) & 0x20019) != 0
      && (cbSecurityDescriptor[1] & 3) == 3 )
    {
      *a2 = 1;
      operator delete(Buffer, 1u);
      v23 = hKey;
      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_48;
      goto LABEL_47;
    }
  }
  *a2 = 0;
  operator delete(Buffer, 1u);
  v23 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_47:
    RegCloseKey(v23);
LABEL_48:
  if ( lpSubKey[1] )
    operator delete((void *)lpSubKey[1], v22);
  if ( v10 )
    operator delete(v10, v22);
  return 0;
}

```

## disassembly

```asm
0x18001d10c  mov     [rsp-8+arg_8], rbx
0x18001d111  push    rbp
0x18001d112  push    rsi
0x18001d113  push    rdi
0x18001d114  push    r12
0x18001d116  push    r13
0x18001d118  push    r14
0x18001d11a  push    r15
0x18001d11c  lea     rbp, [rsp-27h]
0x18001d121  sub     rsp, 0A0h
0x18001d128  mov     r12, rdx
0x18001d12b  mov     r15, rcx
0x18001d12e  xorps   xmm0, xmm0
0x18001d131  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001d135  xor     r13d, r13d
0x18001d138  mov     [rbp+57h+var_38], r13d
0x18001d13c  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18001d140  mov     [rbp+57h+var_70], r13d
0x18001d144  lea     rax, [rbp+57h+lpSubKey]
0x18001d148  mov     [rbp+57h+var_60], rax
0x18001d14c  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001d153  mov     [rbp+57h+var_68], rax
0x18001d157  lea     rax, [rbp+57h+lpSubKey]
0x18001d15b  mov     [rbp+57h+var_58], rax
0x18001d15f  mov     [rbp+57h+hKey], r13
0x18001d163  mov     [rbp+57h+Dacl], r13
0x18001d167  mov     [rbp+57h+DaclPresent], r13b
0x18001d16b  mov     [rbp+57h+DaclDefaulted], r13b
0x18001d16f  test    rcx, rcx
0x18001d172  jz      loc_18001D4FE
0x18001d178  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18001d17c  mov     r8b, 1; AllocateDestinationString
0x18001d17f  mov     rdx, rcx; Sid
0x18001d182  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18001d186  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001d18c  test    eax, eax
0x18001d18e  js      loc_18001D56B
0x18001d194  movzx   r8d, [rbp+57h+UnicodeString.Length]
0x18001d199  shr     r8d, 1; unsigned int
0x18001d19c  mov     rdx, [rbp+57h+UnicodeString.Buffer]; unsigned __int16 *
0x18001d1a0  lea     rcx, [rbp+57h+Src]; this
0x18001d1a4  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18001d1a9  mov     ebx, eax
0x18001d1ab  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18001d1af  call    cs:__imp_RtlFreeUnicodeString
0x18001d1b5  mov     rcx, [rbp+5Fh]; this
0x18001d1b9  test    ebx, ebx
0x18001d1bb  js      loc_18001D70E
0x18001d1c1  mov     rax, [rbp+57h+var_60]
0x18001d1c5  mov     esi, [rax]
0x18001d1c7  mov     r14d, dword ptr [rbp+57h+Src]
0x18001d1cb  mov     eax, r14d
0x18001d1ce  not     eax
0x18001d1d0  cmp     eax, esi
0x18001d1d2  sbb     ebx, ebx
0x18001d1d4  and     ebx, 80070216h
0x18001d1da  mov     rcx, [rbp+5Fh]; this
0x18001d1de  cmp     esi, eax
0x18001d1e0  ja      loc_18001D5B3
0x18001d1e6  lea     edx, [rsi+r14]
0x18001d1ea  cmp     edx, 3FFFFFFFh
0x18001d1f0  ja      loc_18001D4A8
0x18001d1f6  mov     rax, [rbp+57h+var_68]
0x18001d1fa  lea     rcx, [rbp+57h+var_68]
0x18001d1fe  mov     rax, [rax]
0x18001d201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d206  mov     ebx, eax
0x18001d208  mov     rcx, [rbp+5Fh]
0x18001d20c  test    eax, eax
0x18001d20e  js      loc_18001D759
0x18001d214  mov     ebx, r13d
0x18001d217  mov     rcx, [rbp+5Fh]; this
0x18001d21b  mov     rdi, [rbp+57h+Src+8]
0x18001d21f  test    ebx, ebx
0x18001d221  js      loc_18001D5CC
0x18001d227  mov     r8, r14
0x18001d22a  add     r8, r8; Size
0x18001d22d  mov     rax, [rbp+57h+var_60]
0x18001d231  mov     rcx, [rax+8]
0x18001d235  lea     rcx, [rcx+rsi*2]; void *
0x18001d239  mov     rdx, rdi; Src
0x18001d23c  call    memcpy_0
0x18001d241  mov     ebx, r13d
0x18001d244  mov     rcx, [rbp+5Fh]; this
0x18001d248  test    ebx, ebx
0x18001d24a  js      loc_18001D617
0x18001d250  mov     rax, [rbp+57h+var_60]
0x18001d254  mov     r14d, [rax]
0x18001d257  mov     rsi, cs:off_1802121B8; "\\Software\\Classes\\Local Settings\\So"...
0x18001d25e  mov     eax, 0FFFFFFA1h
0x18001d263  cmp     eax, r14d
0x18001d266  sbb     ebx, ebx
0x18001d268  and     ebx, 80070216h
0x18001d26e  mov     rcx, [rbp+5Fh]; this
0x18001d272  cmp     r14d, eax
0x18001d275  ja      loc_18001D5E5
0x18001d27b  lea     edx, [r14+5Eh]
0x18001d27f  cmp     edx, 3FFFFFFFh
0x18001d285  ja      loc_18001D4B2
0x18001d28b  mov     rax, [rbp+57h+var_68]
0x18001d28f  lea     rcx, [rbp+57h+var_68]
0x18001d293  mov     rax, [rax]
0x18001d296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d29b  mov     ebx, eax
0x18001d29d  mov     rcx, [rbp+5Fh]
0x18001d2a1  test    eax, eax
0x18001d2a3  js      loc_18001D766
0x18001d2a9  mov     ebx, r13d
0x18001d2ac  mov     rcx, [rbp+5Fh]; this
0x18001d2b0  test    ebx, ebx
0x18001d2b2  js      loc_18001D5FE
0x18001d2b8  mov     rax, [rbp+57h+var_60]
0x18001d2bc  mov     rcx, [rax+8]
0x18001d2c0  movups  xmm0, xmmword ptr [rsi]
0x18001d2c3  movups  xmmword ptr [rcx+r14*2], xmm0
0x18001d2c8  movups  xmm1, xmmword ptr [rsi+10h]
0x18001d2cc  movups  xmmword ptr [rcx+r14*2+10h], xmm1
0x18001d2d2  movups  xmm0, xmmword ptr [rsi+20h]
0x18001d2d6  movups  xmmword ptr [rcx+r14*2+20h], xmm0
0x18001d2dc  movups  xmm1, xmmword ptr [rsi+30h]
0x18001d2e0  movups  xmmword ptr [rcx+r14*2+30h], xmm1
0x18001d2e6  movups  xmm0, xmmword ptr [rsi+40h]
0x18001d2ea  movups  xmmword ptr [rcx+r14*2+40h], xmm0
0x18001d2f0  movups  xmm1, xmmword ptr [rsi+50h]
0x18001d2f4  movups  xmmword ptr [rcx+r14*2+50h], xmm1
0x18001d2fa  movups  xmm0, xmmword ptr [rsi+60h]
0x18001d2fe  movups  xmmword ptr [rcx+r14*2+60h], xmm0
0x18001d304  movups  xmm1, xmmword ptr [rsi+70h]
0x18001d308  movups  xmmword ptr [rcx+r14*2+70h], xmm1
0x18001d30e  movups  xmm0, xmmword ptr [rsi+80h]
0x18001d315  movups  xmmword ptr [rcx+r14*2+80h], xmm0
0x18001d31e  movups  xmm1, xmmword ptr [rsi+90h]
0x18001d325  movups  xmmword ptr [rcx+r14*2+90h], xmm1
0x18001d32e  movups  xmm0, xmmword ptr [rsi+0A0h]
0x18001d335  movups  xmmword ptr [rcx+r14*2+0A0h], xmm0
0x18001d33e  movups  xmm1, xmmword ptr [rsi+0ACh]
0x18001d345  movups  xmmword ptr [rcx+r14*2+0ACh], xmm1
0x18001d34e  mov     ebx, r13d
0x18001d351  mov     rcx, [rbp+5Fh]; this
0x18001d355  test    ebx, ebx
0x18001d357  js      loc_18001D67E
0x18001d35d  mov     rbx, [rbp+57h+lpSubKey+8]
0x18001d361  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d365  lea     rax, [rcx-1]
0x18001d369  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d36d  jbe     loc_18001D4BC
0x18001d373  mov     [rbp+57h+hKey], r13
0x18001d377  lea     rax, [rbp+57h+hKey]
0x18001d37b  mov     qword ptr [rsp+0D0h+phkResult], rax; int
0x18001d380  mov     r9d, 20019h; samDesired
0x18001d386  xor     r8d, r8d; ulOptions
0x18001d389  mov     rdx, rbx; lpSubKey
0x18001d38c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001d393  call    RegOpenKeyExW_0
0x18001d398  mov     ebx, eax
0x18001d39a  mov     r14d, 80070000h
0x18001d3a0  test    eax, eax
0x18001d3a2  jle     short loc_18001D3AA
0x18001d3a4  movzx   ebx, ax
0x18001d3a7  or      ebx, r14d
0x18001d3aa  mov     rcx, [rbp+5Fh]; this
0x18001d3ae  test    ebx, ebx
0x18001d3b0  js      loc_18001D6D6
0x18001d3b6  mov     rsi, r13
0x18001d3b9  mov     [rbp+57h+UnicodeString.Buffer], r13
0x18001d3bd  mov     dword ptr [rbp+57h+UnicodeString.Length], r13d
0x18001d3c1  mov     [rbp+57h+var_88], r13d
0x18001d3c5  mov     dword ptr [rbp+57h+cbSecurityDescriptor], r13d
0x18001d3c9  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18001d3cd  xor     r8d, r8d; pSecurityDescriptor
0x18001d3d0  lea     edx, [r8+4]; SecurityInformation
0x18001d3d4  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d3d8  call    cs:__imp_RegGetKeySecurity
0x18001d3de  mov     ebx, eax
0x18001d3e0  cmp     eax, 7Ah ; 'z'
0x18001d3e3  jz      loc_18001D4C7
0x18001d3e9  test    ebx, ebx
0x18001d3eb  jnz     loc_18001D497
0x18001d3f1  mov     edx, dword ptr [rbp+57h+cbSecurityDescriptor]; unsigned int
0x18001d3f4  lea     rcx, [rbp+57h+UnicodeString]; this
0x18001d3f8  call    ?SetLength@ByteBuffer@Common@@QEAAJK@Z; Common::ByteBuffer::SetLength(ulong)
0x18001d3fd  mov     ebx, r13d
0x18001d400  mov     rsi, [rbp+57h+UnicodeString.Buffer]
0x18001d404  mov     rcx, [rbp+5Fh]; this
0x18001d408  test    ebx, ebx
0x18001d40a  js      loc_18001D640
0x18001d410  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18001d414  lea     r8, [rbp+57h+Dacl]; Dacl
0x18001d418  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18001d41c  mov     rcx, rsi; SecurityDescriptor
0x18001d41f  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18001d425  test    eax, eax
0x18001d427  js      loc_18001D790
0x18001d42d  mov     r14d, r13d
0x18001d430  mov     rcx, [rbp+57h+Dacl]; Acl
0x18001d434  movzx   eax, word ptr [rcx+4]
0x18001d438  cmp     r14d, eax
0x18001d43b  jnb     loc_18001D58A
0x18001d441  mov     [rbp+57h+cbSecurityDescriptor], r13
0x18001d445  lea     r8, [rbp+57h+cbSecurityDescriptor]; Ace
0x18001d449  mov     edx, r14d; AceIndex
0x18001d44c  call    cs:__imp_RtlGetAce
0x18001d452  test    eax, eax
0x18001d454  js      loc_18001D797
0x18001d45a  mov     rbx, [rbp+57h+cbSecurityDescriptor]
0x18001d45e  cmp     [rbx], r13b
0x18001d461  jnz     short loc_18001D492
0x18001d463  test    byte ptr [rbx+1], 10h
0x18001d467  jnz     short loc_18001D492
0x18001d469  lea     rcx, [rbx+8]; pSid1
0x18001d46d  mov     rdx, r15; pSid2
0x18001d470  call    cs:__imp_EqualSid
0x18001d476  test    eax, eax
0x18001d478  jz      short loc_18001D492
0x18001d47a  test    dword ptr [rbx+4], 20019h
0x18001d481  jz      short loc_18001D492
0x18001d483  mov     rax, [rbp+57h+cbSecurityDescriptor]
0x18001d487  mov     cl, [rax+1]
0x18001d48a  and     cl, 3
0x18001d48d  cmp     cl, 3
0x18001d490  jz      short loc_18001D508
0x18001d492  inc     r14d
0x18001d495  jmp     short loc_18001D430
0x18001d497  jle     loc_18001D404
0x18001d49d  movzx   ebx, bx
0x18001d4a0  or      ebx, r14d
0x18001d4a3  jmp     loc_18001D404
0x18001d4a8  mov     ebx, 80070503h
0x18001d4ad  jmp     loc_18001D217
0x18001d4b2  mov     ebx, 80070503h
0x18001d4b7  jmp     loc_18001D2AC
0x18001d4bc  call    cs:__imp_RegCloseKey
0x18001d4c2  jmp     loc_18001D373
0x18001d4c7  mov     edx, dword ptr [rbp+57h+cbSecurityDescriptor]; unsigned int
0x18001d4ca  lea     rcx, [rbp+57h+UnicodeString]; this
0x18001d4ce  call    ?SetCapacity@ByteBuffer@Common@@QEAAJK@Z; Common::ByteBuffer::SetCapacity(ulong)
0x18001d4d3  mov     ebx, eax
0x18001d4d5  test    eax, eax
0x18001d4d7  js      loc_18001D773
0x18001d4dd  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18001d4e1  mov     rsi, [rbp+57h+UnicodeString.Buffer]
0x18001d4e5  mov     r8, rsi; pSecurityDescriptor
0x18001d4e8  mov     edx, 4; SecurityInformation
0x18001d4ed  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d4f1  call    cs:__imp_RegGetKeySecurity
0x18001d4f7  mov     ebx, eax
0x18001d4f9  jmp     loc_18001D3E9
0x18001d4fe  mov     ebx, 80070057h
0x18001d503  jmp     loc_18001D1B5
0x18001d508  mov     eax, 1
0x18001d50d  mov     [r12], eax
0x18001d511  mov     edx, eax; unsigned __int64
0x18001d513  mov     rcx, rsi; void *
0x18001d516  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d51b  nop
0x18001d51c  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d520  lea     rax, [rcx-1]
0x18001d524  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d528  jbe     short loc_18001D562
0x18001d52a  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18001d52e  test    rcx, rcx
0x18001d531  jz      short loc_18001D538
0x18001d533  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d538  test    rdi, rdi
0x18001d53b  jz      short loc_18001D545
0x18001d53d  mov     rcx, rdi; void *
0x18001d540  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d545  xor     eax, eax
0x18001d547  mov     rbx, [rsp+0D0h+arg_8]
0x18001d54f  add     rsp, 0A0h
0x18001d556  pop     r15
0x18001d558  pop     r14
0x18001d55a  pop     r13
0x18001d55c  pop     r12
0x18001d55e  pop     rdi
0x18001d55f  pop     rsi
0x18001d560  pop     rbp
0x18001d561  retn
0x18001d562  call    cs:__imp_RegCloseKey
0x18001d568  nop
0x18001d569  jmp     short loc_18001D52A
0x18001d56b  mov     rcx, [rbp+5Fh]; this
0x18001d56f  mov     r9d, eax; char *
0x18001d572  lea     r8, aOnecoreBaseApp_65; "onecore\\base\\appmodel\\common\\sidhel"...
0x18001d579  mov     edx, 1Eh; void *
0x18001d57e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001d583  mov     ebx, eax
0x18001d585  jmp     loc_18001D1B5
0x18001d58a  mov     [r12], r13d
0x18001d58e  mov     edx, 1; unsigned __int64
0x18001d593  mov     rcx, rsi; void *
0x18001d596  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d59b  nop
0x18001d59c  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d5a0  lea     rax, [rcx-1]
0x18001d5a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d5a8  jbe     loc_18001D6CB
0x18001d5ae  jmp     loc_18001D52A
0x18001d5b3  mov     r9d, ebx; char *
0x18001d5b6  mov     edx, 107h; void *
  ... truncated ...
```
