# HidForceFeedbackScheduler::StartWorker(void)

- ea: `0x18001e250`
- end: `0x18001e402`
- name: `?StartWorker@HidForceFeedbackScheduler@@QEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(HidForceFeedbackScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f244`

## callees

- `0x180001304`
- `0x18001e250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e27b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e27b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e367`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e29b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e29b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3a1`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackScheduler::StartWorker(HidForceFeedbackScheduler *this)
{
  HANDLE EventW; // rdi
  HANDLE v3; // rax
  signed int LastError; // ebx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rcx
  char *v8; // rdx
  HANDLE Thread; // rdi
  HANDLE v11; // rax
  signed int v12; // [rsp+60h] [rbp+20h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  const char *v14; // [rsp+70h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 3) )
    return 0;
  *((_BYTE *)this + 8) = 0;
  _mm_mfence();
  EventW = CreateEventW(0, 0, 0, 0);
  v3 = (HANDLE)*((_QWORD *)this + 2);
  if ( EventW == v3 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 2);
  }
  else
  {
    if ( v3 )
      CloseHandle(*((HANDLE *)this + 2));
    *((_QWORD *)this + 2) = EventW;
  }
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2 )
    {
      LODWORD(v7) = qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v13 = 21;
        v8 = byte_18005C849;
LABEL_12:
        v14 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackScheduler.cpp";
        v12 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (_DWORD)v8,
          v5,
          v6,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v12);
        goto LABEL_13;
      }
    }
    goto LABEL_13;
  }
  Thread = CreateThread(0, 0, HidForceFeedbackScheduler::WorkerThreadThunk, this, 0, 0);
  v11 = (HANDLE)*((_QWORD *)this + 3);
  if ( Thread == v11 )
  {
    Thread = (HANDLE)*((_QWORD *)this + 3);
  }
  else
  {
    if ( v11 )
      CloseHandle(*((HANDLE *)this + 3));
    *((_QWORD *)this + 3) = Thread;
  }
  if ( Thread )
    return 0;
  LastError = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
  {
    v7 = qword_180069018 & 8;
    if ( v7 == qword_180069018 )
    {
      v13 = 24;
      v8 = byte_18005CC0B;
      goto LABEL_12;
    }
  }
LABEL_13:
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
0x18001e250  push    rbp
0x18001e252  push    rbx
0x18001e253  push    rdi
0x18001e254  mov     rbp, rsp
0x18001e257  sub     rsp, 40h
0x18001e25b  cmp     qword ptr [rcx+18h], 0
0x18001e260  mov     rbx, rcx
0x18001e263  jnz     loc_18001E3F7
0x18001e269  nop
0x18001e26a  mov     byte ptr [rcx+8], 0
0x18001e26e  mfence
0x18001e271  xor     r9d, r9d; lpName
0x18001e274  xor     r8d, r8d; bInitialState
0x18001e277  xor     edx, edx; bManualReset
0x18001e279  xor     ecx, ecx; lpEventAttributes
0x18001e27b  call    cs:__imp_CreateEventW
0x18001e282  nop     dword ptr [rax+rax+00h]
0x18001e287  mov     rdi, rax
0x18001e28a  mov     rax, [rbx+10h]
0x18001e28e  cmp     rdi, rax
0x18001e291  jz      short loc_18001E2AD
0x18001e293  test    rax, rax
0x18001e296  jz      short loc_18001E2A7
0x18001e298  mov     rcx, rax; hObject
0x18001e29b  call    cs:__imp_CloseHandle
0x18001e2a2  nop     dword ptr [rax+rax+00h]
0x18001e2a7  mov     [rbx+10h], rdi
0x18001e2ab  jmp     short loc_18001E2B0
0x18001e2ad  mov     rdi, rax
0x18001e2b0  test    rdi, rdi
0x18001e2b3  jnz     loc_18001E348
0x18001e2b9  call    cs:__imp_GetLastError
0x18001e2c0  nop     dword ptr [rax+rax+00h]
0x18001e2c5  mov     ebx, eax
0x18001e2c7  mov     eax, cs:dword_180069000
0x18001e2cd  cmp     eax, 2
0x18001e2d0  jbe     short loc_18001E32B
0x18001e2d2  mov     rcx, cs:qword_180069018
0x18001e2d9  mov     rax, cs:qword_180069010
0x18001e2e0  test    al, 8
0x18001e2e2  jz      short loc_18001E32B
0x18001e2e4  mov     rax, rcx
0x18001e2e7  and     eax, 8
0x18001e2ea  cmp     rax, rcx
0x18001e2ed  jnz     short loc_18001E32B
0x18001e2ef  mov     [rbp+arg_8], 15h
0x18001e2f6  lea     rdx, byte_18005C849
0x18001e2fd  lea     rax, aOnecoreXboxGam_18; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001e304  mov     [rbp+arg_10], rax
0x18001e308  lea     rax, [rbp+arg_0]
0x18001e30c  mov     [rsp+40h+var_10], rax
0x18001e311  lea     rax, [rbp+arg_8]
0x18001e315  mov     [rsp+40h+lpThreadId], rax
0x18001e31a  lea     rax, [rbp+arg_10]
0x18001e31e  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x18001e323  mov     [rbp+arg_0], ebx
0x18001e326  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e32b  test    ebx, ebx
0x18001e32d  jnz     short loc_18001E336
0x18001e32f  mov     ebx, 8000FFFFh
0x18001e334  jmp     short loc_18001E341
0x18001e336  jle     short loc_18001E341
0x18001e338  movzx   ebx, bx
0x18001e33b  or      ebx, 80070000h
0x18001e341  mov     eax, ebx
0x18001e343  jmp     loc_18001E3F9
0x18001e348  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x18001e351  lea     r8, ?WorkerThreadThunk@HidForceFeedbackScheduler@@CAKPEAX@Z; lpStartAddress
0x18001e358  mov     r9, rbx; lpParameter
0x18001e35b  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x18001e363  xor     edx, edx; dwStackSize
0x18001e365  xor     ecx, ecx; lpThreadAttributes
0x18001e367  call    cs:__imp_CreateThread
0x18001e36e  nop     dword ptr [rax+rax+00h]
0x18001e373  mov     rdi, rax
0x18001e376  mov     rax, [rbx+18h]
0x18001e37a  cmp     rdi, rax
0x18001e37d  jz      short loc_18001E399
0x18001e37f  test    rax, rax
0x18001e382  jz      short loc_18001E393
0x18001e384  mov     rcx, rax; hObject
0x18001e387  call    cs:__imp_CloseHandle
0x18001e38e  nop     dword ptr [rax+rax+00h]
0x18001e393  mov     [rbx+18h], rdi
0x18001e397  jmp     short loc_18001E39C
0x18001e399  mov     rdi, rax
0x18001e39c  test    rdi, rdi
0x18001e39f  jnz     short loc_18001E3F7
0x18001e3a1  call    cs:__imp_GetLastError
0x18001e3a8  nop     dword ptr [rax+rax+00h]
0x18001e3ad  mov     ecx, cs:dword_180069000
0x18001e3b3  mov     ebx, eax
0x18001e3b5  cmp     ecx, 2
0x18001e3b8  jbe     loc_18001E32B
0x18001e3be  mov     rax, cs:qword_180069018
0x18001e3c5  mov     rcx, cs:qword_180069010
0x18001e3cc  test    cl, 8
0x18001e3cf  jz      loc_18001E32B
0x18001e3d5  mov     rcx, rax
0x18001e3d8  and     ecx, 8
0x18001e3db  cmp     rcx, rax
0x18001e3de  jnz     loc_18001E32B
0x18001e3e4  mov     [rbp+arg_8], 18h
0x18001e3eb  lea     rdx, byte_18005CC0B
0x18001e3f2  jmp     loc_18001E2FD
0x18001e3f7  xor     eax, eax
0x18001e3f9  add     rsp, 40h
0x18001e3fd  pop     rdi
0x18001e3fe  pop     rbx
0x18001e3ff  pop     rbp
0x18001e400  retn
```
