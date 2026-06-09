# GameInputServerDevice::SendDriverOffloadRequest(unsigned __int64,ulong,bool)

- ea: `0x1800401cc`
- end: `0x18004043b`
- name: `?SendDriverOffloadRequest@GameInputServerDevice@@QEAAJ_KK_N@Z`
- size: `623`
- prototype: `__int64 __fastcall(GameInputServerDevice *__hidden this, unsigned __int64, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d50c`
- `0x18002f774`

## callees

- `0x180001304`
- `0x1800401cc`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040229`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004036e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004036e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004035a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004035a`

## pseudocode

```c
__int64 __fastcall GameInputServerDevice::SendDriverOffloadRequest(
        GameInputServerDevice *this,
        __int64 a2,
        unsigned int a3,
        char a4)
{
  __int64 v4; // r15
  HANDLE FileW; // rbx
  signed int LastError; // edi
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  const char *v17; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD InBuffer[3]; // [rsp+50h] [rbp-B0h] BYREF
  bool v19; // [rsp+68h] [rbp-98h]
  char v20; // [rsp+70h] [rbp-90h]

  v4 = a3;
  FileW = CreateFileW(L"\\\\.\\XboxGIP_Admin", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v15 = LastError;
      v17 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
      v16 = 1761;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        1024,
        (unsigned int)&byte_18006176F,
        v10,
        v11,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15);
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    memset_0(InBuffer, 0, 0xB8u);
    InBuffer[0] = *((_QWORD *)this + 27) & 0xFFFFFFFFFFFFFFLL;
    InBuffer[1] = a2;
    InBuffer[2] = v4;
    v19 = a4 != 0;
    v20 = 0;
    if ( DeviceIoControl(FileW, 0x40001D50u, InBuffer, 0xB8u, 0, 0, 0, 0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v16 = LastError;
        v17 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
        v15 = 1779;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          1024,
          (unsigned int)&byte_180061DCF,
          v12,
          v13,
          (__int64)&v17,
          (__int64)&v15,
          (__int64)&v16);
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147418113;
      }
    }
    CloseHandle(FileW);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800401cc  mov     [rsp-8+arg_18], rbx
0x1800401d1  push    rbp
0x1800401d2  push    rsi
0x1800401d3  push    rdi
0x1800401d4  push    r14
0x1800401d6  push    r15
0x1800401d8  lea     rbp, [rsp-20h]
0x1800401dd  sub     rsp, 120h
0x1800401e4  mov     rax, cs:__security_cookie
0x1800401eb  xor     rax, rsp
0x1800401ee  mov     [rbp+40h+var_30], rax
0x1800401f2  mov     r15d, r8d
0x1800401f5  mov     dil, r9b
0x1800401f8  mov     r8d, 3; dwShareMode
0x1800401fe  mov     [rsp+140h+hTemplateFile], 0; hTemplateFile
0x180040207  mov     r14, rdx
0x18004020a  mov     [rsp+140h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180040212  mov     rsi, rcx
0x180040215  mov     [rsp+140h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004021a  xor     r9d, r9d; lpSecurityAttributes
0x18004021d  lea     rcx, aXboxgipAdmin; "\\\\.\\XboxGIP_Admin"
0x180040224  mov     edx, 0C0000000h; dwDesiredAccess
0x180040229  call    cs:__imp_CreateFileW
0x180040230  nop     dword ptr [rax+rax+00h]
0x180040235  mov     rbx, rax
0x180040238  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004023c  jnz     loc_1800402E2
0x180040242  call    cs:__imp_GetLastError
0x180040249  nop     dword ptr [rax+rax+00h]
0x18004024e  mov     edi, eax
0x180040250  mov     eax, cs:dword_180069000
0x180040256  cmp     eax, 2
0x180040259  jbe     short loc_1800402C0
0x18004025b  mov     rdx, cs:qword_180069018
0x180040262  mov     ecx, 400h
0x180040267  mov     rax, cs:qword_180069010
0x18004026e  test    rcx, rax
0x180040271  jz      short loc_1800402C0
0x180040273  mov     rax, rdx
0x180040276  and     rax, rcx
0x180040279  cmp     rax, rdx
0x18004027c  jnz     short loc_1800402C0
0x18004027e  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180040285  mov     [rsp+140h+var_100], edi
0x180040289  mov     [rsp+140h+var_F8], rax
0x18004028e  lea     rdx, byte_18006176F
0x180040295  lea     rax, [rsp+140h+var_100]
0x18004029a  mov     [rsp+140h+var_FC], 6E1h
0x1800402a2  mov     [rsp+140h+hTemplateFile], rax
0x1800402a7  lea     rax, [rsp+140h+var_FC]
0x1800402ac  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x1800402b1  lea     rax, [rsp+140h+var_F8]
0x1800402b6  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800402bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800402c0  test    edi, edi
0x1800402c2  jnz     short loc_1800402CE
0x1800402c4  mov     edi, 8000FFFFh
0x1800402c9  jmp     loc_180040415
0x1800402ce  jle     loc_180040415
0x1800402d4  movzx   edi, di
0x1800402d7  or      edi, 80070000h
0x1800402dd  jmp     loc_180040415
0x1800402e2  xor     edx, edx; Val
0x1800402e4  lea     rcx, [rsp+140h+InBuffer]; void *
0x1800402e9  mov     r8d, 0B8h; Size
0x1800402ef  call    memset_0
0x1800402f4  mov     rax, [rsi+0D8h]
0x1800402fb  lea     r8, [rsp+140h+InBuffer]; lpInBuffer
0x180040300  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180040309  mov     rcx, 0FFFFFFFFFFFFFFh
0x180040313  and     rax, rcx
0x180040316  mov     [rsp+140h+hTemplateFile], 0; lpBytesReturned
0x18004031f  test    dil, dil
0x180040322  mov     [rsp+140h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18004032a  mov     r9d, 0B8h; nInBufferSize
0x180040330  mov     [rsp+140h+InBuffer], rax
0x180040335  mov     edx, 40001D50h; dwIoControlCode
0x18004033a  mov     [rsp+140h+var_E8], r14
0x18004033f  mov     rcx, rbx; hDevice
0x180040342  mov     [rsp+140h+var_E0], r15
0x180040347  setnz   [rsp+140h+var_D8]
0x18004034c  mov     [rsp+140h+var_D0], 0
0x180040351  mov     qword ptr [rsp+140h+dwCreationDisposition], 0; lpOutBuffer
0x18004035a  call    cs:__imp_DeviceIoControl
0x180040361  nop     dword ptr [rax+rax+00h]
0x180040366  test    eax, eax
0x180040368  jnz     loc_180040404
0x18004036e  call    cs:__imp_GetLastError
0x180040375  nop     dword ptr [rax+rax+00h]
0x18004037a  mov     edi, eax
0x18004037c  mov     eax, cs:dword_180069000
0x180040382  cmp     eax, 2
0x180040385  jbe     short loc_1800403EC
0x180040387  mov     rdx, cs:qword_180069018
0x18004038e  mov     ecx, 400h
0x180040393  mov     rax, cs:qword_180069010
0x18004039a  test    rcx, rax
0x18004039d  jz      short loc_1800403EC
0x18004039f  mov     rax, rdx
0x1800403a2  and     rax, rcx
0x1800403a5  cmp     rax, rdx
0x1800403a8  jnz     short loc_1800403EC
0x1800403aa  lea     rax, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x1800403b1  mov     [rsp+140h+var_FC], edi
0x1800403b5  mov     [rsp+140h+var_F8], rax
0x1800403ba  lea     rdx, byte_180061DCF
0x1800403c1  lea     rax, [rsp+140h+var_FC]
0x1800403c6  mov     [rsp+140h+var_100], 6F3h
0x1800403ce  mov     [rsp+140h+hTemplateFile], rax
0x1800403d3  lea     rax, [rsp+140h+var_100]
0x1800403d8  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x1800403dd  lea     rax, [rsp+140h+var_F8]
0x1800403e2  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x1800403e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800403ec  test    edi, edi
0x1800403ee  jnz     short loc_1800403F7
0x1800403f0  mov     edi, 8000FFFFh
0x1800403f5  jmp     short loc_180040406
0x1800403f7  jle     short loc_180040406
0x1800403f9  movzx   edi, di
0x1800403fc  or      edi, 80070000h
0x180040402  jmp     short loc_180040406
0x180040404  xor     edi, edi
0x180040406  mov     rcx, rbx; hObject
0x180040409  call    cs:__imp_CloseHandle
0x180040410  nop     dword ptr [rax+rax+00h]
0x180040415  mov     eax, edi
0x180040417  mov     rcx, [rbp+40h+var_30]
0x18004041b  xor     rcx, rsp; StackCookie
0x18004041e  call    __security_check_cookie
0x180040423  mov     rbx, [rsp+140h+arg_18]
0x18004042b  add     rsp, 120h
0x180040432  pop     r15
0x180040434  pop     r14
0x180040436  pop     rdi
0x180040437  pop     rsi
0x180040438  pop     rbp
0x180040439  retn
```
