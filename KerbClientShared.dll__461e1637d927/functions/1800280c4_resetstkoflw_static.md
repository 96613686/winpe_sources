# _resetstkoflw_static

- ea: `0x1800280c4`
- end: `0x1800281f4`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d40`

## callees

- `0x18000eb70`
- `0x1800280c4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180028142`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180028142`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180028151`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180028151`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800281c9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800281c9`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800281e3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800281e3`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002812f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002812f`

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
0x1800280c4  push    rbp
0x1800280c6  push    rbx
0x1800280c7  push    rsi
0x1800280c8  push    rdi
0x1800280c9  push    r14
0x1800280cb  push    r15
0x1800280cd  sub     rsp, 98h
0x1800280d4  lea     rbp, [rsp+20h]
0x1800280d9  mov     rax, cs:__security_cookie
0x1800280e0  xor     rax, rbp
0x1800280e3  mov     [rbp+0A0h+var_38], rax
0x1800280e7  mov     eax, [rsp+0C0h+var_C0]
0x1800280ea  xorps   xmm0, xmm0
0x1800280ed  xorps   xmm1, xmm1
0x1800280f0  mov     [rbp+0A0h+flOldProtect], 0
0x1800280f7  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800280fb  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180028102  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180028106  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18002810a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18002810e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180028112  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180028116  sub     rsp, 10h
0x18002811a  lea     r14, [rsp+0D0h+Address]
0x18002811f  mov     eax, [r14]
0x180028122  mov     r8d, 30h ; '0'; dwLength
0x180028128  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18002812c  mov     rcx, r14; lpAddress
0x18002812f  call    cs:__imp_VirtualQuery
0x180028135  test    rax, rax
0x180028138  jz      short loc_18002817D
0x18002813a  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18002813e  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180028142  call    cs:__imp_GetSystemInfo
0x180028148  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18002814b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18002814f  xor     ebx, ebx
0x180028151  call    cs:__imp_SetThreadStackGuarantee
0x180028157  cmp     eax, 1
0x18002815a  jnz     short loc_180028164
0x18002815c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18002815f  test    eax, eax
0x180028161  cmovnz  ebx, eax
0x180028164  lea     edx, [rdi-1]
0x180028167  lea     ecx, [rdx+rbx]
0x18002816a  cmp     ecx, ebx
0x18002816c  jb      short loc_18002817D
0x18002816e  mov     eax, edx
0x180028170  not     eax
0x180028172  and     eax, ecx
0x180028174  jz      short loc_180028198
0x180028176  lea     ecx, [rax+rdi]
0x180028179  cmp     ecx, eax
0x18002817b  jnb     short loc_18002819A
0x18002817d  xor     eax, eax
0x18002817f  mov     rcx, [rbp+0A0h+var_38]
0x180028183  xor     rcx, rbp; StackCookie
0x180028186  call    __security_check_cookie
0x18002818b  lea     rsp, [rbp+78h]
0x18002818f  pop     r15
0x180028191  pop     r14
0x180028193  pop     rdi
0x180028194  pop     rsi
0x180028195  pop     rbx
0x180028196  pop     rbp
0x180028197  retn
0x180028198  mov     ecx, eax
0x18002819a  lea     eax, [rdi+rdi*2]
0x18002819d  mov     ebx, edx
0x18002819f  cmp     ecx, eax
0x1800281a1  not     rbx
0x1800281a4  cmovnb  eax, ecx
0x1800281a7  and     rbx, r14
0x1800281aa  mov     esi, eax
0x1800281ac  lea     rax, [r15+rdi]
0x1800281b0  sub     rbx, rsi
0x1800281b3  cmp     rbx, rax
0x1800281b6  jb      short loc_18002817D
0x1800281b8  mov     r9d, 4; flProtect
0x1800281be  mov     r8d, 1000h; flAllocationType
0x1800281c4  mov     edx, esi; dwSize
0x1800281c6  mov     rcx, rbx; lpAddress
0x1800281c9  call    cs:__imp_VirtualAlloc
0x1800281cf  test    rax, rax
0x1800281d2  jz      short loc_18002817D
0x1800281d4  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800281d8  mov     r8d, 104h; flNewProtect
0x1800281de  mov     edx, esi; dwSize
0x1800281e0  mov     rcx, rbx; lpAddress
0x1800281e3  call    cs:__imp_VirtualProtect
0x1800281e9  xor     ecx, ecx
0x1800281eb  test    eax, eax
0x1800281ed  setnz   cl
0x1800281f0  mov     eax, ecx
0x1800281f2  jmp     short loc_18002817F
```
