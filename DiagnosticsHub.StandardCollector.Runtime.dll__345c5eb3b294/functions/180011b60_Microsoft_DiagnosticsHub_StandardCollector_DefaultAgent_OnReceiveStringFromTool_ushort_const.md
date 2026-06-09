# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::OnReceiveStringFromTool(ushort * const)

- ea: `0x180011b60`
- end: `0x180011db9`
- name: `?OnReceiveStringFromTool@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJQEAG@Z`
- size: `601`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, unsigned __int16 *const)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011b60`
- `0x180013908`
- `0x180013d1c`
- `0x180013ea8`
- `0x180014084`
- `0x1800143c4`
- `0x180014538`
- `0x1800146e4`
- `0x180014898`
- `0x1800445e0`
- `0x180047744`
- `0x18004b640`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011d1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d5c`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011bdf`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c03`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c27`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c4b`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c6c`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c8d`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011cae`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011ccf`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011cef`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011bdf`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c03`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c27`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c4b`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c6c`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011c8d`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011cae`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011ccf`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x180011cef`

## string_xrefs

- `0x180011d05`: `symbolCachePath`
- `0x180011bb4`: `command`
- `0x180011ce5`: `setSymbolCachePath`
- `0x180011c62`: `removeTargetProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::OnReceiveStringFromTool(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        unsigned __int16 *const a2)
{
  int FieldAsString; // esi
  struct Microsoft::Json::Object *v5; // rdi
  wchar_t *v6; // rbx
  int TargetProcesses; // eax
  struct Microsoft::Json::Object *v8; // rdx
  OLECHAR *v9; // rcx
  OLECHAR *v10; // rdi
  volatile signed __int32 *v11; // rbx
  BSTR bstrString; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+28h] [rbp-18h] BYREF
  Microsoft::Json::Object *v14[2]; // [rsp+30h] [rbp-10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *(_OWORD *)v14 = 0;
  FieldAsString = Microsoft::Json::Services::Deserialize(a2, v14);
  if ( FieldAsString >= 0 )
  {
    String1 = 0;
    v5 = v14[0];
    FieldAsString = Microsoft::Json::Object::GetFieldAsString(v14[0], L"command", &String1);
    v6 = String1;
    if ( FieldAsString >= 0 )
    {
      if ( !wcscmp(String1, L"bulkBreakEvents") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::BulkBreakEvents(this, v5);
LABEL_21:
        FieldAsString = TargetProcesses;
        goto LABEL_29;
      }
      if ( !wcscmp(v6, L"debuggerEnterBreakState") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerEnterBreakState(this, v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"debuggerExitBreakState") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerExitBreakState(this, v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"addTargetProcess") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::AddTargetProcess(this, v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"removeTargetProcess") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::RemoveTargetProcess(this, v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"enableCounters") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::EnableCounters(
                            (RTL_SRWLOCK *)this,
                            v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"getTargetProcesses") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetTargetProcesses(this, v5);
        goto LABEL_21;
      }
      if ( !wcscmp(v6, L"addUserMark") )
      {
        TargetProcesses = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::AddUserMark(this, v8);
        goto LABEL_21;
      }
      if ( wcscmp(v6, L"setSymbolCachePath") )
      {
        FieldAsString = -2147024809;
        goto LABEL_29;
      }
      bstrString = 0;
      FieldAsString = Microsoft::Json::Object::GetFieldAsString(v5, L"symbolCachePath", &bstrString);
      if ( FieldAsString >= 0 )
      {
        v10 = bstrString;
        FieldAsString = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)this + 12) + 128LL))(
                          *((_QWORD *)this + 12),
                          bstrString);
        v9 = v10;
        if ( FieldAsString >= 0 )
        {
          SysFreeString(v10);
          FieldAsString = 0;
          goto LABEL_29;
        }
      }
      else
      {
        v9 = bstrString;
      }
      SysFreeString(v9);
    }
LABEL_29:
    SysFreeString(v6);
  }
  v11 = (volatile signed __int32 *)v14[1];
  if ( v14[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v14[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
  return (unsigned int)FieldAsString;
}

```

## disassembly

```asm
0x180011b60  mov     [rsp-18h+arg_10], rbx
0x180011b65  mov     [rsp-18h+arg_18], rsi
0x180011b6a  push    rbp
0x180011b6b  push    rdi
0x180011b6c  push    r14
0x180011b6e  mov     rbp, rsp
0x180011b71  sub     rsp, 40h
0x180011b75  mov     rax, rdx
0x180011b78  mov     r14, rcx
0x180011b7b  test    rdx, rdx
0x180011b7e  jnz     short loc_180011B8A
0x180011b80  mov     eax, 80004003h
0x180011b85  jmp     loc_180011DA6
0x180011b8a  xorps   xmm1, xmm1
0x180011b8d  movdqu  xmmword ptr [rbp+var_10], xmm1
0x180011b92  lea     rdx, [rbp+var_10]
0x180011b96  mov     rcx, rax
0x180011b99  call    ?Deserialize@Services@Json@Microsoft@@SAJPEBGAEAV?$shared_ptr@VObject@Json@Microsoft@@@std@@@Z; Microsoft::Json::Services::Deserialize(ushort const *,std::shared_ptr<Microsoft::Json::Object> &)
0x180011b9e  mov     esi, eax
0x180011ba0  test    eax, eax
0x180011ba2  js      loc_180011D63
0x180011ba8  mov     [rbp+String1], 0
0x180011bb0  lea     r8, [rbp+String1]; unsigned __int16 **
0x180011bb4  lea     rdx, aCommand; "command"
0x180011bbb  mov     rdi, [rbp+var_10]
0x180011bbf  mov     rcx, rdi; this
0x180011bc2  call    ?GetFieldAsString@Object@Json@Microsoft@@QEAAJPEBGPEAPEAG@Z; Microsoft::Json::Object::GetFieldAsString(ushort const *,ushort * *)
0x180011bc7  mov     esi, eax
0x180011bc9  mov     rbx, [rbp+String1]
0x180011bcd  test    eax, eax
0x180011bcf  js      loc_180011D59
0x180011bd5  lea     rdx, aBulkbreakevent; "bulkBreakEvents"
0x180011bdc  mov     rcx, rbx; String1
0x180011bdf  call    cs:__imp_wcscmp
0x180011be5  test    eax, eax
0x180011be7  jnz     short loc_180011BF9
0x180011be9  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011bec  mov     rcx, r14; this
0x180011bef  call    ?BulkBreakEvents@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::BulkBreakEvents(Microsoft::Json::Object &)
0x180011bf4  jmp     loc_180011CE1
0x180011bf9  lea     rdx, aDebuggerenterb; "debuggerEnterBreakState"
0x180011c00  mov     rcx, rbx; String1
0x180011c03  call    cs:__imp_wcscmp
0x180011c09  test    eax, eax
0x180011c0b  jnz     short loc_180011C1D
0x180011c0d  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011c10  mov     rcx, r14; this
0x180011c13  call    ?DebuggerEnterBreakState@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerEnterBreakState(Microsoft::Json::Object &)
0x180011c18  jmp     loc_180011CE1
0x180011c1d  lea     rdx, aDebuggerexitbr; "debuggerExitBreakState"
0x180011c24  mov     rcx, rbx; String1
0x180011c27  call    cs:__imp_wcscmp
0x180011c2d  test    eax, eax
0x180011c2f  jnz     short loc_180011C41
0x180011c31  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011c34  mov     rcx, r14; this
0x180011c37  call    ?DebuggerExitBreakState@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerExitBreakState(Microsoft::Json::Object &)
0x180011c3c  jmp     loc_180011CE1
0x180011c41  lea     rdx, aAddtargetproce; "addTargetProcess"
0x180011c48  mov     rcx, rbx; String1
0x180011c4b  call    cs:__imp_wcscmp
0x180011c51  test    eax, eax
0x180011c53  jnz     short loc_180011C62
0x180011c55  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011c58  mov     rcx, r14; this
0x180011c5b  call    ?AddTargetProcess@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::AddTargetProcess(Microsoft::Json::Object &)
0x180011c60  jmp     short loc_180011CE1
0x180011c62  lea     rdx, aRemovetargetpr; "removeTargetProcess"
0x180011c69  mov     rcx, rbx; String1
0x180011c6c  call    cs:__imp_wcscmp
0x180011c72  test    eax, eax
0x180011c74  jnz     short loc_180011C83
0x180011c76  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011c79  mov     rcx, r14; this
0x180011c7c  call    ?RemoveTargetProcess@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::RemoveTargetProcess(Microsoft::Json::Object &)
0x180011c81  jmp     short loc_180011CE1
0x180011c83  lea     rdx, aEnablecounters; "enableCounters"
0x180011c8a  mov     rcx, rbx; String1
0x180011c8d  call    cs:__imp_wcscmp
0x180011c93  test    eax, eax
0x180011c95  jnz     short loc_180011CA4
0x180011c97  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011c9a  mov     rcx, r14; this
0x180011c9d  call    ?EnableCounters@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::EnableCounters(Microsoft::Json::Object &)
0x180011ca2  jmp     short loc_180011CE1
0x180011ca4  lea     rdx, aGettargetproce; "getTargetProcesses"
0x180011cab  mov     rcx, rbx; String1
0x180011cae  call    cs:__imp_wcscmp
0x180011cb4  test    eax, eax
0x180011cb6  jnz     short loc_180011CC5
0x180011cb8  mov     rdx, rdi; struct Microsoft::Json::Object *
0x180011cbb  mov     rcx, r14; this
0x180011cbe  call    ?GetTargetProcesses@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetTargetProcesses(Microsoft::Json::Object &)
0x180011cc3  jmp     short loc_180011CE1
0x180011cc5  lea     rdx, aAddusermark; "addUserMark"
0x180011ccc  mov     rcx, rbx; String1
0x180011ccf  call    cs:__imp_wcscmp
0x180011cd5  test    eax, eax
0x180011cd7  jnz     short loc_180011CE5
0x180011cd9  mov     rcx, r14; this
0x180011cdc  call    ?AddUserMark@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::AddUserMark(Microsoft::Json::Object &)
0x180011ce1  mov     esi, eax
0x180011ce3  jmp     short loc_180011D59
0x180011ce5  lea     rdx, aSetsymbolcache; "setSymbolCachePath"
0x180011cec  mov     rcx, rbx; String1
0x180011cef  call    cs:__imp_wcscmp
0x180011cf5  test    eax, eax
0x180011cf7  jnz     short loc_180011D54
0x180011cf9  mov     [rbp+bstrString], 0
0x180011d01  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180011d05  lea     rdx, aSymbolcachepat; "symbolCachePath"
0x180011d0c  mov     rcx, rdi; this
0x180011d0f  call    ?GetFieldAsString@Object@Json@Microsoft@@QEAAJPEBGPEAPEAG@Z; Microsoft::Json::Object::GetFieldAsString(ushort const *,ushort * *)
0x180011d14  mov     esi, eax
0x180011d16  test    eax, eax
0x180011d18  jns     short loc_180011D26
0x180011d1a  mov     rcx, [rbp+bstrString]; bstrString
0x180011d1e  call    cs:__imp_SysFreeString
0x180011d24  jmp     short loc_180011D59
0x180011d26  mov     rcx, [r14+60h]
0x180011d2a  mov     rax, [rcx]
0x180011d2d  mov     rdi, [rbp+bstrString]
0x180011d31  mov     rdx, rdi
0x180011d34  mov     rax, [rax+80h]
0x180011d3b  call    cs:__guard_dispatch_icall_fptr
0x180011d41  mov     esi, eax
0x180011d43  mov     rcx, rdi; bstrString
0x180011d46  test    eax, eax
0x180011d48  js      short loc_180011D1E
0x180011d4a  call    cs:__imp_SysFreeString
0x180011d50  xor     esi, esi
0x180011d52  jmp     short loc_180011D59
0x180011d54  mov     esi, 80070057h
0x180011d59  mov     rcx, rbx; bstrString
0x180011d5c  call    cs:__imp_SysFreeString
0x180011d62  nop
0x180011d63  mov     rbx, [rbp+var_10+8]
0x180011d67  test    rbx, rbx
0x180011d6a  jz      short loc_180011DA4
0x180011d6c  or      edi, 0FFFFFFFFh
0x180011d6f  mov     eax, edi
0x180011d71  lock xadd [rbx+8], eax
0x180011d76  add     eax, edi
0x180011d78  jnz     short loc_180011DA4
0x180011d7a  mov     rax, [rbx]
0x180011d7d  mov     rcx, rbx
0x180011d80  mov     rax, [rax]
0x180011d83  call    cs:__guard_dispatch_icall_fptr
0x180011d89  mov     edx, edi
0x180011d8b  lock xadd [rbx+0Ch], edx
0x180011d90  add     edx, edi
0x180011d92  jnz     short loc_180011DA4
0x180011d94  mov     rdx, [rbx]
0x180011d97  mov     rcx, rbx
0x180011d9a  mov     rax, [rdx+8]
0x180011d9e  call    cs:__guard_dispatch_icall_fptr
0x180011da4  mov     eax, esi
0x180011da6  mov     rbx, [rsp+40h+arg_10]
0x180011dab  mov     rsi, [rsp+40h+arg_18]
0x180011db0  add     rsp, 40h
0x180011db4  pop     r14
0x180011db6  pop     rdi
0x180011db7  pop     rbp
0x180011db8  retn
```
