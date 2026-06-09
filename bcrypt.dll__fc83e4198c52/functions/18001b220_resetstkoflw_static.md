# _resetstkoflw_static

- ea: `0x18001b220`
- end: `0x18001b372`
- name: `_resetstkoflw_static`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cae4`

## callees

- `0x18001b220`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001b2b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18001b2b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001b2a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001b2a4`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001b28b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001b28b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001b358`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001b358`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001b338`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001b338`

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
0x18001b220  push    rbp
0x18001b222  push    rbx
0x18001b223  push    rsi
0x18001b224  push    rdi
0x18001b225  push    r14
0x18001b227  push    r15
0x18001b229  sub     rsp, 98h
0x18001b230  lea     rbp, [rsp+20h]
0x18001b235  mov     rax, cs:__security_cookie
0x18001b23c  xor     rax, rbp
0x18001b23f  mov     [rbp+0A0h+var_38], rax
0x18001b243  mov     eax, [rsp+0C0h+var_C0]
0x18001b246  xorps   xmm0, xmm0
0x18001b249  xorps   xmm1, xmm1
0x18001b24c  mov     [rbp+0A0h+flOldProtect], 0
0x18001b253  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x18001b257  mov     [rbp+0A0h+StackSizeInBytes], 0
0x18001b25e  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x18001b262  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x18001b266  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x18001b26a  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18001b26e  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x18001b272  sub     rsp, 10h
0x18001b276  lea     r14, [rsp+0D0h+Address]
0x18001b27b  mov     eax, [r14]
0x18001b27e  mov     r8d, 30h ; '0'; dwLength
0x18001b284  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18001b288  mov     rcx, r14; lpAddress
0x18001b28b  call    cs:__imp_VirtualQuery
0x18001b292  nop     dword ptr [rax+rax+00h]
0x18001b297  test    rax, rax
0x18001b29a  jz      short loc_18001B2EB
0x18001b29c  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18001b2a0  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18001b2a4  call    cs:__imp_GetSystemInfo
0x18001b2ab  nop     dword ptr [rax+rax+00h]
0x18001b2b0  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x18001b2b3  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18001b2b7  xor     ebx, ebx
0x18001b2b9  call    cs:__imp_SetThreadStackGuarantee
0x18001b2c0  nop     dword ptr [rax+rax+00h]
0x18001b2c5  cmp     eax, 1
0x18001b2c8  jnz     short loc_18001B2D2
0x18001b2ca  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18001b2cd  test    eax, eax
0x18001b2cf  cmovnz  ebx, eax
0x18001b2d2  lea     edx, [rdi-1]
0x18001b2d5  lea     ecx, [rdx+rbx]
0x18001b2d8  cmp     ecx, ebx
0x18001b2da  jb      short loc_18001B2EB
0x18001b2dc  mov     eax, edx
0x18001b2de  not     eax
0x18001b2e0  and     eax, ecx
0x18001b2e2  jz      short loc_18001B307
0x18001b2e4  lea     ecx, [rax+rdi]
0x18001b2e7  cmp     ecx, eax
0x18001b2e9  jnb     short loc_18001B309
0x18001b2eb  xor     eax, eax
0x18001b2ed  mov     rcx, [rbp+0A0h+var_38]
0x18001b2f1  xor     rcx, rbp; StackCookie
0x18001b2f4  call    __security_check_cookie
0x18001b2f9  lea     rsp, [rbp+78h]
0x18001b2fd  pop     r15
0x18001b2ff  pop     r14
0x18001b301  pop     rdi
0x18001b302  pop     rsi
0x18001b303  pop     rbx
0x18001b304  pop     rbp
0x18001b305  retn
0x18001b307  mov     ecx, eax
0x18001b309  lea     eax, [rdi+rdi*2]
0x18001b30c  mov     ebx, edx
0x18001b30e  cmp     ecx, eax
0x18001b310  not     rbx
0x18001b313  cmovnb  eax, ecx
0x18001b316  and     rbx, r14
0x18001b319  mov     esi, eax
0x18001b31b  lea     rax, [r15+rdi]
0x18001b31f  sub     rbx, rsi
0x18001b322  cmp     rbx, rax
0x18001b325  jb      short loc_18001B2EB
0x18001b327  mov     r9d, 4; flProtect
0x18001b32d  mov     r8d, 1000h; flAllocationType
0x18001b333  mov     edx, esi; dwSize
0x18001b335  mov     rcx, rbx; lpAddress
0x18001b338  call    cs:__imp_VirtualAlloc
0x18001b33f  nop     dword ptr [rax+rax+00h]
0x18001b344  test    rax, rax
0x18001b347  jz      short loc_18001B2EB
0x18001b349  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x18001b34d  mov     r8d, 104h; flNewProtect
0x18001b353  mov     edx, esi; dwSize
0x18001b355  mov     rcx, rbx; lpAddress
0x18001b358  call    cs:__imp_VirtualProtect
0x18001b35f  nop     dword ptr [rax+rax+00h]
0x18001b364  xor     ecx, ecx
0x18001b366  test    eax, eax
0x18001b368  setnz   cl
0x18001b36b  mov     eax, ecx
0x18001b36d  jmp     loc_18001B2ED
```
