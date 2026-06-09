# CRegistration::GetNextMessage(unsigned __int64 *,IXMLDOMDocument * *,ulong *)

- ea: `0x180034c5c`
- end: `0x180034f03`
- name: `?GetNextMessage@CRegistration@@QEAAJPEA_KPEAPEAUIXMLDOMDocument@@PEAK@Z`
- size: `679`
- prototype: `__int64 __fastcall(CRegistration *__hidden this, unsigned __int64 *, struct IXMLDOMDocument **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800153cc`

## callees

- `0x18001d548`
- `0x180034c5c`
- `0x180038344`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034df7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034df7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034d84`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034ea2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034ed0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034d84`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034ea2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034ed0`

## string_xrefs

- `0x180034de2`: `MaxAccessCount`
- `0x180034e94`: `LastAccessedMessageId`
- `0x180034e35`: `Automatically acknowledging message %llu for registration %S since it was not acknowledged in previous %d access`
- `0x180034ebf`: `AccessCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistration::GetNextMessage(
        CRegistration *this,
        unsigned __int64 *a2,
        struct IXMLDOMDocument **a3,
        unsigned int *a4)
{
  char *v8; // r14
  unsigned __int64 v9; // r8
  __int64 *v10; // rdx
  __int64 *v11; // rax
  __int64 *v12; // rcx
  unsigned int MessageXML; // ebp
  const WCHAR *v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 *lpData; // rsi
  unsigned int *v17; // rdi
  unsigned int v18; // eax
  const wchar_t *v19; // rcx
  const WCHAR *v20; // rbx
  const WCHAR *v21; // rdx
  int pvData; // [rsp+A0h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+10h] BYREF

  v8 = (char *)this + 304;
  (**((void (__fastcall ***)(char *))this + 38))((char *)this + 304);
  v9 = *a2;
  if ( *a2 || !*((_QWORD *)this + 32) )
  {
    v10 = (__int64 *)*((_QWORD *)this + 31);
    v11 = (__int64 *)v10[1];
    v12 = v10;
    while ( !*((_BYTE *)v11 + 25) )
    {
      if ( v11[4] >= v9 )
        v12 = v11;
      else
        v11 += 2;
      v11 = (__int64 *)*v11;
    }
    if ( *((_BYTE *)v12 + 25) || v9 < v12[4] || v12 == v10 )
    {
      MessageXML = -2147024637;
      goto LABEL_34;
    }
  }
  else
  {
    *a2 = *(_QWORD *)(**((_QWORD **)this + 31) + 32LL);
  }
  *a4 = *((_DWORD *)this + 59);
  MessageXML = CSmsMessageStore::GetMessageXML(*((CSmsMessageStore **)this + 44), *a2, a3);
  if ( *((_QWORD *)this + 33) == *a2 )
  {
    *((_DWORD *)this + 56) = 1;
    *((_DWORD *)this + 68) = 0;
    v14 = (const WCHAR *)((char *)this + 176);
    if ( *((_QWORD *)this + 25) > 7u )
      v14 = *(const WCHAR **)v14;
    RegSetKeyValueW(g_SmsRouterKey, v14, L"NotifyCount", 4u, (char *)this + 272, 4u);
  }
  v15 = *a2;
  lpData = (unsigned __int64 *)((char *)this + 288);
  v17 = (unsigned int *)((char *)this + 296);
  if ( *((_QWORD *)this + 36) == v15 )
  {
    ++*v17;
    pvData = 3;
    pcbData = 4;
    if ( RegGetValueW(g_SmsRouterKey, L"Registration", L"MaxAccessCount", 0x10u, 0, &pvData, &pcbData)
      || (v18 = pvData) == 0 )
    {
      v18 = 3;
    }
    if ( *v17 <= v18 )
      goto LABEL_28;
    if ( *((_QWORD *)this + 3) <= 7u )
      v19 = (const wchar_t *)this;
    else
      v19 = *(const wchar_t **)this;
    LogSmsRouterInfo(
      "CRegistration::GetNextMessage",
      0x40Du,
      "Automatically acknowledging message %llu for registration %S since it was not acknowledged in previous %d access",
      *lpData,
      v19,
      *v17 - 1);
    CRegistration::StartAcknowledgeMessageTimer(this, *lpData, 0);
    *lpData = -1;
  }
  else
  {
    *lpData = v15;
  }
  *v17 = 1;
LABEL_28:
  v20 = (const WCHAR *)((char *)this + 176);
  v21 = v20;
  if ( *((_QWORD *)v20 + 3) > 7u )
    v21 = *(const WCHAR **)v20;
  RegSetKeyValueW(g_SmsRouterKey, v21, L"LastAccessedMessageId", 0xBu, lpData, 8u);
  if ( *((_QWORD *)v20 + 3) > 7u )
    v20 = *(const WCHAR **)v20;
  RegSetKeyValueW(g_SmsRouterKey, v20, L"AccessCount", 4u, v17, 4u);
LABEL_34:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  return MessageXML;
}

```

## disassembly

```asm
0x180034c5c  mov     [rsp+arg_10], rbx
0x180034c61  push    rbp
0x180034c62  push    rsi
0x180034c63  push    rdi
0x180034c64  push    r12
0x180034c66  push    r14
0x180034c68  sub     rsp, 70h
0x180034c6c  mov     rsi, r9
0x180034c6f  mov     rbp, r8
0x180034c72  mov     rdi, rdx
0x180034c75  mov     rbx, rcx
0x180034c78  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180034c7f  mov     [rsp+98h+var_58], rax
0x180034c84  lea     r14, [rcx+130h]
0x180034c8b  mov     [rsp+98h+var_50], r14
0x180034c90  mov     rax, [r14]
0x180034c93  mov     rcx, r14
0x180034c96  mov     rax, [rax]
0x180034c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c9e  nop
0x180034c9f  mov     r8, [rdi]
0x180034ca2  test    r8, r8
0x180034ca5  jnz     short loc_180034CC3
0x180034ca7  cmp     [rbx+100h], r8
0x180034cae  jbe     short loc_180034CC3
0x180034cb0  mov     rax, [rbx+0F8h]
0x180034cb7  mov     rcx, [rax]
0x180034cba  mov     rax, [rcx+20h]
0x180034cbe  mov     [rdi], rax
0x180034cc1  jmp     short loc_180034D0E
0x180034cc3  mov     rdx, [rbx+0F8h]
0x180034cca  mov     rax, [rdx+8]
0x180034cce  xor     ecx, ecx
0x180034cd0  mov     [rsp+98h+var_3C], ecx
0x180034cd4  mov     rcx, rdx
0x180034cd7  jmp     short loc_180034CEB
0x180034cd9  cmp     [rax+20h], r8
0x180034cdd  jnb     short loc_180034CE5
0x180034cdf  add     rax, 10h
0x180034ce3  jmp     short loc_180034CE8
0x180034ce5  mov     rcx, rax
0x180034ce8  mov     rax, [rax]
0x180034ceb  cmp     byte ptr [rax+19h], 0
0x180034cef  jz      short loc_180034CD9
0x180034cf1  cmp     byte ptr [rcx+19h], 0
0x180034cf5  jnz     loc_180034ED8
0x180034cfb  cmp     r8, [rcx+20h]
0x180034cff  jb      loc_180034ED8
0x180034d05  cmp     rcx, rdx
0x180034d08  jz      loc_180034ED8
0x180034d0e  mov     eax, 0ECh
0x180034d13  mov     rcx, rbx
0x180034d16  mov     eax, [rbx+rax]
0x180034d19  mov     [rsi], eax
0x180034d1b  mov     r8, rbp; struct IXMLDOMDocument **
0x180034d1e  mov     rdx, [rdi]; unsigned __int64
0x180034d21  mov     rcx, [rbx+160h]; this
0x180034d28  call    ?GetMessageXML@CSmsMessageStore@@QEAAJ_KPEAPEAUIXMLDOMDocument@@@Z; CSmsMessageStore::GetMessageXML(unsigned __int64,IXMLDOMDocument * *)
0x180034d2d  mov     ebp, eax
0x180034d2f  mov     rcx, [rdi]
0x180034d32  mov     r12d, 4
0x180034d38  cmp     [rbx+108h], rcx
0x180034d3f  jnz     short loc_180034D8A
0x180034d41  mov     dword ptr [rbx+0E0h], 1
0x180034d4b  lea     rcx, [rbx+110h]
0x180034d52  mov     dword ptr [rcx], 0
0x180034d58  lea     rdx, [rbx+0B0h]
0x180034d5f  cmp     qword ptr [rdx+18h], 7
0x180034d64  jbe     short loc_180034D69
0x180034d66  mov     rdx, [rdx]; lpSubKey
0x180034d69  mov     [rsp+98h+cbData], r12d; cbData
0x180034d6e  mov     [rsp+98h+lpData], rcx; lpData
0x180034d73  mov     r9d, r12d; dwType
0x180034d76  lea     r8, aNotifycount; "NotifyCount"
0x180034d7d  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180034d84  call    cs:__imp_RegSetKeyValueW
0x180034d8a  mov     rax, [rdi]
0x180034d8d  lea     rsi, [rbx+120h]
0x180034d94  lea     rdi, [rbx+128h]
0x180034d9b  cmp     [rsi], rax
0x180034d9e  jnz     loc_180034E64
0x180034da4  inc     dword ptr [rdi]
0x180034da6  mov     [rsp+98h+pvData], 3
0x180034db1  mov     [rsp+98h+arg_8], r12d
0x180034db9  lea     rax, [rsp+98h+arg_8]
0x180034dc1  mov     [rsp+98h+pcbData], rax; pcbData
0x180034dc6  lea     rax, [rsp+98h+pvData]
0x180034dce  mov     qword ptr [rsp+98h+cbData], rax; pvData
0x180034dd3  mov     [rsp+98h+lpData], 0; pdwType
0x180034ddc  mov     r9d, 10h; dwFlags
0x180034de2  lea     r8, aMaxaccesscount; "MaxAccessCount"
0x180034de9  lea     rdx, aRegistration; "Registration"
0x180034df0  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x180034df7  call    cs:__imp_RegGetValueW
0x180034dfd  test    eax, eax
0x180034dff  jnz     short loc_180034E0C
0x180034e01  mov     eax, [rsp+98h+pvData]
0x180034e08  test    eax, eax
0x180034e0a  jnz     short loc_180034E11
0x180034e0c  mov     eax, 3
0x180034e11  mov     edx, [rdi]
0x180034e13  cmp     edx, eax
0x180034e15  jbe     short loc_180034E6D
0x180034e17  cmp     qword ptr [rbx+18h], 7
0x180034e1c  jbe     short loc_180034E23
0x180034e1e  mov     rcx, [rbx]
0x180034e21  jmp     short loc_180034E26
0x180034e23  mov     rcx, rbx
0x180034e26  lea     eax, [rdx-1]
0x180034e29  mov     [rsp+98h+cbData], eax
0x180034e2d  mov     [rsp+98h+lpData], rcx
0x180034e32  mov     r9, [rsi]
0x180034e35  lea     r8, aAutomaticallyA; "Automatically acknowledging message %ll"...
0x180034e3c  mov     edx, 40Dh; unsigned int
0x180034e41  lea     rcx, aCregistrationG; "CRegistration::GetNextMessage"
0x180034e48  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180034e4d  xor     r8d, r8d; unsigned int
0x180034e50  mov     rdx, [rsi]; unsigned __int64
0x180034e53  mov     rcx, rbx; this
0x180034e56  call    ?StartAcknowledgeMessageTimer@CRegistration@@QEAAX_KK@Z; CRegistration::StartAcknowledgeMessageTimer(unsigned __int64,ulong)
0x180034e5b  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180034e62  jmp     short loc_180034E67
0x180034e64  mov     [rsi], rax
0x180034e67  mov     dword ptr [rdi], 1
0x180034e6d  add     rbx, 0B0h
0x180034e74  mov     rdx, rbx
0x180034e77  cmp     qword ptr [rbx+18h], 7
0x180034e7c  jbe     short loc_180034E81
0x180034e7e  mov     rdx, [rbx]; lpSubKey
0x180034e81  mov     [rsp+98h+cbData], 8; cbData
0x180034e89  mov     [rsp+98h+lpData], rsi; lpData
0x180034e8e  mov     r9d, 0Bh; dwType
0x180034e94  lea     r8, aLastaccessedme; "LastAccessedMessageId"
0x180034e9b  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180034ea2  call    cs:__imp_RegSetKeyValueW
0x180034ea8  cmp     qword ptr [rbx+18h], 7
0x180034ead  jbe     short loc_180034EB2
0x180034eaf  mov     rbx, [rbx]
0x180034eb2  mov     [rsp+98h+cbData], r12d; cbData
0x180034eb7  mov     [rsp+98h+lpData], rdi; lpData
0x180034ebc  mov     r9d, r12d; dwType
0x180034ebf  lea     r8, aAccesscount; "AccessCount"
0x180034ec6  mov     rdx, rbx; lpSubKey
0x180034ec9  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180034ed0  call    cs:__imp_RegSetKeyValueW
0x180034ed6  jmp     short loc_180034EDD
0x180034ed8  mov     ebp, 80070103h
0x180034edd  mov     rax, [r14]
0x180034ee0  mov     rcx, r14
0x180034ee3  mov     rax, [rax+8]
0x180034ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034eec  nop
0x180034eed  mov     eax, ebp
0x180034eef  mov     rbx, [rsp+98h+arg_10]
0x180034ef7  add     rsp, 70h
0x180034efb  pop     r14
0x180034efd  pop     r12
0x180034eff  pop     rdi
0x180034f00  pop     rsi
0x180034f01  pop     rbp
0x180034f02  retn
```
