# CreateDevice

- ea: `0x180099da0`
- end: `0x180099f5a`
- name: `CreateDevice`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180099f60`

## callees

- `0x180099da0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e63`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099e4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099e4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099dd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099dd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099eb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099ecb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099ef6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099eb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099ecb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099ef6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099f23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099f23`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180099e96`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180099e96`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180099e39`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180099e39`

## pseudocode

```c
__int64 __fastcall CreateDevice(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  signed int LastError; // eax
  signed int v7; // ebx
  DWORD v8; // eax
  signed int v9; // eax
  HANDLE v10; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v13; // rax
  HANDLE hHandle[2]; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-18h]
  __int64 v16; // [rsp+A0h] [rbp+38h] BYREF

  v16 = 0;
  *(_OWORD *)hHandle = 0;
  *(_OWORD *)lpMem = 0;
  hHandle[0] = CreateEventW(0, 0, 0, 0);
  if ( !hHandle[0] )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    if ( v7 >= 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
  v7 = SwDeviceCreate(
         L"MSRRAS",
         L"SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}",
         a1,
         0,
         0,
         &RrasSwDeviceCreateCallback,
         hHandle,
         &v16);
  if ( v7 >= 0 )
  {
    v8 = WaitForSingleObject(hHandle[0], 0x7530u);
    if ( v8 )
    {
      if ( v8 == 258 )
      {
        v7 = -2147023436;
        goto LABEL_13;
      }
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v7 < 0 )
        goto LABEL_13;
    }
    if ( SLODWORD(lpMem[0]) < 0 )
    {
      v7 = (signed int)lpMem[0];
      goto LABEL_12;
    }
    ProcessHeap = GetProcessHeap();
    v13 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v13 )
    {
      v13[1] = v16;
      *v13 = lpMem[1];
      lpMem[1] = 0;
      *a4 = v13;
      goto LABEL_15;
    }
    v7 = -2147024882;
  }
LABEL_13:
  if ( v16 )
    SwDeviceClose();
LABEL_15:
  if ( hHandle[0] )
    CloseHandle(hHandle[0]);
  if ( lpMem[1] )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, lpMem[1]);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180099da0  mov     [rsp-20h+arg_10], r8
0x180099da5  push    rbp
0x180099da6  push    rbx
0x180099da7  push    rsi
0x180099da8  push    rdi
0x180099da9  mov     rbp, rsp
0x180099dac  sub     rsp, 68h
0x180099db0  xorps   xmm0, xmm0
0x180099db3  mov     [rbp+arg_10], 0
0x180099dbb  mov     rsi, r9
0x180099dbe  mov     rbx, rcx
0x180099dc1  xor     r9d, r9d; lpName
0x180099dc4  xor     ecx, ecx; lpEventAttributes
0x180099dc6  xor     r8d, r8d; bInitialState
0x180099dc9  xor     edx, edx; bManualReset
0x180099dcb  movups  xmmword ptr [rbp+hHandle], xmm0
0x180099dcf  xor     edi, edi
0x180099dd1  movups  xmmword ptr [rbp+lpMem], xmm0
0x180099dd5  call    cs:__imp_CreateEventW
0x180099ddb  mov     [rbp+hHandle], rax
0x180099ddf  test    rax, rax
0x180099de2  jnz     short loc_180099E02
0x180099de4  call    cs:__imp_GetLastError
0x180099dea  mov     ebx, eax
0x180099dec  test    eax, eax
0x180099dee  jle     loc_180099E89
0x180099df4  movzx   ebx, ax
0x180099df7  or      ebx, 80070000h
0x180099dfd  jmp     loc_180099E89
0x180099e02  lea     rax, [rbp+arg_10]
0x180099e06  xor     r9d, r9d
0x180099e09  mov     [rsp+68h+var_30], rax
0x180099e0e  lea     rdx, aSwdMsrras5e259; "SWD\\MSRRAS\\{5e259276-bc7e-40e3-b93b-8"...
0x180099e15  lea     rax, [rbp+hHandle]
0x180099e19  mov     r8, rbx
0x180099e1c  mov     [rsp+68h+var_38], rax
0x180099e21  lea     rcx, aMsrras; "MSRRAS"
0x180099e28  lea     rax, RrasSwDeviceCreateCallback
0x180099e2f  mov     [rsp+68h+var_40], rax
0x180099e34  mov     [rsp+68h+var_48], rdi
0x180099e39  call    cs:__imp_SwDeviceCreate
0x180099e3f  mov     ebx, eax
0x180099e41  test    eax, eax
0x180099e43  js      short loc_180099E8D
0x180099e45  mov     rcx, [rbp+hHandle]; hHandle
0x180099e49  mov     edx, 7530h; dwMilliseconds
0x180099e4e  call    cs:__imp_WaitForSingleObject
0x180099e54  test    eax, eax
0x180099e56  jz      short loc_180099E7C
0x180099e58  cmp     eax, 102h
0x180099e5d  jz      loc_180099F07
0x180099e63  call    cs:__imp_GetLastError
0x180099e69  mov     ebx, eax
0x180099e6b  test    eax, eax
0x180099e6d  jle     short loc_180099E78
0x180099e6f  movzx   ebx, ax
0x180099e72  or      ebx, 80070000h
0x180099e78  test    ebx, ebx
0x180099e7a  js      short loc_180099E8D
0x180099e7c  mov     eax, dword ptr [rbp+lpMem]
0x180099e7f  test    eax, eax
0x180099e81  jns     loc_180099F11
0x180099e87  mov     ebx, eax
0x180099e89  test    ebx, ebx
0x180099e8b  jns     short loc_180099ED1
0x180099e8d  mov     rcx, [rbp+arg_10]
0x180099e91  test    rcx, rcx
0x180099e94  jz      short loc_180099E9C
0x180099e96  call    cs:__imp_SwDeviceClose
0x180099e9c  test    rdi, rdi
0x180099e9f  jz      short loc_180099ED1
0x180099ea1  mov     rsi, [rdi]
0x180099ea4  test    rsi, rsi
0x180099ea7  jz      short loc_180099EBD
0x180099ea9  call    cs:__imp_GetProcessHeap
0x180099eaf  mov     r8, rsi; lpMem
0x180099eb2  xor     edx, edx; dwFlags
0x180099eb4  mov     rcx, rax; hHeap
0x180099eb7  call    cs:__imp_HeapFree
0x180099ebd  call    cs:__imp_GetProcessHeap
0x180099ec3  mov     r8, rdi; lpMem
0x180099ec6  xor     edx, edx; dwFlags
0x180099ec8  mov     rcx, rax; hHeap
0x180099ecb  call    cs:__imp_HeapFree
0x180099ed1  mov     rcx, [rbp+hHandle]; hObject
0x180099ed5  test    rcx, rcx
0x180099ed8  jz      short loc_180099EE0
0x180099eda  call    cs:__imp_CloseHandle
0x180099ee0  cmp     [rbp+lpMem+8], 0
0x180099ee5  jz      short loc_180099EFC
0x180099ee7  call    cs:__imp_GetProcessHeap
0x180099eed  mov     r8, [rbp+lpMem+8]; lpMem
0x180099ef1  xor     edx, edx; dwFlags
0x180099ef3  mov     rcx, rax; hHeap
0x180099ef6  call    cs:__imp_HeapFree
0x180099efc  mov     eax, ebx
0x180099efe  add     rsp, 68h
0x180099f02  pop     rdi
0x180099f03  pop     rsi
0x180099f04  pop     rbx
0x180099f05  pop     rbp
0x180099f06  retn
0x180099f07  mov     ebx, 800705B4h
0x180099f0c  jmp     loc_180099E8D
0x180099f11  call    cs:__imp_GetProcessHeap
0x180099f17  mov     edx, 8; dwFlags
0x180099f1c  mov     rcx, rax; hHeap
0x180099f1f  lea     r8d, [rdx+8]; dwBytes
0x180099f23  call    cs:__imp_HeapAlloc
0x180099f29  mov     rdi, rax
0x180099f2c  test    rax, rax
0x180099f2f  jnz     short loc_180099F3B
0x180099f31  mov     ebx, 8007000Eh
0x180099f36  jmp     loc_180099E8D
0x180099f3b  mov     rax, [rbp+arg_10]
0x180099f3f  mov     [rdi+8], rax
0x180099f43  mov     rax, [rbp+lpMem+8]
0x180099f47  mov     [rdi], rax
0x180099f4a  mov     [rbp+lpMem+8], 0
0x180099f52  mov     [rsi], rdi
0x180099f55  jmp     loc_180099ED1
```
