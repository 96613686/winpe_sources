# XinputHid::XinputHidInterface::XusbDeviceNodeArrived(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,XinputHid::XInputHidDevice *)

- ea: `0x180010a74`
- end: `0x180010d15`
- name: `?XusbDeviceNodeArrived@XinputHidInterface@XinputHid@@AEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUXInputHidDevice@2@@Z`
- size: `673`
- prototype: `int __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010768`

## callees

- `0x1800042d4`
- `0x180009260`
- `0x180010014`
- `0x180010588`
- `0x180010a74`
- `0x180010ed4`
- `0x1800111fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010bbd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010bbd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010b0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010b0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010c4c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010c4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c3e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180010bd1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180010bd1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010b59`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180010b59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010acb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010acb`

## pseudocode

```c
int __fastcall XinputHid::XinputHidInterface::XusbDeviceNodeArrived(__int64 a1, __int64 a2, __int64 *a3)
{
  const WCHAR *v4; // rax
  char *FileW; // rax
  void *v7; // rbx
  __int64 v8; // r15
  HANDLE EventW; // rsi
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  unsigned int v20; // eax
  void *v21; // rdx
  unsigned int v22; // r8d
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD BytesReturned; // [rsp+A0h] [rbp+40h] BYREF
  int OutBuffer; // [rsp+A8h] [rbp+48h] BYREF

  v4 = (const WCHAR *)a2;
  if ( *a3 )
    goto LABEL_21;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v4 = *(const WCHAR **)a2;
  FileW = (char *)CreateFileW(v4, 0xC0000000, 3u, 0, 3u, 0x60000000u, 0);
  v7 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    BytesReturned = 0;
    OutBuffer = 0;
    memset(&Overlapped, 0, 24);
    v8 = 1;
    EventW = CreateEventW(0, 1, 0, 0);
    Overlapped.hEvent = EventW;
    if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2A7,
        v10,
        (const char *)0x8000FFFFLL,
        dwCreationDisposition);
    if ( !DeviceIoControl(v7, 0x80006380, 0, 0, &OutBuffer, 4u, &BytesReturned, &Overlapped) )
    {
      if ( GetLastError() != 997 )
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x2BB, v12, v13);
        std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(
          a1 + 96,
          a3[2]);
        if ( !CloseHandle(EventW) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x2AB,
            (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
            v14);
        LODWORD(FileW) = CloseHandle(v7);
        if ( !(_DWORD)FileW )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x29C,
            (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
            v15);
        return (int)FileW;
      }
      WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF);
      if ( !GetOverlappedResult(v7, &Overlapped, &BytesReturned, 0) )
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x2C5, v11, v16);
        std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(
          a1 + 96,
          a3[2]);
        if ( !CloseHandle(EventW) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x2AB,
            (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
            v17);
        LODWORD(FileW) = CloseHandle(v7);
        if ( !(_DWORD)FileW )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x29C,
            (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
            v18);
        return (int)FileW;
      }
    }
    if ( BytesReturned < 4 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2CC,
        v11,
        (const char *)0x8000FFFFLL,
        dwCreationDispositiona);
    if ( OutBuffer )
    {
      if ( OutBuffer != 1 )
      {
        v20 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::FailFast_Hr(retaddr, v21, v22, (const char *)v20, dwCreationDispositiona);
      }
    }
    else
    {
      v8 = 2;
    }
    *a3 = v8;
    a3[1] = (__int64)v7;
    if ( !CloseHandle(EventW) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2AB,
        (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
        v19);
LABEL_21:
    LODWORD(FileW) = SetEvent(*(HANDLE *)(a1 + 48));
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x180010a74  mov     [rsp-28h+arg_0], rbx
0x180010a79  push    rbp
0x180010a7a  push    rsi
0x180010a7b  push    rdi
0x180010a7c  push    r14
0x180010a7e  push    r15
0x180010a80  mov     rbp, rsp
0x180010a83  sub     rsp, 60h
0x180010a87  cmp     qword ptr [r8], 0
0x180010a8b  mov     rdi, r8
0x180010a8e  mov     rax, rdx
0x180010a91  mov     r14, rcx
0x180010a94  jnz     loc_180010C48
0x180010a9a  cmp     qword ptr [rdx+18h], 7
0x180010a9f  jbe     short loc_180010AA4
0x180010aa1  mov     rax, [rdx]
0x180010aa4  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180010aad  mov     r8d, 3; dwShareMode
0x180010ab3  mov     [rsp+60h+dwFlagsAndAttributes], 60000000h; dwFlagsAndAttributes
0x180010abb  xor     r9d, r9d; lpSecurityAttributes
0x180010abe  mov     edx, 0C0000000h; dwDesiredAccess
0x180010ac3  mov     [rsp+60h+dwCreationDisposition], r8d; int
0x180010ac8  mov     rcx, rax; lpFileName
0x180010acb  call    cs:__imp_CreateFileW
0x180010ad1  mov     rbx, rax
0x180010ad4  lea     rcx, [rax-1]
0x180010ad8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180010adc  ja      loc_180010C52
0x180010ae2  xorps   xmm0, xmm0
0x180010ae5  mov     [rbp+BytesReturned], 0
0x180010aec  xor     r9d, r9d; lpName
0x180010aef  mov     [rbp+OutBuffer], 0
0x180010af6  xor     r8d, r8d; bInitialState
0x180010af9  xor     ecx, ecx; lpEventAttributes
0x180010afb  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180010aff  lea     r15d, [r9+1]
0x180010b03  mov     edx, r15d; bManualReset
0x180010b06  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180010b0a  call    cs:__imp_CreateEventW
0x180010b10  mov     rsi, rax
0x180010b13  mov     [rbp+Overlapped.hEvent], rax
0x180010b17  lea     rcx, [rax+1]
0x180010b1b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180010b22  jz      loc_180010CBF
0x180010b28  lea     rax, [rbp+Overlapped]
0x180010b2c  xor     r9d, r9d; nInBufferSize
0x180010b2f  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180010b34  xor     r8d, r8d; lpInBuffer
0x180010b37  lea     rax, [rbp+BytesReturned]
0x180010b3b  mov     edx, 80006380h; dwIoControlCode
0x180010b40  mov     [rsp+60h+hTemplateFile], rax; lpBytesReturned
0x180010b45  mov     rcx, rbx; hDevice
0x180010b48  lea     rax, [rbp+OutBuffer]
0x180010b4c  mov     [rsp+60h+dwFlagsAndAttributes], 4; nOutBufferSize
0x180010b54  mov     qword ptr [rsp+60h+dwCreationDisposition], rax; int
0x180010b59  call    cs:__imp_DeviceIoControl
0x180010b5f  test    eax, eax
0x180010b61  jnz     loc_180010C16
0x180010b67  call    cs:__imp_GetLastError
0x180010b6d  cmp     eax, 3E5h
0x180010b72  jz      short loc_180010BB6
0x180010b74  mov     rcx, [rbp+28h]; this
0x180010b78  mov     edx, 2BBh; void *
0x180010b7d  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180010b82  mov     rdx, [rdi+10h]
0x180010b86  lea     rcx, [r14+60h]
0x180010b8a  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(std::wstring const &)
0x180010b8f  mov     rcx, rsi; hObject
0x180010b92  call    cs:__imp_CloseHandle
0x180010b98  test    eax, eax
0x180010b9a  jz      loc_180010CD4
0x180010ba0  mov     rcx, rbx; hObject
0x180010ba3  call    cs:__imp_CloseHandle
0x180010ba9  test    eax, eax
0x180010bab  jz      loc_180010C7C
0x180010bb1  jmp     loc_180010C52
0x180010bb6  mov     rcx, [rbp+Overlapped.hEvent]; hHandle
0x180010bba  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010bbd  call    cs:__imp_WaitForSingleObject
0x180010bc3  xor     r9d, r9d; bWait
0x180010bc6  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x180010bca  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180010bce  mov     rcx, rbx; hFile
0x180010bd1  call    cs:__imp_GetOverlappedResult
0x180010bd7  test    eax, eax
0x180010bd9  jnz     short loc_180010C16
0x180010bdb  mov     rcx, [rbp+28h]; this
0x180010bdf  mov     edx, 2C5h; void *
0x180010be4  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180010be9  mov     rdx, [rdi+10h]
0x180010bed  lea     rcx, [r14+60h]
0x180010bf1  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(std::wstring const &)
0x180010bf6  mov     rcx, rsi; hObject
0x180010bf9  call    cs:__imp_CloseHandle
0x180010bff  test    eax, eax
0x180010c01  jz      loc_180010CEA
0x180010c07  mov     rcx, rbx; hObject
0x180010c0a  call    cs:__imp_CloseHandle
0x180010c10  test    eax, eax
0x180010c12  jz      short loc_180010C92
0x180010c14  jmp     short loc_180010C52
0x180010c16  cmp     [rbp+BytesReturned], 4
0x180010c1a  jb      loc_180010D00
0x180010c20  mov     ecx, [rbp+OutBuffer]
0x180010c23  test    ecx, ecx
0x180010c25  jz      short loc_180010C2E
0x180010c27  cmp     ecx, r15d
0x180010c2a  jnz     short loc_180010CA8
0x180010c2c  jmp     short loc_180010C34
0x180010c2e  mov     r15d, 2
0x180010c34  mov     [rdi], r15
0x180010c37  mov     rcx, rsi; hObject
0x180010c3a  mov     [rdi+8], rbx
0x180010c3e  call    cs:__imp_CloseHandle
0x180010c44  test    eax, eax
0x180010c46  jz      short loc_180010C66
0x180010c48  mov     rcx, [r14+30h]; hEvent
0x180010c4c  call    cs:__imp_SetEvent
0x180010c52  mov     rbx, [rsp+60h+arg_0]
0x180010c5a  add     rsp, 60h
0x180010c5e  pop     r15
0x180010c60  pop     r14
0x180010c62  pop     rdi
0x180010c63  pop     rsi
0x180010c64  pop     rbp
0x180010c65  retn
0x180010c66  mov     rcx, [rbp+28h]; this
0x180010c6a  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010c71  mov     edx, 2ABh; void *
0x180010c76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010c7c  mov     rcx, [rbp+28h]; this
0x180010c80  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010c87  mov     edx, 29Ch; void *
0x180010c8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010c92  mov     rcx, [rbp+28h]; this
0x180010c96  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010c9d  mov     edx, 29Ch; void *
0x180010ca2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ca8  mov     ecx, 8000FFFFh
0x180010cad  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180010cb2  mov     rcx, [rbp+28h]; this
0x180010cb6  mov     r9d, eax; char *
0x180010cb9  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180010cbf  mov     rcx, [rbp+28h]; this
0x180010cc3  mov     edx, 2A7h; void *
0x180010cc8  mov     r9d, 8000FFFFh; char *
0x180010cce  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180010cd4  mov     rcx, [rbp+28h]; this
0x180010cd8  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010cdf  mov     edx, 2ABh; void *
0x180010ce4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010cea  mov     rcx, [rbp+28h]; this
0x180010cee  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x180010cf5  mov     edx, 2ABh; void *
0x180010cfa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d00  mov     rcx, [rbp+28h]; this
0x180010d04  mov     edx, 2CCh; void *
0x180010d09  mov     r9d, 8000FFFFh; char *
0x180010d0f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
