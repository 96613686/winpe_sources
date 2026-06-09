# OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(ushort const *,OSRollbackService::ICheckpointParameters *)

- ea: `0x18047ede0`
- end: `0x180480702`
- name: `?Finalize@CBootFilesRestoreCheckpoint@OSRollbackService@@UEAAXPEBGPEAUICheckpointParameters@2@@Z`
- size: `6434`
- prototype: `void __fastcall(OSRollbackService::CBootFilesRestoreCheckpoint *this, OSRollbackUtils::VolumeTracking *, struct OSRollbackService::ICheckpointParameters *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x18029fc74`
- `0x180403e1c`
- `0x180405298`
- `0x18040c590`
- `0x18040d0e0`
- `0x18040d148`
- `0x180479c3c`
- `0x18047df74`
- `0x18047ede0`
- `0x18048084c`
- `0x1804809e8`
- `0x180481628`
- `0x18048c4c0`
- `0x1804bbf46`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18047f575`
- `ntdll!RtlInitUnicodeString` at `0x18047f575`
- `ntdll!RtlFreeUnicodeString` at `0x18047f55c`
- `ntdll!RtlFreeUnicodeString` at `0x18047f55c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18047f51c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18047f51c`
- `KERNEL32!GetProcessHeap` at `0x18047eeb1`
- `KERNEL32!GetProcessHeap` at `0x18047ef24`
- `KERNEL32!GetProcessHeap` at `0x18047efce`
- `KERNEL32!GetProcessHeap` at `0x18047f89e`
- `KERNEL32!GetProcessHeap` at `0x180480484`
- `KERNEL32!GetProcessHeap` at `0x18047eeb1`
- `KERNEL32!GetProcessHeap` at `0x18047ef24`
- `KERNEL32!GetProcessHeap` at `0x18047efce`
- `KERNEL32!GetProcessHeap` at `0x18047f89e`
- `KERNEL32!GetProcessHeap` at `0x180480484`
- `KERNEL32!HeapAlloc` at `0x18047eec2`
- `KERNEL32!HeapAlloc` at `0x18047eec2`
- `KERNEL32!HeapFree` at `0x18047ef32`
- `KERNEL32!HeapFree` at `0x18047efe1`
- `KERNEL32!HeapFree` at `0x18047f8ac`
- `KERNEL32!HeapFree` at `0x180480492`
- `KERNEL32!HeapFree` at `0x18047ef32`
- `KERNEL32!HeapFree` at `0x18047efe1`
- `KERNEL32!HeapFree` at `0x18047f8ac`
- `KERNEL32!HeapFree` at `0x180480492`
- `KERNEL32!GetLastError` at `0x18047ef3d`
- `KERNEL32!GetLastError` at `0x18047ef53`
- `KERNEL32!GetLastError` at `0x18047f01e`
- `KERNEL32!GetLastError` at `0x18047f121`
- `KERNEL32!GetLastError` at `0x18047f216`
- `KERNEL32!GetLastError` at `0x18047f2aa`
- `KERNEL32!GetLastError` at `0x18047f449`
- `KERNEL32!GetLastError` at `0x18047f5b4`
- `KERNEL32!GetLastError` at `0x18047f659`
- `KERNEL32!GetLastError` at `0x18047f6b5`
- `KERNEL32!GetLastError` at `0x18047f739`
- `KERNEL32!GetLastError` at `0x18047f79f`
- `KERNEL32!GetLastError` at `0x18047f825`
- `KERNEL32!GetLastError` at `0x18047fa30`
- `KERNEL32!GetLastError` at `0x18047fae8`
- `KERNEL32!GetLastError` at `0x18047fbaa`
- `KERNEL32!GetLastError` at `0x18047fc59`
- `KERNEL32!GetLastError` at `0x18047fccc`
- `KERNEL32!GetLastError` at `0x18047fd61`
- `KERNEL32!GetLastError` at `0x18047fdb5`
- `KERNEL32!GetLastError` at `0x18047fdc6`
- `KERNEL32!GetLastError` at `0x18047fe14`
- `KERNEL32!GetLastError` at `0x18047fe26`
- `KERNEL32!GetLastError` at `0x18047ff75`
- `KERNEL32!GetLastError` at `0x18047ff86`
- `KERNEL32!GetLastError` at `0x18047fff7`
- `KERNEL32!GetLastError` at `0x180480080`
- `KERNEL32!GetLastError` at `0x18048010d`
- `KERNEL32!GetLastError` at `0x1804801de`
- `KERNEL32!GetLastError` at `0x1804802e6`
- `KERNEL32!GetLastError` at `0x1804803d8`
- `KERNEL32!GetLastError` at `0x180480523`
- `KERNEL32!GetLastError` at `0x180480602`
- `KERNEL32!GetLastError` at `0x18047ef3d`
- `KERNEL32!GetLastError` at `0x18047ef53`
- `KERNEL32!GetLastError` at `0x18047f01e`
- `KERNEL32!GetLastError` at `0x18047f121`
- `KERNEL32!GetLastError` at `0x18047f216`
- `KERNEL32!GetLastError` at `0x18047f2aa`
- `KERNEL32!GetLastError` at `0x18047f449`
- `KERNEL32!GetLastError` at `0x18047f5b4`
- `KERNEL32!GetLastError` at `0x18047f659`
- `KERNEL32!GetLastError` at `0x18047f6b5`
- `KERNEL32!GetLastError` at `0x18047f739`
- `KERNEL32!GetLastError` at `0x18047f79f`
- `KERNEL32!GetLastError` at `0x18047f825`
- `KERNEL32!GetLastError` at `0x18047fa30`
- `KERNEL32!GetLastError` at `0x18047fae8`
- `KERNEL32!GetLastError` at `0x18047fbaa`
- `KERNEL32!GetLastError` at `0x18047fc59`
- `KERNEL32!GetLastError` at `0x18047fccc`
- `KERNEL32!GetLastError` at `0x18047fd61`
- `KERNEL32!GetLastError` at `0x18047fdb5`
- `KERNEL32!GetLastError` at `0x18047fdc6`
- `KERNEL32!GetLastError` at `0x18047fe14`
- `KERNEL32!GetLastError` at `0x18047fe26`
- `KERNEL32!GetLastError` at `0x18047ff75`
- `KERNEL32!GetLastError` at `0x18047ff86`
- `KERNEL32!GetLastError` at `0x18047fff7`
- `KERNEL32!GetLastError` at `0x180480080`
- `KERNEL32!GetLastError` at `0x18048010d`
- `KERNEL32!GetLastError` at `0x1804801de`
- `KERNEL32!GetLastError` at `0x1804802e6`
- `KERNEL32!GetLastError` at `0x1804803d8`
- `KERNEL32!GetLastError` at `0x180480523`
- `KERNEL32!GetLastError` at `0x180480602`
- `KERNEL32!SetLastError` at `0x18048051d`
- `KERNEL32!SetLastError` at `0x1804805fc`
- `KERNEL32!SetLastError` at `0x18048051d`
- `KERNEL32!SetLastError` at `0x1804805fc`
- `KERNEL32!CloseHandle` at `0x18047fff1`
- `KERNEL32!CloseHandle` at `0x18047fff1`
- `KERNEL32!Sleep` at `0x18047faa1`
- `KERNEL32!Sleep` at `0x18047faa1`
- `KERNEL32!CreateFileW` at `0x18047ff69`
- `KERNEL32!CreateFileW` at `0x18047ff69`
- `KERNEL32!CopyFileExW` at `0x18047f208`
- `KERNEL32!CopyFileExW` at `0x18047fb9c`
- `KERNEL32!CopyFileExW` at `0x18047f208`
- `KERNEL32!CopyFileExW` at `0x18047fb9c`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f113`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f9e5`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f113`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f9e5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f0cd`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f0f0`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f3ae`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f431`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f914`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f989`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f9c2`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047ff16`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18048028c`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1804802ce`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f0cd`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f0f0`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f3ae`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f431`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f914`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f989`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047f9c2`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047ff16`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18048028c`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1804802ce`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1804804d8`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1804804d8`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f3d7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f8d7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1804802af`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f3d7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047f8d7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1804802af`
- `unbcl!?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z` at `0x18047f95f`
- `unbcl!?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z` at `0x1804803b7`
- `unbcl!?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z` at `0x18047f95f`
- `unbcl!?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z` at `0x1804803b7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f10a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f3ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f8ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f8ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f934`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f945`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f9dc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804802a6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180480396`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804803a4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f10a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f3ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f8ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f8ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f934`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f945`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047f9dc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804802a6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180480396`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804803a4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804804b8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804805a5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804806ae`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804804b8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804805a5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1804806ae`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f137`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f1cc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f1e3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f22c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f243`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f2c0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f2d7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f411`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f462`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f4e8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f96d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f9a6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047f9f8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047faac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fb60`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fb77`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fbc0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fbd7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fd44`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fe33`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fe4a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047fef6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ff36`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ff96`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180480010`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180480096`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180480126`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1804801f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1804802ff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180480316`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1804803ee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180480618`

## string_xrefs

- `0x18047ef02`: `GetSystemPartitionNTPath: Found system partition at [%s].`
- `0x18047ef13`: `GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x`
- `0x18047eff9`: `GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x`
- `0x18047f067`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f17e`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f291`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f323`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f4a9`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f5fd`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f69f`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f700`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f789`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f7ef`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f86d`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fa72`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fb2f`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fc1f`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fc9b`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fd13`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fd9c`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fdfb`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fe9d`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047fed9`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x180480169`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x180480241`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x180480362`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x180480431`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x180480574`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18048067d`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047f039`: `%hs: System volume drive path is [%s]`
- `0x18047f261`: `%hs: Failed to copy "%s" to "%s", what to do?, skip.`
- `0x18047f671`: `%hs:Promoted the newly created store file to the system BCD Store`
- `0x18047f5cf`: `%hs:Created Store %s`
- `0x18047f47b`: `%hs: Running in EFI mode, "%s" does not exist. Will create a temporary system BCD store to bind and save firmware settings.`
- `0x18047f032`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f149`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f25a`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f2ee`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f474`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f5c8`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f66a`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f6c9`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f752`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f7b8`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f836`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fa14`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fe65`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fed2`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480106`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480209`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18048032d`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18048053d`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480646`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f05b`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f172`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f285`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f317`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f49d`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f5f1`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f693`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f6f4`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f77d`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f7e3`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047f861`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fa66`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fadc`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fb23`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fc13`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fc8f`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fd07`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047fe91`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18047ffd3`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x18048015d`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480235`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480356`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480425`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480568`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x180480671`: `OSRollbackService::CBootFilesRestoreCheckpoint::Finalize`
- `0x1804804ed`: `void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRollbackService::ICheckpointParameters *)`
- `0x1804805cd`: `void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRollbackService::ICheckpointParameters *)`
- `0x1804806d6`: `void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRollbackService::ICheckpointParameters *)`
- `0x18047fe6c`: `%hs: Failed to copy "%s" to "%s" GLE = [%d].`
- `0x180480025`: `%hs: Successfully created tag file [%s] to mark the system BCD store as temporary.`
- `0x18047ffaf`: `%hs: Error creating tag file [%s] to mark the system BCD store as temporary, GLE=0x%x`
- `0x18047ff08`: `$NeedDeleteBCD.tag`
- `0x18047f83d`: `%hs: Failed to convert dos path to NT path for system BCD store and firmware setting won't be saved for rollback.`
- `0x18047f7bf`: `%hs: Failed to create directory %s , ec = [%x]`
- `0x18047f759`: `%hs:BcdCreateStore() for %s failed, ec = [%x]`
- `0x18047fd75`: `%hs: Successfully deleted old BCD store`
- `0x180480334`: `%hs: Copy directory [%s] to [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(
        OSRollbackService::CBootFilesRestoreCheckpoint *this,
        OSRollbackUtils::VolumeTracking *a2,
        struct OSRollbackService::ICheckpointParameters *a3)
{
  OSRollbackUtils::VolumeTracking *v3; // r13
  RollbackException *v4; // r15
  OSRollbackService::CSetupBasicCheckpointParameters *v5; // rax
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  unsigned int v8; // r9d
  int SystemPartitionPath; // eax
  unsigned __int16 *v10; // rsi
  unsigned int SystemPartition; // eax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  LPVOID v14; // rax
  void *v15; // rdi
  int v16; // eax
  signed int v17; // ebx
  unsigned int v18; // edx
  HANDLE v19; // rax
  signed int LastError; // eax
  bool v21; // sf
  signed int v22; // eax
  int v23; // ebx
  HANDLE v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  const unsigned __int16 *v28; // rdx
  unsigned __int16 v29; // r9
  int v30; // eax
  unsigned int v31; // r14d
  unsigned int i; // r14d
  struct UnBCL::String *v33; // rax
  struct UnBCL::String *v34; // rax
  const struct UnBCL::String *P; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  UnBCL::String *v38; // rax
  const char *v39; // rax
  struct tagLOG_PARTIAL_MSG *v40; // rax
  UnBCL::String *v41; // rax
  const WCHAR *CString; // rbx
  UnBCL::String *v43; // rax
  const WCHAR *v44; // rax
  DWORD v45; // esi
  __int64 v46; // rdi
  UnBCL::String *v47; // rax
  const char *v48; // rbx
  UnBCL::String *v49; // rax
  const char *v50; // rax
  struct tagLOG_PARTIAL_MSG *v51; // rax
  DWORD v52; // esi
  __int64 v53; // rdi
  UnBCL::String *v54; // rax
  const char *v55; // rbx
  UnBCL::String *v56; // rax
  const char *v57; // rax
  int BootFirmwareType; // edi
  const wchar_t *v59; // rbx
  struct UnBCL::String *v60; // rax
  const struct UnBCL::String *v61; // rax
  WCHAR *v62; // r14
  UnBCL::String *v63; // rax
  const unsigned __int16 *v64; // rax
  struct UnBCL::String *v65; // rax
  DWORD v66; // edi
  __int64 v67; // rbx
  UnBCL::String *v68; // rax
  const char *v69; // rax
  struct tagLOG_PARTIAL_MSG *v70; // rax
  UnBCL::String *v71; // rax
  const unsigned __int16 *v72; // rax
  int v73; // eax
  int v74; // ebx
  int v75; // r13d
  int v76; // r13d
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  int v80; // r13d
  DWORD v81; // edi
  __int64 v82; // rbx
  struct tagLOG_PARTIAL_MSG *v83; // rax
  DWORD v84; // edi
  __int64 v85; // rbx
  DWORD v86; // edi
  __int64 v87; // rbx
  struct tagLOG_PARTIAL_MSG *v88; // rax
  DWORD v89; // edi
  __int64 v90; // rbx
  struct tagLOG_PARTIAL_MSG *v91; // rax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  HANDLE v95; // rax
  const struct UnBCL::String *v96; // rax
  struct UnBCL::String *v97; // rax
  struct UnBCL::String *v98; // rax
  const struct UnBCL::String *v99; // rbx
  const struct UnBCL::String *v100; // rax
  UnBCL::String *v101; // rax
  const unsigned __int16 *v102; // rax
  struct UnBCL::String *v103; // rax
  UnBCL::String *v104; // rax
  const unsigned __int16 *v105; // rax
  struct UnBCL::String *v106; // rax
  const struct UnBCL::String *v107; // rax
  UnBCL::String *v108; // rax
  OSRollbackUtils *v109; // rax
  const unsigned __int16 *v110; // rdx
  unsigned int v111; // eax
  int j; // esi
  DWORD v113; // r13d
  DWORD v114; // edi
  __int64 v115; // rbx
  struct tagLOG_PARTIAL_MSG *v116; // rax
  UnBCL::String *v117; // rax
  OSRollbackUtils *v118; // rax
  const unsigned __int16 *v119; // rdx
  DWORD v120; // edi
  __int64 v121; // rbx
  struct tagLOG_PARTIAL_MSG *v122; // rax
  UnBCL::String *v123; // rax
  const WCHAR *v124; // rbx
  UnBCL::String *v125; // rax
  const WCHAR *v126; // rax
  DWORD v127; // esi
  __int64 v128; // rdi
  UnBCL::String *v129; // rax
  const char *v130; // rbx
  UnBCL::String *v131; // rax
  const char *v132; // rax
  struct tagLOG_PARTIAL_MSG *v133; // rax
  int v134; // esi
  DWORD v135; // edi
  __int64 v136; // rbx
  struct tagLOG_PARTIAL_MSG *v137; // rax
  DWORD v138; // edi
  __int64 v139; // rbx
  struct tagLOG_PARTIAL_MSG *v140; // rax
  UnBCL::String *v141; // rax
  const unsigned __int16 *v142; // rax
  DWORD v143; // edi
  __int64 v144; // rbx
  DWORD v145; // edi
  __int64 v146; // rbx
  DWORD v147; // eax
  struct tagLOG_PARTIAL_MSG *v148; // rax
  DWORD v149; // r14d
  __int64 v150; // rsi
  DWORD v151; // edi
  UnBCL::String *v152; // rax
  const char *v153; // rbx
  UnBCL::String *v154; // rax
  const char *v155; // rax
  struct tagLOG_PARTIAL_MSG *v156; // rax
  UnBCL::String *v157; // rax
  const unsigned __int16 *v158; // rax
  struct UnBCL::String *v159; // rax
  UnBCL::String *v160; // rax
  const WCHAR *v161; // rax
  HANDLE FileW; // rax
  DWORD v163; // esi
  __int64 v164; // rdi
  DWORD v165; // ebx
  UnBCL::String *v166; // rax
  const char *v167; // rax
  struct tagLOG_PARTIAL_MSG *v168; // rax
  DWORD v169; // edi
  __int64 v170; // rbx
  UnBCL::String *v171; // rax
  const char *v172; // rax
  DWORD v173; // edi
  __int64 v174; // rbx
  UnBCL::String *v175; // rax
  const char *v176; // rax
  struct tagLOG_PARTIAL_MSG *v177; // rax
  DWORD v178; // edi
  __int64 v179; // rbx
  UnBCL::String *v180; // rax
  const char *v181; // rax
  struct tagLOG_PARTIAL_MSG *v182; // rax
  DWORD v183; // edi
  __int64 v184; // rbx
  UnBCL::String *v185; // rax
  const char *v186; // rax
  struct tagLOG_PARTIAL_MSG *v187; // rax
  struct UnBCL::String *v188; // rax
  const struct UnBCL::String *v189; // rax
  struct UnBCL::String *v190; // rax
  DWORD v191; // edi
  __int64 v192; // r14
  UnBCL::String *v193; // rax
  const char *v194; // rbx
  UnBCL::String *v195; // rax
  const char *v196; // rax
  struct tagLOG_PARTIAL_MSG *v197; // rax
  const struct UnBCL::String *v198; // rbx
  const struct UnBCL::String *v199; // rax
  DWORD v200; // edi
  __int64 v201; // rbx
  UnBCL::String *v202; // rax
  const char *v203; // rax
  struct tagLOG_PARTIAL_MSG *v204; // rax
  HANDLE ProcessHeap; // rax
  UnBCL::ArgumentNullException *v206; // rax
  UnBCL::ArgumentNullException *v207; // rbx
  DWORD v208; // edi
  __int64 v209; // rbx
  struct tagLOG_PARTIAL_MSG *v210; // rax
  RollbackException *v211; // rax
  DWORD v212; // esi
  __int64 v213; // rdi
  UnBCL::String *v214; // rax
  const char *v215; // rbx
  UnBCL::String *v216; // rax
  const char *v217; // rax
  struct tagLOG_PARTIAL_MSG *v218; // rax
  RollbackException *v219; // rax
  UnBCL::String *v220; // rax
  const char *v221; // rbx
  UnBCL::String *v222; // rax
  const char *v223; // rax
  struct UnBCL::Exception *v224; // rsi
  DWORD v225; // edi
  __int64 v226; // rbx
  UnBCL::String *v227; // rax
  const char *v228; // rax
  struct tagLOG_PARTIAL_MSG *v229; // rax
  int pbCancel; // [rsp+20h] [rbp-138h]
  int pbCancela; // [rsp+20h] [rbp-138h]
  int pbCancelb; // [rsp+20h] [rbp-138h]
  int pbCancelc; // [rsp+20h] [rbp-138h]
  __int64 v234; // [rsp+38h] [rbp-120h]
  __int64 v235; // [rsp+38h] [rbp-120h]
  __int64 v236; // [rsp+38h] [rbp-120h]
  __int64 v237; // [rsp+38h] [rbp-120h]
  DWORD v238; // [rsp+40h] [rbp-118h]
  DWORD v239; // [rsp+40h] [rbp-118h]
  DWORD v240; // [rsp+40h] [rbp-118h]
  DWORD v241; // [rsp+40h] [rbp-118h]
  _QWORD v242[2]; // [rsp+60h] [rbp-F8h] BYREF
  unsigned __int16 *v243; // [rsp+70h] [rbp-E8h] BYREF
  _QWORD v244[2]; // [rsp+78h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-D0h] BYREF
  __int64 v246; // [rsp+90h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-C0h] BYREF
  _QWORD v248[2]; // [rsp+A8h] [rbp-B0h] BYREF
  int v249; // [rsp+B8h] [rbp-A0h]
  unsigned int v250; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v251; // [rsp+C8h] [rbp-90h] BYREF
  _BYTE v252[8]; // [rsp+D0h] [rbp-88h] BYREF
  UnBCL::Exception *v253[3]; // [rsp+D8h] [rbp-80h] BYREF
  __int64 pExceptionObject; // [rsp+F0h] [rbp-68h] BYREF
  __int64 v255; // [rsp+F8h] [rbp-60h] BYREF
  __int64 v256; // [rsp+100h] [rbp-58h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+108h] [rbp-50h] BYREF
  __int64 v258; // [rsp+118h] [rbp-40h]
  struct UnBCL::Exception *v259; // [rsp+120h] [rbp-38h] BYREF
  unsigned int v261; // [rsp+178h] [rbp+20h] BYREF

  v258 = -2;
  v3 = a2;
  v243 = L"C:";
  v4 = 0;
  if ( !a2 )
  {
    v206 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v207 = v206;
    if ( v206 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v206, L"pWorkingDir");
      *(_QWORD *)v207 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v207 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v207,
                         "void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,st"
                         "ruct OSRollbackService::ICheckpointParameters *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v5 = (OSRollbackService::CSetupBasicCheckpointParameters *)_RTDynamicCast_0(
                                                               a3,
                                                               0,
                                                               &OSRollbackService::ICheckpointParameters `RTTI Type Descriptor',
                                                               &OSRollbackService::CSetupBasicCheckpointParameters `RTTI Type Descriptor',
                                                               0);
  if ( !v5 || OSRollbackService::CSetupBasicCheckpointParameters::GetBlackboardDword(v5, v6, v7, v8) != 1 )
  {
    SystemPartitionPath = GetSystemPartitionPath(&v243);
    v10 = v243;
    if ( SystemPartitionPath < 0 && v243 )
    {
LABEL_94:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
      return;
    }
    v261 = 0;
    SystemPartition = SyspartGetSystemPartition(0, 0, &v261);
    if ( SystemPartition == -1073741789 && v261 )
    {
      v12 = 2LL * v261;
      v13 = GetProcessHeap();
      v14 = HeapAlloc(v13, 8u, v12);
      v15 = v14;
      if ( v14 )
      {
        v16 = SyspartGetSystemPartition(v14, v261, &v261);
        if ( v16 < 0 )
        {
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x",
            (unsigned int)v16);
          v17 = 1;
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v15);
          v15 = 0;
        }
        else
        {
          v17 = 0;
          LibLog(&g_WdsLibLog, 0x4000000, L"GetSystemPartitionNTPath: Found system partition at [%s].", v15);
        }
      }
      else
      {
        LastError = GetLastError();
        v21 = LastError < 0;
        if ( LastError > 0 )
          v21 = 1;
        if ( v21 )
        {
          v22 = GetLastError();
          v17 = v22;
          if ( v22 > 0 )
            v17 = (unsigned __int16)v22 | 0x80070000;
        }
        else
        {
          v17 = -2147467259;
        }
      }
      if ( v17 < 0 )
        goto LABEL_92;
      if ( !v15 )
        goto LABEL_27;
      v246 = 2;
      lpMem = v15;
      v23 = PrepareVolumeAccessPath((struct _VOLUME_REFERENCE *)&lpMem, v18, &v243);
      if ( ((_DWORD)v246 == 1 || (unsigned int)(v246 - 2) <= 1) && lpMem )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, lpMem);
      }
      if ( v23 < 0 )
      {
LABEL_92:
        v10 = v243;
        goto LABEL_93;
      }
      v10 = v243;
    }
    else
    {
      LibLog(
        &g_WdsLibLog,
        0x4000000,
        L"GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x",
        SystemPartition);
    }
LABEL_27:
    if ( !v10 )
      return;
    v25 = GetLastError();
    v26 = CurrentIP();
    v27 = ConstructPartialMsgW(
            0x4000000u,
            "%hs: System volume drive path is [%s]",
            "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
            (const char *)v10);
    WdsSetupLogMessageW(
      v27,
      409600,
      L"D",
      0,
      1402,
      L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
      L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
      v26,
      v25,
      0,
      0);
    v30 = OSRollbackUtils::VolumeTracking::TrackVolume(v3, v28, (const unsigned __int16 *)*v10, v29);
    v31 = v30;
    if ( v30 < 0 )
    {
      SetLastError((unsigned __int16)v30);
      v208 = GetLastError();
      v209 = CurrentIP();
      v210 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Failed to mark system volume(%c:); hr = 0x%X",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
               *v10,
               v31);
      WdsSetupLogMessageW(
        v210,
        409600,
        L"D",
        0,
        1412,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v209,
        v208,
        0,
        0);
      v211 = (RollbackException *)UnBCL::Object::operator new(0x48u);
      if ( v211 )
        v4 = RollbackException::RollbackException(
               v211,
               v31,
               L"CBootFilesRestoreCheckpoint::Finalize: Failed to mark system volume.");
      v255 = AddStackTraceToException<UnBCL::InvalidOperationException>(
               v4,
               "void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRol"
               "lbackService::ICheckpointParameters *)");
      throw (RollbackException **)&v255;
    }
    v261 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v33 = UnBCL::String::Format(L"%c:\\%s", *v10, off_1805495F0[i]);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v242, v33);
      v34 = UnBCL::String::Format(L"%s\\%s", v3, off_1805495F0[i]);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v244, v34);
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v242);
      if ( UnBCL::File::Exists(P) )
      {
        v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
        CString = UnBCL::String::get_CString(v41);
        v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
        v44 = UnBCL::String::get_CString(v43);
        if ( CopyFileExW(v44, CString, 0, 0, 0, 0) )
        {
          v52 = GetLastError();
          v53 = CurrentIP();
          v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
          v55 = (const char *)UnBCL::String::get_CString(v54);
          v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
          v57 = (const char *)UnBCL::String::get_CString(v56);
          v51 = ConstructPartialMsgW(
                  0x4000000u,
                  "%hs: Successfully copied \"%s\" to \"%s\".",
                  "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                  v57,
                  v55);
          v238 = v52;
          v234 = v53;
          pbCancel = 1434;
        }
        else
        {
          v45 = GetLastError();
          v46 = CurrentIP();
          v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
          v48 = (const char *)UnBCL::String::get_CString(v47);
          v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
          v50 = (const char *)UnBCL::String::get_CString(v49);
          v51 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: Failed to copy \"%s\" to \"%s\", what to do?, skip.",
                  "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                  v50,
                  v48);
          v238 = v45;
          v234 = v46;
          pbCancel = 1431;
        }
        WdsSetupLogMessageW(
          v51,
          409600,
          L"D",
          0,
          pbCancel,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v234,
          v238,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v244);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v242);
        v10 = v243;
      }
      else
      {
        v36 = GetLastError();
        v37 = CurrentIP();
        v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
        v39 = (const char *)UnBCL::String::get_CString(v38);
        v40 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: %s does not exist, skip.",
                "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                v39);
        WdsSetupLogMessageW(
          v40,
          409600,
          L"D",
          0,
          1425,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v37,
          v36,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v244);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v242);
      }
    }
    BootFirmwareType = GetBootFirmwareType();
    v249 = BootFirmwareType;
    v59 = L"EFI\\Microsoft\\Boot";
    if ( BootFirmwareType != 2 )
      v59 = L"Boot";
    v242[0] = v59;
    v60 = UnBCL::String::Format(L"%c:\\%s", *v10, v59);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&lpMem, v60);
    v61 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&lpMem);
    if ( !UnBCL::Directory::Exists(v61) && BootFirmwareType == 2 )
    {
      v248[0] = 0;
      v62 = 0;
      v244[0] = 0;
      DestinationString = 0;
      v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&lpMem);
      v64 = UnBCL::String::get_CString(v63);
      v65 = UnBCL::String::Format(L"%s\\%s", v64, L"BCD");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v250, v65);
      v66 = GetLastError();
      v67 = CurrentIP();
      v68 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&lpMem);
      v69 = (const char *)UnBCL::String::get_CString(v68);
      v70 = ConstructPartialMsgW(
              0x4000000u,
              "%hs: Running in EFI mode, \"%s\" does not exist. Will create a temporary system BCD store to bind and save"
              " firmware settings.",
              "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v69);
      WdsSetupLogMessageW(
        v70,
        409600,
        L"D",
        0,
        1460,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v67,
        v66,
        0,
        0);
      DestinationString = 0;
      v71 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v250);
      v72 = UnBCL::String::get_CString(v71);
      UnicodeString = 0;
      if ( !v72 )
        goto LABEL_56;
      v73 = RtlDosPathNameToNtPathName_U_WithStatus(v72, &UnicodeString, 0, 0);
      v74 = 0;
      if ( v73 < 0 )
        v74 = v73 | 0x10000000;
      if ( v74 >= 0 )
      {
        v74 = StrAllocatingPrintf(v244, L"%wZ", &UnicodeString);
        v62 = (WCHAR *)v244[0];
      }
      RtlFreeUnicodeString(&UnicodeString);
      if ( v74 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, v62);
        v75 = SetupPrepareForSystemStore(&DestinationString);
        if ( v75 < 0 )
        {
          v89 = GetLastError();
          v90 = CurrentIP();
          v91 = ConstructPartialMsgW(
                  0x3000000u,
                  "%hs: Failed to create directory %s , ec = [%x]",
                  "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                  (const char *)v62,
                  v75);
          WdsSetupLogMessageW(
            v91,
            409600,
            L"D",
            0,
            1497,
            L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
            L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
            v90,
            v89,
            0,
            0);
        }
        else
        {
          v76 = BcdCreateStore(&DestinationString, v248);
          if ( v76 < 0 )
          {
            v86 = GetLastError();
            v87 = CurrentIP();
            v88 = ConstructPartialMsgW(
                    0x3000000u,
                    "%hs:BcdCreateStore() for %s failed, ec = [%x]",
                    "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                    (const char *)v62,
                    v76);
            WdsSetupLogMessageW(
              v88,
              409600,
              L"D",
              0,
              1492,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v87,
              v86,
              0,
              0);
          }
          else
          {
            v77 = GetLastError();
            v78 = CurrentIP();
            v79 = ConstructPartialMsgW(
                    0x4000000u,
                    "%hs:Created Store %s",
                    "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                    (const char *)v62);
            WdsSetupLogMessageW(
              v79,
              409600,
              L"D",
              0,
              1472,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v78,
              v77,
              0,
              0);
            BcdCloseStore(v248[0]);
            v248[0] = 0;
            v80 = BcdImportStore(0);
            if ( v80 < 0 )
            {
              v84 = GetLastError();
              v85 = CurrentIP();
              v83 = ConstructPartialMsgW(
                      0x3000000u,
                      "%hs:BcdImportStore failed, ec = [%x]",
                      "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                      v80);
              v239 = v84;
              v235 = v85;
              pbCancela = 1486;
            }
            else
            {
              v261 = 1;
              v81 = GetLastError();
              v82 = CurrentIP();
              v83 = ConstructPartialMsgW(
                      0x4000000u,
                      "%hs:Promoted the newly created store file to the system BCD Store",
                      "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize");
              v239 = v81;
              v235 = v82;
              pbCancela = 1482;
            }
            WdsSetupLogMessageW(
              v83,
              409600,
              L"D",
              0,
              pbCancela,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v235,
              v239,
              0,
              0);
            DestinationString.Buffer = 0;
          }
        }
        v3 = a2;
      }
      else
      {
LABEL_56:
        v92 = GetLastError();
        v93 = CurrentIP();
        v94 = ConstructPartialMsgW(
                0x3000000u,
                "%hs: Failed to convert dos path to NT path for system BCD store and firmware setting won't be saved for rollback.",
                "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize");
        WdsSetupLogMessageW(
          v94,
          409600,
          L"D",
          0,
          1502,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v93,
          v92,
          0,
          0);
      }
      if ( v62 )
      {
        v95 = GetProcessHeap();
        HeapFree(v95, 0, v62);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v250);
      v59 = (const wchar_t *)v242[0];
    }
    v96 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&lpMem);
    if ( !UnBCL::Directory::Exists(v96) )
    {
      v183 = GetLastError();
      v184 = CurrentIP();
      v185 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&lpMem);
      v186 = (const char *)UnBCL::String::get_CString(v185);
      v187 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: \"%s\" does not exist.",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
               v186);
      WdsSetupLogMessageW(
        v187,
        409600,
        L"D",
        0,
        1632,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v184,
        v183,
        0,
        0);
      goto LABEL_85;
    }
    v97 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&lpMem);
    CBootCopyDelegate::CBootCopyDelegate((CBootCopyDelegate *)&v250, v97);
    v98 = UnBCL::String::Format(L"%s\\%s", v3, v59);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v248, v98);
    v99 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v248);
    v100 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&lpMem);
    UnBCL::Directory::Copy(v100, v99, 1, (struct UnBCL::Directory::ICopyDelegate *)&v250);
    v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&lpMem);
    v102 = UnBCL::String::get_CString(v101);
    v103 = UnBCL::String::Format(L"%s\\%s", v102, L"BCD");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v242, v103);
    v104 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v248);
    v105 = UnBCL::String::get_CString(v104);
    v106 = UnBCL::String::Format(L"%s\\%s", v105, L"BCD");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v244, v106);
    v107 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v242);
    if ( !UnBCL::File::Exists(v107) )
    {
LABEL_83:
      v178 = GetLastError();
      v179 = CurrentIP();
      v180 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&lpMem);
      v181 = (const char *)UnBCL::String::get_CString(v180);
      v182 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: Successfully saved \"%s\".",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
               v181);
      WdsSetupLogMessageW(
        v182,
        409600,
        L"D",
        0,
        1628,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v179,
        v178,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v244);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v242);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v248);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v252);
      UnBCL::Object::~Object((UnBCL::Object *)&v250);
LABEL_85:
      if ( v249 == 2 )
      {
        v188 = UnBCL::String::Format(L"%c:\\%s", *v10, L"EFI\\Microsoft\\Recovery");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v242, v188);
        v189 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v242);
        if ( UnBCL::Directory::Exists(v189) )
        {
          v190 = UnBCL::String::Format(L"%s\\%s", v3, L"EFI\\Microsoft\\Recovery");
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&DestinationString, v190);
          try
          {
            v191 = GetLastError();
            v192 = CurrentIP();
            v193 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&DestinationString);
            v194 = (const char *)UnBCL::String::get_CString(v193);
            v195 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
            v196 = (const char *)UnBCL::String::get_CString(v195);
            v197 = ConstructPartialMsgW(
                     0x4000000u,
                     "%hs: Copy directory [%s] to [%s]",
                     "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                     v196,
                     v194);
            WdsSetupLogMessageW(
              v197,
              409600,
              L"D",
              0,
              1652,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v192,
              v191,
              0,
              0);
            v198 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&DestinationString);
            v199 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v242);
            UnBCL::Directory::Copy(v199, v198, 1, 0);
          }
          catch ( UnBCL::Exception *v259 )
          {
            v220 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&DestinationString);
            v221 = (const char *)UnBCL::String::get_CString(v220);
            v222 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
            v223 = (const char *)UnBCL::String::get_CString(v222);
            v224 = v259;
            pExceptionLogFormat::pExceptionLogFormat(
              (pExceptionLogFormat *)&v250,
              0x3000000u,
              v259,
              "%hs: Failed to copy directory from [%s] to [%s]",
              "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v223,
              v221);
            UnBCL::Exception::AddStackTrace(
              v253[2],
              "void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRoll"
              "backService::ICheckpointParameters *)");
            v225 = GetLastError();
            v226 = CurrentIP();
            v227 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v251);
            v228 = (const char *)UnBCL::String::get_CString(v227);
            v229 = ConstructPartialMsgW(v250, "%s", v228);
            WdsSetupLogMessageW(
              v229,
              409600,
              L"D",
              0,
              1672,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v226,
              v225,
              0,
              0);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v253);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v251);
            if ( v224 )
              (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v224)(v224, 1);
            v10 = v243;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&DestinationString);
        }
        else
        {
          v200 = GetLastError();
          v201 = CurrentIP();
          v202 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
          v203 = (const char *)UnBCL::String::get_CString(v202);
          v204 = ConstructPartialMsgW(
                   0x4000000u,
                   "%hs: \"%s\" does not exist.",
                   "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                   v203);
          WdsSetupLogMessageW(
            v204,
            409600,
            L"D",
            0,
            1678,
            L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
            L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
            v201,
            v200,
            0,
            0);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v242);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&lpMem);
LABEL_93:
      if ( !v10 )
        return;
      goto LABEL_94;
    }
    v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
    v109 = (OSRollbackUtils *)UnBCL::String::get_CString(v108);
    v111 = OSRollbackUtils::SaveSystemBCDDatabase(v109, v110);
    for ( j = 1; ; ++j )
    {
      v113 = v111;
      if ( v111 != 32 )
        break;
      if ( j > 10 )
        goto LABEL_102;
      v114 = GetLastError();
      v115 = CurrentIP();
      v116 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: SaveSystemBCDDatabase returned sharing violation, waiting to retry. ",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize");
      WdsSetupLogMessageW(
        v116,
        409600,
        L"D",
        0,
        1532,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v115,
        v114,
        0,
        0);
      Sleep(100 * j);
      v117 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
      v118 = (OSRollbackUtils *)UnBCL::String::get_CString(v117);
      v111 = OSRollbackUtils::SaveSystemBCDDatabase(v118, v119);
    }
    if ( v111 == 1017 || v111 == 1006 )
    {
      v120 = GetLastError();
      v121 = CurrentIP();
      v122 = ConstructPartialMsgW(
               0x3000000u,
               "%hs: SaveSystemBCDDatabase failed, ec = [0x%X]",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
               v113);
      WdsSetupLogMessageW(
        v122,
        409600,
        L"D",
        0,
        1547,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v121,
        v120,
        0,
        0);
      v123 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
      v124 = UnBCL::String::get_CString(v123);
      v125 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
      v126 = UnBCL::String::get_CString(v125);
      if ( CopyFileExW(v126, v124, 0, 0, 0, 0) )
      {
        v127 = GetLastError();
        v128 = CurrentIP();
        v129 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
        v130 = (const char *)UnBCL::String::get_CString(v129);
        v131 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
        v132 = (const char *)UnBCL::String::get_CString(v131);
        v133 = ConstructPartialMsgW(
                 0x4000000u,
                 "%hs: Successfully copied \"%s\" to \"%s\".",
                 "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                 v132,
                 v130);
        WdsSetupLogMessageW(
          v133,
          409600,
          L"D",
          0,
          1555,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v128,
          v127,
          0,
          0);
        v134 = BcdImportStore(0);
        if ( v134 >= 0 )
        {
          v135 = GetLastError();
          v136 = CurrentIP();
          v137 = ConstructPartialMsgW(
                   0x4000000u,
                   "%hs: Promoted the existing store file to the system BCD Store",
                   "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize");
          v240 = v135;
          v236 = v136;
          pbCancelb = 1562;
LABEL_71:
          WdsSetupLogMessageW(
            v137,
            409600,
            L"D",
            0,
            pbCancelb,
            L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
            L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
            v236,
            v240,
            0,
            0);
LABEL_77:
          if ( v261 )
          {
            v157 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v248);
            v158 = UnBCL::String::get_CString(v157);
            v159 = UnBCL::String::Format(L"%s\\%s", v158, L"$NeedDeleteBCD.tag");
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&DestinationString, v159);
            v160 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&DestinationString);
            v161 = UnBCL::String::get_CString(v160);
            FileW = CreateFileW(v161, 0x40000000u, 1u, 0, 2u, 0x80000007, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              v163 = GetLastError();
              v164 = CurrentIP();
              v165 = GetLastError();
              v166 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&DestinationString);
              v167 = (const char *)UnBCL::String::get_CString(v166);
              v168 = ConstructPartialMsgW(
                       0x3000000u,
                       "%hs: Error creating tag file [%s] to mark the system BCD store as temporary, GLE=0x%x",
                       "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                       v167,
                       v165);
              v241 = v163;
              v237 = v164;
              pbCancelc = 1616;
            }
            else
            {
              CloseHandle(FileW);
              v169 = GetLastError();
              v170 = CurrentIP();
              v171 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&DestinationString);
              v172 = (const char *)UnBCL::String::get_CString(v171);
              v168 = ConstructPartialMsgW(
                       0x4000000u,
                       "%hs: Successfully created tag file [%s] to mark the system BCD store as temporary.",
                       "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                       v172);
              v241 = v169;
              v237 = v170;
              pbCancelc = 1622;
            }
            WdsSetupLogMessageW(
              v168,
              409600,
              L"D",
              0,
              pbCancelc,
              L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
              L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
              v237,
              v241,
              0,
              0);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&DestinationString);
          }
          v173 = GetLastError();
          v174 = CurrentIP();
          v175 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
          v176 = (const char *)UnBCL::String::get_CString(v175);
          v177 = ConstructPartialMsgW(
                   0x4000000u,
                   "%hs: Successfully saved BCD[%s].",
                   "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                   v176);
          WdsSetupLogMessageW(
            v177,
            409600,
            L"D",
            0,
            1625,
            L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
            L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
            v174,
            v173,
            0,
            0);
          v10 = v243;
          v3 = a2;
          goto LABEL_83;
        }
        v138 = GetLastError();
        v139 = CurrentIP();
        v140 = ConstructPartialMsgW(
                 0x3000000u,
                 "%hs: BcdImportStore failed, ec = [0x%X]",
                 "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                 v134);
        WdsSetupLogMessageW(
          v140,
          409600,
          L"D",
          0,
          1567,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v139,
          v138,
          0,
          0);
        v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
        v142 = UnBCL::String::get_CString(v141);
        if ( (unsigned int)DeleteFileEx2(v142, 0) )
        {
          v143 = GetLastError();
          v144 = CurrentIP();
          v137 = ConstructPartialMsgW(
                   0x4000000u,
                   "%hs: Successfully deleted old BCD store",
                   "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize");
          v240 = v143;
          v236 = v144;
          pbCancelb = 1573;
          goto LABEL_71;
        }
        v145 = GetLastError();
        v146 = CurrentIP();
        v147 = GetLastError();
        v148 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Deleting old BCD store failed, gle = [0x%X]",
                 "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                 v147);
        WdsSetupLogMessageW(
          v148,
          409600,
          L"D",
          0,
          1578,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v146,
          v145,
          0,
          0);
      }
      else
      {
        v149 = GetLastError();
        v150 = CurrentIP();
        v151 = GetLastError();
        v152 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
        v153 = (const char *)UnBCL::String::get_CString(v152);
        v154 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
        v155 = (const char *)UnBCL::String::get_CString(v154);
        v156 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Failed to copy \"%s\" to \"%s\" GLE = [%d].",
                 "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
                 v155,
                 v153,
                 v151);
        WdsSetupLogMessageW(
          v156,
          409600,
          L"D",
          0,
          1584,
          L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
          L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
          v150,
          v149,
          0,
          0);
      }
    }
    if ( v113 )
    {
LABEL_102:
      SetLastError(v113);
      v212 = GetLastError();
      v213 = CurrentIP();
      v214 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v244);
      v215 = (const char *)UnBCL::String::get_CString(v214);
      v216 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
      v217 = (const char *)UnBCL::String::get_CString(v216);
      v218 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Failed to backup BCD database from \"%s\" to \"%s\".",
               "OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
               v217,
               v215);
      WdsSetupLogMessageW(
        v218,
        409600,
        L"D",
        0,
        1595,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::Finalize",
        v213,
        v212,
        0,
        0);
      v219 = (RollbackException *)UnBCL::Object::operator new(0x48u);
      if ( v219 )
        v4 = RollbackException::RollbackException(
               v219,
               v113,
               L"CSystemVolumeSelectionCheckpoint: Failed to backup BCD database.");
      v256 = AddStackTraceToException<UnBCL::InvalidOperationException>(
               v4,
               "void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::Finalize(const unsigned short *,struct OSRol"
               "lbackService::ICheckpointParameters *)");
      throw (RollbackException **)&v256;
    }
    goto LABEL_77;
  }
}

```

## disassembly

```asm
0x18047ede0  mov     rax, rsp
0x18047ede3  mov     [rax+10h], rdx
0x18047ede7  push    rdi
0x18047ede8  push    r12
0x18047edea  push    r13
0x18047edec  push    r14
0x18047edee  push    r15
0x18047edf0  sub     rsp, 130h
0x18047edf7  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18047edff  mov     [rax+8], rbx
0x18047ee03  mov     [rax+18h], rsi
0x18047ee07  mov     rax, r8
0x18047ee0a  mov     r13, rdx
0x18047ee0d  lea     rcx, aC; "C:"
0x18047ee14  mov     [rsp+158h+var_E8], rcx
0x18047ee19  xor     r15d, r15d
0x18047ee1c  test    rdx, rdx
0x18047ee1f  jz      loc_1804804B5
0x18047ee25  mov     dword ptr [rsp+158h+pbCancel], r15d
0x18047ee2a  lea     r9, ??_R0?AVCSetupBasicCheckpointParameters@OSRollbackService@@@8; OSRollbackService::CSetupBasicCheckpointParameters `RTTI Type Descriptor'
0x18047ee31  lea     r8, ??_R0?AUICheckpointParameters@OSRollbackService@@@8; OSRollbackService::ICheckpointParameters `RTTI Type Descriptor'
0x18047ee38  xor     edx, edx
0x18047ee3a  mov     rcx, rax
0x18047ee3d  call    __RTDynamicCast_0
0x18047ee42  test    rax, rax
0x18047ee45  jz      short loc_18047EE58
0x18047ee47  mov     rcx, rax; this
0x18047ee4a  call    ?GetBlackboardDword@CSetupBasicCheckpointParameters@OSRollbackService@@QEAAKPEBG0K@Z; OSRollbackService::CSetupBasicCheckpointParameters::GetBlackboardDword(ushort const *,ushort const *,ulong)
0x18047ee4f  cmp     eax, 1
0x18047ee52  jz      loc_180480498
0x18047ee58  lea     rcx, [rsp+158h+var_E8]
0x18047ee5d  call    GetSystemPartitionPath
0x18047ee62  mov     rsi, [rsp+158h+var_E8]
0x18047ee67  test    eax, eax
0x18047ee69  jns     short loc_18047EE74
0x18047ee6b  test    rsi, rsi
0x18047ee6e  jnz     loc_180480484
0x18047ee74  mov     [rsp+158h+arg_18], r15d
0x18047ee7c  lea     r8, [rsp+158h+arg_18]
0x18047ee84  xor     edx, edx
0x18047ee86  xor     ecx, ecx
0x18047ee88  call    cs:__imp_SyspartGetSystemPartition
0x18047ee8e  cmp     eax, 0C0000023h
0x18047ee93  jnz     loc_18047EFF6
0x18047ee99  cmp     [rsp+158h+arg_18], r15d
0x18047eea1  jbe     loc_18047EFF6
0x18047eea7  mov     ebx, [rsp+158h+arg_18]
0x18047eeae  add     rbx, rbx
0x18047eeb1  call    cs:__imp_GetProcessHeap
0x18047eeb7  mov     rcx, rax; hHeap
0x18047eeba  mov     r8, rbx; dwBytes
0x18047eebd  mov     edx, 8; dwFlags
0x18047eec2  call    cs:__imp_HeapAlloc
0x18047eec8  mov     rdi, rax
0x18047eecb  test    rax, rax
0x18047eece  jz      short loc_18047EF3D
0x18047eed0  lea     r8, [rsp+158h+arg_18]
0x18047eed8  mov     edx, [rsp+158h+arg_18]
0x18047eedf  mov     rcx, rax
0x18047eee2  call    cs:__imp_SyspartGetSystemPartition
0x18047eee8  mov     r12d, 4000000h
0x18047eeee  lea     rcx, g_WdsLibLog
0x18047eef5  mov     edx, r12d
0x18047eef8  test    eax, eax
0x18047eefa  js      short loc_18047EF10
0x18047eefc  mov     ebx, r15d
0x18047eeff  mov     r9, rdi
0x18047ef02  lea     r8, aGetsystemparti_1; "GetSystemPartitionNTPath: Found system "...
0x18047ef09  call    LibLog
0x18047ef0e  jmp     short loc_18047EF75
0x18047ef10  mov     r9d, eax
0x18047ef13  lea     r8, aGetsystemparti; "GetSystemPartitionNTPath: BCD APIs coul"...
0x18047ef1a  call    LibLog
0x18047ef1f  mov     ebx, 1
0x18047ef24  call    cs:__imp_GetProcessHeap
0x18047ef2a  mov     rcx, rax; hHeap
0x18047ef2d  mov     r8, rdi; lpMem
0x18047ef30  xor     edx, edx; dwFlags
0x18047ef32  call    cs:__imp_HeapFree
0x18047ef38  mov     rdi, r15
0x18047ef3b  jmp     short loc_18047EF75
0x18047ef3d  call    cs:__imp_GetLastError
0x18047ef43  test    eax, eax
0x18047ef45  jle     short loc_18047EF51
0x18047ef47  movzx   eax, ax
0x18047ef4a  or      eax, 80070000h
0x18047ef4f  test    eax, eax
0x18047ef51  jns     short loc_18047EF6A
0x18047ef53  call    cs:__imp_GetLastError
0x18047ef59  mov     ebx, eax
0x18047ef5b  test    eax, eax
0x18047ef5d  jle     short loc_18047EF6F
0x18047ef5f  movzx   ebx, ax
0x18047ef62  or      ebx, 80070000h
0x18047ef68  jmp     short loc_18047EF6F
0x18047ef6a  mov     ebx, 80004005h
0x18047ef6f  mov     r12d, 4000000h
0x18047ef75  test    ebx, ebx
0x18047ef77  js      loc_18048047A
0x18047ef7d  test    rdi, rdi
0x18047ef80  jz      loc_18047F015
0x18047ef86  mov     [rsp+158h+var_C8], 2
0x18047ef92  mov     [rsp+158h+lpMem], rdi
0x18047ef9a  lea     r8, [rsp+158h+var_E8]; unsigned __int16 **
0x18047ef9f  lea     rcx, [rsp+158h+lpMem]; struct _VOLUME_REFERENCE *
0x18047efa7  call    ?PrepareVolumeAccessPath@@YAJPEAU_VOLUME_REFERENCE@@KPEAPEAG@Z; PrepareVolumeAccessPath(_VOLUME_REFERENCE *,ulong,ushort * *)
0x18047efac  mov     ebx, eax
0x18047efae  mov     eax, dword ptr [rsp+158h+var_C8]
0x18047efb5  sub     eax, 1
0x18047efb8  jz      short loc_18047EFC4
0x18047efba  sub     eax, 1
0x18047efbd  jz      short loc_18047EFC4
0x18047efbf  cmp     eax, 1
0x18047efc2  jnz     short loc_18047EFE7
0x18047efc4  cmp     [rsp+158h+lpMem], r15
0x18047efcc  jz      short loc_18047EFE7
0x18047efce  call    cs:__imp_GetProcessHeap
0x18047efd4  mov     r8, [rsp+158h+lpMem]; lpMem
0x18047efdc  xor     edx, edx; dwFlags
0x18047efde  mov     rcx, rax; hHeap
0x18047efe1  call    cs:__imp_HeapFree
0x18047efe7  test    ebx, ebx
0x18047efe9  js      loc_18048047A
0x18047efef  mov     rsi, [rsp+158h+var_E8]
0x18047eff4  jmp     short loc_18047F015
0x18047eff6  mov     r9d, eax
0x18047eff9  lea     r8, aGetsystemparti; "GetSystemPartitionNTPath: BCD APIs coul"...
0x18047f000  mov     r12d, 4000000h
0x18047f006  mov     edx, r12d
0x18047f009  lea     rcx, g_WdsLibLog
0x18047f010  call    LibLog
0x18047f015  test    rsi, rsi
0x18047f018  jz      loc_180480498
0x18047f01e  call    cs:__imp_GetLastError
0x18047f024  mov     edi, eax
0x18047f026  call    cs:__imp_CurrentIP
0x18047f02c  mov     rbx, rax
0x18047f02f  mov     r9, rsi
0x18047f032  lea     r8, aOsrollbackserv_6; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f039  lea     rdx, aHsSystemVolume; "%hs: System volume drive path is [%s]"
0x18047f040  mov     ecx, r12d; unsigned int
0x18047f043  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047f048  mov     [rsp+158h+var_108], r15d
0x18047f04d  mov     [rsp+158h+var_110], r15
0x18047f052  mov     [rsp+158h+var_118], edi
0x18047f056  mov     [rsp+158h+var_120], rbx
0x18047f05b  lea     rcx, aOsrollbackserv_9; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f062  mov     [rsp+158h+hTemplateFile], rcx
0x18047f067  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\rollback\\src\\comm"...
0x18047f06e  mov     qword ptr [rsp+158h+dwCopyFlags], rcx
0x18047f073  mov     dword ptr [rsp+158h+pbCancel], 57Ah
0x18047f07b  xor     r9d, r9d
0x18047f07e  lea     r8, aD_0; "D"
0x18047f085  mov     edx, 64000h
0x18047f08a  mov     rcx, rax
0x18047f08d  call    cs:__imp_WdsSetupLogMessageW
0x18047f093  movzx   r8d, word ptr [rsi]; unsigned __int16 *
0x18047f097  mov     rcx, r13; this
0x18047f09a  call    ?TrackVolume@VolumeTracking@OSRollbackUtils@@YAJPEBG0G@Z; OSRollbackUtils::VolumeTracking::TrackVolume(ushort const *,ushort const *,ushort)
0x18047f09f  mov     r14d, eax
0x18047f0a2  test    eax, eax
0x18047f0a4  js      loc_180480519
0x18047f0aa  mov     [rsp+158h+arg_18], r15d
0x18047f0b2  mov     r14d, r15d
0x18047f0b5  movsxd  rbx, r14d
0x18047f0b8  lea     rdi, off_1805495F0; "boot.ini"
0x18047f0bf  movzx   edx, word ptr [rsi]
0x18047f0c2  mov     r8, [rdi+rbx*8]
0x18047f0c6  lea     rcx, aCS; "%c:\\%s"
0x18047f0cd  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18047f0d3  mov     rdx, rax
0x18047f0d6  lea     rcx, [rsp+158h+var_F8]
0x18047f0db  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047f0e1  nop
0x18047f0e2  mov     r8, [rdi+rbx*8]
0x18047f0e6  mov     rdx, r13
0x18047f0e9  lea     rcx, aSS_8; "%s\\%s"
0x18047f0f0  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18047f0f6  mov     rdx, rax
0x18047f0f9  lea     rcx, [rsp+158h+var_E0]
0x18047f0fe  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047f104  nop
0x18047f105  lea     rcx, [rsp+158h+var_F8]
0x18047f10a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047f110  mov     rcx, rax
0x18047f113  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18047f119  test    eax, eax
0x18047f11b  jnz     loc_18047F1C7
0x18047f121  call    cs:__imp_GetLastError
0x18047f127  mov     edi, eax
0x18047f129  call    cs:__imp_CurrentIP
0x18047f12f  mov     rbx, rax
0x18047f132  lea     rcx, [rsp+158h+var_F8]
0x18047f137  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f13d  mov     rcx, rax
0x18047f140  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f146  mov     r9, rax
0x18047f149  lea     r8, aOsrollbackserv_6; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f150  lea     rdx, aHsSDoesNotExis_3; "%hs: %s does not exist, skip."
0x18047f157  mov     ecx, r12d; unsigned int
0x18047f15a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047f15f  mov     [rsp+158h+var_108], r15d
0x18047f164  mov     [rsp+158h+var_110], r15
0x18047f169  mov     [rsp+158h+var_118], edi
0x18047f16d  mov     [rsp+158h+var_120], rbx
0x18047f172  lea     rcx, aOsrollbackserv_9; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f179  mov     [rsp+158h+hTemplateFile], rcx
0x18047f17e  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\rollback\\src\\comm"...
0x18047f185  mov     qword ptr [rsp+158h+dwCopyFlags], rcx
0x18047f18a  mov     dword ptr [rsp+158h+pbCancel], 591h
0x18047f192  xor     r9d, r9d
0x18047f195  lea     r8, aD_0; "D"
0x18047f19c  mov     edx, 64000h
0x18047f1a1  mov     rcx, rax
0x18047f1a4  call    cs:__imp_WdsSetupLogMessageW
0x18047f1aa  nop
0x18047f1ab  lea     rcx, [rsp+158h+var_E0]
0x18047f1b0  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047f1b6  nop
0x18047f1b7  lea     rcx, [rsp+158h+var_F8]
0x18047f1bc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047f1c2  jmp     loc_18047F36C
0x18047f1c7  lea     rcx, [rsp+158h+var_E0]
0x18047f1cc  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f1d2  mov     rcx, rax
0x18047f1d5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f1db  mov     rbx, rax
0x18047f1de  lea     rcx, [rsp+158h+var_F8]
0x18047f1e3  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f1e9  mov     rcx, rax
0x18047f1ec  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f1f2  mov     [rsp+158h+dwCopyFlags], r15d; dwCopyFlags
0x18047f1f7  mov     [rsp+158h+pbCancel], r15; pbCancel
0x18047f1fc  xor     r9d, r9d; lpData
0x18047f1ff  xor     r8d, r8d; lpProgressRoutine
0x18047f202  mov     rdx, rbx; lpNewFileName
0x18047f205  mov     rcx, rax; lpExistingFileName
0x18047f208  call    cs:__imp_CopyFileExW
0x18047f20e  test    eax, eax
0x18047f210  jnz     loc_18047F2AA
0x18047f216  call    cs:__imp_GetLastError
0x18047f21c  mov     esi, eax
0x18047f21e  call    cs:__imp_CurrentIP
0x18047f224  mov     rdi, rax
0x18047f227  lea     rcx, [rsp+158h+var_E0]
0x18047f22c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f232  mov     rcx, rax
0x18047f235  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f23b  mov     rbx, rax
0x18047f23e  lea     rcx, [rsp+158h+var_F8]
0x18047f243  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f249  mov     rcx, rax
0x18047f24c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f252  mov     [rsp+158h+pbCancel], rbx
0x18047f257  mov     r9, rax
0x18047f25a  lea     r8, aOsrollbackserv_6; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f261  lea     rdx, aHsFailedToCopy; "%hs: Failed to copy \"%s\" to \"%s\", w"...
0x18047f268  mov     ecx, 2000000h; unsigned int
0x18047f26d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047f272  mov     [rsp+158h+var_108], r15d
0x18047f277  mov     [rsp+158h+var_110], r15
0x18047f27c  mov     [rsp+158h+var_118], esi
0x18047f280  mov     [rsp+158h+var_120], rdi
0x18047f285  lea     rcx, aOsrollbackserv_9; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f28c  mov     [rsp+158h+hTemplateFile], rcx
0x18047f291  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\rollback\\src\\comm"...
0x18047f298  mov     qword ptr [rsp+158h+dwCopyFlags], rcx
0x18047f29d  mov     dword ptr [rsp+158h+pbCancel], 597h
0x18047f2a5  jmp     loc_18047F337
0x18047f2aa  call    cs:__imp_GetLastError
0x18047f2b0  mov     esi, eax
0x18047f2b2  call    cs:__imp_CurrentIP
0x18047f2b8  mov     rdi, rax
0x18047f2bb  lea     rcx, [rsp+158h+var_E0]
0x18047f2c0  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f2c6  mov     rcx, rax
0x18047f2c9  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f2cf  mov     rbx, rax
0x18047f2d2  lea     rcx, [rsp+158h+var_F8]
0x18047f2d7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047f2dd  mov     rcx, rax
0x18047f2e0  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047f2e6  mov     [rsp+158h+pbCancel], rbx
0x18047f2eb  mov     r9, rax
0x18047f2ee  lea     r8, aOsrollbackserv_6; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f2f5  lea     rdx, aHsSuccessfully_4; "%hs: Successfully copied \"%s\" to \"%s"...
0x18047f2fc  mov     ecx, r12d; unsigned int
0x18047f2ff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047f304  mov     [rsp+158h+var_108], r15d
0x18047f309  mov     [rsp+158h+var_110], r15
0x18047f30e  mov     [rsp+158h+var_118], esi
0x18047f312  mov     [rsp+158h+var_120], rdi
0x18047f317  lea     rcx, aOsrollbackserv_9; "OSRollbackService::CBootFilesRestoreChe"...
0x18047f31e  mov     [rsp+158h+hTemplateFile], rcx
0x18047f323  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\rollback\\src\\comm"...
0x18047f32a  mov     qword ptr [rsp+158h+dwCopyFlags], rcx
0x18047f32f  mov     dword ptr [rsp+158h+pbCancel], 59Ah
0x18047f337  xor     r9d, r9d
0x18047f33a  lea     r8, aD_0; "D"
0x18047f341  mov     edx, 64000h
  ... truncated ...
```
