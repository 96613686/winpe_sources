# SCRIPT_MAP_CUSTOM_MAPPER::DoesScriptMapMatch(CONFIG_ELEMENT_LIST *,META_SCRIPT_ENTRY *,INativeConfigurationElement * *,int *,int *)

- ea: `0x18001ca24`
- end: `0x18001cd7c`
- name: `?DoesScriptMapMatch@SCRIPT_MAP_CUSTOM_MAPPER@@AEAAJPEAVCONFIG_ELEMENT_LIST@@PEAVMETA_SCRIPT_ENTRY@@PEAPEAVINativeConfigurationElement@@PEAH3@Z`
- size: `856`
- prototype: `__int64 __fastcall(SCRIPT_MAP_CUSTOM_MAPPER *__hidden this, struct CONFIG_ELEMENT_LIST *, struct META_SCRIPT_ENTRY *, struct INativeConfigurationElement **, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024a10`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18001ca24`
- `0x180026a60`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001cb5c`
- `msvcrt!_wcsicmp` at `0x18001ccca`
- `msvcrt!_wcsicmp` at `0x18001cce8`
- `msvcrt!_wcsicmp` at `0x18001cd17`
- `msvcrt!_wcsicmp` at `0x18001cb5c`
- `msvcrt!_wcsicmp` at `0x18001ccca`
- `msvcrt!_wcsicmp` at `0x18001cce8`
- `msvcrt!_wcsicmp` at `0x18001cd17`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ccb1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ccda`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001cd09`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ccb1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001ccda`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001cd09`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001cb13`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001cb13`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cab2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001cab2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cd51`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001cd51`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ccbe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001ccbe`

## string_xrefs

- `0x18001cb55`: `ServerSideIncludeModule`
- `0x18001cc36`: `requireAccess`

## pseudocode

```c
__int64 __fastcall SCRIPT_MAP_CUSTOM_MAPPER::DoesScriptMapMatch(
        SCRIPT_MAP_CUSTOM_MAPPER *this,
        struct CONFIG_ELEMENT_LIST *a2,
        struct META_SCRIPT_ENTRY *a3,
        struct INativeConfigurationElement **a4,
        int *a5,
        int *a6)
{
  int v6; // r14d
  int v10; // edi
  unsigned int v11; // r15d
  BUFFER *v12; // rax
  struct INativeConfigurationElement *v13; // rsi
  SCRIPT_MAP_CUSTOM_MAPPER *v14; // rbx
  const WCHAR *v15; // rcx
  const wchar_t *Str; // rbx
  const wchar_t *v17; // rax
  const wchar_t *v18; // rax
  const wchar_t *v19; // rax
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSrc; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-C0h]
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  SCRIPT_MAP_CUSTOM_MAPPER *v25; // [rsp+50h] [rbp-B0h]
  wchar_t *v26; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v27; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement **v28; // [rsp+68h] [rbp-98h]
  int *v29; // [rsp+70h] [rbp-90h]
  BUFFER *i; // [rsp+78h] [rbp-88h]
  _BYTE v31[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v32[256]; // [rsp+C0h] [rbp-40h] BYREF

  v6 = 0;
  v25 = this;
  v29 = a6;
  String1 = 0;
  lpSrc = 0;
  v26 = 0;
  v27 = 0;
  v21 = 0;
  v28 = a4;
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v31, v32, 0x100u);
  if ( a2 && a3 && a4 && a5 && a6 )
  {
    v10 = 0;
    *a4 = 0;
    *a5 = 0;
    *a6 = 0;
    v11 = 0;
    v23 = *(_DWORD *)a2;
    if ( v23 )
    {
      v12 = (struct CONFIG_ELEMENT_LIST *)((char *)a2 + 8);
      for ( i = (struct CONFIG_ELEMENT_LIST *)((char *)a2 + 8); ; v12 = i )
      {
        v13 = (struct INativeConfigurationElement *)*((_QWORD *)BUFFER::QueryPtr(v12) + v11);
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                v13,
                L"modules",
                &String1,
                0,
                0);
        if ( v10 < 0 )
          break;
        if ( _wcsicmp(String1, L"ServerSideIncludeModule") )
        {
          v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                  v13,
                  L"scriptProcessor",
                  &lpSrc,
                  0,
                  0);
          if ( v10 < 0 )
            break;
          v15 = lpSrc;
          v14 = v25;
        }
        else
        {
          v14 = v25;
          v15 = (const WCHAR *)((char *)v25 + 8);
          lpSrc = (LPCWSTR)((char *)v25 + 8);
        }
        v10 = ExpandEnvironmentVariables(v15, (struct STRU *)v31);
        if ( v10 < 0 )
          break;
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                v13,
                L"verb",
                &v27,
                0,
                0);
        if ( v10 < 0 )
          break;
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                v13,
                L"path",
                &v26,
                0,
                0);
        if ( v10 < 0 )
          break;
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(
                v13,
                L"requireAccess",
                &v21,
                0,
                0);
        if ( v10 < 0 )
          break;
        if ( v21 == 3 )
          v6 |= 1u;
        v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(
                v13,
                L"resourceType",
                &v21,
                0,
                0);
        if ( v10 < 0 )
          break;
        if ( !v21 )
          v6 |= 4u;
        if ( !*lpSrc )
          lpSrc = (LPCWSTR)((char *)v14 + 8);
        Str = STRU::QueryStr(a3);
        v17 = STRU::QueryStr((STRU *)v31);
        if ( !_wcsicmp(v17, Str) )
        {
          v18 = STRU::QueryStr((struct META_SCRIPT_ENTRY *)((char *)a3 + 112));
          if ( !_wcsicmp(v26, v18) )
          {
            *v28 = v13;
            *v29 = 1;
            v19 = STRU::QueryStr((struct META_SCRIPT_ENTRY *)((char *)a3 + 56));
            if ( !_wcsicmp(v27, v19) && v6 == *((_DWORD *)a3 + 42) )
            {
              *a5 = 1;
              break;
            }
          }
        }
        if ( ++v11 >= v23 )
          break;
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
  STRU::~STRU((STRU *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001ca24  push    rbp
0x18001ca26  push    rbx
0x18001ca27  push    rsi
0x18001ca28  push    rdi
0x18001ca29  push    r12
0x18001ca2b  push    r13
0x18001ca2d  push    r14
0x18001ca2f  push    r15
0x18001ca31  lea     rbp, [rsp-1D8h]
0x18001ca39  sub     rsp, 2D8h
0x18001ca40  mov     rax, cs:__security_cookie
0x18001ca47  xor     rax, rsp
0x18001ca4a  mov     [rbp+210h+var_50], rax
0x18001ca51  mov     r15, [rbp+210h+arg_28]
0x18001ca58  xor     r14d, r14d
0x18001ca5b  mov     r12, [rbp+210h+arg_20]
0x18001ca62  mov     r13, r8
0x18001ca65  mov     rbx, rdx
0x18001ca68  mov     [rsp+310h+var_2C0], rcx
0x18001ca6d  xor     edx, edx; Val
0x18001ca6f  mov     [rsp+310h+var_2A0], r15
0x18001ca74  mov     r8d, 200h; Size
0x18001ca7a  mov     [rsp+310h+String1], r14
0x18001ca7f  lea     rcx, [rbp+210h+var_250]; void *
0x18001ca83  mov     [rsp+310h+lpSrc], r14
0x18001ca88  mov     [rsp+310h+var_2B8], r14
0x18001ca8d  mov     rsi, r9
0x18001ca90  mov     [rsp+310h+var_2B0], r14
0x18001ca95  mov     [rsp+310h+var_2E0], r14d
0x18001ca9a  mov     [rsp+310h+var_2A8], r9
0x18001ca9f  call    memset_0
0x18001caa4  mov     r8d, 100h
0x18001caaa  lea     rdx, [rbp+210h+var_250]
0x18001caae  lea     rcx, [rbp+210h+var_290]
0x18001cab2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001cab8  test    rbx, rbx
0x18001cabb  jz      loc_18001CD48
0x18001cac1  test    r13, r13
0x18001cac4  jz      loc_18001CD48
0x18001caca  test    rsi, rsi
0x18001cacd  jz      loc_18001CD48
0x18001cad3  test    r12, r12
0x18001cad6  jz      loc_18001CD48
0x18001cadc  test    r15, r15
0x18001cadf  jz      loc_18001CD48
0x18001cae5  xor     ecx, ecx
0x18001cae7  mov     edi, r14d
0x18001caea  mov     [rsi], rcx
0x18001caed  mov     [r12], ecx
0x18001caf1  mov     [r15], ecx
0x18001caf4  mov     r15d, ecx
0x18001caf7  mov     eax, [rbx]
0x18001caf9  mov     [rsp+310h+var_2D0], eax
0x18001cafd  test    eax, eax
0x18001caff  jz      loc_18001CD4D
0x18001cb05  lea     rax, [rbx+8]
0x18001cb09  xor     ebx, ebx
0x18001cb0b  mov     [rsp+310h+var_298], rax
0x18001cb10  mov     rcx, rax
0x18001cb13  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001cb19  xor     r9d, r9d
0x18001cb1c  mov     [rsp+310h+var_2F0], rbx
0x18001cb21  mov     rcx, rax
0x18001cb24  lea     r8, [rsp+310h+String1]
0x18001cb29  mov     eax, r15d
0x18001cb2c  lea     rdx, aModules; "modules"
0x18001cb33  mov     rsi, [rcx+rax*8]
0x18001cb37  mov     rcx, rsi
0x18001cb3a  mov     rax, [rsi]
0x18001cb3d  mov     rax, [rax+40h]
0x18001cb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb46  mov     edi, eax
0x18001cb48  test    eax, eax
0x18001cb4a  js      loc_18001CD4D
0x18001cb50  mov     rcx, [rsp+310h+String1]; String1
0x18001cb55  lea     rdx, aServersideincl; "ServerSideIncludeModule"
0x18001cb5c  call    cs:__imp__wcsicmp
0x18001cb62  test    eax, eax
0x18001cb64  jnz     short loc_18001CB76
0x18001cb66  mov     rbx, [rsp+310h+var_2C0]
0x18001cb6b  lea     rcx, [rbx+8]
0x18001cb6f  mov     [rsp+310h+lpSrc], rcx
0x18001cb74  jmp     short loc_18001CBAD
0x18001cb76  mov     rax, [rsi]
0x18001cb79  lea     r8, [rsp+310h+lpSrc]
0x18001cb7e  xor     r9d, r9d
0x18001cb81  mov     [rsp+310h+var_2F0], rbx
0x18001cb86  lea     rdx, aScriptprocesso; "scriptProcessor"
0x18001cb8d  mov     rcx, rsi
0x18001cb90  mov     rax, [rax+40h]
0x18001cb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb99  mov     edi, eax
0x18001cb9b  test    eax, eax
0x18001cb9d  js      loc_18001CD4D
0x18001cba3  mov     rcx, [rsp+310h+lpSrc]; lpSrc
0x18001cba8  mov     rbx, [rsp+310h+var_2C0]
0x18001cbad  lea     rdx, [rbp+210h+var_290]; struct STRU *
0x18001cbb1  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x18001cbb6  mov     edi, eax
0x18001cbb8  test    eax, eax
0x18001cbba  js      loc_18001CD4D
0x18001cbc0  mov     rax, [rsi]
0x18001cbc3  lea     r8, [rsp+310h+var_2B0]
0x18001cbc8  xor     r9d, r9d
0x18001cbcb  mov     [rsp+310h+var_2F0], 0
0x18001cbd4  lea     rdx, aVerb; "verb"
0x18001cbdb  mov     rcx, rsi
0x18001cbde  mov     rax, [rax+40h]
0x18001cbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbe7  mov     edi, eax
0x18001cbe9  test    eax, eax
0x18001cbeb  js      loc_18001CD4D
0x18001cbf1  mov     rax, [rsi]
0x18001cbf4  lea     r8, [rsp+310h+var_2B8]
0x18001cbf9  xor     r9d, r9d
0x18001cbfc  mov     [rsp+310h+var_2F0], 0
0x18001cc05  lea     rdx, aPath; "path"
0x18001cc0c  mov     rcx, rsi
0x18001cc0f  mov     rax, [rax+40h]
0x18001cc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc18  mov     edi, eax
0x18001cc1a  test    eax, eax
0x18001cc1c  js      loc_18001CD4D
0x18001cc22  mov     rax, [rsi]
0x18001cc25  lea     r8, [rsp+310h+var_2E0]
0x18001cc2a  xor     r9d, r9d
0x18001cc2d  mov     [rsp+310h+var_2F0], 0
0x18001cc36  lea     rdx, aRequireaccess; "requireAccess"
0x18001cc3d  mov     rcx, rsi
0x18001cc40  mov     rax, [rax+30h]
0x18001cc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc49  mov     edi, eax
0x18001cc4b  test    eax, eax
0x18001cc4d  js      loc_18001CD4D
0x18001cc53  cmp     [rsp+310h+var_2E0], 3
0x18001cc58  jnz     short loc_18001CC5E
0x18001cc5a  or      r14d, 1
0x18001cc5e  mov     rax, [rsi]
0x18001cc61  lea     r8, [rsp+310h+var_2E0]
0x18001cc66  xor     r9d, r9d
0x18001cc69  mov     [rsp+310h+var_2F0], 0
0x18001cc72  lea     rdx, aResourcetype; "resourceType"
0x18001cc79  mov     rcx, rsi
0x18001cc7c  mov     rax, [rax+30h]
0x18001cc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc85  xor     ecx, ecx
0x18001cc87  mov     edi, eax
0x18001cc89  test    eax, eax
0x18001cc8b  js      loc_18001CD4D
0x18001cc91  cmp     [rsp+310h+var_2E0], ecx
0x18001cc95  jnz     short loc_18001CC9B
0x18001cc97  or      r14d, 4
0x18001cc9b  mov     rax, [rsp+310h+lpSrc]
0x18001cca0  cmp     [rax], cx
0x18001cca3  jnz     short loc_18001CCAE
0x18001cca5  lea     rax, [rbx+8]
0x18001cca9  mov     [rsp+310h+lpSrc], rax
0x18001ccae  mov     rcx, r13
0x18001ccb1  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001ccb7  lea     rcx, [rbp+210h+var_290]
0x18001ccbb  mov     rbx, rax
0x18001ccbe  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001ccc4  mov     rcx, rax; String1
0x18001ccc7  mov     rdx, rbx; String2
0x18001ccca  call    cs:__imp__wcsicmp
0x18001ccd0  xor     ebx, ebx
0x18001ccd2  test    eax, eax
0x18001ccd4  jnz     short loc_18001CD2A
0x18001ccd6  lea     rcx, [r13+70h]
0x18001ccda  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001cce0  mov     rcx, [rsp+310h+var_2B8]; String1
0x18001cce5  mov     rdx, rax; String2
0x18001cce8  call    cs:__imp__wcsicmp
0x18001ccee  test    eax, eax
0x18001ccf0  jnz     short loc_18001CD2A
0x18001ccf2  mov     rax, [rsp+310h+var_2A8]
0x18001ccf7  lea     rcx, [r13+38h]
0x18001ccfb  mov     [rax], rsi
0x18001ccfe  mov     rax, [rsp+310h+var_2A0]
0x18001cd03  mov     dword ptr [rax], 1
0x18001cd09  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001cd0f  mov     rcx, [rsp+310h+var_2B0]; String1
0x18001cd14  mov     rdx, rax; String2
0x18001cd17  call    cs:__imp__wcsicmp
0x18001cd1d  test    eax, eax
0x18001cd1f  jnz     short loc_18001CD2A
0x18001cd21  cmp     r14d, [r13+0A8h]
0x18001cd28  jz      short loc_18001CD3E
0x18001cd2a  inc     r15d
0x18001cd2d  cmp     r15d, [rsp+310h+var_2D0]
0x18001cd32  jnb     short loc_18001CD4D
0x18001cd34  mov     rax, [rsp+310h+var_298]
0x18001cd39  jmp     loc_18001CB10
0x18001cd3e  mov     dword ptr [r12], 1
0x18001cd46  jmp     short loc_18001CD4D
0x18001cd48  mov     edi, 80070057h
0x18001cd4d  lea     rcx, [rbp+210h+var_290]
0x18001cd51  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001cd57  mov     eax, edi
0x18001cd59  mov     rcx, [rbp+210h+var_50]
0x18001cd60  xor     rcx, rsp; StackCookie
0x18001cd63  call    __security_check_cookie
0x18001cd68  add     rsp, 2D8h
0x18001cd6f  pop     r15
0x18001cd71  pop     r14
0x18001cd73  pop     r13
0x18001cd75  pop     r12
0x18001cd77  pop     rdi
0x18001cd78  pop     rsi
0x18001cd79  pop     rbx
0x18001cd7a  pop     rbp
0x18001cd7b  retn
```
