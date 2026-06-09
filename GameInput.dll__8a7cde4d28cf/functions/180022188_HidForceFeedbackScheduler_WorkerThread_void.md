# HidForceFeedbackScheduler::WorkerThread(void)

- ea: `0x180022188`
- end: `0x180022382`
- name: `?WorkerThread@HidForceFeedbackScheduler@@AEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(HidForceFeedbackScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022c20`

## callees

- `0x180001304`
- `0x18000d658`
- `0x180010dc0`
- `0x180022188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022239`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800222e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022239`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800222e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002224e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002232c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002224e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002232c`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x1800222c9`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x1800222c9`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x1800222fa`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x1800222fa`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackScheduler::WorkerThread(HidForceFeedbackScheduler *this, __int64 a2)
{
  char v2; // al
  unsigned __int64 v4; // rax
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  signed int LastError; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int16 *v13; // rdx
  int v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp+30h] BYREF
  const char *v18; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_BYTE *)this + 8);
  v17 = -1;
  if ( v2 )
    return 0;
  while ( 1 )
  {
    v4 = GameInputCurrentTime(this, a2);
    v5 = HidForceFeedbackScheduler::AdvanceThread(this, v4, &v17);
    if ( v5 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
    {
      v8 = qword_180069018 & 8;
      if ( v8 == qword_180069018 )
      {
        v15 = v5;
        v16 = 148;
        v18 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (unsigned __int8 *)&unk_18005C0C0,
          v6,
          v7,
          (__int64 **)&v18,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
    if ( v17 != -1 )
      break;
    if ( WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v12 = qword_180069018;
        if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          v16 = 152;
          v13 = word_18005C37A;
LABEL_13:
          v17 = (unsigned __int64)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
          v15 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v12,
            (unsigned __int8 *)v13,
            v10,
            v11,
            (__int64 **)&v17,
            (__int64)&v16,
            (__int64)&v15);
          goto LABEL_14;
        }
      }
      goto LABEL_14;
    }
LABEL_18:
    if ( *((_BYTE *)this + 8) )
      return 0;
  }
  timeBeginPeriod(1u);
  if ( WaitForSingleObject(*((HANDLE *)this + 2), (unsigned int)v17 / 0x3E8) != -1 )
  {
    timeEndPeriod(1u);
    goto LABEL_18;
  }
  LastError = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
  {
    v12 = qword_180069018 & 8;
    if ( v12 == qword_180069018 )
    {
      v16 = 162;
      v13 = word_18005DB4A;
      goto LABEL_13;
    }
  }
LABEL_14:
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

```

## disassembly

```asm
0x180022188  push    rbp
0x18002218a  push    rbx
0x18002218b  push    rdi
0x18002218c  mov     rbp, rsp
0x18002218f  sub     rsp, 40h
0x180022193  mov     al, [rcx+8]
0x180022196  mov     rbx, rcx
0x180022199  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800221a1  nop
0x1800221a2  test    al, al
0x1800221a4  jnz     loc_180022312
0x1800221aa  lea     rdi, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800221b1  call    GameInputCurrentTime
0x1800221b6  mov     rdx, rax; unsigned __int64
0x1800221b9  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1800221bd  mov     rcx, rbx; this
0x1800221c0  call    ?AdvanceThread@HidForceFeedbackScheduler@@AEAAJ_KPEA_K@Z; HidForceFeedbackScheduler::AdvanceThread(unsigned __int64,unsigned __int64 *)
0x1800221c5  test    eax, eax
0x1800221c7  jns     short loc_180022227
0x1800221c9  mov     ecx, cs:dword_180069000
0x1800221cf  cmp     ecx, 2
0x1800221d2  jbe     short loc_180022227
0x1800221d4  mov     rdx, cs:qword_180069018
0x1800221db  mov     rcx, cs:qword_180069010
0x1800221e2  test    cl, 8
0x1800221e5  jz      short loc_180022227
0x1800221e7  mov     rcx, rdx
0x1800221ea  and     ecx, 8
0x1800221ed  cmp     rcx, rdx
0x1800221f0  jnz     short loc_180022227
0x1800221f2  mov     [rbp+arg_0], eax
0x1800221f5  lea     rdx, unk_18005C0C0
0x1800221fc  lea     rax, [rbp+arg_0]
0x180022200  mov     [rbp+arg_8], 94h
0x180022207  mov     [rsp+40h+var_10], rax
0x18002220c  lea     rax, [rbp+arg_8]
0x180022210  mov     [rsp+40h+var_18], rax
0x180022215  lea     rax, [rbp+arg_18]
0x180022219  mov     [rsp+40h+var_20], rax
0x18002221e  mov     [rbp+arg_18], rdi
0x180022222  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022227  cmp     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x18002222c  jnz     loc_1800222C4
0x180022232  mov     rcx, [rbx+10h]; hHandle
0x180022236  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022239  call    cs:__imp_WaitForSingleObject
0x180022240  nop     dword ptr [rax+rax+00h]
0x180022245  cmp     eax, 0FFFFFFFFh
0x180022248  jnz     loc_180022306
0x18002224e  call    cs:__imp_GetLastError
0x180022255  nop     dword ptr [rax+rax+00h]
0x18002225a  mov     ebx, eax
0x18002225c  mov     eax, cs:dword_180069000
0x180022262  cmp     eax, 2
0x180022265  jbe     short loc_1800222B9
0x180022267  mov     rcx, cs:qword_180069018
0x18002226e  mov     rax, cs:qword_180069010
0x180022275  test    al, 8
0x180022277  jz      short loc_1800222B9
0x180022279  mov     rax, rcx
0x18002227c  and     eax, 8
0x18002227f  cmp     rax, rcx
0x180022282  jnz     short loc_1800222B9
0x180022284  mov     [rbp+arg_8], 98h
0x18002228b  lea     rdx, word_18005C37A
0x180022292  lea     rax, [rbp+arg_0]
0x180022296  mov     [rbp+arg_10], rdi
0x18002229a  mov     [rsp+40h+var_10], rax
0x18002229f  lea     rax, [rbp+arg_8]
0x1800222a3  mov     [rsp+40h+var_18], rax
0x1800222a8  lea     rax, [rbp+arg_10]
0x1800222ac  mov     [rsp+40h+var_20], rax
0x1800222b1  mov     [rbp+arg_0], ebx
0x1800222b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800222b9  test    ebx, ebx
0x1800222bb  jnz     short loc_18002231D
0x1800222bd  mov     ebx, 8000FFFFh
0x1800222c2  jmp     short loc_180022328
0x1800222c4  mov     ecx, 1; uPeriod
0x1800222c9  call    cs:__imp_timeBeginPeriod
0x1800222d0  nop     dword ptr [rax+rax+00h]
0x1800222d5  mov     rcx, [rbx+10h]; hHandle
0x1800222d9  mov     eax, 10624DD3h
0x1800222de  mul     dword ptr [rbp+arg_10]
0x1800222e1  shr     edx, 6; dwMilliseconds
0x1800222e4  call    cs:__imp_WaitForSingleObject
0x1800222eb  nop     dword ptr [rax+rax+00h]
0x1800222f0  cmp     eax, 0FFFFFFFFh
0x1800222f3  jz      short loc_18002232C
0x1800222f5  mov     ecx, 1; uPeriod
0x1800222fa  call    cs:__imp_timeEndPeriod
0x180022301  nop     dword ptr [rax+rax+00h]
0x180022306  mov     al, [rbx+8]
0x180022309  nop
0x18002230a  test    al, al
0x18002230c  jz      loc_1800221B1
0x180022312  xor     eax, eax
0x180022314  add     rsp, 40h
0x180022318  pop     rdi
0x180022319  pop     rbx
0x18002231a  pop     rbp
0x18002231b  retn
0x18002231d  jle     short loc_180022328
0x18002231f  movzx   ebx, bx
0x180022322  or      ebx, 80070000h
0x180022328  mov     eax, ebx
0x18002232a  jmp     short loc_180022314
0x18002232c  call    cs:__imp_GetLastError
0x180022333  nop     dword ptr [rax+rax+00h]
0x180022338  mov     ecx, cs:dword_180069000
0x18002233e  mov     ebx, eax
0x180022340  cmp     ecx, 2
0x180022343  jbe     loc_1800222B9
0x180022349  mov     rax, cs:qword_180069018
0x180022350  mov     rcx, cs:qword_180069010
0x180022357  test    cl, 8
0x18002235a  jz      loc_1800222B9
0x180022360  mov     rcx, rax
0x180022363  and     ecx, 8
0x180022366  cmp     rcx, rax
0x180022369  jnz     loc_1800222B9
0x18002236f  mov     [rbp+arg_8], 0A2h
0x180022376  lea     rdx, word_18005DB4A
0x18002237d  jmp     loc_180022292
```
