# TlmInitialize

- ea: `0x1800119c4`
- end: `0x180011d10`
- name: `TlmInitialize`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180011200`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x1800119c4`
- `0x18001b568`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180011a92`
- `ntdll!RtlInitializeSRWLock` at `0x180011a9f`
- `ntdll!RtlInitializeSRWLock` at `0x180011aac`
- `ntdll!RtlInitializeSRWLock` at `0x180011ab9`
- `ntdll!RtlInitializeSRWLock` at `0x180011a92`
- `ntdll!RtlInitializeSRWLock` at `0x180011a9f`
- `ntdll!RtlInitializeSRWLock` at `0x180011aac`
- `ntdll!RtlInitializeSRWLock` at `0x180011ab9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180011afd`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180011afd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180011ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180011ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180011ac6`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180011ac6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180011cc4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180011cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011be9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011be9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011bf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011bf7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180011b8b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180011b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011cef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011b42`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011b42`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180011b17`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180011b17`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180011bc2`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180011c30`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180011bc2`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameW` at `0x180011c30`

## pseudocode

```c
int TlmInitialize()
{
  struct _PEB *v0; // rax
  __int64 FileW; // rdi
  char v2; // si
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  int v5; // edx
  DWORD pcbBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-B8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  int v12; // [rsp+88h] [rbp-78h]
  __int64 OutBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v14; // [rsp+98h] [rbp-68h]
  _MEMORYSTATUSEX Buffer; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR sz[8]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v17[264]; // [rsp+F0h] [rbp-10h] BYREF

  UnbiasedTime = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  memset_0(v17, 0, 0x208u);
  wcscpy(sz, L"\\\\.\\c:");
  memset_0(&Buffer, 0, sizeof(Buffer));
  InBuffer = 0;
  v12 = 0;
  OutBuffer = 0;
  v14 = 0;
  BytesReturned = 0;
  pcbBuffer = 0;
  v0 = NtCurrentPeb();
  if ( v0->Ldr->ShutdownInProgress )
    return (int)v0;
  FileW = -1;
  memset_0(&byte_180028930, 0, 0x268u);
  RtlInitializeSRWLock(&qword_180028940);
  RtlInitializeSRWLock(&qword_180028970);
  RtlInitializeSRWLock(&qword_1800289B8);
  RtlInitializeSRWLock(&qword_180028A60);
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
    qword_180028B70 = Buffer.ullTotalPhys >> 10;
  GetSystemInfo(&SystemInfo);
  dword_180028B78 = SystemInfo.dwNumberOfProcessors;
  if ( GetWindowsDirectoryW(v17, 0x104u) )
  {
    sz[4] = v17[0];
    CharLowerW(sz);
    FileW = (__int64)CreateFileW(sz, 0, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
    {
      LODWORD(InBuffer) = 7;
      DeviceIoControl((HANDLE)FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0xCu, &BytesReturned, 0);
    }
  }
  if ( BytesReturned - 1 > 0xB )
    dword_180028B7C = -1;
  else
    dword_180028B7C = (_BYTE)v14 == 0;
  v2 = 1;
  if ( !GetUserNameW(String2.Buffer, &pcbBuffer) )
  {
    v3 = (unsigned __int16)(2 * (pcbBuffer + 1));
    String2.MaximumLength = 2 * (pcbBuffer + 1);
    ProcessHeap = GetProcessHeap();
    v0 = (struct _PEB *)HeapAlloc(ProcessHeap, 0, v3);
    String2.Buffer = (PWSTR)&v0->InheritedAddressSpace;
    v5 = v0 == 0 ? 8 : 0;
    if ( !v0 )
      v5 |= 0x80070000;
    if ( v5 < 0 )
      goto LABEL_21;
    GetUserNameW((LPWSTR)&v0->BeingDebugged, &pcbBuffer);
    *String2.Buffer = 92;
    String2.Buffer[((unsigned __int64)String2.MaximumLength >> 1) - 1] = 92;
    String2.Length = String2.MaximumLength;
  }
  LODWORD(v0) = TlgRegisterAggregateProviderEx();
  if ( (int)v0 >= 0 )
  {
    byte_180028B80 = 1;
    if ( !dword_1800281A0
      || (qword_1800281B0 & 0x400000000000LL) == 0
      || (qword_1800281B8 & 0x400000000000LL) != qword_1800281B8 )
    {
      v2 = 0;
    }
    byte_180028930 = v2;
    dword_180028B60 = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    LODWORD(v0) = UnbiasedTime + 3600000;
    dword_180028B40 = 0;
    qword_180028B68 = UnbiasedTime + 3600000;
  }
LABEL_21:
  if ( FileW != -1 )
    LODWORD(v0) = CloseHandle((HANDLE)FileW);
  return (int)v0;
}

```

## disassembly

```asm
0x1800119c4  push    rbp
0x1800119c6  push    rbx
0x1800119c7  push    rsi
0x1800119c8  push    rdi
0x1800119c9  lea     rbp, [rsp-218h]
0x1800119d1  sub     rsp, 318h
0x1800119d8  mov     rax, cs:__security_cookie
0x1800119df  xor     rax, rsp
0x1800119e2  mov     [rbp+230h+var_30], rax
0x1800119e9  xorps   xmm0, xmm0
0x1800119ec  mov     [rsp+330h+UnbiasedTime], 0
0x1800119f5  xor     edx, edx; Val
0x1800119f7  lea     rcx, [rbp+230h+var_240]; void *
0x1800119fb  mov     r8d, 208h; Size
0x180011a01  movups  xmmword ptr [rsp+330h+SystemInfo], xmm0
0x180011a06  movups  xmmword ptr [rsp+330h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180011a0b  movups  xmmword ptr [rsp+330h+SystemInfo.dwNumberOfProcessors], xmm0
0x180011a10  call    memset_0
0x180011a15  mov     rax, 5C002E005C005Ch
0x180011a1f  mov     [rbp+230h+var_246], 3Ah ; ':'
0x180011a26  mov     qword ptr [rbp+230h+sz], rax
0x180011a2a  lea     rcx, [rbp+230h+Buffer]; void *
0x180011a2e  mov     eax, 63h ; 'c'
0x180011a33  xor     edx, edx; Val
0x180011a35  mov     [rbp+230h+var_248], ax
0x180011a39  lea     ebx, [rax-23h]
0x180011a3c  mov     r8d, ebx; Size
0x180011a3f  call    memset_0
0x180011a44  xor     eax, eax
0x180011a46  mov     [rbp+230h+InBuffer], rax
0x180011a4a  mov     [rbp+230h+var_2A8], eax
0x180011a4d  mov     [rbp+230h+OutBuffer], rax
0x180011a51  mov     [rbp+230h+var_298], eax
0x180011a54  mov     [rsp+330h+BytesReturned], eax
0x180011a58  mov     [rsp+330h+pcbBuffer], eax
0x180011a5c  mov     rax, gs:60h
0x180011a65  mov     rcx, [rax+18h]
0x180011a69  cmp     byte ptr [rcx+48h], 0
0x180011a6d  jnz     loc_180011CF5
0x180011a73  xor     edx, edx; Val
0x180011a75  lea     rcx, byte_180028930; void *
0x180011a7c  mov     r8d, 268h; Size
0x180011a82  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011a86  call    memset_0
0x180011a8b  lea     rcx, qword_180028940
0x180011a92  call    cs:__imp_RtlInitializeSRWLock
0x180011a98  lea     rcx, qword_180028970
0x180011a9f  call    cs:__imp_RtlInitializeSRWLock
0x180011aa5  lea     rcx, qword_1800289B8
0x180011aac  call    cs:__imp_RtlInitializeSRWLock
0x180011ab2  lea     rcx, qword_180028A60
0x180011ab9  call    cs:__imp_RtlInitializeSRWLock
0x180011abf  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x180011ac3  mov     [rbp+230h+Buffer.dwLength], ebx
0x180011ac6  call    cs:__imp_GlobalMemoryStatusEx
0x180011acc  test    eax, eax
0x180011ace  jz      short loc_180011ADF
0x180011ad0  mov     rax, [rbp+230h+Buffer.ullTotalPhys]
0x180011ad4  shr     rax, 0Ah
0x180011ad8  mov     cs:qword_180028B70, rax
0x180011adf  lea     rcx, [rsp+330h+SystemInfo]; lpSystemInfo
0x180011ae4  call    cs:__imp_GetSystemInfo
0x180011aea  mov     eax, [rsp+330h+SystemInfo.dwNumberOfProcessors]
0x180011aee  lea     rcx, [rbp+230h+var_240]; lpBuffer
0x180011af2  mov     edx, 104h; uSize
0x180011af7  mov     cs:dword_180028B78, eax
0x180011afd  call    cs:__imp_GetWindowsDirectoryW
0x180011b03  test    eax, eax
0x180011b05  jz      loc_180011B91
0x180011b0b  movzx   eax, [rbp+230h+var_240]
0x180011b0f  lea     rcx, [rbp+230h+sz]; lpsz
0x180011b13  mov     [rbp+230h+var_248], ax
0x180011b17  call    cs:__imp_CharLowerW
0x180011b1d  mov     r8d, 3; dwShareMode
0x180011b23  mov     [rsp+330h+hTemplateFile], 0; hTemplateFile
0x180011b2c  mov     [rsp+330h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180011b34  lea     rcx, [rbp+230h+sz]; lpFileName
0x180011b38  xor     r9d, r9d; lpSecurityAttributes
0x180011b3b  mov     [rsp+330h+dwCreationDisposition], r8d; dwCreationDisposition
0x180011b40  xor     edx, edx; dwDesiredAccess
0x180011b42  call    cs:__imp_CreateFileW
0x180011b48  mov     rdi, rax
0x180011b4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011b4f  jz      short loc_180011B91
0x180011b51  mov     [rsp+330h+lpOverlapped], 0; lpOverlapped
0x180011b5a  lea     rax, [rsp+330h+BytesReturned]
0x180011b5f  mov     [rsp+330h+hTemplateFile], rax; lpBytesReturned
0x180011b64  lea     r8, [rbp+230h+InBuffer]; lpInBuffer
0x180011b68  mov     r9d, 0Ch; nInBufferSize
0x180011b6e  mov     dword ptr [rbp+230h+InBuffer], 7
0x180011b75  lea     rax, [rbp+230h+OutBuffer]
0x180011b79  mov     [rsp+330h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x180011b7e  mov     edx, 2D1400h; dwIoControlCode
0x180011b83  mov     qword ptr [rsp+330h+dwCreationDisposition], rax; lpOutBuffer
0x180011b88  mov     rcx, rdi; hDevice
0x180011b8b  call    cs:__imp_DeviceIoControl
0x180011b91  mov     eax, [rsp+330h+BytesReturned]
0x180011b95  dec     eax
0x180011b97  cmp     eax, 0Bh
0x180011b9a  ja      short loc_180011BAC
0x180011b9c  xor     eax, eax
0x180011b9e  cmp     byte ptr [rbp+230h+var_298], al
0x180011ba1  setz    al
0x180011ba4  mov     cs:dword_180028B7C, eax
0x180011baa  jmp     short loc_180011BB6
0x180011bac  mov     cs:dword_180028B7C, 0FFFFFFFFh
0x180011bb6  mov     rcx, cs:String2.Buffer; lpBuffer
0x180011bbd  lea     rdx, [rsp+330h+pcbBuffer]; pcbBuffer
0x180011bc2  call    cs:__imp_GetUserNameW
0x180011bc8  mov     si, 1
0x180011bcc  test    eax, eax
0x180011bce  jnz     loc_180011C69
0x180011bd4  movzx   eax, word ptr [rsp+330h+pcbBuffer]
0x180011bd9  add     ax, si
0x180011bdc  add     ax, ax
0x180011bdf  movzx   ebx, ax
0x180011be2  mov     cs:String2.MaximumLength, bx
0x180011be9  call    cs:__imp_GetProcessHeap
0x180011bef  mov     r8d, ebx; dwBytes
0x180011bf2  xor     edx, edx; dwFlags
0x180011bf4  mov     rcx, rax; hHeap
0x180011bf7  call    cs:__imp_HeapAlloc
0x180011bfd  mov     rcx, rax
0x180011c00  mov     cs:String2.Buffer, rax
0x180011c07  neg     rcx
0x180011c0a  sbb     edx, edx
0x180011c0c  not     edx
0x180011c0e  and     edx, 8
0x180011c11  mov     ecx, edx
0x180011c13  or      ecx, 80070000h
0x180011c19  test    rax, rax
0x180011c1c  cmovz   edx, ecx
0x180011c1f  test    edx, edx
0x180011c21  js      loc_180011CE6
0x180011c27  lea     rcx, [rax+2]; lpBuffer
0x180011c2b  lea     rdx, [rsp+330h+pcbBuffer]; pcbBuffer
0x180011c30  call    cs:__imp_GetUserNameW
0x180011c36  mov     rax, cs:String2.Buffer
0x180011c3d  mov     edx, 5Ch ; '\'
0x180011c42  mov     [rax], dx
0x180011c45  movzx   ecx, cs:String2.MaximumLength
0x180011c4c  mov     rax, cs:String2.Buffer
0x180011c53  shr     rcx, 1
0x180011c56  mov     [rax+rcx*2-2], dx
0x180011c5b  movzx   eax, cs:String2.MaximumLength
0x180011c62  mov     cs:String2.Length, ax
0x180011c69  call    TlgRegisterAggregateProviderEx
0x180011c6e  test    eax, eax
0x180011c70  js      short loc_180011CE6
0x180011c72  mov     eax, cs:dword_1800281A0
0x180011c78  mov     cs:byte_180028B80, sil
0x180011c7f  test    eax, eax
0x180011c81  jz      short loc_180011CAB
0x180011c83  mov     rcx, cs:qword_1800281B8
0x180011c8a  mov     rdx, 400000000000h
0x180011c94  mov     rax, cs:qword_1800281B0
0x180011c9b  test    rdx, rax
0x180011c9e  jz      short loc_180011CAB
0x180011ca0  mov     rax, rcx
0x180011ca3  and     rax, rdx
0x180011ca6  cmp     rax, rcx
0x180011ca9  jz      short loc_180011CAE
0x180011cab  xor     sil, sil
0x180011cae  lea     rcx, [rsp+330h+UnbiasedTime]; UnbiasedTime
0x180011cb3  mov     cs:byte_180028930, sil
0x180011cba  mov     cs:dword_180028B60, 0
0x180011cc4  call    cs:__imp_QueryUnbiasedInterruptTime
0x180011cca  mov     rax, [rsp+330h+UnbiasedTime]
0x180011ccf  add     rax, 36EE80h
0x180011cd5  mov     cs:dword_180028B40, 0
0x180011cdf  mov     cs:qword_180028B68, rax
0x180011ce6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180011cea  jz      short loc_180011CF5
0x180011cec  mov     rcx, rdi; hObject
0x180011cef  call    cs:__imp_CloseHandle
0x180011cf5  mov     rcx, [rbp+230h+var_30]
0x180011cfc  xor     rcx, rsp; StackCookie
0x180011cff  call    __security_check_cookie
0x180011d04  add     rsp, 318h
0x180011d0b  pop     rdi
0x180011d0c  pop     rsi
0x180011d0d  pop     rbx
0x180011d0e  pop     rbp
0x180011d0f  retn
```
