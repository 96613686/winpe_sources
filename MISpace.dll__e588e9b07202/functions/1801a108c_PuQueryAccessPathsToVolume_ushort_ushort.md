# PuQueryAccessPathsToVolume(ushort *,ushort * *)

- ea: `0x1801a108c`
- end: `0x1801a11ff`
- name: `?PuQueryAccessPathsToVolume@@YAHPEAGPEAPEAG@Z`
- size: `371`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180199c34`
- `0x18019e72c`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x18002a948`
- `0x1801a108c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1147`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a11bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a11bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a11a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a11a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1178`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a1178`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a113f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a1198`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a113f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a1198`

## pseudocode

```c
__int64 __fastcall PuQueryAccessPathsToVolume(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v4; // r9
  __int64 v5; // r11
  BOOL VolumePathNamesForVolumeNameW; // ebx
  DWORD LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  unsigned __int16 *v12; // rdi
  HANDLE v13; // rax
  DWORD cchReturnLength; // [rsp+20h] [rbp-E0h] BYREF
  DWORD v16[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR szVolumeName[264]; // [rsp+30h] [rbp-D0h] BYREF

  cchReturnLength = 0;
  v16[0] = 0;
  *a2 = 0;
  if ( !a1 )
    return 1;
  memset_0(szVolumeName, 0, 0x208u);
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  StringCchCopyNW(szVolumeName, 0x104u, a1, v4);
  do
    ++v5;
  while ( szVolumeName[v5] );
  if ( *((_WORD *)&v16[2] + v5 + 1) != 92 )
    szVolumeName[v5] = 92;
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength);
  LastError = GetLastError();
  if ( !VolumePathNamesForVolumeNameW && LastError != 234 )
    return 0;
  v9 = cchReturnLength;
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap || (v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v9), (v12 = v11) == 0) )
  {
    SetLastError(8u);
    return 0;
  }
  v8 = GetVolumePathNamesForVolumeNameW(szVolumeName, v11, cchReturnLength, v16);
  if ( v8 )
  {
    *a2 = v12;
  }
  else
  {
    v13 = GetProcessHeap();
    if ( v13 )
      HeapFree(v13, 0, v12);
  }
  return v8;
}

```

## disassembly

```asm
0x1801a108c  mov     [rsp-8+arg_10], rbx
0x1801a1091  mov     [rsp-8+arg_18], rsi
0x1801a1096  push    rbp
0x1801a1097  push    rdi
0x1801a1098  push    r14
0x1801a109a  lea     rbp, [rsp-150h]
0x1801a10a2  sub     rsp, 250h
0x1801a10a9  mov     rax, cs:__security_cookie
0x1801a10b0  xor     rax, rsp
0x1801a10b3  mov     [rbp+160h+var_20], rax
0x1801a10ba  xor     r14d, r14d
0x1801a10bd  mov     rsi, rdx
0x1801a10c0  mov     [rsp+260h+cchReturnLength], r14d
0x1801a10c5  mov     rbx, rcx
0x1801a10c8  mov     [rsp+260h+var_23C], r14d
0x1801a10cd  mov     [rdx], r14
0x1801a10d0  test    rcx, rcx
0x1801a10d3  jz      loc_1801A11D1
0x1801a10d9  xor     edx, edx; Val
0x1801a10db  lea     rcx, [rsp+260h+szVolumeName]; void *
0x1801a10e0  mov     r8d, 208h; Size
0x1801a10e6  call    memset_0
0x1801a10eb  or      r11, 0FFFFFFFFFFFFFFFFh
0x1801a10ef  mov     r9, r11
0x1801a10f2  inc     r9; unsigned __int64
0x1801a10f5  cmp     [rbx+r9*2], r14w
0x1801a10fa  jnz     short loc_1801A10F2
0x1801a10fc  mov     r8, rbx; unsigned __int16 *
0x1801a10ff  lea     rcx, [rsp+260h+szVolumeName]; unsigned __int16 *
0x1801a1104  mov     edx, 104h; unsigned __int64
0x1801a1109  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801a110e  lea     rax, [rsp+260h+szVolumeName]
0x1801a1113  inc     r11
0x1801a1116  cmp     [rax+r11*2], r14w
0x1801a111b  jnz     short loc_1801A1113
0x1801a111d  mov     eax, 5Ch ; '\'
0x1801a1122  cmp     [rsp+r11*2+260h+var_232], ax
0x1801a1128  jz      short loc_1801A1130
0x1801a112a  mov     [rsp+r11*2+260h+szVolumeName], ax
0x1801a1130  lea     r9, [rsp+260h+cchReturnLength]; lpcchReturnLength
0x1801a1135  xor     r8d, r8d; cchBufferLength
0x1801a1138  xor     edx, edx; lpszVolumePathNames
0x1801a113a  lea     rcx, [rsp+260h+szVolumeName]; lpszVolumeName
0x1801a113f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801a1145  mov     ebx, eax
0x1801a1147  call    cs:__imp_GetLastError
0x1801a114d  test    ebx, ebx
0x1801a114f  jnz     short loc_1801A115D
0x1801a1151  cmp     eax, 0EAh
0x1801a1156  jz      short loc_1801A115D
0x1801a1158  mov     ebx, r14d
0x1801a115b  jmp     short loc_1801A11D6
0x1801a115d  mov     ebx, [rsp+260h+cchReturnLength]
0x1801a1161  call    cs:__imp_GetProcessHeap
0x1801a1167  test    rax, rax
0x1801a116a  jz      short loc_1801A11C4
0x1801a116c  lea     r8, [rbx+rbx]; dwBytes
0x1801a1170  mov     edx, 8; dwFlags
0x1801a1175  mov     rcx, rax; hHeap
0x1801a1178  call    cs:__imp_HeapAlloc
0x1801a117e  mov     rdi, rax
0x1801a1181  test    rax, rax
0x1801a1184  jz      short loc_1801A11C4
0x1801a1186  mov     r8d, [rsp+260h+cchReturnLength]; cchBufferLength
0x1801a118b  lea     r9, [rsp+260h+var_23C]; lpcchReturnLength
0x1801a1190  mov     rdx, rax; lpszVolumePathNames
0x1801a1193  lea     rcx, [rsp+260h+szVolumeName]; lpszVolumeName
0x1801a1198  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801a119e  mov     ebx, eax
0x1801a11a0  test    eax, eax
0x1801a11a2  jz      short loc_1801A11A9
0x1801a11a4  mov     [rsi], rdi
0x1801a11a7  jmp     short loc_1801A11D6
0x1801a11a9  call    cs:__imp_GetProcessHeap
0x1801a11af  test    rax, rax
0x1801a11b2  jz      short loc_1801A11D6
0x1801a11b4  mov     r8, rdi; lpMem
0x1801a11b7  xor     edx, edx; dwFlags
0x1801a11b9  mov     rcx, rax; hHeap
0x1801a11bc  call    cs:__imp_HeapFree
0x1801a11c2  jmp     short loc_1801A11D6
0x1801a11c4  mov     ecx, 8; dwErrCode
0x1801a11c9  call    cs:__imp_SetLastError
0x1801a11cf  jmp     short loc_1801A1158
0x1801a11d1  mov     ebx, 1
0x1801a11d6  mov     eax, ebx
0x1801a11d8  mov     rcx, [rbp+160h+var_20]
0x1801a11df  xor     rcx, rsp; StackCookie
0x1801a11e2  call    __security_check_cookie
0x1801a11e7  lea     r11, [rsp+260h+var_10]
0x1801a11ef  mov     rbx, [r11+30h]
0x1801a11f3  mov     rsi, [r11+38h]
0x1801a11f7  mov     rsp, r11
0x1801a11fa  pop     r14
0x1801a11fc  pop     rdi
0x1801a11fd  pop     rbp
0x1801a11fe  retn
```
