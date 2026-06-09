# NFCSEUtils::GetDefaultSE(_GUID *,_SECURE_ELEMENT_TYPE)

- ea: `0x180096acc`
- end: `0x180096c6e`
- name: `?GetDefaultSE@NFCSEUtils@@YAJPEAU_GUID@@W4_SECURE_ELEMENT_TYPE@@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800949c0`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x180018a08`
- `0x180096acc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096bd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096bd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096c3d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180096bf6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180096bf6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180096bcc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180096bcc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180096b6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180096b6c`

## pseudocode

```c
__int64 __fastcall NFCSEUtils::GetDefaultSE(_OWORD *a1)
{
  signed int DefaultSEDeviceName; // edi
  void *v3; // rbx
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v6; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v12[20]; // [rsp+74h] [rbp-8Ch] BYREF

  lpFileName = 0;
  OutBuffer = 0;
  memset_0(v12, 0, sizeof(v12));
  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  DefaultSEDeviceName = NfcUtilsGetDefaultSEDeviceName(&lpFileName);
  if ( DefaultSEDeviceName >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    v3 = FileW;
    if ( FileW
      && (DeviceIoControl(FileW, 0x220800u, 0, 0, &OutBuffer, 0x144u, &BytesReturned, &Overlapped)
       || GetLastError() == 997 && GetOverlappedResult(v3, &Overlapped, &BytesReturned, 1)) )
    {
      v6 = 0;
      if ( OutBuffer )
      {
        while ( *((_DWORD *)&v12[1] + 5 * v6) )
        {
          v6 = (unsigned int)(v6 + 1);
          if ( (unsigned int)v6 >= OutBuffer )
            goto LABEL_12;
        }
        DefaultSEDeviceName = 0;
        *a1 = *(_OWORD *)((char *)v12 + 20 * v6);
      }
      else
      {
LABEL_12:
        DefaultSEDeviceName = -2147024637;
      }
    }
    else
    {
      LastError = GetLastError();
      DefaultSEDeviceName = LastError;
      if ( LastError > 0 )
        DefaultSEDeviceName = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v3 = 0;
  }
  CoTaskMemFree((LPVOID)lpFileName);
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  return (unsigned int)DefaultSEDeviceName;
}

```

## disassembly

```asm
0x180096acc  push    rbp
0x180096ace  push    rbx
0x180096acf  push    rsi
0x180096ad0  push    rdi
0x180096ad1  lea     rbp, [rsp-0D8h]
0x180096ad9  sub     rsp, 1D8h
0x180096ae0  mov     rax, cs:__security_cookie
0x180096ae7  xor     rax, rsp
0x180096aea  mov     [rbp+0F0h+var_30], rax
0x180096af1  mov     rsi, rcx
0x180096af4  mov     [rsp+1F0h+lpFileName], 0
0x180096afd  lea     rcx, [rsp+1F0h+var_17C]; void *
0x180096b02  mov     [rsp+1F0h+OutBuffer], 0
0x180096b0a  xor     edx, edx; Val
0x180096b0c  mov     r8d, 140h; Size
0x180096b12  call    memset_0
0x180096b17  xorps   xmm0, xmm0
0x180096b1a  mov     [rsp+1F0h+BytesReturned], 0
0x180096b22  lea     rcx, [rsp+1F0h+lpFileName]
0x180096b27  movups  xmmword ptr [rsp+1F0h+Overlapped.Internal], xmm0
0x180096b2c  movups  xmmword ptr [rsp+1F0h+Overlapped.10h], xmm0
0x180096b31  call    NfcUtilsGetDefaultSEDeviceName
0x180096b36  mov     edi, eax
0x180096b38  test    eax, eax
0x180096b3a  jns     short loc_180096B43
0x180096b3c  xor     ebx, ebx
0x180096b3e  jmp     loc_180096C25
0x180096b43  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x180096b48  mov     r8d, 3; dwShareMode
0x180096b4e  mov     [rsp+1F0h+hTemplateFile], 0; hTemplateFile
0x180096b57  xor     r9d, r9d; lpSecurityAttributes
0x180096b5a  mov     [rsp+1F0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180096b62  mov     edx, 0C0000000h; dwDesiredAccess
0x180096b67  mov     [rsp+1F0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180096b6c  call    cs:__imp_CreateFileW
0x180096b72  mov     rbx, rax
0x180096b75  test    rax, rax
0x180096b78  jnz     short loc_180096B98
0x180096b7a  call    cs:__imp_GetLastError
0x180096b80  mov     edi, eax
0x180096b82  test    eax, eax
0x180096b84  jle     loc_180096C25
0x180096b8a  movzx   edi, ax
0x180096b8d  or      edi, 80070000h
0x180096b93  jmp     loc_180096C25
0x180096b98  lea     rax, [rsp+1F0h+Overlapped]
0x180096b9d  xor     r9d, r9d; nInBufferSize
0x180096ba0  mov     [rsp+1F0h+lpOverlapped], rax; lpOverlapped
0x180096ba5  xor     r8d, r8d; lpInBuffer
0x180096ba8  lea     rax, [rsp+1F0h+BytesReturned]
0x180096bad  mov     edx, 220800h; dwIoControlCode
0x180096bb2  mov     [rsp+1F0h+hTemplateFile], rax; lpBytesReturned
0x180096bb7  mov     rcx, rbx; hDevice
0x180096bba  lea     rax, [rsp+1F0h+OutBuffer]
0x180096bbf  mov     [rsp+1F0h+dwFlagsAndAttributes], 144h; nOutBufferSize
0x180096bc7  mov     qword ptr [rsp+1F0h+dwCreationDisposition], rax; lpOutBuffer
0x180096bcc  call    cs:__imp_DeviceIoControl
0x180096bd2  test    eax, eax
0x180096bd4  jnz     short loc_180096C04
0x180096bd6  call    cs:__imp_GetLastError
0x180096bdc  cmp     eax, 3E5h
0x180096be1  jnz     short loc_180096B7A
0x180096be3  mov     r9d, 1; bWait
0x180096be9  lea     r8, [rsp+1F0h+BytesReturned]; lpNumberOfBytesTransferred
0x180096bee  lea     rdx, [rsp+1F0h+Overlapped]; lpOverlapped
0x180096bf3  mov     rcx, rbx; hFile
0x180096bf6  call    cs:__imp_GetOverlappedResult
0x180096bfc  test    eax, eax
0x180096bfe  jz      loc_180096B7A
0x180096c04  mov     edx, [rsp+1F0h+OutBuffer]
0x180096c08  xor     ecx, ecx
0x180096c0a  test    edx, edx
0x180096c0c  jz      short loc_180096C20
0x180096c0e  lea     r8, [rcx+rcx*4]
0x180096c12  cmp     [rbp+r8*4+0F0h+var_16C], 0
0x180096c18  jz      short loc_180096C60
0x180096c1a  inc     ecx
0x180096c1c  cmp     ecx, edx
0x180096c1e  jb      short loc_180096C0E
0x180096c20  mov     edi, 80070103h
0x180096c25  mov     rcx, [rsp+1F0h+lpFileName]; pv
0x180096c2a  call    cs:__imp_CoTaskMemFree
0x180096c30  lea     rcx, [rbx+1]
0x180096c34  cmp     rcx, 1
0x180096c38  jbe     short loc_180096C43
0x180096c3a  mov     rcx, rbx; hObject
0x180096c3d  call    cs:__imp_CloseHandle
0x180096c43  mov     eax, edi
0x180096c45  mov     rcx, [rbp+0F0h+var_30]
0x180096c4c  xor     rcx, rsp; StackCookie
0x180096c4f  call    __security_check_cookie
0x180096c54  add     rsp, 1D8h
0x180096c5b  pop     rdi
0x180096c5c  pop     rsi
0x180096c5d  pop     rbx
0x180096c5e  pop     rbp
0x180096c5f  retn
0x180096c60  movups  xmm0, [rsp+r8*4+1F0h+var_17C]
0x180096c66  xor     edi, edi
0x180096c68  movdqu  xmmword ptr [rsi], xmm0
0x180096c6c  jmp     short loc_180096C25
```
