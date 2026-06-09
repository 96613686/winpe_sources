# _resetstkoflw_static

- ea: `0x14000f084`
- end: `0x14000f1b4`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f05c`

## callees

- `0x140008c80`
- `0x14000f084`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x14000f111`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x14000f111`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14000f102`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14000f102`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x14000f0ef`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x14000f0ef`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14000f1a3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14000f1a3`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14000f189`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14000f189`

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
0x14000f084  push    rbp
0x14000f086  push    rbx
0x14000f087  push    rsi
0x14000f088  push    rdi
0x14000f089  push    r14
0x14000f08b  push    r15
0x14000f08d  sub     rsp, 98h
0x14000f094  lea     rbp, [rsp+20h]
0x14000f099  mov     rax, cs:__security_cookie
0x14000f0a0  xor     rax, rbp
0x14000f0a3  mov     [rbp+0A0h+var_38], rax
0x14000f0a7  mov     eax, [rsp+0C0h+var_C0]
0x14000f0aa  xorps   xmm0, xmm0
0x14000f0ad  xorps   xmm1, xmm1
0x14000f0b0  mov     [rbp+0A0h+flOldProtect], 0
0x14000f0b7  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x14000f0bb  mov     [rbp+0A0h+StackSizeInBytes], 0
0x14000f0c2  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x14000f0c6  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x14000f0ca  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x14000f0ce  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x14000f0d2  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x14000f0d6  sub     rsp, 10h
0x14000f0da  lea     r14, [rsp+0D0h+Address]
0x14000f0df  mov     eax, [r14]
0x14000f0e2  mov     r8d, 30h ; '0'; dwLength
0x14000f0e8  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x14000f0ec  mov     rcx, r14; lpAddress
0x14000f0ef  call    cs:__imp_VirtualQuery
0x14000f0f5  test    rax, rax
0x14000f0f8  jz      short loc_14000F13D
0x14000f0fa  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x14000f0fe  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x14000f102  call    cs:__imp_GetSystemInfo
0x14000f108  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x14000f10b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x14000f10f  xor     ebx, ebx
0x14000f111  call    cs:__imp_SetThreadStackGuarantee
0x14000f117  cmp     eax, 1
0x14000f11a  jnz     short loc_14000F124
0x14000f11c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x14000f11f  test    eax, eax
0x14000f121  cmovnz  ebx, eax
0x14000f124  lea     edx, [rdi-1]
0x14000f127  lea     ecx, [rdx+rbx]
0x14000f12a  cmp     ecx, ebx
0x14000f12c  jb      short loc_14000F13D
0x14000f12e  mov     eax, edx
0x14000f130  not     eax
0x14000f132  and     eax, ecx
0x14000f134  jz      short loc_14000F158
0x14000f136  lea     ecx, [rax+rdi]
0x14000f139  cmp     ecx, eax
0x14000f13b  jnb     short loc_14000F15A
0x14000f13d  xor     eax, eax
0x14000f13f  mov     rcx, [rbp+0A0h+var_38]
0x14000f143  xor     rcx, rbp; StackCookie
0x14000f146  call    __security_check_cookie
0x14000f14b  lea     rsp, [rbp+78h]
0x14000f14f  pop     r15
0x14000f151  pop     r14
0x14000f153  pop     rdi
0x14000f154  pop     rsi
0x14000f155  pop     rbx
0x14000f156  pop     rbp
0x14000f157  retn
0x14000f158  mov     ecx, eax
0x14000f15a  lea     eax, [rdi+rdi*2]
0x14000f15d  mov     ebx, edx
0x14000f15f  cmp     ecx, eax
0x14000f161  not     rbx
0x14000f164  cmovnb  eax, ecx
0x14000f167  and     rbx, r14
0x14000f16a  mov     esi, eax
0x14000f16c  lea     rax, [r15+rdi]
0x14000f170  sub     rbx, rsi
0x14000f173  cmp     rbx, rax
0x14000f176  jb      short loc_14000F13D
0x14000f178  mov     r9d, 4; flProtect
0x14000f17e  mov     r8d, 1000h; flAllocationType
0x14000f184  mov     edx, esi; dwSize
0x14000f186  mov     rcx, rbx; lpAddress
0x14000f189  call    cs:__imp_VirtualAlloc
0x14000f18f  test    rax, rax
0x14000f192  jz      short loc_14000F13D
0x14000f194  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x14000f198  mov     r8d, 104h; flNewProtect
0x14000f19e  mov     edx, esi; dwSize
0x14000f1a0  mov     rcx, rbx; lpAddress
0x14000f1a3  call    cs:__imp_VirtualProtect
0x14000f1a9  xor     ecx, ecx
0x14000f1ab  test    eax, eax
0x14000f1ad  setnz   cl
0x14000f1b0  mov     eax, ecx
0x14000f1b2  jmp     short loc_14000F13F
```
