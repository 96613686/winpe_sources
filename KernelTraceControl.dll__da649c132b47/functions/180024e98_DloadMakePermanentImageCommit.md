# DloadMakePermanentImageCommit

- ea: `0x180024e98`
- end: `0x180024f2f`
- name: `DloadMakePermanentImageCommit`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024f30`

## callees

- `0x180024e98`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x180024eb6`
- `KERNEL32!VirtualQuery` at `0x180024eb6`
- `KERNEL32!GetSystemInfo` at `0x180024ed2`
- `KERNEL32!GetSystemInfo` at `0x180024ed2`

## pseudocode

```c
volatile signed __int32 *__fastcall DloadMakePermanentImageCommit(unsigned __int64 a1, unsigned __int64 a2)
{
  volatile signed __int32 *result; // rax
  __int64 dwPageSize; // r8
  unsigned int v6; // ecx
  __int64 v7; // rdx
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-68h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-38h] BYREF

  result = (volatile signed __int32 *)VirtualQuery((LPCVOID)a1, &Buffer, 0x30u);
  if ( !result )
    __fastfail(0x19u);
  if ( (Buffer.Protect & 0x44) != 0 )
  {
    GetSystemInfo(&SystemInfo);
    dwPageSize = SystemInfo.dwPageSize;
    v6 = a2 / SystemInfo.dwPageSize
       + (SystemInfo.dwPageSize
        + (unsigned __int64)(((unsigned int)a2 & (SystemInfo.dwPageSize - 1))
                           + ((unsigned int)a1 & (SystemInfo.dwPageSize - 1)))
        - 1)
       / SystemInfo.dwPageSize;
    v7 = v6;
    result = (volatile signed __int32 *)(a1 & ~(SystemInfo.dwPageSize - 1LL));
    if ( v6 )
    {
      do
      {
        _InterlockedOr(result, 0);
        result = (volatile signed __int32 *)((char *)result + dwPageSize);
        --v7;
      }
      while ( v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024e98  mov     [rsp+arg_0], rbx
0x180024e9d  push    rdi
0x180024e9e  sub     rsp, 80h
0x180024ea5  mov     rdi, rdx
0x180024ea8  mov     r8d, 30h ; '0'; dwLength
0x180024eae  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x180024eb3  mov     rbx, rcx
0x180024eb6  call    cs:__imp_VirtualQuery
0x180024ebc  test    rax, rax
0x180024ebf  jnz     short loc_180024EC6
0x180024ec1  lea     ecx, [rax+19h]
0x180024ec4  int     29h; Win8: RtlFailFast(ecx)
0x180024ec6  test    byte ptr [rsp+88h+Buffer.Protect], 44h
0x180024ecb  jz      short loc_180024F1E
0x180024ecd  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180024ed2  call    cs:__imp_GetSystemInfo
0x180024ed8  mov     r8d, [rsp+88h+SystemInfo.dwPageSize]
0x180024edd  xor     edx, edx
0x180024edf  lea     eax, [r8-1]
0x180024ee3  mov     ecx, eax
0x180024ee5  and     eax, ebx
0x180024ee7  and     ecx, edi
0x180024ee9  add     eax, ecx
0x180024eeb  dec     rax
0x180024eee  add     rax, r8
0x180024ef1  div     r8
0x180024ef4  xor     edx, edx
0x180024ef6  mov     rcx, rax
0x180024ef9  mov     rax, rdi
0x180024efc  div     r8
0x180024eff  add     ecx, eax
0x180024f01  lea     rax, [r8-1]
0x180024f05  not     rax
0x180024f08  mov     edx, ecx
0x180024f0a  and     rax, rbx
0x180024f0d  test    ecx, ecx
0x180024f0f  jz      short loc_180024F1E
0x180024f11  lock or dword ptr [rax], 0
0x180024f15  add     rax, r8
0x180024f18  sub     rdx, 1
0x180024f1c  jnz     short loc_180024F11
0x180024f1e  mov     rbx, [rsp+88h+arg_0]
0x180024f26  add     rsp, 80h
0x180024f2d  pop     rdi
0x180024f2e  retn
```
