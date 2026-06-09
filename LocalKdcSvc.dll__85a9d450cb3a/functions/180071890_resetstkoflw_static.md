# _resetstkoflw_static

- ea: `0x180071890`
- end: `0x1800719c0`
- name: `_resetstkoflw_static`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180071868`

## callees

- `0x180002ad0`
- `0x180071890`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18007191d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18007191d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18007190e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18007190e`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800718fb`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800718fb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800719af`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800719af`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180071995`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180071995`

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
0x180071890  push    rbp
0x180071892  push    rbx
0x180071893  push    rsi
0x180071894  push    rdi
0x180071895  push    r14
0x180071897  push    r15
0x180071899  sub     rsp, 98h
0x1800718a0  lea     rbp, [rsp+20h]
0x1800718a5  mov     rax, cs:__security_cookie
0x1800718ac  xor     rax, rbp
0x1800718af  mov     [rbp+0A0h+var_38], rax
0x1800718b3  mov     eax, [rsp+0C0h+var_C0]
0x1800718b6  xorps   xmm0, xmm0
0x1800718b9  xorps   xmm1, xmm1
0x1800718bc  mov     [rbp+0A0h+flOldProtect], 0
0x1800718c3  movups  xmmword ptr [rbp+0A0h+Buffer.BaseAddress], xmm0
0x1800718c7  mov     [rbp+0A0h+StackSizeInBytes], 0
0x1800718ce  movups  xmmword ptr [rbp+0A0h+Buffer.AllocationProtect], xmm0
0x1800718d2  movups  xmmword ptr [rbp+0A0h+Buffer.State], xmm0
0x1800718d6  movups  xmmword ptr [rbp+0A0h+SystemInfo], xmm1
0x1800718da  movups  xmmword ptr [rbp+0A0h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800718de  movups  xmmword ptr [rbp+0A0h+SystemInfo.dwNumberOfProcessors], xmm1
0x1800718e2  sub     rsp, 10h
0x1800718e6  lea     r14, [rsp+0D0h+Address]
0x1800718eb  mov     eax, [r14]
0x1800718ee  mov     r8d, 30h ; '0'; dwLength
0x1800718f4  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x1800718f8  mov     rcx, r14; lpAddress
0x1800718fb  call    cs:__imp_VirtualQuery
0x180071901  test    rax, rax
0x180071904  jz      short loc_180071949
0x180071906  mov     r15, [rbp+0A0h+Buffer.AllocationBase]
0x18007190a  lea     rcx, [rbp+0A0h+SystemInfo]; lpSystemInfo
0x18007190e  call    cs:__imp_GetSystemInfo
0x180071914  mov     edi, [rbp+0A0h+SystemInfo.dwPageSize]
0x180071917  lea     rcx, [rbp+0A0h+StackSizeInBytes]; StackSizeInBytes
0x18007191b  xor     ebx, ebx
0x18007191d  call    cs:__imp_SetThreadStackGuarantee
0x180071923  cmp     eax, 1
0x180071926  jnz     short loc_180071930
0x180071928  mov     eax, [rbp+0A0h+StackSizeInBytes]
0x18007192b  test    eax, eax
0x18007192d  cmovnz  ebx, eax
0x180071930  lea     edx, [rdi-1]
0x180071933  lea     ecx, [rdx+rbx]
0x180071936  cmp     ecx, ebx
0x180071938  jb      short loc_180071949
0x18007193a  mov     eax, edx
0x18007193c  not     eax
0x18007193e  and     eax, ecx
0x180071940  jz      short loc_180071964
0x180071942  lea     ecx, [rax+rdi]
0x180071945  cmp     ecx, eax
0x180071947  jnb     short loc_180071966
0x180071949  xor     eax, eax
0x18007194b  mov     rcx, [rbp+0A0h+var_38]
0x18007194f  xor     rcx, rbp; StackCookie
0x180071952  call    __security_check_cookie
0x180071957  lea     rsp, [rbp+78h]
0x18007195b  pop     r15
0x18007195d  pop     r14
0x18007195f  pop     rdi
0x180071960  pop     rsi
0x180071961  pop     rbx
0x180071962  pop     rbp
0x180071963  retn
0x180071964  mov     ecx, eax
0x180071966  lea     eax, [rdi+rdi*2]
0x180071969  mov     ebx, edx
0x18007196b  cmp     ecx, eax
0x18007196d  not     rbx
0x180071970  cmovnb  eax, ecx
0x180071973  and     rbx, r14
0x180071976  mov     esi, eax
0x180071978  lea     rax, [r15+rdi]
0x18007197c  sub     rbx, rsi
0x18007197f  cmp     rbx, rax
0x180071982  jb      short loc_180071949
0x180071984  mov     r9d, 4; flProtect
0x18007198a  mov     r8d, 1000h; flAllocationType
0x180071990  mov     edx, esi; dwSize
0x180071992  mov     rcx, rbx; lpAddress
0x180071995  call    cs:__imp_VirtualAlloc
0x18007199b  test    rax, rax
0x18007199e  jz      short loc_180071949
0x1800719a0  lea     r9, [rbp+0A0h+flOldProtect]; lpflOldProtect
0x1800719a4  mov     r8d, 104h; flNewProtect
0x1800719aa  mov     edx, esi; dwSize
0x1800719ac  mov     rcx, rbx; lpAddress
0x1800719af  call    cs:__imp_VirtualProtect
0x1800719b5  xor     ecx, ecx
0x1800719b7  test    eax, eax
0x1800719b9  setnz   cl
0x1800719bc  mov     eax, ecx
0x1800719be  jmp     short loc_18007194B
```
