# XusbWatcher::Stop(void)

- ea: `0x180041d1c`
- end: `0x180041ef1`
- name: `?Stop@XusbWatcher@@QEAAXXZ`
- size: `469`
- prototype: `void __fastcall(XusbWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ddd4`
- `0x180041ef8`

## callees

- `0x180001304`
- `0x180041d1c`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180041dd2`
- `ntdll!NtWaitForSingleObject` at `0x180041dd2`
- `ntdll!NtAlertThread` at `0x180041d42`
- `ntdll!NtAlertThread` at `0x180041d42`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180041de6`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180041de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041e65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e75`

## pseudocode

```c
void __fastcall XusbWatcher::Stop(XusbWatcher *this)
{
  NTSTATUS v2; // r8d
  int v3; // r9d
  void *v4; // rcx
  DWORD LastError; // eax
  int v6; // r8d
  int v7; // r9d
  DWORD v8; // eax
  int v9; // r8d
  int v10; // r9d
  DWORD v11; // [rsp+70h] [rbp+28h] BYREF
  int v12; // [rsp+78h] [rbp+30h] BYREF
  const char *v13; // [rsp+80h] [rbp+38h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+88h] [rbp+40h] BYREF

  if ( *((_QWORD *)this + 4) )
  {
    *((_BYTE *)this + 40) = 1;
    _mm_mfence();
    v2 = NtAlertThread(*((HANDLE *)this + 4));
    if ( v2 < 0
      && (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v11 = v2;
      v12 = 121;
      v13 = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_180062161,
        v2,
        v3,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11);
    }
    v4 = (void *)*((_QWORD *)this + 4);
    Timeout.QuadPart = -10000000;
    if ( NtWaitForSingleObject(v4, 0, &Timeout) )
    {
      if ( SuspendThread(*((HANDLE *)this + 4)) == -1 )
      {
        LastError = GetLastError();
        if ( (unsigned int)dword_180069000 > 2
          && (qword_180069010 & 0x400) != 0
          && (qword_180069018 & 0x400) == qword_180069018 )
        {
          v11 = LastError;
          v12 = 134;
          v13 = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018 & 0x400,
            (unsigned int)byte_18005EFA9,
            v6,
            v7,
            (__int64)&v13,
            (__int64)&v12,
            (__int64)&v11);
        }
      }
    }
    if ( !CloseHandle(*((HANDLE *)this + 4)) )
    {
      v8 = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v11 = v8;
        v12 = 137;
        v13 = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018 & 0x400,
          (unsigned int)byte_18005FD15,
          v9,
          v10,
          (__int64)&v13,
          (__int64)&v12,
          (__int64)&v11);
      }
    }
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180041d1c  push    rbp
0x180041d1e  push    rbx
0x180041d1f  push    rsi
0x180041d20  push    rdi
0x180041d21  mov     rbp, rsp
0x180041d24  sub     rsp, 48h
0x180041d28  cmp     qword ptr [rcx+20h], 0
0x180041d2d  mov     rbx, rcx
0x180041d30  jz      loc_180041EE7
0x180041d36  nop
0x180041d37  mov     byte ptr [rcx+28h], 1
0x180041d3b  mfence
0x180041d3e  mov     rcx, [rcx+20h]; ThreadHandle
0x180041d42  call    cs:__imp_NtAlertThread
0x180041d49  nop     dword ptr [rax+rax+00h]
0x180041d4e  mov     edi, 400h
0x180041d53  lea     rsi, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x180041d5a  mov     r8d, eax
0x180041d5d  test    eax, eax
0x180041d5f  jns     short loc_180041DC0
0x180041d61  mov     ecx, cs:dword_180069000
0x180041d67  cmp     ecx, 2
0x180041d6a  jbe     short loc_180041DC0
0x180041d6c  mov     rdx, cs:qword_180069018
0x180041d73  mov     rcx, cs:qword_180069010
0x180041d7a  test    rdi, rcx
0x180041d7d  jz      short loc_180041DC0
0x180041d7f  mov     rax, rdx
0x180041d82  and     rax, rdi
0x180041d85  cmp     rax, rdx
0x180041d88  jnz     short loc_180041DC0
0x180041d8a  lea     rax, [rbp+arg_0]
0x180041d8e  mov     [rbp+arg_0], r8d
0x180041d92  mov     [rsp+48h+var_18], rax
0x180041d97  lea     rdx, byte_180062161
0x180041d9e  lea     rax, [rbp+arg_8]
0x180041da2  mov     [rbp+arg_8], 79h ; 'y'
0x180041da9  mov     [rsp+48h+var_20], rax
0x180041dae  lea     rax, [rbp+arg_10]
0x180041db2  mov     [rsp+48h+var_28], rax
0x180041db7  mov     [rbp+arg_10], rsi
0x180041dbb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041dc0  mov     rcx, [rbx+20h]; Handle
0x180041dc4  lea     r8, [rbp+Timeout]; Timeout
0x180041dc8  xor     edx, edx; Alertable
0x180041dca  mov     qword ptr [rbp+Timeout], 0FFFFFFFFFF676980h
0x180041dd2  call    cs:__imp_NtWaitForSingleObject
0x180041dd9  nop     dword ptr [rax+rax+00h]
0x180041dde  test    eax, eax
0x180041de0  jz      short loc_180041E61
0x180041de2  mov     rcx, [rbx+20h]; hThread
0x180041de6  call    cs:__imp_SuspendThread
0x180041ded  nop     dword ptr [rax+rax+00h]
0x180041df2  cmp     eax, 0FFFFFFFFh
0x180041df5  jnz     short loc_180041E61
0x180041df7  call    cs:__imp_GetLastError
0x180041dfe  nop     dword ptr [rax+rax+00h]
0x180041e03  mov     ecx, cs:dword_180069000
0x180041e09  cmp     ecx, 2
0x180041e0c  jbe     short loc_180041E61
0x180041e0e  mov     rdx, cs:qword_180069018
0x180041e15  mov     rcx, cs:qword_180069010
0x180041e1c  test    rdi, rcx
0x180041e1f  jz      short loc_180041E61
0x180041e21  mov     rcx, rdx
0x180041e24  and     rcx, rdi
0x180041e27  cmp     rcx, rdx
0x180041e2a  jnz     short loc_180041E61
0x180041e2c  mov     [rbp+arg_0], eax
0x180041e2f  lea     rdx, byte_18005EFA9
0x180041e36  lea     rax, [rbp+arg_0]
0x180041e3a  mov     [rbp+arg_8], 86h
0x180041e41  mov     [rsp+48h+var_18], rax
0x180041e46  lea     rax, [rbp+arg_8]
0x180041e4a  mov     [rsp+48h+var_20], rax
0x180041e4f  lea     rax, [rbp+arg_10]
0x180041e53  mov     [rsp+48h+var_28], rax
0x180041e58  mov     [rbp+arg_10], rsi
0x180041e5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041e61  mov     rcx, [rbx+20h]; hObject
0x180041e65  call    cs:__imp_CloseHandle
0x180041e6c  nop     dword ptr [rax+rax+00h]
0x180041e71  test    eax, eax
0x180041e73  jnz     short loc_180041EDF
0x180041e75  call    cs:__imp_GetLastError
0x180041e7c  nop     dword ptr [rax+rax+00h]
0x180041e81  mov     ecx, cs:dword_180069000
0x180041e87  cmp     ecx, 2
0x180041e8a  jbe     short loc_180041EDF
0x180041e8c  mov     rdx, cs:qword_180069018
0x180041e93  mov     rcx, cs:qword_180069010
0x180041e9a  test    rdi, rcx
0x180041e9d  jz      short loc_180041EDF
0x180041e9f  mov     rcx, rdx
0x180041ea2  and     rcx, rdi
0x180041ea5  cmp     rcx, rdx
0x180041ea8  jnz     short loc_180041EDF
0x180041eaa  mov     [rbp+arg_0], eax
0x180041ead  lea     rdx, byte_18005FD15
0x180041eb4  lea     rax, [rbp+arg_0]
0x180041eb8  mov     [rbp+arg_8], 89h
0x180041ebf  mov     [rsp+48h+var_18], rax
0x180041ec4  lea     rax, [rbp+arg_8]
0x180041ec8  mov     [rsp+48h+var_20], rax
0x180041ecd  lea     rax, [rbp+arg_10]
0x180041ed1  mov     [rsp+48h+var_28], rax
0x180041ed6  mov     [rbp+arg_10], rsi
0x180041eda  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041edf  mov     qword ptr [rbx+20h], 0
0x180041ee7  add     rsp, 48h
0x180041eeb  pop     rdi
0x180041eec  pop     rsi
0x180041eed  pop     rbx
0x180041eee  pop     rbp
0x180041eef  retn
```
