# DloadMakePermanentImageCommit

- ea: `0x18001d7e8`
- end: `0x18001d89f`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d8a8`

## callees

- `0x18001d7e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001d841`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001d841`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001d825`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001d825`

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
0x18001d7e8  mov     rax, rsp
0x18001d7eb  mov     [rax+8], rbx
0x18001d7ef  push    rdi
0x18001d7f0  sub     rsp, 80h
0x18001d7f7  xorps   xmm0, xmm0
0x18001d7fa  xorps   xmm1, xmm1
0x18001d7fd  mov     rdi, rdx
0x18001d800  mov     r8d, 30h ; '0'; dwLength
0x18001d806  lea     rdx, [rax-68h]; lpBuffer
0x18001d80a  mov     rbx, rcx
0x18001d80d  movups  xmmword ptr [rax-68h], xmm0
0x18001d811  movups  xmmword ptr [rax-58h], xmm0
0x18001d815  movups  xmmword ptr [rax-48h], xmm0
0x18001d819  movups  xmmword ptr [rax-38h], xmm1
0x18001d81d  movups  xmmword ptr [rax-28h], xmm1
0x18001d821  movups  xmmword ptr [rax-18h], xmm1
0x18001d825  call    cs:__imp_VirtualQuery
0x18001d82b  test    rax, rax
0x18001d82e  jnz     short loc_18001D835
0x18001d830  lea     ecx, [rax+19h]
0x18001d833  int     29h; Win8: RtlFailFast(ecx)
0x18001d835  test    [rsp+88h+var_44], 44h
0x18001d83a  jz      short loc_18001D88E
0x18001d83c  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18001d841  call    cs:__imp_GetSystemInfo
0x18001d847  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18001d84c  xor     edx, edx
0x18001d84e  mov     eax, edi
0x18001d850  mov     r8d, r9d
0x18001d853  neg     r8
0x18001d856  and     r8, rbx
0x18001d859  lea     ecx, [r9-1]
0x18001d85d  and     eax, ecx
0x18001d85f  and     ebx, ecx
0x18001d861  add     eax, ebx
0x18001d863  dec     rax
0x18001d866  add     rax, r9
0x18001d869  div     r9
0x18001d86c  xor     edx, edx
0x18001d86e  mov     rcx, rax
0x18001d871  mov     rax, rdi
0x18001d874  div     r9
0x18001d877  add     rcx, rax
0x18001d87a  mov     eax, ecx
0x18001d87c  test    ecx, ecx
0x18001d87e  jz      short loc_18001D88E
0x18001d880  lock or dword ptr [r8], 0
0x18001d885  add     r8, r9
0x18001d888  sub     rax, 1
0x18001d88c  jnz     short loc_18001D880
0x18001d88e  mov     rbx, [rsp+88h+arg_0]
0x18001d896  add     rsp, 80h
0x18001d89d  pop     rdi
0x18001d89e  retn
```
