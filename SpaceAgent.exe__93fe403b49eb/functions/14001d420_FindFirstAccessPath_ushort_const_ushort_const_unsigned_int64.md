# FindFirstAccessPath(ushort const *,ushort const * *,unsigned __int64 *)

- ea: `0x14001d420`
- end: `0x14001d578`
- name: `?FindFirstAccessPath@@YAPEAXPEBGPEAPEBGPEA_K@Z`
- size: `344`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001cde8`

## callees

- `0x14001d140`
- `0x14001d420`
- `0x14001d580`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001d487`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001d4e9`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001d487`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14001d4e9`
- `KERNEL32!HeapAlloc` at `0x14001d4b2`
- `KERNEL32!HeapAlloc` at `0x14001d4b2`
- `KERNEL32!HeapFree` at `0x14001d529`
- `KERNEL32!HeapFree` at `0x14001d529`
- `KERNEL32!GetProcessHeap` at `0x14001d456`
- `KERNEL32!GetProcessHeap` at `0x14001d456`
- `KERNEL32!SetLastError` at `0x14001d4c3`
- `KERNEL32!SetLastError` at `0x14001d548`
- `KERNEL32!SetLastError` at `0x14001d4c3`
- `KERNEL32!SetLastError` at `0x14001d548`
- `KERNEL32!GetLastError` at `0x14001d493`
- `KERNEL32!GetLastError` at `0x14001d4c9`
- `KERNEL32!GetLastError` at `0x14001d510`
- `KERNEL32!GetLastError` at `0x14001d493`
- `KERNEL32!GetLastError` at `0x14001d4c9`
- `KERNEL32!GetLastError` at `0x14001d510`

## pseudocode

```c
__int64 __fastcall FindFirstAccessPath(const unsigned __int16 *a1, const unsigned __int16 **a2, unsigned __int64 *a3)
{
  HANDLE ProcessHeap; // rbp
  __int64 v7; // rdi
  int VolumePathNamesForVolumeNameW; // esi
  WCHAR *v9; // rax
  DWORD LastError; // ebx
  char *v11; // rbx
  DWORD cchReturnLength[4]; // [rsp+20h] [rbp-B8h] BYREF
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-A8h] BYREF

  cchReturnLength[0] = 0;
  ProcessHeap = GetProcessHeap();
  v7 = 0;
  VolumePathNamesForVolumeNameW = CopyFilesystemRootFromVolumeIdentifier(a1, szVolumeName);
  if ( VolumePathNamesForVolumeNameW )
  {
    VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, cchReturnLength);
    if ( VolumePathNamesForVolumeNameW || GetLastError() == 234 )
    {
      v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * cchReturnLength[0] + 16);
      v7 = (__int64)v9;
      if ( !v9 )
      {
        SetLastError(8u);
        LastError = GetLastError();
        goto LABEL_11;
      }
      v11 = (char *)(v9 + 8);
      VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                        szVolumeName,
                                        v9 + 8,
                                        cchReturnLength[0],
                                        cchReturnLength);
      if ( VolumePathNamesForVolumeNameW )
      {
        *(_QWORD *)v7 = cchReturnLength[0];
        *(_QWORD *)(v7 + 8) = v11;
        VolumePathNamesForVolumeNameW = FindNextAccessPath((void *)v7, a2, a3);
      }
    }
  }
  LastError = GetLastError();
  if ( VolumePathNamesForVolumeNameW )
    goto LABEL_14;
  if ( v7 )
    HeapFree(ProcessHeap, 0, (LPVOID)v7);
LABEL_11:
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v7 = -1;
LABEL_14:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x14001d420  mov     [rsp+arg_18], rbx
0x14001d425  push    rbp
0x14001d426  push    rsi
0x14001d427  push    rdi
0x14001d428  push    r14
0x14001d42a  push    r15
0x14001d42c  sub     rsp, 0B0h
0x14001d433  mov     rax, cs:__security_cookie
0x14001d43a  xor     rax, rsp
0x14001d43d  mov     [rsp+0D8h+var_38], rax
0x14001d445  mov     r14, r8
0x14001d448  mov     [rsp+0D8h+cchReturnLength], 0
0x14001d450  mov     r15, rdx
0x14001d453  mov     rbx, rcx
0x14001d456  call    cs:__imp_GetProcessHeap
0x14001d45c  lea     rdx, [rsp+0D8h+szVolumeName]; unsigned __int16 *
0x14001d461  mov     rcx, rbx; unsigned __int16 *
0x14001d464  mov     rbp, rax
0x14001d467  xor     edi, edi
0x14001d469  call    ?CopyFilesystemRootFromVolumeIdentifier@@YAHPEBGPEAG@Z; CopyFilesystemRootFromVolumeIdentifier(ushort const *,ushort *)
0x14001d46e  mov     esi, eax
0x14001d470  test    eax, eax
0x14001d472  jz      loc_14001D510
0x14001d478  lea     r9, [rsp+0D8h+cchReturnLength]; lpcchReturnLength
0x14001d47d  xor     r8d, r8d; cchBufferLength
0x14001d480  xor     edx, edx; lpszVolumePathNames
0x14001d482  lea     rcx, [rsp+0D8h+szVolumeName]; lpszVolumeName
0x14001d487  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14001d48d  mov     esi, eax
0x14001d48f  test    eax, eax
0x14001d491  jnz     short loc_14001D4A0
0x14001d493  call    cs:__imp_GetLastError
0x14001d499  cmp     eax, 0EAh
0x14001d49e  jnz     short loc_14001D510
0x14001d4a0  mov     r8d, [rsp+0D8h+cchReturnLength]
0x14001d4a5  xor     edx, edx; dwFlags
0x14001d4a7  mov     rcx, rbp; hHeap
0x14001d4aa  lea     r8, ds:10h[r8*2]; dwBytes
0x14001d4b2  call    cs:__imp_HeapAlloc
0x14001d4b8  mov     rdi, rax
0x14001d4bb  test    rax, rax
0x14001d4be  jnz     short loc_14001D4D3
0x14001d4c0  lea     ecx, [rax+8]; dwErrCode
0x14001d4c3  call    cs:__imp_SetLastError
0x14001d4c9  call    cs:__imp_GetLastError
0x14001d4cf  mov     ebx, eax
0x14001d4d1  jmp     short loc_14001D52F
0x14001d4d3  mov     r8d, [rsp+0D8h+cchReturnLength]; cchBufferLength
0x14001d4d8  lea     rbx, [rax+10h]
0x14001d4dc  mov     rdx, rbx; lpszVolumePathNames
0x14001d4df  lea     r9, [rsp+0D8h+cchReturnLength]; lpcchReturnLength
0x14001d4e4  lea     rcx, [rsp+0D8h+szVolumeName]; lpszVolumeName
0x14001d4e9  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14001d4ef  mov     esi, eax
0x14001d4f1  test    eax, eax
0x14001d4f3  jz      short loc_14001D510
0x14001d4f5  mov     eax, [rsp+0D8h+cchReturnLength]
0x14001d4f9  mov     r8, r14; unsigned __int64 *
0x14001d4fc  mov     rdx, r15; unsigned __int16 **
0x14001d4ff  mov     [rdi], rax
0x14001d502  mov     rcx, rdi; void *
0x14001d505  mov     [rdi+8], rbx
0x14001d509  call    ?FindNextAccessPath@@YAHPEAXPEAPEBGPEA_K@Z; FindNextAccessPath(void *,ushort const * *,unsigned __int64 *)
0x14001d50e  mov     esi, eax
0x14001d510  call    cs:__imp_GetLastError
0x14001d516  mov     ebx, eax
0x14001d518  test    esi, esi
0x14001d51a  jnz     short loc_14001D546
0x14001d51c  test    rdi, rdi
0x14001d51f  jz      short loc_14001D52F
0x14001d521  mov     r8, rdi; lpMem
0x14001d524  xor     edx, edx; dwFlags
0x14001d526  mov     rcx, rbp; hHeap
0x14001d529  call    cs:__imp_HeapFree
0x14001d52f  mov     qword ptr [r15], 0
0x14001d536  test    r14, r14
0x14001d539  jz      short loc_14001D542
0x14001d53b  mov     qword ptr [r14], 0
0x14001d542  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001d546  mov     ecx, ebx; dwErrCode
0x14001d548  call    cs:__imp_SetLastError
0x14001d54e  mov     rax, rdi
0x14001d551  mov     rcx, [rsp+0D8h+var_38]
0x14001d559  xor     rcx, rsp; StackCookie
0x14001d55c  call    __security_check_cookie
0x14001d561  mov     rbx, [rsp+0D8h+arg_18]
0x14001d569  add     rsp, 0B0h
0x14001d570  pop     r15
0x14001d572  pop     r14
0x14001d574  pop     rdi
0x14001d575  pop     rsi
0x14001d576  pop     rbp
0x14001d577  retn
```
