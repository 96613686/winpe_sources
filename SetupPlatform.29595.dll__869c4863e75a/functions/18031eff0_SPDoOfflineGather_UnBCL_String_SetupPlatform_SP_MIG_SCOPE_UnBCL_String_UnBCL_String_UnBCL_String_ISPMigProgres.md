# SPDoOfflineGather(UnBCL::String *,SetupPlatform::SP_MIG_SCOPE,UnBCL::String *,UnBCL::String *,UnBCL::String *,ISPMigProgress *)

- ea: `0x18031eff0`
- end: `0x1803208c3`
- name: `?SPDoOfflineGather@@YA?AW4MIGSTATUS@@PEAVString@UnBCL@@W4SP_MIG_SCOPE@SetupPlatform@@000PEAUISPMigProgress@@@Z`
- size: `6355`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801fee00`
- `0x18020f27c`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180035de8`
- `0x18003d0e8`
- `0x180044810`
- `0x180044820`
- `0x18004d4b4`
- `0x180057dec`
- `0x1800b42d0`
- `0x1801ee484`
- `0x1802c7f84`
- `0x1802cff64`
- `0x180301454`
- `0x1803014a8`
- `0x1803014c4`
- `0x180302740`
- `0x180302820`
- `0x180302f18`
- `0x1803039b0`
- `0x180303a00`
- `0x1803051c0`
- `0x1803051e8`
- `0x180305408`
- `0x18030ee30`
- `0x180317914`
- `0x18031eff0`
- `0x180332e7c`
- `0x18033e4f4`
- `0x180341894`
- `0x180509010`

## import_xrefs

- `ADVAPI32!TraceEvent` at `0x18031f0d5`
- `ADVAPI32!TraceEvent` at `0x18031fe80`
- `ADVAPI32!TraceEvent` at `0x18031f0d5`
- `ADVAPI32!TraceEvent` at `0x18031fe80`
- `KERNEL32!GetLastError` at `0x18031f944`
- `KERNEL32!GetLastError` at `0x18031f9fc`
- `KERNEL32!GetLastError` at `0x18031fa6f`
- `KERNEL32!GetLastError` at `0x18031fb6a`
- `KERNEL32!GetLastError` at `0x18031fc64`
- `KERNEL32!GetLastError` at `0x18032000a`
- `KERNEL32!GetLastError` at `0x180320161`
- `KERNEL32!GetLastError` at `0x18032025c`
- `KERNEL32!GetLastError` at `0x18032030e`
- `KERNEL32!GetLastError` at `0x1803203a2`
- `KERNEL32!GetLastError` at `0x180320439`
- `KERNEL32!GetLastError` at `0x180320498`
- `KERNEL32!GetLastError` at `0x180320540`
- `KERNEL32!GetLastError` at `0x1803205e3`
- `KERNEL32!GetLastError` at `0x180320686`
- `KERNEL32!GetLastError` at `0x180320729`
- `KERNEL32!GetLastError` at `0x18032082a`
- `KERNEL32!GetLastError` at `0x18031f944`
- `KERNEL32!GetLastError` at `0x18031f9fc`
- `KERNEL32!GetLastError` at `0x18031fa6f`
- `KERNEL32!GetLastError` at `0x18031fb6a`
- `KERNEL32!GetLastError` at `0x18031fc64`
- `KERNEL32!GetLastError` at `0x18032000a`
- `KERNEL32!GetLastError` at `0x180320161`
- `KERNEL32!GetLastError` at `0x18032025c`
- `KERNEL32!GetLastError` at `0x18032030e`
- `KERNEL32!GetLastError` at `0x1803203a2`
- `KERNEL32!GetLastError` at `0x180320439`
- `KERNEL32!GetLastError` at `0x180320498`
- `KERNEL32!GetLastError` at `0x180320540`
- `KERNEL32!GetLastError` at `0x1803205e3`
- `KERNEL32!GetLastError` at `0x180320686`
- `KERNEL32!GetLastError` at `0x180320729`
- `KERNEL32!GetLastError` at `0x18032082a`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031f89a`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031f89a`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031f80b`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031f80b`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031f832`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031f832`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031fec0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031ff24`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031fec0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031ff24`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18031f74b`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18031f7ad`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18031f74b`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18031f7ad`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f726`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f73e`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f788`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f7a0`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f726`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f73e`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f788`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18031f7a0`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031fc4a`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031fdce`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031fc4a`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031fdce`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031f860`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031f860`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031f8c6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031f8c6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f12b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f13a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f180`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f18f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f1ce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f1dd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f207`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f24a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f259`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f283`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f2ad`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f2d7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f301`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f344`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f353`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f37d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f3c0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f3cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f412`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f421`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f44b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f48e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f49d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f4e0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f4ef`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f519`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f543`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f586`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f595`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f5bf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f5e9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f613`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f656`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f665`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6a8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6b7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6f6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f705`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f87d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f8fa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18032053a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803205dd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180320680`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180320723`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803207c6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f12b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f13a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f180`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f18f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f1ce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f1dd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f207`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f24a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f259`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f283`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f2ad`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f2d7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f301`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f344`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f353`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f37d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f3c0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f3cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f412`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f421`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f44b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f48e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f49d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f4e0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f4ef`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f519`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f543`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f586`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f595`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f5bf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f5e9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f613`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f656`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f665`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6a8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6b7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f6f6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f705`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f87d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031f8fa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18032053a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803205dd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180320680`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180320723`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803207c6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f0fd`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f112`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f152`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f167`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f1a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f1b5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f1ef`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f21c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f231`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f26b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f295`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f2bf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f2e9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f316`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f32b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f365`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f392`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f3a7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f3e4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f3f9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f433`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f460`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f475`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f4b2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f4c7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f501`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f52b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f558`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f56d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f5a7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f5d1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f5fb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f628`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f63d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f67a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f68f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f6c8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f6dd`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f856`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031f8de`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1803204bf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180320567`

## string_xrefs

- `0x18031f847`: `SetupPlatform.dll`
- `0x1803205fb`: `registry`
- `0x180320627`: `   Registry: %d`
- `0x18031f39b`: `MIG_CONTENT_COMPARE_ACLS`
- `0x18031f2dd`: `MIG_REPL_MANIFESTS_DIR`
- `0x18031f289`: `MIG_MANIFESTS`
- `0x18031f2b3`: `MIG_MANIFESTS_DIR`
- `0x18031f549`: `mxeagent.dll`
- `0x18031f561`: `MIG_AGENT_DLL_FILTER`
- `0x18031f4bb`: `MIG_FILE_COMPARE`
- `0x18031f5ef`: `MIG_UPGRADE_AGENT_NO_DISCOVER`
- `0x18031f5c5`: `MIG_UPGRADE_CONFIG_SCRIPT`
- `0x180320275`: `Estimation completed. Number of events: %d`
- `0x18031f3d5`: `COPYRAW`
- `0x18032032b`: `%hs: Cannot create the UNC store. Error: 0x%08X`
- `0x18031fc8c`: `Setup will %scompress the upgrade store`
- `0x18031f307`: `offline.xml`

## pseudocode

```c

```

## disassembly

```asm
0x18031eff0  mov     rax, rsp
0x18031eff3  mov     [rax+20h], r9
0x18031eff7  mov     [rax+18h], r8
0x18031effb  mov     [rax+8], rcx
0x18031efff  push    rbx
0x18031f000  push    rsi
0x18031f001  push    rdi
0x18031f002  push    r12
0x18031f004  push    r13
0x18031f006  push    r14
0x18031f008  push    r15
0x18031f00a  sub     rsp, 2E0h
0x18031f011  mov     qword ptr [rax-148h], 0FFFFFFFFFFFFFFFEh
0x18031f01c  mov     r15, r9
0x18031f01f  mov     rbx, r8
0x18031f022  mov     r12, rcx
0x18031f025  xor     esi, esi
0x18031f027  mov     [rax+10h], sil
0x18031f02b  cmp     edx, 5
0x18031f02e  jz      short loc_18031F037
0x18031f030  xor     eax, eax
0x18031f032  jmp     loc_18031FE8A
0x18031f037  mov     [rsp+318h+var_2B4], esi
0x18031f03b  mov     r14d, 1
0x18031f041  test    cs:Microsoft_Windows_SetupPlatformEnableBits, r14b
0x18031f048  jz      loc_18031F0DC
0x18031f04e  xorps   xmm0, xmm0
0x18031f051  movups  xmmword ptr [rsp+318h+EventTrace.Size], xmm0
0x18031f059  movups  xmmword ptr [rsp+318h+EventTrace.TimeStamp], xmm0
0x18031f061  movups  xmmword ptr [rsp+318h+EventTrace.18h+8], xmm0
0x18031f069  cmp     cs:McGenPreVista, sil
0x18031f070  jnz     short loc_18031F094
0x18031f072  xor     r9d, r9d
0x18031f075  xor     r8d, r8d
0x18031f078  lea     rdx, OfflineGatherRunStart
0x18031f07f  mov     rcx, cs:Microsoft_Windows_SetupPlatform_Context
0x18031f086  mov     rax, cs:PfnEventWrite
0x18031f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031f092  jmp     short loc_18031F0DC
0x18031f094  lea     rax, OfflineGatherRunId
0x18031f09b  mov     qword ptr [rsp+318h+EventTrace.18h], rax
0x18031f0a3  mov     dword ptr [rsp+318h+EventTrace.28h+4], 1A0000h
0x18031f0ae  mov     dword ptr [rsp+318h+EventTrace.4], 401h
0x18031f0b9  mov     eax, 30h ; '0'
0x18031f0be  mov     [rsp+318h+EventTrace.Size], ax
0x18031f0c6  lea     rdx, [rsp+318h+EventTrace]; EventTrace
0x18031f0ce  mov     rcx, cs:TraceHandle; TraceHandle
0x18031f0d5  call    cs:__imp_TraceEvent
0x18031f0db  nop
0x18031f0dc  test    rbx, rbx
0x18031f0df  jz      loc_18031FE9D
0x18031f0e5  test    r15, r15
0x18031f0e8  jz      loc_18031FF00
0x18031f0ee  lea     rdx, aOfflineGather; "Offline gather"
0x18031f0f5  lea     rcx, [rsp+318h+var_280]
0x18031f0fd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f103  mov     rdi, rax
0x18031f106  lea     rdx, aMigDiagSession; "MIG_DIAG_SESSION_NAME"
0x18031f10d  lea     rcx, [rsp+318h+var_2B0]
0x18031f112  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f118  nop
0x18031f119  mov     rdx, rdi
0x18031f11c  mov     rcx, rax
0x18031f11f  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f125  nop
0x18031f126  lea     rcx, [rsp+318h+var_2B0]
0x18031f12b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f131  nop
0x18031f132  lea     rcx, [rsp+318h+var_280]
0x18031f13a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f140  lea     r13, Value; "1"
0x18031f147  mov     rdx, r13
0x18031f14a  lea     rcx, [rsp+318h+var_280]
0x18031f152  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f158  mov     rdi, rax
0x18031f15b  lea     rdx, aMigUpgrade; "MIG_UPGRADE"
0x18031f162  lea     rcx, [rsp+318h+var_2B0]
0x18031f167  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f16d  nop
0x18031f16e  mov     rdx, rdi
0x18031f171  mov     rcx, rax
0x18031f174  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f17a  nop
0x18031f17b  lea     rcx, [rsp+318h+var_2B0]
0x18031f180  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f186  nop
0x18031f187  lea     rcx, [rsp+318h+var_280]
0x18031f18f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f195  mov     rdx, r13
0x18031f198  lea     rcx, [rsp+318h+var_280]
0x18031f1a0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f1a6  mov     rdi, rax
0x18031f1a9  lea     rdx, aMigOsdbCheckWi; "MIG_OSDB_CHECK_WINSXS"
0x18031f1b0  lea     rcx, [rsp+318h+var_2B0]
0x18031f1b5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f1bb  nop
0x18031f1bc  mov     rdx, rdi
0x18031f1bf  mov     rcx, rax
0x18031f1c2  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f1c8  nop
0x18031f1c9  lea     rcx, [rsp+318h+var_2B0]
0x18031f1ce  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f1d4  nop
0x18031f1d5  lea     rcx, [rsp+318h+var_280]
0x18031f1dd  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f1e3  lea     rdx, aMigUpgradeOpti; "MIG_UPGRADE_OPTIMIZE_GAC_MIGRATION"
0x18031f1ea  lea     rcx, [rsp+318h+var_2B0]
0x18031f1ef  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f1f5  nop
0x18031f1f6  xor     edx, edx
0x18031f1f8  mov     rcx, rax
0x18031f1fb  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f201  nop
0x18031f202  lea     rcx, [rsp+318h+var_2B0]
0x18031f207  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f20d  lea     rdx, aNo; "No"
0x18031f214  lea     rcx, [rsp+318h+var_280]
0x18031f21c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f222  mov     rdi, rax
0x18031f225  lea     rdx, aMigUseProcessE; "MIG_USE_PROCESS_ENV"
0x18031f22c  lea     rcx, [rsp+318h+var_2B0]
0x18031f231  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f237  nop
0x18031f238  mov     rdx, rdi
0x18031f23b  mov     rcx, rax
0x18031f23e  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f244  nop
0x18031f245  lea     rcx, [rsp+318h+var_2B0]
0x18031f24a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f250  nop
0x18031f251  lea     rcx, [rsp+318h+var_280]
0x18031f259  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f25f  lea     rdx, aMigDisableCont; "MIG_DISABLE_CONTENT_REMAP"
0x18031f266  lea     rcx, [rsp+318h+var_2B0]
0x18031f26b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f271  nop
0x18031f272  xor     edx, edx
0x18031f274  mov     rcx, rax
0x18031f277  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f27d  nop
0x18031f27e  lea     rcx, [rsp+318h+var_2B0]
0x18031f283  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f289  lea     rdx, aMigManifests; "MIG_MANIFESTS"
0x18031f290  lea     rcx, [rsp+318h+var_2B0]
0x18031f295  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f29b  nop
0x18031f29c  xor     edx, edx
0x18031f29e  mov     rcx, rax
0x18031f2a1  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f2a7  nop
0x18031f2a8  lea     rcx, [rsp+318h+var_2B0]
0x18031f2ad  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f2b3  lea     rdx, aMigManifestsDi; "MIG_MANIFESTS_DIR"
0x18031f2ba  lea     rcx, [rsp+318h+var_2B0]
0x18031f2bf  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f2c5  nop
0x18031f2c6  xor     edx, edx
0x18031f2c8  mov     rcx, rax
0x18031f2cb  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f2d1  nop
0x18031f2d2  lea     rcx, [rsp+318h+var_2B0]
0x18031f2d7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f2dd  lea     rdx, aMigReplManifes; "MIG_REPL_MANIFESTS_DIR"
0x18031f2e4  lea     rcx, [rsp+318h+var_2B0]
0x18031f2e9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f2ef  nop
0x18031f2f0  xor     edx, edx
0x18031f2f2  mov     rcx, rax
0x18031f2f5  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f2fb  nop
0x18031f2fc  lea     rcx, [rsp+318h+var_2B0]
0x18031f301  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f307  lea     rdx, aOfflineXml; "offline.xml"
0x18031f30e  lea     rcx, [rsp+318h+var_280]
0x18031f316  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f31c  mov     rdi, rax
0x18031f31f  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x18031f326  lea     rcx, [rsp+318h+var_2B0]
0x18031f32b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f331  nop
0x18031f332  mov     rdx, rdi
0x18031f335  mov     rcx, rax
0x18031f338  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f33e  nop
0x18031f33f  lea     rcx, [rsp+318h+var_2B0]
0x18031f344  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f34a  nop
0x18031f34b  lea     rcx, [rsp+318h+var_280]
0x18031f353  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f359  lea     rdx, aMigrationScrip; "MIGRATION_SCRIPT_DIR"
0x18031f360  lea     rcx, [rsp+318h+var_2B0]
0x18031f365  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f36b  nop
0x18031f36c  xor     edx, edx
0x18031f36e  mov     rcx, rax
0x18031f371  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f377  nop
0x18031f378  lea     rcx, [rsp+318h+var_2B0]
0x18031f37d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f383  lea     rdx, a0; "0"
0x18031f38a  lea     rcx, [rsp+318h+var_280]
0x18031f392  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f398  mov     rdi, rax
0x18031f39b  lea     rdx, aMigContentComp; "MIG_CONTENT_COMPARE_ACLS"
0x18031f3a2  lea     rcx, [rsp+318h+var_2B0]
0x18031f3a7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f3ad  nop
0x18031f3ae  mov     rdx, rdi
0x18031f3b1  mov     rcx, rax
0x18031f3b4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f3ba  nop
0x18031f3bb  lea     rcx, [rsp+318h+var_2B0]
0x18031f3c0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f3c6  nop
0x18031f3c7  lea     rcx, [rsp+318h+var_280]
0x18031f3cf  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f3d5  lea     rdx, aCopyraw; "COPYRAW"
0x18031f3dc  lea     rcx, [rsp+318h+var_280]
0x18031f3e4  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f3ea  mov     rdi, rax
0x18031f3ed  lea     rdx, aMigEfsMode; "MIG_EFS_MODE"
0x18031f3f4  lea     rcx, [rsp+318h+var_2B0]
0x18031f3f9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f3ff  nop
0x18031f400  mov     rdx, rdi
0x18031f403  mov     rcx, rax
0x18031f406  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f40c  nop
0x18031f40d  lea     rcx, [rsp+318h+var_2B0]
0x18031f412  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f418  nop
0x18031f419  lea     rcx, [rsp+318h+var_280]
0x18031f421  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f427  lea     rdx, aMigIgnoreProfi; "MIG_IGNORE_PROFILE_MISSING"
0x18031f42e  lea     rcx, [rsp+318h+var_2B0]
0x18031f433  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f439  nop
0x18031f43a  xor     edx, edx
0x18031f43c  mov     rcx, rax
0x18031f43f  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f445  nop
0x18031f446  lea     rcx, [rsp+318h+var_2B0]
0x18031f44b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f451  lea     rdx, a0; "0"
0x18031f458  lea     rcx, [rsp+318h+var_280]
0x18031f460  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f466  mov     rdi, rax
0x18031f469  lea     rdx, aMigFailOnProfi; "MIG_FAIL_ON_PROFILE_ERROR"
0x18031f470  lea     rcx, [rsp+318h+var_2B0]
0x18031f475  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f47b  nop
0x18031f47c  mov     rdx, rdi
0x18031f47f  mov     rcx, rax
0x18031f482  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f488  nop
0x18031f489  lea     rcx, [rsp+318h+var_2B0]
0x18031f48e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f494  nop
0x18031f495  lea     rcx, [rsp+318h+var_280]
0x18031f49d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f4a3  lea     rdx, aTime; "TIME"
0x18031f4aa  lea     rcx, [rsp+318h+var_280]
0x18031f4b2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f4b8  mov     rdi, rax
0x18031f4bb  lea     rdx, aMigFileCompare; "MIG_FILE_COMPARE"
0x18031f4c2  lea     rcx, [rsp+318h+var_2B0]
0x18031f4c7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f4cd  nop
0x18031f4ce  mov     rdx, rdi
0x18031f4d1  mov     rcx, rax
0x18031f4d4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f4da  nop
0x18031f4db  lea     rcx, [rsp+318h+var_2B0]
0x18031f4e0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f4e6  nop
0x18031f4e7  lea     rcx, [rsp+318h+var_280]
0x18031f4ef  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f4f5  lea     rdx, aMigCmiMachineS; "MIG_CMI_MACHINE_SPECIFIC"
0x18031f4fc  lea     rcx, [rsp+318h+var_2B0]
0x18031f501  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f507  nop
0x18031f508  xor     edx, edx
0x18031f50a  mov     rcx, rax
0x18031f50d  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f513  nop
0x18031f514  lea     rcx, [rsp+318h+var_2B0]
0x18031f519  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f51f  lea     rdx, aMigCmiInnerSec; "MIG_CMI_INNER_SECTION"
0x18031f526  lea     rcx, [rsp+318h+var_2B0]
0x18031f52b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031f531  nop
0x18031f532  xor     edx, edx
0x18031f534  mov     rcx, rax
0x18031f537  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031f53d  nop
0x18031f53e  lea     rcx, [rsp+318h+var_2B0]
0x18031f543  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031f549  lea     rdx, aMxeagentDll; "mxeagent.dll"
0x18031f550  lea     rcx, [rsp+318h+var_280]
0x18031f558  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
  ... truncated ...
```
