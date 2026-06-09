# CmDebuggerApi::RunProcessInContainer(void *,ushort const *,ushort const *,int,ulong,void * *,void * *,ulong *)

- ea: `0x18000a430`
- end: `0x18000a653`
- name: `?RunProcessInContainer@CmDebuggerApi@@UEAAJPEAXPEBG1HKPEAPEAX2PEAK@Z`
- size: `547`
- prototype: `__int64 __fastcall(CmDebuggerApi *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, int, DWORD dwMilliseconds, void **, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800048a0`
- `0x180004ef8`
- `0x1800066e4`
- `0x18000700c`
- `0x180007044`
- `0x180007350`
- `0x1800079d0`
- `0x18000a430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a540`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a540`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a484`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a58e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a58e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ec`

## string_xrefs

- `0x18000a5ff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a615`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a62b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a641`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a4cf`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`
- `0x18000a50c`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`
- `0x18000a572`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`
- `0x18000a5a2`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`
- `0x18000a5cc`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`

## pseudocode

```c
__int64 __fastcall CmDebuggerApi::RunProcessInContainer(
        CmDebuggerApi *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        DWORD dwMilliseconds,
        void **a7,
        void **a8,
        unsigned int *a9)
{
  int v9; // eax
  int v10; // r14d
  unsigned int *v11; // rsi
  wil::details *v12; // rcx
  HANDLE Event; // rbx
  int ProcessInContainer; // eax
  unsigned int v15; // edi
  const char *v16; // r9
  int LastErrorFailHr; // eax
  DWORD v19; // eax
  const char *v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  const char *v23; // r9
  int v24; // eax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-40h]
  int v27; // [rsp+20h] [rbp-40h]
  int v28; // [rsp+20h] [rbp-40h]
  _QWORD v29[3]; // [rsp+40h] [rbp-20h] BYREF
  int v30; // [rsp+58h] [rbp-8h]
  int v31; // [rsp+5Ch] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 v33; // [rsp+90h] [rbp+30h] BYREF

  v9 = a5;
  v10 = (int)a2;
  v11 = a9;
  v29[0] = a3;
  v29[2] = a4;
  v33 = 0;
  *a9 = -2147467259;
  v29[1] = 0;
  v31 = 0;
  v30 = v9;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    Event = 0;
    v15 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v26);
      return v15;
    }
  }
  ProcessInContainer = CmsCreateProcessInContainer(
                         v10,
                         (unsigned int)v29,
                         (_DWORD)Event,
                         0,
                         (__int64)a7,
                         (__int64)a8,
                         (__int64)&v33);
  v15 = ProcessInContainer;
  if ( ProcessInContainer >= 0 )
  {
    v19 = WaitForSingleObjectEx(Event, dwMilliseconds, 0);
    if ( v19 == 258 )
    {
      v15 = -2147024638;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)0x80070102LL,
        v27);
      v24 = CmsCloseProcess(&v33);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
          (const char *)(unsigned int)v24,
          v28);
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v25);
    }
    else
    {
      if ( v19 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
      v21 = v33;
      *v11 = *(_DWORD *)(v33 + 28);
      v15 = *(_DWORD *)(v21 + 24);
      v22 = CmsCloseProcess(&v33);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
          (const char *)(unsigned int)v22,
          v27);
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v23);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x149,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)(unsigned int)ProcessInContainer,
      v27);
    if ( Event && !CloseHandle(Event) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
  }
  return v15;
}

```

## disassembly

```asm
0x18000a430  mov     [rsp-18h+arg_0], rbx
0x18000a435  mov     [rsp-18h+arg_8], rsi
0x18000a43a  push    rbp
0x18000a43b  push    rdi
0x18000a43c  push    r14
0x18000a43e  mov     rbp, rsp
0x18000a441  sub     rsp, 60h
0x18000a445  mov     eax, [rbp+arg_20]
0x18000a448  mov     r14, rdx
0x18000a44b  mov     rsi, [rbp+arg_40]
0x18000a44f  xor     edx, edx; lpName
0x18000a451  mov     [rbp+var_20], r8
0x18000a455  xor     ecx, ecx; lpEventAttributes
0x18000a457  mov     [rbp+var_10], r9
0x18000a45b  xor     r8d, r8d; dwFlags
0x18000a45e  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a464  mov     [rbp+arg_10], 0
0x18000a46c  mov     dword ptr [rsi], 80004005h
0x18000a472  mov     [rbp+var_18], 0
0x18000a47a  mov     [rbp+var_4], 0
0x18000a481  mov     [rbp+var_8], eax
0x18000a484  call    cs:__imp_CreateEventExW
0x18000a48a  mov     rbx, rax
0x18000a48d  test    rax, rax
0x18000a490  jz      short loc_18000A4FB
0x18000a492  call    cs:__imp_GetLastError
0x18000a498  lea     rax, [rbp+arg_10]
0x18000a49c  xor     r9d, r9d
0x18000a49f  mov     [rsp+60h+var_30], rax
0x18000a4a4  lea     rdx, [rbp+var_20]
0x18000a4a8  mov     rax, [rbp+arg_38]
0x18000a4ac  mov     r8, rbx
0x18000a4af  mov     [rsp+60h+var_38], rax
0x18000a4b4  mov     rcx, r14
0x18000a4b7  mov     rax, [rbp+arg_30]
0x18000a4bb  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000a4c0  call    CmsCreateProcessInContainer
0x18000a4c5  mov     edi, eax
0x18000a4c7  test    eax, eax
0x18000a4c9  jns     short loc_18000A537
0x18000a4cb  mov     rcx, [rbp+18h]; this
0x18000a4cf  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a4d6  mov     r9d, eax; char *
0x18000a4d9  mov     edx, 149h; void *
0x18000a4de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4e3  test    rbx, rbx
0x18000a4e6  jz      short loc_18000A520
0x18000a4e8  mov     rcx, rbx; hObject
0x18000a4eb  call    cs:__imp_CloseHandle
0x18000a4f1  test    eax, eax
0x18000a4f3  jz      loc_18000A611
0x18000a4f9  jmp     short loc_18000A520
0x18000a4fb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a500  xor     ebx, ebx
0x18000a502  mov     edi, eax
0x18000a504  test    eax, eax
0x18000a506  jns     short loc_18000A498
0x18000a508  mov     rcx, [rbp+18h]; this
0x18000a50c  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a513  mov     r9d, eax; char *
0x18000a516  mov     edx, 141h; void *
0x18000a51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a520  lea     r11, [rsp+60h+var_s0]
0x18000a525  mov     eax, edi
0x18000a527  mov     rbx, [r11+20h]
0x18000a52b  mov     rsi, [r11+28h]
0x18000a52f  mov     rsp, r11
0x18000a532  pop     r14
0x18000a534  pop     rdi
0x18000a535  pop     rbp
0x18000a536  retn
0x18000a537  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x18000a53a  xor     r8d, r8d; bAlertable
0x18000a53d  mov     rcx, rbx; hHandle
0x18000a540  call    cs:__imp_WaitForSingleObjectEx
0x18000a546  cmp     eax, 102h
0x18000a54b  jz      short loc_18000A59E
0x18000a54d  test    eax, eax
0x18000a54f  jnz     loc_18000A5FB
0x18000a555  mov     rcx, [rbp+arg_10]
0x18000a559  mov     eax, [rcx+1Ch]
0x18000a55c  mov     [rsi], eax
0x18000a55e  mov     edi, [rcx+18h]
0x18000a561  lea     rcx, [rbp+arg_10]
0x18000a565  call    CmsCloseProcess
0x18000a56a  test    eax, eax
0x18000a56c  jns     short loc_18000A586
0x18000a56e  mov     rcx, [rbp+18h]; this
0x18000a572  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a579  mov     r9d, eax; char *
0x18000a57c  mov     edx, 14Dh; void *
0x18000a581  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a586  test    rbx, rbx
0x18000a589  jz      short loc_18000A520
0x18000a58b  mov     rcx, rbx; hObject
0x18000a58e  call    cs:__imp_CloseHandle
0x18000a594  test    eax, eax
0x18000a596  jz      loc_18000A627
0x18000a59c  jmp     short loc_18000A520
0x18000a59e  mov     rcx, [rbp+18h]; this
0x18000a5a2  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a5a9  mov     edi, 80070102h
0x18000a5ae  mov     edx, 152h; void *
0x18000a5b3  mov     r9d, edi; char *
0x18000a5b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5bb  lea     rcx, [rbp+arg_10]
0x18000a5bf  call    CmsCloseProcess
0x18000a5c4  test    eax, eax
0x18000a5c6  jns     short loc_18000A5E0
0x18000a5c8  mov     rcx, [rbp+18h]; this
0x18000a5cc  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a5d3  mov     r9d, eax; char *
0x18000a5d6  mov     edx, 14Dh; void *
0x18000a5db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a5e0  test    rbx, rbx
0x18000a5e3  jz      loc_18000A520
0x18000a5e9  mov     rcx, rbx; hObject
0x18000a5ec  call    cs:__imp_CloseHandle
0x18000a5f2  test    eax, eax
0x18000a5f4  jz      short loc_18000A63D
0x18000a5f6  jmp     loc_18000A520
0x18000a5fb  mov     rcx, [rbp+18h]; this
0x18000a5ff  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a606  mov     edx, 0B0Fh; void *
0x18000a60b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a611  mov     rcx, [rbp+18h]; this
0x18000a615  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a61c  mov     edx, 0A0Bh; void *
0x18000a621  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a627  mov     rcx, [rbp+18h]; this
0x18000a62b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a632  mov     edx, 0A0Bh; void *
0x18000a637  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a63d  mov     rcx, [rbp+18h]; this
0x18000a641  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a648  mov     edx, 0A0Bh; void *
0x18000a64d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
