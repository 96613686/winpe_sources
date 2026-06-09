# CommonUtil::_dynamic_initializer_for__gs_VersionDll__

- ea: `0x1800011d0`
- end: `0x180001259`
- name: `CommonUtil::_dynamic_initializer_for__gs_VersionDll__`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800011d0`
- `0x18000a010`

## import_xrefs

- `mpclient!MpUtilsExportFunctions` at `0x18000120a`
- `mpclient!MpUtilsExportFunctions` at `0x18000122f`
- `mpclient!MpUtilsExportFunctions` at `0x18000120a`
- `mpclient!MpUtilsExportFunctions` at `0x18000122f`

## pseudocode

```c
void CommonUtil::_dynamic_initializer_for__gs_VersionDll__()
{
  __int64 v0; // rax
  __int64 (__fastcall *v1)(__int64 (__fastcall *)()); // rax
  __int64 v2; // rax
  __int64 (__fastcall *v3)(__int64 (__fastcall *)()); // rax

  if ( !byte_18001381D )
  {
    qword_1800137D0 = (__int64)&off_180012208;
    qword_1800137D8 = (__int64)off_180012210[0];
    *off_180012210[0] = &qword_1800137D0;
    off_180012210[0] = (_UNKNOWN **)&qword_1800137D0;
    v0 = MpUtilsExportFunctions();
    v1 = (__int64 (__fastcall *)(__int64 (__fastcall *)()))(*(__int64 (**)(void))(v0 + 160))();
    qword_1800137E0 = v1(CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize);
    v2 = MpUtilsExportFunctions();
    v3 = (__int64 (__fastcall *)(__int64 (__fastcall *)()))(*(__int64 (**)(void))(v2 + 160))();
    qword_1800137E8 = v3(CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy);
  }
}

```

## disassembly

```asm
0x1800011d0  sub     rsp, 28h
0x1800011d4  cmp     cs:byte_18001381D, 0
0x1800011db  jnz     short loc_180001254
0x1800011dd  mov     rax, cs:off_180012210
0x1800011e4  lea     rcx, off_180012208
0x1800011eb  mov     cs:qword_1800137D0, rcx
0x1800011f2  lea     rcx, qword_1800137D0
0x1800011f9  mov     cs:qword_1800137D8, rax
0x180001200  mov     [rax], rcx
0x180001203  mov     cs:off_180012210, rcx
0x18000120a  call    cs:__imp_MpUtilsExportFunctions
0x180001210  mov     rax, [rax+0A0h]
0x180001217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121c  lea     rcx, ?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)
0x180001223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001228  mov     cs:qword_1800137E0, rax
0x18000122f  call    cs:__imp_MpUtilsExportFunctions
0x180001235  mov     rax, [rax+0A0h]
0x18000123c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001241  lea     rcx, ?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)
0x180001248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000124d  mov     cs:qword_1800137E8, rax
0x180001254  add     rsp, 28h
0x180001258  retn
```
