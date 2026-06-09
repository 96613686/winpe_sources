# CloudAPHelper::GetServerNonce(ushort * *)

- ea: `0x18015a010`
- end: `0x18015a5dc`
- name: `?GetServerNonce@CloudAPHelper@@UEAAJPEAPEAG@Z`
- size: `1484`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000116c`
- `0x18000146c`
- `0x18000202c`
- `0x18000ce04`
- `0x18007f6a4`
- `0x18015944c`
- `0x18015a010`
- `0x18015f650`
- `0x18019c010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18015a5af`
- `SspiCli!LsaFreeReturnBuffer` at `0x18015a5af`

## string_xrefs

- `0x18015a091`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a129`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a1d0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a26f`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a30b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a444`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a4e6`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a55b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a105`: `GetInstanceOfJsonHelper failed`
- `0x18015a1ac`: `spJsonHelper->SetValue(call) failed`
- `0x18015a2e7`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x18015a24b`: `spJsonHelper->SetValue(correlationId) failed`
- `0x18015a420`: `spJsonHelper->SetJsonString failed`
- `0x18015a4c2`: `spJsonHelper->GetValue(ts_nonce) failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::GetServerNonce(CloudAPHelper *this, unsigned __int16 **a2, int a3, int a4)
{
  CloudAPHelper *v5; // r14
  int InstanceOfJsonHelper; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  struct IJsonHelper *v9; // rdi
  int v10; // ecx
  unsigned int v11; // r8d
  int v12; // r9d
  const char **v14; // [rsp+38h] [rbp-29h]
  const char **v15; // [rsp+48h] [rbp-19h]
  const char **v16; // [rsp+50h] [rbp-11h]
  int v17; // [rsp+58h] [rbp-9h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-1h] BYREF
  void *Block; // [rsp+68h] [rbp+7h] BYREF
  struct IJsonHelper *v20; // [rsp+70h] [rbp+Fh] BYREF
  const char *v21; // [rsp+78h] [rbp+17h] BYREF
  const char *v22; // [rsp+80h] [rbp+1Fh] BYREF
  const char *v23; // [rsp+88h] [rbp+27h] BYREF
  _QWORD v24[5]; // [rsp+90h] [rbp+2Fh] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+6Fh] BYREF
  unsigned int v26; // [rsp+D8h] [rbp+77h] BYREF
  int v27; // [rsp+E0h] [rbp+7Fh] BYREF

  v20 = 0;
  Block = 0;
  v5 = this;
  v25 = 0;
  Buffer = 0;
  v26 = 0;
  if ( !a2 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_30;
    v27 = 169;
    v21 = "Missing paramter ppNonce";
    v7 = (__int16 *)qword_18029EFE0;
    v22 = "GetServerNonce";
    v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
    v24[0] = "Error condition failed";
    v16 = &v21;
    v15 = &v22;
    v14 = &v23;
    v8 = (const char **)v24;
    goto LABEL_4;
  }
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v20);
  if ( InstanceOfJsonHelper >= 0 )
  {
    v9 = v20;
    InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *))(*(_QWORD *)v20 + 104LL))(
                             v20,
                             L"call");
    if ( InstanceOfJsonHelper >= 0 )
    {
      InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, __int64))(*(_QWORD *)v9 + 120LL))(
                               v9,
                               L"correlationId",
                               (__int64)v5 + 72);
      if ( InstanceOfJsonHelper >= 0 )
      {
        InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, void **, unsigned int *))(*(_QWORD *)v9 + 48LL))(
                                 v9,
                                 &Block,
                                 &v25);
        if ( InstanceOfJsonHelper >= 0 )
        {
          InstanceOfJsonHelper = CloudAPHelper::CallCloudAP(v5, (unsigned __int8 *)Block, v25, &Buffer, &v26);
          if ( InstanceOfJsonHelper >= 0 )
          {
            if ( Buffer && (v11 = v26) != 0 )
            {
              InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v9 + 56LL))(v9);
              if ( InstanceOfJsonHelper >= 0 )
              {
                InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v9 + 88LL))(
                                         v9,
                                         L"ts_nonce",
                                         a2);
                if ( InstanceOfJsonHelper < 0 && (unsigned int)CallbackContext > 2 )
                {
                  v27 = 207;
                  v24[0] = "spJsonHelper->GetValue(ts_nonce) failed";
                  v7 = &word_18029ECEE;
                  v23 = "GetServerNonce";
                  v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v21 = "Error HResult failed";
                  v16 = (const char **)v24;
                  v15 = &v23;
                  v14 = &v22;
                  v8 = &v21;
                  goto LABEL_4;
                }
              }
              else if ( (unsigned int)CallbackContext > 2 )
              {
                v27 = 204;
                v24[0] = "spJsonHelper->SetJsonString failed";
                v7 = word_18029ED8A;
                v23 = "GetServerNonce";
                v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v21 = "Error HResult failed";
                v16 = (const char **)v24;
                v15 = &v23;
                v14 = &v22;
                v8 = &v21;
                goto LABEL_4;
              }
            }
            else
            {
              InstanceOfJsonHelper = -2147467259;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v27 = 194;
                v24[0] = "GetServerNonce";
                v17 = -2147467259;
                v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v22 = "CloudAP returned an empty responce to the nonce request";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v10,
                  (unsigned int)&dword_18029EE14,
                  v11,
                  v12,
                  (__int64)&v22,
                  (__int64)&v17,
                  (__int64)&v23,
                  (__int64)&v27,
                  (__int64)v24);
              }
            }
          }
          else if ( (unsigned int)CallbackContext > 3 )
          {
            v27 = InstanceOfJsonHelper;
            v24[0] = "GetServerNonce";
            v23 = "CallCloudAP failed";
            v22 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v10,
              (unsigned int)qword_18029EDD8,
              v11,
              v12,
              (__int64)&v22,
              (__int64)&v23,
              (__int64)&v27,
              (__int64)v24);
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = 186;
          v24[0] = "spJsonHelper->GetJsonStringAsByteArray failed";
          v7 = word_18029EE5A;
          v23 = "GetServerNonce";
          v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v21 = "Error HResult failed";
          v16 = (const char **)v24;
          v15 = &v23;
          v14 = &v22;
          v8 = &v21;
          goto LABEL_4;
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v27 = 183;
        v24[0] = "spJsonHelper->SetValue(correlationId) failed";
        v7 = &word_18029EEF6;
        v23 = "GetServerNonce";
        v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v21 = "Error HResult failed";
        v16 = (const char **)v24;
        v15 = &v23;
        v14 = &v22;
        v8 = &v21;
        goto LABEL_4;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 180;
      v24[0] = "spJsonHelper->SetValue(call) failed";
      v7 = (__int16 *)qword_18029EEA8;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
      goto LABEL_4;
    }
  }
  else
  {
    LODWORD(this) = (_DWORD)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 177;
      v24[0] = "GetInstanceOfJsonHelper failed";
      v7 = (__int16 *)&dword_18029EF44;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
LABEL_4:
      v17 = InstanceOfJsonHelper;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v7,
        a3,
        a4,
        (__int64)v8,
        (__int64)&v17,
        (__int64)v14,
        (__int64)&v27,
        (__int64)v15,
        (__int64)v16);
    }
  }
LABEL_30:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( Block )
    operator delete(Block);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v20);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x18015a010  mov     r11, rsp
0x18015a013  push    rbp
0x18015a014  push    rbx
0x18015a015  push    rsi
0x18015a016  push    rdi
0x18015a017  push    r14
0x18015a019  lea     rbp, [r11-5Fh]
0x18015a01d  sub     rsp, 90h
0x18015a024  mov     [rbp+57h+var_48], 0
0x18015a02c  mov     rsi, rdx
0x18015a02f  mov     [rbp+57h+Block], 0
0x18015a037  mov     r14, rcx
0x18015a03a  mov     [rbp+57h+arg_8], 0
0x18015a041  mov     [rbp+57h+Buffer], 0
0x18015a049  mov     [rbp+57h+arg_10], 0
0x18015a050  test    rdx, rdx
0x18015a053  jnz     loc_18015A0E7
0x18015a059  mov     eax, cs:CallbackContext
0x18015a05f  mov     ebx, 80070057h
0x18015a064  cmp     eax, 2
0x18015a067  jbe     loc_18015A5A6
0x18015a06d  lea     rax, aMissingParamte; "Missing paramter ppNonce"
0x18015a074  mov     [rbp+57h+arg_18], 0A9h
0x18015a07b  mov     [rbp+57h+var_40], rax
0x18015a07f  lea     rdx, qword_18029EFE0
0x18015a086  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a08d  mov     [rbp+57h+var_38], rax
0x18015a091  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a098  mov     [rbp+57h+var_30], rax
0x18015a09c  lea     rax, aErrorCondition; "Error condition failed"
0x18015a0a3  mov     [rbp+57h+var_28], rax
0x18015a0a7  lea     rax, [rbp+57h+var_40]
0x18015a0ab  mov     [r11-70h], rax
0x18015a0af  lea     rax, [rbp+57h+var_38]
0x18015a0b3  mov     [r11-78h], rax
0x18015a0b7  lea     rax, [rbp+57h+arg_18]
0x18015a0bb  mov     [r11-80h], rax
0x18015a0bf  lea     rax, [rbp+57h+var_30]
0x18015a0c3  mov     [rsp+0B0h+var_80], rax
0x18015a0c8  lea     rax, [rbp+57h+var_60]
0x18015a0cc  mov     [rsp+0B0h+var_88], rax
0x18015a0d1  lea     rax, [rbp+57h+var_28]
0x18015a0d5  mov     [rbp+57h+var_60], ebx
0x18015a0d8  mov     [rsp+0B0h+var_90], rax
0x18015a0dd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015a0e2  jmp     loc_18015A5A6
0x18015a0e7  lea     rcx, [rbp+57h+var_48]; struct IJsonHelper **
0x18015a0eb  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x18015a0f0  mov     ebx, eax
0x18015a0f2  test    eax, eax
0x18015a0f4  jns     short loc_18015A175
0x18015a0f6  mov     ecx, cs:CallbackContext
0x18015a0fc  cmp     ecx, 2
0x18015a0ff  jbe     loc_18015A5A6
0x18015a105  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x18015a10c  mov     [rbp+57h+arg_18], 0B1h
0x18015a113  mov     [rbp+57h+var_28], rax
0x18015a117  lea     rdx, dword_18029EF44
0x18015a11e  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a125  mov     [rbp+57h+var_30], rax
0x18015a129  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a130  mov     [rbp+57h+var_38], rax
0x18015a134  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a13b  mov     [rbp+57h+var_40], rax
0x18015a13f  lea     rax, [rbp+57h+var_28]
0x18015a143  mov     [rsp+48h], rax
0x18015a148  lea     rax, [rbp+57h+var_30]
0x18015a14c  mov     [rsp+0B0h+var_70], rax
0x18015a151  lea     rax, [rbp+57h+arg_18]
0x18015a155  mov     [rsp+0B0h+var_78], rax
0x18015a15a  lea     rax, [rbp+57h+var_38]
0x18015a15e  mov     [rsp+0B0h+var_80], rax
0x18015a163  lea     rax, [rbp+57h+var_60]
0x18015a167  mov     [rsp+0B0h+var_88], rax
0x18015a16c  lea     rax, [rbp+57h+var_40]
0x18015a170  jmp     loc_18015A0D5
0x18015a175  mov     rdi, [rbp+57h+var_48]
0x18015a179  lea     rdx, aCall; "call"
0x18015a180  movsd   xmm2, cs:__real@4022000000000000
0x18015a188  mov     rcx, rdi
0x18015a18b  mov     rax, [rdi]
0x18015a18e  mov     rax, [rax+68h]
0x18015a192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a197  mov     ebx, eax
0x18015a199  test    eax, eax
0x18015a19b  jns     short loc_18015A21C
0x18015a19d  mov     eax, cs:CallbackContext
0x18015a1a3  cmp     eax, 2
0x18015a1a6  jbe     loc_18015A5A6
0x18015a1ac  lea     rax, aSpjsonhelperSe_2; "spJsonHelper->SetValue(call) failed"
0x18015a1b3  mov     [rbp+57h+arg_18], 0B4h
0x18015a1ba  mov     [rbp+57h+var_28], rax
0x18015a1be  lea     rdx, qword_18029EEA8
0x18015a1c5  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a1cc  mov     [rbp+57h+var_30], rax
0x18015a1d0  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a1d7  mov     [rbp+57h+var_38], rax
0x18015a1db  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a1e2  mov     [rbp+57h+var_40], rax
0x18015a1e6  lea     rax, [rbp+57h+var_28]
0x18015a1ea  mov     [rsp+48h], rax
0x18015a1ef  lea     rax, [rbp+57h+var_30]
0x18015a1f3  mov     [rsp+0B0h+var_70], rax
0x18015a1f8  lea     rax, [rbp+57h+arg_18]
0x18015a1fc  mov     [rsp+0B0h+var_78], rax
0x18015a201  lea     rax, [rbp+57h+var_38]
0x18015a205  mov     [rsp+0B0h+var_80], rax
0x18015a20a  lea     rax, [rbp+57h+var_60]
0x18015a20e  mov     [rsp+0B0h+var_88], rax
0x18015a213  lea     rax, [rbp+57h+var_40]
0x18015a217  jmp     loc_18015A0D5
0x18015a21c  mov     rax, [rdi]
0x18015a21f  lea     r8, [r14+48h]
0x18015a223  lea     rdx, aCorrelationid; "correlationId"
0x18015a22a  mov     rcx, rdi
0x18015a22d  mov     rax, [rax+78h]
0x18015a231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a236  mov     ebx, eax
0x18015a238  test    eax, eax
0x18015a23a  jns     short loc_18015A2BB
0x18015a23c  mov     eax, cs:CallbackContext
0x18015a242  cmp     eax, 2
0x18015a245  jbe     loc_18015A5A6
0x18015a24b  lea     rax, aSpjsonhelperSe_5; "spJsonHelper->SetValue(correlationId) f"...
0x18015a252  mov     [rbp+57h+arg_18], 0B7h
0x18015a259  mov     [rbp+57h+var_28], rax
0x18015a25d  lea     rdx, word_18029EEF6
0x18015a264  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a26b  mov     [rbp+57h+var_30], rax
0x18015a26f  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a276  mov     [rbp+57h+var_38], rax
0x18015a27a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a281  mov     [rbp+57h+var_40], rax
0x18015a285  lea     rax, [rbp+57h+var_28]
0x18015a289  mov     [rsp+48h], rax
0x18015a28e  lea     rax, [rbp+57h+var_30]
0x18015a292  mov     [rsp+0B0h+var_70], rax
0x18015a297  lea     rax, [rbp+57h+arg_18]
0x18015a29b  mov     [rsp+0B0h+var_78], rax
0x18015a2a0  lea     rax, [rbp+57h+var_38]
0x18015a2a4  mov     [rsp+0B0h+var_80], rax
0x18015a2a9  lea     rax, [rbp+57h+var_60]
0x18015a2ad  mov     [rsp+0B0h+var_88], rax
0x18015a2b2  lea     rax, [rbp+57h+var_40]
0x18015a2b6  jmp     loc_18015A0D5
0x18015a2bb  mov     rax, [rdi]
0x18015a2be  lea     r8, [rbp+57h+arg_8]
0x18015a2c2  lea     rdx, [rbp+57h+Block]
0x18015a2c6  mov     rcx, rdi
0x18015a2c9  mov     rax, [rax+30h]
0x18015a2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a2d2  mov     ebx, eax
0x18015a2d4  test    eax, eax
0x18015a2d6  jns     short loc_18015A357
0x18015a2d8  mov     eax, cs:CallbackContext
0x18015a2de  cmp     eax, 2
0x18015a2e1  jbe     loc_18015A5A6
0x18015a2e7  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x18015a2ee  mov     [rbp+57h+arg_18], 0BAh
0x18015a2f5  mov     [rbp+57h+var_28], rax
0x18015a2f9  lea     rdx, word_18029EE5A
0x18015a300  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a307  mov     [rbp+57h+var_30], rax
0x18015a30b  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a312  mov     [rbp+57h+var_38], rax
0x18015a316  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a31d  mov     [rbp+57h+var_40], rax
0x18015a321  lea     rax, [rbp+57h+var_28]
0x18015a325  mov     [rsp+48h], rax
0x18015a32a  lea     rax, [rbp+57h+var_30]
0x18015a32e  mov     [rsp+0B0h+var_70], rax
0x18015a333  lea     rax, [rbp+57h+arg_18]
0x18015a337  mov     [rsp+0B0h+var_78], rax
0x18015a33c  lea     rax, [rbp+57h+var_38]
0x18015a340  mov     [rsp+0B0h+var_80], rax
0x18015a345  lea     rax, [rbp+57h+var_60]
0x18015a349  mov     [rsp+0B0h+var_88], rax
0x18015a34e  lea     rax, [rbp+57h+var_40]
0x18015a352  jmp     loc_18015A0D5
0x18015a357  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18015a35b  lea     rax, [rbp+57h+arg_10]
0x18015a35f  mov     rdx, [rbp+57h+Block]; unsigned __int8 *
0x18015a363  lea     r9, [rbp+57h+Buffer]; void **
0x18015a367  mov     rcx, r14; this
0x18015a36a  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x18015a36f  call    ?CallCloudAP@CloudAPHelper@@AEAAJPEAEKPEAPEAXPEAK@Z; CloudAPHelper::CallCloudAP(uchar *,ulong,void * *,ulong *)
0x18015a374  mov     ebx, eax
0x18015a376  test    eax, eax
0x18015a378  jns     short loc_18015A3E2
0x18015a37a  mov     eax, cs:CallbackContext
0x18015a380  cmp     eax, 3
0x18015a383  jbe     loc_18015A5A6
0x18015a389  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a390  mov     [rbp+57h+arg_18], ebx
0x18015a393  mov     [rbp+57h+var_28], rax
0x18015a397  lea     rdx, qword_18029EDD8
0x18015a39e  lea     rax, aCallcloudapFai; "CallCloudAP failed"
0x18015a3a5  mov     [rbp+57h+var_30], rax
0x18015a3a9  lea     rax, aWarningHresult; "Warning HResult failed"
0x18015a3b0  mov     [rbp+57h+var_38], rax
0x18015a3b4  lea     rax, [rbp+57h+var_28]
0x18015a3b8  mov     [rsp+0B0h+var_78], rax
0x18015a3bd  lea     rax, [rbp+57h+arg_18]
0x18015a3c1  mov     [rsp+0B0h+var_80], rax
0x18015a3c6  lea     rax, [rbp+57h+var_30]
0x18015a3ca  mov     [rsp+0B0h+var_88], rax
0x18015a3cf  lea     rax, [rbp+57h+var_38]
0x18015a3d3  mov     [rsp+0B0h+var_90], rax
0x18015a3d8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18015a3dd  jmp     loc_18015A5A6
0x18015a3e2  mov     rdx, [rbp+57h+Buffer]
0x18015a3e6  test    rdx, rdx
0x18015a3e9  jz      loc_18015A532
0x18015a3ef  mov     r8d, [rbp+57h+arg_10]
0x18015a3f3  test    r8d, r8d
0x18015a3f6  jz      loc_18015A532
0x18015a3fc  mov     rax, [rdi]
0x18015a3ff  mov     rcx, rdi
0x18015a402  mov     rax, [rax+38h]
0x18015a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a40b  mov     ebx, eax
0x18015a40d  test    eax, eax
0x18015a40f  jns     short loc_18015A490
0x18015a411  mov     eax, cs:CallbackContext
0x18015a417  cmp     eax, 2
0x18015a41a  jbe     loc_18015A5A6
0x18015a420  lea     rax, aSpjsonhelperSe_3; "spJsonHelper->SetJsonString failed"
0x18015a427  mov     [rbp+57h+arg_18], 0CCh
0x18015a42e  mov     [rbp+57h+var_28], rax
0x18015a432  lea     rdx, word_18029ED8A
0x18015a439  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a440  mov     [rbp+57h+var_30], rax
0x18015a444  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a44b  mov     [rbp+57h+var_38], rax
0x18015a44f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a456  mov     [rbp+57h+var_40], rax
0x18015a45a  lea     rax, [rbp+57h+var_28]
0x18015a45e  mov     [rsp+48h], rax
0x18015a463  lea     rax, [rbp+57h+var_30]
0x18015a467  mov     [rsp+0B0h+var_70], rax
0x18015a46c  lea     rax, [rbp+57h+arg_18]
0x18015a470  mov     [rsp+0B0h+var_78], rax
0x18015a475  lea     rax, [rbp+57h+var_38]
0x18015a479  mov     [rsp+0B0h+var_80], rax
0x18015a47e  lea     rax, [rbp+57h+var_60]
0x18015a482  mov     [rsp+0B0h+var_88], rax
0x18015a487  lea     rax, [rbp+57h+var_40]
0x18015a48b  jmp     loc_18015A0D5
0x18015a490  mov     rax, [rdi]
0x18015a493  lea     rdx, aTsNonce; "ts_nonce"
0x18015a49a  mov     r8, rsi
0x18015a49d  mov     rcx, rdi
0x18015a4a0  mov     rax, [rax+58h]
0x18015a4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a4a9  mov     ebx, eax
0x18015a4ab  test    eax, eax
0x18015a4ad  jns     loc_18015A5A6
0x18015a4b3  mov     eax, cs:CallbackContext
0x18015a4b9  cmp     eax, 2
0x18015a4bc  jbe     loc_18015A5A6
0x18015a4c2  lea     rax, aSpjsonhelperGe_0; "spJsonHelper->GetValue(ts_nonce) failed"
0x18015a4c9  mov     [rbp+57h+arg_18], 0CFh
0x18015a4d0  mov     [rbp+57h+var_28], rax
0x18015a4d4  lea     rdx, word_18029ECEE
0x18015a4db  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a4e2  mov     [rbp+57h+var_30], rax
0x18015a4e6  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a4ed  mov     [rbp+57h+var_38], rax
0x18015a4f1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015a4f8  mov     [rbp+57h+var_40], rax
0x18015a4fc  lea     rax, [rbp+57h+var_28]
0x18015a500  mov     [rsp+48h], rax
0x18015a505  lea     rax, [rbp+57h+var_30]
0x18015a509  mov     [rsp+0B0h+var_70], rax
0x18015a50e  lea     rax, [rbp+57h+arg_18]
0x18015a512  mov     [rsp+0B0h+var_78], rax
0x18015a517  lea     rax, [rbp+57h+var_38]
0x18015a51b  mov     [rsp+0B0h+var_80], rax
0x18015a520  lea     rax, [rbp+57h+var_60]
0x18015a524  mov     [rsp+0B0h+var_88], rax
0x18015a529  lea     rax, [rbp+57h+var_40]
0x18015a52d  jmp     loc_18015A0D5
0x18015a532  mov     eax, cs:CallbackContext
0x18015a538  mov     ebx, 80004005h
0x18015a53d  cmp     eax, 2
0x18015a540  jbe     short loc_18015A5A6
0x18015a542  lea     rax, aGetservernonce; "GetServerNonce"
0x18015a549  mov     [rbp+57h+arg_18], 0C2h
0x18015a550  mov     [rbp+57h+var_28], rax
0x18015a554  lea     rdx, dword_18029EE14
0x18015a55b  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015a562  mov     [rbp+57h+var_60], ebx
0x18015a565  mov     [rbp+57h+var_30], rax
0x18015a569  lea     rax, aCloudapReturne_2; "CloudAP returned an empty responce to t"...
0x18015a570  mov     [rbp+57h+var_38], rax
0x18015a574  lea     rax, [rbp+57h+var_28]
0x18015a578  mov     [rsp+0B0h+var_70], rax
0x18015a57d  lea     rax, [rbp+57h+arg_18]
0x18015a581  mov     [rsp+0B0h+var_78], rax
0x18015a586  lea     rax, [rbp+57h+var_30]
  ... truncated ...
```
