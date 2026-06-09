# DloadMakePermanentImageCommit(void *,unsigned __int64)

- ea: `0x140002a58`
- end: `0x140002af0`
- name: `?DloadMakePermanentImageCommit@@YAXPEAX_K@Z`
- size: `152`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002b8c`

## callees

- `0x140002a58`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x140002a76`
- `KERNEL32!VirtualQuery` at `0x140002a76`
- `KERNEL32!GetSystemInfo` at `0x140002a92`
- `KERNEL32!GetSystemInfo` at `0x140002a92`

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
0x140002a58  mov     [rsp+arg_0], rbx
0x140002a5d  push    rdi
0x140002a5e  sub     rsp, 80h
0x140002a65  mov     rdi, rdx
0x140002a68  mov     r8d, 30h ; '0'; dwLength
0x140002a6e  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x140002a73  mov     rbx, rcx
0x140002a76  call    cs:__imp_VirtualQuery
0x140002a7c  test    rax, rax
0x140002a7f  jnz     short loc_140002A86
0x140002a81  lea     ecx, [rax+19h]
0x140002a84  int     29h; Win8: RtlFailFast(ecx)
0x140002a86  test    byte ptr [rsp+88h+Buffer.Protect], 44h
0x140002a8b  jz      short loc_140002ADF
0x140002a8d  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x140002a92  call    cs:__imp_GetSystemInfo
0x140002a98  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x140002a9d  xor     edx, edx
0x140002a9f  mov     r8d, r9d
0x140002aa2  neg     r8
0x140002aa5  and     r8, rbx
0x140002aa8  lea     ecx, [r9-1]
0x140002aac  mov     eax, ecx
0x140002aae  and     ecx, ebx
0x140002ab0  and     eax, edi
0x140002ab2  add     eax, ecx
0x140002ab4  dec     rax
0x140002ab7  add     rax, r9
0x140002aba  div     r9
0x140002abd  xor     edx, edx
0x140002abf  mov     rcx, rax
0x140002ac2  mov     rax, rdi
0x140002ac5  div     r9
0x140002ac8  add     rcx, rax
0x140002acb  mov     eax, ecx
0x140002acd  test    ecx, ecx
0x140002acf  jz      short loc_140002ADF
0x140002ad1  lock or dword ptr [r8], 0
0x140002ad6  add     r8, r9
0x140002ad9  sub     rax, 1
0x140002add  jnz     short loc_140002AD1
0x140002adf  mov     rbx, [rsp+88h+arg_0]
0x140002ae7  add     rsp, 80h
0x140002aee  pop     rdi
0x140002aef  retn
```
