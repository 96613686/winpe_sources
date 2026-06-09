# DloadMakePermanentImageCommit

- ea: `0x18000b6c0`
- end: `0x18000b777`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b780`

## callees

- `0x18000b6c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b719`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b719`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000b6fd`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000b6fd`

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
0x18000b6c0  mov     rax, rsp
0x18000b6c3  mov     [rax+8], rbx
0x18000b6c7  push    rdi
0x18000b6c8  sub     rsp, 80h
0x18000b6cf  xorps   xmm0, xmm0
0x18000b6d2  xorps   xmm1, xmm1
0x18000b6d5  mov     rdi, rdx
0x18000b6d8  mov     r8d, 30h ; '0'; dwLength
0x18000b6de  lea     rdx, [rax-68h]; lpBuffer
0x18000b6e2  mov     rbx, rcx
0x18000b6e5  movups  xmmword ptr [rax-68h], xmm0
0x18000b6e9  movups  xmmword ptr [rax-58h], xmm0
0x18000b6ed  movups  xmmword ptr [rax-48h], xmm0
0x18000b6f1  movups  xmmword ptr [rax-38h], xmm1
0x18000b6f5  movups  xmmword ptr [rax-28h], xmm1
0x18000b6f9  movups  xmmword ptr [rax-18h], xmm1
0x18000b6fd  call    cs:__imp_VirtualQuery
0x18000b703  test    rax, rax
0x18000b706  jnz     short loc_18000B70D
0x18000b708  lea     ecx, [rax+19h]
0x18000b70b  int     29h; Win8: RtlFailFast(ecx)
0x18000b70d  test    [rsp+88h+var_44], 44h
0x18000b712  jz      short loc_18000B766
0x18000b714  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000b719  call    cs:__imp_GetSystemInfo
0x18000b71f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18000b724  xor     edx, edx
0x18000b726  mov     eax, edi
0x18000b728  mov     r8d, r9d
0x18000b72b  neg     r8
0x18000b72e  and     r8, rbx
0x18000b731  lea     ecx, [r9-1]
0x18000b735  and     eax, ecx
0x18000b737  and     ebx, ecx
0x18000b739  add     eax, ebx
0x18000b73b  dec     rax
0x18000b73e  add     rax, r9
0x18000b741  div     r9
0x18000b744  xor     edx, edx
0x18000b746  mov     rcx, rax
0x18000b749  mov     rax, rdi
0x18000b74c  div     r9
0x18000b74f  add     rcx, rax
0x18000b752  mov     eax, ecx
0x18000b754  test    ecx, ecx
0x18000b756  jz      short loc_18000B766
0x18000b758  lock or dword ptr [r8], 0
0x18000b75d  add     r8, r9
0x18000b760  sub     rax, 1
0x18000b764  jnz     short loc_18000B758
0x18000b766  mov     rbx, [rsp+88h+arg_0]
0x18000b76e  add     rsp, 80h
0x18000b775  pop     rdi
0x18000b776  retn
```
