# KsSynchronousDeviceControl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x1800c588c`
- end: `0x1800c5b2d`
- name: `?KsSynchronousDeviceControl@@YAJPEAXK0K0KPEAK@Z`
- size: `673`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void *, DWORD, LPDWORD)`
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x18008c758`
- `0x1800c3b6c`
- `0x1800c40f0`
- `0x1800c4160`
- `0x1800c4a80`
- `0x1800c5170`
- `0x1800c51e0`
- `0x1800c5630`
- `0x1800c56a0`
- `0x1800c56e0`
- `0x1800c5b40`
- `0x1800c6610`
- `0x1800c715c`
- `0x1800c739c`
- `0x1800c7610`
- `0x1800cf90c`
- `0x180133144`
- `0x1801333d8`
- `0x1801566d8`
- `0x18015747c`
- `0x18017ad70`
- `0x18017c880`
- `0x18018dca0`
- `0x1802d1710`
- `0x1802d5120`
- `0x1802e6a68`
- `0x1802e94bc`
- `0x1802e9e20`
- `0x1802ea0b0`
- `0x1802ea3f0`
- `0x1802ea690`
- `0x1802eade0`
- `0x1802eb098`
- `0x1802eb708`
- `0x1802ec240`
- `0x1802ec310`
- `0x1802ec350`

## callees

- `0x1800c588c`
- `0x1801859e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c58d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c58d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c590c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c59f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c590c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c59f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c58e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c5a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c58e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c5a79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5aa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5aa5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c596e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c596e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800c59d6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800c59d6`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800c58f9`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800c5a8f`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800c58f9`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800c5a8f`

## pseudocode

```c
__int64 __fastcall KsSynchronousDeviceControl(
        char *hFile,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpBytesReturned)
{
  signed int v11; // edi
  HANDLE CurrentThread; // rax
  signed int v13; // eax
  int v14; // ebx
  LPDWORD v15; // rsi
  signed int LastError; // eax
  signed int v17; // eax
  HANDLE v18; // rax
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-60h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+B0h] [rbp+8h] BYREF

  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 2147942406LL;
  v11 = 0;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"mfdebucketize_kssynchronouscontrol");
  if ( Overlapped.hEvent )
  {
    v15 = lpBytesReturned;
    if ( DeviceIoControl(
           hFile,
           dwIoControlCode,
           lpInBuffer,
           nInBufferSize,
           lpOutBuffer,
           nOutBufferSize,
           lpBytesReturned,
           &Overlapped) )
    {
      if ( Overlapped.Internal )
      {
        switch ( Overlapped.Internal )
        {
          case 0x101uLL:
            v14 = -2147024875;
            break;
          case 0x102uLL:
            v14 = -2147023436;
            break;
          case 0x105uLL:
            v14 = -2147024662;
            break;
          case 0x107uLL:
            v14 = -2147023595;
            break;
          default:
            v14 = LODWORD(Overlapped.Internal) | 0x10000000;
            break;
        }
        goto LABEL_28;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      if ( v14 != -2147023899 )
        goto LABEL_28;
      NumberOfBytesTransferred = 0;
      if ( !GetOverlappedResult(hFile, &Overlapped, &NumberOfBytesTransferred, 1) )
      {
        v17 = GetLastError();
        v11 = v17;
        if ( v17 > 0 )
          v14 = (unsigned __int16)v17 | 0x80070000;
        else
          v14 = v17;
        goto LABEL_28;
      }
      if ( v15 )
        *v15 = NumberOfBytesTransferred;
    }
    v14 = 0;
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    else
      v14 = v13;
  }
LABEL_28:
  v18 = GetCurrentThread();
  SetThreadDescription(v18, &word_18037A70C);
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = 0;
  }
  if ( v14 != -2147024846
    && v14 != -2147023726
    && v14 != -2147023728
    && v14 != -2147024662
    && v14 != -2147024774
    && v14 < 0
    && (unsigned __int8)byte_1803CECED >= 8u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      10,
      &WPP_5e8348319e53326237fea3d85cdb3c95_Traceguids,
      (unsigned int)v14,
      v11);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800c588c  push    rbx
0x1800c588e  push    rsi
0x1800c588f  push    rdi
0x1800c5890  push    r12
0x1800c5892  push    r14
0x1800c5894  push    r15
0x1800c5896  sub     rsp, 78h
0x1800c589a  mov     ebx, r9d
0x1800c589d  mov     r15, r8
0x1800c58a0  mov     r12d, edx
0x1800c58a3  mov     r14, rcx
0x1800c58a6  lea     rax, [rcx-1]
0x1800c58aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c58ae  ja      loc_1800C5B19
0x1800c58b4  xor     edi, edi
0x1800c58b6  mov     [rsp+0A8h+var_64], edi
0x1800c58ba  xorps   xmm0, xmm0
0x1800c58bd  movups  xmmword ptr [rsp+0A8h+Overlapped.Internal], xmm0
0x1800c58c2  movups  xmmword ptr [rsp+0A8h+Overlapped.10h], xmm0
0x1800c58c7  xor     r9d, r9d; lpName
0x1800c58ca  xor     r8d, r8d; bInitialState
0x1800c58cd  lea     edx, [rdi+1]; bManualReset
0x1800c58d0  xor     ecx, ecx; lpEventAttributes
0x1800c58d2  call    cs:__imp_CreateEventW
0x1800c58d9  nop     dword ptr [rax+rax+00h]
0x1800c58de  mov     [rsp+0A8h+Overlapped.hEvent], rax
0x1800c58e3  call    cs:__imp_GetCurrentThread
0x1800c58ea  nop     dword ptr [rax+rax+00h]
0x1800c58ef  mov     rcx, rax; hThread
0x1800c58f2  lea     rdx, ThreadDescription; "mfdebucketize_kssynchronouscontrol"
0x1800c58f9  call    cs:__imp_SetThreadDescription
0x1800c5900  nop     dword ptr [rax+rax+00h]
0x1800c5905  cmp     [rsp+0A8h+Overlapped.hEvent], rdi
0x1800c590a  jnz     short loc_1800C5933
0x1800c590c  call    cs:__imp_GetLastError
0x1800c5913  nop     dword ptr [rax+rax+00h]
0x1800c5918  mov     edi, eax
0x1800c591a  test    eax, eax
0x1800c591c  jg      short loc_1800C5925
0x1800c591e  mov     ebx, eax
0x1800c5920  jmp     loc_1800C5A79
0x1800c5925  movzx   ebx, ax
0x1800c5928  or      ebx, 80070000h
0x1800c592e  jmp     loc_1800C5A79
0x1800c5933  lea     rax, [rsp+0A8h+Overlapped]
0x1800c5938  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x1800c593d  mov     rsi, [rsp+0A8h+arg_30]
0x1800c5945  mov     [rsp+0A8h+lpBytesReturned], rsi; lpBytesReturned
0x1800c594a  mov     eax, [rsp+0A8h+arg_28]
0x1800c5951  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x1800c5955  mov     rax, [rsp+0A8h+arg_20]
0x1800c595d  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x1800c5962  mov     r9d, ebx; nInBufferSize
0x1800c5965  mov     r8, r15; lpInBuffer
0x1800c5968  mov     edx, r12d; dwIoControlCode
0x1800c596b  mov     rcx, r14; hDevice
0x1800c596e  call    cs:__imp_DeviceIoControl
0x1800c5975  nop     dword ptr [rax+rax+00h]
0x1800c597a  test    eax, eax
0x1800c597c  jnz     loc_1800C5A1B
0x1800c5982  call    cs:__imp_GetLastError
0x1800c5989  nop     dword ptr [rax+rax+00h]
0x1800c598e  mov     edi, eax
0x1800c5990  mov     [rsp+0A8h+var_64], eax
0x1800c5994  test    eax, eax
0x1800c5996  jg      short loc_1800C599C
0x1800c5998  mov     ebx, eax
0x1800c599a  jmp     short loc_1800C59A5
0x1800c599c  movzx   ebx, ax
0x1800c599f  or      ebx, 80070000h
0x1800c59a5  mov     [rsp+0A8h+var_68], ebx
0x1800c59a9  cmp     ebx, 800703E5h
0x1800c59af  jnz     loc_1800C5A6A
0x1800c59b5  mov     [rsp+0A8h+NumberOfBytesTransferred], 0
0x1800c59c0  mov     r9d, 1; bWait
0x1800c59c6  lea     r8, [rsp+0A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800c59ce  lea     rdx, [rsp+0A8h+Overlapped]; lpOverlapped
0x1800c59d3  mov     rcx, r14; hFile
0x1800c59d6  call    cs:__imp_GetOverlappedResult
0x1800c59dd  nop     dword ptr [rax+rax+00h]
0x1800c59e2  test    eax, eax
0x1800c59e4  jz      short loc_1800C59F6
0x1800c59e6  test    rsi, rsi
0x1800c59e9  jz      short loc_1800C5A64
0x1800c59eb  mov     eax, [rsp+0A8h+NumberOfBytesTransferred]
0x1800c59f2  mov     [rsi], eax
0x1800c59f4  jmp     short loc_1800C5A64
0x1800c59f6  call    cs:__imp_GetLastError
0x1800c59fd  nop     dword ptr [rax+rax+00h]
0x1800c5a02  mov     edi, eax
0x1800c5a04  mov     [rsp+0A8h+var_64], eax
0x1800c5a08  test    eax, eax
0x1800c5a0a  jg      short loc_1800C5A10
0x1800c5a0c  mov     ebx, eax
0x1800c5a0e  jmp     short loc_1800C5A66
0x1800c5a10  movzx   ebx, ax
0x1800c5a13  or      ebx, 80070000h
0x1800c5a19  jmp     short loc_1800C5A66
0x1800c5a1b  mov     rbx, [rsp+0A8h+Overlapped.Internal]
0x1800c5a20  mov     rax, rbx
0x1800c5a23  test    rbx, rbx
0x1800c5a26  jz      short loc_1800C5A64
0x1800c5a28  sub     rax, 101h
0x1800c5a2e  jz      short loc_1800C5A5D
0x1800c5a30  sub     rax, 1
0x1800c5a34  jz      short loc_1800C5A56
0x1800c5a36  sub     rax, 3
0x1800c5a3a  jz      short loc_1800C5A4F
0x1800c5a3c  cmp     rax, 2
0x1800c5a40  jz      short loc_1800C5A48
0x1800c5a42  bts     ebx, 1Ch
0x1800c5a46  jmp     short loc_1800C5A66
0x1800c5a48  mov     ebx, 80070515h
0x1800c5a4d  jmp     short loc_1800C5A66
0x1800c5a4f  mov     ebx, 800700EAh
0x1800c5a54  jmp     short loc_1800C5A66
0x1800c5a56  mov     ebx, 800705B4h
0x1800c5a5b  jmp     short loc_1800C5A66
0x1800c5a5d  mov     ebx, 80070015h
0x1800c5a62  jmp     short loc_1800C5A66
0x1800c5a64  xor     ebx, ebx
0x1800c5a66  mov     [rsp+0A8h+var_68], ebx
0x1800c5a6a  jmp     short loc_1800C5A79
0x1800c5a6c  mov     ebx, 0C0000008h
0x1800c5a71  mov     [rsp+0A8h+var_68], ebx
0x1800c5a75  mov     edi, [rsp+0A8h+var_64]
0x1800c5a79  call    cs:__imp_GetCurrentThread
0x1800c5a80  nop     dword ptr [rax+rax+00h]
0x1800c5a85  mov     rcx, rax; hThread
0x1800c5a88  lea     rdx, word_18037A70C; lpThreadDescription
0x1800c5a8f  call    cs:__imp_SetThreadDescription
0x1800c5a96  nop     dword ptr [rax+rax+00h]
0x1800c5a9b  mov     rcx, [rsp+0A8h+Overlapped.hEvent]; hObject
0x1800c5aa0  test    rcx, rcx
0x1800c5aa3  jz      short loc_1800C5ABA
0x1800c5aa5  call    cs:__imp_CloseHandle
0x1800c5aac  nop     dword ptr [rax+rax+00h]
0x1800c5ab1  mov     [rsp+0A8h+Overlapped.hEvent], 0
0x1800c5aba  cmp     ebx, 80070032h
0x1800c5ac0  jz      short loc_1800C5B15
0x1800c5ac2  cmp     ebx, 80070492h
0x1800c5ac8  jz      short loc_1800C5B15
0x1800c5aca  cmp     ebx, 80070490h
0x1800c5ad0  jz      short loc_1800C5B15
0x1800c5ad2  cmp     ebx, 800700EAh
0x1800c5ad8  jz      short loc_1800C5B15
0x1800c5ada  cmp     ebx, 8007007Ah
0x1800c5ae0  jz      short loc_1800C5B15
0x1800c5ae2  test    ebx, ebx
0x1800c5ae4  jns     short loc_1800C5B15
0x1800c5ae6  cmp     cs:byte_1803CECED, 8
0x1800c5aed  jb      short loc_1800C5B15
0x1800c5aef  mov     edx, 0Ah
0x1800c5af4  mov     dword ptr [rsp+0A8h+lpOutBuffer], edi
0x1800c5af8  mov     r9d, ebx
0x1800c5afb  lea     r8, WPP_5e8348319e53326237fea3d85cdb3c95_Traceguids
0x1800c5b02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5b09  mov     rcx, [rcx+0D8h]
0x1800c5b10  call    WPP_SF_Dd
0x1800c5b15  mov     eax, ebx
0x1800c5b17  jmp     short loc_1800C5B1E
0x1800c5b19  mov     eax, 80070006h
0x1800c5b1e  add     rsp, 78h
0x1800c5b22  pop     r15
0x1800c5b24  pop     r14
0x1800c5b26  pop     r12
0x1800c5b28  pop     rdi
0x1800c5b29  pop     rsi
0x1800c5b2a  pop     rbx
0x1800c5b2b  retn
0x180344d6c  push    rbp
0x180344d6e  sub     rsp, 40h
0x180344d72  mov     rbp, rdx
0x180344d75  mov     rax, [rcx]
0x180344d78  xor     ecx, ecx
0x180344d7a  cmp     dword ptr [rax], 0C0000008h
0x180344d80  setz    cl
0x180344d83  mov     eax, ecx
0x180344d85  add     rsp, 40h
0x180344d89  pop     rbp
0x180344d8a  retn
```
