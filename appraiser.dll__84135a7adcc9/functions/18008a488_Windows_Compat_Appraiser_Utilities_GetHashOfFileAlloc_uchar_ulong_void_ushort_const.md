# Windows::Compat::Appraiser::Utilities::GetHashOfFileAlloc(uchar * *,ulong *,void * *,ushort const *)

- ea: `0x18008a488`
- end: `0x18008a847`
- name: `?GetHashOfFileAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAEPEAKPEAPEAXPEBG@Z`
- size: `959`
- prototype: `static int(unsigned __int8 **, unsigned int *, void **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180087a0c`

## callees

- `0x180008570`
- `0x180014be8`
- `0x1800301d0`
- `0x18008a488`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008a501`
- `KERNEL32!CreateFileW` at `0x18008a501`
- `KERNEL32!GetProcessHeap` at `0x18008a63b`
- `KERNEL32!GetProcessHeap` at `0x18008a75b`
- `KERNEL32!GetProcessHeap` at `0x18008a814`
- `KERNEL32!GetProcessHeap` at `0x18008a63b`
- `KERNEL32!GetProcessHeap` at `0x18008a75b`
- `KERNEL32!GetProcessHeap` at `0x18008a814`
- `KERNEL32!HeapAlloc` at `0x18008a649`
- `KERNEL32!HeapAlloc` at `0x18008a769`
- `KERNEL32!HeapAlloc` at `0x18008a649`
- `KERNEL32!HeapAlloc` at `0x18008a769`
- `KERNEL32!CloseHandle` at `0x18008a809`
- `KERNEL32!CloseHandle` at `0x18008a809`
- `KERNEL32!GetLastError` at `0x18008a510`
- `KERNEL32!GetLastError` at `0x18008a52f`
- `KERNEL32!GetLastError` at `0x18008a5a7`
- `KERNEL32!GetLastError` at `0x18008a5c6`
- `KERNEL32!GetLastError` at `0x18008a5fe`
- `KERNEL32!GetLastError` at `0x18008a61d`
- `KERNEL32!GetLastError` at `0x18008a682`
- `KERNEL32!GetLastError` at `0x18008a6a1`
- `KERNEL32!GetLastError` at `0x18008a6cd`
- `KERNEL32!GetLastError` at `0x18008a6ec`
- `KERNEL32!GetLastError` at `0x18008a71e`
- `KERNEL32!GetLastError` at `0x18008a73d`
- `KERNEL32!GetLastError` at `0x18008a792`
- `KERNEL32!GetLastError` at `0x18008a7b1`
- `KERNEL32!GetLastError` at `0x18008a510`
- `KERNEL32!GetLastError` at `0x18008a52f`
- `KERNEL32!GetLastError` at `0x18008a5a7`
- `KERNEL32!GetLastError` at `0x18008a5c6`
- `KERNEL32!GetLastError` at `0x18008a5fe`
- `KERNEL32!GetLastError` at `0x18008a61d`
- `KERNEL32!GetLastError` at `0x18008a682`
- `KERNEL32!GetLastError` at `0x18008a6a1`
- `KERNEL32!GetLastError` at `0x18008a6cd`
- `KERNEL32!GetLastError` at `0x18008a6ec`
- `KERNEL32!GetLastError` at `0x18008a71e`
- `KERNEL32!GetLastError` at `0x18008a73d`
- `KERNEL32!GetLastError` at `0x18008a792`
- `KERNEL32!GetLastError` at `0x18008a7b1`
- `KERNEL32!HeapFree` at `0x18008a822`
- `KERNEL32!HeapFree` at `0x18008a822`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18008a7f6`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18008a7f6`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x18008a599`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x18008a599`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18008a5f4`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18008a674`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18008a5f4`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x18008a674`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18008a6bf`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18008a6bf`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18008a714`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18008a788`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18008a714`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18008a788`

## string_xrefs

- `0x18008a551`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008a53e`: `Error opening file: [%d].`
- `0x18008a54a`: `Windows::Compat::Appraiser::Utilities::GetHashOfFileAlloc`

## pseudocode

```c

```
