# Jot::CFileHandle::_CreateFile(wchar_t const *,Jot::StorageAccessMode,ulong,ulong,bool,bool,Jot::CFileHandle *,std::exception_ptr *,Jot::ReconnectCoherencyData *,Jot::CFileHandle *,MsoCF::CExclusive<Jot::CStorageAccessModeFlags> *)

- ea: `0x1801f05b0`
- end: `0x1801f0b4d`
- name: `?_CreateFile@CFileHandle@Jot@@QEAAXPEB_WW4StorageAccessMode@2@KK_N2PEAV12@PEAVexception_ptr@std@@PEAUReconnectCoherencyData@2@3PEAV?$CExclusive@VCStorageAccessModeFlags@Jot@@@MsoCF@@@Z`
- size: `1437`
- prototype: `__int64 __usercall@<rax>(struct Jot::ReconnectCoherencyData *@<rcx>, Jot *this@<rdx>, unsigned int, char, char, Jot::CFileHandle *, __int64, Jot *, struct Jot::ReconnectCoherencyData *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops`

## callers

- `0x1801ef748`

## callees

- `0x1801c3df4`
- `0x1801c53dc`
- `0x1801c5418`
- `0x1801c5510`
- `0x1801c55e4`
- `0x1801ec0e0`
- `0x1801ecf50`
- `0x1801ed020`
- `0x1801ed08c`
- `0x1801f05b0`
- `0x1801f0b50`
- `0x1801f4b80`
- `0x18022fd10`
- `0x18024050c`
- `0x1802e5060`
- `0x1802e5170`
- `0x1803881c4`
- `0x180444d58`
- `0x18046a98c`
- `0x18072ef78`
- `0x18082f460`
- `0x180dad178`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801f0b41`
- `KERNEL32!CloseHandle` at `0x1801f0b41`
- `KERNEL32!GetLastError` at `0x1801f0715`
- `KERNEL32!GetLastError` at `0x1801f0715`
- `MSVCP140!_Mtx_unlock` at `0x1801f09cd`
- `MSVCP140!_Mtx_unlock` at `0x1801f0a0d`
- `MSVCP140!_Mtx_unlock` at `0x1801f09cd`
- `MSVCP140!_Mtx_unlock` at `0x1801f0a0d`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0735`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0774`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f09f8`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0af8`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0b28`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0735`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0774`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f09f8`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0af8`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1801f0b28`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801f086b`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801f0a42`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801f086b`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1801f0a42`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801f0602`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1801f0602`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0740`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f08c5`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0a03`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0b33`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0740`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f08c5`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0a03`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1801f0b33`

## pseudocode

```c

```
