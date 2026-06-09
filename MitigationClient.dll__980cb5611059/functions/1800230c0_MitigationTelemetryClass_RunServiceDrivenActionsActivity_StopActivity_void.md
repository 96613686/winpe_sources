# MitigationTelemetryClass::RunServiceDrivenActionsActivity::StopActivity(void)

- ea: `0x1800230c0`
- end: `0x1800232e2`
- name: `?StopActivity@RunServiceDrivenActionsActivity@MitigationTelemetryClass@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(MitigationTelemetryClass::RunServiceDrivenActionsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x1800230c0`
- `0x1800246bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023282`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::RunServiceDrivenActionsActivity::StopActivity(
        MitigationTelemetryClass::RunServiceDrivenActionsActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const char *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const char *v21; // [rsp+C0h] [rbp+7h] BYREF
  const char *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const char *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = MitigationTelemetryClass::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const char *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const char *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const char *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const char *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const char *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v18 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&word_18006D956,
        v10 + 8,
        v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = MitigationTelemetryClass::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&word_18006D8F6,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1800230c0  push    rbp
0x1800230c2  push    rbx
0x1800230c3  push    rdi
0x1800230c4  lea     rbp, [rsp-47h]
0x1800230c9  sub     rsp, 100h
0x1800230d0  mov     rdi, [rcx+110h]
0x1800230d7  mov     rbx, rcx
0x1800230da  mov     eax, [rdi+48h]
0x1800230dd  test    eax, eax
0x1800230df  jns     loc_180023258
0x1800230e5  add     rdi, 50h ; 'P'
0x1800230e9  cmp     eax, [rdi+8]
0x1800230ec  jnz     loc_180023258
0x1800230f2  test    rdi, rdi
0x1800230f5  jz      loc_180023258
0x1800230fb  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180023100  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180023105  mov     r9, rax
0x180023108  mov     ecx, [rax]
0x18002310a  cmp     ecx, 5
0x18002310d  jbe     loc_1800232D0
0x180023113  mov     rdx, 400000000000h
0x18002311d  mov     rcx, rax
0x180023120  call    _tlgKeywordOn
0x180023125  test    al, al
0x180023127  jz      loc_1800232D0
0x18002312d  mov     rax, [rdi+70h]
0x180023131  lea     rdx, word_18006D956
0x180023138  mov     rcx, [rdi+78h]
0x18002313c  mov     r8, [rbx+110h]
0x180023143  mov     [rbp+57h+var_60], rax
0x180023147  add     r8, 8
0x18002314b  mov     eax, [rdi+68h]
0x18002314e  mov     [rbp+57h+arg_0], eax
0x180023151  mov     rax, [rdi+60h]
0x180023155  mov     [rbp+57h+var_58], rax
0x180023159  mov     rax, [rdi+58h]
0x18002315d  mov     [rbp+57h+var_50], rax
0x180023161  mov     eax, [rdi+50h]
0x180023164  mov     [rbp+57h+arg_8], eax
0x180023167  mov     rax, [rdi+48h]
0x18002316b  mov     [rbp+57h+var_48], rax
0x18002316f  mov     eax, [rdi+20h]
0x180023172  mov     dword ptr [rbp+57h+arg_10], eax
0x180023175  mov     rax, [rdi+18h]
0x180023179  mov     [rbp+57h+var_40], rax
0x18002317d  mov     eax, [rdi]
0x18002317f  mov     [rbp+57h+arg_18], eax
0x180023182  mov     rax, [rdi+80h]
0x180023189  mov     [rbp+57h+var_38], rax
0x18002318d  mov     eax, [rdi+40h]
0x180023190  mov     [rbp+57h+var_70], eax
0x180023193  mov     rax, [rdi+38h]
0x180023197  mov     [rbp+57h+var_30], rax
0x18002319b  mov     eax, [rdi+8]
0x18002319e  mov     [rbp+57h+var_6C], eax
0x1800231a1  mov     eax, 1000000h
0x1800231a6  mov     [rbp+57h+var_28], rax
0x1800231aa  mov     [rbp+57h+var_20], rax
0x1800231ae  lea     rax, [rbp+57h+var_68]
0x1800231b2  mov     [rsp+110h+var_78], rax
0x1800231ba  lea     rax, [rbp+57h+var_60]
0x1800231be  mov     [rsp+110h+var_80], rax
0x1800231c6  lea     rax, [rbp+57h+arg_0]
0x1800231ca  mov     [rsp+110h+var_88], rax
0x1800231d2  lea     rax, [rbp+57h+var_58]
0x1800231d6  mov     [rsp+110h+var_90], rax
0x1800231de  lea     rax, [rbp+57h+var_50]
0x1800231e2  mov     [rsp+110h+var_98], rax
0x1800231e7  lea     rax, [rbp+57h+arg_8]
0x1800231eb  mov     [rsp+110h+var_A0], rax
0x1800231f0  lea     rax, [rbp+57h+var_48]
0x1800231f4  mov     [rsp+110h+var_A8], rax
0x1800231f9  lea     rax, [rbp+57h+arg_10]
0x1800231fd  mov     [rsp+110h+var_B0], rax
0x180023202  lea     rax, [rbp+57h+var_40]
0x180023206  mov     [rsp+110h+var_B8], rax
0x18002320b  lea     rax, [rbp+57h+arg_18]
0x18002320f  mov     [rsp+110h+var_C0], rax
0x180023214  lea     rax, [rbp+57h+var_38]
0x180023218  mov     [rsp+110h+var_C8], rax
0x18002321d  lea     rax, [rbp+57h+var_70]
0x180023221  mov     [rsp+110h+var_D0], rax
0x180023226  lea     rax, [rbp+57h+var_30]
0x18002322a  mov     [rsp+110h+var_D8], rax
0x18002322f  lea     rax, [rbp+57h+var_6C]
0x180023233  mov     [rsp+110h+var_E0], rax
0x180023238  lea     rax, [rbp+57h+var_28]
0x18002323c  mov     [rsp+110h+var_E8], rax
0x180023241  lea     rax, [rbp+57h+var_20]
0x180023245  mov     [rbp+57h+var_68], rcx
0x180023249  mov     rcx, r9
0x18002324c  mov     [rsp+110h+var_F0], rax
0x180023251  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180023256  jmp     short loc_1800232D0
0x180023258  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002325d  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180023262  mov     rdi, rax
0x180023265  mov     ecx, [rax]
0x180023267  cmp     ecx, 5
0x18002326a  jbe     short loc_1800232D0
0x18002326c  mov     rdx, 400000000000h
0x180023276  mov     rcx, rax
0x180023279  call    _tlgKeywordOn
0x18002327e  test    al, al
0x180023280  jz      short loc_1800232D0
0x180023282  call    cs:__imp_GetCurrentThreadId
0x180023288  mov     r8, [rbx+110h]
0x18002328f  lea     rdx, word_18006D8F6
0x180023296  mov     [rbp+57h+arg_0], eax
0x180023299  mov     rcx, rdi
0x18002329c  mov     eax, [r8+48h]
0x1800232a0  add     r8, 8
0x1800232a4  mov     [rbp+57h+arg_8], eax
0x1800232a7  mov     eax, 1000000h
0x1800232ac  mov     [rbp+57h+arg_10], rax
0x1800232b0  lea     rax, [rbp+57h+arg_0]
0x1800232b4  mov     [rsp+110h+var_E0], rax
0x1800232b9  lea     rax, [rbp+57h+arg_8]
0x1800232bd  mov     [rsp+110h+var_E8], rax
0x1800232c2  lea     rax, [rbp+57h+arg_10]
0x1800232c6  mov     [rsp+110h+var_F0], rax
0x1800232cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800232d0  mov     rcx, rbx
0x1800232d3  add     rsp, 100h
0x1800232da  pop     rdi
0x1800232db  pop     rbx
0x1800232dc  pop     rbp
0x1800232dd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
