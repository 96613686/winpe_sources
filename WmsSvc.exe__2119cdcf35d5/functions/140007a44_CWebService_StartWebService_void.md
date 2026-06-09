# CWebService::StartWebService(void)

- ea: `0x140007a44`
- end: `0x140007beb`
- name: `?StartWebService@CWebService@@QEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CWebService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14004ac94`

## callees

- `0x140007a44`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140007b36`
- `KERNEL32!CreateThread` at `0x140007b36`
- `KERNEL32!ResetEvent` at `0x140007a7f`
- `KERNEL32!ResetEvent` at `0x140007a7f`
- `KERNEL32!GetLastError` at `0x140007b4c`
- `KERNEL32!GetLastError` at `0x140007b4c`
- `KERNEL32!IsDebuggerPresent` at `0x140007aca`
- `KERNEL32!IsDebuggerPresent` at `0x140007ba2`
- `KERNEL32!IsDebuggerPresent` at `0x140007aca`
- `KERNEL32!IsDebuggerPresent` at `0x140007ba2`

## string_xrefs

- `0x140007aa4`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007b76`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007a99`: `CWebService::StartWebService`
- `0x140007b6c`: `CWebService::StartWebService`
- `0x140007b11`: `CWebService::StartWebService - starting web service\n`
- `0x140007b81`: `m_hWebServiceThread`

## pseudocode

```c
__int64 __fastcall CWebService::StartWebService(CWebService *this)
{
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // r12
  const unsigned __int16 *v4; // r15
  __int64 v5; // r9
  __int64 v6; // r8
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v10; // [rsp+30h] [rbp-38h]
  unsigned int v11; // [rsp+38h] [rbp-30h]

  if ( !*((_QWORD *)this + 25) )
  {
    if ( !*((_WORD *)this + 96) )
      return (unsigned int)-2147418113;
    if ( ResetEvent(*((HANDLE *)this + 26)) )
    {
      v2 = 0;
      DEBUGMSG(L"CWebService::StartWebService - starting web service\n");
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CWebService::s_WebServiceThreadProc, this, 0, 0);
      *((_QWORD *)this + 25) = Thread;
      if ( Thread )
        return v2;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = L"CBRAEx";
      if ( LastError >= 0 )
        LastError = -2147467259;
      v4 = L"m_hWebServiceThread";
      v2 = LastError;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        0x108u,
        L"CWebService::StartWebService",
        L"CBRAEx",
        L"m_hWebServiceThread",
        LastError);
      if ( IsDebuggerPresent() )
      {
        v5 = 264;
        goto LABEL_8;
      }
      v6 = 264;
    }
    else
    {
      v2 = -2147467259;
      v3 = L"CBRA";
      v4 = L"fSuccess";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        0x103u,
        L"CWebService::StartWebService",
        L"CBRA",
        L"fSuccess",
        -2147467259);
      if ( IsDebuggerPresent() )
      {
        v5 = 259;
LABEL_8:
        v11 = v2;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
          v5,
          L"CWebService::StartWebService",
          v3,
          v4,
          v11);
        return v2;
      }
      v6 = 259;
    }
    v10 = v2;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
      v6,
      L"CWebService::StartWebService",
      v3,
      v4,
      v10);
    return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x140007a44  push    rbx
0x140007a46  push    rsi
0x140007a47  push    rdi
0x140007a48  push    r12
0x140007a4a  push    r15
0x140007a4c  sub     rsp, 40h
0x140007a50  cmp     qword ptr [rcx+0C8h], 0
0x140007a58  mov     rdi, rcx
0x140007a5b  jz      short loc_140007A64
0x140007a5d  xor     ebx, ebx
0x140007a5f  jmp     loc_140007BDD
0x140007a64  cmp     word ptr [rcx+0C0h], 1
0x140007a6c  jnb     short loc_140007A78
0x140007a6e  mov     ebx, 8000FFFFh
0x140007a73  jmp     loc_140007BDD
0x140007a78  mov     rcx, [rcx+0D0h]; hEvent
0x140007a7f  call    cs:__imp_ResetEvent
0x140007a85  test    eax, eax
0x140007a87  jnz     loc_140007B11
0x140007a8d  mov     ebx, 80004005h
0x140007a92  lea     r12, aCbra; "CBRA"
0x140007a99  lea     rsi, aCwebserviceSta_0; "CWebService::StartWebService"
0x140007aa0  mov     dword ptr [rsp+68h+lpThreadId], ebx; int
0x140007aa4  lea     rdi, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007aab  mov     r9, r12; unsigned __int16 *
0x140007aae  lea     r15, aFsuccess; "fSuccess"
0x140007ab5  mov     r8, rsi; unsigned __int16 *
0x140007ab8  mov     rcx, rdi; unsigned __int16 *
0x140007abb  mov     qword ptr [rsp+68h+dwCreationFlags], r15; unsigned __int16 *
0x140007ac0  mov     edx, 103h; unsigned int
0x140007ac5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007aca  call    cs:__imp_IsDebuggerPresent
0x140007ad0  test    eax, eax
0x140007ad2  jz      short loc_140007B06
0x140007ad4  mov     r9d, 103h
0x140007ada  mov     [rsp+68h+var_30], ebx
0x140007ade  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007ae5  mov     [rsp+68h+var_38], r15
0x140007aea  mov     r8, rdi
0x140007aed  mov     [rsp+68h+lpThreadId], r12
0x140007af2  mov     ecx, 2; unsigned __int8
0x140007af7  mov     qword ptr [rsp+68h+dwCreationFlags], rsi
0x140007afc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007b01  jmp     loc_140007BDD
0x140007b06  mov     r8d, 103h
0x140007b0c  jmp     loc_140007BBD
0x140007b11  lea     rcx, aCwebserviceSta; "CWebService::StartWebService - starting"...
0x140007b18  xor     ebx, ebx
0x140007b1a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140007b1f  mov     r9, rdi; lpParameter
0x140007b22  mov     [rsp+68h+lpThreadId], rbx; lpThreadId
0x140007b27  lea     r8, ?s_WebServiceThreadProc@CWebService@@CAKPEAX@Z; lpStartAddress
0x140007b2e  mov     [rsp+68h+dwCreationFlags], ebx; dwCreationFlags
0x140007b32  xor     edx, edx; dwStackSize
0x140007b34  xor     ecx, ecx; lpThreadAttributes
0x140007b36  call    cs:__imp_CreateThread
0x140007b3c  mov     [rdi+0C8h], rax
0x140007b43  test    rax, rax
0x140007b46  jnz     loc_140007BDD
0x140007b4c  call    cs:__imp_GetLastError
0x140007b52  test    eax, eax
0x140007b54  jle     short loc_140007B5E
0x140007b56  movzx   eax, ax
0x140007b59  or      eax, 80070000h
0x140007b5e  test    eax, eax
0x140007b60  lea     r12, aCbraex; "CBRAEx"
0x140007b67  mov     ebx, 80004005h
0x140007b6c  lea     rsi, aCwebserviceSta_0; "CWebService::StartWebService"
0x140007b73  cmovns  eax, ebx
0x140007b76  lea     rdi, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007b7d  mov     dword ptr [rsp+68h+lpThreadId], eax; int
0x140007b81  lea     r15, aMHwebserviceth; "m_hWebServiceThread"
0x140007b88  mov     r9, r12; unsigned __int16 *
0x140007b8b  mov     qword ptr [rsp+68h+dwCreationFlags], r15; unsigned __int16 *
0x140007b90  mov     r8, rsi; unsigned __int16 *
0x140007b93  mov     edx, 108h; unsigned int
0x140007b98  mov     rcx, rdi; unsigned __int16 *
0x140007b9b  mov     ebx, eax
0x140007b9d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007ba2  call    cs:__imp_IsDebuggerPresent
0x140007ba8  test    eax, eax
0x140007baa  jz      short loc_140007BB7
0x140007bac  mov     r9d, 108h
0x140007bb2  jmp     loc_140007ADA
0x140007bb7  mov     r8d, 108h
0x140007bbd  mov     dword ptr [rsp+68h+var_38], ebx
0x140007bc1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007bc8  mov     [rsp+68h+lpThreadId], r15
0x140007bcd  mov     r9, rsi
0x140007bd0  mov     rdx, rdi
0x140007bd3  mov     qword ptr [rsp+68h+dwCreationFlags], r12
0x140007bd8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007bdd  mov     eax, ebx
0x140007bdf  add     rsp, 40h
0x140007be3  pop     r15
0x140007be5  pop     r12
0x140007be7  pop     rdi
0x140007be8  pop     rsi
0x140007be9  pop     rbx
0x140007bea  retn
```
