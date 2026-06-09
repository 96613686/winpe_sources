# CInkThread::_LaunchInkThread(void)

- ea: `0x18009f018`
- end: `0x18009f22c`
- name: `?_LaunchInkThread@CInkThread@@IEAAJXZ`
- size: `532`
- prototype: `__int64 __fastcall(CInkThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009eab0`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x18009f018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f1a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009f053`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009f053`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f108`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f108`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18009f19a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18009f19a`

## string_xrefs

- `0x18009f0b9`: `CInkThread::_LaunchInkThread`
- `0x18009f113`: `CInkThread::_LaunchInkThread`
- `0x18009f0ab`: `CreateThread`
- `0x18009f1e4`: `ResumeThread`
- `0x18009f15d`: `SetThreadPriority`

## pseudocode

```c
__int64 __fastcall CInkThread::_LaunchInkThread(CInkThread *this)
{
  HANDLE v1; // rsi
  signed int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  signed int LastError; // eax
  __int64 v9; // r8
  int v10; // ecx
  unsigned int v11; // r8d
  int v12; // r9d
  signed int v13; // eax
  __int64 v14; // r8
  int v15; // ecx
  unsigned int v16; // r8d
  int v17; // r9d
  DWORD ThreadId; // [rsp+70h] [rbp+28h] BYREF
  int v20; // [rsp+74h] [rbp+2Ch]
  unsigned int v21; // [rsp+78h] [rbp+30h] BYREF
  const wchar_t *v22; // [rsp+80h] [rbp+38h] BYREF
  const wchar_t *v23; // [rsp+88h] [rbp+40h] BYREF

  v20 = HIDWORD(this);
  ThreadId = 0;
  v1 = CreateThread(0, 0, CInkThread::s_InkThreadProc, &CMarshaller::s_inkThread, 4u, &ThreadId);
  if ( v1 )
  {
    dword_18015BF70 = ThreadId;
    hObject = v1;
    if ( !SetThreadPriority(v1, 2) )
    {
      LastError = GetLastError();
      v9 = (unsigned int)LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v9 = 2147500037LL;
      }
      if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v9) )
      {
        v21 = v11;
        v22 = L"SetThreadPriority";
        v23 = L"CInkThread::_LaunchInkThread";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v10,
          (unsigned int)word_18013780A,
          v11,
          v12,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
    if ( ResumeThread(v1) == -1 )
    {
      v13 = GetLastError();
      v14 = (unsigned int)v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
      }
      else
      {
        v14 = 2147500037LL;
      }
      if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v14) )
      {
        v21 = v16;
        v22 = L"ResumeThread";
        v23 = L"CInkThread::_LaunchInkThread";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)word_18013780A,
          v16,
          v17,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
    return 0;
  }
  else
  {
    v2 = GetLastError();
    v4 = v2;
    if ( v2 )
    {
      if ( v2 > 0 )
        v4 = (unsigned __int16)v2 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v3) )
    {
      v21 = v4;
      v22 = L"CreateThread";
      v23 = L"CInkThread::_LaunchInkThread";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v5,
        (unsigned int)word_18013780A,
        v6,
        v7,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18009f018  mov     qword ptr [rsp-20h+ThreadId], rcx
0x18009f01d  push    rbp
0x18009f01e  push    rbx
0x18009f01f  push    rsi
0x18009f020  push    r15
0x18009f022  mov     rbp, rsp
0x18009f025  sub     rsp, 48h
0x18009f029  lea     rax, [rbp+ThreadId]
0x18009f02d  mov     [rbp+ThreadId], 0
0x18009f034  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18009f039  lea     r9, ?s_inkThread@CMarshaller@@0VCInkThread@@A; lpParameter
0x18009f040  lea     r8, ?s_InkThreadProc@CInkThread@@KAKPEAX@Z; lpStartAddress
0x18009f047  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x18009f04f  xor     edx, edx; dwStackSize
0x18009f051  xor     ecx, ecx; lpThreadAttributes
0x18009f053  call    cs:__imp_CreateThread
0x18009f059  mov     rsi, rax
0x18009f05c  test    rax, rax
0x18009f05f  jnz     loc_18009F0F0
0x18009f065  call    cs:__imp_GetLastError
0x18009f06b  mov     ebx, eax
0x18009f06d  test    eax, eax
0x18009f06f  jz      short loc_18009F07E
0x18009f071  jle     short loc_18009F083
0x18009f073  movzx   ebx, ax
0x18009f076  or      ebx, 80070000h
0x18009f07c  jmp     short loc_18009F083
0x18009f07e  mov     ebx, 80004005h
0x18009f083  mov     eax, cs:dword_18015B128
0x18009f089  cmp     eax, 2
0x18009f08c  jbe     loc_18009F220
0x18009f092  mov     edx, 100h
0x18009f097  lea     rcx, dword_18015B128
0x18009f09e  call    _tlgKeywordOn
0x18009f0a3  test    al, al
0x18009f0a5  jz      loc_18009F220
0x18009f0ab  lea     rax, aCreatethread; "CreateThread"
0x18009f0b2  mov     [rbp+arg_8], ebx
0x18009f0b5  mov     [rbp+arg_10], rax
0x18009f0b9  lea     r15, aCinkthreadLaun; "CInkThread::_LaunchInkThread"
0x18009f0c0  lea     rax, [rbp+arg_10]
0x18009f0c4  mov     [rbp+arg_18], r15
0x18009f0c8  mov     [rsp+48h+var_18], rax
0x18009f0cd  lea     rdx, word_18013780A
0x18009f0d4  lea     rax, [rbp+arg_8]
0x18009f0d8  mov     [rsp+48h+lpThreadId], rax
0x18009f0dd  lea     rax, [rbp+arg_18]
0x18009f0e1  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18009f0e6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009f0eb  jmp     loc_18009F220
0x18009f0f0  mov     eax, [rbp+ThreadId]
0x18009f0f3  mov     edx, 2; nPriority
0x18009f0f8  mov     rcx, rsi; hThread
0x18009f0fb  mov     cs:dword_18015BF70, eax
0x18009f101  mov     cs:hObject, rsi
0x18009f108  call    cs:__imp_SetThreadPriority
0x18009f10e  mov     ebx, 80004005h
0x18009f113  lea     r15, aCinkthreadLaun; "CInkThread::_LaunchInkThread"
0x18009f11a  test    eax, eax
0x18009f11c  jnz     short loc_18009F197
0x18009f11e  call    cs:__imp_GetLastError
0x18009f124  mov     r8d, eax
0x18009f127  test    eax, eax
0x18009f129  jz      short loc_18009F13A
0x18009f12b  jle     short loc_18009F13D
0x18009f12d  movzx   r8d, ax
0x18009f131  or      r8d, 80070000h
0x18009f138  jmp     short loc_18009F13D
0x18009f13a  mov     r8d, ebx
0x18009f13d  mov     eax, cs:dword_18015B128
0x18009f143  cmp     eax, 2
0x18009f146  jbe     short loc_18009F197
0x18009f148  mov     edx, 100h
0x18009f14d  lea     rcx, dword_18015B128
0x18009f154  call    _tlgKeywordOn
0x18009f159  test    al, al
0x18009f15b  jz      short loc_18009F197
0x18009f15d  lea     rax, aSetthreadprior; "SetThreadPriority"
0x18009f164  mov     [rbp+arg_8], r8d
0x18009f168  mov     [rbp+arg_10], rax
0x18009f16c  lea     rdx, word_18013780A
0x18009f173  lea     rax, [rbp+arg_10]
0x18009f177  mov     [rbp+arg_18], r15
0x18009f17b  mov     [rsp+48h+var_18], rax
0x18009f180  lea     rax, [rbp+arg_8]
0x18009f184  mov     [rsp+48h+lpThreadId], rax
0x18009f189  lea     rax, [rbp+arg_18]
0x18009f18d  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18009f192  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009f197  mov     rcx, rsi; hThread
0x18009f19a  call    cs:__imp_ResumeThread
0x18009f1a0  cmp     eax, 0FFFFFFFFh
0x18009f1a3  jnz     short loc_18009F21E
0x18009f1a5  call    cs:__imp_GetLastError
0x18009f1ab  mov     r8d, eax
0x18009f1ae  test    eax, eax
0x18009f1b0  jz      short loc_18009F1C1
0x18009f1b2  jle     short loc_18009F1C4
0x18009f1b4  movzx   r8d, ax
0x18009f1b8  or      r8d, 80070000h
0x18009f1bf  jmp     short loc_18009F1C4
0x18009f1c1  mov     r8d, ebx
0x18009f1c4  mov     eax, cs:dword_18015B128
0x18009f1ca  cmp     eax, 2
0x18009f1cd  jbe     short loc_18009F21E
0x18009f1cf  mov     edx, 100h
0x18009f1d4  lea     rcx, dword_18015B128
0x18009f1db  call    _tlgKeywordOn
0x18009f1e0  test    al, al
0x18009f1e2  jz      short loc_18009F21E
0x18009f1e4  lea     rax, aResumethread; "ResumeThread"
0x18009f1eb  mov     [rbp+arg_8], r8d
0x18009f1ef  mov     [rbp+arg_10], rax
0x18009f1f3  lea     rdx, word_18013780A
0x18009f1fa  lea     rax, [rbp+arg_10]
0x18009f1fe  mov     [rbp+arg_18], r15
0x18009f202  mov     [rsp+48h+var_18], rax
0x18009f207  lea     rax, [rbp+arg_8]
0x18009f20b  mov     [rsp+48h+lpThreadId], rax
0x18009f210  lea     rax, [rbp+arg_18]
0x18009f214  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18009f219  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009f21e  xor     ebx, ebx
0x18009f220  mov     eax, ebx
0x18009f222  add     rsp, 48h
0x18009f226  pop     r15
0x18009f228  pop     rsi
0x18009f229  pop     rbx
0x18009f22a  pop     rbp
0x18009f22b  retn
```
