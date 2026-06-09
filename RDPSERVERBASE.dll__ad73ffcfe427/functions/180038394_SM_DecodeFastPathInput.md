# SM_DecodeFastPathInput

- ea: `0x180038394`
- end: `0x180038a98`
- name: `SM_DecodeFastPathInput`
- size: `1796`
- prototype: `void __fastcall(unsigned int *, unsigned __int8 *, unsigned int, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037240`

## callees

- `0x18000116c`
- `0x180001f84`
- `0x180002170`
- `0x180004924`
- `0x18000bc50`
- `0x180038394`
- `0x180076198`
- `0x180079770`
- `0x18007a404`
- `0x18017adb0`
- `0x18017aee4`
- `0x18018520c`
- `0x180191f20`

## import_xrefs

- `RDPBASE!UpdateSessionKey` at `0x18003851d`
- `RDPBASE!UpdateSessionKey` at `0x18003851d`
- `RDPBASE!DecryptData` at `0x180038711`
- `RDPBASE!DecryptData` at `0x180038711`

## string_xrefs

- `0x180038536`: `SM failed to update session key`
- `0x180038931`: `Unencrypted data in encrypted protocol`
- `0x1800383e4`: `SM_DecodeFastPathInput`
- `0x180038943`: `SM_DecodeFastPathInput`
- `0x180038a24`: `SM_DecodeFastPathInput`
- `0x1800385e4`: `PDU len %u too short for security context in FIPS decryption`
- `0x18003841c`: `fastpath: fSecureChecksum: 0x%x setting does not match protocol: 0x%x`
- `0x180038883`: `SM_DecodeFastPathInput: failed session key creation, wait status=%X, sess key status = %X`
- `0x180038a12`: `Received fast-path input data before SM initialized, ignoring`
- `0x1800387fa`: `PDU len %u too short for security context`

## pseudocode

```c
void __fastcall SM_DecodeFastPathInput(
        unsigned int *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        int a6)
{
  unsigned int *v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // rax
  unsigned __int8 *v9; // r14
  int v11; // eax
  int v12; // ecx
  unsigned int *v13; // r13
  int v14; // edx
  int v15; // ecx
  __int64 v16; // r8
  int v17; // r9d
  int *v18; // r13
  __int64 v19; // rcx
  int v20; // r9d
  int v21; // r8d
  const char *v22; // rax
  __int16 *v23; // rdx
  unsigned int v24; // eax
  unsigned __int8 *v25; // rsi
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int *v29; // rdx
  int v30; // eax
  int *v31; // rsi
  unsigned __int8 *v32; // rsi
  int v33; // eax
  ShareClass *v34; // rcx
  __int64 v35; // rax
  int v36; // ecx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v38; // [rsp+28h] [rbp-59h]
  int v39; // [rsp+68h] [rbp-19h] BYREF
  int v40; // [rsp+6Ch] [rbp-15h] BYREF
  int v41; // [rsp+70h] [rbp-11h] BYREF
  const char *v42; // [rsp+78h] [rbp-9h] BYREF
  const char *v43; // [rsp+80h] [rbp-1h] BYREF
  _QWORD v44[8]; // [rsp+88h] [rbp+7h] BYREF
  int v45; // [rsp+D8h] [rbp+57h] BYREF
  unsigned __int8 *v46; // [rsp+E0h] [rbp+5Fh]

  v46 = a2;
  v6 = a1 + 18;
  v7 = a3;
  v8 = *((_QWORD *)a1 + 9);
  v9 = a2;
  if ( !v8 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v45 = 389;
      v42 = "Received fast-path input data before SM initialized, ignoring";
      v44[0] = "SM_DecodeFastPathInput";
      v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
      v41 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)qword_1802ADFC0,
        a3,
        a4,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v43,
        (__int64)&v45,
        (__int64)v44);
    }
    return;
  }
  if ( !*((_BYTE *)a1 + 39) )
  {
LABEL_38:
    v34 = *(ShareClass **)(*(_QWORD *)v6 + 128LL);
    if ( !v34 || *((_BYTE *)a1 + 44) || *((_BYTE *)&qword_18026EB48 + a1[12]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_6b1226df7e133985d489506172584101_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
    }
    else
    {
      ShareClass::IM_DecodeFastPathInput(v34, v9, *(_DWORD *)(*(_QWORD *)v6 + 1860LL), v7, a5);
    }
    return;
  }
  if ( !a4 )
  {
    if ( *(_DWORD *)(v8 + 1332) )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v45 = 369;
        v42 = "Unencrypted data in encrypted protocol";
        v44[0] = "SM_DecodeFastPathInput";
        v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
        v41 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)a1,
          (unsigned int)byte_1802ADED9,
          a3,
          0,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v43,
          (__int64)&v45,
          (__int64)v44);
      }
      goto LABEL_52;
    }
    goto LABEL_38;
  }
  v11 = *((unsigned __int8 *)a1 + 43);
  v12 = a6 != 0;
  if ( v11 == v12 )
  {
    v13 = v6;
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LOBYTE(v45) = *((_BYTE *)a1 + 43);
      v44[0] = "fastpath: fSecureChecksum: 0x%x setting does not match protocol: 0x%x";
      v39 = a6;
      v42 = "SM_DecodeFastPathInput";
      v40 = 259;
      v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
      v41 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)byte_1802AE131,
        a3,
        a4,
        (__int64)v44,
        (__int64)&v41,
        (__int64)&v43,
        (__int64)&v40,
        (__int64)&v42,
        (__int64)&v45,
        (__int64)&v39);
    }
    v13 = a1 + 18;
  }
  v14 = CRDPWDUMXStack::WaitForConnectionEvent(
          *(CRDPWDUMXStack **)(*(_QWORD *)(*(_QWORD *)v6 + 8LL) + 24LL),
          *(void **)(*(_QWORD *)v6 + 104LL),
          *(void **)(*(_QWORD *)v6 + 112LL),
          0x2BF20u);
  if ( !*(_BYTE *)(*(_QWORD *)v6 + 16LL) && !v14 && *(int *)(*(_QWORD *)v6 + 120LL) >= 0 )
  {
    if ( v7 < 8 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v41 = 361;
        v22 = "PDU len %u too short for security context";
        v23 = &word_1802ADF1E;
        goto LABEL_44;
      }
LABEL_45:
      v20 = (int)v46;
      v21 = 224;
      v38 = v7;
LABEL_53:
      v19 = *((_QWORD *)a1 + 9);
LABEL_19:
      WDW_LogAndDisconnect(v19, 1, v21, v20, v38);
      return;
    }
    v18 = (int *)(a1 + 46);
    if ( a1[46] == 4096 )
    {
      v16 = a1[3];
      if ( (_DWORD)v16 != 16
        && !(unsigned int)UpdateSessionKey(a1 + 48, a1 + 52, v16, a1[30], *((_QWORD *)a1 + 28), *a1) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v44[0] = "SM_DecodeFastPathInput";
          v42 = "SM failed to update session key";
          v45 = 296;
          v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
          v41 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)qword_1802AE1F0,
            v16,
            v17,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v43,
            (__int64)&v45,
            (__int64)v44);
        }
        v19 = *(_QWORD *)v6;
        v20 = 0;
        v38 = 0;
        v21 = 401;
        goto LABEL_19;
      }
      *v18 = 0;
      v18 = (int *)(a1 + 46);
    }
    if ( a1[3] == 16 )
    {
      if ( v7 < 0xC )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v41 = 303;
          v22 = "PDU len %u too short for security context in FIPS decryption";
          v23 = word_1802AE05A;
LABEL_44:
          v42 = v22;
          v45 = v7;
          v44[0] = "SM_DecodeFastPathInput";
          v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
          v40 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v15,
            (_DWORD)v23,
            v16,
            v17,
            (__int64)&v42,
            (__int64)&v40,
            (__int64)&v43,
            (__int64)&v41,
            (__int64)v44,
            (__int64)&v45);
          goto LABEL_45;
        }
        goto LABEL_45;
      }
      v24 = a1[47];
      v45 = v7 - 12;
      v46 += 12;
      v25 = v46 - 8;
      if ( (unsigned int)TSFIPS_DecryptData(
                           *((_QWORD *)a1 + 31),
                           (_DWORD)v46,
                           v7 - 12,
                           *(v46 - 9),
                           (__int64)(v46 - 8),
                           v24) )
      {
        if ( (unsigned int)CallbackContext <= 2 )
        {
LABEL_52:
          v38 = 0;
          v20 = 0;
          v21 = 402;
          goto LABEL_53;
        }
        v41 = 322;
        v45 = v7 - 8;
        v29 = (int *)byte_1802AE005;
LABEL_28:
        v40 = -2147467259;
        v42 = "SM failed to decrypt data: len=%u";
        v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
        v44[0] = "SM_DecodeFastPathInput";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v26,
          (_DWORD)v29,
          v27,
          v28,
          (__int64)&v42,
          (__int64)&v40,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)v44,
          (__int64)&v45);
        goto LABEL_52;
      }
      v30 = *(v25 - 1);
      v31 = (int *)(a1 + 46);
      v9 = v46;
      v7 = v45 - v30;
    }
    else
    {
      v7 -= 8;
      v32 = v46 + 8;
      if ( !(unsigned int)DecryptData(*a1, a1 + 52, *((_QWORD *)a1 + 28), a1[30], v46 + 8, v7, a1 + 58, v46, a6, a1[47]) )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_52;
        v45 = v7;
        v29 = &dword_1802AE0DC;
        v41 = 346;
        goto LABEL_28;
      }
      v9 = v32;
      v31 = v18;
    }
    if ( (unsigned int)CallbackContext <= 5 )
    {
      v31 = v18;
    }
    else
    {
      v45 = v7 - 8;
      v44[0] = "Data decrypted: %u";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)byte_1802AE0AB,
        v27,
        v28,
        (__int64)v44,
        (__int64)&v45);
    }
    v33 = a1[46] + 1;
    ++a1[47];
    *v31 = v33;
    v6 = a1 + 18;
    goto LABEL_38;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v35 = *(_QWORD *)v13;
    v44[0] = "SM_DecodeFastPathInput";
    v43 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\asmcpp.cpp";
    v36 = *(_DWORD *)(v35 + 120);
    v42 = "SM_DecodeFastPathInput: failed session key creation, wait status=%X, sess key status = %X";
    v41 = v14;
    v45 = v36;
    v40 = 270;
    v39 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v36,
      (unsigned int)byte_1802AE235,
      v16,
      v17,
      (__int64)&v42,
      (__int64)&v39,
      (__int64)&v43,
      (__int64)&v40,
      (__int64)v44,
      (__int64)&v41,
      (__int64)&v45);
  }
  WDW_LogStateTransitionAndDisconnect(*(_QWORD *)v13, v14, 402, 0, 0, 7, 36);
}

```

## disassembly

```asm
0x180038394  mov     r11, rsp
0x180038397  mov     [r11+18h], rbx
0x18003839b  mov     [r11+10h], rdx
0x18003839f  push    rbp
0x1800383a0  push    rsi
0x1800383a1  push    rdi
0x1800383a2  push    r12
0x1800383a4  push    r13
0x1800383a6  push    r14
0x1800383a8  push    r15
0x1800383aa  lea     rbp, [r11-4Fh]
0x1800383ae  sub     rsp, 90h
0x1800383b5  lea     rsi, [rcx+48h]
0x1800383b9  mov     edi, r8d
0x1800383bc  mov     rax, [rsi]
0x1800383bf  mov     r14, rdx
0x1800383c2  mov     rbx, rcx
0x1800383c5  test    rax, rax
0x1800383c8  jz      loc_180038A07
0x1800383ce  cmp     byte ptr [rcx+27h], 0
0x1800383d2  jz      loc_180038799
0x1800383d8  test    r9d, r9d
0x1800383db  jz      loc_180038919
0x1800383e1  mov     edx, [rbp+47h+arg_28]
0x1800383e4  lea     r14, aSmDecodefastpa; "SM_DecodeFastPathInput"
0x1800383eb  movzx   eax, byte ptr [rbx+2Bh]
0x1800383ef  lea     r15, aOnecoreTermsrv_28; "onecore\\termsrv\\rdpplatform\\drivers"...
0x1800383f6  xor     ecx, ecx
0x1800383f8  mov     r12d, 80004005h
0x1800383fe  test    edx, edx
0x180038400  setnz   cl
0x180038403  cmp     eax, ecx
0x180038405  jz      loc_18003848C
0x18003840b  mov     eax, cs:CallbackContext
0x180038411  cmp     eax, 2
0x180038414  jbe     short loc_180038486
0x180038416  mov     al, [rbx+2Bh]
0x180038419  mov     byte ptr [rbp+47h+arg_0], al
0x18003841c  lea     rax, aFastpathFsecur; "fastpath: fSecureChecksum: 0x%x setting"...
0x180038423  mov     [rbp+47h+var_40], rax
0x180038427  lea     rax, [rbp+47h+var_60]
0x18003842b  mov     [r11-78h], rax
0x18003842f  lea     rax, [rbp+47h+arg_0]
0x180038433  mov     [r11-80h], rax
0x180038437  lea     rax, [rbp+47h+var_50]
0x18003843b  mov     [rsp+0C0h+var_80], rax
0x180038440  lea     rax, [rbp+47h+var_5C]
0x180038444  mov     [rsp+0C0h+var_88], rax
0x180038449  lea     rax, [rbp+47h+var_48]
0x18003844d  mov     [rsp+0C0h+var_90], rax
0x180038452  lea     rax, [rbp+47h+var_58]
0x180038456  mov     [rsp+0C0h+var_98], rax
0x18003845b  lea     rax, [rbp+47h+var_40]
0x18003845f  mov     [rbp+47h+var_60], edx
0x180038462  lea     rdx, byte_1802AE131
0x180038469  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003846e  mov     [rbp+47h+var_50], r14
0x180038472  mov     [rbp+47h+var_5C], 103h
0x180038479  mov     [rbp+47h+var_48], r15
0x18003847d  mov     [rbp+47h+var_58], r12d
0x180038481  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180038486  lea     r13, [rbx+48h]
0x18003848a  jmp     short loc_18003848F
0x18003848c  mov     r13, rsi
0x18003848f  mov     rdx, [rsi]
0x180038492  mov     r9d, 2BF20h; unsigned int
0x180038498  mov     rcx, [rdx+8]
0x18003849c  mov     r8, [rdx+70h]; void *
0x1800384a0  mov     rdx, [rdx+68h]; void *
0x1800384a4  mov     rcx, [rcx+18h]; this
0x1800384a8  call    ?WaitForConnectionEvent@CRDPWDUMXStack@@QEAAJPEAX0K@Z; CRDPWDUMXStack::WaitForConnectionEvent(void *,void *,ulong)
0x1800384ad  mov     edx, eax
0x1800384af  mov     rax, [rsi]
0x1800384b2  cmp     byte ptr [rax+10h], 0
0x1800384b6  jnz     loc_180038869
0x1800384bc  test    edx, edx
0x1800384be  jnz     loc_180038869
0x1800384c4  cmp     [rax+78h], edx
0x1800384c7  jl      loc_180038869
0x1800384cd  cmp     edi, 8
0x1800384d0  jb      loc_1800387E8
0x1800384d6  lea     r13, [rbx+0B8h]
0x1800384dd  cmp     dword ptr [r13+0], 1000h
0x1800384e5  jnz     loc_1800385BF
0x1800384eb  mov     r8d, [rbx+0Ch]
0x1800384ef  cmp     r8d, 10h
0x1800384f3  jz      loc_1800385B0
0x1800384f9  mov     eax, [rbx]
0x1800384fb  lea     rdx, [rbx+0D0h]
0x180038502  mov     r9d, [rbx+78h]
0x180038506  lea     rcx, [rbx+0C0h]
0x18003850d  mov     dword ptr [rsp+0C0h+var_98], eax
0x180038511  mov     rax, [rbx+0E0h]
0x180038518  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003851d  call    cs:__imp_UpdateSessionKey
0x180038523  test    eax, eax
0x180038525  jnz     loc_1800385B0
0x18003852b  mov     eax, cs:CallbackContext
0x180038531  cmp     eax, 2
0x180038534  jbe     short loc_18003858D
0x180038536  lea     rax, aSmFailedToUpda; "SM failed to update session key"
0x18003853d  mov     [rbp+47h+var_40], r14
0x180038541  mov     [rbp+47h+var_50], rax
0x180038545  lea     rdx, qword_1802AE1F0
0x18003854c  lea     rax, [rbp+47h+var_40]
0x180038550  mov     [rbp+47h+arg_0], 128h
0x180038557  mov     [rsp+0C0h+var_80], rax
0x18003855c  lea     rax, [rbp+47h+arg_0]
0x180038560  mov     [rsp+0C0h+var_88], rax
0x180038565  lea     rax, [rbp+47h+var_48]
0x180038569  mov     [rsp+0C0h+var_90], rax
0x18003856e  lea     rax, [rbp+47h+var_58]
0x180038572  mov     [rsp+0C0h+var_98], rax
0x180038577  lea     rax, [rbp+47h+var_50]
0x18003857b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180038580  mov     [rbp+47h+var_48], r15
0x180038584  mov     [rbp+47h+var_58], r12d
0x180038588  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003858d  mov     rcx, [rsi]
0x180038590  xor     r9d, r9d
0x180038593  mov     [rsp+0C0h+var_A0], 0
0x18003859b  mov     r8d, 191h
0x1800385a1  mov     edx, 1
0x1800385a6  call    WDW_LogAndDisconnect
0x1800385ab  jmp     loc_180038A7D
0x1800385b0  mov     dword ptr [r13+0], 0
0x1800385b8  lea     r13, [rbx+0B8h]
0x1800385bf  cmp     dword ptr [rbx+0Ch], 10h
0x1800385c3  jnz     loc_1800386C7
0x1800385c9  cmp     edi, 0Ch
0x1800385cc  jnb     short loc_1800385F7
0x1800385ce  mov     eax, cs:CallbackContext
0x1800385d4  cmp     eax, 2
0x1800385d7  jbe     loc_180038856
0x1800385dd  mov     [rbp+47h+var_58], 12Fh
0x1800385e4  lea     rax, aPduLenUTooShor_1; "PDU len %u too short for security conte"...
0x1800385eb  lea     rdx, word_1802AE05A
0x1800385f2  jmp     loc_180038808
0x1800385f7  mov     rcx, [rbp+47h+arg_8]
0x1800385fb  lea     edx, [rdi-0Ch]
0x1800385fe  mov     eax, [rbx+0BCh]
0x180038604  add     rcx, 0Ch
0x180038608  mov     [rbp+47h+arg_0], edx
0x18003860b  mov     r8d, edx
0x18003860e  mov     [rbp+47h+arg_8], rcx
0x180038612  mov     rdx, rcx
0x180038615  mov     dword ptr [rsp+0C0h+var_98], eax
0x180038619  lea     rsi, [rcx-8]
0x18003861d  mov     rcx, [rbx+0F8h]
0x180038624  movzx   r9d, byte ptr [rsi-1]
0x180038629  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x18003862e  call    TSFIPS_DecryptData
0x180038633  test    eax, eax
0x180038635  jz      short loc_1800386B1
0x180038637  mov     eax, cs:CallbackContext
0x18003863d  cmp     eax, 2
0x180038640  jbe     loc_18003899C
0x180038646  lea     eax, [rdi-8]
0x180038649  mov     [rbp+47h+var_58], 142h
0x180038650  mov     [rbp+47h+arg_0], eax
0x180038653  lea     rdx, byte_1802AE005
0x18003865a  lea     rax, aSmFailedToDecr; "SM failed to decrypt data: len=%u"
0x180038661  mov     [rbp+47h+var_5C], r12d
0x180038665  mov     [rbp+47h+var_50], rax
0x180038669  lea     rax, [rbp+47h+arg_0]
0x18003866d  mov     [rsp+0C0h+var_78], rax
0x180038672  lea     rax, [rbp+47h+var_40]
0x180038676  mov     [rsp+0C0h+var_80], rax
0x18003867b  lea     rax, [rbp+47h+var_58]
0x18003867f  mov     [rsp+0C0h+var_88], rax
0x180038684  lea     rax, [rbp+47h+var_48]
0x180038688  mov     [rsp+0C0h+var_90], rax
0x18003868d  lea     rax, [rbp+47h+var_5C]
0x180038691  mov     [rsp+0C0h+var_98], rax
0x180038696  lea     rax, [rbp+47h+var_50]
0x18003869a  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003869f  mov     [rbp+47h+var_48], r15
0x1800386a3  mov     [rbp+47h+var_40], r14
0x1800386a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800386ac  jmp     loc_18003899C
0x1800386b1  movzx   eax, byte ptr [rsi-1]
0x1800386b5  lea     rsi, [rbx+0B8h]
0x1800386bc  mov     edi, [rbp+47h+arg_0]
0x1800386bf  mov     r14, [rbp+47h+arg_8]
0x1800386c3  sub     edi, eax
0x1800386c5  jmp     short loc_180038746
0x1800386c7  mov     r9, [rbp+47h+arg_8]
0x1800386cb  lea     rcx, [rbx+0E8h]
0x1800386d2  mov     eax, [rbx+0BCh]
0x1800386d8  lea     rdx, [rbx+0D0h]
0x1800386df  mov     r8, [rbx+0E0h]
0x1800386e6  add     edi, 0FFFFFFF8h
0x1800386e9  mov     dword ptr [rsp+0C0h+var_78], eax
0x1800386ed  mov     eax, [rbp+47h+arg_28]
0x1800386f0  lea     rsi, [r9+8]
0x1800386f4  mov     dword ptr [rsp+0C0h+var_80], eax
0x1800386f8  mov     [rsp+0C0h+var_88], r9
0x1800386fd  mov     r9d, [rbx+78h]
0x180038701  mov     [rsp+0C0h+var_90], rcx
0x180038706  mov     ecx, [rbx]
0x180038708  mov     dword ptr [rsp+0C0h+var_98], edi
0x18003870c  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x180038711  call    cs:__imp_DecryptData
0x180038717  test    eax, eax
0x180038719  jnz     short loc_180038740
0x18003871b  mov     eax, cs:CallbackContext
0x180038721  cmp     eax, 2
0x180038724  jbe     loc_18003899C
0x18003872a  mov     [rbp+47h+arg_0], edi
0x18003872d  lea     rdx, dword_1802AE0DC
0x180038734  mov     [rbp+47h+var_58], 15Ah
0x18003873b  jmp     loc_18003865A
0x180038740  mov     r14, rsi
0x180038743  mov     rsi, r13
0x180038746  mov     eax, cs:CallbackContext
0x18003874c  cmp     eax, 5
0x18003874f  jbe     short loc_180038782
0x180038751  lea     eax, [rdi-8]
0x180038754  mov     [rbp+47h+arg_0], eax
0x180038757  lea     rdx, byte_1802AE0AB
0x18003875e  lea     rax, aDataDecryptedU; "Data decrypted: %u"
0x180038765  mov     [rbp+47h+var_40], rax
0x180038769  lea     rax, [rbp+47h+arg_0]
0x18003876d  mov     [rsp+0C0h+var_98], rax
0x180038772  lea     rax, [rbp+47h+var_40]
0x180038776  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003877b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180038780  jmp     short loc_180038785
0x180038782  mov     rsi, r13
0x180038785  mov     eax, [rbx+0B8h]
0x18003878b  inc     eax
0x18003878d  inc     dword ptr [rbx+0BCh]
0x180038793  mov     [rsi], eax
0x180038795  lea     rsi, [rbx+48h]
0x180038799  mov     r8, [rsi]
0x18003879c  mov     rcx, [r8+80h]; this
0x1800387a3  test    rcx, rcx
0x1800387a6  jz      loc_1800389B6
0x1800387ac  cmp     byte ptr [rbx+2Ch], 0
0x1800387b0  jnz     loc_1800389B6
0x1800387b6  mov     eax, [rbx+30h]
0x1800387b9  lea     rdx, qword_18026EB48
0x1800387c0  cmp     byte ptr [rax+rdx], 0
0x1800387c4  jnz     loc_1800389B6
0x1800387ca  mov     eax, [rbp+47h+arg_20]
0x1800387cd  mov     r9d, edi; unsigned int
0x1800387d0  mov     r8d, [r8+744h]; int
0x1800387d7  mov     rdx, r14; unsigned __int8 *
0x1800387da  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800387de  call    ?IM_DecodeFastPathInput@ShareClass@@QEAAXPEAEHII@Z; ShareClass::IM_DecodeFastPathInput(uchar *,int,uint,uint)
0x1800387e3  jmp     loc_180038A7D
0x1800387e8  mov     eax, cs:CallbackContext
0x1800387ee  cmp     eax, 2
0x1800387f1  jbe     short loc_180038856
0x1800387f3  mov     [rbp+47h+var_58], 169h
0x1800387fa  lea     rax, aPduLenUTooShor_0; "PDU len %u too short for security conte"...
0x180038801  lea     rdx, word_1802ADF1E
0x180038808  mov     [rbp+47h+var_50], rax
0x18003880c  lea     rax, [rbp+47h+arg_0]
0x180038810  mov     [rsp+0C0h+var_78], rax
0x180038815  lea     rax, [rbp+47h+var_40]
0x180038819  mov     [rsp+0C0h+var_80], rax
0x18003881e  lea     rax, [rbp+47h+var_58]
0x180038822  mov     [rsp+0C0h+var_88], rax
0x180038827  lea     rax, [rbp+47h+var_48]
0x18003882b  mov     [rsp+0C0h+var_90], rax
0x180038830  lea     rax, [rbp+47h+var_5C]
0x180038834  mov     [rsp+0C0h+var_98], rax
0x180038839  lea     rax, [rbp+47h+var_50]
0x18003883d  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180038842  mov     [rbp+47h+arg_0], edi
0x180038845  mov     [rbp+47h+var_40], r14
0x180038849  mov     [rbp+47h+var_48], r15
0x18003884d  mov     [rbp+47h+var_5C], r12d
0x180038851  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180038856  mov     r9, [rbp+47h+arg_8]
0x18003885a  mov     r8d, 0E0h
0x180038860  mov     [rsp+0C0h+var_A0], edi
0x180038864  jmp     loc_1800389AD
0x180038869  mov     eax, cs:CallbackContext
0x18003886f  cmp     eax, 2
0x180038872  jbe     short loc_1800388EA
0x180038874  mov     rax, [r13+0]
0x180038878  mov     [rbp+47h+var_40], r14
0x18003887c  mov     [rbp+47h+var_48], r15
0x180038880  mov     ecx, [rax+78h]
0x180038883  lea     rax, aSmDecodefastpa_0; "SM_DecodeFastPathInput: failed session "...
0x18003888a  mov     [rbp+47h+var_50], rax
0x18003888e  lea     rax, [rbp+47h+arg_0]
0x180038892  mov     [rsp+50h], rax
0x180038897  lea     rax, [rbp+47h+var_58]
0x18003889b  mov     [rsp+0C0h+var_78], rax
0x1800388a0  lea     rax, [rbp+47h+var_40]
0x1800388a4  mov     [rsp+0C0h+var_80], rax
0x1800388a9  lea     rax, [rbp+47h+var_5C]
0x1800388ad  mov     [rsp+0C0h+var_88], rax
0x1800388b2  lea     rax, [rbp+47h+var_48]
0x1800388b6  mov     [rsp+0C0h+var_90], rax
0x1800388bb  lea     rax, [rbp+47h+var_60]
0x1800388bf  mov     [rsp+0C0h+var_98], rax
  ... truncated ...
```
