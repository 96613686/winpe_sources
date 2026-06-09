# InitializeUninstallVolume_GetAccessPaths

- ea: `0x14001e720`
- end: `0x14001e800`
- name: `InitializeUninstallVolume_GetAccessPaths`
- size: `224`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001e464`

## callees

- `0x14001e720`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001e758`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001e7b7`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001e758`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001e7b7`
- `KERNEL32!HeapAlloc` at `0x14001e784`
- `KERNEL32!HeapAlloc` at `0x14001e784`
- `KERNEL32!HeapFree` at `0x14001e7d8`
- `KERNEL32!HeapFree` at `0x14001e7d8`
- `KERNEL32!GetProcessHeap` at `0x14001e740`
- `KERNEL32!GetProcessHeap` at `0x14001e740`
- `KERNEL32!SetLastError` at `0x14001e797`
- `KERNEL32!SetLastError` at `0x14001e7e5`
- `KERNEL32!SetLastError` at `0x14001e797`
- `KERNEL32!SetLastError` at `0x14001e7e5`
- `KERNEL32!GetLastError` at `0x14001e764`
- `KERNEL32!GetLastError` at `0x14001e79d`
- `KERNEL32!GetLastError` at `0x14001e7bf`
- `KERNEL32!GetLastError` at `0x14001e764`
- `KERNEL32!GetLastError` at `0x14001e79d`
- `KERNEL32!GetLastError` at `0x14001e7bf`

## pseudocode

```c
__int64 __fastcall InitializeUninstallVolume_GetAccessPaths(LPCWSTR lpszVolumeName, WCHAR **a2)
{
  HANDLE ProcessHeap; // rbp
  WCHAR *v5; // rsi
  unsigned int VolumePathNamesForVolumeNameW; // ebx
  WCHAR *v7; // rax
  DWORD LastError; // edi
  DWORD cchReturnLength; // [rsp+50h] [rbp+18h] BYREF

  cchReturnLength = 0;
  ProcessHeap = GetProcessHeap();
  v5 = 0;
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength);
  if ( (VolumePathNamesForVolumeNameW || GetLastError() == 234) && cchReturnLength )
  {
    v7 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * cchReturnLength);
    v5 = v7;
    if ( !v7 )
    {
      VolumePathNamesForVolumeNameW = 0;
      SetLastError(8u);
      LastError = GetLastError();
LABEL_10:
      v5 = 0;
      goto LABEL_11;
    }
    VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                      lpszVolumeName,
                                      v7,
                                      cchReturnLength,
                                      &cchReturnLength);
  }
  LastError = GetLastError();
  if ( !VolumePathNamesForVolumeNameW )
  {
    if ( v5 )
      HeapFree(ProcessHeap, 0, v5);
    goto LABEL_10;
  }
LABEL_11:
  *a2 = v5;
  SetLastError(LastError);
  return VolumePathNamesForVolumeNameW;
}

```

## disassembly

```asm
0x14001e720  mov     [rsp+arg_0], rbx
0x14001e725  mov     [rsp+arg_8], rbp
0x14001e72a  push    rsi
0x14001e72b  push    rdi
0x14001e72c  push    r14
0x14001e72e  sub     rsp, 20h
0x14001e732  mov     r14, rdx
0x14001e735  mov     [rsp+38h+cchReturnLength], 0
0x14001e73d  mov     rdi, rcx
0x14001e740  call    cs:__imp_GetProcessHeap
0x14001e746  lea     r9, [rsp+38h+cchReturnLength]; lpcchReturnLength
0x14001e74b  xor     r8d, r8d; cchBufferLength
0x14001e74e  xor     edx, edx; lpszVolumePathNames
0x14001e750  mov     rcx, rdi; lpszVolumeName
0x14001e753  mov     rbp, rax
0x14001e756  xor     esi, esi
0x14001e758  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14001e75e  mov     ebx, eax
0x14001e760  test    eax, eax
0x14001e762  jnz     short loc_14001E771
0x14001e764  call    cs:__imp_GetLastError
0x14001e76a  cmp     eax, 0EAh
0x14001e76f  jnz     short loc_14001E7BF
0x14001e771  mov     eax, [rsp+38h+cchReturnLength]
0x14001e775  test    eax, eax
0x14001e777  jz      short loc_14001E7BF
0x14001e779  mov     r8d, eax
0x14001e77c  xor     edx, edx; dwFlags
0x14001e77e  add     r8, r8; dwBytes
0x14001e781  mov     rcx, rbp; hHeap
0x14001e784  call    cs:__imp_HeapAlloc
0x14001e78a  mov     rsi, rax
0x14001e78d  test    rax, rax
0x14001e790  jnz     short loc_14001E7A7
0x14001e792  lea     ecx, [rax+8]; dwErrCode
0x14001e795  xor     ebx, ebx
0x14001e797  call    cs:__imp_SetLastError
0x14001e79d  call    cs:__imp_GetLastError
0x14001e7a3  mov     edi, eax
0x14001e7a5  jmp     short loc_14001E7DE
0x14001e7a7  mov     r8d, [rsp+38h+cchReturnLength]; cchBufferLength
0x14001e7ac  lea     r9, [rsp+38h+cchReturnLength]; lpcchReturnLength
0x14001e7b1  mov     rdx, rax; lpszVolumePathNames
0x14001e7b4  mov     rcx, rdi; lpszVolumeName
0x14001e7b7  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14001e7bd  mov     ebx, eax
0x14001e7bf  call    cs:__imp_GetLastError
0x14001e7c5  mov     edi, eax
0x14001e7c7  test    ebx, ebx
0x14001e7c9  jnz     short loc_14001E7E0
0x14001e7cb  test    rsi, rsi
0x14001e7ce  jz      short loc_14001E7DE
0x14001e7d0  mov     r8, rsi; lpMem
0x14001e7d3  xor     edx, edx; dwFlags
0x14001e7d5  mov     rcx, rbp; hHeap
0x14001e7d8  call    cs:__imp_HeapFree
0x14001e7de  xor     esi, esi
0x14001e7e0  mov     ecx, edi; dwErrCode
0x14001e7e2  mov     [r14], rsi
0x14001e7e5  call    cs:__imp_SetLastError
0x14001e7eb  mov     rbp, [rsp+38h+arg_8]
0x14001e7f0  mov     eax, ebx
0x14001e7f2  mov     rbx, [rsp+38h+arg_0]
0x14001e7f7  add     rsp, 20h
0x14001e7fb  pop     r14
0x14001e7fd  pop     rdi
0x14001e7fe  pop     rsi
0x14001e7ff  retn
```
