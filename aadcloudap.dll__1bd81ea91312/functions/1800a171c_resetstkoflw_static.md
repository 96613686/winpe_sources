# _resetstkoflw_static

- ea: `0x1800a171c`
- end: `0x1800a184c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a16f4`

## callees

- `0x180003c20`
- `0x1800a171c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800a17a9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800a17a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a179a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a179a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800a183b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800a183b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800a1821`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800a1821`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800a1787`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800a1787`

## pseudocode

```c
_BOOL8 resetstkoflw_static()
{
  char *AllocationBase; // r15
  __int64 dwPageSize; // rdi
  ULONG v2; // ebx
  unsigned int v3; // edx
  ULONG v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v8; // eax
  unsigned int v9; // esi
  char *v10; // rbx
  _BYTE Address[16]; // [rsp+10h] [rbp-10h] BYREF
  ULONG StackSizeInBytes; // [rsp+20h] [rbp+0h] BYREF
  DWORD flOldProtect; // [rsp+24h] [rbp+4h] BYREF
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+28h] [rbp+8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

  flOldProtect = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  StackSizeInBytes = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !VirtualQuery(Address, &Buffer, 0x30u) )
    return 0;
  AllocationBase = (char *)Buffer.AllocationBase;
  GetSystemInfo(&SystemInfo);
  dwPageSize = SystemInfo.dwPageSize;
  v2 = 0;
  if ( SetThreadStackGuarantee(&StackSizeInBytes) && StackSizeInBytes )
    v2 = StackSizeInBytes;
  v3 = dwPageSize - 1;
  v4 = dwPageSize - 1 + v2;
  if ( v4 < v2 )
    return 0;
  v5 = v4 & ~v3;
  if ( v5 )
  {
    v6 = v5 + dwPageSize;
    if ( v5 + (unsigned int)dwPageSize < v5 )
      return 0;
  }
  else
  {
    v6 = 0;
  }
  v8 = 3 * dwPageSize;
  if ( v6 >= 3 * (int)dwPageSize )
    v8 = v6;
  v9 = v8;
  v10 = (char *)(((unsigned __int64)Address & ~(unsigned __int64)v3) - v8);
  if ( v10 < &AllocationBase[dwPageSize] || !VirtualAlloc(v10, v8, 0x1000u, 4u) )
    return 0;
  return VirtualProtect(v10, v9, 0x104u, &flOldProtect);
}

```

## disassembly

```asm
0x1800a171c  push    rbp
0x1800a171e  push    rbx
0x1800a171f  push    rsi
0x1800a1720  push    rdi
0x1800a1721  push    r14
0x1800a1723  push    r15
0x1800a1725  sub     rsp, 98h
0x1800a172c  lea     rbp, [rsp+20h]
0x1800a1731  mov     rax, cs:__security_cookie
0x1800a1738  xor     rax, rbp
0x1800a173b  mov     [rbp+0A0h+var_38], rax
0x1800a173f  mov     eax, [rsp+0C0h+var_C0]
0x1800a1742  xorps   xmm0, xmm0
0x1800a1745  xorps   xmm1, xmm1
0x1800a1748  mov     [rbp+0A0h+flOldProtect], 0
0x1800a174f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800a1753  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800a175a  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800a175e  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800a1762  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800a1766  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800a176a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800a176e  sub     rsp, 10h
0x1800a1772  lea     r14, [rsp+0D0h+Address]
0x1800a1777  mov     eax, [r14]
0x1800a177a  mov     r8d, 30h ; '0'; dwLength
0x1800a1780  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800a1784  mov     rcx, r14; lpAddress
0x1800a1787  call    cs:__imp_VirtualQuery
0x1800a178d  test    rax, rax
0x1800a1790  jz      short loc_1800A17D5
0x1800a1792  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x1800a1796  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x1800a179a  call    cs:__imp_GetSystemInfo
0x1800a17a0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x1800a17a3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x1800a17a7  xor     ebx, ebx
0x1800a17a9  call    cs:__imp_SetThreadStackGuarantee
0x1800a17af  cmp     eax, 1
0x1800a17b2  jnz     short loc_1800A17BC
0x1800a17b4  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x1800a17b7  test    eax, eax
0x1800a17b9  cmovnz  ebx, eax
0x1800a17bc  lea     edx, [rdi-1]
0x1800a17bf  lea     ecx, [rdx+rbx]
0x1800a17c2  cmp     ecx, ebx
0x1800a17c4  jb      short loc_1800A17D5
0x1800a17c6  mov     eax, edx
0x1800a17c8  not     eax
0x1800a17ca  and     eax, ecx
0x1800a17cc  jz      short loc_1800A17F0
0x1800a17ce  lea     ecx, [rax+rdi]
0x1800a17d1  cmp     ecx, eax
0x1800a17d3  jnb     short loc_1800A17F2
0x1800a17d5  xor     eax, eax
0x1800a17d7  mov     rcx, [rbp+0A0h+var_38]
0x1800a17db  xor     rcx, rbp; StackCookie
0x1800a17de  call    __security_check_cookie
0x1800a17e3  lea     rsp, [rbp+78h]
0x1800a17e7  pop     r15
0x1800a17e9  pop     r14
0x1800a17eb  pop     rdi
0x1800a17ec  pop     rsi
0x1800a17ed  pop     rbx
0x1800a17ee  pop     rbp
0x1800a17ef  retn
0x1800a17f0  mov     ecx, eax
0x1800a17f2  lea     eax, [rdi+rdi*2]
0x1800a17f5  mov     ebx, edx
0x1800a17f7  cmp     ecx, eax
0x1800a17f9  not     rbx
0x1800a17fc  cmovnb  eax, ecx
0x1800a17ff  and     rbx, r14
0x1800a1802  mov     esi, eax
0x1800a1804  lea     rax, [r15+rdi]
0x1800a1808  sub     rbx, rsi
0x1800a180b  cmp     rbx, rax
0x1800a180e  jb      short loc_1800A17D5
0x1800a1810  mov     r9d, 4; flProtect
0x1800a1816  mov     r8d, 1000h; flAllocationType
0x1800a181c  mov     edx, esi; dwSize
0x1800a181e  mov     rcx, rbx; lpAddress
0x1800a1821  call    cs:__imp_VirtualAlloc
0x1800a1827  test    rax, rax
0x1800a182a  jz      short loc_1800A17D5
0x1800a182c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800a1830  mov     r8d, 104h; flNewProtect
0x1800a1836  mov     edx, esi; dwSize
0x1800a1838  mov     rcx, rbx; lpAddress
0x1800a183b  call    cs:__imp_VirtualProtect
0x1800a1841  xor     ecx, ecx
0x1800a1843  test    eax, eax
0x1800a1845  setnz   cl
0x1800a1848  mov     eax, ecx
0x1800a184a  jmp     short loc_1800A17D7
```
