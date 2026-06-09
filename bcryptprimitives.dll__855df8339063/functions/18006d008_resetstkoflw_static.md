# _resetstkoflw_static

- ea: `0x18006d008`
- end: `0x18006d15a`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006cfdc`

## callees

- `0x18006d008`
- `0x18007f790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18006d0a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18006d0a1`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006d073`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18006d073`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006d140`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18006d140`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006d120`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18006d120`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18006d08c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18006d08c`

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
0x18006d008  push    rbp
0x18006d00a  push    rbx
0x18006d00b  push    rsi
0x18006d00c  push    rdi
0x18006d00d  push    r14
0x18006d00f  push    r15
0x18006d011  sub     rsp, 98h
0x18006d018  lea     rbp, [rsp+20h]
0x18006d01d  mov     rax, cs:__security_cookie
0x18006d024  xor     rax, rbp
0x18006d027  mov     [rbp+0A0h+var_38], rax
0x18006d02b  mov     eax, [rsp+0C0h+var_C0]
0x18006d02e  xorps   xmm0, xmm0
0x18006d031  xorps   xmm1, xmm1
0x18006d034  mov     [rbp+0A0h+flOldProtect], 0
0x18006d03b  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18006d03f  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18006d046  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18006d04a  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18006d04e  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18006d052  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18006d056  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18006d05a  sub     rsp, 10h
0x18006d05e  lea     r14, [rsp+0D0h+Address]
0x18006d063  mov     eax, [r14]
0x18006d066  mov     r8d, 30h ; '0'; dwLength
0x18006d06c  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18006d070  mov     rcx, r14; lpAddress
0x18006d073  call    cs:__imp_VirtualQuery
0x18006d07a  nop     dword ptr [rax+rax+00h]
0x18006d07f  test    rax, rax
0x18006d082  jz      short loc_18006D0D3
0x18006d084  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18006d088  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18006d08c  call    cs:__imp_GetSystemInfo
0x18006d093  nop     dword ptr [rax+rax+00h]
0x18006d098  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18006d09b  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18006d09f  xor     ebx, ebx
0x18006d0a1  call    cs:__imp_SetThreadStackGuarantee
0x18006d0a8  nop     dword ptr [rax+rax+00h]
0x18006d0ad  cmp     eax, 1
0x18006d0b0  jnz     short loc_18006D0BA
0x18006d0b2  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18006d0b5  test    eax, eax
0x18006d0b7  cmovnz  ebx, eax
0x18006d0ba  lea     edx, [rdi-1]
0x18006d0bd  lea     ecx, [rdx+rbx]
0x18006d0c0  cmp     ecx, ebx
0x18006d0c2  jb      short loc_18006D0D3
0x18006d0c4  mov     eax, edx
0x18006d0c6  not     eax
0x18006d0c8  and     eax, ecx
0x18006d0ca  jz      short loc_18006D0EF
0x18006d0cc  lea     ecx, [rax+rdi]
0x18006d0cf  cmp     ecx, eax
0x18006d0d1  jnb     short loc_18006D0F1
0x18006d0d3  xor     eax, eax
0x18006d0d5  mov     rcx, [rbp+0A0h+var_38]
0x18006d0d9  xor     rcx, rbp; StackCookie
0x18006d0dc  call    __security_check_cookie
0x18006d0e1  lea     rsp, [rbp+78h]
0x18006d0e5  pop     r15
0x18006d0e7  pop     r14
0x18006d0e9  pop     rdi
0x18006d0ea  pop     rsi
0x18006d0eb  pop     rbx
0x18006d0ec  pop     rbp
0x18006d0ed  retn
0x18006d0ef  mov     ecx, eax
0x18006d0f1  lea     eax, [rdi+rdi*2]
0x18006d0f4  mov     ebx, edx
0x18006d0f6  cmp     ecx, eax
0x18006d0f8  not     rbx
0x18006d0fb  cmovnb  eax, ecx
0x18006d0fe  and     rbx, r14
0x18006d101  mov     esi, eax
0x18006d103  lea     rax, [r15+rdi]
0x18006d107  sub     rbx, rsi
0x18006d10a  cmp     rbx, rax
0x18006d10d  jb      short loc_18006D0D3
0x18006d10f  mov     r9d, 4; flProtect
0x18006d115  mov     r8d, 1000h; flAllocationType
0x18006d11b  mov     edx, esi; dwSize
0x18006d11d  mov     rcx, rbx; lpAddress
0x18006d120  call    cs:__imp_VirtualAlloc
0x18006d127  nop     dword ptr [rax+rax+00h]
0x18006d12c  test    rax, rax
0x18006d12f  jz      short loc_18006D0D3
0x18006d131  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18006d135  mov     r8d, 104h; flNewProtect
0x18006d13b  mov     edx, esi; dwSize
0x18006d13d  mov     rcx, rbx; lpAddress
0x18006d140  call    cs:__imp_VirtualProtect
0x18006d147  nop     dword ptr [rax+rax+00h]
0x18006d14c  xor     ecx, ecx
0x18006d14e  test    eax, eax
0x18006d150  setnz   cl
0x18006d153  mov     eax, ecx
0x18006d155  jmp     loc_18006D0D5
```
