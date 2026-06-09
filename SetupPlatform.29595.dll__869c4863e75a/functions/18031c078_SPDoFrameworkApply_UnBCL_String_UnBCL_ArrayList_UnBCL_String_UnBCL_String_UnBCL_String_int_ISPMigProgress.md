# SPDoFrameworkApply(UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,UnBCL::String *,UnBCL::String *,int,ISPMigProgress *)

- ea: `0x18031c078`
- end: `0x18031d77c`
- name: `?SPDoFrameworkApply@@YA?AW4MIGSTATUS@@PEAVString@UnBCL@@PEAV?$ArrayList@PEAVString@UnBCL@@@3@00HPEAUISPMigProgress@@@Z`
- size: `5892`
- prototype: `void __noreturn(struct UnBCL::String *, int, struct CSPTelemetryData *, int, int, int, struct UnBCL::String *, int, unsigned int, int, char, int, int, __int64, __int64, int, char, __int64, int, int, int, __int64, char, int, int, char, int, int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, int, int, int, int, int, int, __int64, char, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, int, char, int, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64, int, int, struct ISPMigProgress *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801fee00`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180044810`
- `0x180044820`
- `0x180057dec`
- `0x1800b42d0`
- `0x18015dc78`
- `0x18028f81c`
- `0x180292094`
- `0x1802c7f84`
- `0x1803014c4`
- `0x180302820`
- `0x180302f18`
- `0x180303910`
- `0x180303af0`
- `0x180303b40`
- `0x1803051e8`
- `0x180305408`
- `0x18030ee30`
- `0x180317914`
- `0x18031c078`
- `0x180332e7c`
- `0x18033e4f4`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18031c878`
- `KERNEL32!GetLastError` at `0x18031c925`
- `KERNEL32!GetLastError` at `0x18031c99f`
- `KERNEL32!GetLastError` at `0x18031cefa`
- `KERNEL32!GetLastError` at `0x18031cfdd`
- `KERNEL32!GetLastError` at `0x18031d160`
- `KERNEL32!GetLastError` at `0x18031d202`
- `KERNEL32!GetLastError` at `0x18031d276`
- `KERNEL32!GetLastError` at `0x18031d31e`
- `KERNEL32!GetLastError` at `0x18031d3c6`
- `KERNEL32!GetLastError` at `0x18031d46e`
- `KERNEL32!GetLastError` at `0x18031d516`
- `KERNEL32!GetLastError` at `0x18031d62d`
- `KERNEL32!GetLastError` at `0x18031d6da`
- `KERNEL32!GetLastError` at `0x18031c878`
- `KERNEL32!GetLastError` at `0x18031c925`
- `KERNEL32!GetLastError` at `0x18031c99f`
- `KERNEL32!GetLastError` at `0x18031cefa`
- `KERNEL32!GetLastError` at `0x18031cfdd`
- `KERNEL32!GetLastError` at `0x18031d160`
- `KERNEL32!GetLastError` at `0x18031d202`
- `KERNEL32!GetLastError` at `0x18031d276`
- `KERNEL32!GetLastError` at `0x18031d31e`
- `KERNEL32!GetLastError` at `0x18031d3c6`
- `KERNEL32!GetLastError` at `0x18031d46e`
- `KERNEL32!GetLastError` at `0x18031d516`
- `KERNEL32!GetLastError` at `0x18031d62d`
- `KERNEL32!GetLastError` at `0x18031d6da`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031c837`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031c837`
- `unbcl!?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x18031cb6b`
- `unbcl!?Load@XmlDocument@UnBCL@@QEAAXPEAVString@2@@Z` at `0x18031cb6b`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031c7a8`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031c7a8`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031c7cf`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031c7cf`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031cd4e`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031cdb2`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031ce15`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031cd4e`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031cdb2`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031ce15`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cbba`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cc2d`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cd00`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cbba`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cc2d`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031cd00`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x18031cb12`
- `unbcl!??0XmlDocument@UnBCL@@QEAA@XZ` at `0x18031cb12`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031c7fd`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031c7fd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031c702`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031c702`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c10f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c11e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c164`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c173`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1b2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1c1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1eb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c237`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c275`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c284`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c2c7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c2d6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c319`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c328`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c352`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c37c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c3a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c3d0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c413`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c422`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c44c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c48f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c49e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c4e1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c4f0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c51a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c55d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c56c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5af`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5be`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5e8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c612`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c655`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c664`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c68e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c6b8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c6e2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c736`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c781`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c790`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c81a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d318`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d3c0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d468`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d510`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d5b8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c10f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c11e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c164`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c173`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1b2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1c1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c1eb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c237`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c275`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c284`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c2c7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c2d6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c319`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c328`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c352`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c37c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c3a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c3d0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c413`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c422`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c44c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c48f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c49e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c4e1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c4f0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c51a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c55d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c56c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5af`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5be`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c5e8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c612`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c655`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c664`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c68e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c6b8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c6e2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c736`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c781`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c790`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031c81a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d318`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d3c0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d468`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d510`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031d5b8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c0e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c0f6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c136`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c14b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c184`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c199`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c1d3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c209`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c21e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c247`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c25c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c299`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c2ae`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c2eb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c300`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c33a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c364`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c38e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c3b8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c3e5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c3fa`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c434`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c461`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c476`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c4b3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c4c8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c502`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c52f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c544`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c581`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c596`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c5d0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c5fa`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c627`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c63c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c676`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c6a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c6ca`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c71a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c753`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c768`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c7f3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031d29d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031d345`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031d3ed`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031d495`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031d53d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c0e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c0f6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c136`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c14b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c184`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c199`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031c1d3`

## string_xrefs

- `0x18031c7e4`: `SetupPlatform.dll`
- `0x18031d3de`: `registry`
- `0x18031d40a`: `   Registry: %d`
- `0x18031c46a`: `MIG_CONTENT_COMPARE_ACLS`
- `0x18031c3ac`: `MIG_REPL_MANIFESTS_DIR`
- `0x18031c358`: `MIG_MANIFESTS`
- `0x18031c382`: `MIG_MANIFESTS_DIR`
- `0x18031c618`: `mxeagent.dll`
- `0x18031c630`: `MIG_AGENT_DLL_FILTER`
- `0x18031c58a`: `MIG_FILE_COMPARE`
- `0x18031c6be`: `MIG_UPGRADE_AGENT_NO_DISCOVER`
- `0x18031c694`: `MIG_UPGRADE_CONFIG_SCRIPT`
- `0x18031c3d6`: `upgrade_frmwrk.xml`
- `0x18031c4a4`: `COPYRAW`
- `0x18031cff8`: `%hs: Cannot create the UNC store. Error: 0x%08X`

## pseudocode

```c

```

## disassembly

```asm
0x18031c078  mov     rax, rsp
0x18031c07b  mov     [rax+20h], r9
0x18031c07f  mov     [rax+18h], r8
0x18031c083  mov     [rax+10h], rdx
0x18031c087  mov     [rax+8], rcx
0x18031c08b  push    rbx
0x18031c08c  push    rsi
0x18031c08d  push    rdi
0x18031c08e  push    r13
0x18031c090  push    r14
0x18031c092  push    r15
0x18031c094  sub     rsp, 2E8h
0x18031c09b  mov     qword ptr [rax-120h], 0FFFFFFFFFFFFFFFEh
0x18031c0a6  mov     rax, r9
0x18031c0a9  mov     rdi, rcx
0x18031c0ac  xor     esi, esi
0x18031c0ae  mov     [rsp+318h+var_2B0], esi
0x18031c0b2  mov     [rsp+318h+var_2B4], sil
0x18031c0b7  test    rcx, rcx
0x18031c0ba  jz      loc_18031CD2B
0x18031c0c0  test    r8, r8
0x18031c0c3  jz      loc_18031CD8E
0x18031c0c9  test    rax, rax
0x18031c0cc  jz      loc_18031CDF2
0x18031c0d2  lea     rdx, aFrameworkApply; "Framework apply"
0x18031c0d9  lea     rcx, [rsp+318h+var_278]
0x18031c0e1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c0e7  mov     rbx, rax
0x18031c0ea  lea     rdx, aMigDiagSession; "MIG_DIAG_SESSION_NAME"
0x18031c0f1  lea     rcx, [rsp+318h+var_2A8]
0x18031c0f6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c0fc  nop
0x18031c0fd  mov     rdx, rbx
0x18031c100  mov     rcx, rax
0x18031c103  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c109  nop
0x18031c10a  lea     rcx, [rsp+318h+var_2A8]
0x18031c10f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c115  nop
0x18031c116  lea     rcx, [rsp+318h+var_278]
0x18031c11e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c124  lea     r14, Value; "1"
0x18031c12b  mov     rdx, r14
0x18031c12e  lea     rcx, [rsp+318h+var_278]
0x18031c136  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c13c  mov     rbx, rax
0x18031c13f  lea     rdx, aMigUpgrade; "MIG_UPGRADE"
0x18031c146  lea     rcx, [rsp+318h+var_2A8]
0x18031c14b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c151  nop
0x18031c152  mov     rdx, rbx
0x18031c155  mov     rcx, rax
0x18031c158  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c15e  nop
0x18031c15f  lea     rcx, [rsp+318h+var_2A8]
0x18031c164  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c16a  nop
0x18031c16b  lea     rcx, [rsp+318h+var_278]
0x18031c173  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c179  mov     rdx, r14
0x18031c17c  lea     rcx, [rsp+318h+var_278]
0x18031c184  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c18a  mov     rbx, rax
0x18031c18d  lea     rdx, aMigOsdbCheckWi; "MIG_OSDB_CHECK_WINSXS"
0x18031c194  lea     rcx, [rsp+318h+var_2A8]
0x18031c199  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c19f  nop
0x18031c1a0  mov     rdx, rbx
0x18031c1a3  mov     rcx, rax
0x18031c1a6  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c1ac  nop
0x18031c1ad  lea     rcx, [rsp+318h+var_2A8]
0x18031c1b2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c1b8  nop
0x18031c1b9  lea     rcx, [rsp+318h+var_278]
0x18031c1c1  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c1c7  lea     rdx, aMigUpgradeOpti; "MIG_UPGRADE_OPTIMIZE_GAC_MIGRATION"
0x18031c1ce  lea     rcx, [rsp+318h+var_2A8]
0x18031c1d3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c1d9  nop
0x18031c1da  xor     edx, edx
0x18031c1dc  mov     rcx, rax
0x18031c1df  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c1e5  nop
0x18031c1e6  lea     rcx, [rsp+318h+var_2A8]
0x18031c1eb  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c1f1  lea     rcx, [rsp+318h+var_278]
0x18031c1f9  cmp     [rsp+318h+arg_20], esi
0x18031c200  jz      short loc_18031C240
0x18031c202  lea     rdx, aFrameworkfull; "FrameworkFull"
0x18031c209  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c20f  mov     rbx, rax
0x18031c212  lea     rdx, aMigScope; "MIG_SCOPE"
0x18031c219  lea     rcx, [rsp+318h+var_2A8]
0x18031c21e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c224  nop
0x18031c225  mov     rdx, rbx
0x18031c228  mov     rcx, rax
0x18031c22b  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c231  nop
0x18031c232  lea     rcx, [rsp+318h+var_2A8]
0x18031c237  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c23d  nop
0x18031c23e  jmp     short loc_18031C27C
0x18031c240  lea     rdx, aFrameworkbasic; "FrameworkBasic"
0x18031c247  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c24d  mov     rbx, rax
0x18031c250  lea     rdx, aMigScope; "MIG_SCOPE"
0x18031c257  lea     rcx, [rsp+318h+var_2A8]
0x18031c25c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c262  nop
0x18031c263  mov     rdx, rbx
0x18031c266  mov     rcx, rax
0x18031c269  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c26f  nop
0x18031c270  lea     rcx, [rsp+318h+var_2A8]
0x18031c275  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c27b  nop
0x18031c27c  lea     rcx, [rsp+318h+var_278]
0x18031c284  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c28a  lea     rdx, aNo; "No"
0x18031c291  lea     rcx, [rsp+318h+var_278]
0x18031c299  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c29f  mov     rbx, rax
0x18031c2a2  lea     rdx, aMigScopeRequir; "MIG_SCOPE_REQUIRED"
0x18031c2a9  lea     rcx, [rsp+318h+var_2A8]
0x18031c2ae  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c2b4  nop
0x18031c2b5  mov     rdx, rbx
0x18031c2b8  mov     rcx, rax
0x18031c2bb  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c2c1  nop
0x18031c2c2  lea     rcx, [rsp+318h+var_2A8]
0x18031c2c7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c2cd  nop
0x18031c2ce  lea     rcx, [rsp+318h+var_278]
0x18031c2d6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c2dc  lea     rdx, aNo; "No"
0x18031c2e3  lea     rcx, [rsp+318h+var_278]
0x18031c2eb  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c2f1  mov     rbx, rax
0x18031c2f4  lea     rdx, aMigUseProcessE; "MIG_USE_PROCESS_ENV"
0x18031c2fb  lea     rcx, [rsp+318h+var_2A8]
0x18031c300  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c306  nop
0x18031c307  mov     rdx, rbx
0x18031c30a  mov     rcx, rax
0x18031c30d  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c313  nop
0x18031c314  lea     rcx, [rsp+318h+var_2A8]
0x18031c319  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c31f  nop
0x18031c320  lea     rcx, [rsp+318h+var_278]
0x18031c328  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c32e  lea     rdx, aMigDisableCont; "MIG_DISABLE_CONTENT_REMAP"
0x18031c335  lea     rcx, [rsp+318h+var_2A8]
0x18031c33a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c340  nop
0x18031c341  xor     edx, edx
0x18031c343  mov     rcx, rax
0x18031c346  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c34c  nop
0x18031c34d  lea     rcx, [rsp+318h+var_2A8]
0x18031c352  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c358  lea     rdx, aMigManifests; "MIG_MANIFESTS"
0x18031c35f  lea     rcx, [rsp+318h+var_2A8]
0x18031c364  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c36a  nop
0x18031c36b  xor     edx, edx
0x18031c36d  mov     rcx, rax
0x18031c370  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c376  nop
0x18031c377  lea     rcx, [rsp+318h+var_2A8]
0x18031c37c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c382  lea     rdx, aMigManifestsDi; "MIG_MANIFESTS_DIR"
0x18031c389  lea     rcx, [rsp+318h+var_2A8]
0x18031c38e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c394  nop
0x18031c395  xor     edx, edx
0x18031c397  mov     rcx, rax
0x18031c39a  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c3a0  nop
0x18031c3a1  lea     rcx, [rsp+318h+var_2A8]
0x18031c3a6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c3ac  lea     rdx, aMigReplManifes; "MIG_REPL_MANIFESTS_DIR"
0x18031c3b3  lea     rcx, [rsp+318h+var_2A8]
0x18031c3b8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c3be  nop
0x18031c3bf  xor     edx, edx
0x18031c3c1  mov     rcx, rax
0x18031c3c4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c3ca  nop
0x18031c3cb  lea     rcx, [rsp+318h+var_2A8]
0x18031c3d0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c3d6  lea     rdx, aUpgradeFrmwrkX; "upgrade_frmwrk.xml"
0x18031c3dd  lea     rcx, [rsp+318h+var_278]
0x18031c3e5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c3eb  mov     rbx, rax
0x18031c3ee  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x18031c3f5  lea     rcx, [rsp+318h+var_2A8]
0x18031c3fa  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c400  nop
0x18031c401  mov     rdx, rbx
0x18031c404  mov     rcx, rax
0x18031c407  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c40d  nop
0x18031c40e  lea     rcx, [rsp+318h+var_2A8]
0x18031c413  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c419  nop
0x18031c41a  lea     rcx, [rsp+318h+var_278]
0x18031c422  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c428  lea     rdx, aMigrationScrip; "MIGRATION_SCRIPT_DIR"
0x18031c42f  lea     rcx, [rsp+318h+var_2A8]
0x18031c434  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c43a  nop
0x18031c43b  xor     edx, edx
0x18031c43d  mov     rcx, rax
0x18031c440  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c446  nop
0x18031c447  lea     rcx, [rsp+318h+var_2A8]
0x18031c44c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c452  lea     rdx, a0; "0"
0x18031c459  lea     rcx, [rsp+318h+var_278]
0x18031c461  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c467  mov     rbx, rax
0x18031c46a  lea     rdx, aMigContentComp; "MIG_CONTENT_COMPARE_ACLS"
0x18031c471  lea     rcx, [rsp+318h+var_2A8]
0x18031c476  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c47c  nop
0x18031c47d  mov     rdx, rbx
0x18031c480  mov     rcx, rax
0x18031c483  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c489  nop
0x18031c48a  lea     rcx, [rsp+318h+var_2A8]
0x18031c48f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c495  nop
0x18031c496  lea     rcx, [rsp+318h+var_278]
0x18031c49e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c4a4  lea     rdx, aCopyraw; "COPYRAW"
0x18031c4ab  lea     rcx, [rsp+318h+var_278]
0x18031c4b3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c4b9  mov     rbx, rax
0x18031c4bc  lea     rdx, aMigEfsMode; "MIG_EFS_MODE"
0x18031c4c3  lea     rcx, [rsp+318h+var_2A8]
0x18031c4c8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c4ce  nop
0x18031c4cf  mov     rdx, rbx
0x18031c4d2  mov     rcx, rax
0x18031c4d5  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c4db  nop
0x18031c4dc  lea     rcx, [rsp+318h+var_2A8]
0x18031c4e1  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c4e7  nop
0x18031c4e8  lea     rcx, [rsp+318h+var_278]
0x18031c4f0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c4f6  lea     rdx, aMigIgnoreProfi; "MIG_IGNORE_PROFILE_MISSING"
0x18031c4fd  lea     rcx, [rsp+318h+var_2A8]
0x18031c502  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c508  nop
0x18031c509  xor     edx, edx
0x18031c50b  mov     rcx, rax
0x18031c50e  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c514  nop
0x18031c515  lea     rcx, [rsp+318h+var_2A8]
0x18031c51a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c520  lea     rdx, a0; "0"
0x18031c527  lea     rcx, [rsp+318h+var_278]
0x18031c52f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c535  mov     rbx, rax
0x18031c538  lea     rdx, aMigFailOnProfi; "MIG_FAIL_ON_PROFILE_ERROR"
0x18031c53f  lea     rcx, [rsp+318h+var_2A8]
0x18031c544  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c54a  nop
0x18031c54b  mov     rdx, rbx
0x18031c54e  mov     rcx, rax
0x18031c551  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c557  nop
0x18031c558  lea     rcx, [rsp+318h+var_2A8]
0x18031c55d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c563  nop
0x18031c564  lea     rcx, [rsp+318h+var_278]
0x18031c56c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c572  lea     rdx, aTime; "TIME"
0x18031c579  lea     rcx, [rsp+318h+var_278]
0x18031c581  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c587  mov     rbx, rax
0x18031c58a  lea     rdx, aMigFileCompare; "MIG_FILE_COMPARE"
0x18031c591  lea     rcx, [rsp+318h+var_2A8]
0x18031c596  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031c59c  nop
0x18031c59d  mov     rdx, rbx
0x18031c5a0  mov     rcx, rax
0x18031c5a3  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031c5a9  nop
0x18031c5aa  lea     rcx, [rsp+318h+var_2A8]
0x18031c5af  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c5b5  nop
0x18031c5b6  lea     rcx, [rsp+318h+var_278]
0x18031c5be  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031c5c4  lea     rdx, aMigCmiMachineS; "MIG_CMI_MACHINE_SPECIFIC"
  ... truncated ...
```
