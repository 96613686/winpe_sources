# _resetstkoflw_static

- ea: `0x1800183e4`
- end: `0x180018536`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008078`

## callees

- `0x1800183e4`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001847d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001847d`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001851c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001851c`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001844f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001844f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800184fc`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800184fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180018468`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180018468`

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
0x1800183e4  push    rbp
0x1800183e6  push    rbx
0x1800183e7  push    rsi
0x1800183e8  push    rdi
0x1800183e9  push    r14
0x1800183eb  push    r15
0x1800183ed  sub     rsp, 98h
0x1800183f4  lea     rbp, [rsp+20h]
0x1800183f9  mov     rax, cs:__security_cookie
0x180018400  xor     rax, rbp
0x180018403  mov     [rbp+0A0h+var_38], rax
0x180018407  mov     eax, [rsp+0C0h+var_C0]
0x18001840a  xorps   xmm0, xmm0
0x18001840d  xorps   xmm1, xmm1
0x180018410  mov     [rbp+0A0h+flOldProtect], 0
0x180018417  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001841b  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180018422  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180018426  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001842a  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001842e  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180018432  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180018436  sub     rsp, 10h
0x18001843a  lea     r14, [rsp+0D0h+Address]
0x18001843f  mov     eax, [r14]
0x180018442  mov     r8d, 30h ; '0'; dwLength
0x180018448  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001844c  mov     rcx, r14; lpAddress
0x18001844f  call    cs:__imp_VirtualQuery
0x180018456  nop     dword ptr [rax+rax+00h]
0x18001845b  test    rax, rax
0x18001845e  jz      short loc_1800184AF
0x180018460  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180018464  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180018468  call    cs:__imp_GetSystemInfo
0x18001846f  nop     dword ptr [rax+rax+00h]
0x180018474  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180018477  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001847b  xor     ebx, ebx
0x18001847d  call    cs:__imp_SetThreadStackGuarantee
0x180018484  nop     dword ptr [rax+rax+00h]
0x180018489  cmp     eax, 1
0x18001848c  jnz     short loc_180018496
0x18001848e  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180018491  test    eax, eax
0x180018493  cmovnz  ebx, eax
0x180018496  lea     edx, [rdi-1]
0x180018499  lea     ecx, [rdx+rbx]
0x18001849c  cmp     ecx, ebx
0x18001849e  jb      short loc_1800184AF
0x1800184a0  mov     eax, edx
0x1800184a2  not     eax
0x1800184a4  and     eax, ecx
0x1800184a6  jz      short loc_1800184CB
0x1800184a8  lea     ecx, [rax+rdi]
0x1800184ab  cmp     ecx, eax
0x1800184ad  jnb     short loc_1800184CD
0x1800184af  xor     eax, eax
0x1800184b1  mov     rcx, [rbp+0A0h+var_38]
0x1800184b5  xor     rcx, rbp; StackCookie
0x1800184b8  call    __security_check_cookie
0x1800184bd  lea     rsp, [rbp+78h]
0x1800184c1  pop     r15
0x1800184c3  pop     r14
0x1800184c5  pop     rdi
0x1800184c6  pop     rsi
0x1800184c7  pop     rbx
0x1800184c8  pop     rbp
0x1800184c9  retn
0x1800184cb  mov     ecx, eax
0x1800184cd  lea     eax, [rdi+rdi*2]
0x1800184d0  mov     ebx, edx
0x1800184d2  cmp     ecx, eax
0x1800184d4  not     rbx
0x1800184d7  cmovnb  eax, ecx
0x1800184da  and     rbx, r14
0x1800184dd  mov     esi, eax
0x1800184df  lea     rax, [r15+rdi]
0x1800184e3  sub     rbx, rsi
0x1800184e6  cmp     rbx, rax
0x1800184e9  jb      short loc_1800184AF
0x1800184eb  mov     r9d, 4; flProtect
0x1800184f1  mov     r8d, 1000h; flAllocationType
0x1800184f7  mov     edx, esi; dwSize
0x1800184f9  mov     rcx, rbx; lpAddress
0x1800184fc  call    cs:__imp_VirtualAlloc
0x180018503  nop     dword ptr [rax+rax+00h]
0x180018508  test    rax, rax
0x18001850b  jz      short loc_1800184AF
0x18001850d  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180018511  mov     r8d, 104h; flNewProtect
0x180018517  mov     edx, esi; dwSize
0x180018519  mov     rcx, rbx; lpAddress
0x18001851c  call    cs:__imp_VirtualProtect
0x180018523  nop     dword ptr [rax+rax+00h]
0x180018528  xor     ecx, ecx
0x18001852a  test    eax, eax
0x18001852c  setnz   cl
0x18001852f  mov     eax, ecx
0x180018531  jmp     loc_1800184B1
```
