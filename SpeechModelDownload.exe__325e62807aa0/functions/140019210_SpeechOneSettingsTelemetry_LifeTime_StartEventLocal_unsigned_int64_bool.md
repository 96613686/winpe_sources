# SpeechOneSettingsTelemetry::LifeTime::StartEventLocal(unsigned __int64,bool)

- ea: `0x140019210`
- end: `0x1400192a4`
- name: `?StartEventLocal@LifeTime@SpeechOneSettingsTelemetry@@UEAAX_K_N@Z`
- size: `148`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *this, __int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001360`
- `0x1400189d4`
- `0x140019210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001924d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001924d`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::StartEventLocal(
        SpeechOneSettingsTelemetry::LifeTime *this,
        __int64 a2,
        unsigned __int8 a3)
{
  int v3; // esi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r9
  int v11; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v13; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
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
      v11 = v3;
      v12[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)qword_14002A510,
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
0x140019210  push    rbx
0x140019212  push    rbp
0x140019213  push    rsi
0x140019214  push    rdi
0x140019215  sub     rsp, 58h
0x140019219  movzx   esi, r8b
0x14001921d  mov     rbp, rdx
0x140019220  mov     rdi, rcx
0x140019223  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140019228  mov     rbx, rax
0x14001922b  mov     r9d, [rax]
0x14001922e  cmp     r9d, 4
0x140019232  jbe     short loc_14001929B
0x140019234  mov     rax, [rax+18h]
0x140019238  mov     r9, [rbx+10h]
0x14001923c  test    r9b, 1
0x140019240  jz      short loc_14001929B
0x140019242  mov     rcx, rax
0x140019245  and     ecx, 1
0x140019248  cmp     rcx, rax
0x14001924b  jnz     short loc_14001929B
0x14001924d  call    cs:__imp_GetCurrentThreadId
0x140019253  mov     r9, [rdi+30h]
0x140019257  lea     r8, [rdi+20h]
0x14001925b  mov     [rsp+78h+arg_18], eax
0x140019262  lea     rdx, qword_14002A510
0x140019269  lea     rax, [rsp+78h+arg_18]
0x140019271  mov     [rsp+78h+var_38], esi
0x140019275  mov     [rsp+78h+var_48], rax
0x14001927a  mov     rcx, rbx
0x14001927d  lea     rax, [rsp+78h+var_38]
0x140019282  mov     [rsp+78h+var_30], rbp
0x140019287  mov     [rsp+78h+var_50], rax
0x14001928c  lea     rax, [rsp+78h+var_30]
0x140019291  mov     [rsp+78h+var_58], rax
0x140019296  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001929b  add     rsp, 58h
0x14001929f  pop     rdi
0x1400192a0  pop     rsi
0x1400192a1  pop     rbp
0x1400192a2  pop     rbx
0x1400192a3  retn
```
