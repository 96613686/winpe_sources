# SpeechOneSettingsTelemetry::LifeTime::StopEvent(long,unsigned __int64)

- ea: `0x140019a70`
- end: `0x140019b0b`
- name: `?StopEvent@LifeTime@SpeechOneSettingsTelemetry@@UEAAXJ_K@Z`
- size: `155`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *this, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001360`
- `0x1400189d4`
- `0x140019a70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019ab4`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::StopEvent(
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
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = a2;
      v12[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)qword_14002A5F8,
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
0x140019a70  push    rbx
0x140019a72  push    rbp
0x140019a73  push    rsi
0x140019a74  push    rdi
0x140019a75  sub     rsp, 58h
0x140019a79  mov     rsi, r8
0x140019a7c  mov     ebp, edx
0x140019a7e  mov     rdi, rcx
0x140019a81  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140019a86  mov     rbx, rax
0x140019a89  mov     r9d, [rax]
0x140019a8c  cmp     r9d, 4
0x140019a90  jbe     short loc_140019B02
0x140019a92  mov     rax, [rax+18h]
0x140019a96  mov     rdx, 400000000000h
0x140019aa0  mov     r9, [rbx+10h]
0x140019aa4  test    rdx, r9
0x140019aa7  jz      short loc_140019B02
0x140019aa9  mov     rcx, rax
0x140019aac  and     rcx, rdx
0x140019aaf  cmp     rcx, rax
0x140019ab2  jnz     short loc_140019B02
0x140019ab4  call    cs:__imp_GetCurrentThreadId
0x140019aba  mov     r9, [rdi+30h]
0x140019abe  lea     r8, [rdi+20h]
0x140019ac2  mov     [rsp+78h+arg_18], eax
0x140019ac9  lea     rdx, qword_14002A5F8
0x140019ad0  lea     rax, [rsp+78h+arg_18]
0x140019ad8  mov     [rsp+78h+var_38], ebp
0x140019adc  mov     [rsp+78h+var_48], rax
0x140019ae1  mov     rcx, rbx
0x140019ae4  lea     rax, [rsp+78h+var_38]
0x140019ae9  mov     [rsp+78h+var_30], rsi
0x140019aee  mov     [rsp+78h+var_50], rax
0x140019af3  lea     rax, [rsp+78h+var_30]
0x140019af8  mov     [rsp+78h+var_58], rax
0x140019afd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140019b02  add     rsp, 58h
0x140019b06  pop     rdi
0x140019b07  pop     rsi
0x140019b08  pop     rbp
0x140019b09  pop     rbx
0x140019b0a  retn
```
