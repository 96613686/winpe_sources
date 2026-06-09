# GetFileVersion

- ea: `0x140002340`
- end: `0x1400025f6`
- name: `GetFileVersion`
- size: `694`
- prototype: `__int64 __fastcall(LPCWSTR lptstrFilename, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140002798`

## callees

- `0x140001008`
- `0x140002340`
- `0x140006b48`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000241c`
- `ntdll!RtlAllocateHeap` at `0x14000241c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400024c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400024c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002572`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1400024b9`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1400024b9`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x140002366`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x140002366`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140002568`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140002568`

## pseudocode

```c
__int64 __fastcall GetFileVersion(LPCWSTR lptstrFilename, _QWORD *a2)
{
  DWORD FileVersionInfoSizeW; // eax
  DWORD v5; // ebx
  signed int LastError; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  PVOID Heap; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  void *v12; // rdi
  __int64 v13; // r8
  __int64 v14; // r9
  __int16 *v15; // rdx
  unsigned int puLen; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-18h] BYREF
  __int64 *v19[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwHandle; // [rsp+98h] [rbp+38h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+40h] BYREF
  int v22; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  dwHandle = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
  v5 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      LODWORD(v21) = LastError;
      v19[0] = (__int64 *)"onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
      v22 = 16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        2048,
        (int)&word_14000A896,
        v7,
        v8,
        v19,
        (__int64)&v22,
        (__int64)&v21);
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
    return (unsigned int)LastError;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, FileVersionInfoSizeW);
  v12 = Heap;
  if ( Heap )
  {
    if ( GetFileVersionInfoW(lptstrFilename, 0, v5, Heap) )
    {
      lpBuffer = 0;
      puLen = 0;
      if ( VerQueryValueW(v12, L"\\", &lpBuffer, &puLen) )
      {
        LastError = 0;
        HIDWORD(v21) = *((_DWORD *)lpBuffer + 2);
        LODWORD(v21) = *((_DWORD *)lpBuffer + 3);
        *a2 = v21;
LABEL_31:
        operator delete[](v12);
        return (unsigned int)LastError;
      }
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v22 = 30;
        v15 = &word_14000A7C6;
        goto LABEL_20;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v22 = 26;
        v15 = &word_14000A806;
LABEL_20:
        v19[0] = (__int64 *)"onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
        LODWORD(v21) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          2048,
          (int)v15,
          v13,
          v14,
          v19,
          (__int64)&v22,
          (__int64)&v21);
      }
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
    goto LABEL_31;
  }
  LastError = -2147024882;
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    LODWORD(v21) = -2147024882;
    v22 = 19;
    v19[0] = (__int64 *)"onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v19,
      (int)&word_14000A846,
      v10,
      v11,
      v19,
      (__int64)&v22,
      (__int64)&v21);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140002340  push    rbp
0x140002342  push    rbx
0x140002343  push    rsi
0x140002344  push    rdi
0x140002345  push    r14
0x140002347  mov     rbp, rsp
0x14000234a  sub     rsp, 60h
0x14000234e  mov     rsi, rdx
0x140002351  mov     qword ptr [rdx], 0
0x140002358  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x14000235c  mov     [rbp+dwHandle], 0
0x140002363  mov     r14, rcx
0x140002366  call    cs:__imp_GetFileVersionInfoSizeW
0x14000236c  mov     ebx, eax
0x14000236e  test    eax, eax
0x140002370  jnz     loc_14000240A
0x140002376  call    cs:__imp_GetLastError
0x14000237c  mov     ebx, eax
0x14000237e  mov     eax, cs:dword_14000E000
0x140002384  cmp     eax, 2
0x140002387  jbe     short loc_1400023E8
0x140002389  mov     rdx, cs:qword_14000E018
0x140002390  mov     ecx, 800h
0x140002395  mov     rax, cs:qword_14000E010
0x14000239c  test    rcx, rax
0x14000239f  jz      short loc_1400023E8
0x1400023a1  mov     rax, rdx
0x1400023a4  and     rax, rcx
0x1400023a7  cmp     rax, rdx
0x1400023aa  jnz     short loc_1400023E8
0x1400023ac  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400023b3  mov     dword ptr [rbp+arg_10], ebx
0x1400023b6  mov     [rbp+var_10], rax
0x1400023ba  lea     rdx, word_14000A896
0x1400023c1  lea     rax, [rbp+arg_10]
0x1400023c5  mov     [rbp+arg_18], 10h
0x1400023cc  mov     [rsp+60h+var_30], rax
0x1400023d1  lea     rax, [rbp+arg_18]
0x1400023d5  mov     [rsp+60h+var_38], rax
0x1400023da  lea     rax, [rbp+var_10]
0x1400023de  mov     [rsp+60h+var_40], rax
0x1400023e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400023e8  test    ebx, ebx
0x1400023ea  jnz     short loc_1400023F6
0x1400023ec  mov     ebx, 8000FFFFh
0x1400023f1  jmp     loc_1400025E9
0x1400023f6  jle     loc_1400025E9
0x1400023fc  movzx   ebx, bx
0x1400023ff  or      ebx, 80070000h
0x140002405  jmp     loc_1400025E9
0x14000240a  mov     rcx, gs:60h
0x140002413  mov     r8, rbx; Size
0x140002416  xor     edx, edx; Flags
0x140002418  mov     rcx, [rcx+30h]; HeapHandle
0x14000241c  call    cs:__imp_RtlAllocateHeap
0x140002422  mov     rdi, rax
0x140002425  test    rax, rax
0x140002428  jnz     loc_1400024AE
0x14000242e  mov     eax, cs:dword_14000E000
0x140002434  mov     ebx, 8007000Eh
0x140002439  cmp     eax, 2
0x14000243c  jbe     loc_1400025E9
0x140002442  mov     rdx, cs:qword_14000E018
0x140002449  mov     ecx, 800h
0x14000244e  mov     rax, cs:qword_14000E010
0x140002455  test    rcx, rax
0x140002458  jz      loc_1400025E9
0x14000245e  mov     rax, rdx
0x140002461  and     rax, rcx
0x140002464  cmp     rax, rdx
0x140002467  jnz     loc_1400025E9
0x14000246d  lea     rcx, [rbp+arg_10]
0x140002471  mov     dword ptr [rbp+arg_10], ebx
0x140002474  mov     [rsp+60h+var_30], rcx
0x140002479  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002480  lea     rcx, [rbp+arg_18]
0x140002484  mov     [rbp+arg_18], 13h
0x14000248b  mov     [rsp+60h+var_38], rcx
0x140002490  lea     rdx, word_14000A846
0x140002497  lea     rcx, [rbp+var_10]
0x14000249b  mov     [rbp+var_10], rax
0x14000249f  mov     [rsp+60h+var_40], rcx
0x1400024a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400024a9  jmp     loc_1400025E9
0x1400024ae  mov     r9, rdi; lpData
0x1400024b1  mov     r8d, ebx; dwLen
0x1400024b4  xor     edx, edx; dwHandle
0x1400024b6  mov     rcx, r14; lptstrFilename
0x1400024b9  call    cs:__imp_GetFileVersionInfoW
0x1400024bf  test    eax, eax
0x1400024c1  jnz     loc_140002547
0x1400024c7  call    cs:__imp_GetLastError
0x1400024cd  mov     ebx, eax
0x1400024cf  mov     eax, cs:dword_14000E000
0x1400024d5  cmp     eax, 2
0x1400024d8  jbe     short loc_140002539
0x1400024da  mov     rdx, cs:qword_14000E018
0x1400024e1  mov     ecx, 800h
0x1400024e6  mov     rax, cs:qword_14000E010
0x1400024ed  test    rcx, rax
0x1400024f0  jz      short loc_140002539
0x1400024f2  mov     rax, rdx
0x1400024f5  and     rax, rcx
0x1400024f8  cmp     rax, rdx
0x1400024fb  jnz     short loc_140002539
0x1400024fd  mov     [rbp+arg_18], 1Ah
0x140002504  lea     rdx, word_14000A806
0x14000250b  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002512  mov     [rbp+var_10], rax
0x140002516  lea     rax, [rbp+arg_10]
0x14000251a  mov     [rsp+60h+var_30], rax
0x14000251f  lea     rax, [rbp+arg_18]
0x140002523  mov     [rsp+60h+var_38], rax
0x140002528  lea     rax, [rbp+var_10]
0x14000252c  mov     [rsp+60h+var_40], rax
0x140002531  mov     dword ptr [rbp+arg_10], ebx
0x140002534  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140002539  test    ebx, ebx
0x14000253b  jnz     short loc_1400025BB
0x14000253d  mov     ebx, 8000FFFFh
0x140002542  jmp     loc_1400025E1
0x140002547  lea     r9, [rbp+puLen]; puLen
0x14000254b  mov     [rbp+lpBuffer], 0
0x140002553  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x140002557  mov     [rbp+puLen], 0
0x14000255e  lea     rdx, SubBlock; "\\"
0x140002565  mov     rcx, rdi; pBlock
0x140002568  call    cs:__imp_VerQueryValueW
0x14000256e  test    eax, eax
0x140002570  jnz     short loc_1400025C8
0x140002572  call    cs:__imp_GetLastError
0x140002578  mov     ebx, eax
0x14000257a  mov     eax, cs:dword_14000E000
0x140002580  cmp     eax, 2
0x140002583  jbe     short loc_140002539
0x140002585  mov     rdx, cs:qword_14000E018
0x14000258c  mov     ecx, 800h
0x140002591  mov     rax, cs:qword_14000E010
0x140002598  test    rcx, rax
0x14000259b  jz      short loc_140002539
0x14000259d  mov     rax, rdx
0x1400025a0  and     rax, rcx
0x1400025a3  cmp     rax, rdx
0x1400025a6  jnz     short loc_140002539
0x1400025a8  mov     [rbp+arg_18], 1Eh
0x1400025af  lea     rdx, word_14000A7C6
0x1400025b6  jmp     loc_14000250B
0x1400025bb  jle     short loc_1400025E1
0x1400025bd  movzx   ebx, bx
0x1400025c0  or      ebx, 80070000h
0x1400025c6  jmp     short loc_1400025E1
0x1400025c8  mov     rcx, [rbp+lpBuffer]
0x1400025cc  xor     ebx, ebx
0x1400025ce  mov     eax, [rcx+8]
0x1400025d1  mov     dword ptr [rbp+arg_10+4], eax
0x1400025d4  mov     eax, [rcx+0Ch]
0x1400025d7  mov     dword ptr [rbp+arg_10], eax
0x1400025da  mov     rax, [rbp+arg_10]
0x1400025de  mov     [rsi], rax
0x1400025e1  mov     rcx, rdi; P
0x1400025e4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400025e9  mov     eax, ebx
0x1400025eb  add     rsp, 60h
0x1400025ef  pop     r14
0x1400025f1  pop     rdi
0x1400025f2  pop     rsi
0x1400025f3  pop     rbx
0x1400025f4  pop     rbp
0x1400025f5  retn
```
