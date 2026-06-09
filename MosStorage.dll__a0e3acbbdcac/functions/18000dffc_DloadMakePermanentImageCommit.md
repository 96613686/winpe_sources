# DloadMakePermanentImageCommit

- ea: `0x18000dffc`
- end: `0x18000e0b3`
- name: `DloadMakePermanentImageCommit`
- size: `183`
- prototype: `SIZE_T __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e0bc`

## callees

- `0x18000dffc`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000e039`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18000e039`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e055`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e055`

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
0x18000dffc  mov     rax, rsp
0x18000dfff  mov     [rax+8], rbx
0x18000e003  push    rdi
0x18000e004  sub     rsp, 80h
0x18000e00b  xorps   xmm0, xmm0
0x18000e00e  xorps   xmm1, xmm1
0x18000e011  mov     rdi, rdx
0x18000e014  mov     r8d, 30h ; '0'; dwLength
0x18000e01a  lea     rdx, [rax-68h]; lpBuffer
0x18000e01e  mov     rbx, rcx
0x18000e021  movups  xmmword ptr [rax-68h], xmm0
0x18000e025  movups  xmmword ptr [rax-58h], xmm0
0x18000e029  movups  xmmword ptr [rax-48h], xmm0
0x18000e02d  movups  xmmword ptr [rax-38h], xmm1
0x18000e031  movups  xmmword ptr [rax-28h], xmm1
0x18000e035  movups  xmmword ptr [rax-18h], xmm1
0x18000e039  call    cs:__imp_VirtualQuery
0x18000e03f  test    rax, rax
0x18000e042  jnz     short loc_18000E049
0x18000e044  lea     ecx, [rax+19h]
0x18000e047  int     29h; Win8: RtlFailFast(ecx)
0x18000e049  test    [rsp+88h+var_44], 44h
0x18000e04e  jz      short loc_18000E0A2
0x18000e050  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000e055  call    cs:__imp_GetSystemInfo
0x18000e05b  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18000e060  xor     edx, edx
0x18000e062  mov     eax, edi
0x18000e064  mov     r8d, r9d
0x18000e067  neg     r8
0x18000e06a  and     r8, rbx
0x18000e06d  lea     ecx, [r9-1]
0x18000e071  and     eax, ecx
0x18000e073  and     ebx, ecx
0x18000e075  add     eax, ebx
0x18000e077  dec     rax
0x18000e07a  add     rax, r9
0x18000e07d  div     r9
0x18000e080  xor     edx, edx
0x18000e082  mov     rcx, rax
0x18000e085  mov     rax, rdi
0x18000e088  div     r9
0x18000e08b  add     rcx, rax
0x18000e08e  mov     eax, ecx
0x18000e090  test    ecx, ecx
0x18000e092  jz      short loc_18000E0A2
0x18000e094  lock or dword ptr [r8], 0
0x18000e099  add     r8, r9
0x18000e09c  sub     rax, 1
0x18000e0a0  jnz     short loc_18000E094
0x18000e0a2  mov     rbx, [rsp+88h+arg_0]
0x18000e0aa  add     rsp, 80h
0x18000e0b1  pop     rdi
0x18000e0b2  retn
```
