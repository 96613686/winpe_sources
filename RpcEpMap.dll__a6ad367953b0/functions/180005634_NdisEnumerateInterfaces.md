# NdisEnumerateInterfaces

- ea: `0x180005634`
- end: `0x18000573b`
- name: `NdisEnumerateInterfaces`
- size: `263`
- prototype: `__int64 __fastcall(LPVOID lpOutBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005370`

## callees

- `0x180005634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000572a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000572a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005720`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005671`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800056b2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800056b2`

## pseudocode

```c
__int64 __fastcall NdisEnumerateInterfaces(char *lpOutBuffer)
{
  HANDLE FileW; // rbp
  unsigned int v3; // esi
  DWORD LastError; // edi
  unsigned int i; // r8d
  __int64 v6; // rdx
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF

  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 0;
    LastError = GetLastError();
  }
  else
  {
    v3 = DeviceIoControl(FileW, 0x170010u, 0, 0, lpOutBuffer, 0x1400u, &BytesReturned, 0);
    LastError = GetLastError();
    CloseHandle(FileW);
    if ( v3 || LastError == 234 )
    {
      for ( i = 0;
            i < *(_DWORD *)lpOutBuffer;
            *(_QWORD *)&lpOutBuffer[v6 + 40] = (unsigned __int64)&lpOutBuffer[*(_QWORD *)&lpOutBuffer[v6 + 40]]
                                             & -(__int64)(*(_QWORD *)&lpOutBuffer[v6 + 40] != 0) )
      {
        v6 = 32LL * i;
        *(_QWORD *)&lpOutBuffer[v6 + 24] = (unsigned __int64)&lpOutBuffer[*(_QWORD *)&lpOutBuffer[v6 + 24]]
                                         & -(__int64)(*(_QWORD *)&lpOutBuffer[v6 + 24] != 0);
        ++i;
      }
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x180005634  mov     rax, rsp
0x180005637  mov     [rax+10h], edx
0x18000563a  push    rbx
0x18000563b  push    rbp
0x18000563c  push    rsi
0x18000563d  push    rdi
0x18000563e  sub     rsp, 48h
0x180005642  mov     qword ptr [rax-38h], 0
0x18000564a  mov     rbx, rcx
0x18000564d  mov     dword ptr [rax-40h], 0
0x180005654  lea     rcx, FileName; "\\\\.\\NDIS"
0x18000565b  xor     r9d, r9d; lpSecurityAttributes
0x18000565e  mov     dword ptr [rax-48h], 3
0x180005665  xor     r8d, r8d; dwShareMode
0x180005668  mov     dword ptr [rax+10h], 0
0x18000566f  xor     edx, edx; dwDesiredAccess
0x180005671  call    cs:__imp_CreateFileW
0x180005677  mov     rbp, rax
0x18000567a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000567e  jz      loc_18000571E
0x180005684  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000568d  lea     rax, [rsp+68h+BytesReturned]
0x180005692  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180005697  xor     r9d, r9d; nInBufferSize
0x18000569a  mov     [rsp+68h+nOutBufferSize], 1400h; nOutBufferSize
0x1800056a2  xor     r8d, r8d; lpInBuffer
0x1800056a5  mov     edx, 170010h; dwIoControlCode
0x1800056aa  mov     [rsp+68h+lpOutBuffer], rbx; lpOutBuffer
0x1800056af  mov     rcx, rbp; hDevice
0x1800056b2  call    cs:__imp_DeviceIoControl
0x1800056b8  mov     esi, eax
0x1800056ba  call    cs:__imp_GetLastError
0x1800056c0  mov     rcx, rbp; hObject
0x1800056c3  mov     edi, eax
0x1800056c5  call    cs:__imp_CloseHandle
0x1800056cb  test    esi, esi
0x1800056cd  jnz     short loc_1800056D7
0x1800056cf  cmp     edi, 0EAh
0x1800056d5  jnz     short loc_180005728
0x1800056d7  xor     r8d, r8d
0x1800056da  cmp     [rbx], r8d
0x1800056dd  jbe     short loc_180005728
0x1800056df  mov     edx, r8d
0x1800056e2  shl     rdx, 5
0x1800056e6  mov     rax, [rdx+rbx+18h]
0x1800056eb  lea     rcx, [rax+rbx]
0x1800056ef  neg     rax
0x1800056f2  sbb     rax, rax
0x1800056f5  and     rax, rcx
0x1800056f8  mov     [rdx+rbx+18h], rax
0x1800056fd  mov     rax, [rdx+rbx+28h]
0x180005702  lea     rcx, [rax+rbx]
0x180005706  neg     rax
0x180005709  sbb     rax, rax
0x18000570c  inc     r8d
0x18000570f  and     rax, rcx
0x180005712  mov     [rdx+rbx+28h], rax
0x180005717  cmp     r8d, [rbx]
0x18000571a  jb      short loc_1800056DF
0x18000571c  jmp     short loc_180005728
0x18000571e  xor     esi, esi
0x180005720  call    cs:__imp_GetLastError
0x180005726  mov     edi, eax
0x180005728  mov     ecx, edi; dwErrCode
0x18000572a  call    cs:__imp_SetLastError
0x180005730  mov     eax, esi
0x180005732  add     rsp, 48h
0x180005736  pop     rdi
0x180005737  pop     rsi
0x180005738  pop     rbp
0x180005739  pop     rbx
0x18000573a  retn
```
