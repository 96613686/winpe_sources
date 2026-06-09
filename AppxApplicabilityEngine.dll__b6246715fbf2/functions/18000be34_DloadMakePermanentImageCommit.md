# DloadMakePermanentImageCommit

- ea: `0x18000be34`
- end: `0x18000beeb`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b69c`

## callees

- `0x18000be34`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000be8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000be8d`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000be71`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000be71`

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
0x18000be34  mov     rax, rsp
0x18000be37  mov     [rax+8], rbx
0x18000be3b  push    rdi
0x18000be3c  sub     rsp, 80h
0x18000be43  xorps   xmm0, xmm0
0x18000be46  xorps   xmm1, xmm1
0x18000be49  mov     rdi, rdx
0x18000be4c  mov     r8d, 30h ; '0'; dwLength
0x18000be52  lea     rdx, [rax-68h]; lpBuffer
0x18000be56  mov     rbx, rcx
0x18000be59  movups  xmmword ptr [rax-68h], xmm0
0x18000be5d  movups  xmmword ptr [rax-58h], xmm0
0x18000be61  movups  xmmword ptr [rax-48h], xmm0
0x18000be65  movups  xmmword ptr [rax-38h], xmm1
0x18000be69  movups  xmmword ptr [rax-28h], xmm1
0x18000be6d  movups  xmmword ptr [rax-18h], xmm1
0x18000be71  call    cs:__imp_VirtualQuery
0x18000be77  test    rax, rax
0x18000be7a  jnz     short loc_18000BE81
0x18000be7c  lea     ecx, [rax+19h]
0x18000be7f  int     29h; Win8: RtlFailFast(ecx)
0x18000be81  test    [rsp+88h+var_44], 44h
0x18000be86  jz      short loc_18000BEDA
0x18000be88  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000be8d  call    cs:__imp_GetSystemInfo
0x18000be93  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18000be98  xor     edx, edx
0x18000be9a  mov     eax, edi
0x18000be9c  mov     r8d, r9d
0x18000be9f  neg     r8
0x18000bea2  and     r8, rbx
0x18000bea5  lea     ecx, [r9-1]
0x18000bea9  and     eax, ecx
0x18000beab  and     ebx, ecx
0x18000bead  add     eax, ebx
0x18000beaf  dec     rax
0x18000beb2  add     rax, r9
0x18000beb5  div     r9
0x18000beb8  xor     edx, edx
0x18000beba  mov     rcx, rax
0x18000bebd  mov     rax, rdi
0x18000bec0  div     r9
0x18000bec3  add     rcx, rax
0x18000bec6  mov     eax, ecx
0x18000bec8  test    ecx, ecx
0x18000beca  jz      short loc_18000BEDA
0x18000becc  lock or dword ptr [r8], 0
0x18000bed1  add     r8, r9
0x18000bed4  sub     rax, 1
0x18000bed8  jnz     short loc_18000BECC
0x18000beda  mov     rbx, [rsp+88h+arg_0]
0x18000bee2  add     rsp, 80h
0x18000bee9  pop     rdi
0x18000beea  retn
```
