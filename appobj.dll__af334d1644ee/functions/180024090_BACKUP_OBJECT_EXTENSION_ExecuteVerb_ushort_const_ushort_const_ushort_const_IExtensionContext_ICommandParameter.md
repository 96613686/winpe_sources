# BACKUP_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180024090`
- end: `0x1800243bf`
- name: `?ExecuteVerb@BACKUP_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(BACKUP_OBJECT_EXTENSION *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180022a9c`
- `0x180023ba8`
- `0x180024090`
- `0x180025170`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180024183`
- `msvcrt!_wcsicmp` at `0x1800241be`
- `msvcrt!_wcsicmp` at `0x1800242e5`
- `msvcrt!_wcsicmp` at `0x18002431f`
- `msvcrt!_wcsicmp` at `0x180024183`
- `msvcrt!_wcsicmp` at `0x1800241be`
- `msvcrt!_wcsicmp` at `0x1800242e5`
- `msvcrt!_wcsicmp` at `0x18002431f`

## string_xrefs

- `0x180024315`: `DELETE`

## pseudocode

```c
__int64 __fastcall BACKUP_OBJECT_EXTENSION::ExecuteVerb(
        BACKUP_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7)
{
  int v10; // ebx
  int v11; // eax
  BACKUP_OBJECT_EXTENSION *v12; // rcx
  int v13; // eax
  BACKUP_OBJECT_EXTENSION *v14; // rcx
  BACKUP_OBJECT_EXTENSION *v15; // rcx
  struct BACKUP_OBJECT *v17; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandParameterList *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  __int16 v25; // [rsp+9Ch] [rbp-64h]
  int v26; // [rsp+A0h] [rbp-60h]
  __int16 v27; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[510]; // [rsp+B2h] [rbp-4Eh] BYREF

  v17 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  memset_0(v28, 0, sizeof(v28));
  v24 = 512;
  v23 = (const unsigned __int16 *)&v27;
  v25 = 256;
  v26 = 0;
  v27 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
    goto LABEL_28;
  v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
          a6,
          &v18);
  if ( v10 < 0 )
    goto LABEL_29;
  if ( !_wcsicmp(a3, L"LIST") )
  {
    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)a5 + 56LL))(
            a5,
            a2,
            a4,
            a6,
            a7,
            0);
LABEL_12:
    v10 = v11;
    goto LABEL_29;
  }
  if ( !_wcsicmp(a3, L"ADD") )
  {
    v11 = BACKUP_OBJECT_EXTENSION::AddBackup(v12, a5, a4, v18, a7);
    goto LABEL_12;
  }
  if ( !*a4 )
  {
    v13 = APP_OBJECT_UTILS::PopParameter(v12, a5, v18, L"BACKUP.NAME", (struct STRU *)v22, 0, 1);
    v10 = v13;
    if ( v13 == -2147023483 )
    {
      *((_QWORD *)&v20 + 1) = L"BACKUP.NAME";
      *(_QWORD *)&v20 = L"BACKUP";
      v10 = -2147024846;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a5 + 144LL))(
        a5,
        2147942450LL,
        3221226474LL,
        &v20,
        0);
      goto LABEL_29;
    }
    if ( v13 < 0 )
      goto LABEL_29;
    a4 = v23;
  }
  v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct BACKUP_OBJECT **, _DWORD))(*(_QWORD *)a5 + 64LL))(
          a5,
          a2,
          a4,
          &v17,
          0);
  if ( v10 < 0 )
    goto LABEL_29;
  if ( !v17 )
  {
    v10 = -2147467261;
    goto LABEL_29;
  }
  v10 = (*(__int64 (__fastcall **)(struct BACKUP_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v17 + 80LL))(
          v17,
          L"BACKUP.NAME",
          &v19);
  if ( v10 >= 0 )
  {
    if ( v19 )
    {
      if ( !_wcsicmp(a3, L"RESTORE") )
      {
        v11 = BACKUP_OBJECT_EXTENSION::RestoreBackup(v14, a5, v17, v18, a7, &v21);
        goto LABEL_12;
      }
      if ( !_wcsicmp(a3, L"DELETE") )
      {
        v11 = BACKUP_OBJECT_EXTENSION::DeleteBackup(v15, a5, v17, v18, a7);
        goto LABEL_12;
      }
      v10 = -2147024846;
      goto LABEL_29;
    }
LABEL_28:
    v10 = -2147024809;
  }
LABEL_29:
  if ( v17 )
  {
    (*(void (__fastcall **)(struct BACKUP_OBJECT *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180024090  mov     [rsp-8+arg_0], rbx
0x180024095  push    rbp
0x180024096  push    rsi
0x180024097  push    rdi
0x180024098  push    r12
0x18002409a  push    r13
0x18002409c  push    r14
0x18002409e  push    r15
0x1800240a0  lea     rbp, [rsp-1C0h]
0x1800240a8  sub     rsp, 2C0h
0x1800240af  mov     rax, cs:__security_cookie
0x1800240b6  xor     rax, rsp
0x1800240b9  mov     [rbp+1F0h+var_40], rax
0x1800240c0  mov     rdi, [rbp+1F0h+arg_20]
0x1800240c7  lea     rcx, [rbp+1F0h+var_23E]; void *
0x1800240cb  mov     r12, [rbp+1F0h+arg_28]
0x1800240d2  xor     ebx, ebx
0x1800240d4  mov     r15, [rbp+1F0h+arg_30]
0x1800240db  mov     r14, r8
0x1800240de  mov     r13, rdx
0x1800240e1  mov     [rsp+2F0h+var_2B0], rbx
0x1800240e6  xorps   xmm0, xmm0
0x1800240e9  mov     [rsp+2F0h+var_2A0], rbx
0x1800240ee  xor     edx, edx; Val
0x1800240f0  mov     [rsp+2F0h+var_2A8], rbx
0x1800240f5  mov     r8d, 1FEh; Size
0x1800240fb  mov     rsi, r9
0x1800240fe  movups  [rsp+2F0h+var_298], xmm0
0x180024103  call    memset_0
0x180024108  mov     [rbp+1F0h+var_258], 200h
0x18002410f  lea     rax, [rbp+1F0h+var_240]
0x180024113  mov     [rbp+1F0h+var_260], rax
0x180024117  mov     [rbp+1F0h+var_254], 100h
0x18002411d  mov     [rbp+1F0h+var_250], ebx
0x180024120  mov     [rbp+1F0h+var_240], bx
0x180024124  test    r13, r13
0x180024127  jz      loc_18002434C
0x18002412d  test    r14, r14
0x180024130  jz      loc_18002434C
0x180024136  test    rsi, rsi
0x180024139  jz      loc_18002434C
0x18002413f  test    rdi, rdi
0x180024142  jz      loc_18002434C
0x180024148  test    r12, r12
0x18002414b  jz      loc_18002434C
0x180024151  test    r15, r15
0x180024154  jz      loc_18002434C
0x18002415a  mov     rax, [r12]
0x18002415e  lea     rdx, [rsp+2F0h+var_2A8]
0x180024163  mov     rcx, r12
0x180024166  mov     rax, [rax+50h]
0x18002416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002416f  mov     ebx, eax
0x180024171  test    eax, eax
0x180024173  js      loc_180024351
0x180024179  lea     rdx, aList; "LIST"
0x180024180  mov     rcx, r14; String1
0x180024183  call    cs:__imp__wcsicmp
0x180024189  test    eax, eax
0x18002418b  jnz     short loc_1800241B4
0x18002418d  mov     rax, [rdi]
0x180024190  mov     r9, r12
0x180024193  mov     dword ptr [rsp+2F0h+var_2C8], 0
0x18002419b  mov     r8, rsi
0x18002419e  mov     rdx, r13
0x1800241a1  mov     [rsp+2F0h+var_2D0], r15
0x1800241a6  mov     rcx, rdi
0x1800241a9  mov     rax, [rax+38h]
0x1800241ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241b2  jmp     short loc_1800241E0
0x1800241b4  lea     rdx, aAdd_0; "ADD"
0x1800241bb  mov     rcx, r14; String1
0x1800241be  call    cs:__imp__wcsicmp
0x1800241c4  xor     r12d, r12d
0x1800241c7  test    eax, eax
0x1800241c9  jnz     short loc_1800241E7
0x1800241cb  mov     r9, [rsp+2F0h+var_2A8]; struct ICommandParameterList *
0x1800241d0  mov     r8, rsi; unsigned __int16 *
0x1800241d3  mov     rdx, rdi; struct IExtensionContext *
0x1800241d6  mov     [rsp+2F0h+var_2D0], r15; struct ICommandObjectList *
0x1800241db  call    ?AddBackup@BACKUP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z; BACKUP_OBJECT_EXTENSION::AddBackup(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x1800241e0  mov     ebx, eax
0x1800241e2  jmp     loc_180024351
0x1800241e7  cmp     [rsi], r12w
0x1800241eb  jnz     loc_180024277
0x1800241f1  mov     r8, [rsp+2F0h+var_2A8]; struct ICommandParameterList *
0x1800241f6  lea     rax, [rsp+2F0h+var_280]
0x1800241fb  mov     [rsp+2F0h+var_2C0], 1; int
0x180024203  lea     r9, aBackupName; "BACKUP.NAME"
0x18002420a  mov     dword ptr [rsp+2F0h+var_2C8], r12d; int
0x18002420f  mov     rdx, rdi; struct IExtensionContext *
0x180024212  mov     [rsp+2F0h+var_2D0], rax; struct STRU *
0x180024217  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18002421c  mov     ebx, eax
0x18002421e  cmp     eax, 80070585h
0x180024223  jnz     short loc_18002426B
0x180024225  lea     rdx, aBackupName; "BACKUP.NAME"
0x18002422c  mov     dword ptr [rsp+2F0h+var_2D0], r12d
0x180024231  lea     rax, aBackup; "BACKUP"
0x180024238  mov     qword ptr [rsp+2F0h+var_298+8], rdx
0x18002423d  mov     qword ptr [rsp+2F0h+var_298], rax
0x180024242  lea     r9, [rsp+2F0h+var_298]
0x180024247  mov     rax, [rdi]
0x18002424a  mov     ebx, 80070032h
0x18002424f  mov     r8d, 0C00003EAh
0x180024255  mov     edx, ebx
0x180024257  mov     rcx, rdi
0x18002425a  mov     rax, [rax+90h]
0x180024261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024266  jmp     loc_180024351
0x18002426b  test    eax, eax
0x18002426d  js      loc_180024351
0x180024273  mov     rsi, [rbp+1F0h+var_260]
0x180024277  mov     rax, [rdi]
0x18002427a  lea     r9, [rsp+2F0h+var_2B0]
0x18002427f  mov     r8, rsi
0x180024282  mov     dword ptr [rsp+2F0h+var_2D0], r12d
0x180024287  mov     rdx, r13
0x18002428a  mov     rcx, rdi
0x18002428d  mov     rax, [rax+40h]
0x180024291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024296  mov     ebx, eax
0x180024298  test    eax, eax
0x18002429a  js      loc_180024351
0x1800242a0  cmp     [rsp+2F0h+var_2B0], r12
0x1800242a5  jnz     short loc_1800242B1
0x1800242a7  mov     ebx, 80004003h
0x1800242ac  jmp     loc_180024351
0x1800242b1  mov     rcx, [rsp+2F0h+var_2B0]
0x1800242b6  lea     r8, [rsp+2F0h+var_2A0]
0x1800242bb  lea     rdx, aBackupName; "BACKUP.NAME"
0x1800242c2  mov     rax, [rcx]
0x1800242c5  mov     rax, [rax+50h]
0x1800242c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242ce  mov     ebx, eax
0x1800242d0  test    eax, eax
0x1800242d2  js      short loc_180024351
0x1800242d4  cmp     [rsp+2F0h+var_2A0], r12
0x1800242d9  jz      short loc_18002434C
0x1800242db  lea     rdx, aRestore; "RESTORE"
0x1800242e2  mov     rcx, r14; String1
0x1800242e5  call    cs:__imp__wcsicmp
0x1800242eb  test    eax, eax
0x1800242ed  jnz     short loc_180024315
0x1800242ef  mov     r9, [rsp+2F0h+var_2A8]; struct ICommandParameterList *
0x1800242f4  lea     rax, [rsp+2F0h+var_288]
0x1800242f9  mov     r8, [rsp+2F0h+var_2B0]; struct BACKUP_OBJECT *
0x1800242fe  mov     rdx, rdi; struct IExtensionContext *
0x180024301  mov     [rsp+2F0h+var_2C8], rax; void **
0x180024306  mov     [rsp+2F0h+var_2D0], r15; struct ICommandObjectList *
0x18002430b  call    ?RestoreBackup@BACKUP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVBACKUP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAPEAX@Z; BACKUP_OBJECT_EXTENSION::RestoreBackup(IExtensionContext *,BACKUP_OBJECT *,ICommandParameterList *,ICommandObjectList *,void * *)
0x180024310  jmp     loc_1800241E0
0x180024315  lea     rdx, aDelete_0; "DELETE"
0x18002431c  mov     rcx, r14; String1
0x18002431f  call    cs:__imp__wcsicmp
0x180024325  test    eax, eax
0x180024327  jnz     short loc_180024345
0x180024329  mov     r9, [rsp+2F0h+var_2A8]; struct ICommandParameterList *
0x18002432e  mov     rdx, rdi; struct IExtensionContext *
0x180024331  mov     r8, [rsp+2F0h+var_2B0]; struct BACKUP_OBJECT *
0x180024336  mov     [rsp+2F0h+var_2D0], r15; struct ICommandObjectList *
0x18002433b  call    ?DeleteBackup@BACKUP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVBACKUP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; BACKUP_OBJECT_EXTENSION::DeleteBackup(IExtensionContext *,BACKUP_OBJECT *,ICommandParameterList *,ICommandObjectList *)
0x180024340  jmp     loc_1800241E0
0x180024345  mov     ebx, 80070032h
0x18002434a  jmp     short loc_180024351
0x18002434c  mov     ebx, 80070057h
0x180024351  mov     rcx, [rsp+2F0h+var_2B0]
0x180024356  xor     edi, edi
0x180024358  test    rcx, rcx
0x18002435b  jz      short loc_18002436E
0x18002435d  mov     rax, [rcx]
0x180024360  mov     rax, [rax+10h]
0x180024364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024369  mov     [rsp+2F0h+var_2B0], rdi
0x18002436e  mov     rcx, [rsp+2F0h+var_2A8]
0x180024373  test    rcx, rcx
0x180024376  jz      short loc_180024389
0x180024378  mov     rax, [rcx]
0x18002437b  mov     rax, [rax+10h]
0x18002437f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024384  mov     [rsp+2F0h+var_2A8], rdi
0x180024389  lea     rcx, [rsp+2F0h+var_280]; this
0x18002438e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024393  mov     eax, ebx
0x180024395  mov     rcx, [rbp+1F0h+var_40]
0x18002439c  xor     rcx, rsp; StackCookie
0x18002439f  call    __security_check_cookie
0x1800243a4  mov     rbx, [rsp+2F0h+arg_0]
0x1800243ac  add     rsp, 2C0h
0x1800243b3  pop     r15
0x1800243b5  pop     r14
0x1800243b7  pop     r13
0x1800243b9  pop     r12
0x1800243bb  pop     rdi
0x1800243bc  pop     rsi
0x1800243bd  pop     rbp
0x1800243be  retn
```
