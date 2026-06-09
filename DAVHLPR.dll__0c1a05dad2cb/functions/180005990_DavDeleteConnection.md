# DavDeleteConnection

- ea: `0x180005990`
- end: `0x1800059f5`
- name: `DavDeleteConnection`
- size: `101`
- prototype: `DWORD __stdcall(HANDLE ConnectionHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005990`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800059e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800059e5`
- `ntdll!NtFsControlFile` at `0x1800059d9`
- `ntdll!NtFsControlFile` at `0x1800059d9`

## pseudocode

```c
DWORD __stdcall DavDeleteConnection(HANDLE ConnectionHandle)
{
  DWORD v1; // ebx
  int v2; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  int InputBuffer; // [rsp+78h] [rbp+10h] BYREF

  InputBuffer = 2;
  v1 = 0;
  IoStatusBlock = 0;
  v2 = NtFsControlFile(ConnectionHandle, 0, 0, 0, &IoStatusBlock, 0x4000020u, &InputBuffer, 4u, 0, 0);
  if ( v2 < 0 )
    return RtlNtStatusToDosError(v2);
  return v1;
}

```

## disassembly

```asm
0x180005990  mov     rax, rsp
0x180005993  push    rbx
0x180005994  sub     rsp, 60h
0x180005998  mov     dword ptr [rax+10h], 2
0x18000599f  lea     rax, [rax+10h]
0x1800059a3  xor     ebx, ebx
0x1800059a5  xorps   xmm0, xmm0
0x1800059a8  mov     [rax-30h], ebx
0x1800059ab  xor     r9d, r9d; ApcContext
0x1800059ae  mov     [rax-38h], rbx
0x1800059b2  xor     r8d, r8d; ApcRoutine
0x1800059b5  mov     dword ptr [rax-40h], 4
0x1800059bc  xor     edx, edx; Event
0x1800059be  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x1800059c3  movups  xmmword ptr [rax-28h], xmm0
0x1800059c7  lea     rax, [rsp+68h+var_18]
0x1800059cc  mov     [rsp+68h+FsControlCode], 4000020h; FsControlCode
0x1800059d4  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800059d9  call    cs:__imp_NtFsControlFile
0x1800059df  test    eax, eax
0x1800059e1  jns     short loc_1800059ED
0x1800059e3  mov     ecx, eax; Status
0x1800059e5  call    cs:__imp_RtlNtStatusToDosError
0x1800059eb  mov     ebx, eax
0x1800059ed  mov     eax, ebx
0x1800059ef  add     rsp, 60h
0x1800059f3  pop     rbx
0x1800059f4  retn
```
