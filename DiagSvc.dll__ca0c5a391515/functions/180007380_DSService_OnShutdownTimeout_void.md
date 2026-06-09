# DSService::OnShutdownTimeout(void)

- ea: `0x180007380`
- end: `0x18000742f`
- name: `?OnShutdownTimeout@DSService@@IEAAXXZ`
- size: `175`
- prototype: `void __fastcall(DSService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007e40`

## callees

- `0x180001178`
- `0x180001720`
- `0x180007380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007391`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007391`

## string_xrefs

- `0x1800073af`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x1800073c8`: `DSService::OnShutdownTimeout`

## pseudocode

```c
void __fastcall DSService::OnShutdownTimeout(HANDLE *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v8; // [rsp+50h] [rbp-18h] BYREF
  char *v9; // [rsp+58h] [rbp-10h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF
  const char *v11; // [rsp+90h] [rbp+28h] BYREF
  const char *v12; // [rsp+98h] [rbp+30h] BYREF

  SetEvent(this[9]);
  if ( (unsigned int)dword_180039000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v3, v2, v4) )
    {
      v11 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v10 = 0;
      v12 = "DSService::OnShutdownTimeout";
      v8 = "Shutdown timer time out";
      v9 = (char *)(this + 13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)&byte_18002EEDF,
        v6,
        v7,
        &v9,
        (__int64)&v10,
        &v8,
        &v12,
        &v11);
    }
  }
}

```

## disassembly

```asm
0x180007380  push    rbp
0x180007382  push    rbx
0x180007383  mov     rbp, rsp
0x180007386  sub     rsp, 68h
0x18000738a  mov     rbx, rcx
0x18000738d  mov     rcx, [rcx+48h]; hEvent
0x180007391  call    cs:__imp_SetEvent
0x180007397  mov     eax, cs:dword_180039000
0x18000739d  cmp     eax, 5
0x1800073a0  jbe     loc_180007428
0x1800073a6  call    _tlgKeywordOn
0x1800073ab  test    al, al
0x1800073ad  jz      short loc_180007428
0x1800073af  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800073b6  mov     [rbp+arg_0], 27Dh
0x1800073bd  mov     [rbp+arg_10], rax
0x1800073c1  lea     rdx, byte_18002EEDF
0x1800073c8  lea     rax, aDsserviceOnshu; "DSService::OnShutdownTimeout"
0x1800073cf  mov     [rbp+arg_8], 0
0x1800073d6  mov     [rbp+arg_18], rax
0x1800073da  lea     rax, aShutdownTimerT; "Shutdown timer time out"
0x1800073e1  mov     [rbp+var_18], rax
0x1800073e5  lea     rax, [rbx+68h]
0x1800073e9  mov     [rbp+var_10], rax
0x1800073ed  lea     rax, [rbp+arg_0]
0x1800073f1  mov     [rsp+68h+var_20], rax
0x1800073f6  lea     rax, [rbp+arg_10]
0x1800073fa  mov     [rsp+68h+var_28], rax
0x1800073ff  lea     rax, [rbp+arg_18]
0x180007403  mov     [rsp+68h+var_30], rax
0x180007408  lea     rax, [rbp+var_18]
0x18000740c  mov     [rsp+68h+var_38], rax
0x180007411  lea     rax, [rbp+arg_8]
0x180007415  mov     [rsp+68h+var_40], rax
0x18000741a  lea     rax, [rbp+var_10]
0x18000741e  mov     [rsp+68h+var_48], rax
0x180007423  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007428  add     rsp, 68h
0x18000742c  pop     rbx
0x18000742d  pop     rbp
0x18000742e  retn
```
