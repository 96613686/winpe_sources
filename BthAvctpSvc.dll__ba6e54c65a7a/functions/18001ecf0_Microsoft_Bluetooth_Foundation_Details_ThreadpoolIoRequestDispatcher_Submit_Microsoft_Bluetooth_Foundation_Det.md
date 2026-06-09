# Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::Submit(Microsoft::Bluetooth::Foundation::Details::IoTargetIoctlRequest &)

- ea: `0x18001ecf0`
- end: `0x18001ed85`
- name: `?Submit@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA?AUSubmissionResult@RequestDispatcher@2345@AEAVIoTargetIoctlRequest@2345@@Z`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001e160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed5e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ed0e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001ed0e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ed52`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ed52`

## pseudocode

```c
_DWORD *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::Submit(
        __int64 a1,
        _DWORD *a2,
        __int64 a3)
{
  BOOL v6; // eax
  int v7; // edi
  DWORD LastError; // eax
  DWORD BytesReturned; // [rsp+70h] [rbp+8h] BYREF

  BytesReturned = 0;
  StartThreadpoolIo(*(PTP_IO *)(a1 + 24));
  v6 = DeviceIoControl(
         *(HANDLE *)(a1 + 16),
         *(_DWORD *)(a3 + 80),
         *(LPVOID *)(a3 + 88),
         *(_DWORD *)(a3 + 96),
         *(LPVOID *)(a3 + 104),
         *(_DWORD *)(a3 + 112),
         &BytesReturned,
         (LPOVERLAPPED)((a3 + 8) & -(__int64)(a3 != 0)));
  LODWORD(a3) = BytesReturned;
  v7 = v6;
  LastError = GetLastError();
  Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(a1, a2, v7, LastError, a3);
  return a2;
}

```

## disassembly

```asm
0x18001ecf0  push    rbx
0x18001ecf2  push    rbp
0x18001ecf3  push    rsi
0x18001ecf4  push    rdi
0x18001ecf5  sub     rsp, 48h
0x18001ecf9  mov     rsi, rcx
0x18001ecfc  mov     [rsp+68h+BytesReturned], 0
0x18001ed04  mov     rcx, [rcx+18h]; pio
0x18001ed08  mov     rbx, r8
0x18001ed0b  mov     rbp, rdx
0x18001ed0e  call    cs:__imp_StartThreadpoolIo
0x18001ed14  mov     r8, [rbx+58h]; lpInBuffer
0x18001ed18  lea     r10, [rbx+8]
0x18001ed1c  mov     edx, [rbx+50h]; dwIoControlCode
0x18001ed1f  mov     rax, rbx
0x18001ed22  mov     rcx, [rsi+10h]; hDevice
0x18001ed26  neg     rax
0x18001ed29  lea     rax, [rsp+68h+BytesReturned]
0x18001ed2e  sbb     r9, r9
0x18001ed31  and     r9, r10
0x18001ed34  mov     [rsp+68h+lpOverlapped], r9; lpOverlapped
0x18001ed39  mov     r9d, [rbx+60h]; nInBufferSize
0x18001ed3d  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18001ed42  mov     eax, [rbx+70h]
0x18001ed45  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x18001ed49  mov     rax, [rbx+68h]
0x18001ed4d  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x18001ed52  call    cs:__imp_DeviceIoControl
0x18001ed58  mov     ebx, [rsp+68h+BytesReturned]
0x18001ed5c  mov     edi, eax
0x18001ed5e  call    cs:__imp_GetLastError
0x18001ed64  mov     r8d, edi
0x18001ed67  mov     dword ptr [rsp+68h+lpOutBuffer], ebx
0x18001ed6b  mov     r9d, eax
0x18001ed6e  mov     rdx, rbp
0x18001ed71  mov     rcx, rsi
0x18001ed74  call    ?ProcessApiResult@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HKK@Z; Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ProcessApiResult(int,ulong,ulong)
0x18001ed79  mov     rax, rbp
0x18001ed7c  add     rsp, 48h
0x18001ed80  pop     rdi
0x18001ed81  pop     rsi
0x18001ed82  pop     rbp
0x18001ed83  pop     rbx
0x18001ed84  retn
```
