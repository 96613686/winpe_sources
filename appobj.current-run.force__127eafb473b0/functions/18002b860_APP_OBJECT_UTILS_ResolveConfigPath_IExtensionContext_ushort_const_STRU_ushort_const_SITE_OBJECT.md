# APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)

- ea: `0x18002b860`
- end: `0x18002bb1a`
- name: `?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z`
- size: `698`
- prototype: `int(APP_OBJECT_UTILS *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct STRU *, const unsigned __int16 **, struct SITE_OBJECT **)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800085a0`
- `0x180018fd0`
- `0x18001a850`
- `0x180027190`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180002e90`
- `0x18002b860`
- `0x18002bb20`
- `0x180034cbe`
- `0x180034cca`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002b959`
- `msvcrt!wcsstr` at `0x18002b959`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::ResolveConfigPath(
        APP_OBJECT_UTILS *this,
        struct IExtensionContext *a2,
        unsigned __int16 *a3,
        struct STRU *a4,
        unsigned __int16 **a5,
        struct SITE_OBJECT **a6)
{
  int v9; // ebx
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // eax
  int v12; // eax
  const wchar_t *v13; // rdx
  struct SITE_OBJECT *v14; // rcx
  struct SITE_OBJECT *v16; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  __int16 v22; // [rsp+74h] [rbp-8Ch]
  int v23; // [rsp+78h] [rbp-88h]
  __int16 v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[510]; // [rsp+82h] [rbp-7Eh] BYREF

  memset_0(v25, 0, sizeof(v25));
  v21 = 512;
  v22 = 256;
  v20 = &v24;
  v23 = 0;
  v24 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_30;
  }
  if ( !wcscmp_0(a3, L"MACHINE")
    || !wcscmp_0(a3, L"MACHINE/REDIRECTION")
    || !wcscmp_0(a3, L"MACHINE/WEBROOT")
    || wcsstr(a3, L"MACHINE/WEBROOT/APPHOST") == a3 )
  {
    v13 = a3;
LABEL_19:
    v11 = STRU::Copy((STRU *)v19, (const unsigned __int8 *)v13);
LABEL_20:
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_30;
    goto LABEL_21;
  }
  if ( !*a3 )
  {
    v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a2 + 216LL))(a2);
    v13 = L"MACHINE/WEBROOT";
    if ( !v12 )
      v13 = L"MACHINE/WEBROOT/APPHOST";
    goto LABEL_19;
  }
  v9 = STRU::Copy((STRU *)v19, (const unsigned __int8 *)L"MACHINE/WEBROOT/APPHOST");
  if ( v9 < 0 )
    goto LABEL_30;
  v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, struct SITE_OBJECT **, int))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"SITE",
         a3,
         &v16,
         4);
  if ( v9 < 0 )
    goto LABEL_30;
  v9 = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v16 + 80LL))(
         v16,
         L"SITE.NAME",
         &v17);
  if ( v9 < 0 )
    goto LABEL_30;
  v9 = STRU::Append((STRU *)v19, L"/");
  if ( v9 < 0 )
    goto LABEL_30;
  v9 = STRU::Append((STRU *)v19, v17);
  if ( v9 < 0 )
    goto LABEL_30;
  v9 = APP_OBJECT_UTILS::ResolveUrl(v10, a3, 0, (const unsigned __int16 **)&v18, 0);
  if ( v9 < 0 )
    goto LABEL_30;
  a3 = v18;
  if ( v18 )
  {
    v11 = STRU::Append((STRU *)v19, v18);
    goto LABEL_20;
  }
LABEL_21:
  v9 = STRU::Copy(a4, (const struct STRU *)v19);
  if ( v9 >= 0 )
  {
    if ( a5 )
      *a5 = a3;
    if ( a6 )
    {
      v14 = v16;
      *a6 = v16;
      if ( v14 )
        (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    v9 = 0;
  }
LABEL_30:
  if ( v16 )
  {
    (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b860  mov     [rsp-8+arg_0], rbx
0x18002b865  push    rbp
0x18002b866  push    rsi
0x18002b867  push    rdi
0x18002b868  push    r12
0x18002b86a  push    r13
0x18002b86c  push    r14
0x18002b86e  push    r15
0x18002b870  lea     rbp, [rsp-190h]
0x18002b878  sub     rsp, 290h
0x18002b87f  mov     rax, cs:__security_cookie
0x18002b886  xor     rax, rsp
0x18002b889  mov     [rbp+1C0h+var_40], rax
0x18002b890  mov     r15, [rbp+1C0h+arg_20]
0x18002b897  lea     rcx, [rbp+1C0h+var_23E]; void *
0x18002b89b  mov     r14, [rbp+1C0h+arg_28]
0x18002b8a2  mov     rdi, r8
0x18002b8a5  mov     rsi, rdx
0x18002b8a8  mov     r8d, 1FEh; Size
0x18002b8ae  xor     edx, edx; Val
0x18002b8b0  mov     r12, r9
0x18002b8b3  call    memset_0
0x18002b8b8  xor     r13d, r13d
0x18002b8bb  mov     [rsp+2C0h+var_250], 200h
0x18002b8c3  mov     [rsp+2C0h+var_24C], 100h
0x18002b8ca  lea     rax, [rbp+1C0h+var_240]
0x18002b8ce  mov     [rsp+2C0h+var_258], rax
0x18002b8d3  mov     [rsp+2C0h+var_248], r13d
0x18002b8d8  mov     [rbp+1C0h+var_240], r13w
0x18002b8dd  mov     [rsp+2C0h+var_290], r13
0x18002b8e2  mov     [rsp+2C0h+var_288], r13
0x18002b8e7  mov     [rsp+2C0h+var_280], r13
0x18002b8ec  test    rsi, rsi
0x18002b8ef  jz      loc_18002BAC4
0x18002b8f5  test    rdi, rdi
0x18002b8f8  jz      loc_18002BAC4
0x18002b8fe  test    r12, r12
0x18002b901  jz      loc_18002BAC4
0x18002b907  lea     rdx, aMachine_0; "MACHINE"
0x18002b90e  mov     rcx, rdi; String1
0x18002b911  call    wcscmp_0
0x18002b916  test    eax, eax
0x18002b918  jz      loc_18002BABA
0x18002b91e  lea     rdx, aMachineRedirec; "MACHINE/REDIRECTION"
0x18002b925  mov     rcx, rdi; String1
0x18002b928  call    wcscmp_0
0x18002b92d  test    eax, eax
0x18002b92f  jz      loc_18002BABA
0x18002b935  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18002b93c  mov     rcx, rdi; String1
0x18002b93f  call    wcscmp_0
0x18002b944  test    eax, eax
0x18002b946  jz      loc_18002BABA
0x18002b94c  lea     rbx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002b953  mov     rcx, rdi; Str
0x18002b956  mov     rdx, rbx; SubStr
0x18002b959  call    cs:__imp_wcsstr
0x18002b95f  cmp     rax, rdi
0x18002b962  jz      loc_18002BABA
0x18002b968  cmp     [rdi], r13w
0x18002b96c  jz      loc_18002BA4C
0x18002b972  mov     rdx, rbx; unsigned __int16 *
0x18002b975  lea     rcx, [rsp+2C0h+var_278]; this
0x18002b97a  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b97f  mov     ebx, eax
0x18002b981  test    eax, eax
0x18002b983  js      loc_18002BAC9
0x18002b989  mov     rax, [rsi]
0x18002b98c  lea     r9, [rsp+2C0h+var_290]
0x18002b991  mov     r8, rdi
0x18002b994  mov     dword ptr [rsp+2C0h+var_2A0], 4
0x18002b99c  lea     rdx, aSite_0; "SITE"
0x18002b9a3  mov     rcx, rsi
0x18002b9a6  mov     rax, [rax+40h]
0x18002b9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9af  mov     ebx, eax
0x18002b9b1  test    eax, eax
0x18002b9b3  js      loc_18002BAC9
0x18002b9b9  mov     rcx, [rsp+2C0h+var_290]
0x18002b9be  lea     r8, [rsp+2C0h+var_288]
0x18002b9c3  lea     rdx, aSiteName; "SITE.NAME"
0x18002b9ca  mov     rax, [rcx]
0x18002b9cd  mov     rax, [rax+50h]
0x18002b9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9d6  mov     ebx, eax
0x18002b9d8  test    eax, eax
0x18002b9da  js      loc_18002BAC9
0x18002b9e0  lea     rdx, SubStr; "/"
0x18002b9e7  lea     rcx, [rsp+2C0h+var_278]; this
0x18002b9ec  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002b9f1  mov     ebx, eax
0x18002b9f3  test    eax, eax
0x18002b9f5  js      loc_18002BAC9
0x18002b9fb  mov     rdx, [rsp+2C0h+var_288]; unsigned __int16 *
0x18002ba00  lea     rcx, [rsp+2C0h+var_278]; this
0x18002ba05  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ba0a  mov     ebx, eax
0x18002ba0c  test    eax, eax
0x18002ba0e  js      loc_18002BAC9
0x18002ba14  lea     r9, [rsp+2C0h+var_280]; unsigned __int16 **
0x18002ba19  mov     [rsp+2C0h+var_2A0], r13; int *
0x18002ba1e  xor     r8d, r8d; struct STRU *
0x18002ba21  mov     rdx, rdi; unsigned __int16 *
0x18002ba24  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x18002ba29  mov     ebx, eax
0x18002ba2b  test    eax, eax
0x18002ba2d  js      loc_18002BAC9
0x18002ba33  mov     rdi, [rsp+2C0h+var_280]
0x18002ba38  test    rdi, rdi
0x18002ba3b  jz      short loc_18002BA7C
0x18002ba3d  mov     rdx, rdi; unsigned __int16 *
0x18002ba40  lea     rcx, [rsp+2C0h+var_278]; this
0x18002ba45  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ba4a  jmp     short loc_18002BA76
0x18002ba4c  mov     rax, [rsi]
0x18002ba4f  mov     rcx, rsi
0x18002ba52  mov     rax, [rax+0D8h]
0x18002ba59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba5e  lea     rcx, [rsp+2C0h+var_278]; this
0x18002ba63  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18002ba6a  test    eax, eax
0x18002ba6c  jnz     short loc_18002BA71
0x18002ba6e  mov     rdx, rbx; unsigned __int16 *
0x18002ba71  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002ba76  mov     ebx, eax
0x18002ba78  test    eax, eax
0x18002ba7a  js      short loc_18002BAC9
0x18002ba7c  lea     rdx, [rsp+2C0h+var_278]; struct STRU *
0x18002ba81  mov     rcx, r12; this
0x18002ba84  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002ba89  mov     ebx, eax
0x18002ba8b  test    eax, eax
0x18002ba8d  js      short loc_18002BAC9
0x18002ba8f  test    r15, r15
0x18002ba92  jz      short loc_18002BA97
0x18002ba94  mov     [r15], rdi
0x18002ba97  test    r14, r14
0x18002ba9a  jz      short loc_18002BAB5
0x18002ba9c  mov     rcx, [rsp+2C0h+var_290]
0x18002baa1  mov     [r14], rcx
0x18002baa4  test    rcx, rcx
0x18002baa7  jz      short loc_18002BAB5
0x18002baa9  mov     rax, [rcx]
0x18002baac  mov     rax, [rax+8]
0x18002bab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bab5  mov     ebx, r13d
0x18002bab8  jmp     short loc_18002BAC9
0x18002baba  mov     rdx, rdi
0x18002babd  lea     rcx, [rsp+2C0h+var_278]
0x18002bac2  jmp     short loc_18002BA71
0x18002bac4  mov     ebx, 80070057h
0x18002bac9  mov     rcx, [rsp+2C0h+var_290]
0x18002bace  test    rcx, rcx
0x18002bad1  jz      short loc_18002BAE4
0x18002bad3  mov     rax, [rcx]
0x18002bad6  mov     rax, [rax+10h]
0x18002bada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002badf  mov     [rsp+2C0h+var_290], r13
0x18002bae4  lea     rcx, [rsp+2C0h+var_278]; this
0x18002bae9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002baee  mov     eax, ebx
0x18002baf0  mov     rcx, [rbp+1C0h+var_40]
0x18002baf7  xor     rcx, rsp; StackCookie
0x18002bafa  call    __security_check_cookie
0x18002baff  mov     rbx, [rsp+2C0h+arg_0]
0x18002bb07  add     rsp, 290h
0x18002bb0e  pop     r15
0x18002bb10  pop     r14
0x18002bb12  pop     r13
0x18002bb14  pop     r12
0x18002bb16  pop     rdi
0x18002bb17  pop     rsi
0x18002bb18  pop     rbp
0x18002bb19  retn
```
