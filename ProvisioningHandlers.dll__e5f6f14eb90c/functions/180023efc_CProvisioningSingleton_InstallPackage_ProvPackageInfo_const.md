# CProvisioningSingleton::InstallPackage(ProvPackageInfo const &)

- ea: `0x180023efc`
- end: `0x180023f47`
- name: `?InstallPackage@CProvisioningSingleton@@QEAAJAEBVProvPackageInfo@@@Z`
- size: `75`
- prototype: `int(CProvisioningSingleton *__hidden this, const struct ProvPackageInfo *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013c10`
- `0x180019ee0`

## callees

- `0x1800087ec`
- `0x180023efc`
- `0x18002c010`

## string_xrefs

- `0x180023f26`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningSingleton::InstallPackage(
        CProvisioningSingleton *this,
        const struct ProvPackageInfo *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (*(__int64 (__fastcall **)(__int64, const struct ProvPackageInfo *, __int64))(*(_QWORD *)qword_18003EF18 + 40LL))(
         qword_18003EF18,
         a2,
         5);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13F,
    (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180023efc  push    rbx; int
0x180023efe  sub     rsp, 20h
0x180023f02  mov     rcx, cs:qword_18003EF18
0x180023f09  mov     r8d, 5
0x180023f0f  mov     rax, [rcx]
0x180023f12  mov     rax, [rax+28h]
0x180023f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f1b  mov     ebx, eax
0x180023f1d  test    eax, eax
0x180023f1f  jns     short loc_180023F3E
0x180023f21  mov     rcx, [rsp+28h]; this
0x180023f26  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023f2d  mov     r9d, eax; char *
0x180023f30  mov     edx, 13Fh; void *
0x180023f35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f3a  mov     eax, ebx
0x180023f3c  jmp     short loc_180023F40
0x180023f3e  xor     eax, eax
0x180023f40  add     rsp, 20h
0x180023f44  pop     rbx
0x180023f45  retn
```
