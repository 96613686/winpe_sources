# CRDPWDUMXStack::IsSecureInputEnabled(int *)

- ea: `0x180120aa0`
- end: `0x18012119f`
- name: `?IsSecureInputEnabled@CRDPWDUMXStack@@IEAAJPEAH@Z`
- size: `1791`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18012d824`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x18007e9e0`
- `0x180120aa0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180120e20`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180121094`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012113b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180120e20`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180121094`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012113b`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::IsSecureInputEnabled(CRDPWDUMXStack *this, unsigned int *a2)
{
  int v4; // ebx
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const char *v14; // rcx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rcx
  unsigned int v20; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+5Ch] [rbp-ACh] BYREF
  const char *v22; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-98h] BYREF
  const char *v25; // [rsp+80h] [rbp-88h] BYREF
  const char *v26; // [rsp+88h] [rbp-80h] BYREF
  const char *v27; // [rsp+90h] [rbp-78h] BYREF
  int v28; // [rsp+98h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-60h] BYREF
  char *v31; // [rsp+B8h] [rbp-50h]
  int v32; // [rsp+C0h] [rbp-48h]
  int v33; // [rsp+C4h] [rbp-44h]
  const char *v34; // [rsp+C8h] [rbp-40h]
  __int64 v35; // [rsp+D0h] [rbp-38h]
  unsigned int *v36; // [rsp+D8h] [rbp-30h]
  __int64 v37; // [rsp+E0h] [rbp-28h]
  const char *v38; // [rsp+E8h] [rbp-20h]
  __int64 v39; // [rsp+F0h] [rbp-18h]
  const char **v40; // [rsp+F8h] [rbp-10h]
  __int64 v41; // [rsp+100h] [rbp-8h]
  const char *v42; // [rsp+108h] [rbp+0h]
  __int64 v43; // [rsp+110h] [rbp+8h]
  const char *v44; // [rsp+118h] [rbp+10h]
  __int64 v45; // [rsp+120h] [rbp+18h]

  v29 = 0;
  v28 = 0;
  LODWORD(v23) = 0;
  if ( !*((_QWORD *)this + 78) )
  {
    v4 = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      EventDescriptor.Keyword = 0;
      v44 = "m_spPlatformContext is NULL";
      LODWORD(v22) = 6429;
      v40 = &v22;
      v21 = -2147024809;
      v36 = &v21;
      v45 = 28;
      v34 = "Error condition failed";
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1802BB1B8;
      v42 = "IsSecureInputEnabled";
      v43 = 21;
      v41 = 4;
      v38 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v39 = 61;
      v37 = 4;
      v35 = 23;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = (unsigned __int16)*off_1802BB1B8;
      v31 = byte_18028E655;
      UserData.Reserved = 2;
      v32 = 72;
      v33 = 1;
      v20 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
    }
    goto LABEL_30;
  }
  *a2 = 0;
  v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 78))(
         *((_QWORD *)this + 78),
         &IID_IRDPCollection,
         &v29);
  v4 = v5;
  if ( v5 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 6433;
      v22 = "Failed to QI for RDP Collection from Platfornm Context";
      v25 = "IsSecureInputEnabled";
      v27 = "Error HResult failed";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v21 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1802903DD,
        v6,
        v7,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)&v22);
    }
    goto LABEL_30;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v29 + 32LL))(
         v29,
         L"IsSecureInputEnabled",
         &v23);
  if ( v4 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = "IsSecureInputEnabled";
      v25 = "Failed to get secure input BRS property";
      v20 = 6438;
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v21 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (unsigned int)word_18028DABA,
        v9,
        v10,
        (__int64)&v25,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v27);
    }
    LODWORD(v23) = 0;
    v4 = 0;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v20 = v23;
    EventDescriptor.Keyword = 0;
    v36 = &v20;
    v37 = 4;
    v34 = "BRS secure input";
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_1802BB1B8;
    v35 = 17;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = (unsigned __int16)*off_1802BB1B8;
    v31 = (char *)&dword_18028C4BC;
    UserData.Reserved = 2;
    v32 = 57;
    v33 = 1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  if ( (_DWORD)v23 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v29 + 40LL))(
           v29,
           L"ReverseConnectMode",
           &v28) >= 0
      && v28 )
    {
      v22 = 0;
      v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, const char **))this + 78))(
             *((_QWORD *)this + 78),
             &IID_IRDPENCPlatformContext,
             &v22);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(const char *, const wchar_t *, unsigned int *))(*(_QWORD *)v22 + 32LL))(
               v22,
               L"WVD::AVDStackEnableKeyboardProtection",
               a2);
        if ( v4 >= 0 )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            v20 = *a2;
            EventDescriptor.Keyword = 0;
            v36 = &v20;
            v37 = 4;
            v34 = "WVD Enable keyboard protection ";
            *(_DWORD *)&EventDescriptor.Level = 4;
            UserData.Ptr = (ULONGLONG)off_1802BB1B8;
            v35 = 32;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            UserData.Size = (unsigned __int16)*off_1802BB1B8;
            v31 = (char *)word_18028F9F2;
            UserData.Reserved = 2;
            v32 = 47;
            v33 = 1;
            v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = "IsSecureInputEnabled";
          *(_QWORD *)&EventDescriptor.Id = "Get WVD property failed";
          v20 = 6459;
          v25 = "Error HResult failed";
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v21 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)byte_18028E43B,
            v16,
            v17,
            (__int64)&v25,
            (__int64)&v21,
            (__int64)&v26,
            (__int64)&v20,
            (__int64)&v27,
            (__int64)&EventDescriptor);
        }
        v14 = v22;
        if ( v22 )
          goto LABEL_20;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v26 = "IsSecureInputEnabled";
          v27 = "m_spPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) failed";
          v20 = 6456;
          *(_QWORD *)&EventDescriptor.Id = "Error HResult failed";
          v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v21 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v11,
            (unsigned int)byte_18028E52B,
            v12,
            v13,
            (__int64)&EventDescriptor,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v20,
            (__int64)&v26,
            (__int64)&v27);
        }
        v14 = v22;
        if ( v22 )
        {
LABEL_20:
          v22 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      v35 = 82;
      v34 = "Not in reverse connect mode, Secure Input can only be enabled for WVD connections";
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_1802BB1B8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_1802BB1B8;
      v31 = byte_18028EBE3;
      UserData.Reserved = 2;
      v32 = 28;
      v33 = 1;
      v20 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
LABEL_30:
  v18 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180120aa0  mov     r11, rsp
0x180120aa3  push    rbp
0x180120aa4  push    rbx
0x180120aa5  push    r14
0x180120aa7  lea     rbp, [r11-68h]
0x180120aab  sub     rsp, 150h
0x180120ab2  mov     rax, cs:__security_cookie
0x180120ab9  xor     rax, rsp
0x180120abc  mov     [rbp+60h+var_40], rax
0x180120ac0  mov     [r11+18h], rsi
0x180120ac4  xor     r14d, r14d
0x180120ac7  mov     [r11-20h], rdi
0x180120acb  mov     [r11-28h], r12
0x180120acf  mov     r12, rdx
0x180120ad2  mov     [r11-30h], r13
0x180120ad6  mov     [r11-38h], r15
0x180120ada  mov     r15, rcx
0x180120add  mov     [rbp+60h+var_C8], r14
0x180120ae1  mov     [rbp+60h+var_D0], r14d
0x180120ae5  mov     dword ptr [rsp+160h+var_100], r14d
0x180120aea  cmp     [rcx+270h], r14
0x180120af1  jnz     loc_180120BFE
0x180120af7  mov     eax, cs:CallbackContext
0x180120afd  mov     ebx, 80070057h
0x180120b02  cmp     eax, 2
0x180120b05  jbe     loc_180121144
0x180120b0b  mov     [rsp+160h+EventDescriptor.Keyword], r14
0x180120b10  lea     rax, aMSpplatformcon_1; "m_spPlatformContext is NULL"
0x180120b17  mov     [rbp+60h+var_50], rax
0x180120b1b  lea     rdi, aIssecureinpute_0; "IsSecureInputEnabled"
0x180120b22  lea     rax, [rsp+160h+var_108]
0x180120b27  mov     dword ptr [rsp+160h+var_108], 191Dh
0x180120b2f  mov     [rbp+60h+var_70], rax
0x180120b33  lea     rsi, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180120b3a  lea     rax, [rsp+160h+var_110+4]
0x180120b3f  mov     dword ptr [rsp+160h+var_110+4], ebx
0x180120b43  mov     [rbp+60h+var_90], rax
0x180120b47  lea     r14, _TraceLoggingMetadataEnd
0x180120b4e  lea     rax, aErrorCondition; "Error condition failed"
0x180120b55  mov     [rbp+60h+var_48], 1Ch
0x180120b5d  mov     [rbp+60h+var_A0], rax
0x180120b61  lea     r13, _TraceLoggingMetadata
0x180120b68  movzx   eax, cs:word_18028E64B
0x180120b6f  sub     r14d, r13d
0x180120b72  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x180120b76  mov     rax, cs:off_1802BB1B8
0x180120b7d  mov     [rbp+60h+var_C0.Ptr], rax
0x180120b81  mov     [rbp+60h+var_60], rdi
0x180120b85  mov     [rbp+60h+var_58], 15h
0x180120b8d  mov     [rbp+60h+var_68], 4
0x180120b95  mov     [rbp+60h+var_80], rsi
0x180120b99  mov     [rbp+60h+var_78], 3Dh ; '='
0x180120ba1  mov     [rbp+60h+var_88], 4
0x180120ba9  mov     [rbp+60h+var_98], 17h
0x180120bb1  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x180120bb9  movzx   eax, word ptr [rax]
0x180120bbc  mov     [rbp+60h+var_C0.Size], eax
0x180120bbf  lea     rax, byte_18028E655
0x180120bc6  mov     [rbp+60h+var_B0], rax
0x180120bca  mov     dword ptr [rbp+60h+var_C0.0Ch], 2
0x180120bd1  mov     [rbp+60h+var_A8], 48h ; 'H'
0x180120bd8  mov     [rbp+60h+var_A4], 1
0x180120bdf  mov     dword ptr [rsp+160h+var_110], r14d
0x180120be4  mov     eax, dword ptr [rsp+160h+var_110]
0x180120be8  lea     rax, [rbp+60h+var_C0]
0x180120bec  mov     [rsp+160h+UserData], rax
0x180120bf1  mov     [rsp+160h+UserDataCount], 8
0x180120bf9  jmp     loc_180121129
0x180120bfe  mov     [rdx], r14d
0x180120c01  lea     r8, [rbp+60h+var_C8]
0x180120c05  mov     rcx, [rcx+270h]
0x180120c0c  lea     rdx, IID_IRDPCollection
0x180120c13  mov     rax, [rcx]
0x180120c16  mov     rax, [rax]
0x180120c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120c1e  mov     ebx, eax
0x180120c20  test    eax, eax
0x180120c22  jns     loc_180120CBC
0x180120c28  mov     ecx, cs:CallbackContext
0x180120c2e  cmp     ecx, 2
0x180120c31  jbe     loc_180121144
0x180120c37  lea     rax, aFailedToQiForR_0; "Failed to QI for RDP Collection from Pl"...
0x180120c3e  mov     dword ptr [rsp+160h+var_110], 1921h
0x180120c46  mov     [rsp+160h+var_108], rax
0x180120c4b  lea     rdi, aIssecureinpute_0; "IsSecureInputEnabled"
0x180120c52  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180120c59  mov     [rsp+160h+var_E8], rdi
0x180120c5e  mov     [rbp+60h+var_D8], rax
0x180120c62  lea     rsi, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180120c69  lea     rax, [rsp+160h+var_108]
0x180120c6e  mov     [rbp+60h+var_E0], rsi
0x180120c72  mov     qword ptr [rsp+160h+var_118], rax
0x180120c77  lea     rdx, byte_1802903DD
0x180120c7e  lea     rax, [rsp+160h+var_E8]
0x180120c83  mov     dword ptr [rsp+160h+var_110+4], ebx
0x180120c87  mov     [rsp+160h+var_120], rax
0x180120c8c  lea     rax, [rsp+160h+var_110]
0x180120c91  mov     [rsp+160h+var_128], rax
0x180120c96  lea     rax, [rbp+60h+var_E0]
0x180120c9a  mov     [rsp+160h+var_130], rax
0x180120c9f  lea     rax, [rsp+160h+var_110+4]
0x180120ca4  mov     [rsp+160h+UserData], rax
0x180120ca9  lea     rax, [rbp+60h+var_D8]
0x180120cad  mov     qword ptr [rsp+160h+UserDataCount], rax
0x180120cb2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180120cb7  jmp     loc_180121144
0x180120cbc  mov     rcx, [rbp+60h+var_C8]
0x180120cc0  lea     r8, [rsp+160h+var_100]
0x180120cc5  lea     rdx, aIssecureinpute; "IsSecureInputEnabled"
0x180120ccc  mov     rax, [rcx]
0x180120ccf  mov     rax, [rax+20h]
0x180120cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120cd8  lea     rdi, aIssecureinpute_0; "IsSecureInputEnabled"
0x180120cdf  mov     ebx, eax
0x180120ce1  lea     rsi, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180120ce8  test    eax, eax
0x180120cea  jns     short loc_180120D5B
0x180120cec  mov     eax, cs:CallbackContext
0x180120cf2  cmp     eax, 2
0x180120cf5  jbe     short loc_180120D53
0x180120cf7  lea     rax, aFailedToGetSec; "Failed to get secure input BRS property"
0x180120cfe  mov     [rbp+60h+var_D8], rdi
0x180120d02  mov     [rsp+160h+var_E8], rax
0x180120d07  lea     rdx, word_18028DABA
0x180120d0e  lea     rax, [rbp+60h+var_D8]
0x180120d12  mov     dword ptr [rsp+160h+var_110], 1926h
0x180120d1a  mov     [rsp+160h+var_120], rax
0x180120d1f  lea     rax, [rsp+160h+var_110]
0x180120d24  mov     [rsp+160h+var_128], rax
0x180120d29  lea     rax, [rbp+60h+var_E0]
0x180120d2d  mov     [rsp+160h+var_130], rax
0x180120d32  lea     rax, [rsp+160h+var_110+4]
0x180120d37  mov     [rsp+160h+UserData], rax
0x180120d3c  lea     rax, [rsp+160h+var_E8]
0x180120d41  mov     qword ptr [rsp+160h+UserDataCount], rax
0x180120d46  mov     [rbp+60h+var_E0], rsi
0x180120d4a  mov     dword ptr [rsp+160h+var_110+4], ebx
0x180120d4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180120d53  mov     dword ptr [rsp+160h+var_100], r14d
0x180120d58  mov     ebx, r14d
0x180120d5b  mov     eax, cs:CallbackContext
0x180120d61  lea     r14, _TraceLoggingMetadataEnd
0x180120d68  lea     r13, _TraceLoggingMetadata
0x180120d6f  cmp     eax, 4
0x180120d72  jbe     loc_180120E26
0x180120d78  mov     eax, dword ptr [rsp+160h+var_100]
0x180120d7c  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x180120d81  mov     dword ptr [rsp+160h+var_110], eax
0x180120d85  xor     ecx, ecx
0x180120d87  mov     [rsp+160h+EventDescriptor.Keyword], rcx
0x180120d8c  lea     rax, [rsp+160h+var_110]
0x180120d91  mov     [rbp+60h+var_90], rax
0x180120d95  xor     r9d, r9d; RelatedActivityId
0x180120d98  lea     rax, aBrsSecureInput; "BRS secure input"
0x180120d9f  mov     [rbp+60h+var_88], 4
0x180120da7  mov     [rbp+60h+var_A0], rax
0x180120dab  xor     r8d, r8d; ActivityId
0x180120dae  movzx   eax, cs:word_18028C4B2
0x180120db5  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x180120db9  mov     rax, cs:off_1802BB1B8
0x180120dc0  mov     [rbp+60h+var_C0.Ptr], rax
0x180120dc4  mov     [rbp+60h+var_98], 11h
0x180120dcc  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x180120dd4  movzx   eax, word ptr [rax]
0x180120dd7  mov     [rbp+60h+var_C0.Size], eax
0x180120dda  lea     rax, dword_18028C4BC
0x180120de1  mov     [rbp+60h+var_B0], rax
0x180120de5  mov     rax, r14
0x180120de8  sub     eax, r13d
0x180120deb  mov     dword ptr [rbp+60h+var_C0.0Ch], 2
0x180120df2  mov     [rbp+60h+var_A8], 39h ; '9'
0x180120df9  mov     [rbp+60h+var_A4], 1
0x180120e00  mov     dword ptr [rsp+160h+var_110+4], eax
0x180120e04  mov     eax, dword ptr [rsp+160h+var_110+4]
0x180120e08  mov     rcx, cs:RegHandle; RegHandle
0x180120e0f  lea     rax, [rbp+60h+var_C0]
0x180120e13  mov     [rsp+160h+UserData], rax; UserData
0x180120e18  mov     [rsp+160h+UserDataCount], 4; UserDataCount
0x180120e20  call    cs:__imp_EventWriteTransfer
0x180120e26  cmp     dword ptr [rsp+160h+var_100], 0
0x180120e2b  jz      loc_180121141
0x180120e31  mov     rcx, [rbp+60h+var_C8]
0x180120e35  lea     r8, [rbp+60h+var_D0]
0x180120e39  lea     rdx, aReverseconnect_1; "ReverseConnectMode"
0x180120e40  mov     rax, [rcx]
0x180120e43  mov     rax, [rax+28h]
0x180120e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e4c  test    eax, eax
0x180120e4e  js      loc_18012109F
0x180120e54  cmp     [rbp+60h+var_D0], 0
0x180120e58  jz      loc_18012109F
0x180120e5e  xor     ecx, ecx
0x180120e60  lea     r8, [rsp+160h+var_108]
0x180120e65  mov     [rsp+160h+var_108], rcx
0x180120e6a  lea     rdx, IID_IRDPENCPlatformContext
0x180120e71  mov     rcx, [r15+270h]
0x180120e78  mov     rax, [rcx]
0x180120e7b  mov     rax, [rax]
0x180120e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e83  mov     ebx, eax
0x180120e85  test    eax, eax
0x180120e87  jns     loc_180120F31
0x180120e8d  mov     eax, cs:CallbackContext
0x180120e93  cmp     eax, 2
0x180120e96  jbe     short loc_180120F0A
0x180120e98  lea     rax, aMSpplatformcon_0; "m_spPlatformContext->QueryInterface(IID"...
0x180120e9f  mov     [rbp+60h+var_E0], rdi
0x180120ea3  mov     [rbp+60h+var_D8], rax
0x180120ea7  lea     rdx, byte_18028E52B
0x180120eae  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180120eb5  mov     dword ptr [rsp+160h+var_110], 1938h
0x180120ebd  mov     qword ptr [rsp+160h+EventDescriptor.Id], rax
0x180120ec2  lea     rax, [rbp+60h+var_D8]
0x180120ec6  mov     qword ptr [rsp+160h+var_118], rax
0x180120ecb  lea     rax, [rbp+60h+var_E0]
0x180120ecf  mov     [rsp+160h+var_120], rax
0x180120ed4  lea     rax, [rsp+160h+var_110]
0x180120ed9  mov     [rsp+160h+var_128], rax
0x180120ede  lea     rax, [rsp+160h+var_E8]
0x180120ee3  mov     [rsp+160h+var_130], rax
0x180120ee8  lea     rax, [rsp+160h+var_110+4]
0x180120eed  mov     [rsp+160h+UserData], rax
0x180120ef2  lea     rax, [rsp+160h+EventDescriptor]
0x180120ef7  mov     qword ptr [rsp+160h+UserDataCount], rax
0x180120efc  mov     [rsp+160h+var_E8], rsi
0x180120f01  mov     dword ptr [rsp+160h+var_110+4], ebx
0x180120f05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180120f0a  mov     rcx, [rsp+160h+var_108]
0x180120f0f  test    rcx, rcx
0x180120f12  jz      loc_180121141
0x180120f18  xor     r14d, r14d
0x180120f1b  mov     [rsp+160h+var_108], r14
0x180120f20  mov     rax, [rcx]
0x180120f23  mov     rax, [rax+10h]
0x180120f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f2c  jmp     loc_180121144
0x180120f31  mov     rcx, [rsp+160h+var_108]
0x180120f36  lea     rdx, aWvdAvdstackena; "WVD::AVDStackEnableKeyboardProtection"
0x180120f3d  mov     r8, r12
0x180120f40  mov     rax, [rcx]
0x180120f43  mov     rax, [rax+20h]
0x180120f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f4c  mov     ebx, eax
0x180120f4e  test    eax, eax
0x180120f50  mov     eax, cs:CallbackContext
0x180120f56  jns     loc_180120FE9
0x180120f5c  cmp     eax, 2
0x180120f5f  jbe     short loc_180120FD3
0x180120f61  lea     rax, aGetWvdProperty; "Get WVD property failed"
0x180120f68  mov     [rbp+60h+var_D8], rdi
0x180120f6c  mov     qword ptr [rsp+160h+EventDescriptor.Id], rax
0x180120f71  lea     rdx, byte_18028E43B
0x180120f78  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180120f7f  mov     dword ptr [rsp+160h+var_110], 193Bh
0x180120f87  mov     [rsp+160h+var_E8], rax
0x180120f8c  lea     rax, [rsp+160h+EventDescriptor]
0x180120f91  mov     qword ptr [rsp+160h+var_118], rax
0x180120f96  lea     rax, [rbp+60h+var_D8]
0x180120f9a  mov     [rsp+160h+var_120], rax
0x180120f9f  lea     rax, [rsp+160h+var_110]
0x180120fa4  mov     [rsp+160h+var_128], rax
0x180120fa9  lea     rax, [rbp+60h+var_E0]
0x180120fad  mov     [rsp+160h+var_130], rax
0x180120fb2  lea     rax, [rsp+160h+var_110+4]
0x180120fb7  mov     [rsp+160h+UserData], rax
0x180120fbc  lea     rax, [rsp+160h+var_E8]
0x180120fc1  mov     qword ptr [rsp+160h+UserDataCount], rax
0x180120fc6  mov     [rbp+60h+var_E0], rsi
0x180120fca  mov     dword ptr [rsp+160h+var_110+4], ebx
0x180120fce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180120fd3  mov     rcx, [rsp+160h+var_108]
0x180120fd8  xor     r14d, r14d
0x180120fdb  test    rcx, rcx
0x180120fde  jz      loc_180121144
0x180120fe4  jmp     loc_180120F1B
0x180120fe9  cmp     eax, 4
0x180120fec  jbe     short loc_180120FD3
0x180120fee  mov     eax, [r12]
0x180120ff2  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x180120ff7  mov     dword ptr [rsp+160h+var_110], eax
0x180120ffb  xor     ecx, ecx
0x180120ffd  mov     [rsp+160h+EventDescriptor.Keyword], rcx
0x180121002  lea     rax, [rsp+160h+var_110]
0x180121007  mov     [rbp+60h+var_90], rax
0x18012100b  sub     r14d, r13d
0x18012100e  lea     rax, aWvdEnableKeybo; "WVD Enable keyboard protection "
0x180121015  mov     [rbp+60h+var_88], 4
0x18012101d  mov     [rbp+60h+var_A0], rax
0x180121021  xor     r9d, r9d; RelatedActivityId
0x180121024  movzx   eax, cs:word_18028F9E8
0x18012102b  xor     r8d, r8d; ActivityId
0x18012102e  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x180121032  mov     rax, cs:off_1802BB1B8
0x180121039  mov     [rbp+60h+var_C0.Ptr], rax
0x18012103d  mov     [rbp+60h+var_98], 20h ; ' '
0x180121045  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x18012104d  movzx   eax, word ptr [rax]
0x180121050  mov     [rbp+60h+var_C0.Size], eax
0x180121053  lea     rax, word_18028F9F2
0x18012105a  mov     [rbp+60h+var_B0], rax
  ... truncated ...
```
