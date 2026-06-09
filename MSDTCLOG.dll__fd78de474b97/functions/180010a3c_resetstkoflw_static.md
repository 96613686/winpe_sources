# _resetstkoflw_static

- ea: `0x180010a3c`
- end: `0x180010b6c`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010a14`

## callees

- `0x180010a3c`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180010b41`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180010b41`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180010b5b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180010b5b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180010aa7`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180010aa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010aba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010aba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180010ac9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x180010ac9`

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
0x180010a3c  push    rbp
0x180010a3e  push    rbx
0x180010a3f  push    rsi
0x180010a40  push    rdi
0x180010a41  push    r14
0x180010a43  push    r15
0x180010a45  sub     rsp, 98h
0x180010a4c  lea     rbp, [rsp+20h]
0x180010a51  mov     rax, cs:__security_cookie
0x180010a58  xor     rax, rbp
0x180010a5b  mov     [rbp+0A0h+var_38], rax
0x180010a5f  mov     eax, [rsp+0C0h+var_C0]
0x180010a62  xorps   xmm0, xmm0
0x180010a65  xorps   xmm1, xmm1
0x180010a68  mov     [rbp+0A0h+flOldProtect], 0
0x180010a6f  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x180010a73  mov     [rbp+0A0h+StackSizeInBytes], 0
0x180010a7a  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x180010a7e  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x180010a82  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x180010a86  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180010a8a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x180010a8e  sub     rsp, 10h
0x180010a92  lea     r14, [rsp+0D0h+Address]
0x180010a97  mov     eax, [r14]
0x180010a9a  mov     r8d, 30h ; '0'; dwLength
0x180010aa0  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180010aa4  mov     rcx, r14; lpAddress
0x180010aa7  call    cs:__imp_VirtualQuery
0x180010aad  test    rax, rax
0x180010ab0  jz      short loc_180010AF5
0x180010ab2  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x180010ab6  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x180010aba  call    cs:__imp_GetSystemInfo
0x180010ac0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180010ac3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x180010ac7  xor     ebx, ebx
0x180010ac9  call    cs:__imp_SetThreadStackGuarantee
0x180010acf  cmp     eax, 1
0x180010ad2  jnz     short loc_180010ADC
0x180010ad4  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x180010ad7  test    eax, eax
0x180010ad9  cmovnz  ebx, eax
0x180010adc  lea     edx, [rdi-1]
0x180010adf  lea     ecx, [rdx+rbx]
0x180010ae2  cmp     ecx, ebx
0x180010ae4  jb      short loc_180010AF5
0x180010ae6  mov     eax, edx
0x180010ae8  not     eax
0x180010aea  and     eax, ecx
0x180010aec  jz      short loc_180010B10
0x180010aee  lea     ecx, [rax+rdi]
0x180010af1  cmp     ecx, eax
0x180010af3  jnb     short loc_180010B12
0x180010af5  xor     eax, eax
0x180010af7  mov     rcx, [rbp+0A0h+var_38]
0x180010afb  xor     rcx, rbp; StackCookie
0x180010afe  call    __security_check_cookie
0x180010b03  lea     rsp, [rbp+78h]
0x180010b07  pop     r15
0x180010b09  pop     r14
0x180010b0b  pop     rdi
0x180010b0c  pop     rsi
0x180010b0d  pop     rbx
0x180010b0e  pop     rbp
0x180010b0f  retn
0x180010b10  mov     ecx, eax
0x180010b12  lea     eax, [rdi+rdi*2]
0x180010b15  mov     ebx, edx
0x180010b17  cmp     ecx, eax
0x180010b19  not     rbx
0x180010b1c  cmovnb  eax, ecx
0x180010b1f  and     rbx, r14
0x180010b22  mov     esi, eax
0x180010b24  lea     rax, [r15+rdi]
0x180010b28  sub     rbx, rsi
0x180010b2b  cmp     rbx, rax
0x180010b2e  jb      short loc_180010AF5
0x180010b30  mov     r9d, 4; flProtect
0x180010b36  mov     r8d, 1000h; flAllocationType
0x180010b3c  mov     edx, esi; dwSize
0x180010b3e  mov     rcx, rbx; lpAddress
0x180010b41  call    cs:__imp_VirtualAlloc
0x180010b47  test    rax, rax
0x180010b4a  jz      short loc_180010AF5
0x180010b4c  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x180010b50  mov     r8d, 104h; flNewProtect
0x180010b56  mov     edx, esi; dwSize
0x180010b58  mov     rcx, rbx; lpAddress
0x180010b5b  call    cs:__imp_VirtualProtect
0x180010b61  xor     ecx, ecx
0x180010b63  test    eax, eax
0x180010b65  setnz   cl
0x180010b68  mov     eax, ecx
0x180010b6a  jmp     short loc_180010AF7
```
