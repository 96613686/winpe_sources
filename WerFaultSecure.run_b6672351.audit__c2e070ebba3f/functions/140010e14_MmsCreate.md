# MmsCreate

- ea: `0x140010e14`
- end: `0x140010f4e`
- name: `MmsCreate`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000e8c4`

## callees

- `0x140002fcc`
- `0x140010e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010f0e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140010eff`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140010eff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140010e70`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140010e70`

## pseudocode

```c
signed int __fastcall MmsCreate(__int64 a1)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  DWORD dwAllocationGranularity; // edx
  signed int result; // eax
  int v8; // ecx
  int v9; // ecx
  HANDLE FileMappingW; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
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
  dwAllocationGranularity = SystemInfo.dwAllocationGranularity;
  if ( ((SystemInfo.dwAllocationGranularity - 1) & 0x4000000) != 0 )
    return -2147023764;
  v8 = 1;
  while ( 1 << v8 != SystemInfo.dwPageSize )
  {
    if ( (unsigned int)++v8 >= 0x20 )
    {
      LOBYTE(v8) = 0;
      break;
    }
  }
  *(_BYTE *)(a1 + 72) = v8;
  if ( !(_BYTE)v8 )
    return -2147023434;
  v9 = 1;
  while ( 1 << v9 != dwAllocationGranularity )
  {
    if ( (unsigned int)++v9 >= 0x20 )
    {
      LOBYTE(v9) = 0;
      break;
    }
  }
  *(_BYTE *)(a1 + 73) = v9;
  if ( !(_BYTE)v9 )
    return -2147023434;
  *(_DWORD *)(a1 + 44) = 2;
  *(_DWORD *)(a1 + 40) = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 2u, 0, 0);
  *(_QWORD *)(a1 + 8) = FileMappingW;
  if ( FileMappingW )
  {
    *(_QWORD *)(a1 + 16) = 0x4000000;
    *(_QWORD *)a1 = off_140013160;
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
0x140010e14  mov     [rsp-8+arg_0], rbx
0x140010e19  push    rbp
0x140010e1a  mov     rbp, rsp
0x140010e1d  sub     rsp, 80h
0x140010e24  xor     edx, edx; Val
0x140010e26  mov     rbx, rcx
0x140010e29  lea     rcx, [rbp+SystemInfo]; void *
0x140010e2d  lea     r8d, [rdx+50h]; Size
0x140010e31  call    memset_0
0x140010e36  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x140010e3a  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x140010e3e  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x140010e42  movaps  xmmword ptr [rbx], xmm0
0x140010e45  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x140010e49  movaps  xmmword ptr [rbx+10h], xmm1
0x140010e4d  movups  xmm1, [rbp+var_20]
0x140010e51  movaps  xmmword ptr [rbx+20h], xmm0
0x140010e55  movups  xmm0, [rbp+var_10]
0x140010e59  movaps  xmmword ptr [rbx+30h], xmm1
0x140010e5d  xorps   xmm1, xmm1
0x140010e60  movaps  xmmword ptr [rbx+40h], xmm0
0x140010e64  movups  xmmword ptr [rbp+SystemInfo], xmm1
0x140010e68  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm1
0x140010e6c  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm1
0x140010e70  call    cs:__imp_GetSystemInfo
0x140010e76  mov     edx, [rbp+SystemInfo.dwAllocationGranularity]
0x140010e79  lea     eax, [rdx-1]
0x140010e7c  bt      eax, 1Ah
0x140010e80  jnb     short loc_140010E8C
0x140010e82  mov     eax, 8007046Ch
0x140010e87  jmp     loc_140010F3D
0x140010e8c  mov     r8d, 1
0x140010e92  mov     ecx, r8d
0x140010e95  mov     eax, r8d
0x140010e98  shl     eax, cl
0x140010e9a  cmp     eax, [rbp+SystemInfo.dwPageSize]
0x140010e9d  jz      short loc_140010EA9
0x140010e9f  add     ecx, r8d
0x140010ea2  cmp     ecx, 20h ; ' '
0x140010ea5  jb      short loc_140010E95
0x140010ea7  xor     ecx, ecx
0x140010ea9  mov     [rbx+48h], cl
0x140010eac  test    cl, cl
0x140010eae  jz      loc_140010F38
0x140010eb4  mov     ecx, r8d
0x140010eb7  mov     eax, r8d
0x140010eba  shl     eax, cl
0x140010ebc  cmp     eax, edx
0x140010ebe  jz      short loc_140010ECA
0x140010ec0  add     ecx, r8d
0x140010ec3  cmp     ecx, 20h ; ' '
0x140010ec6  jb      short loc_140010EB7
0x140010ec8  xor     ecx, ecx
0x140010eca  mov     [rbx+49h], cl
0x140010ecd  test    cl, cl
0x140010ecf  jz      short loc_140010F38
0x140010ed1  mov     r9d, 2; dwMaximumSizeHigh
0x140010ed7  mov     [rsp+80h+lpName], 0; lpName
0x140010ee0  xor     edx, edx; lpFileMappingAttributes
0x140010ee2  mov     [rbx+2Ch], r9d
0x140010ee6  mov     r8d, 4000004h; flProtect
0x140010eec  mov     dword ptr [rbx+28h], 0
0x140010ef3  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140010ef7  mov     [rsp+80h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x140010eff  call    cs:__imp_CreateFileMappingW
0x140010f05  mov     [rbx+8], rax
0x140010f09  test    rax, rax
0x140010f0c  jnz     short loc_140010F22
0x140010f0e  call    cs:__imp_GetLastError
0x140010f14  test    eax, eax
0x140010f16  jle     short loc_140010F3D
0x140010f18  movzx   eax, ax
0x140010f1b  or      eax, 80070000h
0x140010f20  jmp     short loc_140010F3D
0x140010f22  lea     rax, off_140013160
0x140010f29  mov     qword ptr [rbx+10h], 4000000h
0x140010f31  mov     [rbx], rax
0x140010f34  xor     eax, eax
0x140010f36  jmp     short loc_140010F3D
0x140010f38  mov     eax, 800705B6h
0x140010f3d  mov     rbx, [rsp+80h+arg_0]
0x140010f45  add     rsp, 80h
0x140010f4c  pop     rbp
0x140010f4d  retn
```
