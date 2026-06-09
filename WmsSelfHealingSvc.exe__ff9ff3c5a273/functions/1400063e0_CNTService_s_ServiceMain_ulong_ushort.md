# CNTService::s_ServiceMain(ulong,ushort * *)

- ea: `0x1400063e0`
- end: `0x14000653b`
- name: `?s_ServiceMain@CNTService@@SAXKPEAPEAG@Z`
- size: `347`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x1400058e8`
- `0x1400063e0`
- `0x14000c010`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1400064ac`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1400064ac`
- `KERNEL32!IsDebuggerPresent` at `0x140006434`
- `KERNEL32!IsDebuggerPresent` at `0x140006434`
- `KERNEL32!GetLastError` at `0x1400064be`
- `KERNEL32!GetLastError` at `0x1400064ef`
- `KERNEL32!GetLastError` at `0x1400064be`
- `KERNEL32!GetLastError` at `0x1400064ef`
- `KERNEL32!HeapSetInformation` at `0x1400063f7`
- `KERNEL32!HeapSetInformation` at `0x1400063f7`

## string_xrefs

- `0x140006428`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14000644a`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x140006473`: `termsrv\wms\src\common\ntservice\ntservice.cpp`
- `0x14000640b`: `CNTService::s_ServiceMain`
- `0x1400064c6`: `CNTService::s_ServiceMainService Not Registered %x\n`

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
0x1400063e0  push    rbx
0x1400063e2  push    rdi
0x1400063e3  push    r12
0x1400063e5  push    r15
0x1400063e7  sub     rsp, 48h
0x1400063eb  xor     r9d, r9d; HeapInformationLength
0x1400063ee  xor     r8d, r8d; HeapInformation
0x1400063f1  xor     ecx, ecx; HeapHandle
0x1400063f3  lea     edx, [r9+1]; HeapInformationClass
0x1400063f7  call    cs:__imp_HeapSetInformation
0x1400063fd  mov     ebx, 2
0x140006402  cmp     eax, 1
0x140006405  jz      loc_140006491
0x14000640b  lea     r15, aCntserviceSSer; "CNTService::s_ServiceMain"
0x140006412  mov     edi, 279h
0x140006417  lea     r12, aFsuccessTrue; "fSuccess == TRUE"
0x14000641e  mov     r8, r15; unsigned __int16 *
0x140006421  mov     edx, edi; unsigned int
0x140006423  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x140006428  lea     rcx, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14000642f  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140006434  call    cs:__imp_IsDebuggerPresent
0x14000643a  test    eax, eax
0x14000643c  lea     rax, aAssert; "ASSERT"
0x140006443  jz      short loc_14000646E
0x140006445  mov     [rsp+68h+var_38], r12
0x14000644a  lea     r8, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x140006451  mov     [rsp+68h+var_40], rax
0x140006456  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000645d  mov     r9d, edi
0x140006460  mov     [rsp+68h+var_48], r15
0x140006465  mov     ecx, ebx; unsigned __int8
0x140006467  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000646c  jmp     short loc_140006491
0x14000646e  mov     [rsp+68h+var_40], r12
0x140006473  lea     rdx, aTermsrvWmsSrcC_5; "termsrv\\wms\\src\\common\\ntservice\\n"...
0x14000647a  mov     r9, r15
0x14000647d  mov     [rsp+68h+var_48], rax
0x140006482  mov     r8d, edi
0x140006485  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000648c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140006491  mov     rdi, cs:?s_pSingleInstance@CNTService@@2PEAV1@EA; CNTService * CNTService::s_pSingleInstance
0x140006498  lea     rdx, ?s_HandlerEx@CNTService@@SAKKKPEAX0@Z; lpHandlerProc
0x14000649f  xor     r8d, r8d; lpContext
0x1400064a2  lea     rcx, [rdi+8]; lpServiceName
0x1400064a6  mov     [rdi+314h], ebx
0x1400064ac  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1400064b2  mov     [rdi+308h], rax
0x1400064b9  test    rax, rax
0x1400064bc  jnz     short loc_1400064D4
0x1400064be  call    cs:__imp_GetLastError
0x1400064c4  mov     edx, eax
0x1400064c6  lea     rcx, aCntserviceSSer_0; "CNTService::s_ServiceMainService Not Re"...
0x1400064cd  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400064d2  jmp     short loc_140006530
0x1400064d4  mov     edx, ebx; unsigned int
0x1400064d6  mov     rcx, rdi; this
0x1400064d9  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x1400064de  mov     rax, [rdi]
0x1400064e1  mov     rcx, rdi
0x1400064e4  mov     rax, [rax+20h]
0x1400064e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064ed  mov     ebx, eax
0x1400064ef  call    cs:__imp_GetLastError
0x1400064f5  mov     qword ptr [rdi+324h], 0
0x140006500  mov     [rdi+31Ch], eax
0x140006506  test    ebx, ebx
0x140006508  jz      short loc_140006523
0x14000650a  mov     rax, [rdi]
0x14000650d  mov     rcx, rdi
0x140006510  mov     dword ptr [rdi+31Ch], 0
0x14000651a  mov     rax, [rax+18h]
0x14000651e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006523  mov     edx, 1; unsigned int
0x140006528  mov     rcx, rdi; this
0x14000652b  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x140006530  add     rsp, 48h
0x140006534  pop     r15
0x140006536  pop     r12
0x140006538  pop     rdi
0x140006539  pop     rbx
0x14000653a  retn
```
