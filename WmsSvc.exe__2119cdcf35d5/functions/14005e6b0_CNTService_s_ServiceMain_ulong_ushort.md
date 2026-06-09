# CNTService::s_ServiceMain(ulong,ushort * *)

- ea: `0x14005e6b0`
- end: `0x14005e80b`
- name: `?s_ServiceMain@CNTService@@SAXKPEAPEAG@Z`
- size: `347`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005dcb8`
- `0x14005e6b0`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x14005e77c`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x14005e77c`
- `KERNEL32!HeapSetInformation` at `0x14005e6c7`
- `KERNEL32!HeapSetInformation` at `0x14005e6c7`
- `KERNEL32!GetLastError` at `0x14005e78e`
- `KERNEL32!GetLastError` at `0x14005e7bf`
- `KERNEL32!GetLastError` at `0x14005e78e`
- `KERNEL32!GetLastError` at `0x14005e7bf`
- `KERNEL32!IsDebuggerPresent` at `0x14005e704`
- `KERNEL32!IsDebuggerPresent` at `0x14005e704`

## string_xrefs

- `0x14005e6f8`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e71a`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e743`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14005e6db`: `CNTService::s_ServiceMain`
- `0x14005e796`: `CNTService::s_ServiceMainService Not Registered %x\n`

## pseudocode

```c
void __fastcall CNTService::s_ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // r9
  CNTService *v3; // rdi
  const WCHAR *v4; // rcx
  SERVICE_STATUS_HANDLE v5; // rax
  DWORD v6; // eax
  int v7; // ebx
  DWORD LastError; // eax
  __int64 v9; // rax

  if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
      0x279u,
      L"CNTService::s_ServiceMain",
      v2,
      L"fSuccess == TRUE");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        633,
        L"CNTService::s_ServiceMain",
        L"ASSERT",
        L"fSuccess == TRUE");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\ntservice\\ntservice.cpp",
        633,
        L"CNTService::s_ServiceMain",
        L"ASSERT",
        L"fSuccess == TRUE");
  }
  v3 = CNTService::s_pSingleInstance;
  v4 = (const WCHAR *)((char *)CNTService::s_pSingleInstance + 8);
  *((_DWORD *)CNTService::s_pSingleInstance + 197) = 2;
  v5 = RegisterServiceCtrlHandlerExW(v4, CNTService::s_HandlerEx, 0);
  *((_QWORD *)v3 + 97) = v5;
  if ( v5 )
  {
    CNTService::SetStatus(v3, 2u);
    v7 = (*(__int64 (__fastcall **)(CNTService *))(*(_QWORD *)v3 + 32LL))(v3);
    LastError = GetLastError();
    *(_QWORD *)((char *)v3 + 804) = 0;
    *((_DWORD *)v3 + 199) = LastError;
    if ( v7 )
    {
      v9 = *(_QWORD *)v3;
      *((_DWORD *)v3 + 199) = 0;
      (*(void (__fastcall **)(CNTService *))(v9 + 24))(v3);
    }
    CNTService::SetStatus(v3, 1u);
  }
  else
  {
    v6 = GetLastError();
    DEBUGMSG(L"CNTService::s_ServiceMainService Not Registered %x\n", v6);
  }
}

```

## disassembly

```asm
0x14005e6b0  push    rbx
0x14005e6b2  push    rdi
0x14005e6b3  push    r12
0x14005e6b5  push    r15
0x14005e6b7  sub     rsp, 48h
0x14005e6bb  xor     r9d, r9d; HeapInformationLength
0x14005e6be  xor     r8d, r8d; HeapInformation
0x14005e6c1  xor     ecx, ecx; HeapHandle
0x14005e6c3  lea     edx, [r9+1]; HeapInformationClass
0x14005e6c7  call    cs:__imp_HeapSetInformation
0x14005e6cd  mov     ebx, 2
0x14005e6d2  cmp     eax, 1
0x14005e6d5  jz      loc_14005E761
0x14005e6db  lea     r15, aCntserviceSSer; "CNTService::s_ServiceMain"
0x14005e6e2  mov     edi, 279h
0x14005e6e7  lea     r12, aFsuccessTrue; "fSuccess == TRUE"
0x14005e6ee  mov     r8, r15; unsigned __int16 *
0x14005e6f1  mov     edx, edi; unsigned int
0x14005e6f3  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x14005e6f8  lea     rcx, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e6ff  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14005e704  call    cs:__imp_IsDebuggerPresent
0x14005e70a  test    eax, eax
0x14005e70c  lea     rax, aAssert; "ASSERT"
0x14005e713  jz      short loc_14005E73E
0x14005e715  mov     [rsp+68h+var_38], r12
0x14005e71a  lea     r8, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e721  mov     [rsp+68h+var_40], rax
0x14005e726  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005e72d  mov     r9d, edi
0x14005e730  mov     [rsp+68h+var_48], r15
0x14005e735  mov     ecx, ebx; unsigned __int8
0x14005e737  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005e73c  jmp     short loc_14005E761
0x14005e73e  mov     [rsp+68h+var_40], r12
0x14005e743  lea     rdx, aTermsrvWmsSrcC_23; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14005e74a  mov     r9, r15
0x14005e74d  mov     [rsp+68h+var_48], rax
0x14005e752  mov     r8d, edi
0x14005e755  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005e75c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005e761  mov     rdi, cs:?s_pSingleInstance@CNTService@@2PEAV1@EA; CNTService * CNTService::s_pSingleInstance
0x14005e768  lea     rdx, ?s_HandlerEx@CNTService@@SAKKKPEAX0@Z; lpHandlerProc
0x14005e76f  xor     r8d, r8d; lpContext
0x14005e772  lea     rcx, [rdi+8]; lpServiceName
0x14005e776  mov     [rdi+314h], ebx
0x14005e77c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x14005e782  mov     [rdi+308h], rax
0x14005e789  test    rax, rax
0x14005e78c  jnz     short loc_14005E7A4
0x14005e78e  call    cs:__imp_GetLastError
0x14005e794  mov     edx, eax
0x14005e796  lea     rcx, aCntserviceSSer_0; "CNTService::s_ServiceMainService Not Re"...
0x14005e79d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005e7a2  jmp     short loc_14005E800
0x14005e7a4  mov     edx, ebx; unsigned int
0x14005e7a6  mov     rcx, rdi; this
0x14005e7a9  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14005e7ae  mov     rax, [rdi]
0x14005e7b1  mov     rcx, rdi
0x14005e7b4  mov     rax, [rax+20h]
0x14005e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e7bd  mov     ebx, eax
0x14005e7bf  call    cs:__imp_GetLastError
0x14005e7c5  mov     qword ptr [rdi+324h], 0
0x14005e7d0  mov     [rdi+31Ch], eax
0x14005e7d6  test    ebx, ebx
0x14005e7d8  jz      short loc_14005E7F3
0x14005e7da  mov     rax, [rdi]
0x14005e7dd  mov     rcx, rdi
0x14005e7e0  mov     dword ptr [rdi+31Ch], 0
0x14005e7ea  mov     rax, [rax+18h]
0x14005e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e7f3  mov     edx, 1; unsigned int
0x14005e7f8  mov     rcx, rdi; this
0x14005e7fb  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x14005e800  add     rsp, 48h
0x14005e804  pop     r15
0x14005e806  pop     r12
0x14005e808  pop     rdi
0x14005e809  pop     rbx
0x14005e80a  retn
```
