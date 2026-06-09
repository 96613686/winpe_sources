# MmsCreate

- ea: `0x18009d1f8`
- end: `0x18009d30d`
- name: `MmsCreate`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18007fd58`

## callees

- `0x1800517cc`
- `0x18009cd38`
- `0x18009d1f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009d254`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009d254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2cd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009d2be`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009d2be`

## pseudocode

```c
signed int __fastcall MmsCreate(__int64 a1)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  signed int result; // eax
  char v7; // al
  unsigned int v8; // r9d
  char v9; // al
  HANDLE FileMappingW; // rax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]
  __int128 v13; // [rsp+70h] [rbp-10h]

  memset_0(&SystemInfo, 0, 0x50u);
  v2 = *(_OWORD *)&SystemInfo.lpMaximumApplicationAddress;
  *(_OWORD *)a1 = *(_OWORD *)&SystemInfo.dwOemId;
  v3 = *(_OWORD *)&SystemInfo.dwNumberOfProcessors;
  *(_OWORD *)(a1 + 16) = v2;
  v4 = v12;
  *(_OWORD *)(a1 + 32) = v3;
  v5 = v13;
  *(_OWORD *)(a1 + 48) = v4;
  *(_OWORD *)(a1 + 64) = v5;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( ((SystemInfo.dwAllocationGranularity - 1) & 0x4000000) != 0 )
    return -2147023764;
  v7 = MmspCalculateIntegerShift(SystemInfo.dwPageSize);
  *(_BYTE *)(a1 + 72) = v7;
  if ( !v7 )
    return -2147023434;
  v9 = MmspCalculateIntegerShift(v8);
  *(_BYTE *)(a1 + 73) = v9;
  if ( !v9 )
    return -2147023434;
  *(_DWORD *)(a1 + 44) = 2;
  *(_DWORD *)(a1 + 40) = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 2u, 0, 0);
  *(_QWORD *)(a1 + 8) = FileMappingW;
  if ( FileMappingW )
  {
    *(_QWORD *)(a1 + 16) = 0x4000000;
    *(_QWORD *)a1 = &off_1800AE900;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18009d1f8  mov     [rsp-8+arg_0], rbx
0x18009d1fd  push    rbp
0x18009d1fe  mov     rbp, rsp
0x18009d201  sub     rsp, 80h
0x18009d208  xor     edx, edx; Val
0x18009d20a  mov     rbx, rcx
0x18009d20d  lea     rcx, [rbp+SystemInfo]; void *
0x18009d211  lea     r8d, [rdx+50h]; Size
0x18009d215  call    memset_0
0x18009d21a  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x18009d21e  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18009d222  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x18009d226  movaps  xmmword ptr [rbx], xmm0
0x18009d229  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x18009d22d  movaps  xmmword ptr [rbx+10h], xmm1
0x18009d231  movups  xmm1, [rbp+var_20]
0x18009d235  movaps  xmmword ptr [rbx+20h], xmm0
0x18009d239  movups  xmm0, [rbp+var_10]
0x18009d23d  movaps  xmmword ptr [rbx+30h], xmm1
0x18009d241  xorps   xmm1, xmm1
0x18009d244  movaps  xmmword ptr [rbx+40h], xmm0
0x18009d248  movups  xmmword ptr [rbp+SystemInfo], xmm1
0x18009d24c  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18009d250  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm1
0x18009d254  call    cs:__imp_GetSystemInfo
0x18009d25a  mov     r9d, [rbp+SystemInfo.dwAllocationGranularity]
0x18009d25e  lea     eax, [r9-1]
0x18009d262  bt      eax, 1Ah
0x18009d266  jnb     short loc_18009D272
0x18009d268  mov     eax, 8007046Ch
0x18009d26d  jmp     loc_18009D2FC
0x18009d272  mov     ecx, [rbp+SystemInfo.dwPageSize]
0x18009d275  call    MmspCalculateIntegerShift
0x18009d27a  mov     [rbx+48h], al
0x18009d27d  test    al, al
0x18009d27f  jz      short loc_18009D2F7
0x18009d281  mov     ecx, r9d
0x18009d284  call    MmspCalculateIntegerShift
0x18009d289  mov     [rbx+49h], al
0x18009d28c  test    al, al
0x18009d28e  jz      short loc_18009D2F7
0x18009d290  mov     r9d, 2; dwMaximumSizeHigh
0x18009d296  mov     [rsp+80h+lpName], 0; lpName
0x18009d29f  xor     edx, edx; lpFileMappingAttributes
0x18009d2a1  mov     [rbx+2Ch], r9d
0x18009d2a5  mov     r8d, 4000004h; flProtect
0x18009d2ab  mov     dword ptr [rbx+28h], 0
0x18009d2b2  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18009d2b6  mov     [rsp+80h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18009d2be  call    cs:__imp_CreateFileMappingW
0x18009d2c4  mov     [rbx+8], rax
0x18009d2c8  test    rax, rax
0x18009d2cb  jnz     short loc_18009D2E1
0x18009d2cd  call    cs:__imp_GetLastError
0x18009d2d3  test    eax, eax
0x18009d2d5  jle     short loc_18009D2FC
0x18009d2d7  movzx   eax, ax
0x18009d2da  or      eax, 80070000h
0x18009d2df  jmp     short loc_18009D2FC
0x18009d2e1  lea     rax, off_1800AE900
0x18009d2e8  mov     qword ptr [rbx+10h], 4000000h
0x18009d2f0  mov     [rbx], rax
0x18009d2f3  xor     eax, eax
0x18009d2f5  jmp     short loc_18009D2FC
0x18009d2f7  mov     eax, 800705B6h
0x18009d2fc  mov     rbx, [rsp+80h+arg_0]
0x18009d304  add     rsp, 80h
0x18009d30b  pop     rbp
0x18009d30c  retn
```
