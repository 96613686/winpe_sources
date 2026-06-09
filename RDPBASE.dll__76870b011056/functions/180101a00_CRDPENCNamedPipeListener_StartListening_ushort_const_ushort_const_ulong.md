# CRDPENCNamedPipeListener::StartListening(ushort const *,ushort const * *,ulong)

- ea: `0x180101a00`
- end: `0x180101bfb`
- name: `?StartListening@CRDPENCNamedPipeListener@@UEAAJPEBGPEAPEBGK@Z`
- size: `507`
- prototype: `__int64 __fastcall(CRDPENCNamedPipeListener *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18006f3dc`
- `0x180101a00`
- `0x180101f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101b5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101a51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101a51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180101b0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180101b0e`

## string_xrefs

- `0x180101a77`: `SIDs array allocation failed`
- `0x180101b7e`: `Invalid input SID`

## pseudocode

```c
__int64 __fastcall CRDPENCNamedPipeListener::StartListening(
        CRDPENCNamedPipeListener *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        unsigned int a4)
{
  _QWORD *v4; // rdi
  _QWORD *v6; // rsi
  int v10; // ebx
  HLOCAL v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  signed int started; // ebx
  const unsigned __int16 *v16; // rcx
  signed int LastError; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  const char *v22; // [rsp+50h] [rbp-20h] BYREF
  const char *v23; // [rsp+58h] [rbp-18h] BYREF
  const char *v24; // [rsp+60h] [rbp-10h] BYREF
  const char *v25; // [rsp+68h] [rbp-8h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  int v27; // [rsp+C8h] [rbp+58h] BYREF

  v4 = (_QWORD *)((char *)this + 680);
  v6 = (_QWORD *)((char *)this + 672);
  DeleteSidsArray((char *)this + 672, (char *)this + 680);
  v10 = 0;
  if ( !a4 )
  {
LABEL_10:
    started = CRDPENCNamedPipeListener::StartListeningInternal(this, a2, 0, 0);
    goto LABEL_11;
  }
  v11 = LocalAlloc(0x40u, 8LL * a4);
  *v6 = v11;
  if ( !v11 )
  {
    started = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 236;
      v22 = "SIDs array allocation failed";
      v26 = -2147024882;
      v23 = "StartListening";
      v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
      v25 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_1801C654F,
        v13,
        v14,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v23,
        (__int64)&v22);
    }
    goto LABEL_12;
  }
  while ( 1 )
  {
    v16 = a3[v10];
    if ( !v16 || !*v16 )
      goto LABEL_9;
    if ( !ConvertStringSidToSidW(v16, (PSID *)(*v6 + 8LL * *v4)) )
      break;
    ++*v4;
LABEL_9:
    if ( ++v10 >= a4 )
      goto LABEL_10;
  }
  LastError = GetLastError();
  started = LastError;
  if ( LastError > 0 )
    started = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v27 = 242;
    v25 = "Invalid input SID";
    v26 = started;
    v24 = "StartListening";
    v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v22 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)byte_1801C65A1,
      v20,
      v21,
      (__int64)&v22,
      (__int64)&v26,
      (__int64)&v23,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v25);
  }
LABEL_11:
  if ( started < 0 )
LABEL_12:
    DeleteSidsArray(v6, v4);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180101a00  mov     [rsp-38h+arg_8], rbx
0x180101a05  push    rbp
0x180101a06  push    rsi
0x180101a07  push    rdi
0x180101a08  push    r12
0x180101a0a  push    r13
0x180101a0c  push    r14
0x180101a0e  push    r15
0x180101a10  mov     rbp, rsp
0x180101a13  sub     rsp, 70h
0x180101a17  lea     rdi, [rcx+2A8h]
0x180101a1e  mov     r14d, r9d
0x180101a21  lea     rsi, [rcx+2A0h]
0x180101a28  mov     r12, rdx
0x180101a2b  mov     r15, rcx
0x180101a2e  mov     rdx, rdi
0x180101a31  mov     rcx, rsi
0x180101a34  mov     r13, r8
0x180101a37  call    DeleteSidsArray
0x180101a3c  xor     ebx, ebx
0x180101a3e  test    r14d, r14d
0x180101a41  jz      loc_180101B22
0x180101a47  mov     edx, r14d
0x180101a4a  lea     ecx, [rbx+40h]; uFlags
0x180101a4d  shl     rdx, 3; uBytes
0x180101a51  call    cs:__imp_LocalAlloc
0x180101a57  mov     [rsi], rax
0x180101a5a  test    rax, rax
0x180101a5d  jnz     loc_180101AF1
0x180101a63  mov     eax, cs:CallbackContext
0x180101a69  mov     ebx, 8007000Eh
0x180101a6e  cmp     eax, 2
0x180101a71  jbe     loc_180101B39
0x180101a77  lea     rax, aSidsArrayAlloc; "SIDs array allocation failed"
0x180101a7e  mov     [rbp+arg_18], 0ECh
0x180101a85  mov     [rbp+var_20], rax
0x180101a89  lea     rdx, byte_1801C654F
0x180101a90  lea     rax, aStartlistening_2; "StartListening"
0x180101a97  mov     [rbp+arg_0], ebx
0x180101a9a  mov     [rbp+var_18], rax
0x180101a9e  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101aa5  mov     [rbp+var_10], rax
0x180101aa9  lea     rax, aErrorCondition; "Error condition failed"
0x180101ab0  mov     [rbp+var_8], rax
0x180101ab4  lea     rax, [rbp+var_20]
0x180101ab8  mov     [rsp+70h+var_28], rax
0x180101abd  lea     rax, [rbp+var_18]
0x180101ac1  mov     [rsp+70h+var_30], rax
0x180101ac6  lea     rax, [rbp+arg_18]
0x180101aca  mov     [rsp+70h+var_38], rax
0x180101acf  lea     rax, [rbp+var_10]
0x180101ad3  mov     [rsp+70h+var_40], rax
0x180101ad8  lea     rax, [rbp+arg_0]
0x180101adc  mov     [rsp+70h+var_48], rax
0x180101ae1  lea     rax, [rbp+var_8]
0x180101ae5  mov     [rsp+70h+var_50], rax
0x180101aea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180101aef  jmp     short loc_180101B39
0x180101af1  mov     eax, ebx
0x180101af3  mov     rcx, [r13+rax*8+0]; StringSid
0x180101af8  xor     eax, eax
0x180101afa  test    rcx, rcx
0x180101afd  jz      short loc_180101B1B
0x180101aff  cmp     [rcx], ax
0x180101b02  jz      short loc_180101B1B
0x180101b04  mov     rdx, [rdi]
0x180101b07  mov     rax, [rsi]
0x180101b0a  lea     rdx, [rax+rdx*8]; Sid
0x180101b0e  call    cs:__imp_ConvertStringSidToSidW
0x180101b14  test    eax, eax
0x180101b16  jz      short loc_180101B5E
0x180101b18  inc     qword ptr [rdi]
0x180101b1b  inc     ebx
0x180101b1d  cmp     ebx, r14d
0x180101b20  jb      short loc_180101AF1
0x180101b22  xor     r9d, r9d; int
0x180101b25  xor     r8d, r8d; int
0x180101b28  mov     rdx, r12; unsigned __int16 *
0x180101b2b  mov     rcx, r15; this
0x180101b2e  call    ?StartListeningInternal@CRDPENCNamedPipeListener@@IEAAJPEBGHH@Z; CRDPENCNamedPipeListener::StartListeningInternal(ushort const *,int,int)
0x180101b33  mov     ebx, eax
0x180101b35  test    ebx, ebx
0x180101b37  jns     short loc_180101B44
0x180101b39  mov     rdx, rdi
0x180101b3c  mov     rcx, rsi
0x180101b3f  call    DeleteSidsArray
0x180101b44  mov     eax, ebx
0x180101b46  mov     rbx, [rsp+70h+arg_8]
0x180101b4e  add     rsp, 70h
0x180101b52  pop     r15
0x180101b54  pop     r14
0x180101b56  pop     r13
0x180101b58  pop     r12
0x180101b5a  pop     rdi
0x180101b5b  pop     rsi
0x180101b5c  pop     rbp
0x180101b5d  retn
0x180101b5e  call    cs:__imp_GetLastError
0x180101b64  mov     ebx, eax
0x180101b66  test    eax, eax
0x180101b68  jle     short loc_180101B73
0x180101b6a  movzx   ebx, ax
0x180101b6d  or      ebx, 80070000h
0x180101b73  mov     eax, cs:CallbackContext
0x180101b79  cmp     eax, 2
0x180101b7c  jbe     short loc_180101B35
0x180101b7e  lea     rax, aInvalidInputSi; "Invalid input SID"
0x180101b85  mov     [rbp+arg_18], 0F2h
0x180101b8c  mov     [rbp+var_8], rax
0x180101b90  lea     rdx, byte_1801C65A1
0x180101b97  lea     rax, aStartlistening_2; "StartListening"
0x180101b9e  mov     [rbp+arg_0], ebx
0x180101ba1  mov     [rbp+var_10], rax
0x180101ba5  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101bac  mov     [rbp+var_18], rax
0x180101bb0  lea     rax, aErrorCondition; "Error condition failed"
0x180101bb7  mov     [rbp+var_20], rax
0x180101bbb  lea     rax, [rbp+var_8]
0x180101bbf  mov     [rsp+70h+var_28], rax
0x180101bc4  lea     rax, [rbp+var_10]
0x180101bc8  mov     [rsp+70h+var_30], rax
0x180101bcd  lea     rax, [rbp+arg_18]
0x180101bd1  mov     [rsp+70h+var_38], rax
0x180101bd6  lea     rax, [rbp+var_18]
0x180101bda  mov     [rsp+70h+var_40], rax
0x180101bdf  lea     rax, [rbp+arg_0]
0x180101be3  mov     [rsp+70h+var_48], rax
0x180101be8  lea     rax, [rbp+var_20]
0x180101bec  mov     [rsp+70h+var_50], rax
0x180101bf1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180101bf6  jmp     loc_180101B35
```
