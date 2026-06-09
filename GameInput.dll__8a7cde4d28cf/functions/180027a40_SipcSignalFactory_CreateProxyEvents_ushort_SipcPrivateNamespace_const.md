# SipcSignalFactory::CreateProxyEvents(ushort,SipcPrivateNamespace const &)

- ea: `0x180027a40`
- end: `0x180027c6d`
- name: `?CreateProxyEvents@SipcSignalFactory@@SAJGAEBVSipcPrivateNamespace@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(unsigned __int16, const struct SipcPrivateNamespace *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18002a900`

## callees

- `0x180027a40`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x180027b11`
- `ntdll!swprintf_s` at `0x180027baa`
- `ntdll!swprintf_s` at `0x180027b11`
- `ntdll!swprintf_s` at `0x180027baa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027aa0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027aa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c0e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027b63`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027bfe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027b63`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180027bfe`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::CreateProxyEvents(unsigned __int16 a1, const struct SipcPrivateNamespace *a2)
{
  unsigned int v2; // esi
  HANDLE FileW; // rbx
  signed int LastError; // eax
  unsigned int v6; // edi
  signed int v7; // eax
  wchar_t Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+250h] [rbp+150h]
  wchar_t InBuffer[264]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v12; // [rsp+470h] [rbp+370h]

  v2 = a1;
  FileW = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = -2147418113;
    if ( LastError < 0 )
      return (unsigned int)LastError;
  }
  else
  {
    memset_0(Buffer, 0, 0x218u);
    swprintf_s(Buffer, 0x104u, L"%4.4X_%s", v2, L"ClientSignal");
    v10 = *(_QWORD *)a2;
    Buffer[260] = 3;
    if ( DeviceIoControl(FileW, 0x1501FCu, Buffer, 0x218u, 0, 0, 0, 0)
      && (memset_0(InBuffer, 0, 0x218u),
          swprintf_s(InBuffer, 0x104u, L"%4.4X_%s", v2, L"ServerSignal"),
          v12 = *(_QWORD *)a2,
          InBuffer[260] = 259,
          DeviceIoControl(FileW, 0x1501FCu, InBuffer, 0x218u, 0, 0, 0, 0)) )
    {
      v6 = 0;
    }
    else
    {
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v6 = -2147418113;
      if ( v7 < 0 )
        v6 = v7;
    }
    CloseHandle(FileW);
  }
  return v6;
}

```

## disassembly

```asm
0x180027a40  mov     [rsp-8+arg_10], rbx
0x180027a45  mov     [rsp-8+arg_18], rsi
0x180027a4a  push    rbp
0x180027a4b  push    rdi
0x180027a4c  push    r12
0x180027a4e  lea     rbp, [rsp-390h]
0x180027a56  sub     rsp, 490h
0x180027a5d  mov     rax, cs:__security_cookie
0x180027a64  xor     rax, rsp
0x180027a67  mov     [rbp+3A0h+var_20], rax
0x180027a6e  xor     r9d, r9d; lpSecurityAttributes
0x180027a71  movzx   esi, cx
0x180027a74  mov     rdi, rdx
0x180027a77  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180027a80  mov     [rsp+4A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180027a88  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x180027a8f  mov     edx, 0C0000000h; dwDesiredAccess
0x180027a94  mov     [rsp+4A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180027a9c  lea     r8d, [r9+3]; dwShareMode
0x180027aa0  call    cs:__imp_CreateFileW
0x180027aa7  nop     dword ptr [rax+rax+00h]
0x180027aac  mov     rbx, rax
0x180027aaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027ab3  jnz     short loc_180027ADC
0x180027ab5  call    cs:__imp_GetLastError
0x180027abc  nop     dword ptr [rax+rax+00h]
0x180027ac1  test    eax, eax
0x180027ac3  jle     short loc_180027ACD
0x180027ac5  movzx   eax, ax
0x180027ac8  or      eax, 80070000h
0x180027acd  test    eax, eax
0x180027acf  mov     edi, 8000FFFFh
0x180027ad4  cmovs   edi, eax
0x180027ad7  jmp     loc_180027C43
0x180027adc  mov     r12d, 218h
0x180027ae2  lea     rcx, [rsp+4A0h+Buffer]; void *
0x180027ae7  mov     r8d, r12d; Size
0x180027aea  xor     edx, edx; Val
0x180027aec  call    memset_0
0x180027af1  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x180027af8  mov     r9d, esi
0x180027afb  lea     r8, a44xS; "%4.4X_%s"
0x180027b02  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x180027b07  mov     edx, 104h; BufferCount
0x180027b0c  lea     rcx, [rsp+4A0h+Buffer]; Buffer
0x180027b11  call    cs:__imp_swprintf_s
0x180027b18  nop     dword ptr [rax+rax+00h]
0x180027b1d  mov     rax, [rdi]
0x180027b20  lea     r8, [rsp+4A0h+Buffer]; lpInBuffer
0x180027b25  mov     [rsp+4A0h+lpOverlapped], 0; lpOverlapped
0x180027b2e  mov     r9d, r12d; nInBufferSize
0x180027b31  mov     [rsp+4A0h+hTemplateFile], 0; lpBytesReturned
0x180027b3a  mov     edx, 1501FCh; dwIoControlCode
0x180027b3f  mov     [rsp+4A0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180027b47  mov     rcx, rbx; hDevice
0x180027b4a  mov     [rbp+3A0h+var_250], rax
0x180027b51  mov     qword ptr [rsp+4A0h+dwCreationDisposition], 0; lpOutBuffer
0x180027b5a  mov     [rbp+3A0h+var_258], 3
0x180027b63  call    cs:__imp_DeviceIoControl
0x180027b6a  nop     dword ptr [rax+rax+00h]
0x180027b6f  test    eax, eax
0x180027b71  jz      loc_180027C0E
0x180027b77  mov     r8d, r12d; Size
0x180027b7a  lea     rcx, [rbp+3A0h+InBuffer]; void *
0x180027b81  xor     edx, edx; Val
0x180027b83  call    memset_0
0x180027b88  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x180027b8f  mov     r9d, esi
0x180027b92  lea     r8, a44xS; "%4.4X_%s"
0x180027b99  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x180027b9e  mov     edx, 104h; BufferCount
0x180027ba3  lea     rcx, [rbp+3A0h+InBuffer]; Buffer
0x180027baa  call    cs:__imp_swprintf_s
0x180027bb1  nop     dword ptr [rax+rax+00h]
0x180027bb6  mov     rax, [rdi]
0x180027bb9  lea     r8, [rbp+3A0h+InBuffer]; lpInBuffer
0x180027bc0  mov     [rsp+4A0h+lpOverlapped], 0; lpOverlapped
0x180027bc9  mov     r9d, r12d; nInBufferSize
0x180027bcc  mov     [rsp+4A0h+hTemplateFile], 0; lpBytesReturned
0x180027bd5  mov     edx, 1501FCh; dwIoControlCode
0x180027bda  mov     [rsp+4A0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180027be2  mov     rcx, rbx; hDevice
0x180027be5  mov     [rbp+3A0h+var_30], rax
0x180027bec  mov     qword ptr [rsp+4A0h+dwCreationDisposition], 0; lpOutBuffer
0x180027bf5  mov     [rbp+3A0h+var_38], 103h
0x180027bfe  call    cs:__imp_DeviceIoControl
0x180027c05  nop     dword ptr [rax+rax+00h]
0x180027c0a  test    eax, eax
0x180027c0c  jnz     short loc_180027C32
0x180027c0e  call    cs:__imp_GetLastError
0x180027c15  nop     dword ptr [rax+rax+00h]
0x180027c1a  test    eax, eax
0x180027c1c  jle     short loc_180027C26
0x180027c1e  movzx   eax, ax
0x180027c21  or      eax, 80070000h
0x180027c26  test    eax, eax
0x180027c28  mov     edi, 8000FFFFh
0x180027c2d  cmovs   edi, eax
0x180027c30  jmp     short loc_180027C34
0x180027c32  xor     edi, edi
0x180027c34  mov     rcx, rbx; hObject
0x180027c37  call    cs:__imp_CloseHandle
0x180027c3e  nop     dword ptr [rax+rax+00h]
0x180027c43  mov     eax, edi
0x180027c45  mov     rcx, [rbp+3A0h+var_20]
0x180027c4c  xor     rcx, rsp; StackCookie
0x180027c4f  call    __security_check_cookie
0x180027c54  lea     r11, [rsp+4A0h+var_10]
0x180027c5c  mov     rbx, [r11+30h]
0x180027c60  mov     rsi, [r11+38h]
0x180027c64  mov     rsp, r11
0x180027c67  pop     r12
0x180027c69  pop     rdi
0x180027c6a  pop     rbp
0x180027c6b  retn
```
