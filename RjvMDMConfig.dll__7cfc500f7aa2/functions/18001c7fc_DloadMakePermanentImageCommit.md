# DloadMakePermanentImageCommit

- ea: `0x18001c7fc`
- end: `0x18001c8c0`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c8c8`

## callees

- `0x18001c7fc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001c85b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001c85b`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001c839`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18001c839`

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
0x18001c7fc  mov     rax, rsp
0x18001c7ff  mov     [rax+8], rbx
0x18001c803  push    rdi
0x18001c804  sub     rsp, 80h
0x18001c80b  xorps   xmm0, xmm0
0x18001c80e  xorps   xmm1, xmm1
0x18001c811  mov     rdi, rdx
0x18001c814  mov     r8d, 30h ; '0'; dwLength
0x18001c81a  lea     rdx, [rax-68h]; lpBuffer
0x18001c81e  mov     rbx, rcx
0x18001c821  movups  xmmword ptr [rax-68h], xmm0
0x18001c825  movups  xmmword ptr [rax-58h], xmm0
0x18001c829  movups  xmmword ptr [rax-48h], xmm0
0x18001c82d  movups  xmmword ptr [rax-38h], xmm1
0x18001c831  movups  xmmword ptr [rax-28h], xmm1
0x18001c835  movups  xmmword ptr [rax-18h], xmm1
0x18001c839  call    cs:__imp_VirtualQuery
0x18001c840  nop     dword ptr [rax+rax+00h]
0x18001c845  test    rax, rax
0x18001c848  jnz     short loc_18001C84F
0x18001c84a  lea     ecx, [rax+19h]
0x18001c84d  int     29h; Win8: RtlFailFast(ecx)
0x18001c84f  test    [rsp+88h+var_44], 44h
0x18001c854  jz      short loc_18001C8AE
0x18001c856  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18001c85b  call    cs:__imp_GetSystemInfo
0x18001c862  nop     dword ptr [rax+rax+00h]
0x18001c867  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x18001c86c  xor     edx, edx
0x18001c86e  mov     eax, edi
0x18001c870  mov     r8d, r9d
0x18001c873  neg     r8
0x18001c876  and     r8, rbx
0x18001c879  lea     ecx, [r9-1]
0x18001c87d  and     eax, ecx
0x18001c87f  and     ebx, ecx
0x18001c881  add     eax, ebx
0x18001c883  dec     rax
0x18001c886  add     rax, r9
0x18001c889  div     r9
0x18001c88c  xor     edx, edx
0x18001c88e  mov     rcx, rax
0x18001c891  mov     rax, rdi
0x18001c894  div     r9
0x18001c897  add     rcx, rax
0x18001c89a  mov     eax, ecx
0x18001c89c  test    ecx, ecx
0x18001c89e  jz      short loc_18001C8AE
0x18001c8a0  lock or dword ptr [r8], 0
0x18001c8a5  add     r8, r9
0x18001c8a8  sub     rax, 1
0x18001c8ac  jnz     short loc_18001C8A0
0x18001c8ae  mov     rbx, [rsp+88h+arg_0]
0x18001c8b6  add     rsp, 80h
0x18001c8bd  pop     rdi
0x18001c8be  retn
```
