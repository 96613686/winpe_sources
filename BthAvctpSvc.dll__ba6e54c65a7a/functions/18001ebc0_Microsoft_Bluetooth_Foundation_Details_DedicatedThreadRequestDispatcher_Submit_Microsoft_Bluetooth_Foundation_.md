# Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::Submit(Microsoft::Bluetooth::Foundation::Details::IoTargetReadRequest &)

- ea: `0x18001ebc0`
- end: `0x18001ec2f`
- name: `?Submit@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA?AUSubmissionResult@RequestDispatcher@2345@AEAVIoTargetReadRequest@2345@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18001e114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec05`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ebfd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ebfd`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::Submit(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int File; // ebx
  DWORD LastError; // eax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 56));
  File = ReadFile(
           *(HANDLE *)(a1 + 24),
           *(LPVOID *)(a3 + 88),
           *(_DWORD *)(a3 + 96),
           0,
           (LPOVERLAPPED)((a3 + 8) & -(__int64)(a3 != 0)));
  LastError = GetLastError();
  Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::ProcessApiResult(a1, a2, File, LastError);
  return a2;
}

```

## disassembly

```asm
0x18001ebc0  mov     [rsp+arg_0], rbx
0x18001ebc5  mov     [rsp+arg_8], rsi
0x18001ebca  push    rdi
0x18001ebcb  sub     rsp, 30h
0x18001ebcf  mov     rsi, rdx
0x18001ebd2  mov     rdi, rcx
0x18001ebd5  lea     rdx, [r8+58h]
0x18001ebd9  lock inc dword ptr [rcx+38h]
0x18001ebdd  mov     rcx, [rcx+18h]; hFile
0x18001ebe1  lea     r9, [r8+8]
0x18001ebe5  neg     r8
0x18001ebe8  mov     r8d, [rdx+8]; nNumberOfBytesToRead
0x18001ebec  mov     rdx, [rdx]; lpBuffer
0x18001ebef  sbb     rax, rax
0x18001ebf2  and     rax, r9
0x18001ebf5  xor     r9d, r9d; lpNumberOfBytesRead
0x18001ebf8  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18001ebfd  call    cs:__imp_ReadFile
0x18001ec03  mov     ebx, eax
0x18001ec05  call    cs:__imp_GetLastError
0x18001ec0b  mov     r8d, ebx
0x18001ec0e  mov     rdx, rsi
0x18001ec11  mov     r9d, eax
0x18001ec14  mov     rcx, rdi
0x18001ec17  call    ?ProcessApiResult@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HK@Z; Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::ProcessApiResult(int,ulong)
0x18001ec1c  mov     rbx, [rsp+38h+arg_0]
0x18001ec21  mov     rax, rsi
0x18001ec24  mov     rsi, [rsp+38h+arg_8]
0x18001ec29  add     rsp, 30h
0x18001ec2d  pop     rdi
0x18001ec2e  retn
```
