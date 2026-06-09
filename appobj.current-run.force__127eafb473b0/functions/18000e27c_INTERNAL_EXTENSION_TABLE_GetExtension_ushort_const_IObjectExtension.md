# INTERNAL_EXTENSION_TABLE::GetExtension(ushort const *,IObjectExtension * *)

- ea: `0x18000e27c`
- end: `0x18000e7a6`
- name: `?GetExtension@INTERNAL_EXTENSION_TABLE@@QEAAJPEBGPEAPEAVIObjectExtension@@@Z`
- size: `1322`
- prototype: `int(INTERNAL_EXTENSION_TABLE *__hidden this, const unsigned __int16 *, struct IObjectExtension **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000eb40`

## callees

- `0x180001044`
- `0x180002e90`
- `0x180005d74`
- `0x18000e27c`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e2e9`
- `msvcrt!_wcsicmp` at `0x18000e32c`
- `msvcrt!_wcsicmp` at `0x18000e383`
- `msvcrt!_wcsicmp` at `0x18000e3cb`
- `msvcrt!_wcsicmp` at `0x18000e413`
- `msvcrt!_wcsicmp` at `0x18000e466`
- `msvcrt!_wcsicmp` at `0x18000e4ae`
- `msvcrt!_wcsicmp` at `0x18000e4fd`
- `msvcrt!_wcsicmp` at `0x18000e545`
- `msvcrt!_wcsicmp` at `0x18000e58d`
- `msvcrt!_wcsicmp` at `0x18000e5d5`
- `msvcrt!_wcsicmp` at `0x18000e616`
- `msvcrt!_wcsicmp` at `0x18000e2e9`
- `msvcrt!_wcsicmp` at `0x18000e32c`
- `msvcrt!_wcsicmp` at `0x18000e383`
- `msvcrt!_wcsicmp` at `0x18000e3cb`
- `msvcrt!_wcsicmp` at `0x18000e413`
- `msvcrt!_wcsicmp` at `0x18000e466`
- `msvcrt!_wcsicmp` at `0x18000e4ae`
- `msvcrt!_wcsicmp` at `0x18000e4fd`
- `msvcrt!_wcsicmp` at `0x18000e545`
- `msvcrt!_wcsicmp` at `0x18000e58d`
- `msvcrt!_wcsicmp` at `0x18000e5d5`
- `msvcrt!_wcsicmp` at `0x18000e616`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e660`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000e660`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e68a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e68a`

## string_xrefs

- `0x18000e45c`: `DefaultConfigObject`

## pseudocode

```c
__int64 __fastcall INTERNAL_EXTENSION_TABLE::GetExtension(
        INTERNAL_EXTENSION_TABLE *this,
        const unsigned __int16 *a2,
        struct IObjectExtension **a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  struct IObjectExtension *v8; // rax
  HRESULT v9; // ebx
  _QWORD *v10; // rax
  void *v11; // rcx
  void *v12; // rax
  void **v13; // rax
  void *v14; // rax
  _QWORD *v15; // rax
  void *v16; // rax
  _QWORD *v17; // rax
  void *v18; // rax
  void *v19; // rax
  void *v20; // rax
  void *v21; // rax
  void *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rdi
  LPVOID v25; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-18h] BYREF

  ppv = 0;
  pclsid = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v6);
      if ( !_wcsicmp(*(const wchar_t **)(v7 + 56), a2) )
        break;
      if ( ++v6 >= *((_DWORD *)this + 4) )
        goto LABEL_8;
    }
    ppv = *(LPVOID *)(v7 + 16);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
LABEL_8:
    v8 = (struct IObjectExtension *)ppv;
    v9 = 0;
    if ( ppv )
      goto LABEL_55;
  }
  if ( !_wcsicmp(a2, L"DefaultSiteObject") )
  {
    v10 = operator new(0x48u);
    v11 = v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 2) = 1;
      v10[2] = 0;
      v10[3] = 0;
      v10[4] = 0;
      *((_DWORD *)v10 + 10) = 0;
      *v10 = &SITE_OBJECT_EXTENSION::`vftable';
      *((_DWORD *)v10 + 12) = 0;
      v10[7] = 0;
      *((_DWORD *)v10 + 16) = 0;
LABEL_44:
      ppv = v11;
      goto LABEL_47;
    }
    goto LABEL_43;
  }
  if ( !_wcsicmp(a2, L"DefaultAppObject") )
  {
    v12 = operator new(0x30u);
    v11 = v12;
    if ( !v12 )
      goto LABEL_43;
    *((_DWORD *)v12 + 2) = 1;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_DWORD *)v12 + 10) = 0;
    v13 = &APP_OBJECT_EXTENSION::`vftable';
LABEL_42:
    *(_QWORD *)v11 = v13;
    goto LABEL_44;
  }
  if ( !_wcsicmp(a2, L"DefaultDirObject") )
  {
    v14 = operator new(0x30u);
    v11 = v14;
    if ( !v14 )
      goto LABEL_43;
    *((_DWORD *)v14 + 2) = 1;
    *((_QWORD *)v14 + 2) = 0;
    *((_QWORD *)v14 + 3) = 0;
    *((_QWORD *)v14 + 4) = 0;
    *((_DWORD *)v14 + 10) = 0;
    v13 = &VDIR_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultAppPoolObject") )
  {
    v15 = operator new(0x40u);
    v11 = v15;
    if ( v15 )
    {
      *((_DWORD *)v15 + 2) = 1;
      v15[2] = 0;
      v15[3] = 0;
      v15[4] = 0;
      *((_DWORD *)v15 + 10) = 0;
      *v15 = &APPPOOL_OBJECT_EXTENSION::`vftable';
      v15[6] = 0;
      *((_DWORD *)v15 + 14) = 0;
      goto LABEL_44;
    }
LABEL_43:
    v11 = 0;
    goto LABEL_44;
  }
  if ( !_wcsicmp(a2, L"DefaultConfigObject") )
  {
    v16 = operator new(0x30u);
    v11 = v16;
    if ( !v16 )
      goto LABEL_43;
    *((_DWORD *)v16 + 2) = 1;
    *((_QWORD *)v16 + 2) = 0;
    *((_QWORD *)v16 + 3) = 0;
    *((_QWORD *)v16 + 4) = 0;
    *((_DWORD *)v16 + 10) = 0;
    v13 = &CONFIG_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultWorkerProcessObject") )
  {
    v17 = operator new(0x38u);
    v11 = v17;
    if ( v17 )
    {
      *((_DWORD *)v17 + 2) = 1;
      v17[2] = 0;
      v17[3] = 0;
      v17[4] = 0;
      *((_DWORD *)v17 + 10) = 0;
      *v17 = &WP_OBJECT_EXTENSION::`vftable';
      v17[6] = 0;
      goto LABEL_44;
    }
    goto LABEL_43;
  }
  if ( !_wcsicmp(a2, L"DefaultRequestObject") )
  {
    v18 = operator new(0x30u);
    v11 = v18;
    if ( !v18 )
      goto LABEL_43;
    *((_DWORD *)v18 + 2) = 1;
    *((_QWORD *)v18 + 2) = 0;
    *((_QWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 4) = 0;
    *((_DWORD *)v18 + 10) = 0;
    v13 = &REQUEST_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultModuleObject") )
  {
    v19 = operator new(0x30u);
    v11 = v19;
    if ( !v19 )
      goto LABEL_43;
    *((_DWORD *)v19 + 2) = 1;
    *((_QWORD *)v19 + 2) = 0;
    *((_QWORD *)v19 + 3) = 0;
    *((_QWORD *)v19 + 4) = 0;
    *((_DWORD *)v19 + 10) = 0;
    v13 = &MODULE_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultBackupObject") )
  {
    v20 = operator new(0x30u);
    v11 = v20;
    if ( !v20 )
      goto LABEL_43;
    *((_DWORD *)v20 + 2) = 1;
    *((_QWORD *)v20 + 2) = 0;
    *((_QWORD *)v20 + 3) = 0;
    *((_QWORD *)v20 + 4) = 0;
    *((_DWORD *)v20 + 10) = 0;
    v13 = &BACKUP_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultTraceObject") )
  {
    v21 = operator new(0x30u);
    v11 = v21;
    if ( !v21 )
      goto LABEL_43;
    *((_DWORD *)v21 + 2) = 1;
    *((_QWORD *)v21 + 2) = 0;
    *((_QWORD *)v21 + 3) = 0;
    *((_QWORD *)v21 + 4) = 0;
    *((_DWORD *)v21 + 10) = 0;
    v13 = &TRACE_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  if ( !_wcsicmp(a2, L"DefaultBindingObject") )
  {
    v22 = operator new(0x30u);
    v11 = v22;
    if ( !v22 )
      goto LABEL_43;
    *((_DWORD *)v22 + 2) = 1;
    *((_QWORD *)v22 + 2) = 0;
    *((_QWORD *)v22 + 3) = 0;
    *((_QWORD *)v22 + 4) = 0;
    *((_DWORD *)v22 + 10) = 0;
    v13 = &BINDING_OBJECT_EXTENSION::`vftable';
    goto LABEL_42;
  }
  v9 = CLSIDFromString(a2, &pclsid);
  if ( v9 < 0 )
    goto LABEL_59;
  CoCreateInstance(&pclsid, 0, 0x17u, &IID_IObjectExtension, &ppv);
  v11 = ppv;
LABEL_47:
  if ( !v11 )
    return (unsigned int)-2147024894;
  v9 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v11 + 48LL))(v11);
  if ( v9 >= 0 )
  {
    v23 = operator new(0x50u);
    v24 = v23;
    if ( v23 )
    {
      v23[2] = 0;
      v23[3] = 0;
      *v23 = &EXTENSION_ENTRY::`vftable';
      v23[7] = v23 + 3;
      *((_DWORD *)v23 + 16) = 32;
      *((_WORD *)v23 + 34) = 256;
      *((_DWORD *)v23 + 18) = 0;
      *((_DWORD *)v23 + 2) = 1313167429;
      v25 = ppv;
      if ( ppv )
      {
        v23[2] = ppv;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 8LL))(v25);
        v9 = STRU::Copy((STRU *)(v24 + 3), a2);
        if ( v9 >= 0 )
        {
          v9 = ARRAY_LIST::AddEntry(
                 (INTERNAL_EXTENSION_TABLE *)((char *)this + 8),
                 (struct IArrayListEntry *)v24,
                 0xFFFFFFFF);
          if ( v9 >= 0 )
          {
            v8 = (struct IObjectExtension *)ppv;
LABEL_55:
            *a3 = v8;
            return (unsigned int)v9;
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
      (*(void (__fastcall **)(_QWORD *))*v24)(v24);
    }
    else
    {
      v9 = -2147024888;
    }
  }
LABEL_59:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e27c  mov     [rsp-38h+arg_18], rbx
0x18000e281  push    rbp
0x18000e282  push    rsi
0x18000e283  push    rdi
0x18000e284  push    r12
0x18000e286  push    r13
0x18000e288  push    r14
0x18000e28a  push    r15
0x18000e28c  mov     rbp, rsp
0x18000e28f  sub     rsp, 50h
0x18000e293  mov     rax, cs:__security_cookie
0x18000e29a  xor     rax, rsp
0x18000e29d  mov     [rbp+var_8], rax
0x18000e2a1  xor     r12d, r12d
0x18000e2a4  xorps   xmm0, xmm0
0x18000e2a7  mov     [rbp+var_20], r12
0x18000e2ab  mov     r15, r8
0x18000e2ae  mov     rsi, rdx
0x18000e2b1  mov     r14, rcx
0x18000e2b4  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18000e2b8  test    rdx, rdx
0x18000e2bb  jz      loc_18000E77B
0x18000e2c1  test    r8, r8
0x18000e2c4  jz      loc_18000E77B
0x18000e2ca  lea     r13d, [r12+1]
0x18000e2cf  mov     ebx, r12d
0x18000e2d2  cmp     [rcx+10h], r12d
0x18000e2d6  jbe     short loc_18000E322
0x18000e2d8  mov     rax, [r14+8]
0x18000e2dc  mov     rdx, rsi; String2
0x18000e2df  mov     ecx, ebx
0x18000e2e1  mov     rdi, [rax+rcx*8]
0x18000e2e5  mov     rcx, [rdi+38h]; String1
0x18000e2e9  call    cs:__imp__wcsicmp
0x18000e2ef  test    eax, eax
0x18000e2f1  jz      short loc_18000E2FE
0x18000e2f3  add     ebx, r13d
0x18000e2f6  cmp     ebx, [r14+10h]
0x18000e2fa  jb      short loc_18000E2D8
0x18000e2fc  jmp     short loc_18000E312
0x18000e2fe  mov     rcx, [rdi+10h]
0x18000e302  mov     [rbp+var_20], rcx
0x18000e306  mov     rax, [rcx]
0x18000e309  mov     rax, [rax+8]
0x18000e30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e312  mov     rax, [rbp+var_20]
0x18000e316  mov     ebx, r12d
0x18000e319  test    rax, rax
0x18000e31c  jnz     loc_18000E745
0x18000e322  lea     rdx, aDefaultsiteobj; "DefaultSiteObject"
0x18000e329  mov     rcx, rsi; String1
0x18000e32c  call    cs:__imp__wcsicmp
0x18000e332  test    eax, eax
0x18000e334  jnz     short loc_18000E379
0x18000e336  lea     ecx, [rax+48h]; Size
0x18000e339  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e33e  mov     rcx, rax
0x18000e341  test    rax, rax
0x18000e344  jz      loc_18000E650
0x18000e34a  mov     [rax+8], r13d
0x18000e34e  mov     [rax+10h], r12
0x18000e352  mov     [rax+18h], r12
0x18000e356  mov     [rax+20h], r12
0x18000e35a  mov     [rax+28h], r12d
0x18000e35e  lea     rax, ??_7SITE_OBJECT_EXTENSION@@6B@; const SITE_OBJECT_EXTENSION::`vftable'
0x18000e365  mov     [rcx], rax
0x18000e368  mov     [rcx+30h], r12d
0x18000e36c  mov     [rcx+38h], r12
0x18000e370  mov     [rcx+40h], r12d
0x18000e374  jmp     loc_18000E653
0x18000e379  lea     rdx, aDefaultappobje; "DefaultAppObject"
0x18000e380  mov     rcx, rsi; String1
0x18000e383  call    cs:__imp__wcsicmp
0x18000e389  test    eax, eax
0x18000e38b  jnz     short loc_18000E3C1
0x18000e38d  lea     ecx, [rax+30h]; Size
0x18000e390  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e395  mov     rcx, rax
0x18000e398  test    rax, rax
0x18000e39b  jz      loc_18000E650
0x18000e3a1  mov     [rax+8], r13d
0x18000e3a5  mov     [rax+10h], r12
0x18000e3a9  mov     [rax+18h], r12
0x18000e3ad  mov     [rax+20h], r12
0x18000e3b1  mov     [rax+28h], r12d
0x18000e3b5  lea     rax, ??_7APP_OBJECT_EXTENSION@@6B@; const APP_OBJECT_EXTENSION::`vftable'
0x18000e3bc  jmp     loc_18000E64B
0x18000e3c1  lea     rdx, aDefaultdirobje; "DefaultDirObject"
0x18000e3c8  mov     rcx, rsi; String1
0x18000e3cb  call    cs:__imp__wcsicmp
0x18000e3d1  test    eax, eax
0x18000e3d3  jnz     short loc_18000E409
0x18000e3d5  lea     ecx, [rax+30h]; Size
0x18000e3d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e3dd  mov     rcx, rax
0x18000e3e0  test    rax, rax
0x18000e3e3  jz      loc_18000E650
0x18000e3e9  mov     [rax+8], r13d
0x18000e3ed  mov     [rax+10h], r12
0x18000e3f1  mov     [rax+18h], r12
0x18000e3f5  mov     [rax+20h], r12
0x18000e3f9  mov     [rax+28h], r12d
0x18000e3fd  lea     rax, ??_7VDIR_OBJECT_EXTENSION@@6B@; const VDIR_OBJECT_EXTENSION::`vftable'
0x18000e404  jmp     loc_18000E64B
0x18000e409  lea     rdx, aDefaultapppool; "DefaultAppPoolObject"
0x18000e410  mov     rcx, rsi; String1
0x18000e413  call    cs:__imp__wcsicmp
0x18000e419  test    eax, eax
0x18000e41b  jnz     short loc_18000E45C
0x18000e41d  lea     ecx, [rax+40h]; Size
0x18000e420  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e425  mov     rcx, rax
0x18000e428  test    rax, rax
0x18000e42b  jz      loc_18000E650
0x18000e431  mov     [rax+8], r13d
0x18000e435  mov     [rax+10h], r12
0x18000e439  mov     [rax+18h], r12
0x18000e43d  mov     [rax+20h], r12
0x18000e441  mov     [rax+28h], r12d
0x18000e445  lea     rax, ??_7APPPOOL_OBJECT_EXTENSION@@6B@; const APPPOOL_OBJECT_EXTENSION::`vftable'
0x18000e44c  mov     [rcx], rax
0x18000e44f  mov     [rcx+30h], r12
0x18000e453  mov     [rcx+38h], r12d
0x18000e457  jmp     loc_18000E653
0x18000e45c  lea     rdx, aDefaultconfigo; "DefaultConfigObject"
0x18000e463  mov     rcx, rsi; String1
0x18000e466  call    cs:__imp__wcsicmp
0x18000e46c  test    eax, eax
0x18000e46e  jnz     short loc_18000E4A4
0x18000e470  lea     ecx, [rax+30h]; Size
0x18000e473  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e478  mov     rcx, rax
0x18000e47b  test    rax, rax
0x18000e47e  jz      loc_18000E650
0x18000e484  mov     [rax+8], r13d
0x18000e488  mov     [rax+10h], r12
0x18000e48c  mov     [rax+18h], r12
0x18000e490  mov     [rax+20h], r12
0x18000e494  mov     [rax+28h], r12d
0x18000e498  lea     rax, ??_7CONFIG_OBJECT_EXTENSION@@6B@; const CONFIG_OBJECT_EXTENSION::`vftable'
0x18000e49f  jmp     loc_18000E64B
0x18000e4a4  lea     rdx, aDefaultworkerp; "DefaultWorkerProcessObject"
0x18000e4ab  mov     rcx, rsi; String1
0x18000e4ae  call    cs:__imp__wcsicmp
0x18000e4b4  test    eax, eax
0x18000e4b6  jnz     short loc_18000E4F3
0x18000e4b8  lea     ecx, [rax+38h]; Size
0x18000e4bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e4c0  mov     rcx, rax
0x18000e4c3  test    rax, rax
0x18000e4c6  jz      loc_18000E650
0x18000e4cc  mov     [rax+8], r13d
0x18000e4d0  mov     [rax+10h], r12
0x18000e4d4  mov     [rax+18h], r12
0x18000e4d8  mov     [rax+20h], r12
0x18000e4dc  mov     [rax+28h], r12d
0x18000e4e0  lea     rax, ??_7WP_OBJECT_EXTENSION@@6B@; const WP_OBJECT_EXTENSION::`vftable'
0x18000e4e7  mov     [rcx], rax
0x18000e4ea  mov     [rcx+30h], r12
0x18000e4ee  jmp     loc_18000E653
0x18000e4f3  lea     rdx, aDefaultrequest; "DefaultRequestObject"
0x18000e4fa  mov     rcx, rsi; String1
0x18000e4fd  call    cs:__imp__wcsicmp
0x18000e503  test    eax, eax
0x18000e505  jnz     short loc_18000E53B
0x18000e507  lea     ecx, [rax+30h]; Size
0x18000e50a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e50f  mov     rcx, rax
0x18000e512  test    rax, rax
0x18000e515  jz      loc_18000E650
0x18000e51b  mov     [rax+8], r13d
0x18000e51f  mov     [rax+10h], r12
0x18000e523  mov     [rax+18h], r12
0x18000e527  mov     [rax+20h], r12
0x18000e52b  mov     [rax+28h], r12d
0x18000e52f  lea     rax, ??_7REQUEST_OBJECT_EXTENSION@@6B@; const REQUEST_OBJECT_EXTENSION::`vftable'
0x18000e536  jmp     loc_18000E64B
0x18000e53b  lea     rdx, aDefaultmoduleo; "DefaultModuleObject"
0x18000e542  mov     rcx, rsi; String1
0x18000e545  call    cs:__imp__wcsicmp
0x18000e54b  test    eax, eax
0x18000e54d  jnz     short loc_18000E583
0x18000e54f  lea     ecx, [rax+30h]; Size
0x18000e552  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e557  mov     rcx, rax
0x18000e55a  test    rax, rax
0x18000e55d  jz      loc_18000E650
0x18000e563  mov     [rax+8], r13d
0x18000e567  mov     [rax+10h], r12
0x18000e56b  mov     [rax+18h], r12
0x18000e56f  mov     [rax+20h], r12
0x18000e573  mov     [rax+28h], r12d
0x18000e577  lea     rax, ??_7MODULE_OBJECT_EXTENSION@@6B@; const MODULE_OBJECT_EXTENSION::`vftable'
0x18000e57e  jmp     loc_18000E64B
0x18000e583  lea     rdx, aDefaultbackupo; "DefaultBackupObject"
0x18000e58a  mov     rcx, rsi; String1
0x18000e58d  call    cs:__imp__wcsicmp
0x18000e593  test    eax, eax
0x18000e595  jnz     short loc_18000E5CB
0x18000e597  lea     ecx, [rax+30h]; Size
0x18000e59a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e59f  mov     rcx, rax
0x18000e5a2  test    rax, rax
0x18000e5a5  jz      loc_18000E650
0x18000e5ab  mov     [rax+8], r13d
0x18000e5af  mov     [rax+10h], r12
0x18000e5b3  mov     [rax+18h], r12
0x18000e5b7  mov     [rax+20h], r12
0x18000e5bb  mov     [rax+28h], r12d
0x18000e5bf  lea     rax, ??_7BACKUP_OBJECT_EXTENSION@@6B@; const BACKUP_OBJECT_EXTENSION::`vftable'
0x18000e5c6  jmp     loc_18000E64B
0x18000e5cb  lea     rdx, aDefaulttraceob; "DefaultTraceObject"
0x18000e5d2  mov     rcx, rsi; String1
0x18000e5d5  call    cs:__imp__wcsicmp
0x18000e5db  test    eax, eax
0x18000e5dd  jnz     short loc_18000E60C
0x18000e5df  lea     ecx, [rax+30h]; Size
0x18000e5e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e5e7  mov     rcx, rax
0x18000e5ea  test    rax, rax
0x18000e5ed  jz      short loc_18000E650
0x18000e5ef  mov     [rax+8], r13d
0x18000e5f3  mov     [rax+10h], r12
0x18000e5f7  mov     [rax+18h], r12
0x18000e5fb  mov     [rax+20h], r12
0x18000e5ff  mov     [rax+28h], r12d
0x18000e603  lea     rax, ??_7TRACE_OBJECT_EXTENSION@@6B@; const TRACE_OBJECT_EXTENSION::`vftable'
0x18000e60a  jmp     short loc_18000E64B
0x18000e60c  lea     rdx, aDefaultbinding; "DefaultBindingObject"
0x18000e613  mov     rcx, rsi; String1
0x18000e616  call    cs:__imp__wcsicmp
0x18000e61c  test    eax, eax
0x18000e61e  jnz     short loc_18000E659
0x18000e620  lea     ecx, [rax+30h]; Size
0x18000e623  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e628  mov     rcx, rax
0x18000e62b  test    rax, rax
0x18000e62e  jz      short loc_18000E650
0x18000e630  mov     [rax+8], r13d
0x18000e634  mov     [rax+10h], r12
0x18000e638  mov     [rax+18h], r12
0x18000e63c  mov     [rax+20h], r12
0x18000e640  mov     [rax+28h], r12d
0x18000e644  lea     rax, ??_7BINDING_OBJECT_EXTENSION@@6B@; const BINDING_OBJECT_EXTENSION::`vftable'
0x18000e64b  mov     [rcx], rax
0x18000e64e  jmp     short loc_18000E653
0x18000e650  mov     rcx, r12
0x18000e653  mov     [rbp+var_20], rcx
0x18000e657  jmp     short loc_18000E694
0x18000e659  lea     rdx, [rbp+pclsid]; pclsid
0x18000e65d  mov     rcx, rsi; lpsz
0x18000e660  call    cs:__imp_CLSIDFromString
0x18000e666  mov     ebx, eax
0x18000e668  test    eax, eax
0x18000e66a  js      loc_18000E764
0x18000e670  xor     edx, edx; pUnkOuter
0x18000e672  lea     rax, [rbp+var_20]
0x18000e676  lea     r9, IID_IObjectExtension; riid
0x18000e67d  mov     [rsp+50h+ppv], rax; ppv
0x18000e682  lea     rcx, [rbp+pclsid]; rclsid
0x18000e686  lea     r8d, [rdx+17h]; dwClsContext
0x18000e68a  call    cs:__imp_CoCreateInstance
0x18000e690  mov     rcx, [rbp+var_20]
0x18000e694  test    rcx, rcx
0x18000e697  jnz     short loc_18000E6A3
0x18000e699  mov     ebx, 80070002h
0x18000e69e  jmp     loc_18000E780
0x18000e6a3  mov     rax, [rcx]
0x18000e6a6  mov     rax, [rax+30h]
0x18000e6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6af  mov     ebx, eax
0x18000e6b1  test    eax, eax
0x18000e6b3  js      loc_18000E764
0x18000e6b9  mov     ecx, 50h ; 'P'; Size
0x18000e6be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6c3  mov     rdi, rax
0x18000e6c6  test    rax, rax
0x18000e6c9  jz      loc_18000E75F
0x18000e6cf  lea     rcx, [rdi+18h]
0x18000e6d3  mov     [rdi+10h], r12
0x18000e6d7  lea     rax, ??_7EXTENSION_ENTRY@@6B@; const EXTENSION_ENTRY::`vftable'
0x18000e6de  mov     [rcx], r12
0x18000e6e1  mov     [rdi], rax
0x18000e6e4  mov     [rcx+20h], rcx
0x18000e6e8  mov     dword ptr [rcx+28h], 20h ; ' '
0x18000e6ef  mov     word ptr [rcx+2Ch], 100h
0x18000e6f5  mov     [rcx+30h], r12d
0x18000e6f9  mov     dword ptr [rdi+8], 4E455845h
0x18000e700  mov     rcx, [rbp+var_20]
0x18000e704  test    rcx, rcx
0x18000e707  jz      short loc_18000E74A
0x18000e709  mov     [rdi+10h], rcx
0x18000e70d  mov     rax, [rcx]
0x18000e710  mov     rax, [rax+8]
0x18000e714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e719  lea     rcx, [rdi+18h]; this
0x18000e71d  mov     rdx, rsi; unsigned __int16 *
0x18000e720  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000e725  mov     ebx, eax
0x18000e727  test    eax, eax
  ... truncated ...
```
