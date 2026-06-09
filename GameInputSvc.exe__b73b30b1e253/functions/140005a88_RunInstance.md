# RunInstance

- ea: `0x140005a88`
- end: `0x140005c73`
- name: `RunInstance`
- size: `491`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005cb8`

## callees

- `0x140001008`
- `0x140001718`
- `0x140001cec`
- `0x140001d80`
- `0x140005a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005aaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c66`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005ad7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005ad7`

## pseudocode

```c
__int64 __fastcall RunInstance(unsigned __int16 *a1)
{
  int v2; // ebx
  HANDLE EventW; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  GameInputServerManager *v7; // rcx
  int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  int *v12; // rdx
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+78h] [rbp+28h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  const char *v16; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  while ( 1 )
  {
    EventW = CreateEventW(0, 0, 0, L"Local\\GameInputSvc-8C761C64-DD9B-403D-A557-072D78006269");
    if ( !EventW )
    {
LABEL_5:
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v14 = -2147418113;
        v16 = "onecore\\xbox\\gameinput\\published\\svc\\winmain.cpp";
        v15 = 98;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (int)&word_14000B85E,
          v4,
          v5,
          (__int64 **)&v16,
          (__int64)&v15,
          (__int64)&v14);
      }
      return 2147549183LL;
    }
    if ( GetLastError() != 183 )
      break;
    CloseHandle(EventW);
    Sleep(0x64u);
    if ( (unsigned int)++v2 >= 5 )
      goto LABEL_5;
  }
  v13 = 0;
  v8 = GameInputServerManager::Start((struct _RTL_CRITICAL_SECTION **)&v13);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 )
    {
      v10 = qword_14000E018;
      v11 = qword_14000E010;
      if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v15 = 101;
        v12 = (int *)byte_14000B821;
        goto LABEL_20;
      }
    }
    goto LABEL_21;
  }
  v8 = GameInputServerManager::WaitForStopOnEvent(v7, a1);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 )
    {
      v10 = qword_14000E018;
      v11 = qword_14000E010;
      if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v15 = 102;
        v12 = &dword_14000B7E4;
LABEL_20:
        v16 = "onecore\\xbox\\gameinput\\published\\svc\\winmain.cpp";
        v14 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v11,
          (int)v12,
          v10,
          v9,
          (__int64 **)&v16,
          (__int64)&v15,
          (__int64)&v14);
      }
    }
LABEL_21:
    GameInputServerManager::~GameInputServerManager((GameInputServerManager *)&v13);
    CloseHandle(EventW);
    return (unsigned int)v8;
  }
  GameInputServerManager::~GameInputServerManager((GameInputServerManager *)&v13);
  CloseHandle(EventW);
  return 0;
}

```

## disassembly

```asm
0x140005a88  mov     [rsp-18h+arg_0], rbx
0x140005a8d  push    rbp
0x140005a8e  push    rsi
0x140005a8f  push    rdi
0x140005a90  mov     rbp, rsp
0x140005a93  sub     rsp, 50h
0x140005a97  mov     rsi, rcx
0x140005a9a  xor     ebx, ebx
0x140005a9c  lea     r9, Name; "Local\\GameInputSvc-8C761C64-DD9B-403D-"...
0x140005aa3  xor     r8d, r8d; bInitialState
0x140005aa6  xor     edx, edx; bManualReset
0x140005aa8  xor     ecx, ecx; lpEventAttributes
0x140005aaa  call    cs:__imp_CreateEventW
0x140005ab0  mov     rdi, rax
0x140005ab3  test    rax, rax
0x140005ab6  jz      short loc_140005AE4
0x140005ab8  call    cs:__imp_GetLastError
0x140005abe  cmp     eax, 0B7h
0x140005ac3  jnz     loc_140005B64
0x140005ac9  mov     rcx, rdi; hObject
0x140005acc  call    cs:__imp_CloseHandle
0x140005ad2  mov     ecx, 64h ; 'd'; dwMilliseconds
0x140005ad7  call    cs:__imp_Sleep
0x140005add  inc     ebx
0x140005adf  cmp     ebx, 5
0x140005ae2  jb      short loc_140005A9C
0x140005ae4  mov     eax, cs:dword_14000E000
0x140005aea  cmp     eax, 2
0x140005aed  jbe     short loc_140005B52
0x140005aef  mov     rcx, cs:qword_14000E018
0x140005af6  mov     edx, 800h
0x140005afb  mov     rax, cs:qword_14000E010
0x140005b02  test    rdx, rax
0x140005b05  jz      short loc_140005B52
0x140005b07  mov     rax, rcx
0x140005b0a  and     rax, rdx
0x140005b0d  cmp     rax, rcx
0x140005b10  jnz     short loc_140005B52
0x140005b12  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\published\\sv"...
0x140005b19  mov     [rbp+arg_8], 8000FFFFh
0x140005b20  mov     [rbp+arg_18], rax
0x140005b24  lea     rdx, word_14000B85E
0x140005b2b  lea     rax, [rbp+arg_8]
0x140005b2f  mov     [rbp+arg_10], 62h ; 'b'
0x140005b36  mov     [rsp+50h+var_20], rax
0x140005b3b  lea     rax, [rbp+arg_10]
0x140005b3f  mov     [rsp+50h+var_28], rax
0x140005b44  lea     rax, [rbp+arg_18]
0x140005b48  mov     [rsp+50h+var_30], rax
0x140005b4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140005b52  mov     eax, 8000FFFFh
0x140005b57  mov     rbx, [rsp+50h+arg_0]
0x140005b5c  add     rsp, 50h
0x140005b60  pop     rdi
0x140005b61  pop     rsi
0x140005b62  pop     rbp
0x140005b63  retn
0x140005b64  xorps   xmm0, xmm0
0x140005b67  lea     rcx, [rbp+var_10]; this
0x140005b6b  movdqu  [rbp+var_10], xmm0
0x140005b70  call    ?Start@GameInputServerManager@@QEAAJXZ; GameInputServerManager::Start(void)
0x140005b75  mov     ebx, eax
0x140005b77  test    eax, eax
0x140005b79  jns     short loc_140005BC5
0x140005b7b  mov     ecx, cs:dword_14000E000
0x140005b81  cmp     ecx, 2
0x140005b84  jbe     loc_140005C41
0x140005b8a  mov     r8, cs:qword_14000E018
0x140005b91  mov     edx, 800h
0x140005b96  mov     rcx, cs:qword_14000E010
0x140005b9d  test    rdx, rcx
0x140005ba0  jz      loc_140005C41
0x140005ba6  mov     rax, r8
0x140005ba9  and     rax, rdx
0x140005bac  cmp     rax, r8
0x140005baf  jnz     loc_140005C41
0x140005bb5  mov     [rbp+arg_10], 65h ; 'e'
0x140005bbc  lea     rdx, byte_14000B821
0x140005bc3  jmp     short loc_140005C13
0x140005bc5  mov     rdx, rsi; unsigned __int16 *
0x140005bc8  call    ?WaitForStopOnEvent@GameInputServerManager@@QEAAJPEBG@Z; GameInputServerManager::WaitForStopOnEvent(ushort const *)
0x140005bcd  mov     ebx, eax
0x140005bcf  test    eax, eax
0x140005bd1  jns     loc_140005C5A
0x140005bd7  mov     ecx, cs:dword_14000E000
0x140005bdd  cmp     ecx, 2
0x140005be0  jbe     short loc_140005C41
0x140005be2  mov     r8, cs:qword_14000E018
0x140005be9  mov     edx, 800h
0x140005bee  mov     rcx, cs:qword_14000E010
0x140005bf5  test    rdx, rcx
0x140005bf8  jz      short loc_140005C41
0x140005bfa  mov     rax, r8
0x140005bfd  and     rax, rdx
0x140005c00  cmp     rax, r8
0x140005c03  jnz     short loc_140005C41
0x140005c05  mov     [rbp+arg_10], 66h ; 'f'
0x140005c0c  lea     rdx, dword_14000B7E4
0x140005c13  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\published\\sv"...
0x140005c1a  mov     [rbp+arg_18], rax
0x140005c1e  lea     rax, [rbp+arg_8]
0x140005c22  mov     [rsp+50h+var_20], rax
0x140005c27  lea     rax, [rbp+arg_10]
0x140005c2b  mov     [rsp+50h+var_28], rax
0x140005c30  lea     rax, [rbp+arg_18]
0x140005c34  mov     [rsp+50h+var_30], rax
0x140005c39  mov     [rbp+arg_8], ebx
0x140005c3c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140005c41  lea     rcx, [rbp+var_10]; this
0x140005c45  call    ??1GameInputServerManager@@QEAA@XZ; GameInputServerManager::~GameInputServerManager(void)
0x140005c4a  mov     rcx, rdi; hObject
0x140005c4d  call    cs:__imp_CloseHandle
0x140005c53  mov     eax, ebx
0x140005c55  jmp     loc_140005B57
0x140005c5a  lea     rcx, [rbp+var_10]; this
0x140005c5e  call    ??1GameInputServerManager@@QEAA@XZ; GameInputServerManager::~GameInputServerManager(void)
0x140005c63  mov     rcx, rdi; hObject
0x140005c66  call    cs:__imp_CloseHandle
0x140005c6c  xor     eax, eax
0x140005c6e  jmp     loc_140005B57
```
