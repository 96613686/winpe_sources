# DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::Stop(bool)

- ea: `0x14000bb94`
- end: `0x14000be2c`
- name: `?Stop@GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAAX_N@Z`
- size: `664`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x14000b0cc`

## callees

- `0x1400012cc`
- `0x1400022ec`
- `0x140002318`
- `0x140002f40`
- `0x1400082c0`
- `0x14000946c`
- `0x14000bb94`
- `0x14000efa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bd85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000bd85`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::Stop(
        DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *this,
        unsigned __int8 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  const struct _tlgProvider_t *v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v17; // [rsp+B4h] [rbp-7Ch] BYREF
  int v18; // [rsp+B8h] [rbp-78h] BYREF
  int v19; // [rsp+BCh] [rbp-74h] BYREF
  int v20; // [rsp+C0h] [rbp-70h] BYREF
  int v21; // [rsp+C4h] [rbp-6Ch] BYREF
  int v22; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30; // [rsp+108h] [rbp-28h] BYREF
  __int64 v31; // [rsp+110h] [rbp-20h] BYREF
  __int64 v32; // [rsp+118h] [rbp-18h] BYREF
  char v33[32]; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v34; // [rsp+140h] [rbp+10h]
  __int64 v35; // [rsp+148h] [rbp+18h]
  int *v36; // [rsp+150h] [rbp+20h]
  __int64 v37; // [rsp+158h] [rbp+28h]
  DWORD *v38; // [rsp+160h] [rbp+30h]
  __int64 v39; // [rsp+168h] [rbp+38h]
  int *v40; // [rsp+170h] [rbp+40h]
  __int64 v41; // [rsp+178h] [rbp+48h]

  v2 = *((_QWORD *)this + 34);
  v4 = a2;
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = DirectXDatabaseUpdaterLogging::Provider();
    v10 = v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v24 = *((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v25 = *((_QWORD *)v6 + 14);
      v20 = v6[26];
      v26 = *((_QWORD *)v6 + 12);
      v27 = *((_QWORD *)v6 + 11);
      v21 = v6[20];
      v28 = *((_QWORD *)v6 + 9);
      v22 = v6[8];
      v29 = *((_QWORD *)v6 + 3);
      v16 = *v6;
      v30 = *((_QWORD *)v6 + 16);
      v17 = v6[16];
      v31 = *((_QWORD *)v6 + 7);
      v18 = v6[2];
      v32 = 0x1000000;
      v23 = 0x1000000;
      v19 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&byte_14001DD9F,
        v11 + 8,
        (_DWORD)v10,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v18,
        (__int64)&v31,
        (__int64)&v17,
        (__int64)&v30,
        (__int64)&v16,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v21,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = DirectXDatabaseUpdaterLogging::Provider();
    v13 = v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v18 = v4;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v17 = CurrentThreadId;
      v41 = 4;
      v39 = 4;
      v16 = *(_DWORD *)(v15 + 72);
      v23 = 0x1000000;
      v40 = &v18;
      v38 = &v17;
      v36 = &v16;
      v34 = &v23;
      v37 = 4;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v13, &word_14001DAC6, v15 + 8, 0, 6, v33);
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x14000bb94  push    rbp
0x14000bb96  push    rbx
0x14000bb97  push    rsi
0x14000bb98  push    rdi
0x14000bb99  lea     rbp, [rsp-68h]
0x14000bb9e  sub     rsp, 198h
0x14000bba5  mov     rax, cs:__security_cookie
0x14000bbac  xor     rax, rsp
0x14000bbaf  mov     [rbp+80h+var_30], rax
0x14000bbb3  mov     rdi, [rcx+110h]
0x14000bbba  mov     rbx, rcx
0x14000bbbd  movzx   esi, dl
0x14000bbc0  mov     eax, [rdi+48h]
0x14000bbc3  test    eax, eax
0x14000bbc5  jns     loc_14000BD50
0x14000bbcb  add     rdi, 50h ; 'P'
0x14000bbcf  cmp     eax, [rdi+8]
0x14000bbd2  jnz     loc_14000BD50
0x14000bbd8  test    rdi, rdi
0x14000bbdb  jz      loc_14000BD50
0x14000bbe1  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000bbe6  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000bbeb  mov     r9, rax
0x14000bbee  mov     ecx, [rax]
0x14000bbf0  cmp     ecx, 5
0x14000bbf3  jbe     loc_14000BE0C
0x14000bbf9  mov     rdx, 400000000000h
0x14000bc03  mov     rcx, rax
0x14000bc06  call    _tlgKeywordOn
0x14000bc0b  test    al, al
0x14000bc0d  jz      loc_14000BE0C
0x14000bc13  mov     rax, [rdi+78h]
0x14000bc17  lea     rdx, byte_14001DD9F
0x14000bc1e  mov     [rbp+80h+var_D8], rax
0x14000bc22  mov     rcx, r9
0x14000bc25  mov     rax, [rdi+70h]
0x14000bc29  mov     r8, [rbx+110h]
0x14000bc30  mov     [rbp+80h+var_D0], rax
0x14000bc34  add     r8, 8
0x14000bc38  mov     eax, [rdi+68h]
0x14000bc3b  mov     [rbp+80h+var_F0], eax
0x14000bc3e  mov     rax, [rdi+60h]
0x14000bc42  mov     [rbp+80h+var_C8], rax
0x14000bc46  mov     rax, [rdi+58h]
0x14000bc4a  mov     [rbp+80h+var_C0], rax
0x14000bc4e  mov     eax, [rdi+50h]
0x14000bc51  mov     [rbp+80h+var_EC], eax
0x14000bc54  mov     rax, [rdi+48h]
0x14000bc58  mov     [rbp+80h+var_B8], rax
0x14000bc5c  mov     eax, [rdi+20h]
0x14000bc5f  mov     [rbp+80h+var_E8], eax
0x14000bc62  mov     rax, [rdi+18h]
0x14000bc66  mov     [rbp+80h+var_B0], rax
0x14000bc6a  mov     eax, [rdi]
0x14000bc6c  mov     [rbp+80h+var_100], eax
0x14000bc6f  mov     rax, [rdi+80h]
0x14000bc76  mov     [rbp+80h+var_A8], rax
0x14000bc7a  mov     eax, [rdi+40h]
0x14000bc7d  mov     [rbp+80h+var_FC], eax
0x14000bc80  mov     rax, [rdi+38h]
0x14000bc84  mov     [rbp+80h+var_A0], rax
0x14000bc88  mov     eax, [rdi+8]
0x14000bc8b  mov     [rbp+80h+var_F8], eax
0x14000bc8e  mov     eax, 1000000h
0x14000bc93  mov     [rbp+80h+var_98], rax
0x14000bc97  mov     [rbp+80h+var_E0], rax
0x14000bc9b  lea     rax, [rbp+80h+var_F4]
0x14000bc9f  mov     [rsp+1B0h+var_110], rax
0x14000bca7  lea     rax, [rbp+80h+var_D8]
0x14000bcab  mov     [rsp+1B0h+var_118], rax
0x14000bcb3  lea     rax, [rbp+80h+var_D0]
0x14000bcb7  mov     [rsp+1B0h+var_120], rax
0x14000bcbf  lea     rax, [rbp+80h+var_F0]
0x14000bcc3  mov     [rsp+1B0h+var_128], rax
0x14000bccb  lea     rax, [rbp+80h+var_C8]
0x14000bccf  mov     [rsp+1B0h+var_130], rax
0x14000bcd7  lea     rax, [rbp+80h+var_C0]
0x14000bcdb  mov     [rsp+1B0h+var_138], rax
0x14000bce0  lea     rax, [rbp+80h+var_EC]
0x14000bce4  mov     [rsp+1B0h+var_140], rax
0x14000bce9  lea     rax, [rbp+80h+var_B8]
0x14000bced  mov     [rsp+1B0h+var_148], rax
0x14000bcf2  lea     rax, [rbp+80h+var_E8]
0x14000bcf6  mov     [rsp+1B0h+var_150], rax
0x14000bcfb  lea     rax, [rbp+80h+var_B0]
0x14000bcff  mov     [rsp+1B0h+var_158], rax
0x14000bd04  lea     rax, [rbp+80h+var_100]
0x14000bd08  mov     [rsp+1B0h+var_160], rax
0x14000bd0d  lea     rax, [rbp+80h+var_A8]
0x14000bd11  mov     [rsp+1B0h+var_168], rax
0x14000bd16  lea     rax, [rbp+80h+var_FC]
0x14000bd1a  mov     [rsp+1B0h+var_170], rax
0x14000bd1f  lea     rax, [rbp+80h+var_A0]
0x14000bd23  mov     [rsp+1B0h+var_178], rax
0x14000bd28  lea     rax, [rbp+80h+var_F8]
0x14000bd2c  mov     [rsp+1B0h+var_180], rax
0x14000bd31  lea     rax, [rbp+80h+var_98]
0x14000bd35  mov     [rsp+1B0h+var_188], rax
0x14000bd3a  lea     rax, [rbp+80h+var_E0]
0x14000bd3e  mov     [rsp+1B0h+var_190], rax
0x14000bd43  mov     [rbp+80h+var_F4], esi
0x14000bd46  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14000bd4b  jmp     loc_14000BE0C
0x14000bd50  call    ?zInternalStop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000bd55  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000bd5a  mov     rdi, rax
0x14000bd5d  mov     ecx, [rax]
0x14000bd5f  cmp     ecx, 5
0x14000bd62  jbe     loc_14000BE0C
0x14000bd68  mov     rdx, 400000000000h
0x14000bd72  mov     rcx, rax
0x14000bd75  call    _tlgKeywordOn
0x14000bd7a  test    al, al
0x14000bd7c  jz      loc_14000BE0C
0x14000bd82  mov     [rbp+80h+var_F8], esi
0x14000bd85  call    cs:__imp_GetCurrentThreadId
0x14000bd8b  mov     r8, [rbx+110h]
0x14000bd92  lea     rdx, word_14001DAC6
0x14000bd99  mov     [rbp+80h+var_FC], eax
0x14000bd9c  xor     r9d, r9d
0x14000bd9f  mov     rcx, rdi
0x14000bda2  mov     [rbp+80h+var_38], 4
0x14000bdaa  mov     [rbp+80h+var_48], 4
0x14000bdb2  mov     eax, [r8+48h]
0x14000bdb6  add     r8, 8
0x14000bdba  mov     [rbp+80h+var_100], eax
0x14000bdbd  mov     eax, 1000000h
0x14000bdc2  mov     [rbp+80h+var_E0], rax
0x14000bdc6  lea     rax, [rbp+80h+var_F8]
0x14000bdca  mov     [rbp+80h+var_40], rax
0x14000bdce  lea     rax, [rbp+80h+var_FC]
0x14000bdd2  mov     [rbp+80h+var_50], rax
0x14000bdd6  lea     rax, [rbp+80h+var_100]
0x14000bdda  mov     [rbp+80h+var_60], rax
0x14000bdde  lea     rax, [rbp+80h+var_E0]
0x14000bde2  mov     [rbp+80h+var_70], rax
0x14000bde6  lea     rax, [rbp+80h+var_90]
0x14000bdea  mov     [rsp+1B0h+var_188], rax
0x14000bdef  mov     dword ptr [rsp+1B0h+var_190], 6
0x14000bdf7  mov     [rbp+80h+var_58], 4
0x14000bdff  mov     [rbp+80h+var_68], 8
0x14000be07  call    _tlgWriteTransfer_EventWriteTransfer
0x14000be0c  mov     rcx, rbx
0x14000be0f  call    ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000be14  mov     rcx, [rbp+80h+var_30]
0x14000be18  xor     rcx, rsp; StackCookie
0x14000be1b  call    __security_check_cookie
0x14000be20  add     rsp, 198h
0x14000be27  pop     rdi
0x14000be28  pop     rsi
0x14000be29  pop     rbx
0x14000be2a  pop     rbp
0x14000be2b  retn
```
