# SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)

- ea: `0x1801a8374`
- end: `0x1801a85ea`
- name: `?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _VOLUME_DISK_EXTENTS **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801a8fa8`
- `0x1801aa3c8`

## callees

- `0x180006290`
- `0x1801a8374`
- `0x1801a9974`
- `0x1801ab1bc`
- `0x1801ab268`
- `0x1801ab4a0`
- `0x1801ab4d0`
- `0x1801ab5c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a84c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a84c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a85b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a85b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a84fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a84fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a84b7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a854b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a84b7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a854b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a845f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a845f`

## pseudocode

```c
__int64 __fastcall SxGetDiskExts(const unsigned __int16 *a1, struct _VOLUME_DISK_EXTENTS **a2)
{
  __int64 FileW; // rbx
  struct _VOLUME_DISK_EXTENTS *v5; // rdi
  __int16 v6; // ax
  unsigned __int16 v7; // dx
  DWORD v8; // r14d
  unsigned int v9; // edi
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-41h] BYREF
  __int16 v13; // [rsp+4Ch] [rbp-3Dh]
  __int16 v14; // [rsp+4Eh] [rbp-3Bh]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-9h] BYREF
  _OWORD OutBuffer[2]; // [rsp+90h] [rbp+7h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetDiskExts", 0x989u, 1u);
  lpFileName[0] = (LPCWSTR)qword_1802DEE50;
  FileW = -1;
  BytesReturned = 0;
  lpFileName[1] = 0;
  v5 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( a2 )
    *a2 = 0;
  v6 = 2451;
  if ( !a1 || (v13 = 2451, v6 = 2452, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_5:
    v14 = v6;
    goto LABEL_20;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2452;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a1);
  v6 = 2454;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_5;
  v13 = 2454;
  CBsString::UnTrailing((CBsString *)lpFileName, v7);
  FileW = (__int64)CreateFileW(lpFileName[0], 0, 3u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2464;
    goto LABEL_5;
  }
  v13 = 2464;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) && GetLastError() != 234 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2475;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2475;
  v8 = 24 * LODWORD(OutBuffer[0]) + 8;
  v5 = (struct _VOLUME_DISK_EXTENTS *)CoTaskMemAlloc(v8);
  v6 = 2480;
  if ( !v5 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_5;
  }
  v13 = 2480;
  LastFailureAsHRESULT = 0;
  if ( !DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v5, v8, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v6 = 2489;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2489;
  v6 = 2490;
  if ( !v5->NumberOfDiskExtents )
  {
    LastFailureAsHRESULT = -2147418113;
    goto LABEL_5;
  }
  *a2 = v5;
  v5 = 0;
  v13 = 2490;
LABEL_20:
  CoTaskMemFree(v5);
  v9 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x1801a8374  mov     [rsp-8+arg_10], rbx
0x1801a8379  push    rbp
0x1801a837a  push    rsi
0x1801a837b  push    rdi
0x1801a837c  push    r14
0x1801a837e  push    r15
0x1801a8380  lea     rbp, [rsp-37h]
0x1801a8385  sub     rsp, 0C0h
0x1801a838c  mov     rax, cs:__security_cookie
0x1801a8393  xor     rax, rsp
0x1801a8396  mov     [rbp+57h+var_30], rax
0x1801a839a  mov     rsi, rdx
0x1801a839d  mov     r14, rcx
0x1801a83a0  lea     rdx, aSxgetdiskexts; "SxGetDiskExts"
0x1801a83a7  mov     r9d, 1; unsigned __int16
0x1801a83ad  lea     rcx, [rbp+57h+var_98]; this
0x1801a83b1  mov     r8d, 989h; unsigned __int16
0x1801a83b7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801a83bc  xor     r15d, r15d
0x1801a83bf  lea     rax, qword_1802DEE50
0x1801a83c6  xorps   xmm0, xmm0
0x1801a83c9  mov     [rbp+57h+lpFileName], rax
0x1801a83cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801a83d1  mov     [rbp+57h+BytesReturned], r15d
0x1801a83d5  mov     [rbp+57h+var_58], r15
0x1801a83d9  mov     edi, r15d
0x1801a83dc  movups  [rbp+57h+OutBuffer], xmm0
0x1801a83e0  movups  [rbp+57h+var_40], xmm0
0x1801a83e4  test    rsi, rsi
0x1801a83e7  jz      short loc_1801A83EC
0x1801a83e9  mov     [rsi], r15
0x1801a83ec  mov     eax, 993h
0x1801a83f1  test    r14, r14
0x1801a83f4  jnz     short loc_1801A8406
0x1801a83f6  mov     [rbp+57h+var_98], 80070057h
0x1801a83fd  mov     [rbp+57h+var_92], ax
0x1801a8401  jmp     loc_1801A8594
0x1801a8406  mov     [rbp+57h+var_94], ax
0x1801a840a  mov     eax, 994h
0x1801a840f  test    rsi, rsi
0x1801a8412  jz      short loc_1801A83F6
0x1801a8414  mov     rdx, r14; unsigned __int16 *
0x1801a8417  mov     [rbp+57h+var_98], r15d
0x1801a841b  lea     rcx, [rbp+57h+lpFileName]; this
0x1801a841f  mov     [rbp+57h+var_94], ax
0x1801a8423  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801a8428  mov     [rbp+57h+var_98], eax
0x1801a842b  test    eax, eax
0x1801a842d  mov     eax, 996h
0x1801a8432  js      short loc_1801A83FD
0x1801a8434  lea     rcx, [rbp+57h+lpFileName]; this
0x1801a8438  mov     [rbp+57h+var_94], ax
0x1801a843c  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801a8441  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1801a8445  mov     r8d, 3; dwShareMode
0x1801a844b  mov     [rsp+0E0h+hTemplateFile], r15; hTemplateFile
0x1801a8450  xor     r9d, r9d; lpSecurityAttributes
0x1801a8453  mov     [rsp+0E0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801a8458  xor     edx, edx; dwDesiredAccess
0x1801a845a  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801a845f  call    cs:__imp_CreateFileW
0x1801a8465  mov     rbx, rax
0x1801a8468  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a846c  jnz     short loc_1801A847D
0x1801a846e  call    GetLastFailureAsHRESULT
0x1801a8473  mov     [rbp+57h+var_98], eax
0x1801a8476  mov     eax, 9A0h
0x1801a847b  jmp     short loc_1801A83FD
0x1801a847d  mov     [rsp+0E0h+lpOverlapped], r15; lpOverlapped
0x1801a8482  mov     eax, 9A0h
0x1801a8487  mov     [rbp+57h+var_94], ax
0x1801a848b  xor     r9d, r9d; nInBufferSize
0x1801a848e  lea     rax, [rbp+57h+BytesReturned]
0x1801a8492  mov     [rbp+57h+var_98], r15d
0x1801a8496  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1801a849b  xor     r8d, r8d; lpInBuffer
0x1801a849e  lea     rax, [rbp+57h+OutBuffer]
0x1801a84a2  mov     [rsp+0E0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x1801a84aa  mov     edx, 560000h; dwIoControlCode
0x1801a84af  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x1801a84b4  mov     rcx, rbx; hDevice
0x1801a84b7  call    cs:__imp_DeviceIoControl
0x1801a84bd  test    eax, eax
0x1801a84bf  jnz     short loc_1801A84E0
0x1801a84c1  call    cs:__imp_GetLastError
0x1801a84c7  cmp     eax, 0EAh
0x1801a84cc  jz      short loc_1801A84E0
0x1801a84ce  call    GetLastFailureAsHRESULT
0x1801a84d3  mov     [rbp+57h+var_98], eax
0x1801a84d6  mov     eax, 9ABh
0x1801a84db  jmp     loc_1801A83FD
0x1801a84e0  mov     eax, 9ABh
0x1801a84e5  mov     [rbp+57h+var_98], r15d
0x1801a84e9  mov     [rbp+57h+var_94], ax
0x1801a84ed  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x1801a84f0  lea     ecx, [rax+rax*2]
0x1801a84f3  lea     r14d, ds:8[rcx*8]
0x1801a84fb  mov     ecx, r14d; cb
0x1801a84fe  call    cs:__imp_CoTaskMemAlloc
0x1801a8504  mov     rdi, rax
0x1801a8507  test    rax, rax
0x1801a850a  mov     eax, 9B0h
0x1801a850f  jnz     short loc_1801A851D
0x1801a8511  mov     [rbp+57h+var_98], 8007000Eh
0x1801a8518  jmp     loc_1801A83FD
0x1801a851d  mov     [rsp+0E0h+lpOverlapped], r15; lpOverlapped
0x1801a8522  xor     r9d, r9d; nInBufferSize
0x1801a8525  mov     [rbp+57h+var_94], ax
0x1801a8529  xor     r8d, r8d; lpInBuffer
0x1801a852c  lea     rax, [rbp+57h+BytesReturned]
0x1801a8530  mov     [rbp+57h+var_98], r15d
0x1801a8534  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1801a8539  mov     edx, 560000h; dwIoControlCode
0x1801a853e  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1801a8543  mov     rcx, rbx; hDevice
0x1801a8546  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rdi; lpOutBuffer
0x1801a854b  call    cs:__imp_DeviceIoControl
0x1801a8551  test    eax, eax
0x1801a8553  jnz     short loc_1801A8567
0x1801a8555  call    GetLastFailureAsHRESULT
0x1801a855a  mov     [rbp+57h+var_98], eax
0x1801a855d  mov     eax, 9B9h
0x1801a8562  jmp     loc_1801A83FD
0x1801a8567  mov     eax, 9B9h
0x1801a856c  mov     [rbp+57h+var_98], r15d
0x1801a8570  mov     [rbp+57h+var_94], ax
0x1801a8574  mov     eax, 9BAh
0x1801a8579  cmp     [rdi], r15d
0x1801a857c  jnz     short loc_1801A858A
0x1801a857e  mov     [rbp+57h+var_98], 8000FFFFh
0x1801a8585  jmp     loc_1801A83FD
0x1801a858a  mov     [rsi], rdi
0x1801a858d  mov     rdi, r15
0x1801a8590  mov     [rbp+57h+var_94], ax
0x1801a8594  mov     rcx, rdi; pv
0x1801a8597  call    cs:__imp_CoTaskMemFree
0x1801a859d  mov     edi, [rbp+57h+var_98]
0x1801a85a0  lea     rcx, [rbp+57h+lpFileName]; this
0x1801a85a4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1801a85a9  lea     rdx, [rbx-1]
0x1801a85ad  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801a85b1  ja      short loc_1801A85BC
0x1801a85b3  mov     rcx, rbx; hObject
0x1801a85b6  call    cs:__imp_CloseHandle
0x1801a85bc  lea     rcx, [rbp+57h+var_98]; this
0x1801a85c0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801a85c5  mov     eax, edi
0x1801a85c7  mov     rcx, [rbp+57h+var_30]
0x1801a85cb  xor     rcx, rsp; StackCookie
0x1801a85ce  call    __security_check_cookie
0x1801a85d3  mov     rbx, [rsp+0E0h+arg_10]
0x1801a85db  add     rsp, 0C0h
0x1801a85e2  pop     r15
0x1801a85e4  pop     r14
0x1801a85e6  pop     rdi
0x1801a85e7  pop     rsi
0x1801a85e8  pop     rbp
0x1801a85e9  retn
```
