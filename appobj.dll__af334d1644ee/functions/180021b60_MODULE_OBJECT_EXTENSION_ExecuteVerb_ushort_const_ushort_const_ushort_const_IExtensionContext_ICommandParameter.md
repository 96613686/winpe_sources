# MODULE_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180021b60`
- end: `0x180021f74`
- name: `?ExecuteVerb@MODULE_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(MODULE_OBJECT_EXTENSION *this, const unsigned __int16 *, wchar_t *String1, unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180020674`
- `0x180020fd8`
- `0x180021658`
- `0x180021b60`
- `0x18002bcd4`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021bed`
- `msvcrt!_wcsicmp` at `0x180021c2a`
- `msvcrt!_wcsicmp` at `0x180021c70`
- `msvcrt!_wcsicmp` at `0x180021cb9`
- `msvcrt!_wcsicmp` at `0x180021e9c`
- `msvcrt!_wcsicmp` at `0x180021ed7`
- `msvcrt!_wcsicmp` at `0x180021bed`
- `msvcrt!_wcsicmp` at `0x180021c2a`
- `msvcrt!_wcsicmp` at `0x180021c70`
- `msvcrt!_wcsicmp` at `0x180021cb9`
- `msvcrt!_wcsicmp` at `0x180021e9c`
- `msvcrt!_wcsicmp` at `0x180021ed7`

## string_xrefs

- `0x180021ecd`: `DELETE`
- `0x180021c66`: `INSTALL`
- `0x180021caf`: `UNINSTALL`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::ExecuteVerb(
        MODULE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        wchar_t *String1,
        unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  struct IExtensionContext *v11; // rdi
  struct ICommandParameterList *v12; // r14
  struct ICommandObjectList *v13; // r15
  int v14; // eax
  int v15; // ebx
  APP_OBJECT_UTILS *v16; // rcx
  APP_OBJECT_UTILS *v17; // rcx
  __int64 v18; // r8
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+40h] [rbp-30h] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h] BYREF
  __int64 v24; // [rsp+50h] [rbp-20h] BYREF
  __int64 v25; // [rsp+58h] [rbp-18h] BYREF
  __int128 v26; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v28; // [rsp+C8h] [rbp+58h] BYREF

  v28 = a4;
  v22 = 0;
  v27 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  if ( !a2 || !String1 || !a4 || (v11 = a5) == 0 || (v12 = a6) == 0 || (v13 = a7) == 0 )
  {
    v15 = -2147024809;
    goto LABEL_41;
  }
  if ( !_wcsicmp(String1, L"LIST") )
  {
    v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)v11 + 56LL))(
            v11,
            a2,
            v28,
            v12,
            v13,
            0);
LABEL_9:
    v15 = v14;
    goto LABEL_41;
  }
  if ( _wcsicmp(String1, L"ADD") )
  {
    if ( !_wcsicmp(String1, L"INSTALL") )
    {
      v15 = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v17, v11, v28);
      if ( v15 >= 0 )
      {
        v14 = MODULE_OBJECT_EXTENSION::DoInstall(this, v12, v11, v13, a8);
        goto LABEL_9;
      }
      goto LABEL_41;
    }
    if ( !_wcsicmp(String1, L"UNINSTALL") )
    {
      v14 = MODULE_OBJECT_EXTENSION::DoUnInstall(this, a2, v28, v12, v11, v13);
      goto LABEL_9;
    }
    v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)v11 + 184LL))(v11, &v22);
    if ( v15 < 0 )
      goto LABEL_41;
    v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)v11 + 192LL))(v11, &v23);
    if ( v15 < 0 )
      goto LABEL_41;
    if ( *v28
      || (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v12 + 40LL))(
           v12,
           L"MODULE.NAME",
           &v28) >= 0
      && *v28 )
    {
      if ( (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v12 + 40LL))(
             v12,
             L"APP.NAME",
             &v25) >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v23 + 56LL))(
                v23,
                L"APP.NAME",
                v25);
        if ( v15 < 0 )
          goto LABEL_41;
      }
      v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, __int64, __int64, _DWORD))(*(_QWORD *)v11 + 56LL))(
              v11,
              a2,
              v28,
              v23,
              v22,
              0);
      if ( v15 < 0 )
        goto LABEL_41;
      v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 32LL))(v22, &v27);
      if ( v15 < 0 )
        goto LABEL_41;
      if ( v27 )
      {
        if ( v27 <= 1 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, 0, &v24);
          if ( v15 >= 0 )
          {
            if ( !_wcsicmp(String1, L"SET") )
            {
              v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, _DWORD))(*(_QWORD *)v11 + 168LL))(
                      v11,
                      v24,
                      v12,
                      v13,
                      a8,
                      0);
              goto LABEL_9;
            }
            if ( !_wcsicmp(String1, L"DELETE") )
            {
              v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, struct ICommandObjectList *))(*(_QWORD *)v11 + 176LL))(
                      v11,
                      v24,
                      v13);
              goto LABEL_9;
            }
            v15 = -2147024846;
          }
          goto LABEL_41;
        }
        v15 = -2147024846;
        *((_QWORD *)&v26 + 1) = String1;
        v20 = 2147942450LL;
        *(_QWORD *)&v26 = L"MODULE";
        v18 = 3221226475LL;
LABEL_25:
        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)v11 + 144LL))(
          v11,
          v20,
          v18,
          &v26,
          0);
        goto LABEL_41;
      }
      v18 = 3221226521LL;
      *(_QWORD *)&v26 = L"MODULE";
      v19 = v28;
    }
    else
    {
      v18 = 3221226474LL;
      *(_QWORD *)&v26 = L"MODULE";
      v19 = L"MODULE.NAME";
    }
    v20 = 2147942402LL;
    *((_QWORD *)&v26 + 1) = v19;
    v15 = -2147024894;
    goto LABEL_25;
  }
  v15 = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v16, v11, v28);
  if ( v15 >= 0 )
  {
    v14 = MODULE_OBJECT_EXTENSION::DoAdd(this, v12, v11, v13, a8);
    goto LABEL_9;
  }
LABEL_41:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180021b60  mov     [rsp-38h+arg_0], rbx
0x180021b65  mov     [rsp-38h+arg_18], r9
0x180021b6a  push    rbp
0x180021b6b  push    rsi
0x180021b6c  push    rdi
0x180021b6d  push    r12
0x180021b6f  push    r13
0x180021b71  push    r14
0x180021b73  push    r15
0x180021b75  mov     rbp, rsp
0x180021b78  sub     rsp, 70h
0x180021b7c  xor     ebx, ebx
0x180021b7e  xorps   xmm0, xmm0
0x180021b81  mov     [rbp+var_30], rbx
0x180021b85  mov     rsi, r8
0x180021b88  mov     [rbp+arg_8], ebx
0x180021b8b  mov     r13, rdx
0x180021b8e  mov     [rbp+var_28], rbx
0x180021b92  mov     r12, rcx
0x180021b95  mov     [rbp+var_18], rbx
0x180021b99  mov     [rbp+var_20], rbx
0x180021b9d  movups  [rbp+var_10], xmm0
0x180021ba1  test    rdx, rdx
0x180021ba4  jz      loc_180021F06
0x180021baa  test    r8, r8
0x180021bad  jz      loc_180021F06
0x180021bb3  test    r9, r9
0x180021bb6  jz      loc_180021F06
0x180021bbc  mov     rdi, [rbp+arg_20]
0x180021bc0  test    rdi, rdi
0x180021bc3  jz      loc_180021F06
0x180021bc9  mov     r14, [rbp+arg_28]
0x180021bcd  test    r14, r14
0x180021bd0  jz      loc_180021F06
0x180021bd6  mov     r15, [rbp+arg_30]
0x180021bda  test    r15, r15
0x180021bdd  jz      loc_180021F06
0x180021be3  lea     rdx, aList; "LIST"
0x180021bea  mov     rcx, r8; String1
0x180021bed  call    cs:__imp__wcsicmp
0x180021bf3  test    eax, eax
0x180021bf5  jnz     short loc_180021C20
0x180021bf7  mov     rax, [rdi]
0x180021bfa  mov     r9, r14
0x180021bfd  mov     r8, [rbp+arg_18]
0x180021c01  mov     rdx, r13
0x180021c04  mov     dword ptr [rsp+70h+var_48], ebx
0x180021c08  mov     [rsp+70h+var_50], r15
0x180021c0d  mov     rax, [rax+38h]
0x180021c11  mov     rcx, rdi
0x180021c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c19  mov     ebx, eax
0x180021c1b  jmp     loc_180021F0B
0x180021c20  lea     rdx, aAdd_0; "ADD"
0x180021c27  mov     rcx, rsi; String1
0x180021c2a  call    cs:__imp__wcsicmp
0x180021c30  test    eax, eax
0x180021c32  jnz     short loc_180021C66
0x180021c34  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180021c38  mov     rdx, rdi; struct IExtensionContext *
0x180021c3b  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x180021c40  mov     ebx, eax
0x180021c42  test    eax, eax
0x180021c44  js      loc_180021F0B
0x180021c4a  mov     rax, [rbp+arg_38]
0x180021c4e  mov     r9, r15; struct ICommandObjectList *
0x180021c51  mov     r8, rdi; struct IExtensionContext *
0x180021c54  mov     [rsp+70h+var_50], rax; struct IXMLDOMDocument *
0x180021c59  mov     rdx, r14; struct ICommandParameterList *
0x180021c5c  mov     rcx, r12; this
0x180021c5f  call    ?DoAdd@MODULE_OBJECT_EXTENSION@@AEAAJPEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; MODULE_OBJECT_EXTENSION::DoAdd(ICommandParameterList *,IExtensionContext *,ICommandObjectList *,IXMLDOMDocument *)
0x180021c64  jmp     short loc_180021C19
0x180021c66  lea     rdx, aInstall_0; "INSTALL"
0x180021c6d  mov     rcx, rsi; String1
0x180021c70  call    cs:__imp__wcsicmp
0x180021c76  test    eax, eax
0x180021c78  jnz     short loc_180021CAF
0x180021c7a  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180021c7e  mov     rdx, rdi; struct IExtensionContext *
0x180021c81  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x180021c86  mov     ebx, eax
0x180021c88  test    eax, eax
0x180021c8a  js      loc_180021F0B
0x180021c90  mov     rax, [rbp+arg_38]
0x180021c94  mov     r9, r15; struct ICommandObjectList *
0x180021c97  mov     r8, rdi; struct IExtensionContext *
0x180021c9a  mov     [rsp+70h+var_50], rax; struct IXMLDOMDocument *
0x180021c9f  mov     rdx, r14; struct ICommandParameterList *
0x180021ca2  mov     rcx, r12; this
0x180021ca5  call    ?DoInstall@MODULE_OBJECT_EXTENSION@@AEAAJPEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; MODULE_OBJECT_EXTENSION::DoInstall(ICommandParameterList *,IExtensionContext *,ICommandObjectList *,IXMLDOMDocument *)
0x180021caa  jmp     loc_180021C19
0x180021caf  lea     rdx, aUninstall; "UNINSTALL"
0x180021cb6  mov     rcx, rsi; String1
0x180021cb9  call    cs:__imp__wcsicmp
0x180021cbf  test    eax, eax
0x180021cc1  jnz     short loc_180021CE4
0x180021cc3  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180021cc7  mov     r9, r14; struct ICommandParameterList *
0x180021cca  mov     [rsp+70h+var_48], r15; struct ICommandObjectList *
0x180021ccf  mov     rdx, r13; unsigned __int16 *
0x180021cd2  mov     rcx, r12; this
0x180021cd5  mov     [rsp+70h+var_50], rdi; struct IExtensionContext *
0x180021cda  call    ?DoUnInstall@MODULE_OBJECT_EXTENSION@@AEAAJPEBG0PEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@@Z; MODULE_OBJECT_EXTENSION::DoUnInstall(ushort const *,ushort const *,ICommandParameterList *,IExtensionContext *,ICommandObjectList *)
0x180021cdf  jmp     loc_180021C19
0x180021ce4  mov     rax, [rdi]
0x180021ce7  lea     rdx, [rbp+var_30]
0x180021ceb  mov     rcx, rdi
0x180021cee  mov     rax, [rax+0B8h]
0x180021cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cfa  xor     r12d, r12d
0x180021cfd  mov     ebx, eax
0x180021cff  test    eax, eax
0x180021d01  js      loc_180021F0B
0x180021d07  mov     rax, [rdi]
0x180021d0a  lea     rdx, [rbp+var_28]
0x180021d0e  mov     rcx, rdi
0x180021d11  mov     rax, [rax+0C0h]
0x180021d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d1d  mov     ebx, eax
0x180021d1f  test    eax, eax
0x180021d21  js      loc_180021F0B
0x180021d27  mov     rax, [rbp+arg_18]
0x180021d2b  cmp     [rax], r12w
0x180021d2f  jnz     short loc_180021D9C
0x180021d31  mov     rax, [r14]
0x180021d34  lea     r8, [rbp+arg_18]
0x180021d38  lea     rdx, aModuleName_0; "MODULE.NAME"
0x180021d3f  mov     rcx, r14
0x180021d42  mov     rax, [rax+28h]
0x180021d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d4b  test    eax, eax
0x180021d4d  js      short loc_180021D59
0x180021d4f  mov     rax, [rbp+arg_18]
0x180021d53  cmp     [rax], r12w
0x180021d57  jnz     short loc_180021D9C
0x180021d59  lea     rax, aModule_0; "MODULE"
0x180021d60  mov     r8d, 0C00003EAh
0x180021d66  mov     qword ptr [rbp+var_10], rax
0x180021d6a  lea     rax, aModuleName_0; "MODULE.NAME"
0x180021d71  mov     edx, 80070002h
0x180021d76  mov     qword ptr [rbp+var_10+8], rax
0x180021d7a  mov     ebx, edx
0x180021d7c  mov     rax, [rdi]
0x180021d7f  lea     r9, [rbp+var_10]
0x180021d83  mov     rcx, rdi
0x180021d86  mov     dword ptr [rsp+70h+var_50], r12d
0x180021d8b  mov     rax, [rax+90h]
0x180021d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d97  jmp     loc_180021F0B
0x180021d9c  mov     rax, [r14]
0x180021d9f  lea     r8, [rbp+var_18]
0x180021da3  lea     rdx, aAppName_0; "APP.NAME"
0x180021daa  mov     rcx, r14
0x180021dad  mov     rax, [rax+28h]
0x180021db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021db6  test    eax, eax
0x180021db8  js      short loc_180021DDF
0x180021dba  mov     rcx, [rbp+var_28]
0x180021dbe  lea     rdx, aAppName_0; "APP.NAME"
0x180021dc5  mov     r8, [rbp+var_18]
0x180021dc9  mov     rax, [rcx]
0x180021dcc  mov     rax, [rax+38h]
0x180021dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dd5  mov     ebx, eax
0x180021dd7  test    eax, eax
0x180021dd9  js      loc_180021F0B
0x180021ddf  mov     rcx, [rbp+var_30]
0x180021de3  mov     rdx, r13
0x180021de6  mov     rax, [rdi]
0x180021de9  mov     r9, [rbp+var_28]
0x180021ded  mov     r8, [rbp+arg_18]
0x180021df1  mov     dword ptr [rsp+70h+var_48], r12d
0x180021df6  mov     rax, [rax+38h]
0x180021dfa  mov     [rsp+70h+var_50], rcx
0x180021dff  mov     rcx, rdi
0x180021e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e07  mov     ebx, eax
0x180021e09  test    eax, eax
0x180021e0b  js      loc_180021F0B
0x180021e11  mov     rcx, [rbp+var_30]
0x180021e15  lea     rdx, [rbp+arg_8]
0x180021e19  mov     rax, [rcx]
0x180021e1c  mov     rax, [rax+20h]
0x180021e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e25  mov     ebx, eax
0x180021e27  test    eax, eax
0x180021e29  js      loc_180021F0B
0x180021e2f  mov     eax, [rbp+arg_8]
0x180021e32  test    eax, eax
0x180021e34  jnz     short loc_180021E50
0x180021e36  lea     rax, aModule_0; "MODULE"
0x180021e3d  mov     r8d, 0C0000419h
0x180021e43  mov     qword ptr [rbp+var_10], rax
0x180021e47  mov     rax, [rbp+arg_18]
0x180021e4b  jmp     loc_180021D71
0x180021e50  cmp     eax, 1
0x180021e53  jbe     short loc_180021E76
0x180021e55  mov     ebx, 80070032h
0x180021e5a  mov     qword ptr [rbp+var_10+8], rsi
0x180021e5e  lea     rax, aModule_0; "MODULE"
0x180021e65  mov     edx, ebx
0x180021e67  mov     qword ptr [rbp+var_10], rax
0x180021e6b  mov     r8d, 0C00003EBh
0x180021e71  jmp     loc_180021D7C
0x180021e76  mov     rcx, [rbp+var_30]
0x180021e7a  lea     r8, [rbp+var_20]
0x180021e7e  xor     edx, edx
0x180021e80  mov     rax, [rcx]
0x180021e83  mov     rax, [rax+28h]
0x180021e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e8c  mov     ebx, eax
0x180021e8e  test    eax, eax
0x180021e90  js      short loc_180021F0B
0x180021e92  lea     rdx, aSet_0; "SET"
0x180021e99  mov     rcx, rsi; String1
0x180021e9c  call    cs:__imp__wcsicmp
0x180021ea2  test    eax, eax
0x180021ea4  jnz     short loc_180021ECD
0x180021ea6  mov     rax, [rdi]
0x180021ea9  mov     r9, r15
0x180021eac  mov     rcx, [rbp+arg_38]
0x180021eb0  mov     r8, r14
0x180021eb3  mov     rdx, [rbp+var_20]
0x180021eb7  mov     dword ptr [rsp+70h+var_48], r12d
0x180021ebc  mov     rax, [rax+0A8h]
0x180021ec3  mov     [rsp+70h+var_50], rcx
0x180021ec8  jmp     loc_180021C11
0x180021ecd  lea     rdx, aDelete_0; "DELETE"
0x180021ed4  mov     rcx, rsi; String1
0x180021ed7  call    cs:__imp__wcsicmp
0x180021edd  test    eax, eax
0x180021edf  jnz     short loc_180021EFF
0x180021ee1  mov     rax, [rdi]
0x180021ee4  mov     r8, r15
0x180021ee7  mov     rdx, [rbp+var_20]
0x180021eeb  mov     rcx, rdi
0x180021eee  mov     rax, [rax+0B0h]
0x180021ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021efa  jmp     loc_180021C19
0x180021eff  mov     ebx, 80070032h
0x180021f04  jmp     short loc_180021F0B
0x180021f06  mov     ebx, 80070057h
0x180021f0b  mov     rcx, [rbp+var_30]
0x180021f0f  test    rcx, rcx
0x180021f12  jz      short loc_180021F28
0x180021f14  mov     rax, [rcx]
0x180021f17  mov     rax, [rax+10h]
0x180021f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f20  mov     [rbp+var_30], 0
0x180021f28  mov     rcx, [rbp+var_28]
0x180021f2c  test    rcx, rcx
0x180021f2f  jz      short loc_180021F45
0x180021f31  mov     rax, [rcx]
0x180021f34  mov     rax, [rax+10h]
0x180021f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f3d  mov     [rbp+var_28], 0
0x180021f45  mov     rcx, [rbp+var_20]
0x180021f49  test    rcx, rcx
0x180021f4c  jz      short loc_180021F5A
0x180021f4e  mov     rax, [rcx]
0x180021f51  mov     rax, [rax+10h]
0x180021f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f5a  mov     eax, ebx
0x180021f5c  mov     rbx, [rsp+70h+arg_0]
0x180021f64  add     rsp, 70h
0x180021f68  pop     r15
0x180021f6a  pop     r14
0x180021f6c  pop     r13
0x180021f6e  pop     r12
0x180021f70  pop     rdi
0x180021f71  pop     rsi
0x180021f72  pop     rbp
0x180021f73  retn
```
