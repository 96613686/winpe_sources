# BfsServiceBootFilesEx2

- ea: `0x180049234`
- end: `0x18004a670`
- name: `BfsServiceBootFilesEx2`
- size: `5180`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ee78`

## callees

- `0x18000282c`
- `0x180002858`
- `0x1800078b0`
- `0x1800085d4`
- `0x180046374`
- `0x180046544`
- `0x1800466c0`
- `0x1800466ec`
- `0x180047280`
- `0x1800472f4`
- `0x18004851c`
- `0x1800489c4`
- `0x180049234`
- `0x18004a678`
- `0x18004aca0`
- `0x18004aec4`
- `0x18004b38c`
- `0x18004b700`
- `0x18004b980`
- `0x18004bc94`
- `0x18004bf48`
- `0x18004c03c`
- `0x18004c0c4`
- `0x18004c548`
- `0x18004c58c`
- `0x18004c5d0`
- `0x18004c614`
- `0x18004ccf0`
- `0x18004cdac`
- `0x18004cdd4`
- `0x18004cf64`
- `0x18004d118`
- `0x18004d3e0`
- `0x18004d500`
- `0x18004d778`
- `0x18004d7b4`
- `0x180051378`
- `0x1800513d4`
- `0x1800515f4`
- `0x18005176c`
- `0x180051c74`
- `0x18005214c`
- `0x180052400`
- `0x180052c8c`
- `0x180053994`
- `0x180059278`

## import_xrefs

- `ntdll!NtClose` at `0x180049e13`
- `ntdll!NtClose` at `0x180049e13`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180049da8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180049da8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049bb9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049bb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004999d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049fd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a0c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a40c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a463`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a49d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a568`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a585`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049583`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004999d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049fd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a0c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a40c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a463`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a49d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a4f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a568`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a585`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a5f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004998f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049aaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a0b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a3fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a41b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a48f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a53d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a55a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a577`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004998f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049aaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a0b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a3fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a41b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a48f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a4e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a53d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a55a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a577`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a5eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a608`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ac3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049d59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ac3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a26f`

## string_xrefs

- `0x1800493f7`: `ServiceBootFiles MuiOnly:%c Res:%c Fonts:%c BootMgrOvw:%c BootStatOvw:%c DbgTrn:%c SuspendBDE:%c BootEx:%c Offline:%c DryRun:%c ChkReseal:%c`
- `0x18004994a`: `Failed to copy Boot Manager to default EFI application. Last error = %#x`
- `0x1800498cd`: `Default EFI application is not Windows boot manager, will not update.`
- `0x180049918`: `Failed to create path for default EFI application. Last error = %#x`
- `0x1800499c3`: `Copy files which lack a version: %s	%s -> %s `
- `0x1800498f9`: `Bootmgfw on ESP is newer than that in source, will not update Default EFI application.`
- `0x180049a9e`: `Creating Recovery directory.`
- `0x180049a0b`: `Error copying boot files from %s to %s! Last Error = %#x`
- `0x180049bf6`: `Failed to expand Recovery directory path`
- `0x180049b46`: `Failed to create Recovery directory. Last error = %#x`
- `0x180049c9d`: `Error uncompressing boor manager (%s)! Last Error = %#x`
- `0x180049e29`: `Error uncompressing boot status data log(%s)! Last Error = %#x`
- `0x180049fbf`: `Error copying font files from %s to %s.Last Error = %#x`
- `0x180049f73`: `Copying font files from %s to %s...`
- `0x18004a05c`: `Copying resource files from %s to %s...`
- `0x18004a1ff`: `Error copying %s to %s. Last Error = %#x`
- `0x18004a275`: `Error setting security attributes on %s. Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfsServiceBootFilesEx2(const WCHAR *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  void *v5; // r12
  WCHAR *v6; // rdi
  unsigned int v7; // esi
  __int64 v8; // rbx
  unsigned int v9; // r13d
  const wchar_t *Value; // rax
  wchar_t *v11; // r14
  LPWSTR v12; // r15
  unsigned int ShouldUse; // eax
  unsigned int v14; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // rax
  signed __int64 v17; // rdx
  unsigned __int16 v18; // cx
  int v19; // edi
  bool v20; // zf
  void *VolumeName; // rax
  DWORD LastError; // eax
  const wchar_t *v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int ShouldFileBeCopied; // r14d
  const WCHAR *v28; // rax
  void *v29; // r15
  LPCWSTR v30; // rdi
  void *v31; // rsi
  __int64 v32; // rax
  WCHAR *v33; // rdi
  int v34; // ebx
  int IsWindowsBinary; // eax
  wchar_t *v36; // rbx
  DWORD v37; // eax
  DWORD v38; // eax
  HANDLE v39; // rax
  HANDLE v40; // rax
  const wchar_t *v41; // r8
  int v42; // ebx
  DWORD v43; // eax
  const wchar_t *v44; // rdx
  LPVOID v45; // r9
  void *v46; // r8
  HANDLE v47; // rax
  HANDLE v48; // rax
  HANDLE v49; // rax
  _OWORD *v50; // rax
  __int64 v51; // rax
  void *v52; // rbx
  DWORD v53; // eax
  HANDLE v54; // rax
  HANDLE FileW; // rdi
  const WCHAR *v56; // rdi
  unsigned int v57; // eax
  DWORD v58; // eax
  HANDLE v59; // rax
  void *v60; // rax
  void *v61; // rbx
  DWORD v62; // eax
  HANDLE v63; // rax
  unsigned int v64; // eax
  __int64 v65; // rbx
  void *v66; // rax
  int v67; // edi
  HANDLE v68; // rax
  HANDLE v69; // rax
  void *v70; // rax
  int v71; // r15d
  HANDLE v72; // rax
  WCHAR *v73; // rdi
  void *v74; // rax
  __int64 v75; // r14
  DWORD v76; // eax
  const wchar_t *v77; // r8
  void *v78; // rax
  __int64 v79; // r15
  unsigned int v80; // eax
  BOOL v81; // edi
  HANDLE v82; // rax
  void *v83; // rdi
  HANDLE v84; // rax
  void *v85; // rdi
  HANDLE v86; // rax
  WCHAR *v87; // rdi
  HANDLE v88; // rax
  void *v89; // rdi
  HANDLE v90; // rax
  LPWSTR v91; // rdi
  HANDLE v92; // rax
  wchar_t *v93; // rdi
  HANDLE v94; // rax
  WCHAR *v95; // rdi
  HANDLE v96; // rax
  void *v97; // rdi
  HANDLE v98; // rax
  void *v99; // rdi
  HANDLE v100; // rax
  void *v101; // rdi
  HANDLE v102; // rax
  WCHAR *v103; // rdi
  HANDLE v104; // rax
  WCHAR *v105; // rdi
  HANDLE v106; // rax
  WCHAR *v107; // rdi
  HANDLE v108; // rax
  PTOKEN_PRIVILEGES v109; // rdi
  HANDLE v110; // rax
  PTOKEN_PRIVILEGES v111; // rdi
  HANDLE v112; // rax
  void *v113; // rdi
  HANDLE v114; // rax
  void *v115; // rdi
  HANDLE v116; // rax
  void *v117; // rdi
  HANDLE v118; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  int v122; // [rsp+70h] [rbp-90h]
  BOOL v123; // [rsp+74h] [rbp-8Ch]
  __int128 v124; // [rsp+78h] [rbp-88h] BYREF
  int v125; // [rsp+88h] [rbp-78h]
  unsigned int v126; // [rsp+8Ch] [rbp-74h]
  BOOL v127; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v128; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v129; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-60h]
  BOOL v131; // [rsp+A8h] [rbp-58h]
  LPVOID lpMem; // [rsp+B0h] [rbp-50h]
  LPCWSTR v133; // [rsp+B8h] [rbp-48h]
  wchar_t *Str; // [rsp+C0h] [rbp-40h]
  unsigned int v135; // [rsp+C8h] [rbp-38h] BYREF
  int v136; // [rsp+CCh] [rbp-34h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v138; // [rsp+D8h] [rbp-28h]
  LPCWSTR v139; // [rsp+E0h] [rbp-20h]
  LPVOID v140; // [rsp+E8h] [rbp-18h] BYREF
  LPWSTR pObjectName; // [rsp+F0h] [rbp-10h]
  __int64 v142; // [rsp+F8h] [rbp-8h]
  LPCWSTR v143; // [rsp+100h] [rbp+0h]
  PTOKEN_PRIVILEGES v144; // [rsp+108h] [rbp+8h]
  PTOKEN_PRIVILEGES NewState; // [rsp+110h] [rbp+10h] BYREF
  LPVOID v146; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v147; // [rsp+120h] [rbp+20h]
  __int64 v148; // [rsp+128h] [rbp+28h] BYREF
  LPCWSTR v149; // [rsp+130h] [rbp+30h]
  LPCWSTR lpszFileName; // [rsp+138h] [rbp+38h]
  LPVOID v151; // [rsp+140h] [rbp+40h]
  LPVOID v152; // [rsp+148h] [rbp+48h]
  LPVOID v153; // [rsp+150h] [rbp+50h]
  LPVOID v154; // [rsp+158h] [rbp+58h]
  char v155[32]; // [rsp+160h] [rbp+60h] BYREF
  __int64 *v156; // [rsp+180h] [rbp+80h]
  __int64 v157; // [rsp+188h] [rbp+88h]
  unsigned int *v158; // [rsp+190h] [rbp+90h]
  __int64 v159; // [rsp+198h] [rbp+98h]
  unsigned int *v160; // [rsp+1A0h] [rbp+A0h]
  __int64 v161; // [rsp+1A8h] [rbp+A8h]
  BOOL *v162; // [rsp+1B0h] [rbp+B0h]
  __int64 v163; // [rsp+1B8h] [rbp+B8h]

  v148 = a4;
  lpszFileName = a1;
  v127 = 0;
  v136 = 0;
  NumberOfBytesWritten = 0;
  v122 = 1;
  v5 = 0;
  v124 = 0;
  pObjectName = 0;
  Str = 0;
  v153 = 0;
  lpFileName = 0;
  v133 = 0;
  v140 = 0;
  v138 = 0;
  v139 = 0;
  v151 = 0;
  v152 = 0;
  v123 = 0;
  NewState = 0;
  v144 = 0;
  v154 = 0;
  v146 = 0;
  lpMem = 0;
  v147 = 0;
  v149 = 0;
  v143 = 0;
  v126 = 0;
  v135 = 0;
  v128 = 0;
  if ( (unsigned int)Feature_UseExDefault__private_IsEnabledDeviceUsageNoInline() && (a2 & 0x800) == 0 )
    a2 |= 0x400u;
  BfspLogInitializeFromFlags(a2);
  v125 = a2 & 1;
  BfspLogMessage(
    2,
    L"ServiceBootFiles MuiOnly:%c Res:%c Fonts:%c BootMgrOvw:%c BootStatOvw:%c DbgTrn:%c SuspendBDE:%c BootEx:%c Offline:%"
     "c DryRun:%c ChkReseal:%c",
    v125 != 0 ? 121 : 110,
    (a2 & 4) != 0 ? 121 : 110,
    (a2 & 8) != 0 ? 121 : 110,
    (a2 & 0x20) != 0 ? 121 : 110,
    (a2 & 0x80u) != 0 ? 121 : 110,
    (a2 & 0x100) != 0 ? 121 : 110,
    (a2 & 0x200) != 0 ? 121 : 110,
    (a2 & 0x400) != 0 ? 121 : 110,
    (a2 & 0x800) != 0 ? 121 : 110,
    (a2 & 0x1000) != 0 ? 121 : 110,
    (a2 & 0x2000) != 0 ? 121 : 110);
  v6 = (WCHAR *)lpszFileName;
  v7 = a2 & 0xFFFFFEF3;
  if ( (a2 & 1) == 0 )
    v7 = a2;
  v129 = v7;
  if ( !(unsigned int)BfspCreateEnvironment((unsigned __int16 *)lpszFileName) )
  {
    LODWORD(v8) = GetLastError();
    v9 = 1;
    goto LABEL_203;
  }
  v9 = 1;
  if ( !(unsigned int)BfspCreateTokenPrivilegesInformation(BfspPrivilegeNames, 4, 1, &NewState)
    || !(unsigned int)BfspAdjustTokenPrivileges(NewState) )
  {
    goto LABEL_9;
  }
  Value = (const wchar_t *)BfspEnvGetValue(&v124, L"FWTYPE");
  if ( !wcsncmp_0(Value, L"EFI", 4u) )
  {
    if ( (v7 & 0x800) == 0 )
      BfspDeleteBootmgfwForceSha1Variable();
  }
  else
  {
    v122 = 0;
  }
  v142 = BfspEnvGetValue(&v124, L"ACLS");
  v131 = v142 != 0;
  Str = (wchar_t *)BfspEnvExpandString(&v124, L"|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|");
  v11 = Str;
  if ( !Str )
    goto LABEL_9;
  pObjectName = (LPWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\|BOOTMGBIN|");
  v12 = pObjectName;
  if ( !pObjectName )
    goto LABEL_9;
  LODWORD(v8) = 0;
  if ( (unsigned int)Feature_Servicing_BFSVCExFiles__private_IsEnabledDeviceUsageNoInline() && v122 )
  {
    ShouldUse = BfspShouldUseExFiles(v7, v12, &v140, &v135);
    LODWORD(v8) = ShouldUse;
    if ( ShouldUse )
    {
      BfspLogMessage(4, L"ShouldUseExFiles check failed: %x, defaulting to 2011 binaries", ShouldUse);
      v14 = 0;
      LODWORD(v8) = 0;
    }
    else
    {
      v14 = v135;
    }
    v126 = v14;
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      Str = (wchar_t *)BfspEnvExpandString(&v124, L"|SOURCE|\\|FWTYPE|_EX\\|BOOTMGBINEX|");
      v11 = Str;
      if ( !Str )
        goto LABEL_9;
    }
    if ( v140 )
    {
      LODWORD(v8) = BfspCheckFileCertAuthority(v11, &v146);
      if ( (_DWORD)v8 )
        goto LABEL_202;
      v16 = (unsigned __int16 *)v140;
      v17 = (_BYTE *)v146 - (_BYTE *)v140;
      while ( 1 )
      {
        v18 = *v16;
        if ( *v16 != *(unsigned __int16 *)((char *)v16 + v17) )
          break;
        ++v16;
        if ( !v18 )
        {
          v19 = 0;
          goto LABEL_31;
        }
      }
      v19 = v18 < *(unsigned __int16 *)((char *)v16 + v17) ? -1 : 1;
LABEL_31:
      BfspLogMessage(2, L"Bootmgfw cert changed: %c", v19 != 0 ? 121 : 110);
      v20 = v19 == 0;
      v6 = (WCHAR *)lpszFileName;
      v123 = !v20;
    }
  }
  BfspSetSourceOsVersion(&v124);
  if ( (v7 & 0x200) != 0 )
  {
    VolumeName = (void *)BfsGetVolumeName(v6);
    v147 = VolumeName;
    if ( !VolumeName )
    {
      LastError = GetLastError();
      v23 = L"Failed to get VolumeName for %ws %x";
LABEL_35:
      LODWORD(v8) = LastError;
      v24 = LastError;
LABEL_36:
      BfspLogMessage(4, v23, v6, v24);
      goto LABEL_202;
    }
    BfspLogMessage(2, L"Source VolumeName %ws", VolumeName);
    v26 = BfspSuspendBitLocker(v147, v25, &v127, &v136);
    if ( v26 )
    {
      LODWORD(v8) = (unsigned __int16)v26;
      if ( (v26 & 0x1FFF0000) != 0x70000 )
        LODWORD(v8) = v26;
      BfspLogMessage(4, L"BfspSuspendBitLocker FAILED Error code = %#x", (unsigned int)v8);
      goto LABEL_202;
    }
    BfspLogMessage(
      2,
      L"BfspSuspendBitLocker SUCCEEDED (Enabled:%c Suspended:%c)",
      v127 ? 121 : 110,
      v136 != 0 ? 121 : 110);
  }
  if ( (v7 & 0x20) == 0 )
  {
    if ( v122 )
    {
      if ( !(unsigned int)BfspValidateChecksum(v11, 0) )
        goto LABEL_46;
      if ( (unsigned int)BfspValidateChecksum(v12, 0) && !v123 )
        goto LABEL_49;
    }
    else
    {
      if ( !(unsigned int)BfspValidateChecksum(v11, 1) )
      {
LABEL_46:
        LODWORD(v8) = 193;
        BfspLogMessage(4, L"Failed to validate boot manager checksum (%s)! Error code = %#x", v11, 193);
        goto LABEL_202;
      }
      v28 = (const WCHAR *)BfspEnvExpandString(&v124, L"|SYSPART|\\|BOOTMGBIN|");
      v139 = v28;
      if ( !v28 )
        goto LABEL_9;
      if ( (unsigned int)BfspValidateChecksum(v28, 1) )
      {
LABEL_49:
        ShouldFileBeCopied = BfspShouldFileBeCopied(v11);
        goto LABEL_54;
      }
    }
    ShouldFileBeCopied = 1;
    goto LABEL_54;
  }
  ShouldFileBeCopied = 1;
  BfspLogMessage(3, L"Boot manager to be overwritten by user policy.");
LABEL_54:
  v5 = (void *)BfspEnvExpandString(&v124, L"|SOURCE|\\|FWTYPE|");
  if ( v5 )
  {
    if ( v126 )
    {
      lpMem = (LPVOID)BfspEnvExpandString(&v124, L"|SOURCE|\\|FWTYPE|_EX");
      v29 = lpMem;
      if ( !lpMem )
        goto LABEL_9;
    }
    else
    {
      v29 = lpMem;
    }
    v133 = (LPCWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|");
    v30 = v133;
    if ( v133 )
    {
      if ( (unsigned int)Feature_Servicing_BfsvcDeferServicingOnPcr7Incompatibility__private_IsEnabledDeviceUsageNoInline()
        && (v7 & 0x2000) != 0 )
      {
        if ( (int)BfsWillBitLockerResealSucceed(&v128) >= 0 && !v128 && v123 )
          LODWORD(v8) = 50;
        dwCreationDisposition[0] = v8;
        BfspLogMessage(
          2,
          L"FVE Reseal Capability Check: WillResealSucceed = %d HasBootmgfwCertAuthChanged = %d ErrorCode = 0x%08x",
          v128,
          v123,
          *(_QWORD *)dwCreationDisposition);
      }
      if ( (v7 & 0x1000) != 0 )
        goto LABEL_202;
      if ( !v122 )
      {
LABEL_86:
        v41 = L"y";
        if ( !ShouldFileBeCopied )
          v41 = L"n";
        BfspLogMessage(2, L"Copy files which lack a version: %s\t%s -> %s ", v41, v5, v30);
        v42 = v125;
        if ( !(unsigned int)BfspCopyBootFileDirectory(
                              (_DWORD)v5,
                              (_DWORD)v29,
                              (_DWORD)v30,
                              0,
                              ShouldFileBeCopied,
                              v131,
                              v125,
                              1) )
        {
          v43 = GetLastError();
          v44 = L"Error copying boot files from %s to %s! Last Error = %#x";
LABEL_90:
          v45 = (LPVOID)v30;
LABEL_91:
          v46 = v5;
LABEL_92:
          dwCreationDispositiona[0] = v43;
          LODWORD(v8) = v43;
          BfspLogMessage(4, v44, v46, v45, *(_QWORD *)dwCreationDispositiona);
          goto LABEL_202;
        }
        if ( v122 && !(unsigned int)BfspServiceBootStl(v5, v30) )
        {
          v43 = GetLastError();
          v44 = L"Error servcing boot.stl from %s to %s! Last Error = %#x";
          goto LABEL_90;
        }
        v47 = GetProcessHeap();
        if ( HeapFree(v47, 0, v5) )
          v5 = 0;
        if ( v29 )
        {
          v48 = GetProcessHeap();
          if ( HeapFree(v48, 0, v29) )
            v29 = 0;
          lpMem = v29;
        }
        if ( v122 )
        {
          BfspLogMessage(2, L"Creating Recovery directory.");
          v49 = GetProcessHeap();
          LODWORD(v8) = 8;
          v50 = HeapAlloc(v49, 8u, 0x42u);
          v154 = v50;
          if ( !v50 )
            goto LABEL_202;
          *((_WORD *)v50 + 32) = 0;
          *v50 = *(_OWORD *)L"|SYSPART|";
          *((_WORD *)v50 + 8) = aSyspart[8];
          *((_WORD *)v50 + 9) = 92;
          *(_OWORD *)((char *)v50 + 20) = *(_OWORD *)L"EFI\\Microsoft\\Recovery";
          *(_OWORD *)((char *)v50 + 36) = *(_OWORD *)L"osoft\\Recovery";
          v50[3] = *(_OWORD *)L"Recovery";
          v51 = BfspEnvExpandString(&v124, v50);
          v52 = (void *)v51;
          if ( v51 )
          {
            if ( !(unsigned int)CreatePath(v51) )
            {
              v53 = GetLastError();
              BfspLogMessage(3, L"Failed to create Recovery directory. Last error = %#x", v53);
            }
            v54 = GetProcessHeap();
            HeapFree(v54, 0, v52);
          }
          else
          {
            BfspLogMessage(3, L"Failed to expand Recovery directory path");
          }
        }
        else if ( !v42 )
        {
          v6 = (WCHAR *)v139;
          if ( v142 )
          {
            if ( !v139 )
            {
              v139 = (LPCWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|BOOTMGBIN|");
              v6 = (WCHAR *)v139;
              if ( !v139 )
                goto LABEL_9;
            }
            if ( !(unsigned int)BfspSetFileDirectorySecurityDescriptor(v6) && GetLastError() != 2 )
              goto LABEL_9;
          }
          if ( ShouldFileBeCopied && !(unsigned int)BfspCopyFile((__int64)Str, v6) )
            goto LABEL_9;
          v57 = BfspUncompressFile(v6);
          LODWORD(v8) = v57;
          if ( v57 )
          {
            BfspPrintOwnerProcessOnSharingError(v6, v57);
            v24 = (unsigned int)v8;
            v23 = L"Error uncompressing boor manager (%s)! Last Error = %#x";
            goto LABEL_36;
          }
          if ( !(unsigned int)BfspSetAttributes(v6) )
            goto LABEL_9;
          if ( v142 )
          {
            if ( !(unsigned int)BfspSetFileDirectorySecurityDescriptor(v6) )
              goto LABEL_9;
            v6 = pObjectName;
            if ( !(unsigned int)BfspSetFileDirectorySecurityDescriptor(pObjectName) )
              goto LABEL_9;
          }
          else
          {
            v6 = pObjectName;
          }
          if ( !DeleteFileEx2((__int64)v6) )
          {
            v8 = GetLastError();
            BfspPrintOwnerProcessOnSharingError(v6, v8);
            v24 = (unsigned int)v8;
            v23 = L"Error deleting boot manager(%s)! Last Error = %#x";
            goto LABEL_36;
          }
        }
        lpFileName = (LPCWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\BOOTSTAT.DAT");
        FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, (unsigned int)((v7 & 0x80) != 0) + 1, 6u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          if ( GetLastError() != 80 || (v7 & 0x80) != 0 )
          {
            v58 = GetLastError();
            v56 = lpFileName;
            BfspLogMessage(3, L"Error creating boot status data log(%s)! Last Error = %#x", lpFileName, v58);
          }
          else
          {
            v56 = lpFileName;
            BfspBsdLogServicingEvent(lpFileName);
          }
        }
        else
        {
          v59 = GetProcessHeap();
          v60 = HeapAlloc(v59, 8u, 0x10000u);
          v61 = v60;
          if ( v60 )
          {
            memset_0(v60, 0, 0x10000u);
            if ( WriteFile(FileW, v61, 0x10000u, &NumberOfBytesWritten, 0) )
            {
              if ( NumberOfBytesWritten != 0x10000 )
                BfspLogMessage(
                  3,
                  L"Error creating boot status data log(%s)! Bytes written = %#x, desired = %#x",
                  lpFileName);
            }
            else
            {
              v62 = GetLastError();
              BfspLogMessage(3, L"Error creating boot status data log(%s)! Last Error = %#x", lpFileName, v62);
            }
            v63 = GetProcessHeap();
            HeapFree(v63, 0, v61);
          }
          else
          {
            BfspLogMessage(3, L"Error creating boot status data log(%s)! Unable to allocate memory", lpFileName);
          }
          NtClose(FileW);
          v56 = lpFileName;
          v64 = BfspUncompressFile(lpFileName);
          if ( v64 )
            BfspLogMessage(3, L"Error uncompressing boot status data log(%s)! Last Error = %#x", v56, v64);
        }
        v65 = v142;
        if ( !v122 )
        {
          if ( v142 && !(unsigned int)BfspSetFileDirectorySecurityDescriptor((LPWSTR)v133) )
            goto LABEL_9;
          if ( !v125 )
          {
            v149 = (LPCWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\BCD");
            v143 = (LPCWSTR)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\BCD.LOG");
            if ( !(unsigned int)BfspSetAttributes(v149) && GetLastError() != 2 )
              goto LABEL_9;
            if ( !(unsigned int)BfspSetAttributes(v143) && GetLastError() != 2
              || !(unsigned int)BfspSetAttributes(v56) && GetLastError() != 2 )
            {
              goto LABEL_9;
            }
          }
        }
        if ( (v7 & 8) != 0 )
        {
          v5 = (void *)BfspEnvExpandString(&v124, L"|SOURCE|\\|FONTS|");
          if ( !v5 )
            goto LABEL_9;
          if ( v126 )
          {
            lpMem = (LPVOID)BfspEnvExpandString(&v124, L"|SOURCE|\\|FONTS|_EX");
            v29 = lpMem;
            if ( !lpMem )
              goto LABEL_9;
          }
          v66 = (void *)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\|FONTS|");
          v138 = v66;
          if ( !v66 )
            goto LABEL_9;
          BfspLogMessage(2, L"Copying font files from %s to %s...", v5, v66);
          v67 = v125;
          if ( !(unsigned int)BfspCopyBootFileDirectory(
                                (_DWORD)v5,
                                (_DWORD)v29,
                                (_DWORD)v138,
                                0,
                                ShouldFileBeCopied,
                                v131,
                                v125,
                                1) )
          {
            v43 = GetLastError();
            v45 = v138;
            v44 = L"Error copying font files from %s to %s.Last Error = %#x";
            goto LABEL_91;
          }
          v68 = GetProcessHeap();
          if ( HeapFree(v68, 0, v5) )
            v5 = 0;
          if ( v29 )
          {
            v69 = GetProcessHeap();
            if ( HeapFree(v69, 0, v29) )
              v29 = 0;
            lpMem = v29;
          }
        }
        else
        {
          v67 = v125;
        }
        if ( (v7 & 4) != 0 )
        {
          v5 = (void *)BfspEnvExpandString(&v124, L"|SOURCE|\\|RESOURCES|");
          if ( !v5 )
            goto LABEL_9;
          v70 = (void *)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\|RESOURCES|");
          v138 = v70;
          v71 = (int)v70;
          if ( !v70 )
            goto LABEL_9;
          BfspLogMessage(2, L"Copying resource files from %s to %s...", v5, v70);
          if ( !(unsigned int)BfspCopyBootFileDirectory((_DWORD)v5, 0, v71, 0, ShouldFileBeCopied, v131, v67, 1) )
          {
            BfspLogMessage(
              3,
              L"Resource files missing from %s. These files are required for some editions of Windows. If you are servicin"
               "g older versions of Windows, you can ignore this message.",
              v5);
            SetLastError(0);
          }
          v72 = GetProcessHeap();
          if ( HeapFree(v72, 0, v5) )
            v5 = 0;
        }
        if ( !v122 )
        {
          v73 = (WCHAR *)v133;
          if ( !(unsigned int)BfspSetAttributes(v133)
            || v65 && !(unsigned int)BfspSetFileDirectorySecurityDescriptor(v73) )
          {
            goto LABEL_9;
          }
          v74 = (void *)BfspEnvExpandString(&v124, L"|SYSPART|\\|DEST|\\BOOTNXT");
          v153 = v74;
          v75 = (__int64)v74;
          if ( !v74 )
          {
            v76 = GetLastError();
            v77 = L"|SYSPART|\\|DEST|\\BOOTNXT";
LABEL_178:
            LODWORD(v8) = v76;
            BfspLogMessage(4, L"Error expanding string %s. Last Error = %#x", v77, v76);
            goto LABEL_202;
          }
          if ( (unsigned int)BfspFileExists(v74) )
          {
            v151 = (LPVOID)BfspEnvExpandString(&v124, L"|SYSPART|\\BOOTNXT");
            v6 = (WCHAR *)v151;
            if ( !v151 )
            {
              v76 = GetLastError();
              v77 = L"|SYSPART|\\BOOTNXT";
              goto LABEL_178;
            }
            v78 = (void *)BfspEnvExpandString(&v124, L"|SYSPART|\\BOOTTGT");
            v152 = v78;
            v79 = (__int64)v78;
            if ( !v78 )
            {
              v76 = GetLastError();
              v77 = L"|SYSPART|\\BOOTTGT";
              goto LABEL_178;
            }
            if ( (unsigned int)BfspFileExists(v78) && !DeleteFileEx2(v79) )
            {
              v8 = GetLastError();
              BfspLogMessage(4, L"Error deleting boottgt(%s)! Last Error = %#x", v79, v8);
              goto LABEL_202;
            }
            if ( !(unsigned int)BfspCopyFile(v75, v6) )
            {
              v43 = GetLastError();
              v45 = v6;
              v44 = L"Error copying %s to %s. Last Error = %#x";
              v46 = (void *)v75;
              goto LABEL_92;
            }
            if ( !DeleteFileEx2(v75) )
            {
              v8 = GetLastError();
              BfspLogMessage(4, L"Error deleting bootnxt from the BOOT folder (%s)! Last Error = %#x", v75, v8);
              goto LABEL_202;
            }
            if ( !(unsigned int)BfspSetAttributes(v6) )
            {
              LastError = GetLastError();
              v23 = L"Error setting attributes on %s. Last Error = %#x";
              goto LABEL_35;
            }
            if ( v65
              && !(unsigned int)BfspSetSecurityDescriptor(
                                  v6,
                                  L"O:SYG:SYD:P(A;ID;FA;;;SY)(A;ID;FA;;;BA)(A;ID;0x1200a9;;;BU)") )
            {
              LastError = GetLastError();
              v23 = L"Error setting security attributes on %s. Last Error = %#x";
              goto LABEL_35;
            }
          }
        }
        if ( ((v7 & 0x100) == 0 || (unsigned int)BfspServiceDebuggerFiles(&v124))
          && (unsigned int)BfspServiceSpaces(&v124) )
        {
          v80 = BfspFlushSystemPartition();
          if ( v80 )
            BfspLogMessage(3, L"Failed to flush system volume. Error = %#x", v80);
          LODWORD(v8) = 0;
          goto LABEL_202;
        }
        goto LABEL_9;
      }
      v31 = (void *)BfspEnvExpandString(&v124, L"|SYSPART|\\|EFIDEFAULTDIR|");
      v32 = BfspEnvExpandString(&v124, L"|SYSPART|\\|EFIDEFAULTDIR|\\|DEFAULTAPP|");
      v33 = (WCHAR *)v32;
      if ( v31 && v32 )
      {
        v34 = BfspFileExists(v32);
        IsWindowsBinary = BfspIsWindowsBinary(v33, L"bootmgr.exe", 2);
        if ( v34 )
        {
          if ( !IsWindowsBinary )
          {
            BfspLogMessage(3, L"Default EFI application is not Windows boot manager, will not update.");
            goto LABEL_82;
          }
          v36 = Str;
          if ( !(unsigned int)BfspShouldFileBeCopied(Str) )
          {
            BfspLogMessage(3, L"Bootmgfw on ESP is newer than that in source, will not update Default EFI application.");
            goto LABEL_82;
          }
        }
        else
        {
          v36 = Str;
        }
        if ( (unsigned int)CreatePath(v31) )
        {
          BfspLogMessage(2, L"Updating %s", v33);
          if ( !(unsigned int)BfspCopyFile((__int64)v36, v33) )
          {
            v38 = GetLastError();
            BfspLogMessage(3, L"Failed to copy Boot Manager to default EFI application. Last error = %#x", v38);
          }
        }
        else
        {
          v37 = GetLastError();
          BfspLogMessage(3, L"Failed to create path for default EFI application. Last error = %#x", v37);
        }
        goto LABEL_82;
      }
      BfspLogMessage(3, L"Failed to expand default EFI application location.");
      if ( !v31 )
      {
LABEL_83:
        if ( v33 )
        {
          v40 = GetProcessHeap();
          HeapFree(v40, 0, v33);
        }
        v30 = v133;
        LOWORD(v7) = v129;
        goto LABEL_86;
      }
LABEL_82:
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v31);
      goto LABEL_83;
    }
  }
LABEL_9:
  LODWORD(v8) = GetLastError();
LABEL_202:
  BfspEnvDestory(&v124);
LABEL_203:
  if ( (_DWORD)v8 )
  {
    BfspLogMessage(4, L"ServicingBootFiles failed. Error = %#x", (unsigned int)v8);
  }
  else if ( v148 )
  {
    v81 = v123;
    *(_DWORD *)v148 = v123;
    goto LABEL_206;
  }
  v81 = v123;
LABEL_206:
  if ( (unsigned int)Feature_Servicing_BFSVCTelemetry__private_IsEnabledDeviceUsageNoInline()
    && v122
    && (int)RegisterBfsTelemetryProvider() >= 0 )
  {
    if ( (unsigned int)dword_1800A3188 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800A3188, 0x800000000000LL) )
    {
      v148 = 0x1000000;
      v156 = &v148;
      v157 = 8;
      v158 = &v129;
      v128 = v126;
      v129 = v8;
      v160 = &v128;
      v162 = &v127;
      v159 = 4;
      v161 = 4;
      v127 = v81;
      v163 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800A3188, byte_18009584D, 0, 0, 6, v155);
    }
    UnregisterBfsTelemetryProvider();
  }
  BfspLogDestroy();
  if ( v144 )
    BfspAdjustTokenPrivileges(v144);
  if ( v5 )
  {
    v82 = GetProcessHeap();
    HeapFree(v82, 0, v5);
  }
  v83 = lpMem;
  if ( lpMem )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, v83);
  }
  v85 = v138;
  if ( v138 )
  {
    v86 = GetProcessHeap();
    HeapFree(v86, 0, v85);
  }
  v87 = (WCHAR *)v133;
  if ( v133 )
  {
    v88 = GetProcessHeap();
    HeapFree(v88, 0, v87);
  }
  v89 = v140;
  if ( v140 )
  {
    v90 = GetProcessHeap();
    HeapFree(v90, 0, v89);
  }
  v91 = pObjectName;
  if ( pObjectName )
  {
    v92 = GetProcessHeap();
    HeapFree(v92, 0, v91);
  }
  v93 = Str;
  if ( Str )
  {
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v93);
  }
  v95 = (WCHAR *)v139;
  if ( v139 )
  {
    v96 = GetProcessHeap();
    HeapFree(v96, 0, v95);
  }
  v97 = v151;
  if ( v151 )
  {
    v98 = GetProcessHeap();
    HeapFree(v98, 0, v97);
  }
  v99 = v152;
  if ( v152 )
  {
    v100 = GetProcessHeap();
    HeapFree(v100, 0, v99);
  }
  v101 = v153;
  if ( v153 )
  {
    v102 = GetProcessHeap();
    HeapFree(v102, 0, v101);
  }
  v103 = (WCHAR *)v149;
  if ( v149 )
  {
    v104 = GetProcessHeap();
    HeapFree(v104, 0, v103);
  }
  v105 = (WCHAR *)v143;
  if ( v143 )
  {
    v106 = GetProcessHeap();
    HeapFree(v106, 0, v105);
  }
  v107 = (WCHAR *)lpFileName;
  if ( lpFileName )
  {
    v108 = GetProcessHeap();
    HeapFree(v108, 0, v107);
  }
  v109 = v144;
  if ( v144 )
  {
    v110 = GetProcessHeap();
    HeapFree(v110, 0, v109);
  }
  v111 = NewState;
  if ( NewState )
  {
    v112 = GetProcessHeap();
    HeapFree(v112, 0, v111);
  }
  v113 = v146;
  if ( v146 )
  {
    v114 = GetProcessHeap();
    HeapFree(v114, 0, v113);
  }
  v115 = v147;
  if ( v147 )
  {
    v116 = GetProcessHeap();
    HeapFree(v116, 0, v115);
  }
  v117 = v154;
  if ( v154 )
  {
    v118 = GetProcessHeap();
    HeapFree(v118, 0, v117);
  }
  if ( (_DWORD)v8 )
  {
    SetLastError(v8);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180049234  mov     [rsp-8+arg_10], rbx
0x180049239  push    rbp
0x18004923a  push    rsi
0x18004923b  push    rdi
0x18004923c  push    r12
0x18004923e  push    r13
0x180049240  push    r14
0x180049242  push    r15
0x180049244  lea     rbp, [rsp-0D0h]
0x18004924c  sub     rsp, 1D0h
0x180049253  mov     rax, cs:__security_cookie
0x18004925a  xor     rax, rsp
0x18004925d  mov     [rbp+100h+var_40], rax
0x180049264  xor     edi, edi
0x180049266  mov     [rbp+100h+var_D8], r9
0x18004926a  mov     eax, edi
0x18004926c  mov     [rbp+100h+lpszFileName], rcx
0x180049270  xorps   xmm0, xmm0
0x180049273  mov     [rbp+100h+var_170], edi
0x180049276  mov     r13d, edx
0x180049279  mov     [rbp+100h+var_134], edi
0x18004927c  lea     ebx, [rdi+1]
0x18004927f  mov     [rbp+100h+NumberOfBytesWritten], edi
0x180049282  mov     [rsp+200h+var_190], ebx
0x180049286  mov     r12d, edi
0x180049289  movups  [rsp+200h+var_188], xmm0
0x18004928e  mov     [rbp+100h+pObjectName], rdi
0x180049292  mov     [rbp+100h+Str], rdi
0x180049296  mov     [rbp+100h+var_B0], rdi
0x18004929a  mov     [rbp+100h+lpFileName], rdi
0x18004929e  mov     [rbp+100h+var_148], rdi
0x1800492a2  mov     [rbp+100h+var_118], rdi
0x1800492a6  mov     [rbp+100h+var_128], rdi
0x1800492aa  mov     [rbp+100h+var_120], rdi
0x1800492ae  mov     [rbp+100h+var_C0], rdi
0x1800492b2  mov     [rbp+100h+var_B8], rdi
0x1800492b6  mov     [rsp+200h+var_18C], edi
0x1800492ba  mov     [rbp+100h+NewState], rdi
0x1800492be  mov     [rbp+100h+var_F8], rdi
0x1800492c2  mov     [rbp+100h+var_A8], rdi
0x1800492c6  mov     [rbp+100h+var_E8], rdi
0x1800492ca  mov     [rbp+100h+lpMem], rdi
0x1800492ce  mov     [rbp+100h+var_E0], rdi
0x1800492d2  mov     [rbp+100h+var_D0], rdi
0x1800492d6  mov     [rbp+100h+var_100], rdi
0x1800492da  mov     [rbp+100h+var_174], eax
0x1800492dd  mov     [rbp+100h+var_138], eax
0x1800492e0  mov     [rbp+100h+var_16C], edi
0x1800492e3  call    Feature_UseExDefault__private_IsEnabledDeviceUsageNoInline
0x1800492e8  mov     esi, 800h
0x1800492ed  test    eax, eax
0x1800492ef  jz      short loc_1800492FB
0x1800492f1  test    esi, r13d
0x1800492f4  jnz     short loc_1800492FB
0x1800492f6  bts     r13d, 0Ah
0x1800492fb  mov     ecx, r13d
0x1800492fe  call    BfspLogInitializeFromFlags
0x180049303  mov     r9d, 0Bh
0x180049309  mov     r8d, r13d
0x18004930c  and     r8d, ebx
0x18004930f  mov     eax, r13d
0x180049312  and     eax, 2000h
0x180049317  mov     [rbp+100h+var_178], r8d
0x18004931b  neg     eax
0x18004931d  lea     ecx, [r9+63h]
0x180049321  mov     eax, r13d
0x180049324  sbb     r15d, r15d
0x180049327  and     eax, 1000h
0x18004932c  and     r15d, r9d
0x18004932f  add     r15d, ecx
0x180049332  neg     eax
0x180049334  mov     [rsp+200h+var_1A0], r15d
0x180049339  mov     eax, r13d
0x18004933c  sbb     r14d, r14d
0x18004933f  and     eax, esi
0x180049341  and     r14d, r9d
0x180049344  add     r14d, ecx
0x180049347  neg     eax
0x180049349  mov     [rsp+200h+var_1A8], r14d
0x18004934e  mov     eax, r13d
0x180049351  sbb     esi, esi
0x180049353  and     eax, 400h
0x180049358  and     esi, r9d
0x18004935b  add     esi, ecx
0x18004935d  neg     eax
0x18004935f  mov     [rsp+200h+var_1B0], esi
0x180049363  mov     eax, r13d
0x180049366  sbb     edi, edi
0x180049368  and     eax, 200h
0x18004936d  and     edi, r9d
0x180049370  add     edi, ecx
0x180049372  neg     eax
0x180049374  mov     [rsp+200h+var_1B8], edi
0x180049378  mov     eax, r13d
0x18004937b  sbb     ebx, ebx
0x18004937d  and     eax, 100h
0x180049382  and     ebx, r9d
0x180049385  add     ebx, ecx
0x180049387  neg     eax
0x180049389  mov     [rsp+200h+var_1C0], ebx
0x18004938d  mov     eax, r13d
0x180049390  sbb     r11d, r11d
0x180049393  and     al, 80h
0x180049395  and     r11d, r9d
0x180049398  add     r11d, ecx
0x18004939b  neg     al
0x18004939d  mov     [rsp+200h+var_1C8], r11d
0x1800493a2  mov     eax, r13d
0x1800493a5  sbb     r10d, r10d
0x1800493a8  and     al, 20h
0x1800493aa  and     r10d, r9d
0x1800493ad  add     r10d, ecx
0x1800493b0  neg     al
0x1800493b2  mov     dword ptr [rsp+200h+hTemplateFile], r10d
0x1800493b7  mov     eax, r13d
0x1800493ba  sbb     edx, edx
0x1800493bc  and     al, 8
0x1800493be  and     edx, r9d
0x1800493c1  add     edx, ecx
0x1800493c3  neg     al
0x1800493c5  mov     [rsp+200h+dwFlagsAndAttributes], edx
0x1800493c9  mov     eax, r13d
0x1800493cc  sbb     ecx, ecx
0x1800493ce  and     al, 4
0x1800493d0  and     ecx, r9d
0x1800493d3  add     ecx, 6Eh ; 'n'
0x1800493d6  neg     al
0x1800493d8  mov     [rsp+200h+dwCreationDisposition], ecx
0x1800493dc  mov     eax, r8d
0x1800493df  sbb     r9d, r9d
0x1800493e2  and     r9d, 0Bh
0x1800493e6  add     r9d, 6Eh ; 'n'
0x1800493ea  neg     eax
0x1800493ec  sbb     r8d, r8d
0x1800493ef  and     r8d, 0Bh
0x1800493f3  add     r8d, 6Eh ; 'n'
0x1800493f7  lea     rdx, aServicebootfil; "ServiceBootFiles MuiOnly:%c Res:%c Font"...
0x1800493fe  mov     ecx, 2
0x180049403  call    BfspLogMessage
0x180049408  mov     rdi, [rbp+100h+lpszFileName]
0x18004940c  lea     r8, [rsp+200h+var_188]
0x180049411  mov     esi, r13d
0x180049414  mov     rcx, rdi; unsigned __int16 *
0x180049417  and     esi, 0FFFFFEF3h
0x18004941d  cmp     [rbp+100h+var_178], r12d
0x180049421  cmovz   esi, r13d
0x180049425  mov     [rbp+100h+var_168], esi
0x180049428  call    BfspCreateEnvironment
0x18004942d  test    eax, eax
0x18004942f  jnz     short loc_180049444
0x180049431  call    cs:__imp_GetLastError
0x180049437  mov     ebx, eax
0x180049439  mov     r13d, 1
0x18004943f  jmp     loc_18004A2D4
0x180049444  mov     r13d, 1
0x18004944a  lea     r9, [rbp+100h+NewState]
0x18004944e  mov     r8d, r13d
0x180049451  lea     rcx, BfspPrivilegeNames
0x180049458  lea     ebx, [r13+3]
0x18004945c  mov     edx, ebx
0x18004945e  call    BfspCreateTokenPrivilegesInformation
0x180049463  test    eax, eax
0x180049465  jnz     short loc_180049474
0x180049467  call    cs:__imp_GetLastError
0x18004946d  mov     ebx, eax
0x18004946f  jmp     loc_18004A2CA
0x180049474  mov     rcx, [rbp+100h+NewState]; NewState
0x180049478  lea     rdx, [rbp+100h+var_F8]
0x18004947c  call    BfspAdjustTokenPrivileges
0x180049481  test    eax, eax
0x180049483  jz      short loc_180049467
0x180049485  lea     rdx, aFwtype; "FWTYPE"
0x18004948c  lea     rcx, [rsp+200h+var_188]
0x180049491  call    BfspEnvGetValue
0x180049496  mov     rcx, rax; String1
0x180049499  lea     rdx, aEfi; "EFI"
0x1800494a0  mov     r8d, ebx; MaxCount
0x1800494a3  call    wcsncmp_0
0x1800494a8  test    eax, eax
0x1800494aa  jz      short loc_1800494B3
0x1800494ac  mov     [rsp+200h+var_190], r12d
0x1800494b1  jmp     short loc_1800494BE
0x1800494b3  bt      esi, 0Bh
0x1800494b7  jb      short loc_1800494BE
0x1800494b9  call    BfspDeleteBootmgfwForceSha1Variable
0x1800494be  lea     rdx, aAcls; "ACLS"
0x1800494c5  lea     rcx, [rsp+200h+var_188]
0x1800494ca  call    BfspEnvGetValue
0x1800494cf  xor     ecx, ecx
0x1800494d1  mov     [rbp+100h+var_108], rax
0x1800494d5  test    rax, rax
0x1800494d8  lea     rdx, aSourceFwtypeBo; "|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|"
0x1800494df  setnz   cl
0x1800494e2  mov     [rbp+100h+var_158], ecx
0x1800494e5  lea     rcx, [rsp+200h+var_188]
0x1800494ea  call    BfspEnvExpandString
0x1800494ef  mov     [rbp+100h+Str], rax
0x1800494f3  mov     r14, rax
0x1800494f6  test    rax, rax
0x1800494f9  jz      loc_180049467
0x1800494ff  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x180049506  lea     rcx, [rsp+200h+var_188]
0x18004950b  call    BfspEnvExpandString
0x180049510  mov     [rbp+100h+pObjectName], rax
0x180049514  mov     r15, rax
0x180049517  test    rax, rax
0x18004951a  jz      loc_180049467
0x180049520  xor     ebx, ebx
0x180049522  call    Feature_Servicing_BFSVCExFiles__private_IsEnabledDeviceUsageNoInline
0x180049527  test    eax, eax
0x180049529  jz      loc_18004961B
0x18004952f  cmp     [rsp+200h+var_190], ebx
0x180049533  jz      loc_18004961B
0x180049539  lea     r9, [rbp+100h+var_138]
0x18004953d  mov     rdx, r15
0x180049540  lea     r8, [rbp+100h+var_118]
0x180049544  mov     ecx, esi
0x180049546  call    BfspShouldUseExFiles
0x18004954b  mov     ebx, eax
0x18004954d  test    eax, eax
0x18004954f  jz      short loc_18004956B
0x180049551  mov     r8d, eax
0x180049554  lea     rdx, aShoulduseexfil; "ShouldUseExFiles check failed: %x, defa"...
0x18004955b  mov     ecx, 4
0x180049560  call    BfspLogMessage
0x180049565  xor     eax, eax
0x180049567  xor     ebx, ebx
0x180049569  jmp     short loc_18004956E
0x18004956b  mov     eax, [rbp+100h+var_138]
0x18004956e  mov     [rbp+100h+var_174], eax
0x180049571  test    eax, eax
0x180049573  jz      short loc_1800495AA
0x180049575  call    cs:__imp_GetProcessHeap
0x18004957b  mov     r8, r14; lpMem
0x18004957e  xor     edx, edx; dwFlags
0x180049580  mov     rcx, rax; hHeap
0x180049583  call    cs:__imp_HeapFree
0x180049589  lea     rdx, aSourceFwtypeEx_0; "|SOURCE|\\|FWTYPE|_EX\\|BOOTMGBINEX|"
0x180049590  lea     rcx, [rsp+200h+var_188]
0x180049595  call    BfspEnvExpandString
0x18004959a  mov     [rbp+100h+Str], rax
0x18004959e  mov     r14, rax
0x1800495a1  test    rax, rax
0x1800495a4  jz      loc_180049467
0x1800495aa  cmp     [rbp+100h+var_118], r12
0x1800495ae  jz      short loc_18004961B
0x1800495b0  lea     rdx, [rbp+100h+var_E8]
0x1800495b4  mov     rcx, r14
0x1800495b7  call    BfspCheckFileCertAuthority
0x1800495bc  mov     ebx, eax
0x1800495be  test    eax, eax
0x1800495c0  jnz     loc_18004A2CA
0x1800495c6  mov     rax, [rbp+100h+var_118]
0x1800495ca  mov     rdx, [rbp+100h+var_E8]
0x1800495ce  sub     rdx, rax
0x1800495d1  movzx   ecx, word ptr [rax]
0x1800495d4  cmp     cx, [rax+rdx]
0x1800495d8  jnz     short loc_1800495E7
0x1800495da  add     rax, 2
0x1800495de  test    cx, cx
0x1800495e1  jnz     short loc_1800495D1
0x1800495e3  xor     edi, edi
0x1800495e5  jmp     short loc_1800495EC
0x1800495e7  sbb     edi, edi
0x1800495e9  or      edi, r13d
0x1800495ec  mov     eax, edi
0x1800495ee  lea     rdx, aBootmgfwCertCh; "Bootmgfw cert changed: %c"
0x1800495f5  neg     eax
0x1800495f7  mov     ecx, 2
0x1800495fc  sbb     r8d, r8d
0x1800495ff  and     r8d, 0Bh
0x180049603  add     r8d, 6Eh ; 'n'
0x180049607  call    BfspLogMessage
0x18004960c  xor     eax, eax
0x18004960e  test    edi, edi
0x180049610  mov     rdi, [rbp+100h+lpszFileName]
0x180049614  setnz   al
0x180049617  mov     [rsp+200h+var_18C], eax
0x18004961b  lea     rcx, [rsp+200h+var_188]
0x180049620  call    BfspSetSourceOsVersion
0x180049625  bt      esi, 9
0x180049629  jnb     loc_1800496EC
0x18004962f  mov     rcx, rdi; lpszFileName
0x180049632  call    BfsGetVolumeName
0x180049637  mov     [rbp+100h+var_E0], rax
0x18004963b  test    rax, rax
0x18004963e  jnz     short loc_180049664
0x180049640  call    cs:__imp_GetLastError
0x180049646  lea     rdx, aFailedToGetVol; "Failed to get VolumeName for %ws %x"
0x18004964d  mov     ebx, eax
0x18004964f  mov     r9d, eax
0x180049652  mov     r8, rdi
0x180049655  mov     ecx, 4
0x18004965a  call    BfspLogMessage
0x18004965f  jmp     loc_18004A2CA
0x180049664  mov     r8, rax
0x180049667  lea     rdx, aSourceVolumena; "Source VolumeName %ws"
0x18004966e  mov     ecx, 2
0x180049673  call    BfspLogMessage
0x180049678  mov     rcx, [rbp+100h+var_E0]
  ... truncated ...
```
