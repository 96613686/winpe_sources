# CInkDesktopHost::RuntimeClassInitialize(void)

- ea: `0x1800b2dd0`
- end: `0x1800b309b`
- name: `?RuntimeClassInitialize@CInkDesktopHost@@UEAAJXZ`
- size: `715`
- prototype: `__int64 __fastcall(CInkDesktopHost *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180002f6c`
- `0x18000354c`
- `0x1800b2dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2f5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2f5a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2e40`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f09`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b2efb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b2efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b300f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b3000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b300f`

## string_xrefs

- `0x1800b2f47`: `CreateThread`
- `0x1800b2f84`: `Wait failed on thread startup`
- `0x1800b2fb4`: `Thread init failed`
- `0x1800b2e91`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall CInkDesktopHost::RuntimeClassInitialize(CInkDesktopHost *this, __int64 a2, __int64 a3)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v6; // r8
  int v7; // ecx
  int v8; // r9d
  const wchar_t *v9; // rax
  int v10; // ebx
  HANDLE Thread; // rsi
  signed int v12; // eax
  __int64 v13; // r8
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const wchar_t *v17; // rax
  void *v18; // rcx
  char *v19; // rdx
  const wchar_t *v21; // [rsp+70h] [rbp+30h] BYREF
  const wchar_t *v22; // [rsp+78h] [rbp+38h] BYREF
  const wchar_t *v23; // [rsp+80h] [rbp+40h] BYREF

  if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 2050, a3) )
  {
    v21 = L"CInkDesktopHost::RuntimeClassInitialize[Enter]";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18015B128,
      (unsigned int)&dword_18013BD8C,
      0,
      0,
      (__int64)&v21);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 7) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = (unsigned int)LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = 2147500037LL;
    }
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v6) )
      goto LABEL_13;
    v9 = L"CreateEvent";
LABEL_12:
    v22 = v9;
    LODWORD(v21) = v6;
    v23 = L"CInkDesktopHost::RuntimeClassInitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)word_18013780A,
      v6,
      v8,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v22);
LABEL_13:
    v10 = -2147418113;
    goto LABEL_34;
  }
  Thread = CreateThread(0, 0, CInkDesktopHost::s_InkHostThreadProc, this, 0, 0);
  if ( !Thread )
  {
    v12 = GetLastError();
    v6 = (unsigned int)v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v6 = 2147500037LL;
    }
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v6) )
      goto LABEL_13;
    v9 = L"CreateThread";
    goto LABEL_12;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF) )
  {
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v13) )
      goto LABEL_32;
    v17 = L"Wait failed on thread startup";
LABEL_31:
    v22 = v17;
    LODWORD(v21) = -2147418113;
    v23 = L"CInkDesktopHost::RuntimeClassInitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v14,
      (unsigned int)word_18013780A,
      v15,
      v16,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v22);
LABEL_32:
    v10 = -2147418113;
    goto LABEL_33;
  }
  if ( !*((_QWORD *)this + 6) )
  {
    if ( (unsigned int)dword_18015B128 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v13) )
      goto LABEL_32;
    v17 = L"Thread init failed";
    goto LABEL_31;
  }
  v10 = 0;
LABEL_33:
  CloseHandle(Thread);
LABEL_34:
  v18 = (void *)*((_QWORD *)this + 7);
  if ( v18 )
    CloseHandle(v18);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 2050, v6) )
    {
      v19 = byte_18013BDE3;
      goto LABEL_43;
    }
  }
  else if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 2050, v6) )
  {
    v19 = &byte_18013BD2F;
LABEL_43:
    v22 = L"CInkDesktopHost::RuntimeClassInitialize[Exit]";
    LODWORD(v21) = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18015B128,
      (_DWORD)v19,
      0,
      0,
      (__int64)&v22,
      (__int64)&v21);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b2dd0  mov     [rsp-28h+arg_18], rbx
0x1800b2dd5  push    rbp
0x1800b2dd6  push    rsi
0x1800b2dd7  push    rdi
0x1800b2dd8  push    r12
0x1800b2dda  push    r15
0x1800b2ddc  mov     rbp, rsp
0x1800b2ddf  sub     rsp, 40h
0x1800b2de3  mov     eax, cs:dword_18015B128
0x1800b2de9  lea     r15, dword_18015B128
0x1800b2df0  mov     rdi, rcx
0x1800b2df3  mov     r12d, 802h
0x1800b2df9  cmp     eax, 4
0x1800b2dfc  jbe     short loc_1800B2E36
0x1800b2dfe  mov     edx, r12d
0x1800b2e01  mov     rcx, r15
0x1800b2e04  call    _tlgKeywordOn
0x1800b2e09  test    al, al
0x1800b2e0b  jz      short loc_1800B2E36
0x1800b2e0d  lea     rax, aCinkdesktophos; "CInkDesktopHost::RuntimeClassInitialize"...
0x1800b2e14  xor     r9d, r9d
0x1800b2e17  mov     [rbp+arg_0], rax
0x1800b2e1b  lea     rdx, dword_18013BD8C
0x1800b2e22  lea     rax, [rbp+arg_0]
0x1800b2e26  xor     r8d, r8d
0x1800b2e29  mov     rcx, r15
0x1800b2e2c  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x1800b2e31  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b2e36  xor     r9d, r9d; lpName
0x1800b2e39  xor     r8d, r8d; bInitialState
0x1800b2e3c  xor     edx, edx; bManualReset
0x1800b2e3e  xor     ecx, ecx; lpEventAttributes
0x1800b2e40  call    cs:__imp_CreateEventW
0x1800b2e46  mov     [rdi+38h], rax
0x1800b2e4a  test    rax, rax
0x1800b2e4d  jnz     loc_1800B2EDC
0x1800b2e53  call    cs:__imp_GetLastError
0x1800b2e59  mov     r8d, eax
0x1800b2e5c  test    eax, eax
0x1800b2e5e  jz      short loc_1800B2E6F
0x1800b2e60  jle     short loc_1800B2E75
0x1800b2e62  movzx   r8d, ax
0x1800b2e66  or      r8d, 80070000h
0x1800b2e6d  jmp     short loc_1800B2E75
0x1800b2e6f  mov     r8d, 80004005h
0x1800b2e75  mov     eax, cs:dword_18015B128
0x1800b2e7b  cmp     eax, 2
0x1800b2e7e  jbe     short loc_1800B2ED2
0x1800b2e80  mov     edx, 100h
0x1800b2e85  mov     rcx, r15
0x1800b2e88  call    _tlgKeywordOn
0x1800b2e8d  test    al, al
0x1800b2e8f  jz      short loc_1800B2ED2
0x1800b2e91  lea     rax, aCreateevent; "CreateEvent"
0x1800b2e98  mov     [rbp+arg_8], rax
0x1800b2e9c  lea     rdx, word_18013780A
0x1800b2ea3  lea     rax, aCinkdesktophos_12; "CInkDesktopHost::RuntimeClassInitialize"
0x1800b2eaa  mov     dword ptr [rbp+arg_0], r8d
0x1800b2eae  mov     [rbp+arg_10], rax
0x1800b2eb2  lea     rax, [rbp+arg_8]
0x1800b2eb6  mov     [rsp+40h+var_10], rax
0x1800b2ebb  lea     rax, [rbp+arg_0]
0x1800b2ebf  mov     [rsp+40h+lpThreadId], rax
0x1800b2ec4  lea     rax, [rbp+arg_10]
0x1800b2ec8  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x1800b2ecd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800b2ed2  mov     ebx, 8000FFFFh
0x1800b2ed7  jmp     loc_1800B3006
0x1800b2edc  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x1800b2ee5  lea     r8, ?s_InkHostThreadProc@CInkDesktopHost@@KAKPEAX@Z; lpStartAddress
0x1800b2eec  mov     r9, rdi; lpParameter
0x1800b2eef  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x1800b2ef7  xor     edx, edx; dwStackSize
0x1800b2ef9  xor     ecx, ecx; lpThreadAttributes
0x1800b2efb  call    cs:__imp_CreateThread
0x1800b2f01  mov     rsi, rax
0x1800b2f04  test    rax, rax
0x1800b2f07  jnz     short loc_1800B2F53
0x1800b2f09  call    cs:__imp_GetLastError
0x1800b2f0f  mov     r8d, eax
0x1800b2f12  test    eax, eax
0x1800b2f14  jz      short loc_1800B2F25
0x1800b2f16  jle     short loc_1800B2F2B
0x1800b2f18  movzx   r8d, ax
0x1800b2f1c  or      r8d, 80070000h
0x1800b2f23  jmp     short loc_1800B2F2B
0x1800b2f25  mov     r8d, 80004005h
0x1800b2f2b  mov     eax, cs:dword_18015B128
0x1800b2f31  cmp     eax, 2
0x1800b2f34  jbe     short loc_1800B2ED2
0x1800b2f36  mov     edx, 100h
0x1800b2f3b  mov     rcx, r15
0x1800b2f3e  call    _tlgKeywordOn
0x1800b2f43  test    al, al
0x1800b2f45  jz      short loc_1800B2ED2
0x1800b2f47  lea     rax, aCreatethread; "CreateThread"
0x1800b2f4e  jmp     loc_1800B2E98
0x1800b2f53  mov     rcx, [rdi+38h]; hHandle
0x1800b2f57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2f5a  call    cs:__imp_WaitForSingleObject
0x1800b2f60  test    eax, eax
0x1800b2f62  jz      short loc_1800B2F8D
0x1800b2f64  mov     eax, cs:dword_18015B128
0x1800b2f6a  cmp     eax, 2
0x1800b2f6d  jbe     loc_1800B2FF8
0x1800b2f73  mov     edx, 100h
0x1800b2f78  mov     rcx, r15
0x1800b2f7b  call    _tlgKeywordOn
0x1800b2f80  test    al, al
0x1800b2f82  jz      short loc_1800B2FF8
0x1800b2f84  lea     rax, aWaitFailedOnTh; "Wait failed on thread startup"
0x1800b2f8b  jmp     short loc_1800B2FBB
0x1800b2f8d  cmp     qword ptr [rdi+30h], 0
0x1800b2f92  jz      short loc_1800B2F98
0x1800b2f94  xor     ebx, ebx
0x1800b2f96  jmp     short loc_1800B2FFD
0x1800b2f98  mov     eax, cs:dword_18015B128
0x1800b2f9e  cmp     eax, 2
0x1800b2fa1  jbe     short loc_1800B2FF8
0x1800b2fa3  mov     edx, 100h
0x1800b2fa8  mov     rcx, r15
0x1800b2fab  call    _tlgKeywordOn
0x1800b2fb0  test    al, al
0x1800b2fb2  jz      short loc_1800B2FF8
0x1800b2fb4  lea     rax, aThreadInitFail; "Thread init failed"
0x1800b2fbb  mov     [rbp+arg_8], rax
0x1800b2fbf  lea     rdx, word_18013780A
0x1800b2fc6  lea     rax, aCinkdesktophos_12; "CInkDesktopHost::RuntimeClassInitialize"
0x1800b2fcd  mov     dword ptr [rbp+arg_0], 8000FFFFh
0x1800b2fd4  mov     [rbp+arg_10], rax
0x1800b2fd8  lea     rax, [rbp+arg_8]
0x1800b2fdc  mov     [rsp+40h+var_10], rax
0x1800b2fe1  lea     rax, [rbp+arg_0]
0x1800b2fe5  mov     [rsp+40h+lpThreadId], rax
0x1800b2fea  lea     rax, [rbp+arg_10]
0x1800b2fee  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x1800b2ff3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800b2ff8  mov     ebx, 8000FFFFh
0x1800b2ffd  mov     rcx, rsi; hObject
0x1800b3000  call    cs:__imp_CloseHandle
0x1800b3006  mov     rcx, [rdi+38h]; hObject
0x1800b300a  test    rcx, rcx
0x1800b300d  jz      short loc_1800B3015
0x1800b300f  call    cs:__imp_CloseHandle
0x1800b3015  mov     eax, cs:dword_18015B128
0x1800b301b  test    ebx, ebx
0x1800b301d  js      short loc_1800B303C
0x1800b301f  cmp     eax, 4
0x1800b3022  jbe     short loc_1800B3085
0x1800b3024  mov     rdx, r12
0x1800b3027  mov     rcx, r15
0x1800b302a  call    _tlgKeywordOn
0x1800b302f  test    al, al
0x1800b3031  jz      short loc_1800B3085
0x1800b3033  lea     rdx, byte_18013BD2F
0x1800b303a  jmp     short loc_1800B3057
0x1800b303c  cmp     eax, 2
0x1800b303f  jbe     short loc_1800B3085
0x1800b3041  mov     rdx, r12
0x1800b3044  mov     rcx, r15
0x1800b3047  call    _tlgKeywordOn
0x1800b304c  test    al, al
0x1800b304e  jz      short loc_1800B3085
0x1800b3050  lea     rdx, byte_18013BDE3
0x1800b3057  lea     rax, aCinkdesktophos_2; "CInkDesktopHost::RuntimeClassInitialize"...
0x1800b305e  mov     [rbp+arg_8], rax
0x1800b3062  lea     rax, [rbp+arg_0]
0x1800b3066  mov     [rsp+40h+lpThreadId], rax
0x1800b306b  lea     rax, [rbp+arg_8]
0x1800b306f  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x1800b3074  xor     r9d, r9d
0x1800b3077  mov     dword ptr [rbp+arg_0], ebx
0x1800b307a  xor     r8d, r8d
0x1800b307d  mov     rcx, r15
0x1800b3080  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b3085  mov     eax, ebx
0x1800b3087  mov     rbx, [rsp+40h+arg_18]
0x1800b308f  add     rsp, 40h
0x1800b3093  pop     r15
0x1800b3095  pop     r12
0x1800b3097  pop     rdi
0x1800b3098  pop     rsi
0x1800b3099  pop     rbp
0x1800b309a  retn
```
