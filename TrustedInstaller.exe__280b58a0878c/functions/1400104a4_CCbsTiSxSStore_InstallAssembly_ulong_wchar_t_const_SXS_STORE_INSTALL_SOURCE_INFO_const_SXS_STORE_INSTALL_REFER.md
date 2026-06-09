# CCbsTiSxSStore::InstallAssembly(ulong,wchar_t const *,_SXS_STORE_INSTALL_SOURCE_INFO const *,_SXS_STORE_INSTALL_REFERENCEW const *)

- ea: `0x1400104a4`
- end: `0x140010563`
- name: `?InstallAssembly@CCbsTiSxSStore@@UEAAJKPEB_WPEBU_SXS_STORE_INSTALL_SOURCE_INFO@@PEBU_SXS_STORE_INSTALL_REFERENCEW@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CCbsTiSxSStore *__hidden this, unsigned int, const wchar_t *, const struct _SXS_STORE_INSTALL_SOURCE_INFO *, const struct _SXS_STORE_INSTALL_REFERENCEW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140010490`

## callees

- `0x1400104a4`
- `0x1400108cc`
- `0x140017658`
- `0x1400200b8`
- `0x14002b010`

## string_xrefs

- `0x14001052b`: `Failed to create worker SxS store`
- `0x1400104c2`: `Invalid argument: manifestPath.`

## pseudocode

```c
__int64 __fastcall CCbsTiSxSStore::InstallAssembly(
        CCbsTiSxSStore *this,
        unsigned int a2,
        const wchar_t *a3,
        const struct _SXS_STORE_INSTALL_SOURCE_INFO *a4,
        const struct _SXS_STORE_INSTALL_REFERENCEW *a5)
{
  const char *v9; // r9
  size_t v10; // rdx
  unsigned int v11; // ebx
  int IsAdministrator; // eax

  if ( !a3 )
  {
    v9 = "Invalid argument: manifestPath.";
LABEL_3:
    v10 = 2147500035LL;
    v11 = -2147467261;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v9 = "Invalid argument: pcsisi.";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v9 = "Invalid argument: pReference.";
    goto LABEL_3;
  }
  IsAdministrator = EnsureCallerIsAdministrator();
  v11 = IsAdministrator;
  if ( IsAdministrator >= 0 )
  {
    IsAdministrator = CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable((CCbsTiSxSStore *)((char *)this - 88));
    v11 = IsAdministrator;
    if ( IsAdministrator >= 0 )
      return (*(unsigned int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, const struct _SXS_STORE_INSTALL_SOURCE_INFO *, const struct _SXS_STORE_INSTALL_REFERENCEW *))(**((_QWORD **)this - 2) + 32LL))(
               *((_QWORD *)this - 2),
               a2,
               a3,
               a4,
               a5);
    v9 = "Failed to create worker SxS store";
  }
  else
  {
    v9 = "Client failed admin check.";
  }
  v10 = (unsigned int)IsAdministrator;
LABEL_4:
  CBSWdsLogLight(0x4000000u, v10, (size_t *)1, v9);
  return v11;
}

```

## disassembly

```asm
0x1400104a4  push    rbx
0x1400104a6  push    rbp
0x1400104a7  push    rsi
0x1400104a8  push    rdi
0x1400104a9  push    r14
0x1400104ab  push    r15
0x1400104ad  sub     rsp, 38h
0x1400104b1  mov     rsi, r9
0x1400104b4  mov     r14, r8
0x1400104b7  mov     r15d, edx
0x1400104ba  mov     rbp, rcx
0x1400104bd  test    r8, r8
0x1400104c0  jnz     short loc_1400104E2
0x1400104c2  lea     r9, aInvalidArgumen_13; "Invalid argument: manifestPath."
0x1400104c9  mov     edx, 80004003h
0x1400104ce  mov     ebx, edx
0x1400104d0  mov     r8d, 1
0x1400104d6  mov     ecx, 4000000h
0x1400104db  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400104e0  jmp     short loc_140010554
0x1400104e2  test    rsi, rsi
0x1400104e5  jnz     short loc_1400104F0
0x1400104e7  lea     r9, aInvalidArgumen_5; "Invalid argument: pcsisi."
0x1400104ee  jmp     short loc_1400104C9
0x1400104f0  mov     rdi, [rsp+68h+arg_20]
0x1400104f8  test    rdi, rdi
0x1400104fb  jnz     short loc_140010506
0x1400104fd  lea     r9, aInvalidArgumen_3; "Invalid argument: pReference."
0x140010504  jmp     short loc_1400104C9
0x140010506  call    EnsureCallerIsAdministrator
0x14001050b  mov     ebx, eax
0x14001050d  test    eax, eax
0x14001050f  jns     short loc_14001051C
0x140010511  lea     r9, aClientFailedAd; "Client failed admin check."
0x140010518  mov     edx, eax
0x14001051a  jmp     short loc_1400104D0
0x14001051c  lea     rcx, [rbp-58h]; this
0x140010520  call    ?MakeSureWorkerSxSStoreAvailable@CCbsTiSxSStore@@AEAAJXZ; CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(void)
0x140010525  mov     ebx, eax
0x140010527  test    eax, eax
0x140010529  jns     short loc_140010534
0x14001052b  lea     r9, aFailedToCreate_15; "Failed to create worker SxS store"
0x140010532  jmp     short loc_140010518
0x140010534  mov     rcx, [rbp-10h]
0x140010538  mov     r9, rsi
0x14001053b  mov     r8, r14
0x14001053e  mov     [rsp+68h+var_48], rdi
0x140010543  mov     edx, r15d
0x140010546  mov     rax, [rcx]
0x140010549  mov     rax, [rax+20h]
0x14001054d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010552  mov     ebx, eax
0x140010554  mov     eax, ebx
0x140010556  add     rsp, 38h
0x14001055a  pop     r15
0x14001055c  pop     r14
0x14001055e  pop     rdi
0x14001055f  pop     rsi
0x140010560  pop     rbp
0x140010561  pop     rbx
0x140010562  retn
```
