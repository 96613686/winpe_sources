# IssueHsmControl

- ea: `0x18001bb5c`
- end: `0x18001bd49`
- name: `IssueHsmControl`
- size: `493`
- prototype: `__int64 __fastcall(unsigned __int64 hFile, void *, DWORD, void *, DWORD nOutBufferSize, LPDWORD lpNumberOfBytesTransferred, struct _OVERLAPPED *)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c00`
- `0x18000b080`
- `0x18000b284`
- `0x18000d560`
- `0x18000d7b0`
- `0x18000daa0`
- `0x18000dc80`
- `0x18000dd60`
- `0x18000deb0`
- `0x18000e020`
- `0x18000e150`
- `0x18000e2c0`
- `0x18000e460`
- `0x18000e610`
- `0x18000ea30`
- `0x18000eae0`
- `0x18000f6fc`
- `0x1800101a0`
- `0x180010280`
- `0x1800103d0`
- `0x180010490`
- `0x1800115f8`

## callees

- `0x18001bb5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bceb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bbb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bbb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bcc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bcc8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bc4a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bc4a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001bcdd`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001bcdd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bc86`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001bc86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd32`

## pseudocode

```c
__int64 __fastcall IssueHsmControl(
        unsigned __int64 hFile,
        void *a2,
        DWORD a3,
        void *a4,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred,
        struct _OVERLAPPED *a7)
{
  DWORD *lpBytesReturned; // r12
  __int64 EventW; // rdi
  signed int v10; // ebx
  signed int LastError; // eax
  struct _OVERLAPPED *lpOverlapped; // rbp
  unsigned int v13; // esi
  DWORD v14; // ecx
  signed int v15; // eax
  HANDLE hEvent; // rcx
  signed int v17; // eax
  int v19; // [rsp+40h] [rbp-68h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-60h] BYREF

  v19 = 0;
  lpBytesReturned = (DWORD *)&v19;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  if ( a7 )
  {
    lpOverlapped = a7;
    v10 = 0;
    EventW = -1;
  }
  else
  {
    EventW = (__int64)CreateEventW(0, 1, 0, 0);
    if ( EventW == -1 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = 0;
    }
    if ( v10 < 0 )
      goto LABEL_40;
    Overlapped.hEvent = (HANDLE)EventW;
    lpOverlapped = &Overlapped;
  }
  v13 = 0;
  if ( hFile != -1 && (hFile & 1) != 0 )
  {
    lpOverlapped->hEvent = (HANDLE)((unsigned __int64)lpOverlapped->hEvent | 1);
    hFile = *(_QWORD *)(hFile & 0xFFFFFFFFFFFFFFFEuLL);
  }
  while ( 1 )
  {
    if ( v10 == -2147023659 )
    {
      if ( v13 )
      {
        if ( v13 == 1 )
          v14 = 400;
        else
          v14 = 1000;
      }
      else
      {
        v14 = 100;
      }
      Sleep(v14);
      ++v13;
    }
    if ( DeviceIoControl((HANDLE)hFile, 0x903BCu, a2, a3, a4, nOutBufferSize, lpBytesReturned, lpOverlapped) )
    {
      v10 = 0;
    }
    else
    {
      v15 = GetLastError();
      v10 = v15;
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
    }
    if ( a7 )
      break;
    if ( v10 == -2147023899 )
    {
      hEvent = lpOverlapped->hEvent;
      if ( hEvent )
        WaitForSingleObject(hEvent, 0xFFFFFFFF);
      if ( GetOverlappedResult((HANDLE)hFile, lpOverlapped, lpBytesReturned, 1) )
      {
        v10 = 0;
      }
      else
      {
        v17 = GetLastError();
        v10 = v17;
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_40;
    }
    if ( v10 != -2147023659 )
      goto LABEL_40;
    if ( v13 >= 0xA )
      goto LABEL_39;
  }
  if ( v10 == -2147023659 && v13 >= 0xA )
LABEL_39:
    v10 = -2147024726;
LABEL_40:
  if ( EventW != -1 )
    CloseHandle((HANDLE)EventW);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001bb5c  mov     rax, rsp
0x18001bb5f  mov     [rax+20h], r9
0x18001bb63  mov     [rax+18h], r8d
0x18001bb67  mov     [rax+10h], rdx
0x18001bb6b  push    rbx
0x18001bb6c  push    rbp
0x18001bb6d  push    rsi
0x18001bb6e  push    rdi
0x18001bb6f  push    r12
0x18001bb71  push    r13
0x18001bb73  push    r14
0x18001bb75  sub     rsp, 70h
0x18001bb79  xorps   xmm0, xmm0
0x18001bb7c  mov     dword ptr [rax-68h], 0
0x18001bb83  lea     r12, [rax-68h]
0x18001bb87  mov     r14, rcx
0x18001bb8a  movups  xmmword ptr [rax-60h], xmm0
0x18001bb8e  movups  xmmword ptr [rax-50h], xmm0
0x18001bb92  mov     rax, [rsp+0A8h+lpNumberOfBytesTransferred]
0x18001bb9a  test    rax, rax
0x18001bb9d  cmovnz  r12, rax
0x18001bba1  cmp     [rsp+0A8h+arg_30], 0
0x18001bbaa  jnz     short loc_18001BBF4
0x18001bbac  xor     r9d, r9d; lpName
0x18001bbaf  xor     r8d, r8d; bInitialState
0x18001bbb2  xor     ecx, ecx; lpEventAttributes
0x18001bbb4  lea     edx, [r9+1]; bManualReset
0x18001bbb8  call    cs:__imp_CreateEventW
0x18001bbbe  mov     rdi, rax
0x18001bbc1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bbc5  jz      short loc_18001BBCB
0x18001bbc7  xor     ebx, ebx
0x18001bbc9  jmp     short loc_18001BBE0
0x18001bbcb  call    cs:__imp_GetLastError
0x18001bbd1  mov     ebx, eax
0x18001bbd3  test    eax, eax
0x18001bbd5  jle     short loc_18001BBE0
0x18001bbd7  movzx   ebx, ax
0x18001bbda  or      ebx, 80070000h
0x18001bbe0  test    ebx, ebx
0x18001bbe2  js      loc_18001BD29
0x18001bbe8  mov     [rsp+0A8h+Overlapped.hEvent], rdi
0x18001bbed  lea     rbp, [rsp+0A8h+Overlapped]
0x18001bbf2  jmp     short loc_18001BC02
0x18001bbf4  mov     rbp, [rsp+0A8h+arg_30]
0x18001bbfc  xor     ebx, ebx
0x18001bbfe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bc02  xor     esi, esi
0x18001bc04  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001bc08  jz      short loc_18001BC1C
0x18001bc0a  test    r14b, 1
0x18001bc0e  jz      short loc_18001BC1C
0x18001bc10  or      qword ptr [rbp+18h], 1
0x18001bc15  and     r14, 0FFFFFFFFFFFFFFFEh
0x18001bc19  mov     r14, [r14]
0x18001bc1c  mov     r13d, [rsp+0A8h+arg_20]
0x18001bc24  cmp     ebx, 800704D5h
0x18001bc2a  jnz     short loc_18001BC52
0x18001bc2c  mov     eax, esi
0x18001bc2e  test    esi, esi
0x18001bc30  jz      short loc_18001BC45
0x18001bc32  cmp     eax, 1
0x18001bc35  jz      short loc_18001BC3E
0x18001bc37  mov     ecx, 3E8h
0x18001bc3c  jmp     short loc_18001BC4A
0x18001bc3e  mov     ecx, 190h
0x18001bc43  jmp     short loc_18001BC4A
0x18001bc45  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001bc4a  call    cs:__imp_Sleep
0x18001bc50  inc     esi
0x18001bc52  mov     rax, [rsp+0A8h+arg_18]
0x18001bc5a  mov     edx, 903BCh; dwIoControlCode
0x18001bc5f  mov     r9d, [rsp+0A8h+nInBufferSize]; nInBufferSize
0x18001bc67  mov     rcx, r14; hDevice
0x18001bc6a  mov     r8, [rsp+0A8h+lpInBuffer]; lpInBuffer
0x18001bc72  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x18001bc77  mov     [rsp+0A8h+lpBytesReturned], r12; lpBytesReturned
0x18001bc7c  mov     [rsp+0A8h+nOutBufferSize], r13d; nOutBufferSize
0x18001bc81  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x18001bc86  call    cs:__imp_DeviceIoControl
0x18001bc8c  test    eax, eax
0x18001bc8e  jz      short loc_18001BC94
0x18001bc90  xor     ebx, ebx
0x18001bc92  jmp     short loc_18001BCA9
0x18001bc94  call    cs:__imp_GetLastError
0x18001bc9a  mov     ebx, eax
0x18001bc9c  test    eax, eax
0x18001bc9e  jle     short loc_18001BCA9
0x18001bca0  movzx   ebx, ax
0x18001bca3  or      ebx, 80070000h
0x18001bca9  cmp     [rsp+0A8h+arg_30], 0
0x18001bcb2  jnz     short loc_18001BD17
0x18001bcb4  cmp     ebx, 800703E5h
0x18001bcba  jnz     short loc_18001BD04
0x18001bcbc  mov     rcx, [rbp+18h]; hHandle
0x18001bcc0  test    rcx, rcx
0x18001bcc3  jz      short loc_18001BCCE
0x18001bcc5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001bcc8  call    cs:__imp_WaitForSingleObject
0x18001bcce  mov     r9d, 1; bWait
0x18001bcd4  mov     r8, r12; lpNumberOfBytesTransferred
0x18001bcd7  mov     rdx, rbp; lpOverlapped
0x18001bcda  mov     rcx, r14; hFile
0x18001bcdd  call    cs:__imp_GetOverlappedResult
0x18001bce3  test    eax, eax
0x18001bce5  jz      short loc_18001BCEB
0x18001bce7  xor     ebx, ebx
0x18001bce9  jmp     short loc_18001BD00
0x18001bceb  call    cs:__imp_GetLastError
0x18001bcf1  mov     ebx, eax
0x18001bcf3  test    eax, eax
0x18001bcf5  jle     short loc_18001BD00
0x18001bcf7  movzx   ebx, ax
0x18001bcfa  or      ebx, 80070000h
0x18001bd00  test    ebx, ebx
0x18001bd02  js      short loc_18001BD29
0x18001bd04  cmp     ebx, 800704D5h
0x18001bd0a  jnz     short loc_18001BD29
0x18001bd0c  cmp     esi, 0Ah
0x18001bd0f  jb      loc_18001BC24
0x18001bd15  jmp     short loc_18001BD24
0x18001bd17  cmp     ebx, 800704D5h
0x18001bd1d  jnz     short loc_18001BD29
0x18001bd1f  cmp     esi, 0Ah
0x18001bd22  jb      short loc_18001BD29
0x18001bd24  mov     ebx, 800700AAh
0x18001bd29  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001bd2d  jz      short loc_18001BD38
0x18001bd2f  mov     rcx, rdi; hObject
0x18001bd32  call    cs:__imp_CloseHandle
0x18001bd38  mov     eax, ebx
0x18001bd3a  add     rsp, 70h
0x18001bd3e  pop     r14
0x18001bd40  pop     r13
0x18001bd42  pop     r12
0x18001bd44  pop     rdi
0x18001bd45  pop     rsi
0x18001bd46  pop     rbp
0x18001bd47  pop     rbx
0x18001bd48  retn
```
