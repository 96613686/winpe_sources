# GipQuiesceWatcher::RequestQuiesceNotification(void)

- ea: `0x18001a2bc`
- end: `0x18001a5f9`
- name: `?RequestQuiesceNotification@GipQuiesceWatcher@@AEAAJXZ`
- size: `829`
- prototype: `__int64 __fastcall(GipQuiesceWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012ac4`
- `0x180021f3c`

## callees

- `0x180001304`
- `0x1800023a4`
- `0x18000248c`
- `0x18001a2bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a334`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a334`

## string_xrefs

- `0x18001a38b`: `GIP quiesce notification completed immediately, retrying`

## pseudocode

```c
__int64 __fastcall GipQuiesceWatcher::RequestQuiesceNotification(GipQuiesceWatcher *this)
{
  struct _OVERLAPPED *lpOverlapped; // r15
  char v3; // si
  const char **v4; // r14
  void *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  signed int LastError; // ebx
  const char *v10; // [rsp+50h] [rbp-10h] BYREF
  const char *v11; // [rsp+58h] [rbp-8h] BYREF
  int v12; // [rsp+98h] [rbp+38h] BYREF
  const char *v13; // [rsp+A0h] [rbp+40h] BYREF
  const char *v14; // [rsp+A8h] [rbp+48h] BYREF

  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 16);
  v3 = 0;
  v4 = (const char **)((char *)this + 48);
  while ( 1 )
  {
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    v5 = *(void **)this;
    *((_QWORD *)this + 5) = *((_QWORD *)this + 1);
    if ( DeviceIoControl(v5, 0x40001DC0u, v4, 8u, 0, 0, 0, lpOverlapped) )
    {
      if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v13 = *v4;
        v14 = "GIP quiesce notification completed immediately, retrying";
        v12 = 184;
        v10 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          qword_180069018,
          (unsigned int)&word_18005A68E,
          v6,
          v7,
          (__int64)&v10,
          (__int64)&v12,
          (__int64)&v14,
          (__int64)&v13);
      }
      goto LABEL_13;
    }
    LastError = GetLastError();
    if ( LastError == 997 )
      break;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v14 = *v4;
      v10 = "GIP quiesce notification request failed";
      v11 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
      v12 = LastError;
      LODWORD(v13) = 208;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005C7F9,
        v6,
        v7,
        (__int64)&v11,
        (__int64)&v13,
        (__int64)&v10,
        (__int64)&v14,
        (__int64)&v12);
    }
    if ( LastError )
    {
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v12 = LastError;
        v14 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
        LODWORD(v13) = 210;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned __int8 *)byte_18005E439,
          v6,
          v7,
          (__int64 **)&v14,
          (__int64)&v13,
          (__int64)&v12);
      }
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)LastError;
    }
LABEL_13:
    if ( (unsigned __int8)++v3 >= 0x32u )
    {
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v12 = -2147418113;
        LODWORD(v13) = 216;
        v14 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned __int8 *)&unk_18005C990,
          v6,
          v7,
          (__int64 **)&v14,
          (__int64)&v13,
          (__int64)&v12);
      }
      return 2147549183LL;
    }
  }
  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v13 = *v4;
    v14 = "GIP quiesce notification requested";
    v11 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
    v12 = 196;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      qword_180069018,
      (unsigned int)byte_18005A8B3,
      v6,
      v7,
      (__int64)&v11,
      (__int64)&v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  *((_BYTE *)this + 56) = 1;
  return 0;
}

```

## disassembly

```asm
0x18001a2bc  mov     [rsp-28h+arg_0], rbx
0x18001a2c1  push    rbp
0x18001a2c2  push    rsi
0x18001a2c3  push    rdi
0x18001a2c4  push    r14
0x18001a2c6  push    r15
0x18001a2c8  mov     rbp, rsp
0x18001a2cb  sub     rsp, 60h
0x18001a2cf  mov     rdi, rcx
0x18001a2d2  lea     r15, [rcx+10h]
0x18001a2d6  xor     sil, sil
0x18001a2d9  lea     r14, [rcx+30h]
0x18001a2dd  lea     rbx, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x18001a2e4  mov     qword ptr [rdi+10h], 0
0x18001a2ec  mov     r9d, 8; nInBufferSize
0x18001a2f2  mov     qword ptr [rdi+18h], 0
0x18001a2fa  mov     r8, r14; lpInBuffer
0x18001a2fd  mov     qword ptr [rdi+20h], 0
0x18001a305  mov     edx, 40001DC0h; dwIoControlCode
0x18001a30a  mov     rax, [rdi+8]
0x18001a30e  mov     rcx, [rdi]; hDevice
0x18001a311  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18001a316  mov     [rsp+60h+lpBytesReturned], 0; lpBytesReturned
0x18001a31f  mov     [rsp+60h+nOutBufferSize], 0; nOutBufferSize
0x18001a327  mov     [rdi+28h], rax
0x18001a32b  mov     [rsp+60h+lpOutBuffer], 0; lpOutBuffer
0x18001a334  call    cs:__imp_DeviceIoControl
0x18001a33b  nop     dword ptr [rax+rax+00h]
0x18001a340  cmp     eax, 1
0x18001a343  jnz     loc_18001A3CF
0x18001a349  mov     eax, cs:dword_180069000
0x18001a34f  cmp     eax, 5
0x18001a352  jbe     loc_18001A47B
0x18001a358  mov     rcx, cs:qword_180069018
0x18001a35f  mov     rax, cs:qword_180069010
0x18001a366  test    al, 8
0x18001a368  jz      loc_18001A47B
0x18001a36e  mov     rax, rcx
0x18001a371  and     eax, 8
0x18001a374  cmp     rax, rcx
0x18001a377  jnz     loc_18001A47B
0x18001a37d  mov     rax, [r14]
0x18001a380  lea     rdx, word_18005A68E
0x18001a387  mov     [rbp+arg_10], rax
0x18001a38b  lea     rax, aGipQuiesceNoti_3; "GIP quiesce notification completed imme"...
0x18001a392  mov     [rbp+arg_18], rax
0x18001a396  lea     rax, [rbp+arg_10]
0x18001a39a  mov     [rsp+60h+lpOverlapped], rax
0x18001a39f  lea     rax, [rbp+arg_18]
0x18001a3a3  mov     [rsp+60h+lpBytesReturned], rax
0x18001a3a8  lea     rax, [rbp+arg_8]
0x18001a3ac  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x18001a3b1  lea     rax, [rbp+var_10]
0x18001a3b5  mov     [rsp+60h+lpOutBuffer], rax
0x18001a3ba  mov     [rbp+arg_8], 0B8h
0x18001a3c1  mov     [rbp+var_10], rbx
0x18001a3c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001a3ca  jmp     loc_18001A47B
0x18001a3cf  call    cs:__imp_GetLastError
0x18001a3d6  nop     dword ptr [rax+rax+00h]
0x18001a3db  mov     ebx, eax
0x18001a3dd  cmp     eax, 3E5h
0x18001a3e2  mov     eax, cs:dword_180069000
0x18001a3e8  jz      loc_18001A568
0x18001a3ee  cmp     eax, 2
0x18001a3f1  jbe     short loc_18001A470
0x18001a3f3  mov     rcx, cs:qword_180069018
0x18001a3fa  mov     rax, cs:qword_180069010
0x18001a401  test    al, 8
0x18001a403  jz      short loc_18001A470
0x18001a405  mov     rax, rcx
0x18001a408  and     eax, 8
0x18001a40b  cmp     rax, rcx
0x18001a40e  jnz     short loc_18001A470
0x18001a410  mov     rax, [r14]
0x18001a413  lea     rdx, byte_18005C7F9
0x18001a41a  mov     [rbp+arg_18], rax
0x18001a41e  lea     rax, aGipQuiesceNoti; "GIP quiesce notification request failed"
0x18001a425  mov     [rbp+var_10], rax
0x18001a429  lea     rax, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x18001a430  mov     [rbp+var_8], rax
0x18001a434  lea     rax, [rbp+arg_8]
0x18001a438  mov     [rsp+60h+var_20], rax
0x18001a43d  lea     rax, [rbp+arg_18]
0x18001a441  mov     [rsp+60h+lpOverlapped], rax
0x18001a446  lea     rax, [rbp+var_10]
0x18001a44a  mov     [rsp+60h+lpBytesReturned], rax
0x18001a44f  lea     rax, [rbp+arg_10]
0x18001a453  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x18001a458  lea     rax, [rbp+var_8]
0x18001a45c  mov     [rsp+60h+lpOutBuffer], rax
0x18001a461  mov     [rbp+arg_8], ebx
0x18001a464  mov     dword ptr [rbp+arg_10], 0D0h
0x18001a46b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001a470  test    ebx, ebx
0x18001a472  jnz     short loc_18001A4F3
0x18001a474  lea     rbx, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x18001a47b  inc     sil
0x18001a47e  cmp     sil, 32h ; '2'
0x18001a482  jb      loc_18001A2E4
0x18001a488  mov     eax, cs:dword_180069000
0x18001a48e  cmp     eax, 2
0x18001a491  jbe     short loc_18001A4E9
0x18001a493  mov     rcx, cs:qword_180069018
0x18001a49a  mov     rax, cs:qword_180069010
0x18001a4a1  test    al, 8
0x18001a4a3  jz      short loc_18001A4E9
0x18001a4a5  mov     rax, rcx
0x18001a4a8  and     eax, 8
0x18001a4ab  cmp     rax, rcx
0x18001a4ae  jnz     short loc_18001A4E9
0x18001a4b0  lea     rax, [rbp+arg_8]
0x18001a4b4  mov     [rbp+arg_8], 8000FFFFh
0x18001a4bb  mov     [rsp+60h+lpBytesReturned], rax
0x18001a4c0  lea     rdx, unk_18005C990
0x18001a4c7  lea     rax, [rbp+arg_10]
0x18001a4cb  mov     dword ptr [rbp+arg_10], 0D8h
0x18001a4d2  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x18001a4d7  lea     rax, [rbp+arg_18]
0x18001a4db  mov     [rsp+60h+lpOutBuffer], rax
0x18001a4e0  mov     [rbp+arg_18], rbx
0x18001a4e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a4e9  mov     eax, 8000FFFFh
0x18001a4ee  jmp     loc_18001A5E4
0x18001a4f3  mov     eax, cs:dword_180069000
0x18001a4f9  cmp     eax, 2
0x18001a4fc  jbe     short loc_18001A557
0x18001a4fe  mov     rcx, cs:qword_180069018
0x18001a505  mov     rax, cs:qword_180069010
0x18001a50c  test    al, 8
0x18001a50e  jz      short loc_18001A557
0x18001a510  mov     rax, rcx
0x18001a513  and     eax, 8
0x18001a516  cmp     rax, rcx
0x18001a519  jnz     short loc_18001A557
0x18001a51b  lea     rax, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x18001a522  mov     [rbp+arg_8], ebx
0x18001a525  mov     [rbp+arg_18], rax
0x18001a529  lea     rdx, byte_18005E439
0x18001a530  lea     rax, [rbp+arg_8]
0x18001a534  mov     dword ptr [rbp+arg_10], 0D2h
0x18001a53b  mov     [rsp+60h+lpBytesReturned], rax
0x18001a540  lea     rax, [rbp+arg_10]
0x18001a544  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x18001a549  lea     rax, [rbp+arg_18]
0x18001a54d  mov     [rsp+60h+lpOutBuffer], rax
0x18001a552  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a557  test    ebx, ebx
0x18001a559  jle     short loc_18001A564
0x18001a55b  movzx   ebx, bx
0x18001a55e  or      ebx, 80070000h
0x18001a564  mov     eax, ebx
0x18001a566  jmp     short loc_18001A5E4
0x18001a568  cmp     eax, 5
0x18001a56b  jbe     short loc_18001A5DE
0x18001a56d  mov     rcx, cs:qword_180069018
0x18001a574  mov     rax, cs:qword_180069010
0x18001a57b  test    al, 8
0x18001a57d  jz      short loc_18001A5DE
0x18001a57f  mov     rax, rcx
0x18001a582  and     eax, 8
0x18001a585  cmp     rax, rcx
0x18001a588  jnz     short loc_18001A5DE
0x18001a58a  mov     rax, [r14]
0x18001a58d  lea     rdx, byte_18005A8B3
0x18001a594  mov     [rbp+arg_10], rax
0x18001a598  lea     rax, aGipQuiesceNoti_0; "GIP quiesce notification requested"
0x18001a59f  mov     [rbp+arg_18], rax
0x18001a5a3  lea     rax, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x18001a5aa  mov     [rbp+var_8], rax
0x18001a5ae  lea     rax, [rbp+arg_10]
0x18001a5b2  mov     [rsp+60h+lpOverlapped], rax
0x18001a5b7  lea     rax, [rbp+arg_18]
0x18001a5bb  mov     [rsp+60h+lpBytesReturned], rax
0x18001a5c0  lea     rax, [rbp+arg_8]
0x18001a5c4  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x18001a5c9  lea     rax, [rbp+var_8]
0x18001a5cd  mov     [rsp+60h+lpOutBuffer], rax
0x18001a5d2  mov     [rbp+arg_8], 0C4h
0x18001a5d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001a5de  mov     byte ptr [rdi+38h], 1
0x18001a5e2  xor     eax, eax
0x18001a5e4  mov     rbx, [rsp+60h+arg_0]
0x18001a5ec  add     rsp, 60h
0x18001a5f0  pop     r15
0x18001a5f2  pop     r14
0x18001a5f4  pop     rdi
0x18001a5f5  pop     rsi
0x18001a5f6  pop     rbp
0x18001a5f7  retn
```
