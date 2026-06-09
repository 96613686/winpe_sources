# std::thread::_Invoke_std::tuple__lambda_b1869bd9891c80d61737e8e479659c54____0_

- ea: `0x14000cfd0`
- end: `0x14000d122`
- name: `std::thread::_Invoke_std::tuple__lambda_b1869bd9891c80d61737e8e479659c54____0_`
- size: `338`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001ba0`
- `0x140001e34`
- `0x1400026c0`
- `0x1400026d8`
- `0x14000cfd0`
- `0x1400151b0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x14000d0ef`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x14000d0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0a9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000d06f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000d06f`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000cff7`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000d0da`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000cff7`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000d0da`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x14000d09f`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x14000d09f`

## string_xrefs

- `0x14000d0c0`: `Windows::Compat::Inventory::GetMoreData::CaptureAslLogging::<lambda_b1869bd9891c80d61737e8e479659c54>::operator ()`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_b1869bd9891c80d61737e8e479659c54____0_(void *a1)
{
  BOOL i; // ecx
  DWORD LastError; // eax
  const char *v4; // r9
  __int64 v5; // r8
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-838h]
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-828h] BYREF
  _BYTE Buffer[2048]; // [rsp+40h] [rbp-818h] BYREF

  for ( i = ConnectNamedPipe(*(HANDLE *)(*(_QWORD *)a1 + 16LL), 0);
        !*(_BYTE *)(*(_QWORD *)a1 + 24LL);
        i = ConnectNamedPipe(*(HANDLE *)(*(_QWORD *)a1 + 16LL), 0) )
  {
    if ( i || GetLastError() == 535 )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      NumberOfBytesRead = 0;
      if ( ReadFile(*(HANDLE *)(*(_QWORD *)a1 + 16LL), Buffer, 0x800u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
        fwprintf(*(FILE *const *)(*(_QWORD *)a1 + 8LL), L"%ls", Buffer);
      if ( DisconnectNamedPipe(*(HANDLE *)(*(_QWORD *)a1 + 16LL)) )
        continue;
      LastError = GetLastError();
      v4 = "DisconnectNamedPipe failed [%d]";
      v5 = 385;
    }
    else
    {
      LastError = GetLastError();
      v4 = "ConnectNamedPipe failed [%d]";
      v5 = 390;
    }
    LODWORD(lpOverlapped) = LastError;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::GetMoreData::CaptureAslLogging::<lambda_b1869bd9891c80d61737e8e479659c54>::operator ()",
      v5,
      v4,
      lpOverlapped);
  }
  _Cnd_do_broadcast_at_thread_exit();
  if ( a1 )
    operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x14000cfd0  push    rbx
0x14000cfd2  sub     rsp, 850h
0x14000cfd9  mov     rax, cs:__security_cookie
0x14000cfe0  xor     rax, rsp
0x14000cfe3  mov     [rsp+858h+var_18], rax
0x14000cfeb  mov     rbx, rcx
0x14000cfee  mov     rcx, [rcx]
0x14000cff1  xor     edx, edx; lpOverlapped
0x14000cff3  mov     rcx, [rcx+10h]; hNamedPipe
0x14000cff7  call    cs:__imp_ConnectNamedPipe
0x14000cffd  mov     ecx, eax
0x14000cfff  mov     rdx, [rbx]
0x14000d002  cmp     byte ptr [rdx+18h], 0
0x14000d006  jnz     loc_14000D0EF
0x14000d00c  test    ecx, ecx
0x14000d00e  jnz     short loc_14000D035
0x14000d010  call    cs:__imp_GetLastError
0x14000d016  cmp     eax, 217h
0x14000d01b  jz      short loc_14000D035
0x14000d01d  call    cs:__imp_GetLastError
0x14000d023  lea     r9, aConnectnamedpi; "ConnectNamedPipe failed [%d]"
0x14000d02a  mov     r8d, 186h
0x14000d030  jmp     loc_14000D0BC
0x14000d035  xor     edx, edx; Val
0x14000d037  mov     r8d, 800h; Size
0x14000d03d  lea     rcx, [rsp+858h+Buffer]; void *
0x14000d042  call    memset_0
0x14000d047  mov     [rsp+858h+NumberOfBytesRead], 0
0x14000d04f  mov     rcx, [rbx]
0x14000d052  mov     [rsp+858h+lpOverlapped], 0; lpOverlapped
0x14000d05b  lea     r9, [rsp+858h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000d060  mov     r8d, 800h; nNumberOfBytesToRead
0x14000d066  lea     rdx, [rsp+858h+Buffer]; lpBuffer
0x14000d06b  mov     rcx, [rcx+10h]; hFile
0x14000d06f  call    cs:__imp_ReadFile
0x14000d075  test    eax, eax
0x14000d077  jz      short loc_14000D098
0x14000d079  cmp     [rsp+858h+NumberOfBytesRead], 0
0x14000d07e  jbe     short loc_14000D098
0x14000d080  mov     rcx, [rbx]
0x14000d083  lea     r8, [rsp+858h+Buffer]
0x14000d088  lea     rdx, aLs; "%ls"
0x14000d08f  mov     rcx, [rcx+8]; Stream
0x14000d093  call    fwprintf
0x14000d098  mov     rcx, [rbx]
0x14000d09b  mov     rcx, [rcx+10h]; hNamedPipe
0x14000d09f  call    cs:__imp_DisconnectNamedPipe
0x14000d0a5  test    eax, eax
0x14000d0a7  jnz     short loc_14000D0D1
0x14000d0a9  call    cs:__imp_GetLastError
0x14000d0af  lea     r9, aDisconnectname; "DisconnectNamedPipe failed [%d]"
0x14000d0b6  mov     r8d, 181h
0x14000d0bc  mov     dword ptr [rsp+858h+lpOverlapped], eax
0x14000d0c0  lea     rdx, aWindowsCompatI_0; "Windows::Compat::Inventory::GetMoreData"...
0x14000d0c7  mov     ecx, 1
0x14000d0cc  call    AslLogCallPrintf
0x14000d0d1  mov     rcx, [rbx]
0x14000d0d4  xor     edx, edx; lpOverlapped
0x14000d0d6  mov     rcx, [rcx+10h]; hNamedPipe
0x14000d0da  call    cs:__imp_ConnectNamedPipe
0x14000d0e0  mov     ecx, eax
0x14000d0e2  mov     rax, [rbx]
0x14000d0e5  cmp     byte ptr [rax+18h], 0
0x14000d0e9  jz      loc_14000D00C
0x14000d0ef  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x14000d0f5  test    rbx, rbx
0x14000d0f8  jz      short loc_14000D107
0x14000d0fa  mov     edx, 8; unsigned __int64
0x14000d0ff  mov     rcx, rbx; void *
0x14000d102  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d107  xor     eax, eax
0x14000d109  mov     rcx, [rsp+858h+var_18]
0x14000d111  xor     rcx, rsp; StackCookie
0x14000d114  call    __security_check_cookie
0x14000d119  add     rsp, 850h
0x14000d120  pop     rbx
0x14000d121  retn
```
