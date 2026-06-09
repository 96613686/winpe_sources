# ConvertWebAuthNCredentialsListToExperimental2WebAuthNPluginCredentialsList(_WEBAUTHN_CREDENTIAL_DETAILS_LIST *,_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS * *,ulong *)

- ea: `0x1800b3a70`
- end: `0x1800b3f78`
- name: `?ConvertWebAuthNCredentialsListToExperimental2WebAuthNPluginCredentialsList@@YAJPEAU_WEBAUTHN_CREDENTIAL_DETAILS_LIST@@PEAPEAU_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@PEAK@Z`
- size: `1288`
- prototype: `__int64 __fastcall(struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *, struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e8a0`

## callees

- `0x180036da4`
- `0x180043ab4`
- `0x18005378c`
- `0x18009b790`
- `0x1800b01b8`
- `0x1800b0240`
- `0x1800b3a70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3ebf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3c03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3dd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3e88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3ebf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3ef6`

## string_xrefs

- `0x1800b3b78`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3be9`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3db4`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3e00`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3e37`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3e6e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3ea5`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3edc`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3f22`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b3f48`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ConvertWebAuthNCredentialsListToExperimental2WebAuthNPluginCredentialsList(
        struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *a1,
        struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS **a2,
        unsigned int *a3)
{
  int v5; // edi
  unsigned int v6; // r12d
  const char *v7; // r9
  struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *v8; // rbx
  unsigned int i; // eax
  __int64 v10; // r14
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // r13
  __int64 result; // rax
  __int64 v16; // rdx
  void *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 *v28; // rax
  __int64 v29; // rcx
  __int128 v30; // xmm1
  __int128 v31; // xmm2
  __int128 v32; // xmm3
  __int64 v33; // r14
  void *v34; // rcx
  LPVOID v35; // [rsp+20h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-B0h] BYREF
  void *v37; // [rsp+30h] [rbp-A8h]
  char v38[8]; // [rsp+38h] [rbp-A0h] BYREF
  char v39[8]; // [rsp+40h] [rbp-98h] BYREF
  char v40[8]; // [rsp+48h] [rbp-90h] BYREF
  char v41[8]; // [rsp+50h] [rbp-88h] BYREF
  _DWORD v42[2]; // [rsp+58h] [rbp-80h] BYREF
  void *v43; // [rsp+60h] [rbp-78h]
  __int64 v44; // [rsp+68h] [rbp-70h]
  __int64 v45; // [rsp+70h] [rbp-68h]
  int v46; // [rsp+78h] [rbp-60h]
  int v47; // [rsp+7Ch] [rbp-5Ch]
  void *v48; // [rsp+80h] [rbp-58h]
  __int64 v49; // [rsp+88h] [rbp-50h]
  __int64 v50; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  unsigned int v53; // [rsp+F8h] [rbp+20h]

  try
  {
    v5 = 0;
    if ( a1 && a2 )
    {
      *a2 = 0;
      *a3 = 0;
      v6 = *(_DWORD *)a1;
      wil::make_unique_cotaskmem_nothrow<_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS [0]>(&pv, *(unsigned int *)a1);
      v8 = (struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *)pv;
      if ( pv )
      {
        for ( i = 0; ; i = v53 + 1 )
        {
          v53 = i;
          if ( i >= v6 )
          {
            *a2 = v8;
            *a3 = v6;
            return 0;
          }
          v10 = i;
          v11 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL * i);
          if ( !v11 )
            break;
          v12 = *(_QWORD *)(v11 + 16);
          if ( !v12 )
            break;
          v13 = *(_QWORD *)(v11 + 24);
          if ( !v13 )
            break;
          if ( !*(_DWORD *)(v11 + 4) || !*(_QWORD *)(v11 + 8) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB6F,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80070057LL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942487LL;
          }
          if ( !*(_DWORD *)(v13 + 4) || !*(_QWORD *)(v13 + 8) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB70,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80070057LL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942487LL;
          }
          if ( !*(_QWORD *)(v12 + 8) || !*(_QWORD *)(v12 + 16) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB71,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80070057LL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942487LL;
          }
          if ( !*(_QWORD *)(v13 + 16) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB72,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80070057LL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942487LL;
          }
          v14 = CoTaskMemAlloc(*(unsigned int *)(v11 + 4));
          if ( !v14 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB77,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x8007000ELL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942414LL;
          }
          v16 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10);
          memcpy_0(v14, *(const void **)(v16 + 8), *(unsigned int *)(v16 + 4));
          v17 = CoTaskMemAlloc(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10) + 24LL) + 4LL));
          v37 = v17;
          if ( !v17 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB7B,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x8007000ELL,
              (int)v35);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942414LL;
          }
          v18 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10) + 24LL);
          memcpy_0(v17, *(const void **)(v18 + 8), *(unsigned int *)(v18 + 4));
          v19 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10);
          v42[0] = *(_DWORD *)(v19 + 4);
          v42[1] = 0;
          v43 = v14;
          v20 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                             v41,
                             *(_QWORD *)(*(_QWORD *)(v19 + 16) + 8LL));
          v21 = *v20;
          *v20 = 0;
          v44 = v21;
          v22 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                             v40,
                             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10) + 16LL) + 16LL));
          v23 = *v22;
          *v22 = 0;
          v45 = v23;
          v24 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10) + 24LL);
          v46 = *(_DWORD *)(v24 + 4);
          v47 = 0;
          v48 = v37;
          v25 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                             v39,
                             *(_QWORD *)(v24 + 16));
          v26 = *v25;
          *v25 = 0;
          v49 = v26;
          v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v10) + 24LL) + 32LL);
          if ( v27 )
          {
            v28 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                               v38,
                               v27);
            v5 |= 1u;
            v29 = *v28;
            *v28 = 0;
            v50 = v29;
          }
          else
          {
            v50 = 0;
          }
          wil::make_unique_cotaskmem<_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS,_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS>(&v35, v42);
          if ( (v5 & 1) != 0 )
          {
            v5 &= ~1u;
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v38);
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v39);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v40);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v41);
          if ( !v35 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB8B,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x8007000ELL,
              0);
            v34 = v35;
            v35 = 0;
            if ( v34 )
              CoTaskMemFree(v34);
            if ( v8 )
              CoTaskMemFree(v8);
            return 2147942414LL;
          }
          v30 = *((_OWORD *)v35 + 1);
          v31 = *((_OWORD *)v35 + 2);
          v32 = *((_OWORD *)v35 + 3);
          v33 = v10 << 6;
          *(_OWORD *)((char *)v8 + v33) = *(_OWORD *)v35;
          *(_OWORD *)((char *)v8 + v33 + 16) = v30;
          *(_OWORD *)((char *)v8 + v33 + 32) = v31;
          *(_OWORD *)((char *)v8 + v33 + 48) = v32;
          v35 = 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6E,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80070057LL,
          (int)v35);
        if ( v8 )
          CoTaskMemFree(v8);
        result = 2147942487LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB69,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x8007000ELL,
          (int)v35);
        result = 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5E,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80070057LL,
        (int)v35);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB96,
                           (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800b3a70  mov     rax, rsp
0x1800b3a73  mov     [rax+18h], r8
0x1800b3a77  push    rbx
0x1800b3a78  push    rsi
0x1800b3a79  push    rdi
0x1800b3a7a  push    r12
0x1800b3a7c  push    r13
0x1800b3a7e  push    r14
0x1800b3a80  push    r15
0x1800b3a82  sub     rsp, 0A0h
0x1800b3a89  mov     r15, rdx
0x1800b3a8c  mov     rsi, rcx
0x1800b3a8f  xor     r13d, r13d
0x1800b3a92  mov     edi, r13d
0x1800b3a95  mov     [rax+8], r13d
0x1800b3a99  test    rcx, rcx
0x1800b3a9c  jz      loc_1800B3F38
0x1800b3aa2  test    rdx, rdx
0x1800b3aa5  jz      loc_1800B3F38
0x1800b3aab  mov     [rdx], r13
0x1800b3aae  mov     [r8], r13d
0x1800b3ab1  mov     r12d, [rcx]
0x1800b3ab4  mov     edx, r12d
0x1800b3ab7  lea     rcx, [rsp+0D8h+pv]
0x1800b3abc  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS [0]>(unsigned __int64)
0x1800b3ac1  nop
0x1800b3ac2  mov     rbx, [rsp+0D8h+pv]
0x1800b3ac7  test    rbx, rbx
0x1800b3aca  jz      loc_1800B3F12
0x1800b3ad0  mov     eax, r13d
0x1800b3ad3  mov     [rsp+0D8h+arg_18], eax
0x1800b3ada  cmp     eax, r12d
0x1800b3add  jnb     loc_1800B3F00
0x1800b3ae3  mov     r14d, eax
0x1800b3ae6  mov     rax, [rsi+8]
0x1800b3aea  mov     rcx, [rax+r14*8]
0x1800b3aee  test    rcx, rcx
0x1800b3af1  jz      loc_1800B3ECC
0x1800b3af7  mov     rdx, [rcx+10h]
0x1800b3afb  test    rdx, rdx
0x1800b3afe  jz      loc_1800B3ECC
0x1800b3b04  mov     rax, [rcx+18h]
0x1800b3b08  test    rax, rax
0x1800b3b0b  jz      loc_1800B3ECC
0x1800b3b11  cmp     [rcx+4], r13d
0x1800b3b15  jz      loc_1800B3E95
0x1800b3b1b  cmp     [rcx+8], r13
0x1800b3b1f  jz      loc_1800B3E95
0x1800b3b25  cmp     [rax+4], r13d
0x1800b3b29  jz      loc_1800B3E5E
0x1800b3b2f  cmp     [rax+8], r13
0x1800b3b33  jz      loc_1800B3E5E
0x1800b3b39  cmp     [rdx+8], r13
0x1800b3b3d  jz      loc_1800B3E27
0x1800b3b43  cmp     [rdx+10h], r13
0x1800b3b47  jz      loc_1800B3E27
0x1800b3b4d  cmp     [rax+10h], r13
0x1800b3b51  jz      loc_1800B3DF0
0x1800b3b57  mov     ecx, [rcx+4]; cb
0x1800b3b5a  call    cs:__imp_CoTaskMemAlloc
0x1800b3b60  mov     r13, rax
0x1800b3b63  test    rax, rax
0x1800b3b66  jnz     short loc_1800B3B9F
0x1800b3b68  mov     rcx, [rsp+0D8h]; this
0x1800b3b70  mov     edi, 8007000Eh
0x1800b3b75  mov     r9d, edi; char *
0x1800b3b78  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3b7f  mov     edx, 0B77h; void *
0x1800b3b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3b89  nop
0x1800b3b8a  test    rbx, rbx
0x1800b3b8d  jz      short loc_1800B3B98
0x1800b3b8f  mov     rcx, rbx; pv
0x1800b3b92  call    cs:__imp_CoTaskMemFree
0x1800b3b98  mov     eax, edi
0x1800b3b9a  jmp     loc_1800B3F64
0x1800b3b9f  mov     rax, [rsi+8]
0x1800b3ba3  mov     rdx, [rax+r14*8]
0x1800b3ba7  mov     r8d, [rdx+4]; Size
0x1800b3bab  mov     rdx, [rdx+8]; Src
0x1800b3baf  mov     rcx, r13; void *
0x1800b3bb2  call    memcpy_0
0x1800b3bb7  mov     rax, [rsi+8]
0x1800b3bbb  mov     rcx, [rax+r14*8]
0x1800b3bbf  mov     rax, [rcx+18h]
0x1800b3bc3  mov     ecx, [rax+4]; cb
0x1800b3bc6  call    cs:__imp_CoTaskMemAlloc
0x1800b3bcc  mov     r9, rax
0x1800b3bcf  mov     [rsp+0D8h+var_A8], rax
0x1800b3bd4  test    rax, rax
0x1800b3bd7  jnz     short loc_1800B3C10
0x1800b3bd9  mov     rcx, [rsp+0D8h]; this
0x1800b3be1  mov     edi, 8007000Eh
0x1800b3be6  mov     r9d, edi; char *
0x1800b3be9  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3bf0  mov     edx, 0B7Bh; void *
0x1800b3bf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3bfa  nop
0x1800b3bfb  test    rbx, rbx
0x1800b3bfe  jz      short loc_1800B3C09
0x1800b3c00  mov     rcx, rbx; pv
0x1800b3c03  call    cs:__imp_CoTaskMemFree
0x1800b3c09  mov     eax, edi
0x1800b3c0b  jmp     loc_1800B3F64
0x1800b3c10  mov     rax, [rsi+8]
0x1800b3c14  mov     rcx, [rax+r14*8]
0x1800b3c18  mov     rdx, [rcx+18h]
0x1800b3c1c  mov     r8d, [rdx+4]; Size
0x1800b3c20  mov     rdx, [rdx+8]; Src
0x1800b3c24  mov     rcx, r9; void *
0x1800b3c27  call    memcpy_0
0x1800b3c2c  mov     rax, [rsi+8]
0x1800b3c30  mov     rdx, [rax+r14*8]
0x1800b3c34  mov     eax, [rdx+4]
0x1800b3c37  mov     [rsp+0D8h+var_80], eax
0x1800b3c3b  xor     eax, eax
0x1800b3c3d  mov     [rsp+0D8h+var_7C], eax
0x1800b3c41  mov     [rsp+0D8h+var_78], r13
0x1800b3c46  mov     rdx, [rdx+10h]
0x1800b3c4a  mov     rdx, [rdx+8]
0x1800b3c4e  lea     rcx, [rsp+0D8h+var_88]
0x1800b3c53  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b3c58  nop
0x1800b3c59  mov     rcx, [rax]
0x1800b3c5c  xor     r13d, r13d
0x1800b3c5f  mov     [rax], r13
0x1800b3c62  mov     [rsp+0D8h+var_70], rcx
0x1800b3c67  mov     rax, [rsi+8]
0x1800b3c6b  mov     rcx, [rax+r14*8]
0x1800b3c6f  mov     rdx, [rcx+10h]
0x1800b3c73  mov     rdx, [rdx+10h]
0x1800b3c77  lea     rcx, [rsp+0D8h+var_90]
0x1800b3c7c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b3c81  nop
0x1800b3c82  mov     rcx, [rax]
0x1800b3c85  mov     [rax], r13
0x1800b3c88  mov     [rsp+0D8h+var_68], rcx
0x1800b3c8d  mov     rax, [rsi+8]
0x1800b3c91  mov     rcx, [rax+r14*8]
0x1800b3c95  mov     rdx, [rcx+18h]
0x1800b3c99  mov     eax, [rdx+4]
0x1800b3c9c  mov     [rsp+0D8h+var_60], eax
0x1800b3ca0  xor     eax, eax
0x1800b3ca2  mov     [rsp+0D8h+var_5C], eax
0x1800b3ca6  mov     rax, [rsp+0D8h+var_A8]
0x1800b3cab  mov     [rsp+0D8h+var_58], rax
0x1800b3cb3  mov     rdx, [rdx+10h]
0x1800b3cb7  lea     rcx, [rsp+0D8h+var_98]
0x1800b3cbc  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b3cc1  nop
0x1800b3cc2  mov     rcx, [rax]
0x1800b3cc5  mov     [rax], r13
0x1800b3cc8  mov     [rsp+0D8h+var_50], rcx
0x1800b3cd0  mov     rax, [rsi+8]
0x1800b3cd4  mov     rcx, [rax+r14*8]
0x1800b3cd8  mov     rax, [rcx+18h]
0x1800b3cdc  mov     rdx, [rax+20h]
0x1800b3ce0  test    rdx, rdx
0x1800b3ce3  jz      short loc_1800B3D0A
0x1800b3ce5  lea     rcx, [rsp+0D8h+var_A0]
0x1800b3cea  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b3cef  nop
0x1800b3cf0  or      edi, 1
0x1800b3cf3  mov     [rsp+0D8h+arg_0], edi
0x1800b3cfa  mov     rcx, [rax]
0x1800b3cfd  mov     [rax], r13
0x1800b3d00  mov     [rsp+0D8h+var_48], rcx
0x1800b3d08  jmp     short loc_1800B3D12
0x1800b3d0a  mov     [rsp+0D8h+var_48], r13
0x1800b3d12  lea     rdx, [rsp+0D8h+var_80]
0x1800b3d17  lea     rcx, [rsp+0D8h+var_B8]
0x1800b3d1c  call    ??$make_unique_cotaskmem@U_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@U1@@wil@@YA?AV?$unique_ptr@U_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@$$QEAU_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@@Z; wil::make_unique_cotaskmem<_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS,_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS>(_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS &&)
0x1800b3d21  nop
0x1800b3d22  test    dil, 1
0x1800b3d26  jz      short loc_1800B3D3D
0x1800b3d28  and     edi, 0FFFFFFFEh
0x1800b3d2b  mov     [rsp+0D8h+arg_0], edi
0x1800b3d32  lea     rcx, [rsp+0D8h+var_A0]
0x1800b3d37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b3d3c  nop
0x1800b3d3d  lea     rcx, [rsp+0D8h+var_98]
0x1800b3d42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b3d47  nop
0x1800b3d48  lea     rcx, [rsp+0D8h+var_90]
0x1800b3d4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b3d52  nop
0x1800b3d53  lea     rcx, [rsp+0D8h+var_88]
0x1800b3d58  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b3d5d  mov     rax, [rsp+0D8h+var_B8]
0x1800b3d62  test    rax, rax
0x1800b3d65  jz      short loc_1800B3DA4
0x1800b3d67  movups  xmm0, xmmword ptr [rax]
0x1800b3d6a  movups  xmm1, xmmword ptr [rax+10h]
0x1800b3d6e  movups  xmm2, xmmword ptr [rax+20h]
0x1800b3d72  movups  xmm3, xmmword ptr [rax+30h]
0x1800b3d76  shl     r14, 6
0x1800b3d7a  movups  xmmword ptr [r14+rbx], xmm0
0x1800b3d7f  movups  xmmword ptr [r14+rbx+10h], xmm1
0x1800b3d85  movups  xmmword ptr [r14+rbx+20h], xmm2
0x1800b3d8b  movups  xmmword ptr [r14+rbx+30h], xmm3
0x1800b3d91  mov     [rsp+0D8h+var_B8], r13
0x1800b3d96  mov     eax, [rsp+0D8h+arg_18]
0x1800b3d9d  inc     eax
0x1800b3d9f  jmp     loc_1800B3AD3
0x1800b3da4  mov     rcx, [rsp+0D8h]; this
0x1800b3dac  mov     edi, 8007000Eh
0x1800b3db1  mov     r9d, edi; char *
0x1800b3db4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3dbb  mov     edx, 0B8Bh; void *
0x1800b3dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3dc5  mov     rcx, [rsp+0D8h+var_B8]; pv
0x1800b3dca  mov     [rsp+0D8h+var_B8], r13
0x1800b3dcf  test    rcx, rcx
0x1800b3dd2  jz      short loc_1800B3DDB
0x1800b3dd4  call    cs:__imp_CoTaskMemFree
0x1800b3dda  nop
0x1800b3ddb  test    rbx, rbx
0x1800b3dde  jz      short loc_1800B3DE9
0x1800b3de0  mov     rcx, rbx; pv
0x1800b3de3  call    cs:__imp_CoTaskMemFree
0x1800b3de9  mov     eax, edi
0x1800b3deb  jmp     loc_1800B3F64
0x1800b3df0  mov     rcx, [rsp+0D8h]; this
0x1800b3df8  mov     edi, 80070057h
0x1800b3dfd  mov     r9d, edi; char *
0x1800b3e00  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3e07  mov     edx, 0B72h; void *
0x1800b3e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3e11  nop
0x1800b3e12  test    rbx, rbx
0x1800b3e15  jz      short loc_1800B3E20
0x1800b3e17  mov     rcx, rbx; pv
0x1800b3e1a  call    cs:__imp_CoTaskMemFree
0x1800b3e20  mov     eax, edi
0x1800b3e22  jmp     loc_1800B3F64
0x1800b3e27  mov     rcx, [rsp+0D8h]; this
0x1800b3e2f  mov     edi, 80070057h
0x1800b3e34  mov     r9d, edi; char *
0x1800b3e37  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3e3e  mov     edx, 0B71h; void *
0x1800b3e43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3e48  nop
0x1800b3e49  test    rbx, rbx
0x1800b3e4c  jz      short loc_1800B3E57
0x1800b3e4e  mov     rcx, rbx; pv
0x1800b3e51  call    cs:__imp_CoTaskMemFree
0x1800b3e57  mov     eax, edi
0x1800b3e59  jmp     loc_1800B3F64
0x1800b3e5e  mov     rcx, [rsp+0D8h]; this
0x1800b3e66  mov     edi, 80070057h
0x1800b3e6b  mov     r9d, edi; char *
0x1800b3e6e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3e75  mov     edx, 0B70h; void *
0x1800b3e7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3e7f  nop
0x1800b3e80  test    rbx, rbx
0x1800b3e83  jz      short loc_1800B3E8E
0x1800b3e85  mov     rcx, rbx; pv
0x1800b3e88  call    cs:__imp_CoTaskMemFree
0x1800b3e8e  mov     eax, edi
0x1800b3e90  jmp     loc_1800B3F64
0x1800b3e95  mov     rcx, [rsp+0D8h]; this
0x1800b3e9d  mov     edi, 80070057h
0x1800b3ea2  mov     r9d, edi; char *
0x1800b3ea5  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3eac  mov     edx, 0B6Fh; void *
0x1800b3eb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3eb6  nop
0x1800b3eb7  test    rbx, rbx
0x1800b3eba  jz      short loc_1800B3EC5
0x1800b3ebc  mov     rcx, rbx; pv
0x1800b3ebf  call    cs:__imp_CoTaskMemFree
0x1800b3ec5  mov     eax, edi
0x1800b3ec7  jmp     loc_1800B3F64
0x1800b3ecc  mov     rcx, [rsp+0D8h]; this
0x1800b3ed4  mov     edi, 80070057h
0x1800b3ed9  mov     r9d, edi; char *
0x1800b3edc  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3ee3  mov     edx, 0B6Eh; void *
0x1800b3ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3eed  nop
0x1800b3eee  test    rbx, rbx
0x1800b3ef1  jz      short loc_1800B3EFC
0x1800b3ef3  mov     rcx, rbx; pv
0x1800b3ef6  call    cs:__imp_CoTaskMemFree
0x1800b3efc  mov     eax, edi
0x1800b3efe  jmp     short loc_1800B3F64
0x1800b3f00  mov     [r15], rbx
0x1800b3f03  mov     rax, [rsp+0D8h+arg_10]
0x1800b3f0b  mov     [rax], r12d
0x1800b3f0e  xor     eax, eax
0x1800b3f10  jmp     short loc_1800B3F64
0x1800b3f12  mov     rcx, [rsp+0D8h]; this
0x1800b3f1a  mov     edi, 8007000Eh
0x1800b3f1f  mov     r9d, edi; char *
0x1800b3f22  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b3f29  mov     edx, 0B69h; void *
0x1800b3f2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3f33  nop
0x1800b3f34  mov     eax, edi
  ... truncated ...
```
