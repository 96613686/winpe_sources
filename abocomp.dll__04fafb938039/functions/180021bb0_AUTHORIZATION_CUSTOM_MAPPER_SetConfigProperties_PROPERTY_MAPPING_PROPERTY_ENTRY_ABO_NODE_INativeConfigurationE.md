# AUTHORIZATION_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180021bb0`
- end: `0x180021df8`
- name: `?SetConfigProperties@AUTHORIZATION_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(AUTHORIZATION_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003426`
- `0x180021bb0`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021d77`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021d98`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021dc9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021d77`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021d98`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180021dc9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021bfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021c2f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021ccd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021cfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d48`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d5d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021bfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021c2f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021ccd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021cfc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d48`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d5d`

## string_xrefs

- `0x180021c6f`: `system.webServer/security/authentication/windowsAuthentication`
- `0x180021d07`: `system.webServer/security/authentication/windowsAuthentication`
- `0x180021c3a`: `system.webServer/security/authentication/basicAuthentication`
- `0x180021c87`: `system.webServer/security/authentication/anonymousAuthentication`
- `0x180021c57`: `system.webServer/security/authentication/digestAuthentication`
- `0x180021d80`: `system.webServer/security/authentication/clientCertificateMappingAuthentication`
- `0x180021da1`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`

## pseudocode

```c
__int64 __fastcall AUTHORIZATION_CUSTOM_MAPPER::SetConfigProperties(
        AUTHORIZATION_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  struct INativeConfigurationElement *v6; // rdi
  BUFFER *v7; // rbx
  int v8; // esi
  _DWORD **Ptr; // rax
  wchar_t *v10; // rbp
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  _DWORD **v14; // rbx
  unsigned int v15; // r14d
  const wchar_t *Str; // rax
  const wchar_t *v17; // rax
  unsigned int (__fastcall *v18)(struct INativeConfigurationElement *, const unsigned __int16 *, _QWORD, _QWORD); // rbx
  const unsigned __int16 *v19; // rdx
  wchar_t *String1; // [rsp+78h] [rbp+10h] BYREF

  String1 = 0;
  if ( !a2 || !a3 || !a4 || (v6 = a5) == 0 )
    return (unsigned int)-2147024809;
  v7 = (struct PROPERTY_ENTRY *)((char *)a3 + 16);
  if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) == 6000 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, wchar_t **))(*(_QWORD *)v6 + 24LL))(
           v6,
           &String1);
    if ( v8 >= 0 )
    {
      Ptr = (_DWORD **)BUFFER::QueryPtr(v7);
      v10 = String1;
      v11 = *Ptr[3];
      if ( !wcscmp_0(String1, L"system.webServer/security/authentication/basicAuthentication") )
      {
        v11 >>= 1;
LABEL_14:
        v12 = v11 & 1;
        return (unsigned int)(*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v6 + 136LL))(
                               v6,
                               L"enabled",
                               v12,
                               0);
      }
      if ( !wcscmp_0(v10, L"system.webServer/security/authentication/digestAuthentication") )
      {
        v11 >>= 4;
        goto LABEL_14;
      }
      if ( !wcscmp_0(v10, L"system.webServer/security/authentication/windowsAuthentication") )
      {
        v11 >>= 2;
        goto LABEL_14;
      }
      if ( !wcscmp_0(v10, L"system.webServer/security/authentication/anonymousAuthentication") )
        goto LABEL_14;
    }
  }
  else
  {
    if ( *(_DWORD *)BUFFER::QueryPtr(v7) != 6031 )
    {
      v8 = 0;
      if ( *(_DWORD *)BUFFER::QueryPtr(v7) != 6030 )
        return (unsigned int)v8;
      v15 = **((_DWORD **)BUFFER::QueryPtr(v7) + 3);
      v12 = (v15 >> 7) & 1;
      Str = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
      if ( wcscmp_0(Str, L"system.webServer/security/authentication/clientCertificateMappingAuthentication") )
      {
        v17 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
        if ( wcscmp_0(v17, L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication") )
        {
          if ( *((_DWORD *)a2 + 38) != 1 )
            return (unsigned int)v8;
          v18 = *(unsigned int (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v6 + 112LL);
          v19 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
          return v18(v6, v19, v15 & 0x168, 0);
        }
      }
      return (unsigned int)(*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v6 + 136LL))(
                             v6,
                             L"enabled",
                             v12,
                             0);
    }
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, wchar_t **))(*(_QWORD *)v6 + 24LL))(
           v6,
           &String1);
    if ( v8 >= 0 )
    {
      v14 = (_DWORD **)BUFFER::QueryPtr(v7);
      if ( !wcscmp_0(String1, L"system.webServer/security/authentication/windowsAuthentication") )
        return (unsigned int)(*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v6 + 136LL))(
                               v6,
                               L"authPersistSingleRequest",
                               (*v14[3] >> 6) & 1,
                               0);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021bb0  push    rbx
0x180021bb2  push    rbp
0x180021bb3  push    rsi
0x180021bb4  push    rdi
0x180021bb5  push    r14
0x180021bb7  push    r15
0x180021bb9  sub     rsp, 38h
0x180021bbd  mov     [rsp+68h+String1], 0
0x180021bc6  mov     rbp, rdx
0x180021bc9  test    rdx, rdx
0x180021bcc  jz      loc_180021DE4
0x180021bd2  test    r8, r8
0x180021bd5  jz      loc_180021DE4
0x180021bdb  test    r9, r9
0x180021bde  jz      loc_180021DE4
0x180021be4  mov     rdi, [rsp+68h+arg_20]
0x180021bec  test    rdi, rdi
0x180021bef  jz      loc_180021DE4
0x180021bf5  lea     rbx, [r8+10h]
0x180021bf9  mov     rcx, rbx
0x180021bfc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021c02  cmp     dword ptr [rax], 1770h
0x180021c08  jnz     loc_180021CCA
0x180021c0e  mov     rax, [rdi]
0x180021c11  lea     rdx, [rsp+68h+String1]
0x180021c16  mov     rcx, rdi
0x180021c19  mov     rax, [rax+18h]
0x180021c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c22  mov     esi, eax
0x180021c24  test    eax, eax
0x180021c26  js      loc_180021DE9
0x180021c2c  mov     rcx, rbx
0x180021c2f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021c35  mov     rbp, [rsp+68h+String1]
0x180021c3a  lea     rdx, aSystemWebserve_6; "system.webServer/security/authenticatio"...
0x180021c41  mov     rcx, [rax+18h]
0x180021c45  mov     ebx, [rcx]
0x180021c47  mov     rcx, rbp; String1
0x180021c4a  call    wcscmp_0
0x180021c4f  test    eax, eax
0x180021c51  jnz     short loc_180021C57
0x180021c53  shr     ebx, 1
0x180021c55  jmp     short loc_180021CA1
0x180021c57  lea     rdx, aSystemWebserve_18; "system.webServer/security/authenticatio"...
0x180021c5e  mov     rcx, rbp; String1
0x180021c61  call    wcscmp_0
0x180021c66  test    eax, eax
0x180021c68  jnz     short loc_180021C6F
0x180021c6a  shr     ebx, 4
0x180021c6d  jmp     short loc_180021CA1
0x180021c6f  lea     rdx, aSystemWebserve_23; "system.webServer/security/authenticatio"...
0x180021c76  mov     rcx, rbp; String1
0x180021c79  call    wcscmp_0
0x180021c7e  test    eax, eax
0x180021c80  jnz     short loc_180021C87
0x180021c82  shr     ebx, 2
0x180021c85  jmp     short loc_180021CA1
0x180021c87  lea     rdx, aSystemWebserve_22; "system.webServer/security/authenticatio"...
0x180021c8e  mov     rcx, rbp; String1
0x180021c91  call    wcscmp_0
0x180021c96  test    eax, eax
0x180021c98  jnz     loc_180021DE9
0x180021c9e  movzx   ebx, bl
0x180021ca1  and     ebx, 1
0x180021ca4  mov     rax, [rdi]
0x180021ca7  lea     rdx, aEnabled; "enabled"
0x180021cae  mov     r8d, ebx
0x180021cb1  mov     rax, [rax+88h]
0x180021cb8  xor     r9d, r9d
0x180021cbb  mov     rcx, rdi
0x180021cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cc3  mov     esi, eax
0x180021cc5  jmp     loc_180021DE9
0x180021cca  mov     rcx, rbx
0x180021ccd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021cd3  cmp     dword ptr [rax], 178Fh
0x180021cd9  jnz     short loc_180021D43
0x180021cdb  mov     rax, [rdi]
0x180021cde  lea     rdx, [rsp+68h+String1]
0x180021ce3  mov     rcx, rdi
0x180021ce6  mov     rax, [rax+18h]
0x180021cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cef  mov     esi, eax
0x180021cf1  test    eax, eax
0x180021cf3  js      loc_180021DE9
0x180021cf9  mov     rcx, rbx
0x180021cfc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021d02  mov     rcx, [rsp+68h+String1]; String1
0x180021d07  lea     rdx, aSystemWebserve_23; "system.webServer/security/authenticatio"...
0x180021d0e  mov     rbx, rax
0x180021d11  call    wcscmp_0
0x180021d16  test    eax, eax
0x180021d18  jnz     loc_180021DE9
0x180021d1e  mov     rax, [rbx+18h]
0x180021d22  lea     rdx, aAuthpersistsin; "authPersistSingleRequest"
0x180021d29  mov     r10, [rdi]
0x180021d2c  mov     r8d, [rax]
0x180021d2f  mov     rax, [r10+88h]
0x180021d36  shr     r8d, 6
0x180021d3a  and     r8d, 1
0x180021d3e  jmp     loc_180021CB8
0x180021d43  mov     rcx, rbx
0x180021d46  xor     esi, esi
0x180021d48  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021d4e  cmp     dword ptr [rax], 178Eh
0x180021d54  jnz     loc_180021DE9
0x180021d5a  mov     rcx, rbx
0x180021d5d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021d63  mov     rcx, [rax+18h]
0x180021d67  mov     r14d, [rcx]
0x180021d6a  mov     ebx, r14d
0x180021d6d  shr     ebx, 7
0x180021d70  lea     rcx, [rbp+20h]
0x180021d74  and     ebx, 1
0x180021d77  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180021d7d  mov     rcx, rax; String1
0x180021d80  lea     rdx, aSystemWebserve_20; "system.webServer/security/authenticatio"...
0x180021d87  call    wcscmp_0
0x180021d8c  test    eax, eax
0x180021d8e  jz      loc_180021CA4
0x180021d94  lea     rcx, [rbp+20h]
0x180021d98  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180021d9e  mov     rcx, rax; String1
0x180021da1  lea     rdx, aSystemWebserve_11; "system.webServer/security/authenticatio"...
0x180021da8  call    wcscmp_0
0x180021dad  test    eax, eax
0x180021daf  jz      loc_180021CA4
0x180021db5  cmp     dword ptr [rbp+98h], 1
0x180021dbc  jnz     short loc_180021DE9
0x180021dbe  mov     rax, [rdi]
0x180021dc1  lea     rcx, [rbp+58h]
0x180021dc5  mov     rbx, [rax+70h]
0x180021dc9  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180021dcf  and     r14d, 168h
0x180021dd6  mov     rdx, rax
0x180021dd9  mov     r8d, r14d
0x180021ddc  mov     rax, rbx
0x180021ddf  jmp     loc_180021CB8
0x180021de4  mov     esi, 80070057h
0x180021de9  mov     eax, esi
0x180021deb  add     rsp, 38h
0x180021def  pop     r15
0x180021df1  pop     r14
0x180021df3  pop     rdi
0x180021df4  pop     rsi
0x180021df5  pop     rbp
0x180021df6  pop     rbx
0x180021df7  retn
```
