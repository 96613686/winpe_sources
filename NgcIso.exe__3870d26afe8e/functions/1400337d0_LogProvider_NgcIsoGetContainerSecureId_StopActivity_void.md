# LogProvider::NgcIsoGetContainerSecureId::StopActivity(void)

- ea: `0x1400337d0`
- end: `0x1400339f5`
- name: `?StopActivity@NgcIsoGetContainerSecureId@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::NgcIsoGetContainerSecureId *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x1400337d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033992`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033992`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetContainerSecureId::StopActivity(LogProvider::NgcIsoGetContainerSecureId *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LogProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (unsigned __int8 *)&word_14008B5EE,
        (const GUID *)(v10 + 8),
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_14008B720,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1400337d0  push    rbp
0x1400337d2  push    rbx
0x1400337d3  push    rdi
0x1400337d4  lea     rbp, [rsp-47h]
0x1400337d9  sub     rsp, 100h
0x1400337e0  mov     rdi, [rcx+110h]
0x1400337e7  mov     rbx, rcx
0x1400337ea  mov     eax, [rdi+48h]
0x1400337ed  test    eax, eax
0x1400337ef  jns     loc_140033968
0x1400337f5  add     rdi, 50h ; 'P'
0x1400337f9  cmp     eax, [rdi+8]
0x1400337fc  jnz     loc_140033968
0x140033802  test    rdi, rdi
0x140033805  jz      loc_140033968
0x14003380b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140033810  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033815  mov     r9, rax
0x140033818  mov     ecx, [rax]
0x14003381a  cmp     ecx, 4
0x14003381d  jbe     loc_1400339E3
0x140033823  mov     rdx, 400000000000h
0x14003382d  mov     rcx, rax
0x140033830  call    _tlgKeywordOn
0x140033835  test    al, al
0x140033837  jz      loc_1400339E3
0x14003383d  mov     rax, [rdi+70h]
0x140033841  lea     rdx, word_14008B5EE
0x140033848  mov     rcx, [rdi+78h]
0x14003384c  mov     r8, [rbx+110h]
0x140033853  mov     [rbp+57h+var_60], rax
0x140033857  add     r8, 8
0x14003385b  mov     eax, [rdi+68h]
0x14003385e  mov     [rbp+57h+arg_0], eax
0x140033861  mov     rax, [rdi+60h]
0x140033865  mov     [rbp+57h+var_58], rax
0x140033869  mov     rax, [rdi+58h]
0x14003386d  mov     [rbp+57h+var_50], rax
0x140033871  mov     eax, [rdi+50h]
0x140033874  mov     [rbp+57h+arg_8], eax
0x140033877  mov     rax, [rdi+48h]
0x14003387b  mov     [rbp+57h+var_48], rax
0x14003387f  mov     eax, [rdi+20h]
0x140033882  mov     dword ptr [rbp+57h+arg_10], eax
0x140033885  mov     rax, [rdi+18h]
0x140033889  mov     [rbp+57h+var_40], rax
0x14003388d  mov     eax, [rdi]
0x14003388f  mov     [rbp+57h+arg_18], eax
0x140033892  mov     rax, [rdi+80h]
0x140033899  mov     [rbp+57h+var_38], rax
0x14003389d  mov     eax, [rdi+40h]
0x1400338a0  mov     [rbp+57h+var_70], eax
0x1400338a3  mov     rax, [rdi+38h]
0x1400338a7  mov     [rbp+57h+var_30], rax
0x1400338ab  mov     eax, [rdi+8]
0x1400338ae  mov     [rbp+57h+var_6C], eax
0x1400338b1  mov     eax, 1000000h
0x1400338b6  mov     [rbp+57h+var_28], rax
0x1400338ba  mov     [rbp+57h+var_20], rax
0x1400338be  lea     rax, [rbp+57h+var_68]
0x1400338c2  mov     [rsp+110h+var_78], rax
0x1400338ca  lea     rax, [rbp+57h+var_60]
0x1400338ce  mov     [rsp+110h+var_80], rax
0x1400338d6  lea     rax, [rbp+57h+arg_0]
0x1400338da  mov     [rsp+110h+var_88], rax
0x1400338e2  lea     rax, [rbp+57h+var_58]
0x1400338e6  mov     [rsp+110h+var_90], rax
0x1400338ee  lea     rax, [rbp+57h+var_50]
0x1400338f2  mov     [rsp+110h+var_98], rax
0x1400338f7  lea     rax, [rbp+57h+arg_8]
0x1400338fb  mov     [rsp+110h+var_A0], rax
0x140033900  lea     rax, [rbp+57h+var_48]
0x140033904  mov     [rsp+110h+var_A8], rax
0x140033909  lea     rax, [rbp+57h+arg_10]
0x14003390d  mov     [rsp+110h+var_B0], rax
0x140033912  lea     rax, [rbp+57h+var_40]
0x140033916  mov     [rsp+110h+var_B8], rax
0x14003391b  lea     rax, [rbp+57h+arg_18]
0x14003391f  mov     [rsp+110h+var_C0], rax
0x140033924  lea     rax, [rbp+57h+var_38]
0x140033928  mov     [rsp+110h+var_C8], rax
0x14003392d  lea     rax, [rbp+57h+var_70]
0x140033931  mov     [rsp+110h+var_D0], rax
0x140033936  lea     rax, [rbp+57h+var_30]
0x14003393a  mov     [rsp+110h+var_D8], rax
0x14003393f  lea     rax, [rbp+57h+var_6C]
0x140033943  mov     [rsp+110h+var_E0], rax
0x140033948  lea     rax, [rbp+57h+var_28]
0x14003394c  mov     [rsp+110h+var_E8], rax
0x140033951  lea     rax, [rbp+57h+var_20]
0x140033955  mov     [rbp+57h+var_68], rcx
0x140033959  mov     rcx, r9
0x14003395c  mov     [rsp+110h+var_F0], rax
0x140033961  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140033966  jmp     short loc_1400339E3
0x140033968  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14003396d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033972  mov     rdi, rax
0x140033975  mov     ecx, [rax]
0x140033977  cmp     ecx, 4
0x14003397a  jbe     short loc_1400339E3
0x14003397c  mov     rdx, 400000000000h
0x140033986  mov     rcx, rax
0x140033989  call    _tlgKeywordOn
0x14003398e  test    al, al
0x140033990  jz      short loc_1400339E3
0x140033992  call    cs:__imp_GetCurrentThreadId
0x140033998  mov     r8, [rbx+110h]
0x14003399f  lea     rdx, unk_14008B720
0x1400339a6  mov     [rbp+57h+arg_0], eax
0x1400339a9  xor     r9d, r9d
0x1400339ac  mov     rcx, rdi
0x1400339af  mov     eax, [r8+48h]
0x1400339b3  add     r8, 8
0x1400339b7  mov     [rbp+57h+arg_8], eax
0x1400339ba  mov     eax, 1000000h
0x1400339bf  mov     [rbp+57h+arg_10], rax
0x1400339c3  lea     rax, [rbp+57h+arg_0]
0x1400339c7  mov     [rsp+110h+var_E0], rax
0x1400339cc  lea     rax, [rbp+57h+arg_8]
0x1400339d0  mov     [rsp+110h+var_E8], rax
0x1400339d5  lea     rax, [rbp+57h+arg_10]
0x1400339d9  mov     [rsp+110h+var_F0], rax
0x1400339de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400339e3  mov     rcx, rbx
0x1400339e6  add     rsp, 100h
0x1400339ed  pop     rdi
0x1400339ee  pop     rbx
0x1400339ef  pop     rbp
0x1400339f0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
