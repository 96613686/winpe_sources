# CCbsTiSxSStore::UninstallAssembly(ulong,wchar_t const *,_SXS_STORE_INSTALL_REFERENCEW const *,ulong *)

- ea: `0x140012a74`
- end: `0x140012b33`
- name: `?UninstallAssembly@CCbsTiSxSStore@@UEAAJKPEB_WPEBU_SXS_STORE_INSTALL_REFERENCEW@@PEAK@Z`
- size: `191`
- prototype: `__int64 __fastcall(CCbsTiSxSStore *__hidden this, unsigned int, const wchar_t *, const struct _SXS_STORE_INSTALL_REFERENCEW *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140012a60`

## callees

- `0x1400108cc`
- `0x140012a74`
- `0x140017658`
- `0x1400200b8`
- `0x14002b010`

## string_xrefs

- `0x140012afb`: `Failed to create worker SxS store`
- `0x140012ab7`: `Invalid argument: lpInstallRef.`

## pseudocode

```c
__int64 __fastcall CCbsTiSxSStore::UninstallAssembly(
        CCbsTiSxSStore *this,
        unsigned int a2,
        const wchar_t *a3,
        const struct _SXS_STORE_INSTALL_REFERENCEW *a4,
        unsigned int *a5)
{
  const char *v9; // r9
  size_t v10; // rdx
  unsigned int v11; // ebx
  int IsAdministrator; // eax

  if ( !a3 )
  {
    v9 = "Invalid argument: lpAssemblyIdentity.";
LABEL_3:
    v10 = 2147500035LL;
    v11 = -2147467261;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v9 = "Invalid argument: lpInstallRef.";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v9 = "Invalid argument: pdwDisposition.";
    goto LABEL_3;
  }
  IsAdministrator = EnsureCallerIsAdministrator();
  v11 = IsAdministrator;
  if ( IsAdministrator >= 0 )
  {
    IsAdministrator = CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable((CCbsTiSxSStore *)((char *)this - 88));
    v11 = IsAdministrator;
    if ( IsAdministrator >= 0 )
      return (*(unsigned int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, const struct _SXS_STORE_INSTALL_REFERENCEW *, unsigned int *))(**((_QWORD **)this - 2) + 48LL))(
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
0x140012a74  push    rbx
0x140012a76  push    rbp
0x140012a77  push    rsi
0x140012a78  push    rdi
0x140012a79  push    r14
0x140012a7b  push    r15
0x140012a7d  sub     rsp, 38h
0x140012a81  mov     rsi, r9
0x140012a84  mov     r14, r8
0x140012a87  mov     r15d, edx
0x140012a8a  mov     rbp, rcx
0x140012a8d  test    r8, r8
0x140012a90  jnz     short loc_140012AB2
0x140012a92  lea     r9, aInvalidArgumen_23; "Invalid argument: lpAssemblyIdentity."
0x140012a99  mov     edx, 80004003h
0x140012a9e  mov     ebx, edx
0x140012aa0  mov     r8d, 1
0x140012aa6  mov     ecx, 4000000h
0x140012aab  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012ab0  jmp     short loc_140012B24
0x140012ab2  test    rsi, rsi
0x140012ab5  jnz     short loc_140012AC0
0x140012ab7  lea     r9, aInvalidArgumen_29; "Invalid argument: lpInstallRef."
0x140012abe  jmp     short loc_140012A99
0x140012ac0  mov     rdi, [rsp+68h+arg_20]
0x140012ac8  test    rdi, rdi
0x140012acb  jnz     short loc_140012AD6
0x140012acd  lea     r9, aInvalidArgumen_6; "Invalid argument: pdwDisposition."
0x140012ad4  jmp     short loc_140012A99
0x140012ad6  call    EnsureCallerIsAdministrator
0x140012adb  mov     ebx, eax
0x140012add  test    eax, eax
0x140012adf  jns     short loc_140012AEC
0x140012ae1  lea     r9, aClientFailedAd; "Client failed admin check."
0x140012ae8  mov     edx, eax
0x140012aea  jmp     short loc_140012AA0
0x140012aec  lea     rcx, [rbp-58h]; this
0x140012af0  call    ?MakeSureWorkerSxSStoreAvailable@CCbsTiSxSStore@@AEAAJXZ; CCbsTiSxSStore::MakeSureWorkerSxSStoreAvailable(void)
0x140012af5  mov     ebx, eax
0x140012af7  test    eax, eax
0x140012af9  jns     short loc_140012B04
0x140012afb  lea     r9, aFailedToCreate_15; "Failed to create worker SxS store"
0x140012b02  jmp     short loc_140012AE8
0x140012b04  mov     rcx, [rbp-10h]
0x140012b08  mov     r9, rsi
0x140012b0b  mov     r8, r14
0x140012b0e  mov     [rsp+68h+var_48], rdi
0x140012b13  mov     edx, r15d
0x140012b16  mov     rax, [rcx]
0x140012b19  mov     rax, [rax+30h]
0x140012b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b22  mov     ebx, eax
0x140012b24  mov     eax, ebx
0x140012b26  add     rsp, 38h
0x140012b2a  pop     r15
0x140012b2c  pop     r14
0x140012b2e  pop     rdi
0x140012b2f  pop     rsi
0x140012b30  pop     rbp
0x140012b31  pop     rbx
0x140012b32  retn
```
