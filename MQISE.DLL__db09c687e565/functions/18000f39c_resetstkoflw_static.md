# _resetstkoflw_static

- ea: `0x18000f39c`
- end: `0x18000f4cc`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f374`

## callees

- `0x18000f39c`
- `0x18000f5f0`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x18000f407`
- `KERNEL32!VirtualQuery` at `0x18000f407`
- `KERNEL32!SetThreadStackGuarantee` at `0x18000f429`
- `KERNEL32!SetThreadStackGuarantee` at `0x18000f429`
- `KERNEL32!VirtualAlloc` at `0x18000f4a1`
- `KERNEL32!VirtualAlloc` at `0x18000f4a1`
- `KERNEL32!VirtualProtect` at `0x18000f4bb`
- `KERNEL32!VirtualProtect` at `0x18000f4bb`
- `KERNEL32!GetSystemInfo` at `0x18000f41a`
- `KERNEL32!GetSystemInfo` at `0x18000f41a`

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
0x18000f39c  push    rbp
0x18000f39e  push    rbx
0x18000f39f  push    rsi
0x18000f3a0  push    rdi
0x18000f3a1  push    r14
0x18000f3a3  push    r15
0x18000f3a5  sub     rsp, 98h
0x18000f3ac  lea     rbp, [rsp+20h]
0x18000f3b1  mov     rax, cs:__security_cookie
0x18000f3b8  xor     rax, rbp
0x18000f3bb  mov     [rbp+0A0h+var_38], rax
0x18000f3bf  mov     eax, [rsp+0C0h+var_C0]
0x18000f3c2  xorps   xmm0, xmm0
0x18000f3c5  xorps   xmm1, xmm1
0x18000f3c8  mov     [rbp+0A0h+flOldProtect], 0
0x18000f3cf  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18000f3d3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18000f3da  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18000f3de  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18000f3e2  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18000f3e6  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18000f3ea  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18000f3ee  sub     rsp, 10h
0x18000f3f2  lea     r14, [rsp+0D0h+Address]
0x18000f3f7  mov     eax, [r14]
0x18000f3fa  mov     r8d, 30h ; '0'; dwLength
0x18000f400  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18000f404  mov     rcx, r14; lpAddress
0x18000f407  call    cs:__imp_VirtualQuery
0x18000f40d  test    rax, rax
0x18000f410  jz      short loc_18000F455
0x18000f412  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18000f416  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18000f41a  call    cs:__imp_GetSystemInfo
0x18000f420  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18000f423  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18000f427  xor     ebx, ebx
0x18000f429  call    cs:__imp_SetThreadStackGuarantee
0x18000f42f  cmp     eax, 1
0x18000f432  jnz     short loc_18000F43C
0x18000f434  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18000f437  test    eax, eax
0x18000f439  cmovnz  ebx, eax
0x18000f43c  lea     edx, [rdi-1]
0x18000f43f  lea     ecx, [rdx+rbx]
0x18000f442  cmp     ecx, ebx
0x18000f444  jb      short loc_18000F455
0x18000f446  mov     eax, edx
0x18000f448  not     eax
0x18000f44a  and     eax, ecx
0x18000f44c  jz      short loc_18000F470
0x18000f44e  lea     ecx, [rax+rdi]
0x18000f451  cmp     ecx, eax
0x18000f453  jnb     short loc_18000F472
0x18000f455  xor     eax, eax
0x18000f457  mov     rcx, [rbp+0A0h+var_38]
0x18000f45b  xor     rcx, rbp; StackCookie
0x18000f45e  call    __security_check_cookie
0x18000f463  lea     rsp, [rbp+78h]
0x18000f467  pop     r15
0x18000f469  pop     r14
0x18000f46b  pop     rdi
0x18000f46c  pop     rsi
0x18000f46d  pop     rbx
0x18000f46e  pop     rbp
0x18000f46f  retn
0x18000f470  mov     ecx, eax
0x18000f472  lea     eax, [rdi+rdi*2]
0x18000f475  mov     ebx, edx
0x18000f477  cmp     ecx, eax
0x18000f479  not     rbx
0x18000f47c  cmovnb  eax, ecx
0x18000f47f  and     rbx, r14
0x18000f482  mov     esi, eax
0x18000f484  lea     rax, [r15+rdi]
0x18000f488  sub     rbx, rsi
0x18000f48b  cmp     rbx, rax
0x18000f48e  jb      short loc_18000F455
0x18000f490  mov     r9d, 4; flProtect
0x18000f496  mov     r8d, 1000h; flAllocationType
0x18000f49c  mov     edx, esi; dwSize
0x18000f49e  mov     rcx, rbx; lpAddress
0x18000f4a1  call    cs:__imp_VirtualAlloc
0x18000f4a7  test    rax, rax
0x18000f4aa  jz      short loc_18000F455
0x18000f4ac  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18000f4b0  mov     r8d, 104h; flNewProtect
0x18000f4b6  mov     edx, esi; dwSize
0x18000f4b8  mov     rcx, rbx; lpAddress
0x18000f4bb  call    cs:__imp_VirtualProtect
0x18000f4c1  xor     ecx, ecx
0x18000f4c3  test    eax, eax
0x18000f4c5  setnz   cl
0x18000f4c8  mov     eax, ecx
0x18000f4ca  jmp     short loc_18000F457
```
