# CRegistryPropertyStore::GetAt(ulong,_tagpropertykey *)

- ea: `0x180062d30`
- end: `0x180062efa`
- name: `?GetAt@CRegistryPropertyStore@@UEAAJKPEAU_tagpropertykey@@@Z`
- size: `458`
- prototype: `int(CRegistryPropertyStore *__hidden this, unsigned int, struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010da8`
- `0x180022de4`
- `0x180026fcc`
- `0x180033578`
- `0x18003e920`
- `0x180062d30`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180062eca`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180062eca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180062e23`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180062e23`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062e82`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062e82`

## string_xrefs

- `0x180062da6`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062dd5`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062e9b`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`
- `0x180062ea2`: `Unable to convert the string %ws to CLSID`

## pseudocode

```c
__int64 __fastcall CRegistryPropertyStore::GetAt(CRegistryPropertyStore *this, DWORD a2, struct _tagpropertykey *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  HKEY v11; // rcx
  LSTATUS v12; // eax
  WCHAR *i; // rdi
  int lpReserved; // [rsp+20h] [rbp-79h]
  _BYTE v16[4]; // [rsp+40h] [rbp-59h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-55h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-51h] BYREF
  LPCRITICAL_SECTION v19[2]; // [rsp+50h] [rbp-49h] BYREF
  WCHAR ValueName[48]; // [rsp+60h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  ATL::CCritSecLock::CCritSecLock(
    (ATL::CCritSecLock *)v19,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16),
    (bool)a3);
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 484;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)v6,
      lpReserved);
    goto LABEL_21;
  }
  v8 = *(_QWORD *)this;
  v16[0] = 0;
  v9 = (*(__int64 (__fastcall **)(CRegistryPropertyStore *, _BYTE *))(v8 + 80))(this, v16);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !v16[0] )
    {
      v6 = -2147024894;
      v7 = 488;
      goto LABEL_8;
    }
    v11 = (HKEY)*((_QWORD *)this + 1);
    cchValueName = 48;
    v12 = RegEnumValueW(v11, a2, ValueName, &cchValueName, 0, 0, 0, 0);
    if ( v12 == 259 )
    {
      v6 = -2147024809;
      goto LABEL_21;
    }
    if ( v12 )
    {
      v6 = -2147024809;
      v7 = 500;
      goto LABEL_8;
    }
    EndPtr = 0;
    for ( i = &ValueName[cchValueName]; i != ValueName; --i )
    {
      if ( *i == 44 )
      {
        *i++ = 0;
        break;
      }
    }
    v6 = CLSIDFromString(ValueName, &a3->fmtid);
    if ( (v6 & 0x80000000) == 0 )
    {
      a3->pid = wcstoul(i, &EndPtr, 10);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x204,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)v6,
        (int)"Unable to convert the string %ws to CLSID",
        (const char *)ValueName);
    }
  }
  else
  {
    v6 = -2147024891;
    if ( v9 != -2147024891 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E7,
        (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
        (const char *)(unsigned int)v9,
        lpReserved);
      v6 = v10;
    }
  }
LABEL_21:
  ATL::CCritSecLock::~CCritSecLock(v19);
  return v6;
}

```

## disassembly

```asm
0x180062d30  push    rbp
0x180062d32  push    rbx
0x180062d33  push    rsi
0x180062d34  push    rdi
0x180062d35  push    r14
0x180062d37  lea     rbp, [rsp-37h]
0x180062d3c  sub     rsp, 0D0h
0x180062d43  mov     rax, cs:__security_cookie
0x180062d4a  xor     rax, rsp
0x180062d4d  mov     [rbp+57h+var_30], rax
0x180062d51  mov     r14d, edx
0x180062d54  mov     rbx, rcx
0x180062d57  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x180062d5b  mov     rsi, r8
0x180062d5e  lea     rcx, [rbp+57h+var_A0]; this
0x180062d62  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180062d67  test    rsi, rsi
0x180062d6a  jnz     short loc_180062D78
0x180062d6c  mov     ebx, 80004003h
0x180062d71  mov     edx, 1E4h
0x180062d76  jmp     short loc_180062DD1
0x180062d78  mov     rax, [rbx]
0x180062d7b  lea     rdx, [rbp+57h+var_B0]
0x180062d7f  mov     rcx, rbx
0x180062d82  mov     [rbp+57h+var_B0], 0
0x180062d86  mov     rax, [rax+50h]
0x180062d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d8f  mov     edi, eax
0x180062d91  test    eax, eax
0x180062d93  jns     short loc_180062DC1
0x180062d95  mov     ebx, 80070005h
0x180062d9a  cmp     eax, ebx
0x180062d9c  jz      loc_180062ED5
0x180062da2  mov     rcx, [rbp+5Fh]; this
0x180062da6  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062dad  mov     r9d, eax; char *
0x180062db0  mov     edx, 1E7h; void *
0x180062db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062dba  mov     ebx, edi
0x180062dbc  jmp     loc_180062ED5
0x180062dc1  cmp     [rbp+57h+var_B0], 0
0x180062dc5  jnz     short loc_180062DE9
0x180062dc7  mov     ebx, 80070002h
0x180062dcc  mov     edx, 1E8h; void *
0x180062dd1  mov     rcx, [rbp+5Fh]; this
0x180062dd5  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062ddc  mov     r9d, ebx; char *
0x180062ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062de4  jmp     loc_180062ED5
0x180062de9  mov     rcx, [rbx+8]; hKey
0x180062ded  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180062df1  mov     [rsp+0F0h+lpcbData], 0; lpcbData
0x180062dfa  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180062dfe  mov     [rsp+0F0h+lpData], 0; lpData
0x180062e07  mov     edx, r14d; dwIndex
0x180062e0a  mov     [rsp+0F0h+lpType], 0; lpType
0x180062e13  mov     [rsp+0F0h+lpReserved], 0; lpReserved
0x180062e1c  mov     [rbp+57h+cchValueName], 30h ; '0'
0x180062e23  call    cs:__imp_RegEnumValueW
0x180062e29  cmp     eax, 103h
0x180062e2e  jnz     short loc_180062E3A
0x180062e30  mov     ebx, 80070057h
0x180062e35  jmp     loc_180062ED5
0x180062e3a  test    eax, eax
0x180062e3c  jz      short loc_180062E4A
0x180062e3e  mov     ebx, 80070057h
0x180062e43  mov     edx, 1F4h
0x180062e48  jmp     short loc_180062DD1
0x180062e4a  mov     eax, [rbp+57h+cchValueName]
0x180062e4d  lea     rdi, [rbp+57h+ValueName]
0x180062e51  mov     [rbp+57h+EndPtr], 0
0x180062e59  lea     rdi, [rdi+rax*2]
0x180062e5d  lea     rax, [rbp+57h+ValueName]
0x180062e61  cmp     rdi, rax
0x180062e64  jz      short loc_180062E7B
0x180062e66  cmp     word ptr [rdi], 2Ch ; ','
0x180062e6a  jz      short loc_180062E72
0x180062e6c  sub     rdi, 2
0x180062e70  jmp     short loc_180062E5D
0x180062e72  xor     eax, eax
0x180062e74  mov     [rdi], ax
0x180062e77  add     rdi, 2
0x180062e7b  mov     rdx, rsi; pclsid
0x180062e7e  lea     rcx, [rbp+57h+ValueName]; lpsz
0x180062e82  call    cs:__imp_CLSIDFromString
0x180062e88  mov     ebx, eax
0x180062e8a  test    eax, eax
0x180062e8c  jns     short loc_180062EBD
0x180062e8e  mov     rcx, [rbp+5Fh]; this
0x180062e92  lea     rax, [rbp+57h+ValueName]
0x180062e96  mov     [rsp+0F0h+lpType], rax; char *
0x180062e9b  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x180062ea2  lea     rax, aUnableToConver; "Unable to convert the string %ws to CLS"...
0x180062ea9  mov     r9d, ebx; char *
0x180062eac  mov     edx, 204h; void *
0x180062eb1  mov     [rsp+0F0h+lpReserved], rax; int
0x180062eb6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180062ebb  jmp     short loc_180062ED5
0x180062ebd  mov     r8d, 0Ah; Radix
0x180062ec3  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x180062ec7  mov     rcx, rdi; String
0x180062eca  call    cs:__imp_wcstoul
0x180062ed0  mov     [rsi+10h], eax
0x180062ed3  xor     ebx, ebx
0x180062ed5  lea     rcx, [rbp+57h+var_A0]; this
0x180062ed9  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180062ede  mov     eax, ebx
0x180062ee0  mov     rcx, [rbp+57h+var_30]
0x180062ee4  xor     rcx, rsp; StackCookie
0x180062ee7  call    __security_check_cookie
0x180062eec  add     rsp, 0D0h
0x180062ef3  pop     r14
0x180062ef5  pop     rdi
0x180062ef6  pop     rsi
0x180062ef7  pop     rbx
0x180062ef8  pop     rbp
0x180062ef9  retn
```
