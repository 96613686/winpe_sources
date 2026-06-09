# DloadMakePermanentImageCommit

- ea: `0x180008ec4`
- end: `0x180008f88`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f90`

## callees

- `0x180008ec4`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x180008f01`
- `KERNEL32!VirtualQuery` at `0x180008f01`
- `KERNEL32!GetSystemInfo` at `0x180008f23`
- `KERNEL32!GetSystemInfo` at `0x180008f23`

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
0x180008ec4  mov     rax, rsp
0x180008ec7  mov     [rax+8], rbx
0x180008ecb  push    rdi
0x180008ecc  sub     rsp, 80h
0x180008ed3  xorps   xmm0, xmm0
0x180008ed6  xorps   xmm1, xmm1
0x180008ed9  mov     rdi, rdx
0x180008edc  mov     r8d, 30h ; '0'; dwLength
0x180008ee2  lea     rdx, [rax-68h]; lpBuffer
0x180008ee6  mov     rbx, rcx
0x180008ee9  movups  xmmword ptr [rax-68h], xmm0
0x180008eed  movups  xmmword ptr [rax-58h], xmm0
0x180008ef1  movups  xmmword ptr [rax-48h], xmm0
0x180008ef5  movups  xmmword ptr [rax-38h], xmm1
0x180008ef9  movups  xmmword ptr [rax-28h], xmm1
0x180008efd  movups  xmmword ptr [rax-18h], xmm1
0x180008f01  call    cs:__imp_VirtualQuery
0x180008f08  nop     dword ptr [rax+rax+00h]
0x180008f0d  test    rax, rax
0x180008f10  jnz     short loc_180008F17
0x180008f12  lea     ecx, [rax+19h]
0x180008f15  int     29h; Win8: RtlFailFast(ecx)
0x180008f17  test    [rsp+88h+var_44], 44h
0x180008f1c  jz      short loc_180008F76
0x180008f1e  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180008f23  call    cs:__imp_GetSystemInfo
0x180008f2a  nop     dword ptr [rax+rax+00h]
0x180008f2f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x180008f34  xor     edx, edx
0x180008f36  mov     eax, edi
0x180008f38  mov     r8d, r9d
0x180008f3b  neg     r8
0x180008f3e  and     r8, rbx
0x180008f41  lea     ecx, [r9-1]
0x180008f45  and     eax, ecx
0x180008f47  and     ebx, ecx
0x180008f49  add     eax, ebx
0x180008f4b  dec     rax
0x180008f4e  add     rax, r9
0x180008f51  div     r9
0x180008f54  xor     edx, edx
0x180008f56  mov     rcx, rax
0x180008f59  mov     rax, rdi
0x180008f5c  div     r9
0x180008f5f  add     rcx, rax
0x180008f62  mov     eax, ecx
0x180008f64  test    ecx, ecx
0x180008f66  jz      short loc_180008F76
0x180008f68  lock or dword ptr [r8], 0
0x180008f6d  add     r8, r9
0x180008f70  sub     rax, 1
0x180008f74  jnz     short loc_180008F68
0x180008f76  mov     rbx, [rsp+88h+arg_0]
0x180008f7e  add     rsp, 80h
0x180008f85  pop     rdi
0x180008f86  retn
```
