# CClientNotificationSink::Initialize(IWSDiscoveryProvider *)

- ea: `0x14007ae24`
- end: `0x14007b056`
- name: `?Initialize@CClientNotificationSink@@QEAAJPEAUIWSDiscoveryProvider@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CClientNotificationSink *__hidden this, struct IWSDiscoveryProvider *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14007a7ac`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007ae24`
- `0x14007c3c4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14007aec1`
- `KERNEL32!CreateEventW` at `0x14007af87`
- `KERNEL32!CreateEventW` at `0x14007aec1`
- `KERNEL32!CreateEventW` at `0x14007af87`
- `KERNEL32!GetLastError` at `0x14007aed4`
- `KERNEL32!GetLastError` at `0x14007af96`
- `KERNEL32!GetLastError` at `0x14007aed4`
- `KERNEL32!GetLastError` at `0x14007af96`
- `KERNEL32!IsDebuggerPresent` at `0x14007af2a`
- `KERNEL32!IsDebuggerPresent` at `0x14007b002`
- `KERNEL32!IsDebuggerPresent` at `0x14007af2a`
- `KERNEL32!IsDebuggerPresent` at `0x14007b002`

## string_xrefs

- `0x14007ae55`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007af0d`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007af45`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007aff6`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b036`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007aee9`: `m_hProbeCompletionEvent != 0`

## pseudocode

```c
__int64 __fastcall CClientNotificationSink::Initialize(CClientNotificationSink *this, struct IWSDiscoveryProvider *a2)
{
  const wchar_t *v4; // rax
  __int64 v5; // r9
  unsigned int v6; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  const unsigned __int16 *v9; // r14
  unsigned int v10; // ebp
  HANDLE v11; // rax
  signed int v12; // eax
  int WideStringHostName; // eax
  unsigned int v15; // [rsp+30h] [rbp-38h]
  unsigned int v16; // [rsp+30h] [rbp-38h]
  unsigned int v17; // [rsp+38h] [rbp-30h]
  unsigned int v18; // [rsp+38h] [rbp-30h]

  if ( !*((_QWORD *)this + 9) )
  {
    v4 = L"Discovered server list critical section is not initialized.";
    v5 = 98;
LABEL_3:
    v6 = -2147024882;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      v5,
      L"CClientNotificationSink::Initialize",
      v4);
    return v6;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    v4 = L"Discover probe critical section is not initialized.";
    v5 = 99;
    goto LABEL_3;
  }
  DEBUGMSG(L"CClientNotificationSink::Initialize: Initializing Peer server list to an empty list.\n");
  CClientNotificationSink::s_pProvider = a2;
  *((_QWORD *)this + 3) = (char *)this + 16;
  *((_QWORD *)this + 2) = (char *)this + 16;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v9 = L"m_hProbeCompletionEvent != 0";
    v10 = 111;
LABEL_10:
    if ( (v6 & 0x80000000) == 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      v10,
      L"CClientNotificationSink::Initialize",
      L"CBRAEx",
      v9,
      v6);
    if ( IsDebuggerPresent() )
    {
      v17 = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        v10,
        L"CClientNotificationSink::Initialize",
        L"CBRAEx",
        v9,
        v17);
    }
    else
    {
      v15 = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        v10,
        L"CClientNotificationSink::Initialize",
        L"CBRAEx",
        v9,
        v15);
    }
    return v6;
  }
  v11 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 5) = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v9 = L"m_hProbeFailedEvent != 0";
    v10 = 114;
    goto LABEL_10;
  }
  WideStringHostName = GetWideStringHostName((unsigned __int16 **)this + 6);
  v6 = WideStringHostName;
  if ( WideStringHostName < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      0x75u,
      L"CClientNotificationSink::Initialize",
      L"CHRA",
      L"hr",
      WideStringHostName);
    if ( IsDebuggerPresent() )
    {
      v18 = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        117,
        L"CClientNotificationSink::Initialize",
        L"CHRA",
        L"hr",
        v18);
    }
    else
    {
      v16 = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        117,
        L"CClientNotificationSink::Initialize",
        L"CHRA",
        L"hr",
        v16);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14007ae24  push    rbx
0x14007ae26  push    rbp
0x14007ae27  push    rsi
0x14007ae28  push    rdi
0x14007ae29  push    r14
0x14007ae2b  sub     rsp, 40h
0x14007ae2f  cmp     qword ptr [rcx+48h], 0
0x14007ae34  mov     rdi, rdx
0x14007ae37  mov     rbx, rcx
0x14007ae3a  jnz     short loc_14007AE7C
0x14007ae3c  lea     rax, aDiscoveredServ; "Discovered server list critical section"...
0x14007ae43  mov     r9d, 62h ; 'b'
0x14007ae49  mov     qword ptr [rsp+68h+var_40], rax
0x14007ae4e  lea     rdi, aCclientnotific_11; "CClientNotificationSink::Initialize"
0x14007ae55  lea     r8, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007ae5c  mov     [rsp+68h+var_48], rdi
0x14007ae61  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14007ae68  mov     ecx, 4; unsigned __int8
0x14007ae6d  mov     ebx, 8007000Eh
0x14007ae72  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007ae77  jmp     loc_14007B049
0x14007ae7c  cmp     qword ptr [rcx+80h], 0
0x14007ae84  jnz     short loc_14007AE95
0x14007ae86  lea     rax, aDiscoverProbeC; "Discover probe critical section is not "...
0x14007ae8d  mov     r9d, 63h ; 'c'
0x14007ae93  jmp     short loc_14007AE49
0x14007ae95  lea     rcx, aCclientnotific_19; "CClientNotificationSink::Initialize: In"...
0x14007ae9c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14007aea1  lea     rax, [rbx+10h]
0x14007aea5  mov     cs:?s_pProvider@CClientNotificationSink@@0PEAUIWSDiscoveryProvider@@EA, rdi; IWSDiscoveryProvider * CClientNotificationSink::s_pProvider
0x14007aeac  xor     r9d, r9d; lpName
0x14007aeaf  mov     [rax+8], rax
0x14007aeb3  xor     r8d, r8d; bInitialState
0x14007aeb6  mov     [rax], rax
0x14007aeb9  xor     ecx, ecx; lpEventAttributes
0x14007aebb  lea     edi, [r9+1]
0x14007aebf  mov     edx, edi; bManualReset
0x14007aec1  call    cs:__imp_CreateEventW
0x14007aec7  mov     [rbx+20h], rax
0x14007aecb  test    rax, rax
0x14007aece  jnz     loc_14007AF7D
0x14007aed4  call    cs:__imp_GetLastError
0x14007aeda  mov     ebx, eax
0x14007aedc  test    eax, eax
0x14007aede  jle     short loc_14007AEE9
0x14007aee0  movzx   ebx, ax
0x14007aee3  or      ebx, 80070000h
0x14007aee9  lea     r14, aMHprobecomplet; "m_hProbeCompletionEvent != 0"
0x14007aef0  mov     ebp, 6Fh ; 'o'
0x14007aef5  mov     eax, 80004005h
0x14007aefa  lea     rdi, aCclientnotific_11; "CClientNotificationSink::Initialize"
0x14007af01  test    ebx, ebx
0x14007af03  lea     rsi, aCbraex; "CBRAEx"
0x14007af0a  mov     r8, rdi; unsigned __int16 *
0x14007af0d  lea     rcx, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007af14  cmovns  ebx, eax
0x14007af17  mov     r9, rsi; unsigned __int16 *
0x14007af1a  mov     [rsp+68h+var_40], ebx; int
0x14007af1e  mov     edx, ebp; unsigned int
0x14007af20  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x14007af25  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007af2a  call    cs:__imp_IsDebuggerPresent
0x14007af30  test    eax, eax
0x14007af32  jz      short loc_14007AF67
0x14007af34  mov     [rsp+68h+var_30], ebx
0x14007af38  mov     r9d, ebp
0x14007af3b  mov     [rsp+68h+var_38], r14
0x14007af40  mov     qword ptr [rsp+68h+var_40], rsi
0x14007af45  lea     r8, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007af4c  mov     [rsp+68h+var_48], rdi
0x14007af51  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007af58  mov     ecx, 2; unsigned __int8
0x14007af5d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007af62  jmp     loc_14007B049
0x14007af67  mov     dword ptr [rsp+68h+var_38], ebx
0x14007af6b  mov     r8d, ebp
0x14007af6e  mov     qword ptr [rsp+68h+var_40], r14
0x14007af73  mov     [rsp+68h+var_48], rsi
0x14007af78  jmp     loc_14007B033
0x14007af7d  xor     r9d, r9d; lpName
0x14007af80  xor     r8d, r8d; bInitialState
0x14007af83  mov     edx, edi; bManualReset
0x14007af85  xor     ecx, ecx; lpEventAttributes
0x14007af87  call    cs:__imp_CreateEventW
0x14007af8d  mov     [rbx+28h], rax
0x14007af91  test    rax, rax
0x14007af94  jnz     short loc_14007AFBC
0x14007af96  call    cs:__imp_GetLastError
0x14007af9c  mov     ebx, eax
0x14007af9e  test    eax, eax
0x14007afa0  jle     short loc_14007AFAB
0x14007afa2  movzx   ebx, ax
0x14007afa5  or      ebx, 80070000h
0x14007afab  lea     r14, aMHprobefailede; "m_hProbeFailedEvent != 0"
0x14007afb2  mov     ebp, 72h ; 'r'
0x14007afb7  jmp     loc_14007AEF5
0x14007afbc  lea     rcx, [rbx+30h]; unsigned __int16 **
0x14007afc0  call    ?GetWideStringHostName@@YAJPEAPEAG@Z; GetWideStringHostName(ushort * *)
0x14007afc5  mov     ebx, eax
0x14007afc7  test    eax, eax
0x14007afc9  jns     short loc_14007B049
0x14007afcb  mov     [rsp+68h+var_40], eax; int
0x14007afcf  lea     r14, aChra; "CHRA"
0x14007afd6  lea     rdi, aCclientnotific_11; "CClientNotificationSink::Initialize"
0x14007afdd  mov     esi, 75h ; 'u'
0x14007afe2  lea     rbp, aHr; "hr"
0x14007afe9  mov     r9, r14; unsigned __int16 *
0x14007afec  mov     r8, rdi; unsigned __int16 *
0x14007afef  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x14007aff4  mov     edx, esi; unsigned int
0x14007aff6  lea     rcx, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007affd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b002  call    cs:__imp_IsDebuggerPresent
0x14007b008  test    eax, eax
0x14007b00a  jz      short loc_14007B022
0x14007b00c  mov     [rsp+68h+var_30], ebx
0x14007b010  mov     r9d, esi
0x14007b013  mov     [rsp+68h+var_38], rbp
0x14007b018  mov     qword ptr [rsp+68h+var_40], r14
0x14007b01d  jmp     loc_14007AF45
0x14007b022  mov     dword ptr [rsp+68h+var_38], ebx
0x14007b026  mov     r8d, esi
0x14007b029  mov     qword ptr [rsp+68h+var_40], rbp
0x14007b02e  mov     [rsp+68h+var_48], r14
0x14007b033  mov     r9, rdi
0x14007b036  lea     rdx, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b03d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007b044  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007b049  mov     eax, ebx
0x14007b04b  add     rsp, 40h
0x14007b04f  pop     r14
0x14007b051  pop     rdi
0x14007b052  pop     rsi
0x14007b053  pop     rbp
0x14007b054  pop     rbx
0x14007b055  retn
```
