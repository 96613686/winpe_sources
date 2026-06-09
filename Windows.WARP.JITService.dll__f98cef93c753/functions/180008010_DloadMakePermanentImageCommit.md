# DloadMakePermanentImageCommit

- ea: `0x180008010`
- end: `0x1800080c7`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800080d0`

## callees

- `0x180008010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180008069`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180008069`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000804d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000804d`

## pseudocode

```c
SIZE_T __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  SIZE_T result; // rax
  __int64 dwPageSize; // r9
  volatile signed __int32 *v6; // r8
  unsigned __int64 v7; // rcx
  struct _MEMORY_BASIC_INFORMATION v8; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  memset(&v8, 0, sizeof(v8));
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  result = VirtualQuery((LPCVOID)a1, &v8, 0x30u);
  if ( !result )
    __fastfail(0x19u);
  if ( (v8.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v6 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v7 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((SystemInfo.dwPageSize - 1) & (unsigned int)a1)
                           + ((SystemInfo.dwPageSize - 1) & (unsigned int)a2))
        - 1)
       / SystemInfo.dwPageSize;
    for ( result = (unsigned int)v7; result; --result )
    {
      _InterlockedOr(v6, 0);
      v6 = (volatile signed __int32 *)((char *)v6 + dwPageSize);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008010  mov     rax, rsp
0x180008013  mov     [rax+8], rbx
0x180008017  push    rdi
0x180008018  sub     rsp, 80h
0x18000801f  xorps   xmm0, xmm0
0x180008022  xorps   xmm1, xmm1
0x180008025  mov     rdi, rdx
0x180008028  mov     r8d, 30h ; '0'; dwLength
0x18000802e  lea     rdx, [rax-68h]; lpBuffer
0x180008032  mov     rbx, rcx
0x180008035  movups  xmmword ptr [rax-68h], xmm0
0x180008039  movups  xmmword ptr [rax-58h], xmm0
0x18000803d  movups  xmmword ptr [rax-48h], xmm0
0x180008041  movups  xmmword ptr [rax-38h], xmm1
0x180008045  movups  xmmword ptr [rax-28h], xmm1
0x180008049  movups  xmmword ptr [rax-18h], xmm1
0x18000804d  call    cs:__imp_VirtualQuery
0x180008053  test    rax, rax
0x180008056  jnz     short loc_18000805D
0x180008058  lea     ecx, [rax+19h]
0x18000805b  int     29h; Win8: RtlFailFast(ecx)
0x18000805d  test    [rsp+88h+var_44], 44h
0x180008062  jz      short loc_1800080B6
0x180008064  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180008069  call    cs:__imp_GetSystemInfo
0x18000806f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180008074  xor     edx, edx
0x180008076  mov     eax, edi
0x180008078  mov     r8d, r9d
0x18000807b  neg     r8
0x18000807e  and     r8, rbx
0x180008081  lea     ecx, [r9-1]
0x180008085  and     eax, ecx
0x180008087  and     ebx, ecx
0x180008089  add     eax, ebx
0x18000808b  dec     rax
0x18000808e  add     rax, r9
0x180008091  div     r9
0x180008094  xor     edx, edx
0x180008096  mov     rcx, rax
0x180008099  mov     rax, rdi
0x18000809c  div     r9
0x18000809f  add     rcx, rax
0x1800080a2  mov     eax, ecx
0x1800080a4  test    ecx, ecx
0x1800080a6  jz      short loc_1800080B6
0x1800080a8  lock or dword ptr [r8], 0
0x1800080ad  add     r8, r9
0x1800080b0  sub     rax, 1
0x1800080b4  jnz     short loc_1800080A8
0x1800080b6  mov     rbx, [rsp+88h+arg_0]
0x1800080be  add     rsp, 80h
0x1800080c5  pop     rdi
0x1800080c6  retn
```
