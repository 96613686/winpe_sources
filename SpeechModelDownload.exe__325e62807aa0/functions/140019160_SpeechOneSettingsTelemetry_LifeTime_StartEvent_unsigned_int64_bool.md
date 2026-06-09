# SpeechOneSettingsTelemetry::LifeTime::StartEvent(unsigned __int64,bool)

- ea: `0x140019160`
- end: `0x1400191fd`
- name: `?StartEvent@LifeTime@SpeechOneSettingsTelemetry@@UEAAX_K_N@Z`
- size: `157`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *this, __int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001360`
- `0x1400189d4`
- `0x140019160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400191a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400191a6`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::StartEvent(
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
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = v3;
      v12[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_14002A349,
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
0x140019160  push    rbx
0x140019162  push    rbp
0x140019163  push    rsi
0x140019164  push    rdi
0x140019165  sub     rsp, 58h
0x140019169  movzx   esi, r8b
0x14001916d  mov     rbp, rdx
0x140019170  mov     rdi, rcx
0x140019173  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x140019178  mov     rbx, rax
0x14001917b  mov     r9d, [rax]
0x14001917e  cmp     r9d, 4
0x140019182  jbe     short loc_1400191F4
0x140019184  mov     rax, [rax+18h]
0x140019188  mov     rdx, 400000000000h
0x140019192  mov     r9, [rbx+10h]
0x140019196  test    rdx, r9
0x140019199  jz      short loc_1400191F4
0x14001919b  mov     rcx, rax
0x14001919e  and     rcx, rdx
0x1400191a1  cmp     rcx, rax
0x1400191a4  jnz     short loc_1400191F4
0x1400191a6  call    cs:__imp_GetCurrentThreadId
0x1400191ac  mov     r9, [rdi+30h]
0x1400191b0  lea     r8, [rdi+20h]
0x1400191b4  mov     [rsp+78h+arg_18], eax
0x1400191bb  lea     rdx, byte_14002A349
0x1400191c2  lea     rax, [rsp+78h+arg_18]
0x1400191ca  mov     [rsp+78h+var_38], esi
0x1400191ce  mov     [rsp+78h+var_48], rax
0x1400191d3  mov     rcx, rbx
0x1400191d6  lea     rax, [rsp+78h+var_38]
0x1400191db  mov     [rsp+78h+var_30], rbp
0x1400191e0  mov     [rsp+78h+var_50], rax
0x1400191e5  lea     rax, [rsp+78h+var_30]
0x1400191ea  mov     [rsp+78h+var_58], rax
0x1400191ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400191f4  add     rsp, 58h
0x1400191f8  pop     rdi
0x1400191f9  pop     rsi
0x1400191fa  pop     rbp
0x1400191fb  pop     rbx
0x1400191fc  retn
```
