# _resetstkoflw_static

- ea: `0x140036fbc`
- end: `0x1400370ec`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140036f94`

## callees

- `0x140036fbc`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x140037049`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x140037049`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14003703a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14003703a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1400370db`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1400370db`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400370c1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1400370c1`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x140037027`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x140037027`

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
0x140036fbc  push    rbp
0x140036fbe  push    rbx
0x140036fbf  push    rsi
0x140036fc0  push    rdi
0x140036fc1  push    r14
0x140036fc3  push    r15
0x140036fc5  sub     rsp, 98h
0x140036fcc  lea     rbp, [rsp+20h]
0x140036fd1  mov     rax, cs:__security_cookie
0x140036fd8  xor     rax, rbp
0x140036fdb  mov     [rbp+0A0h+var_38], rax
0x140036fdf  mov     eax, [rsp+0C0h+var_C0]
0x140036fe2  xorps   xmm0, xmm0
0x140036fe5  xorps   xmm1, xmm1
0x140036fe8  mov     [rbp+0A0h+flOldProtect], 0
0x140036fef  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x140036ff3  mov     [rbp+0A0h+StackSizeInBytes], 0
0x140036ffa  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x140036ffe  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x140037002  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x140037006  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x14003700a  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x14003700e  sub     rsp, 10h
0x140037012  lea     r14, [rsp+0D0h+Address]
0x140037017  mov     eax, [r14]
0x14003701a  mov     r8d, 30h ; '0'; dwLength
0x140037020  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x140037024  mov     rcx, r14; lpAddress
0x140037027  call    cs:__imp_VirtualQuery
0x14003702d  test    rax, rax
0x140037030  jz      short loc_140037075
0x140037032  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x140037036  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x14003703a  call    cs:__imp_GetSystemInfo
0x140037040  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x140037043  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x140037047  xor     ebx, ebx
0x140037049  call    cs:__imp_SetThreadStackGuarantee
0x14003704f  cmp     eax, 1
0x140037052  jnz     short loc_14003705C
0x140037054  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x140037057  test    eax, eax
0x140037059  cmovnz  ebx, eax
0x14003705c  lea     edx, [rdi-1]
0x14003705f  lea     ecx, [rdx+rbx]
0x140037062  cmp     ecx, ebx
0x140037064  jb      short loc_140037075
0x140037066  mov     eax, edx
0x140037068  not     eax
0x14003706a  and     eax, ecx
0x14003706c  jz      short loc_140037090
0x14003706e  lea     ecx, [rax+rdi]
0x140037071  cmp     ecx, eax
0x140037073  jnb     short loc_140037092
0x140037075  xor     eax, eax
0x140037077  mov     rcx, [rbp+0A0h+var_38]
0x14003707b  xor     rcx, rbp; StackCookie
0x14003707e  call    __security_check_cookie
0x140037083  lea     rsp, [rbp+78h]
0x140037087  pop     r15
0x140037089  pop     r14
0x14003708b  pop     rdi
0x14003708c  pop     rsi
0x14003708d  pop     rbx
0x14003708e  pop     rbp
0x14003708f  retn
0x140037090  mov     ecx, eax
0x140037092  lea     eax, [rdi+rdi*2]
0x140037095  mov     ebx, edx
0x140037097  cmp     ecx, eax
0x140037099  not     rbx
0x14003709c  cmovnb  eax, ecx
0x14003709f  and     rbx, r14
0x1400370a2  mov     esi, eax
0x1400370a4  lea     rax, [r15+rdi]
0x1400370a8  sub     rbx, rsi
0x1400370ab  cmp     rbx, rax
0x1400370ae  jb      short loc_140037075
0x1400370b0  mov     r9d, 4; flProtect
0x1400370b6  mov     r8d, 1000h; flAllocationType
0x1400370bc  mov     edx, esi; dwSize
0x1400370be  mov     rcx, rbx; lpAddress
0x1400370c1  call    cs:__imp_VirtualAlloc
0x1400370c7  test    rax, rax
0x1400370ca  jz      short loc_140037075
0x1400370cc  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1400370d0  mov     r8d, 104h; flNewProtect
0x1400370d6  mov     edx, esi; dwSize
0x1400370d8  mov     rcx, rbx; lpAddress
0x1400370db  call    cs:__imp_VirtualProtect
0x1400370e1  xor     ecx, ecx
0x1400370e3  test    eax, eax
0x1400370e5  setnz   cl
0x1400370e8  mov     eax, ecx
0x1400370ea  jmp     short loc_140037077
```
