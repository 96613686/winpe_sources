# DloadMakePermanentImageCommit

- ea: `0x18000b41c`
- end: `0x18000b4d3`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b4dc`

## callees

- `0x18000b41c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b475`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000b475`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000b459`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000b459`

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
0x18000b41c  mov     rax, rsp
0x18000b41f  mov     [rax+8], rbx
0x18000b423  push    rdi
0x18000b424  sub     rsp, 80h
0x18000b42b  xorps   xmm0, xmm0
0x18000b42e  xorps   xmm1, xmm1
0x18000b431  mov     rdi, rdx
0x18000b434  mov     r8d, 30h ; '0'; dwLength
0x18000b43a  lea     rdx, [rax-68h]; lpBuffer
0x18000b43e  mov     rbx, rcx
0x18000b441  movups  xmmword ptr [rax-68h], xmm0
0x18000b445  movups  xmmword ptr [rax-58h], xmm0
0x18000b449  movups  xmmword ptr [rax-48h], xmm0
0x18000b44d  movups  xmmword ptr [rax-38h], xmm1
0x18000b451  movups  xmmword ptr [rax-28h], xmm1
0x18000b455  movups  xmmword ptr [rax-18h], xmm1
0x18000b459  call    cs:__imp_VirtualQuery
0x18000b45f  test    rax, rax
0x18000b462  jnz     short loc_18000B469
0x18000b464  lea     ecx, [rax+19h]
0x18000b467  int     29h; Win8: RtlFailFast(ecx)
0x18000b469  test    [rsp+88h+var_44], 44h
0x18000b46e  jz      short loc_18000B4C2
0x18000b470  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000b475  call    cs:__imp_GetSystemInfo
0x18000b47b  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18000b480  xor     edx, edx
0x18000b482  mov     eax, edi
0x18000b484  mov     r8d, r9d
0x18000b487  neg     r8
0x18000b48a  and     r8, rbx
0x18000b48d  lea     ecx, [r9-1]
0x18000b491  and     eax, ecx
0x18000b493  and     ebx, ecx
0x18000b495  add     eax, ebx
0x18000b497  dec     rax
0x18000b49a  add     rax, r9
0x18000b49d  div     r9
0x18000b4a0  xor     edx, edx
0x18000b4a2  mov     rcx, rax
0x18000b4a5  mov     rax, rdi
0x18000b4a8  div     r9
0x18000b4ab  add     rcx, rax
0x18000b4ae  mov     eax, ecx
0x18000b4b0  test    ecx, ecx
0x18000b4b2  jz      short loc_18000B4C2
0x18000b4b4  lock or dword ptr [r8], 0
0x18000b4b9  add     r8, r9
0x18000b4bc  sub     rax, 1
0x18000b4c0  jnz     short loc_18000B4B4
0x18000b4c2  mov     rbx, [rsp+88h+arg_0]
0x18000b4ca  add     rsp, 80h
0x18000b4d1  pop     rdi
0x18000b4d2  retn
```
