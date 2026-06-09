# XusbWatcher::Create(GameInputServerDevice *,Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *,XusbWatcher * *)

- ea: `0x18002fca4`
- end: `0x180030302`
- name: `?Create@XusbWatcher@@SAJPEAVGameInputServerDevice@@PEAUIGameControllerProviderPrivate@Internal@Input@Gaming@Windows@@PEAPEAV1@@Z`
- size: `1630`
- prototype: `__int64 __fastcall(struct GameInputServerDevice *, struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, struct XusbWatcher **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18003197c`

## callees

- `0x180001304`
- `0x180001540`
- `0x18002fca4`
- `0x18003b830`
- `0x18003c7e4`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003010c`
- `ntdll!RtlAllocateHeap` at `0x18003010c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fed4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fed4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fdef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fdef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030178`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003023f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030178`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003023f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002feec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002feec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fe9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ff92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800300cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003018d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fd8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fe9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ff92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800300cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003018d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002fdbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002fdbd`

## pseudocode

```c
__int64 __fastcall XusbWatcher::Create(
        struct GameInputServerDevice *a1,
        __int64 (__fastcall ***a2)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *),
        struct XusbWatcher **a3)
{
  __int64 (__fastcall **v5)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *); // rax
  int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  __int64 (__fastcall **v10)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *); // rax
  __int64 v11; // rbx
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // r8
  int v15; // r9d
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rdi
  signed int LastError; // esi
  int v20; // r8d
  int v21; // r9d
  HANDLE EventW; // rax
  void *v23; // rsi
  int v24; // r8d
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  const char *v29; // rax
  __int64 *v30; // rdx
  _QWORD *Heap; // rax
  int v32; // r8d
  int v33; // r9d
  _QWORD *v34; // r14
  int v35; // r15d
  __int128 v36; // xmm0
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  __int64 v38; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v39[4]; // [rsp+50h] [rbp-20h] BYREF
  int v40; // [rsp+B8h] [rbp+48h] BYREF
  int v41; // [rsp+C0h] [rbp+50h] BYREF
  const char *v42; // [rsp+C8h] [rbp+58h] BYREF

  *a3 = 0;
  v5 = *a2;
  v38 = 0;
  v7 = (*v5)(
         (struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *)a2,
         &GUID_ac104f57_79bd_4af3_9675_5e667484818b,
         &v38);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v41 = v7;
      v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
      LODWORD(v42) = 49;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&byte_180062B37,
        v8,
        v9,
        (__int64)v39,
        (__int64)&v42,
        (__int64)&v41);
    }
    return (unsigned int)v7;
  }
  else
  {
    v10 = *a2;
    v11 = v38;
    string = 0;
    v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *), HSTRING *))v10[17])(
            a2,
            &string);
    if ( v13 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v14 = qword_180069018;
        v12 = 1024;
        if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
        {
          v41 = v13;
          v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
          LODWORD(v42) = 52;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&dword_180061E4C,
            qword_180069018,
            v15,
            (__int64)v39,
            (__int64)&v42,
            (__int64)&v41);
        }
      }
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v11 + 16LL))(v11, v12, v14);
      return (unsigned int)v13;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FileW = CreateFileW(StringRawBuffer, 0xC0000000, 3u, 0, 3u, 0xE0000000, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v41 = LastError;
        v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
        LODWORD(v42) = 63;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)byte_18005F919,
          v20,
          v21,
          (__int64)v39,
          (__int64)&v42,
          (__int64)&v41);
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
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( !v11 )
        return (unsigned int)LastError;
      goto LABEL_24;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    v23 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v41 = LastError;
        v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
        LODWORD(v42) = 71;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)&word_18005F026,
          v24,
          v25,
          (__int64)v39,
          (__int64)&v42,
          (__int64)&v41);
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
      CloseHandle(FileW);
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( !v11 )
        return (unsigned int)LastError;
LABEL_24:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)LastError;
    }
    if ( !XusbWatcher::IsUnfilteredStateIOCTLSupported(FileW, EventW) )
    {
      if ( (unsigned int)dword_180069000 <= 3 )
        goto LABEL_50;
      v28 = qword_180069018;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_50;
      v29 = "Failed to query unfiltered gamepad state";
      v41 = 78;
      v30 = qword_180060030;
LABEL_49:
      v42 = v29;
      v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v28,
        (_DWORD)v30,
        v26,
        v27,
        (__int64)v39,
        (__int64)&v41,
        (__int64)&v42);
LABEL_50:
      CloseHandle(v23);
      CloseHandle(FileW);
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return 1;
    }
    v40 = 0;
    if ( !XusbWatcher::GetManagementDriver(FileW, (enum _GIP_SYSTEM_MANAGEMENT_DRIVER *)&v40, v23) )
    {
      if ( (unsigned int)dword_180069000 <= 3 )
        goto LABEL_50;
      v28 = qword_180069018;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_50;
      v29 = "Failed to query management driver";
      v41 = 86;
      v30 = (__int64 *)byte_18005EA95;
      goto LABEL_49;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x40u);
    v34 = Heap;
    if ( Heap )
    {
      v35 = v40;
      *Heap = FileW;
      Heap[1] = v23;
      Heap[2] = a1;
      Heap[3] = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      *((_BYTE *)v34 + 40) = 0;
      v34[4] = 0;
      memset(&v39[1], 0, 19);
      v36 = *(_OWORD *)&v39[1];
      *((_DWORD *)v34 + 15) = v35;
      *(_OWORD *)((char *)v34 + 41) = v36;
      *((_DWORD *)v34 + 14) = 0;
      *a3 = (struct XusbWatcher *)v34;
      CloseHandle(0);
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return 0;
    }
    else
    {
      *a3 = 0;
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v41 = -2147024882;
        v39[0] = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
        LODWORD(v42) = 92;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)byte_18005F0A3,
          v32,
          v33,
          (__int64)v39,
          (__int64)&v42,
          (__int64)&v41);
      }
      CloseHandle(v23);
      CloseHandle(FileW);
      if ( string )
      {
        WindowsDeleteString(string);
        string = 0;
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x18002fca4  mov     [rsp-38h+arg_0], rbx
0x18002fca9  push    rbp
0x18002fcaa  push    rsi
0x18002fcab  push    rdi
0x18002fcac  push    r12
0x18002fcae  push    r13
0x18002fcb0  push    r14
0x18002fcb2  push    r15
0x18002fcb4  mov     rbp, rsp
0x18002fcb7  sub     rsp, 70h
0x18002fcbb  mov     rdi, rdx
0x18002fcbe  xor     r15d, r15d
0x18002fcc1  mov     [r8], r15
0x18002fcc4  mov     r12, r8
0x18002fcc7  mov     rax, [rdx]
0x18002fcca  lea     r8, [rbp+var_28]
0x18002fcce  mov     r13, rcx
0x18002fcd1  mov     [rbp+var_28], r15
0x18002fcd5  lea     rdx, _GUID_ac104f57_79bd_4af3_9675_5e667484818b
0x18002fcdc  mov     rcx, rdi
0x18002fcdf  mov     rax, [rax]
0x18002fce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fce7  mov     ebx, eax
0x18002fce9  test    eax, eax
0x18002fceb  js      loc_18003027D
0x18002fcf1  mov     rax, [rdi]
0x18002fcf4  lea     rdx, [rbp+string]
0x18002fcf8  mov     rbx, [rbp+var_28]
0x18002fcfc  mov     rcx, rdi
0x18002fcff  mov     [rbp+string], r15
0x18002fd03  mov     rax, [rax+88h]
0x18002fd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd0f  mov     edi, eax
0x18002fd11  test    eax, eax
0x18002fd13  jns     loc_18002FDB7
0x18002fd19  mov     ecx, cs:dword_180069000
0x18002fd1f  cmp     ecx, 2
0x18002fd22  jbe     short loc_18002FD83
0x18002fd24  mov     r8, cs:qword_180069018
0x18002fd2b  mov     edx, 400h
0x18002fd30  mov     rcx, cs:qword_180069010
0x18002fd37  test    rdx, rcx
0x18002fd3a  jz      short loc_18002FD83
0x18002fd3c  mov     rax, r8
0x18002fd3f  and     rax, rdx
0x18002fd42  cmp     rax, r8
0x18002fd45  jnz     short loc_18002FD83
0x18002fd47  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x18002fd4e  mov     [rbp+arg_10], edi
0x18002fd51  mov     [rbp+var_20], rax
0x18002fd55  lea     rdx, dword_180061E4C
0x18002fd5c  lea     rax, [rbp+arg_10]
0x18002fd60  mov     dword ptr [rbp+arg_18], 34h ; '4'
0x18002fd67  mov     [rsp+70h+hTemplateFile], rax
0x18002fd6c  lea     rax, [rbp+arg_18]
0x18002fd70  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x18002fd75  lea     rax, [rbp+var_20]
0x18002fd79  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18002fd7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002fd83  mov     rcx, [rbp+string]; string
0x18002fd87  test    rcx, rcx
0x18002fd8a  jz      short loc_18002FD9C
0x18002fd8c  call    cs:__imp_WindowsDeleteString
0x18002fd93  nop     dword ptr [rax+rax+00h]
0x18002fd98  mov     [rbp+string], r15
0x18002fd9c  test    rbx, rbx
0x18002fd9f  jz      short loc_18002FDB0
0x18002fda1  mov     rax, [rbx]
0x18002fda4  mov     rcx, rbx
0x18002fda7  mov     rax, [rax+10h]
0x18002fdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb0  mov     eax, edi
0x18002fdb2  jmp     loc_1800302E9
0x18002fdb7  mov     rcx, [rbp+string]; string
0x18002fdbb  xor     edx, edx; length
0x18002fdbd  call    cs:__imp_WindowsGetStringRawBuffer
0x18002fdc4  nop     dword ptr [rax+rax+00h]
0x18002fdc9  mov     r14d, 3
0x18002fdcf  mov     [rsp+70h+hTemplateFile], r15; hTemplateFile
0x18002fdd4  mov     rcx, rax; lpFileName
0x18002fdd7  mov     [rsp+70h+dwFlagsAndAttributes], 0E0000000h; dwFlagsAndAttributes
0x18002fddf  mov     r8d, r14d; dwShareMode
0x18002fde2  mov     [rsp+70h+dwCreationDisposition], r14d; dwCreationDisposition
0x18002fde7  xor     r9d, r9d; lpSecurityAttributes
0x18002fdea  mov     edx, 0C0000000h; dwDesiredAccess
0x18002fdef  call    cs:__imp_CreateFileW
0x18002fdf6  nop     dword ptr [rax+rax+00h]
0x18002fdfb  mov     rdi, rax
0x18002fdfe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fe02  jnz     loc_18002FECA
0x18002fe08  call    cs:__imp_GetLastError
0x18002fe0f  nop     dword ptr [rax+rax+00h]
0x18002fe14  mov     esi, eax
0x18002fe16  mov     eax, cs:dword_180069000
0x18002fe1c  cmp     eax, 2
0x18002fe1f  jbe     short loc_18002FE80
0x18002fe21  mov     rcx, cs:qword_180069018
0x18002fe28  mov     edx, 400h
0x18002fe2d  mov     rax, cs:qword_180069010
0x18002fe34  test    rdx, rax
0x18002fe37  jz      short loc_18002FE80
0x18002fe39  mov     rax, rcx
0x18002fe3c  and     rax, rdx
0x18002fe3f  cmp     rax, rcx
0x18002fe42  jnz     short loc_18002FE80
0x18002fe44  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x18002fe4b  mov     [rbp+arg_10], esi
0x18002fe4e  mov     [rbp+var_20], rax
0x18002fe52  lea     rdx, byte_18005F919
0x18002fe59  lea     rax, [rbp+arg_10]
0x18002fe5d  mov     dword ptr [rbp+arg_18], 3Fh ; '?'
0x18002fe64  mov     [rsp+70h+hTemplateFile], rax
0x18002fe69  lea     rax, [rbp+arg_18]
0x18002fe6d  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x18002fe72  lea     rax, [rbp+var_20]
0x18002fe76  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18002fe7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002fe80  test    esi, esi
0x18002fe82  jnz     short loc_18002FE8B
0x18002fe84  mov     esi, 8000FFFFh
0x18002fe89  jmp     short loc_18002FE96
0x18002fe8b  jle     short loc_18002FE96
0x18002fe8d  movzx   esi, si
0x18002fe90  or      esi, 80070000h
0x18002fe96  mov     rcx, [rbp+string]; string
0x18002fe9a  test    rcx, rcx
0x18002fe9d  jz      short loc_18002FEAF
0x18002fe9f  call    cs:__imp_WindowsDeleteString
0x18002fea6  nop     dword ptr [rax+rax+00h]
0x18002feab  mov     [rbp+string], r15
0x18002feaf  test    rbx, rbx
0x18002feb2  jz      short loc_18002FEC3
0x18002feb4  mov     rax, [rbx]
0x18002feb7  mov     rax, [rax+10h]
0x18002febb  mov     rcx, rbx
0x18002febe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fec3  mov     eax, esi
0x18002fec5  jmp     loc_1800302E9
0x18002feca  xor     r9d, r9d; lpName
0x18002fecd  xor     r8d, r8d; bInitialState
0x18002fed0  xor     edx, edx; bManualReset
0x18002fed2  xor     ecx, ecx; lpEventAttributes
0x18002fed4  call    cs:__imp_CreateEventW
0x18002fedb  nop     dword ptr [rax+rax+00h]
0x18002fee0  mov     rsi, rax
0x18002fee3  test    rax, rax
0x18002fee6  jnz     loc_18002FFB7
0x18002feec  call    cs:__imp_GetLastError
0x18002fef3  nop     dword ptr [rax+rax+00h]
0x18002fef8  mov     esi, eax
0x18002fefa  mov     eax, cs:dword_180069000
0x18002ff00  cmp     eax, 2
0x18002ff03  jbe     short loc_18002FF64
0x18002ff05  mov     rcx, cs:qword_180069018
0x18002ff0c  mov     edx, 400h
0x18002ff11  mov     rax, cs:qword_180069010
0x18002ff18  test    rdx, rax
0x18002ff1b  jz      short loc_18002FF64
0x18002ff1d  mov     rax, rcx
0x18002ff20  and     rax, rdx
0x18002ff23  cmp     rax, rcx
0x18002ff26  jnz     short loc_18002FF64
0x18002ff28  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x18002ff2f  mov     [rbp+arg_10], esi
0x18002ff32  mov     [rbp+var_20], rax
0x18002ff36  lea     rdx, word_18005F026
0x18002ff3d  lea     rax, [rbp+arg_10]
0x18002ff41  mov     dword ptr [rbp+arg_18], 47h ; 'G'
0x18002ff48  mov     [rsp+70h+hTemplateFile], rax
0x18002ff4d  lea     rax, [rbp+arg_18]
0x18002ff51  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x18002ff56  lea     rax, [rbp+var_20]
0x18002ff5a  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18002ff5f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002ff64  test    esi, esi
0x18002ff66  jnz     short loc_18002FF6F
0x18002ff68  mov     esi, 8000FFFFh
0x18002ff6d  jmp     short loc_18002FF7A
0x18002ff6f  jle     short loc_18002FF7A
0x18002ff71  movzx   esi, si
0x18002ff74  or      esi, 80070000h
0x18002ff7a  mov     rcx, rdi; hObject
0x18002ff7d  call    cs:__imp_CloseHandle
0x18002ff84  nop     dword ptr [rax+rax+00h]
0x18002ff89  mov     rcx, [rbp+string]; string
0x18002ff8d  test    rcx, rcx
0x18002ff90  jz      short loc_18002FFA2
0x18002ff92  call    cs:__imp_WindowsDeleteString
0x18002ff99  nop     dword ptr [rax+rax+00h]
0x18002ff9e  mov     [rbp+string], r15
0x18002ffa2  test    rbx, rbx
0x18002ffa5  jz      loc_18002FEC3
0x18002ffab  mov     rcx, [rbx]
0x18002ffae  mov     rax, [rcx+10h]
0x18002ffb2  jmp     loc_18002FEBB
0x18002ffb7  mov     rdx, rsi; Handle
0x18002ffba  mov     rcx, rdi; hFile
0x18002ffbd  call    ?IsUnfilteredStateIOCTLSupported@XusbWatcher@@CA_NPEAX0@Z; XusbWatcher::IsUnfilteredStateIOCTLSupported(void *,void *)
0x18002ffc2  test    al, al
0x18002ffc4  jnz     short loc_180030017
0x18002ffc6  mov     eax, cs:dword_180069000
0x18002ffcc  cmp     eax, r14d
0x18002ffcf  jbe     loc_1800300A4
0x18002ffd5  mov     rcx, cs:qword_180069018
0x18002ffdc  mov     edx, 400h
0x18002ffe1  mov     rax, cs:qword_180069010
0x18002ffe8  test    rdx, rax
0x18002ffeb  jz      loc_1800300A4
0x18002fff1  mov     rax, rcx
0x18002fff4  and     rax, rdx
0x18002fff7  cmp     rax, rcx
0x18002fffa  jnz     loc_1800300A4
0x180030000  lea     rax, aFailedToQueryU; "Failed to query unfiltered gamepad stat"...
0x180030007  mov     [rbp+arg_10], 4Eh ; 'N'
0x18003000e  lea     rdx, qword_180060030
0x180030015  jmp     short loc_180030075
0x180030017  mov     r8, rsi; void *
0x18003001a  mov     [rbp+arg_8], r15d
0x18003001e  lea     rdx, [rbp+arg_8]; enum _GIP_SYSTEM_MANAGEMENT_DRIVER *
0x180030022  mov     rcx, rdi; void *
0x180030025  call    ?GetManagementDriver@XusbWatcher@@CA_NPEAXPEAW4_GIP_SYSTEM_MANAGEMENT_DRIVER@@0@Z; XusbWatcher::GetManagementDriver(void *,_GIP_SYSTEM_MANAGEMENT_DRIVER *,void *)
0x18003002a  test    al, al
0x18003002c  jnz     loc_1800300F9
0x180030032  mov     eax, cs:dword_180069000
0x180030038  cmp     eax, r14d
0x18003003b  jbe     short loc_1800300A4
0x18003003d  mov     rcx, cs:qword_180069018
0x180030044  mov     edx, 400h
0x180030049  mov     rax, cs:qword_180069010
0x180030050  test    rdx, rax
0x180030053  jz      short loc_1800300A4
0x180030055  mov     rax, rcx
0x180030058  and     rax, rdx
0x18003005b  cmp     rax, rcx
0x18003005e  jnz     short loc_1800300A4
0x180030060  lea     rax, aFailedToQueryM; "Failed to query management driver"
0x180030067  mov     [rbp+arg_10], 56h ; 'V'
0x18003006e  lea     rdx, byte_18005EA95
0x180030075  mov     [rbp+arg_18], rax
0x180030079  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x180030080  mov     [rbp+var_20], rax
0x180030084  lea     rax, [rbp+arg_18]
0x180030088  mov     [rsp+70h+hTemplateFile], rax
0x18003008d  lea     rax, [rbp+arg_10]
0x180030091  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180030096  lea     rax, [rbp+var_20]
0x18003009a  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18003009f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800300a4  mov     rcx, rsi; hObject
0x1800300a7  call    cs:__imp_CloseHandle
0x1800300ae  nop     dword ptr [rax+rax+00h]
0x1800300b3  mov     rcx, rdi; hObject
0x1800300b6  call    cs:__imp_CloseHandle
0x1800300bd  nop     dword ptr [rax+rax+00h]
0x1800300c2  mov     rcx, [rbp+string]; string
0x1800300c6  test    rcx, rcx
0x1800300c9  jz      short loc_1800300DB
0x1800300cb  call    cs:__imp_WindowsDeleteString
0x1800300d2  nop     dword ptr [rax+rax+00h]
0x1800300d7  mov     [rbp+string], r15
0x1800300db  test    rbx, rbx
0x1800300de  jz      short loc_1800300EF
0x1800300e0  mov     rax, [rbx]
0x1800300e3  mov     rcx, rbx
0x1800300e6  mov     rax, [rax+10h]
0x1800300ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ef  mov     eax, 1
0x1800300f4  jmp     loc_1800302E9
0x1800300f9  mov     rcx, gs:60h
0x180030102  xor     edx, edx; Flags
0x180030104  mov     rcx, [rcx+30h]; HeapHandle
0x180030108  lea     r8d, [rdx+40h]; Size
0x18003010c  call    cs:__imp_RtlAllocateHeap
0x180030113  nop     dword ptr [rax+rax+00h]
0x180030118  mov     r14, rax
0x18003011b  test    rax, rax
0x18003011e  jz      loc_1800301B8
0x180030124  mov     r15d, [rbp+arg_8]
0x180030128  mov     [rax], rdi
0x18003012b  xor     edi, edi
0x18003012d  mov     [rax+8], rsi
0x180030131  mov     [rax+10h], r13
0x180030135  mov     [rax+18h], rbx
0x180030139  test    rbx, rbx
0x18003013c  jz      short loc_18003014D
0x18003013e  mov     rcx, [rbx]
0x180030141  mov     rax, [rcx+8]
0x180030145  mov     rcx, rbx
0x180030148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003014d  mov     [r14+28h], dil
0x180030151  xorps   xmm0, xmm0
0x180030154  xor     eax, eax
0x180030156  mov     [r14+20h], rdi
0x18003015a  movups  xmmword ptr [rbp+var_18], xmm0
0x18003015e  mov     dword ptr [rbp+var_18+0Fh], eax
0x180030161  xor     ecx, ecx; hObject
0x180030163  movups  xmm0, xmmword ptr [rbp+var_18]
0x180030167  mov     [r14+3Ch], r15d
0x18003016b  movups  xmmword ptr [r14+29h], xmm0
0x180030170  mov     [r14+38h], eax
  ... truncated ...
```
