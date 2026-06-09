# SpeechOneSettingsTelemetry::LifeTime::StopEventLocal(long,unsigned __int64)

- ea: `0x140019b20`
- end: `0x140019bb2`
- name: `?StopEventLocal@LifeTime@SpeechOneSettingsTelemetry@@UEAAXJ_K@Z`
- size: `146`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *this, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001360`
- `0x1400189d4`
- `0x140019b20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019b5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019b5b`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::StopEventLocal(
        SpeechOneSettingsTelemetry::LifeTime *this,
        int a2,
        __int64 a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r9
  int v11; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v13; // [rsp+98h] [rbp+20h] BYREF

  v6 = SpeechOneSettingsLogging::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    v8 = *((_QWORD *)v6 + 3);
    if ( (*(_QWORD *)(v7 + 16) & 1) != 0 && (v8 & 1) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = a2;
      v12[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&dword_14002A4CC,
        (__int64)this + 32,
        v10,
        (__int64)v12,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
}

```

## disassembly

```asm
0x140019b20  push    rbx
0x140019b22  push    rbp
0x140019b23  push    rsi
0x140019b24  push    rdi
0x140019b25  sub     rsp, 58h
0x140019b29  mov     rsi, r8
0x140019b2c  mov     ebp, edx
0x140019b2e  mov     rdi, rcx
0x140019b31  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140019b36  mov     rbx, rax
0x140019b39  mov     r9d, [rax]
0x140019b3c  cmp     r9d, 4
0x140019b40  jbe     short loc_140019BA9
0x140019b42  mov     rax, [rax+18h]
0x140019b46  mov     r9, [rbx+10h]
0x140019b4a  test    r9b, 1
0x140019b4e  jz      short loc_140019BA9
0x140019b50  mov     rcx, rax
0x140019b53  and     ecx, 1
0x140019b56  cmp     rcx, rax
0x140019b59  jnz     short loc_140019BA9
0x140019b5b  call    cs:__imp_GetCurrentThreadId
0x140019b61  mov     r9, [rdi+30h]
0x140019b65  lea     r8, [rdi+20h]
0x140019b69  mov     [rsp+78h+arg_18], eax
0x140019b70  lea     rdx, dword_14002A4CC
0x140019b77  lea     rax, [rsp+78h+arg_18]
0x140019b7f  mov     [rsp+78h+var_38], ebp
0x140019b83  mov     [rsp+78h+var_48], rax
0x140019b88  mov     rcx, rbx
0x140019b8b  lea     rax, [rsp+78h+var_38]
0x140019b90  mov     [rsp+78h+var_30], rsi
0x140019b95  mov     [rsp+78h+var_50], rax
0x140019b9a  lea     rax, [rsp+78h+var_30]
0x140019b9f  mov     [rsp+78h+var_58], rax
0x140019ba4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140019ba9  add     rsp, 58h
0x140019bad  pop     rdi
0x140019bae  pop     rsi
0x140019baf  pop     rbp
0x140019bb0  pop     rbx
0x140019bb1  retn
```
