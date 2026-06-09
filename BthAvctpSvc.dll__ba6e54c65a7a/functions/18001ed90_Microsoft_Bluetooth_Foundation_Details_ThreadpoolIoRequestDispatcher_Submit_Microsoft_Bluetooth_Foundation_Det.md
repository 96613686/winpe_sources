# Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::Submit(Microsoft::Bluetooth::Foundation::Details::IoTargetReadRequest &)

- ea: `0x18001ed90`
- end: `0x18001ee0d`
- name: `?Submit@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA?AUSubmissionResult@RequestDispatcher@2345@AEAVIoTargetReadRequest@2345@@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18001e160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001edb2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001edb2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001edda`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001edda`

## pseudocode

```c
_DWORD *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::Submit(
        __int64 a1,
        _DWORD *a2,
        __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  BOOL v7; // eax
  DWORD LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  v4 = a3 + 88;
  v5 = a3;
  StartThreadpoolIo(*(PTP_IO *)(a1 + 24));
  v7 = ReadFile(
         *(HANDLE *)(a1 + 16),
         *(LPVOID *)v4,
         *(_DWORD *)(v4 + 8),
         &NumberOfBytesRead,
         (LPOVERLAPPED)((v5 + 8) & -(__int64)(v5 != 0)));
  LODWORD(v5) = NumberOfBytesRead;
  LODWORD(v4) = v7;
  LastError = GetLastError();
  Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(a1, a2, v4, LastError, v5);
  return a2;
}

```

## disassembly

```asm
0x18001ed90  push    rbx
0x18001ed92  push    rbp
0x18001ed93  push    rsi
0x18001ed94  push    rdi
0x18001ed95  sub     rsp, 38h
0x18001ed99  mov     rsi, rcx
0x18001ed9c  mov     [rsp+58h+NumberOfBytesRead], 0
0x18001eda4  mov     rcx, [rcx+18h]; pio
0x18001eda8  lea     rdi, [r8+58h]
0x18001edac  mov     rbx, r8
0x18001edaf  mov     rbp, rdx
0x18001edb2  call    cs:__imp_StartThreadpoolIo
0x18001edb8  mov     r8d, [rdi+8]; nNumberOfBytesToRead
0x18001edbc  lea     r9, [rbx+8]
0x18001edc0  mov     rdx, [rdi]; lpBuffer
0x18001edc3  neg     rbx
0x18001edc6  mov     rcx, [rsi+10h]; hFile
0x18001edca  sbb     rax, rax
0x18001edcd  and     rax, r9
0x18001edd0  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001edd5  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18001edda  call    cs:__imp_ReadFile
0x18001ede0  mov     ebx, [rsp+58h+NumberOfBytesRead]
0x18001ede4  mov     edi, eax
0x18001ede6  call    cs:__imp_GetLastError
0x18001edec  mov     r8d, edi
0x18001edef  mov     dword ptr [rsp+58h+lpOverlapped], ebx
0x18001edf3  mov     r9d, eax
0x18001edf6  mov     rdx, rbp
0x18001edf9  mov     rcx, rsi
0x18001edfc  call    ?ProcessApiResult@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HKK@Z; Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(int,ulong,ulong)
0x18001ee01  mov     rax, rbp
0x18001ee04  add     rsp, 38h
0x18001ee08  pop     rdi
0x18001ee09  pop     rsi
0x18001ee0a  pop     rbp
0x18001ee0b  pop     rbx
0x18001ee0c  retn
```
