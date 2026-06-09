# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180bfa28c`
- end: `0x180bfa360`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `HRESULT __fastcall(HSTRING__ *hstrContractId, HSTRING__ **phstrBaseActionId, HSTRING__ **hstrContractId)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180bfab40`

## callees

- `0x180bfa28c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180bfa2d5`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180bfa2d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180bfa345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180bfa2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180bfa2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180bfa31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180bfa31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180bfa305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180bfa305`

## pseudocode

```c
__int64 __fastcall SplitActionAndServiceId(HSTRING hstrContractId, HSTRING__ **phstrBaseActionId, HSTRING__ **a3)
{
  unsigned int v5; // edi
  const wchar_t *StringRawBuffer; // rax
  size_t v7; // r14
  HRESULT v8; // eax
  Microsoft::WRL::Wrappers::HString strBaseActionId; // [rsp+48h] [rbp+28h] BYREF
  HSTRING__ **cchContractId; // [rsp+50h] [rbp+30h] BYREF

  cchContractId = a3;
  if ( phstrBaseActionId )
    *phstrBaseActionId = 0;
  v5 = 0;
  strBaseActionId.hstr_ = 0;
  LODWORD(cchContractId) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(hstrContractId, (UINT32 *)&cchContractId);
  v7 = wcscspn(StringRawBuffer, c_szActionServiceDelimiter);
  if ( phstrBaseActionId )
  {
    if ( v7 >= (unsigned int)cchContractId )
    {
      WindowsDeleteString(strBaseActionId.hstr_);
      strBaseActionId.hstr_ = 0;
      v8 = WindowsDuplicateString(hstrContractId, &strBaseActionId.hstr_);
    }
    else
    {
      WindowsDeleteString(strBaseActionId.hstr_);
      strBaseActionId.hstr_ = 0;
      v8 = WindowsSubstringWithSpecifiedLength(hstrContractId, 0, v7, &strBaseActionId.hstr_);
    }
    v5 = v8;
    if ( v8 >= 0 )
    {
      *phstrBaseActionId = strBaseActionId.hstr_;
      strBaseActionId.hstr_ = 0;
    }
  }
  WindowsDeleteString(0);
  WindowsDeleteString(strBaseActionId.hstr_);
  return v5;
}

```

## disassembly

```asm
0x180bfa28c  mov     [rsp-18h+arg_0], rbx
0x180bfa291  mov     [rsp-18h+arg_18], rsi
0x180bfa296  mov     [rsp-18h+cchContractId], r8
0x180bfa29b  push    rbp
0x180bfa29c  push    rdi
0x180bfa29d  push    r14
0x180bfa29f  mov     rbp, rsp
0x180bfa2a2  sub     rsp, 20h
0x180bfa2a6  mov     rbx, phstrBaseActionId
0x180bfa2a9  mov     rsi, hstrContractId
0x180bfa2ac  test    phstrBaseActionId, phstrBaseActionId
0x180bfa2af  jz      short loc_180BFA2B8
0x180bfa2b1  mov     qword ptr [phstrBaseActionId], 0
0x180bfa2b8  xor     edi, edi
0x180bfa2ba  lea     phstrBaseActionId, [rbp+cchContractId]; length
0x180bfa2be  mov     [rbp+strBaseActionId.hstr_], rdi
0x180bfa2c2  mov     dword ptr [rbp+cchContractId], edi
0x180bfa2c5  call    cs:__imp_WindowsGetStringRawBuffer
0x180bfa2cb  mov     hstrContractId, rax; String
0x180bfa2ce  lea     phstrBaseActionId, ?c_szActionServiceDelimiter@@3QBGB; Control
0x180bfa2d5  call    cs:__imp_wcscspn
0x180bfa2db  mov     r14, rax
0x180bfa2de  test    rbx, rbx
0x180bfa2e1  jz      short loc_180BFA339
0x180bfa2e3  mov     eax, dword ptr [rbp+cchContractId]
0x180bfa2e6  mov     hstrContractId, [rbp+strBaseActionId.hstr_]; string
0x180bfa2ea  cmp     r14, rax
0x180bfa2ed  jnb     short loc_180BFA30D
0x180bfa2ef  call    cs:__imp_WindowsDeleteString
0x180bfa2f5  mov     r8d, r14d; length
0x180bfa2f8  mov     [rbp+strBaseActionId.hstr_], rdi
0x180bfa2fc  lea     r9, [rbp+strBaseActionId]; newString
0x180bfa300  xor     edx, edx; startIndex
0x180bfa302  mov     hstrContractId, rsi; string
0x180bfa305  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180bfa30b  jmp     short loc_180BFA324
0x180bfa30d  call    cs:__imp_WindowsDeleteString
0x180bfa313  lea     phstrBaseActionId, [rbp+strBaseActionId]; newString
0x180bfa317  mov     [rbp+strBaseActionId.hstr_], rdi
0x180bfa31b  mov     hstrContractId, rsi; string
0x180bfa31e  call    cs:__imp_WindowsDuplicateString
0x180bfa324  mov     edi, eax
0x180bfa326  test    eax, eax
0x180bfa328  js      short loc_180BFA339
0x180bfa32a  mov     rax, [rbp+strBaseActionId.hstr_]
0x180bfa32e  mov     [rbx], rax
0x180bfa331  mov     [rbp+strBaseActionId.hstr_], 0
0x180bfa339  xor     ecx, ecx; string
0x180bfa33b  call    cs:__imp_WindowsDeleteString
0x180bfa341  mov     hstrContractId, [rbp+strBaseActionId.hstr_]; string
0x180bfa345  call    cs:__imp_WindowsDeleteString
0x180bfa34b  mov     rbx, [rsp+20h+arg_0]
0x180bfa350  mov     eax, edi
0x180bfa352  mov     rsi, [rsp+20h+arg_18]
0x180bfa357  add     rsp, 20h
0x180bfa35b  pop     r14
0x180bfa35d  pop     rdi
0x180bfa35e  pop     rbp
0x180bfa35f  retn
```
