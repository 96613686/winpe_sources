# Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::Submit(Microsoft::Bluetooth::Foundation::Details::IoTargetWriteRequest &)

- ea: `0x18001ec40`
- end: `0x18001ecaf`
- name: `?Submit@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@UEAA?AUSubmissionResult@RequestDispatcher@2345@AEAVIoTargetWriteRequest@2345@@Z`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18001e114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec85`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ec7d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ec7d`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::Submit(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  DWORD LastError; // eax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 56));
  v5 = WriteFile(
         *(HANDLE *)(a1 + 24),
         *(LPCVOID *)(a3 + 88),
         *(_DWORD *)(a3 + 96),
         0,
         (LPOVERLAPPED)((a3 + 8) & -(__int64)(a3 != 0)));
  LastError = GetLastError();
  Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::ProcessApiResult(a1, a2, v5, LastError);
  return a2;
}

```

## disassembly

```asm
0x18001ec40  mov     [rsp+arg_0], rbx
0x18001ec45  mov     [rsp+arg_8], rsi
0x18001ec4a  push    rdi
0x18001ec4b  sub     rsp, 30h
0x18001ec4f  mov     rsi, rdx
0x18001ec52  mov     rdi, rcx
0x18001ec55  lea     rdx, [r8+58h]
0x18001ec59  lock inc dword ptr [rcx+38h]
0x18001ec5d  mov     rcx, [rcx+18h]; hFile
0x18001ec61  lea     r9, [r8+8]
0x18001ec65  neg     r8
0x18001ec68  mov     r8d, [rdx+8]; nNumberOfBytesToWrite
0x18001ec6c  mov     rdx, [rdx]; lpBuffer
0x18001ec6f  sbb     rax, rax
0x18001ec72  and     rax, r9
0x18001ec75  xor     r9d, r9d; lpNumberOfBytesWritten
0x18001ec78  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18001ec7d  call    cs:__imp_WriteFile
0x18001ec83  mov     ebx, eax
0x18001ec85  call    cs:__imp_GetLastError
0x18001ec8b  mov     r8d, ebx
0x18001ec8e  mov     rdx, rsi
0x18001ec91  mov     r9d, eax
0x18001ec94  mov     rcx, rdi
0x18001ec97  call    ?ProcessApiResult@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA?AUSubmissionResult@RequestDispatcher@2345@HK@Z; Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::ProcessApiResult(int,ulong)
0x18001ec9c  mov     rbx, [rsp+38h+arg_0]
0x18001eca1  mov     rax, rsi
0x18001eca4  mov     rsi, [rsp+38h+arg_8]
0x18001eca9  add     rsp, 30h
0x18001ecad  pop     rdi
0x18001ecae  retn
```
