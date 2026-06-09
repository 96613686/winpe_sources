# Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::Submit(Microsoft::Bluetooth::Foundation::Details::IoTargetWriteRequest &)

- ea: `0x18001ee20`
- end: `0x18001ee9d`
- name: `?Submit@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA?AUSubmissionResult@RequestDispatcher@2345@AEAVIoTargetWriteRequest@2345@@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18001e160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee76`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ee42`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ee42`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ee6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ee6a`

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
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  v4 = a3 + 88;
  v5 = a3;
  StartThreadpoolIo(*(PTP_IO *)(a1 + 24));
  v7 = WriteFile(
         *(HANDLE *)(a1 + 16),
         *(LPCVOID *)v4,
         *(_DWORD *)(v4 + 8),
         &NumberOfBytesWritten,
         (LPOVERLAPPED)((v5 + 8) & -(__int64)(v5 != 0)));
  LODWORD(v5) = NumberOfBytesWritten;
  LODWORD(v4) = v7;
  LastError = GetLastError();
  Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(a1, a2, v4, LastError, v5);
  return a2;
}

```

## disassembly

```asm
0x18001ee20  push    rbx
0x18001ee22  push    rbp
0x18001ee23  push    rsi
0x18001ee24  push    rdi
0x18001ee25  sub     rsp, 38h
0x18001ee29  mov     rsi, rcx
0x18001ee2c  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18001ee34  mov     rcx, [rcx+18h]; pio
0x18001ee38  lea     rdi, [r8+58h]
0x18001ee3c  mov     rbx, r8
0x18001ee3f  mov     rbp, rdx
0x18001ee42  call    cs:__imp_StartThreadpoolIo
0x18001ee48  mov     r8d, [rdi+8]; nNumberOfBytesToWrite
0x18001ee4c  lea     r9, [rbx+8]
0x18001ee50  mov     rdx, [rdi]; lpBuffer
0x18001ee53  neg     rbx
0x18001ee56  mov     rcx, [rsi+10h]; hFile
0x18001ee5a  sbb     rax, rax
0x18001ee5d  and     rax, r9
0x18001ee60  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ee65  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18001ee6a  call    cs:__imp_WriteFile
0x18001ee70  mov     ebx, [rsp+58h+NumberOfBytesWritten]
0x18001ee74  mov     edi, eax
0x18001ee76  call    cs:__imp_GetLastError
0x18001ee7c  mov     r8d, edi
0x18001ee7f  mov     dword ptr [rsp+58h+lpOverlapped], ebx
0x18001ee83  mov     r9d, eax
0x18001ee86  mov     rdx, rbp
0x18001ee89  mov     rcx, rsi
0x18001ee8c  call    ?ProcessApiResult@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HKK@Z; Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(int,ulong,ulong)
0x18001ee91  mov     rax, rbp
0x18001ee94  add     rsp, 38h
0x18001ee98  pop     rdi
0x18001ee99  pop     rsi
0x18001ee9a  pop     rbp
0x18001ee9b  pop     rbx
0x18001ee9c  retn
```
