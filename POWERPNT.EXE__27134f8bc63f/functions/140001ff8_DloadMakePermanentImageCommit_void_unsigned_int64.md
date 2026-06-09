# DloadMakePermanentImageCommit(void *,unsigned __int64)

- ea: `0x140001ff8`
- end: `0x140002090`
- name: `?DloadMakePermanentImageCommit@@YAXPEAX_K@Z`
- size: `152`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001f00`

## callees

- `0x140001ff8`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x140002016`
- `KERNEL32!VirtualQuery` at `0x140002016`
- `KERNEL32!GetSystemInfo` at `0x140002032`
- `KERNEL32!GetSystemInfo` at `0x140002032`

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
0x140001ff8  mov     [rsp+arg_0], rbx
0x140001ffd  push    rdi
0x140001ffe  sub     rsp, 80h
0x140002005  mov     rdi, rdx
0x140002008  mov     r8d, 30h ; '0'; dwLength
0x14000200e  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x140002013  mov     rbx, rcx
0x140002016  call    cs:__imp_VirtualQuery
0x14000201c  test    rax, rax
0x14000201f  jnz     short loc_140002026
0x140002021  lea     ecx, [rax+19h]
0x140002024  int     29h; Win8: RtlFailFast(ecx)
0x140002026  test    byte ptr [rsp+88h+Buffer.Protect], 44h
0x14000202b  jz      short loc_14000207F
0x14000202d  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x140002032  call    cs:__imp_GetSystemInfo
0x140002038  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x14000203d  xor     edx, edx
0x14000203f  mov     r8d, r9d
0x140002042  neg     r8
0x140002045  and     r8, rbx
0x140002048  lea     ecx, [r9-1]
0x14000204c  mov     eax, ecx
0x14000204e  and     ecx, ebx
0x140002050  and     eax, edi
0x140002052  add     eax, ecx
0x140002054  dec     rax
0x140002057  add     rax, r9
0x14000205a  div     r9
0x14000205d  xor     edx, edx
0x14000205f  mov     rcx, rax
0x140002062  mov     rax, rdi
0x140002065  div     r9
0x140002068  add     rcx, rax
0x14000206b  mov     eax, ecx
0x14000206d  test    ecx, ecx
0x14000206f  jz      short loc_14000207F
0x140002071  lock or dword ptr [r8], 0
0x140002076  add     r8, r9
0x140002079  sub     rax, 1
0x14000207d  jnz     short loc_140002071
0x14000207f  mov     rbx, [rsp+88h+arg_0]
0x140002087  add     rsp, 80h
0x14000208e  pop     rdi
0x14000208f  retn
```
