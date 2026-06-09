# CWebService::Initialize(void *)

- ea: `0x140007798`
- end: `0x140007a3b`
- name: `?Initialize@CWebService@@QEAAJPEAX@Z`
- size: `675`
- prototype: `__int64 __fastcall(CWebService *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14004ac94`

## callees

- `0x140007798`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1400078f6`
- `KERNEL32!CreateEventW` at `0x1400078f6`
- `KERNEL32!GetLastError` at `0x14000790c`
- `KERNEL32!GetLastError` at `0x14000790c`
- `KERNEL32!IsDebuggerPresent` at `0x140007841`
- `KERNEL32!IsDebuggerPresent` at `0x140007967`
- `KERNEL32!IsDebuggerPresent` at `0x140007841`
- `KERNEL32!IsDebuggerPresent` at `0x140007967`
- `HTTPAPI!HttpInitialize` at `0x1400077ea`
- `HTTPAPI!HttpInitialize` at `0x1400077ea`
- `webservices!WsCreateError` at `0x1400078dc`
- `webservices!WsCreateError` at `0x1400078dc`
- `WS2_32!__imp_WSAStartup` at `0x1400078af`
- `WS2_32!__imp_WSAStartup` at `0x1400078af`

## string_xrefs

- `0x14000780b`: `CWebService::Initialize`
- `0x14000792f`: `CWebService::Initialize`
- `0x140007820`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x14000793c`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007946`: `m_hEventShutdownWebService`

## pseudocode

```c
__int64 __fastcall CWebService::Initialize(CWebService *this, void *a2)
{
  signed int v4; // eax
  int Error; // ebx
  unsigned int v6; // r15d
  int v7; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  WSAData WSAData; // [rsp+50h] [rbp-1E8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  *((_QWORD *)this + 27) = a2;
  v4 = HttpInitialize((HTTPAPI_VERSION)1, 2u, 0);
  Error = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      Error = (unsigned __int16)v4 | 0x80070000;
    v6 = 116;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
      v6,
      L"CWebService::Initialize",
      L"CBRAEx",
      L"retCode == 0L",
      Error);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        v6,
        L"CWebService::Initialize",
        L"CBRAEx",
        L"retCode == 0L",
        Error,
        1);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        v6,
        L"CWebService::Initialize",
        L"CBRAEx",
        L"retCode == 0L",
        Error);
    return (unsigned int)Error;
  }
  *((_DWORD *)this + 4) = 1;
  v7 = WSAStartup(0x202u, &WSAData);
  Error = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      Error = (unsigned __int16)v7 | 0x80070000;
    v6 = 120;
    goto LABEL_5;
  }
  *((_DWORD *)this + 5) = 1;
  Error = WsCreateError(0, 0, (WS_ERROR **)this + 3);
  if ( Error >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 26) = EventW;
    if ( EventW )
    {
      *((_DWORD *)this + 8) = 0;
      *((_DWORD *)this + 12) = 8;
      *((_QWORD *)this + 5) = (char *)this + 152;
      *((_QWORD *)this + 19) = CWebService::AcceptChannelCallback;
      *((_QWORD *)this + 8) = (char *)this + 160;
      *((_QWORD *)this + 20) = CWebService::CloseChannelCallback;
      *((_DWORD *)this + 14) = 1;
      *((_QWORD *)this + 11) = &CWebService::s_kcbBodyHeapMaxSize;
      *((_QWORD *)this + 14) = &CWebService::s_kcbMaxMessageSize;
      *((_QWORD *)this + 17) = &CWebService::s_fEnableTimeouts;
      *((_DWORD *)this + 18) = 8;
      *((_DWORD *)this + 20) = 4;
      *((_DWORD *)this + 24) = 8;
      *((_DWORD *)this + 26) = 0;
      *((_DWORD *)this + 30) = 4;
      *((_DWORD *)this + 32) = 17;
      *((_DWORD *)this + 36) = 4;
    }
    else
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      if ( Error >= 0 )
        Error = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        0x81u,
        L"CWebService::Initialize",
        L"CBRAEx",
        L"m_hEventShutdownWebService",
        Error);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
          129,
          L"CWebService::Initialize",
          L"CBRAEx",
          L"m_hEventShutdownWebService",
          Error,
          1);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
          129,
          L"CWebService::Initialize",
          L"CBRAEx",
          L"m_hEventShutdownWebService",
          Error);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140007798  push    rbx
0x14000779a  push    rbp
0x14000779b  push    rsi
0x14000779c  push    rdi
0x14000779d  push    r14
0x14000779f  push    r15
0x1400077a1  sub     rsp, 208h
0x1400077a8  mov     rax, cs:__security_cookie
0x1400077af  xor     rax, rsp
0x1400077b2  mov     [rsp+238h+var_48], rax
0x1400077ba  mov     rbx, rdx
0x1400077bd  mov     rdi, rcx
0x1400077c0  mov     esi, 1
0x1400077c5  lea     rcx, [rsp+238h+WSAData]; void *
0x1400077ca  xor     edx, edx; Val
0x1400077cc  mov     [rsp+238h+var_1F8], esi
0x1400077d0  mov     r8d, 198h; Size
0x1400077d6  call    memset_0
0x1400077db  xor     r8d, r8d; pReserved
0x1400077de  mov     [rdi+0D8h], rbx
0x1400077e5  lea     edx, [rsi+1]; Flags
0x1400077e8  mov     ecx, esi; Version
0x1400077ea  call    cs:__imp_HttpInitialize
0x1400077f0  mov     ebx, eax
0x1400077f2  test    eax, eax
0x1400077f4  jz      loc_1400078A2
0x1400077fa  jle     short loc_140007805
0x1400077fc  movzx   ebx, ax
0x1400077ff  or      ebx, 80070000h
0x140007805  mov     r15d, 74h ; 't'
0x14000780b  lea     rsi, aCwebserviceIni; "CWebService::Initialize"
0x140007812  mov     [rsp+238h+var_210], ebx; int
0x140007816  lea     rbp, aCbraex; "CBRAEx"
0x14000781d  mov     r8, rsi; unsigned __int16 *
0x140007820  lea     rdi, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007827  mov     r9, rbp; unsigned __int16 *
0x14000782a  lea     r14, aRetcode0l; "retCode == 0L"
0x140007831  mov     rcx, rdi; unsigned __int16 *
0x140007834  mov     edx, r15d; unsigned int
0x140007837  mov     [rsp+238h+var_218], r14; unsigned __int16 *
0x14000783c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007841  call    cs:__imp_IsDebuggerPresent
0x140007847  test    eax, eax
0x140007849  jz      short loc_14000787A
0x14000784b  mov     [rsp+238h+var_200], ebx
0x14000784f  mov     r9d, r15d
0x140007852  mov     [rsp+238h+var_208], r14
0x140007857  mov     qword ptr [rsp+238h+var_210], rbp
0x14000785c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007863  mov     r8, rdi
0x140007866  mov     [rsp+238h+var_218], rsi
0x14000786b  mov     ecx, 2; unsigned __int8
0x140007870  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007875  jmp     loc_140007A19
0x14000787a  mov     dword ptr [rsp+238h+var_208], ebx
0x14000787e  mov     r8d, r15d
0x140007881  mov     qword ptr [rsp+238h+var_210], r14
0x140007886  mov     r9, rsi
0x140007889  mov     [rsp+238h+var_218], rbp
0x14000788e  mov     rdx, rdi
0x140007891  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007898  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000789d  jmp     loc_140007A19
0x1400078a2  mov     ecx, 202h; wVersionRequested
0x1400078a7  mov     [rdi+10h], esi
0x1400078aa  lea     rdx, [rsp+238h+WSAData]; lpWSAData
0x1400078af  call    cs:__imp_WSAStartup
0x1400078b5  mov     ebx, eax
0x1400078b7  test    eax, eax
0x1400078b9  jz      short loc_1400078D1
0x1400078bb  jle     short loc_1400078C6
0x1400078bd  movzx   ebx, ax
0x1400078c0  or      ebx, 80070000h
0x1400078c6  mov     r15d, 78h ; 'x'
0x1400078cc  jmp     loc_14000780B
0x1400078d1  lea     r8, [rdi+18h]; error
0x1400078d5  mov     [rdi+14h], esi
0x1400078d8  xor     edx, edx; propertyCount
0x1400078da  xor     ecx, ecx; properties
0x1400078dc  call    cs:__imp_WsCreateError
0x1400078e2  mov     ebx, eax
0x1400078e4  test    eax, eax
0x1400078e6  js      loc_140007A19
0x1400078ec  xor     r9d, r9d; lpName
0x1400078ef  xor     r8d, r8d; bInitialState
0x1400078f2  mov     edx, esi; bManualReset
0x1400078f4  xor     ecx, ecx; lpEventAttributes
0x1400078f6  call    cs:__imp_CreateEventW
0x1400078fc  mov     [rdi+0D0h], rax
0x140007903  test    rax, rax
0x140007906  jnz     loc_140007993
0x14000790c  call    cs:__imp_GetLastError
0x140007912  mov     ebx, eax
0x140007914  test    eax, eax
0x140007916  jle     short loc_140007921
0x140007918  movzx   ebx, ax
0x14000791b  or      ebx, 80070000h
0x140007921  mov     eax, 80004005h
0x140007926  lea     rbp, aCbraex; "CBRAEx"
0x14000792d  test    ebx, ebx
0x14000792f  lea     rsi, aCwebserviceIni; "CWebService::Initialize"
0x140007936  mov     r14d, 81h
0x14000793c  lea     rdi, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007943  cmovns  ebx, eax
0x140007946  lea     r15, aMHeventshutdow; "m_hEventShutdownWebService"
0x14000794d  mov     [rsp+238h+var_210], ebx; int
0x140007951  mov     r9, rbp; unsigned __int16 *
0x140007954  mov     r8, rsi; unsigned __int16 *
0x140007957  mov     [rsp+238h+var_218], r15; unsigned __int16 *
0x14000795c  mov     edx, r14d; unsigned int
0x14000795f  mov     rcx, rdi; unsigned __int16 *
0x140007962  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007967  call    cs:__imp_IsDebuggerPresent
0x14000796d  test    eax, eax
0x14000796f  jz      short loc_140007982
0x140007971  mov     [rsp+238h+var_200], ebx
0x140007975  mov     r9d, r14d
0x140007978  mov     [rsp+238h+var_208], r15
0x14000797d  jmp     loc_140007857
0x140007982  mov     dword ptr [rsp+238h+var_208], ebx
0x140007986  mov     r8d, r14d
0x140007989  mov     qword ptr [rsp+238h+var_210], r15
0x14000798e  jmp     loc_140007886
0x140007993  mov     edx, 8
0x140007998  mov     dword ptr [rdi+20h], 0
0x14000799f  lea     rax, [rdi+98h]
0x1400079a6  mov     [rdi+30h], edx
0x1400079a9  mov     [rdi+28h], rax
0x1400079ad  lea     rcx, ?AcceptChannelCallback@CWebService@@CAJPEBU_WS_OPERATION_CONTEXT@@PEAPEAXPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; CWebService::AcceptChannelCallback(_WS_OPERATION_CONTEXT const *,void * *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)
0x1400079b4  mov     [rax], rcx
0x1400079b7  lea     rax, [rdi+0A0h]
0x1400079be  mov     [rdi+40h], rax
0x1400079c2  lea     rcx, ?CloseChannelCallback@CWebService@@CAJPEBU_WS_OPERATION_CONTEXT@@PEBU_WS_ASYNC_CONTEXT@@@Z; CWebService::CloseChannelCallback(_WS_OPERATION_CONTEXT const *,_WS_ASYNC_CONTEXT const *)
0x1400079c9  mov     [rax], rcx
0x1400079cc  lea     ecx, [rdx-4]
0x1400079cf  lea     rax, ?s_kcbBodyHeapMaxSize@CWebService@@0_KA; unsigned __int64 CWebService::s_kcbBodyHeapMaxSize
0x1400079d6  mov     [rdi+38h], esi
0x1400079d9  mov     [rdi+58h], rax
0x1400079dd  lea     rax, ?s_kcbMaxMessageSize@CWebService@@0KA; ulong CWebService::s_kcbMaxMessageSize
0x1400079e4  mov     [rdi+70h], rax
0x1400079e8  lea     rax, ?s_fEnableTimeouts@CWebService@@0HA; int CWebService::s_fEnableTimeouts
0x1400079ef  mov     [rdi+88h], rax
0x1400079f6  mov     [rdi+48h], edx
0x1400079f9  mov     [rdi+50h], ecx
0x1400079fc  mov     [rdi+60h], edx
0x1400079ff  mov     dword ptr [rdi+68h], 0
0x140007a06  mov     [rdi+78h], ecx
0x140007a09  mov     dword ptr [rdi+80h], 11h
0x140007a13  mov     [rdi+90h], ecx
0x140007a19  mov     eax, ebx
0x140007a1b  mov     rcx, [rsp+238h+var_48]
0x140007a23  xor     rcx, rsp; StackCookie
0x140007a26  call    __security_check_cookie
0x140007a2b  add     rsp, 208h
0x140007a32  pop     r15
0x140007a34  pop     r14
0x140007a36  pop     rdi
0x140007a37  pop     rsi
0x140007a38  pop     rbp
0x140007a39  pop     rbx
0x140007a3a  retn
```
