# DiagnosticRunner::CreateEngine(IScriptedDiagnosticExecution * *)

- ea: `0x18001ee60`
- end: `0x18001ef57`
- name: `?CreateEngine@DiagnosticRunner@@MEAAJPEAPEAUIScriptedDiagnosticExecution@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(DiagnosticRunner *this, LPVOID *ppv, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x18001ee60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ee9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ee9d`

## string_xrefs

- `0x18001eed7`: `DiagnosticRunner::CreateEngine`
- `0x18001eeed`: `Create Engine`

## pseudocode

```c
__int64 __fastcall DiagnosticRunner::CreateEngine(DiagnosticRunner *this, LPVOID *ppv, __int64 a3)
{
  unsigned int Instance; // ebx
  int v5; // r8d
  int v6; // r9d
  const char *v8; // [rsp+60h] [rbp-20h] BYREF
  const char *v9; // [rsp+68h] [rbp-18h] BYREF
  const char *v10; // [rsp+70h] [rbp-10h] BYREF
  char *v11; // [rsp+78h] [rbp-8h] BYREF
  int v12; // [rsp+A8h] [rbp+28h] BYREF
  unsigned int v13; // [rsp+B0h] [rbp+30h] BYREF
  char *v14; // [rsp+B8h] [rbp+38h] BYREF

  if ( ppv )
  {
    *ppv = 0;
    Instance = CoCreateInstance(&CLSID_CScriptedDiag, 0, 0x15u, &IID_IScriptedDiagnosticExecution, ppv);
  }
  else
  {
    Instance = -2147024809;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, ppv, a3) )
  {
    v12 = 253;
    v8 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v14 = (char *)this + 64;
    v9 = "DiagnosticRunner::CreateEngine";
    v13 = Instance;
    v10 = "Create Engine";
    v11 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)this + 64,
      (unsigned int)byte_18003270D,
      v5,
      v6,
      (__int64)&v11,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v9,
      (__int64)&v8,
      (__int64)&v12,
      (__int64)&v14);
  }
  return Instance;
}

```

## disassembly

```asm
0x18001ee60  push    rbp
0x18001ee62  push    rbx
0x18001ee63  push    rdi
0x18001ee64  mov     rbp, rsp
0x18001ee67  sub     rsp, 80h
0x18001ee6e  mov     rdi, rcx
0x18001ee71  test    rdx, rdx
0x18001ee74  jnz     short loc_18001EE7D
0x18001ee76  mov     ebx, 80070057h
0x18001ee7b  jmp     short loc_18001EEA5
0x18001ee7d  mov     qword ptr [rdx], 0
0x18001ee84  lea     r9, IID_IScriptedDiagnosticExecution; riid
0x18001ee8b  mov     [rsp+80h+ppv], rdx; ppv
0x18001ee90  lea     rcx, CLSID_CScriptedDiag; rclsid
0x18001ee97  xor     edx, edx; pUnkOuter
0x18001ee99  lea     r8d, [rdx+15h]; dwClsContext
0x18001ee9d  call    cs:__imp_CoCreateInstance
0x18001eea3  mov     ebx, eax
0x18001eea5  mov     ecx, cs:dword_180039000
0x18001eeab  cmp     ecx, 5
0x18001eeae  jbe     loc_18001EF4A
0x18001eeb4  call    _tlgKeywordOn
0x18001eeb9  test    al, al
0x18001eebb  jz      loc_18001EF4A
0x18001eec1  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001eec8  mov     [rbp+arg_8], 0FDh
0x18001eecf  mov     [rbp+var_20], rax
0x18001eed3  lea     rcx, [rdi+40h]
0x18001eed7  lea     rax, aDiagnosticrunn_10; "DiagnosticRunner::CreateEngine"
0x18001eede  mov     [rbp+arg_18], rcx
0x18001eee2  mov     [rbp+var_18], rax
0x18001eee6  lea     rdx, byte_18003270D
0x18001eeed  lea     rax, aCreateEngine; "Create Engine"
0x18001eef4  mov     [rbp+arg_10], ebx
0x18001eef7  mov     [rbp+var_10], rax
0x18001eefb  lea     rax, [rdi+0C1h]
0x18001ef02  mov     [rbp+var_8], rax
0x18001ef06  lea     rax, [rbp+arg_18]
0x18001ef0a  mov     [rsp+80h+var_30], rax
0x18001ef0f  lea     rax, [rbp+arg_8]
0x18001ef13  mov     [rsp+80h+var_38], rax
0x18001ef18  lea     rax, [rbp+var_20]
0x18001ef1c  mov     [rsp+80h+var_40], rax
0x18001ef21  lea     rax, [rbp+var_18]
0x18001ef25  mov     [rsp+80h+var_48], rax
0x18001ef2a  lea     rax, [rbp+var_10]
0x18001ef2e  mov     [rsp+80h+var_50], rax
0x18001ef33  lea     rax, [rbp+arg_10]
0x18001ef37  mov     [rsp+80h+var_58], rax
0x18001ef3c  lea     rax, [rbp+var_8]
0x18001ef40  mov     [rsp+80h+ppv], rax
0x18001ef45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ef4a  mov     eax, ebx
0x18001ef4c  add     rsp, 80h
0x18001ef53  pop     rdi
0x18001ef54  pop     rbx
0x18001ef55  pop     rbp
0x18001ef56  retn
```
