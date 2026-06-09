# _resetstkoflw_static

- ea: `0x18001dda4`
- end: `0x18001ded4`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dd7c`

## callees

- `0x18001dda4`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001de31`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001de31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001de22`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001de22`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001dea9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001dea9`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001de0f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001de0f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001dec3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001dec3`

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
  struct _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+38h] BYREF

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
0x18001dda4  push    rbp
0x18001dda6  push    rbx
0x18001dda7  push    rsi
0x18001dda8  push    rdi
0x18001dda9  push    r14
0x18001ddab  push    r15
0x18001ddad  sub     rsp, 98h
0x18001ddb4  lea     rbp, [rsp+20h]
0x18001ddb9  mov     rax, cs:__security_cookie
0x18001ddc0  xor     rax, rbp
0x18001ddc3  mov     [rbp+0A0h+var_38], rax
0x18001ddc7  mov     eax, [rsp+0C0h+var_C0]
0x18001ddca  xorps   xmm0, xmm0
0x18001ddcd  xorps   xmm1, xmm1
0x18001ddd0  mov     [rbp+0A0h+flOldProtect], 0
0x18001ddd7  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001dddb  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001dde2  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001dde6  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001ddea  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001ddee  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001ddf2  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001ddf6  sub     rsp, 10h
0x18001ddfa  lea     r14, [rsp+0D0h+Address]
0x18001ddff  mov     eax, [r14]
0x18001de02  mov     r8d, 30h ; '0'; dwLength
0x18001de08  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001de0c  mov     rcx, r14; lpAddress
0x18001de0f  call    cs:__imp_VirtualQuery
0x18001de15  test    rax, rax
0x18001de18  jz      short loc_18001DE5D
0x18001de1a  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001de1e  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001de22  call    cs:__imp_GetSystemInfo
0x18001de28  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001de2b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001de2f  xor     ebx, ebx
0x18001de31  call    cs:__imp_SetThreadStackGuarantee
0x18001de37  cmp     eax, 1
0x18001de3a  jnz     short loc_18001DE44
0x18001de3c  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001de3f  test    eax, eax
0x18001de41  cmovnz  ebx, eax
0x18001de44  lea     edx, [rdi-1]
0x18001de47  lea     ecx, [rdx+rbx]
0x18001de4a  cmp     ecx, ebx
0x18001de4c  jb      short loc_18001DE5D
0x18001de4e  mov     eax, edx
0x18001de50  not     eax
0x18001de52  and     eax, ecx
0x18001de54  jz      short loc_18001DE78
0x18001de56  lea     ecx, [rax+rdi]
0x18001de59  cmp     ecx, eax
0x18001de5b  jnb     short loc_18001DE7A
0x18001de5d  xor     eax, eax
0x18001de5f  mov     rcx, [rbp+0A0h+var_38]
0x18001de63  xor     rcx, rbp; StackCookie
0x18001de66  call    __security_check_cookie
0x18001de6b  lea     rsp, [rbp+78h]
0x18001de6f  pop     r15
0x18001de71  pop     r14
0x18001de73  pop     rdi
0x18001de74  pop     rsi
0x18001de75  pop     rbx
0x18001de76  pop     rbp
0x18001de77  retn
0x18001de78  mov     ecx, eax
0x18001de7a  lea     eax, [rdi+rdi*2]
0x18001de7d  mov     ebx, edx
0x18001de7f  cmp     ecx, eax
0x18001de81  not     rbx
0x18001de84  cmovnb  eax, ecx
0x18001de87  and     rbx, r14
0x18001de8a  mov     esi, eax
0x18001de8c  lea     rax, [r15+rdi]
0x18001de90  sub     rbx, rsi
0x18001de93  cmp     rbx, rax
0x18001de96  jb      short loc_18001DE5D
0x18001de98  mov     r9d, 4; flProtect
0x18001de9e  mov     r8d, 1000h; flAllocationType
0x18001dea4  mov     edx, esi; dwSize
0x18001dea6  mov     rcx, rbx; lpAddress
0x18001dea9  call    cs:__imp_VirtualAlloc
0x18001deaf  test    rax, rax
0x18001deb2  jz      short loc_18001DE5D
0x18001deb4  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001deb8  mov     r8d, 104h; flNewProtect
0x18001debe  mov     edx, esi; dwSize
0x18001dec0  mov     rcx, rbx; lpAddress
0x18001dec3  call    cs:__imp_VirtualProtect
0x18001dec9  xor     ecx, ecx
0x18001decb  test    eax, eax
0x18001decd  setnz   cl
0x18001ded0  mov     eax, ecx
0x18001ded2  jmp     short loc_18001DE5F
```
