# DloadMakePermanentImageCommit(void *,unsigned __int64)

- ea: `0x180014990`
- end: `0x180014a28`
- name: `?DloadMakePermanentImageCommit@@YAXPEAX_K@Z`
- size: `152`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014ad0`

## callees

- `0x180014990`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800149ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800149ca`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800149ae`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1800149ae`

## pseudocode

```c
void __fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  __int64 dwPageSize; // r9
  volatile signed __int32 *v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  if ( !VirtualQuery((LPCVOID)a1, &Buffer, 0x30u) )
    __fastfail(0x19u);
  if ( (Buffer.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v5 = (volatile signed __int32 *)(a1 & -(__int64)SystemInfo.dwPageSize);
    v6 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((unsigned int)a1 & (SystemInfo.dwPageSize - 1))
                           + ((unsigned int)a2 & (SystemInfo.dwPageSize - 1)))
        - 1)
       / SystemInfo.dwPageSize;
    v7 = (unsigned int)v6;
    if ( (_DWORD)v6 )
    {
      do
      {
        _InterlockedOr(v5, 0);
        v5 = (volatile signed __int32 *)((char *)v5 + dwPageSize);
        --v7;
      }
      while ( v7 );
    }
  }
}

```

## disassembly

```asm
0x180014990  mov     [rsp+arg_0], rbx
0x180014995  push    rdi
0x180014996  sub     rsp, 80h
0x18001499d  mov     rdi, rdx
0x1800149a0  mov     r8d, 30h ; '0'; dwLength
0x1800149a6  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x1800149ab  mov     rbx, rcx
0x1800149ae  call    cs:__imp_VirtualQuery
0x1800149b4  test    rax, rax
0x1800149b7  jnz     short loc_1800149BE
0x1800149b9  lea     ecx, [rax+19h]
0x1800149bc  int     29h; Win8: RtlFailFast(ecx)
0x1800149be  test    byte ptr [rsp+88h+Buffer.Protect], 44h
0x1800149c3  jz      short loc_180014A17
0x1800149c5  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800149ca  call    cs:__imp_GetSystemInfo
0x1800149d0  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x1800149d5  xor     edx, edx
0x1800149d7  mov     r8d, r9d
0x1800149da  neg     r8
0x1800149dd  and     r8, rbx
0x1800149e0  lea     ecx, [r9-1]
0x1800149e4  mov     eax, ecx
0x1800149e6  and     ecx, ebx
0x1800149e8  and     eax, edi
0x1800149ea  add     eax, ecx
0x1800149ec  dec     rax
0x1800149ef  add     rax, r9
0x1800149f2  div     r9
0x1800149f5  xor     edx, edx
0x1800149f7  mov     rcx, rax
0x1800149fa  mov     rax, rdi
0x1800149fd  div     r9
0x180014a00  add     rcx, rax
0x180014a03  mov     eax, ecx
0x180014a05  test    ecx, ecx
0x180014a07  jz      short loc_180014A17
0x180014a09  lock or dword ptr [r8], 0
0x180014a0e  add     r8, r9
0x180014a11  sub     rax, 1
0x180014a15  jnz     short loc_180014A09
0x180014a17  mov     rbx, [rsp+88h+arg_0]
0x180014a1f  add     rsp, 80h
0x180014a26  pop     rdi
0x180014a27  retn
```
