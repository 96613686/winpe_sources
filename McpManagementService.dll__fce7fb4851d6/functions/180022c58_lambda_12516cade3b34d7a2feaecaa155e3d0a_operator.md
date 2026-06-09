# _lambda_12516cade3b34d7a2feaecaa155e3d0a_::operator()

- ea: `0x180022c58`
- end: `0x180022d4d`
- name: `_lambda_12516cade3b34d7a2feaecaa155e3d0a_::operator()`
- size: `245`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180023250`

## callees

- `0x18000df30`
- `0x18001364c`
- `0x1800142f0`
- `0x180022000`
- `0x180022b04`
- `0x180022c58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022d3f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022d3f`

## pseudocode

```c
__int64 __fastcall lambda_12516cade3b34d7a2feaecaa155e3d0a_::operator()(__int64 *a1)
{
  _QWORD *v2; // rdx
  int AuthorizationHeaderSilent; // eax
  __int64 v4; // r9
  unsigned int v5; // ebx
  char v7; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_QWORD **)(*a1 + 232);
  if ( v2 )
    v2 = (_QWORD *)*v2;
  PrintCore::ImpersonateUserRAII::ImpersonateUserRAII((PrintCore::ImpersonateUserRAII *)&v7, v2);
  if ( *(_BYTE *)(*a1 + 24) )
  {
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetAuthorizationHeaderOperation::RuntimeClassInitialize::<lambda_12516cade3b34d7a2feaecaa155e3d0a>::operator ()",
      L"Calling CloudPrintHelper::GetAuthorizationHeaderSilent");
    AuthorizationHeaderSilent = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderSilent(
                                  (unsigned int)*a1 + 40,
                                  (unsigned int)*a1 + 72,
                                  (unsigned int)*a1 + 104,
                                  (unsigned int)*a1 + 136,
                                  *a1 + 168,
                                  *a1 + 200);
  }
  else
  {
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetAuthorizationHeaderOperation::RuntimeClassInitialize::<lambda_12516cade3b34d7a2feaecaa155e3d0a>::operator ()",
      L"Calling CloudPrintHelper::GetAuthorizationHeader");
    v4 = *a1;
    LOBYTE(v4) = *(_BYTE *)(*a1 + 25);
    AuthorizationHeaderSilent = CloudPrint::CloudPrintHelper::GetAuthorizationHeader(
                                  (unsigned int)*a1 + 40,
                                  (unsigned int)*a1 + 72,
                                  (unsigned int)*a1 + 104,
                                  v4,
                                  *(_QWORD *)(*a1 + 32),
                                  *a1 + 136,
                                  *a1 + 168,
                                  *a1 + 200);
  }
  v5 = AuthorizationHeaderSilent;
  if ( AuthorizationHeaderSilent < 0 )
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpGetAuthorizationHeaderOperation::RuntimeClassInitialize::<lambda_12516cade3b34d7a2feaecaa155e3d0a>::operator ()",
      L"CloudPrintHelper::GetAuthorizationHeader/Silent failed. hr=%#x",
      (unsigned int)AuthorizationHeaderSilent);
  SetThreadToken(0, 0);
  return v5;
}

```

## disassembly

```asm
0x180022c58  push    rbx
0x180022c5a  sub     rsp, 50h
0x180022c5e  mov     rax, [rcx]
0x180022c61  mov     rbx, rcx
0x180022c64  mov     rdx, [rax+0E8h]
0x180022c6b  test    rdx, rdx
0x180022c6e  jz      short loc_180022C73
0x180022c70  mov     rdx, [rdx]; void *
0x180022c73  lea     rcx, [rsp+58h+arg_0]; this
0x180022c78  call    ??0ImpersonateUserRAII@PrintCore@@QEAA@PEAX@Z; PrintCore::ImpersonateUserRAII::ImpersonateUserRAII(void *)
0x180022c7d  mov     rax, [rbx]
0x180022c80  lea     rcx, aMcpgetauthoriz_5; "McpGetAuthorizationHeaderOperation::Run"...
0x180022c87  cmp     byte ptr [rax+18h], 0
0x180022c8b  jz      short loc_180022CCE
0x180022c8d  lea     rdx, aCallingCloudpr_0; "Calling CloudPrintHelper::GetAuthorizat"...
0x180022c94  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180022c99  mov     rcx, [rbx]
0x180022c9c  lea     rax, [rcx+0C8h]
0x180022ca3  lea     r10, [rcx+0A8h]
0x180022caa  mov     [rsp+58h+var_30], rax
0x180022caf  lea     r9, [rcx+88h]
0x180022cb6  mov     [rsp+58h+var_38], r10
0x180022cbb  lea     r8, [rcx+68h]
0x180022cbf  lea     rdx, [rcx+48h]
0x180022cc3  add     rcx, 28h ; '('
0x180022cc7  call    ?GetAuthorizationHeaderSilent@CloudPrintHelper@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAV34@111@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderSilent(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x180022ccc  jmp     short loc_180022D1F
0x180022cce  lea     rdx, aCallingCloudpr; "Calling CloudPrintHelper::GetAuthorizat"...
0x180022cd5  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180022cda  mov     r9, [rbx]
0x180022cdd  lea     rax, [r9+0C8h]
0x180022ce4  mov     [rsp+58h+var_20], rax
0x180022ce9  lea     r10, [r9+0A8h]
0x180022cf0  mov     rax, [r9+20h]
0x180022cf4  lea     r11, [r9+88h]
0x180022cfb  mov     [rsp+58h+var_28], r10
0x180022d00  lea     r8, [r9+68h]
0x180022d04  lea     rdx, [r9+48h]
0x180022d08  mov     [rsp+58h+var_30], r11
0x180022d0d  lea     rcx, [r9+28h]
0x180022d11  mov     [rsp+58h+var_38], rax
0x180022d16  mov     r9b, [r9+19h]
0x180022d1a  call    ?GetAuthorizationHeader@CloudPrintHelper@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NPEAUHWND__@@PEAV34@333@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeader(std::wstring const &,std::wstring const &,std::wstring const &,bool,HWND__ *,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x180022d1f  mov     ebx, eax
0x180022d21  test    eax, eax
0x180022d23  jns     short loc_180022D3B
0x180022d25  mov     r8d, eax
0x180022d28  lea     rdx, aCloudprinthelp_0; "CloudPrintHelper::GetAuthorizationHeade"...
0x180022d2f  lea     rcx, aMcpgetauthoriz_5; "McpGetAuthorizationHeaderOperation::Run"...
0x180022d36  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180022d3b  xor     edx, edx; Token
0x180022d3d  xor     ecx, ecx; Thread
0x180022d3f  call    cs:__imp_SetThreadToken
0x180022d45  mov     eax, ebx
0x180022d47  add     rsp, 50h
0x180022d4b  pop     rbx
0x180022d4c  retn
```
