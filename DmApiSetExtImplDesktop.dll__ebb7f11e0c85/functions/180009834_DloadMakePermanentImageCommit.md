# DloadMakePermanentImageCommit

- ea: `0x180009834`
- end: `0x1800098f8`
- name: `DloadMakePermanentImageCommit`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009900`

## callees

- `0x180009834`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180009893`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180009893`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180009871`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180009871`

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
0x180009834  mov     rax, rsp
0x180009837  mov     [rax+8], rbx
0x18000983b  push    rdi
0x18000983c  sub     rsp, 80h
0x180009843  xorps   xmm0, xmm0
0x180009846  xorps   xmm1, xmm1
0x180009849  mov     rdi, rdx
0x18000984c  mov     r8d, 30h ; '0'; dwLength
0x180009852  lea     rdx, [rax-68h]; lpBuffer
0x180009856  mov     rbx, rcx
0x180009859  movups  xmmword ptr [rax-68h], xmm0
0x18000985d  movups  xmmword ptr [rax-58h], xmm0
0x180009861  movups  xmmword ptr [rax-48h], xmm0
0x180009865  movups  xmmword ptr [rax-38h], xmm1
0x180009869  movups  xmmword ptr [rax-28h], xmm1
0x18000986d  movups  xmmword ptr [rax-18h], xmm1
0x180009871  call    cs:__imp_VirtualQuery
0x180009878  nop     dword ptr [rax+rax+00h]
0x18000987d  test    rax, rax
0x180009880  jnz     short loc_180009887
0x180009882  lea     ecx, [rax+19h]
0x180009885  int     29h; Win8: RtlFailFast(ecx)
0x180009887  test    [rsp+88h+var_44], 44h
0x18000988c  jz      short loc_1800098E6
0x18000988e  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180009893  call    cs:__imp_GetSystemInfo
0x18000989a  nop     dword ptr [rax+rax+00h]
0x18000989f  mov     r9d, [rsp+88h+SystemInfo.dwPageSize]
0x1800098a4  xor     edx, edx
0x1800098a6  mov     eax, edi
0x1800098a8  mov     r8d, r9d
0x1800098ab  neg     r8
0x1800098ae  and     r8, rbx
0x1800098b1  lea     ecx, [r9-1]
0x1800098b5  and     eax, ecx
0x1800098b7  and     ebx, ecx
0x1800098b9  add     eax, ebx
0x1800098bb  dec     rax
0x1800098be  add     rax, r9
0x1800098c1  div     r9
0x1800098c4  xor     edx, edx
0x1800098c6  mov     rcx, rax
0x1800098c9  mov     rax, rdi
0x1800098cc  div     r9
0x1800098cf  add     rcx, rax
0x1800098d2  mov     eax, ecx
0x1800098d4  test    ecx, ecx
0x1800098d6  jz      short loc_1800098E6
0x1800098d8  lock or dword ptr [r8], 0
0x1800098dd  add     r8, r9
0x1800098e0  sub     rax, 1
0x1800098e4  jnz     short loc_1800098D8
0x1800098e6  mov     rbx, [rsp+88h+arg_0]
0x1800098ee  add     rsp, 80h
0x1800098f5  pop     rdi
0x1800098f6  retn
```
