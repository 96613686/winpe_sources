# CRDPWDUMXStack::Connect(void)

- ea: `0x18010fc30`
- end: `0x18010fdb8`
- name: `?Connect@CRDPWDUMXStack@@UEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000116c`
- `0x180050dbc`
- `0x180068a9c`
- `0x18010fc30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010fd07`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010fd07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010fd1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010fd1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010fda5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010fda5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010fc45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010fc45`

## string_xrefs

- `0x18010fce4`: `Failed to create the wd stack`
- `0x18010fd61`: `Failed to start the connection thread`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::Connect(CRDPWDUMXStack *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  char *v6; // rdx
  const char *v7; // rax
  int v8; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  const char *v12; // [rsp+50h] [rbp-10h] BYREF
  int v13; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+38h] BYREF
  const char *v15; // [rsp+A0h] [rbp+40h] BYREF
  const char *v16; // [rsp+A8h] [rbp+48h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( (*((_BYTE *)this + 44) & 2) != 0 )
  {
    v8 = CRDPWDUMXStack::WDCreateAndConfigureStack((CRDPWDUMXStack *)((char *)this - 64), *((_DWORD *)this + 95));
    if ( v8 )
    {
      v5 = NTSTATUS2HR(v8);
      if ( (unsigned int)CallbackContext > 2 )
      {
        v13 = 1061;
        v15 = "Connect";
        v6 = (char *)&unk_18028FD90;
        v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v7 = "Failed to create the wd stack";
        goto LABEL_12;
      }
    }
    else
    {
      v5 = 0;
      Thread = CreateThread(0, 0, CRDPWDUMXStack::STATIC_WDShareWorkerThreadProc, (char *)this - 64, 0, 0);
      *((_QWORD *)this + 28) = Thread;
      if ( !Thread )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v13 = 1079;
          v15 = "Connect";
          v6 = (char *)&unk_180288268;
          v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v7 = "Failed to start the connection thread";
          goto LABEL_12;
        }
      }
    }
  }
  else
  {
    v5 = -2147467260;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v13 = 1054;
      v15 = "Connect";
      v6 = byte_18028F655;
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v7 = "STACK NOT INITIALIZED";
LABEL_12:
      v12 = v7;
      v14 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v2,
        (_DWORD)v6,
        v3,
        v4,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v16,
        (__int64)&v13,
        (__int64)&v15);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  return v5;
}

```

## disassembly

```asm
0x18010fc30  push    rbp
0x18010fc32  push    rbx
0x18010fc33  push    rsi
0x18010fc34  push    rdi
0x18010fc35  push    r14
0x18010fc37  mov     rbp, rsp
0x18010fc3a  sub     rsp, 60h
0x18010fc3e  mov     rdi, rcx
0x18010fc41  add     rcx, 68h ; 'h'; lpCriticalSection
0x18010fc45  call    cs:__imp_EnterCriticalSection
0x18010fc4b  test    byte ptr [rdi+2Ch], 2
0x18010fc4f  jnz     short loc_18010FC95
0x18010fc51  mov     eax, cs:CallbackContext
0x18010fc57  mov     ebx, 80004004h
0x18010fc5c  cmp     eax, 2
0x18010fc5f  jbe     loc_18010FDA1
0x18010fc65  lea     rax, aConnect; "Connect"
0x18010fc6c  mov     [rbp+arg_0], 41Eh
0x18010fc73  mov     [rbp+arg_10], rax
0x18010fc77  lea     rdx, byte_18028F655
0x18010fc7e  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fc85  mov     [rbp+arg_18], rax
0x18010fc89  lea     rax, aStackNotInitia; "STACK NOT INITIALIZED"
0x18010fc90  jmp     loc_18010FD68
0x18010fc95  mov     edx, [rdi+17Ch]; unsigned int
0x18010fc9b  lea     rcx, [rdi-40h]; this
0x18010fc9f  call    ?WDCreateAndConfigureStack@CRDPWDUMXStack@@IEAAJK@Z; CRDPWDUMXStack::WDCreateAndConfigureStack(ulong)
0x18010fca4  test    eax, eax
0x18010fca6  jz      short loc_18010FCED
0x18010fca8  mov     ecx, eax; int
0x18010fcaa  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x18010fcaf  mov     ebx, eax
0x18010fcb1  mov     eax, cs:CallbackContext
0x18010fcb7  cmp     eax, 2
0x18010fcba  jbe     loc_18010FDA1
0x18010fcc0  lea     rax, aConnect; "Connect"
0x18010fcc7  mov     [rbp+arg_0], 425h
0x18010fcce  mov     [rbp+arg_10], rax
0x18010fcd2  lea     rdx, unk_18028FD90
0x18010fcd9  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fce0  mov     [rbp+arg_18], rax
0x18010fce4  lea     rax, aFailedToCreate_31; "Failed to create the wd stack"
0x18010fceb  jmp     short loc_18010FD68
0x18010fced  xor     ebx, ebx
0x18010fcef  lea     r9, [rdi-40h]; lpParameter
0x18010fcf3  mov     [rsp+60h+lpThreadId], rbx; lpThreadId
0x18010fcf8  lea     r8, ?STATIC_WDShareWorkerThreadProc@CRDPWDUMXStack@@KAKPEAX@Z; lpStartAddress
0x18010fcff  xor     edx, edx; dwStackSize
0x18010fd01  mov     [rsp+60h+dwCreationFlags], ebx; dwCreationFlags
0x18010fd05  xor     ecx, ecx; lpThreadAttributes
0x18010fd07  call    cs:__imp_CreateThread
0x18010fd0d  mov     [rdi+0E0h], rax
0x18010fd14  test    rax, rax
0x18010fd17  jnz     loc_18010FDA1
0x18010fd1d  call    cs:__imp_GetLastError
0x18010fd23  mov     ebx, eax
0x18010fd25  test    eax, eax
0x18010fd27  jle     short loc_18010FD32
0x18010fd29  movzx   ebx, ax
0x18010fd2c  or      ebx, 80070000h
0x18010fd32  mov     eax, cs:CallbackContext
0x18010fd38  cmp     eax, 2
0x18010fd3b  jbe     short loc_18010FDA1
0x18010fd3d  lea     rax, aConnect; "Connect"
0x18010fd44  mov     [rbp+arg_0], 437h
0x18010fd4b  mov     [rbp+arg_10], rax
0x18010fd4f  lea     rdx, unk_180288268
0x18010fd56  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fd5d  mov     [rbp+arg_18], rax
0x18010fd61  lea     rax, aFailedToStartT; "Failed to start the connection thread"
0x18010fd68  mov     [rbp+var_10], rax
0x18010fd6c  lea     rax, [rbp+arg_10]
0x18010fd70  mov     [rsp+60h+var_20], rax
0x18010fd75  lea     rax, [rbp+arg_0]
0x18010fd79  mov     [rsp+60h+var_28], rax
0x18010fd7e  lea     rax, [rbp+arg_18]
0x18010fd82  mov     [rsp+60h+var_30], rax
0x18010fd87  lea     rax, [rbp+arg_8]
0x18010fd8b  mov     [rsp+60h+lpThreadId], rax
0x18010fd90  lea     rax, [rbp+var_10]
0x18010fd94  mov     qword ptr [rsp+60h+dwCreationFlags], rax
0x18010fd99  mov     [rbp+arg_8], ebx
0x18010fd9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010fda1  lea     rcx, [rdi+68h]; lpCriticalSection
0x18010fda5  call    cs:__imp_LeaveCriticalSection
0x18010fdab  mov     eax, ebx
0x18010fdad  add     rsp, 60h
0x18010fdb1  pop     r14
0x18010fdb3  pop     rdi
0x18010fdb4  pop     rsi
0x18010fdb5  pop     rbx
0x18010fdb6  pop     rbp
0x18010fdb7  retn
```
