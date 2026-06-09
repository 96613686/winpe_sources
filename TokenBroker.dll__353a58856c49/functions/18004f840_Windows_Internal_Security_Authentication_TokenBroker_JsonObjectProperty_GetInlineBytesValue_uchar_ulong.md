# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetInlineBytesValue(uchar * *,ulong *)

- ea: `0x18004f840`
- end: `0x18004fc6c`
- name: `?GetInlineBytesValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEBAJPEAPEAEPEAK@Z`
- size: `1068`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a790`
- `0x180037330`
- `0x18004f7ec`

## callees

- `0x18000bd40`
- `0x18004f840`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004f9ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004f9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fa72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fa72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fafb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004f9d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004f9d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fa40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fa40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fa91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fa91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fc3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004fa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004faba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004fa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004faba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004f99a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004fbbc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004f99a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004fbbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fb13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fc13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fb13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004fc13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004faa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004faa7`
- `CRYPT32!CryptUnprotectData` at `0x18004fbfd`
- `CRYPT32!CryptUnprotectData` at `0x18004fbfd`
- `CRYPT32!CryptStringToBinaryW` at `0x18004fa68`
- `CRYPT32!CryptStringToBinaryW` at `0x18004faf1`
- `CRYPT32!CryptStringToBinaryW` at `0x18004fa68`
- `CRYPT32!CryptStringToBinaryW` at `0x18004faf1`

## string_xrefs

- `0x18004fa12`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::GetInlineBytesValue(
        HSTRING *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  PCWSTR StringRawBuffer; // rcx
  __int64 v7; // rax
  int v8; // eax
  HSTRING v10; // rbx
  __int64 (__fastcall *v11)(HSTRING, HSTRING, HSTRING *); // rsi
  int v12; // eax
  unsigned int v13; // r15d
  DWORD StringLen; // ebx
  const WCHAR *v15; // rax
  signed int LastError; // eax
  unsigned int v17; // ebx
  BYTE *v18; // rsi
  DWORD v19; // ebx
  const WCHAR *v20; // rax
  signed int v21; // eax
  unsigned __int8 *Keyword; // rbx
  DWORD v23; // eax
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  DWORD pcbBinary; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+6Ch] [rbp-94h] BYREF
  EVENT_DESCRIPTOR v31; // [rsp+70h] [rbp-90h] BYREF
  DATA_BLOB pDataIn; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  int *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  const char *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  int *v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  PCWSTR v45; // [rsp+100h] [rbp+0h]
  int v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+10Ch] [rbp+Ch]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  if ( *(_DWORD *)this != 2 )
  {
    if ( (unsigned int)dword_180175000 > 3 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(this[2], 0);
      v29 = *(_DWORD *)this;
      v30 = -2147023092;
      if ( StringRawBuffer )
      {
        v7 = -1;
        do
          ++v7;
        while ( StringRawBuffer[v7] );
        v8 = 2 * v7 + 2;
      }
      else
      {
        StringRawBuffer = &word_1801330B0;
        v8 = 2;
      }
      v45 = StringRawBuffer;
      v46 = v8;
      v47 = 0;
      v43 = &v29;
      v44 = 4;
      v41 = "The property is not an inline bytes value";
      v42 = 42;
      v39 = &v30;
      v40 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 3;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180175008;
      UserData.Size = *(unsigned __int16 *)off_180175008;
      UserData.Reserved = 2;
      v36 = byte_18015A1ED;
      v37 = 81;
      v38 = 1;
      v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    return 2147944204LL;
  }
  v26 = 0;
  v10 = this[1];
  v11 = *(__int64 (__fastcall **)(HSTRING, HSTRING, HSTRING *))(*(_QWORD *)v10 + 80LL);
  if ( WindowsCreateStringReference(L"Value", 5u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v12 = v11(v10, string, &v26);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v12,
      UserDataCount);
LABEL_32:
    if ( v26 )
      WindowsDeleteString(v26);
    return v13;
  }
  pcbBinary = 0;
  StringLen = WindowsGetStringLen(v26);
  v15 = WindowsGetStringRawBuffer(v26, 0);
  if ( !CryptStringToBinaryW(v15, StringLen, 6u, 0, &pcbBinary, 0, 0)
    || (v18 = (BYTE *)LocalAlloc(0x40u, pcbBinary)) == 0 )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  v19 = WindowsGetStringLen(v26);
  v20 = WindowsGetStringRawBuffer(v26, 0);
  if ( CryptStringToBinaryW(v20, v19, 6u, v18, &pcbBinary, 0, 0) )
  {
    if ( *((_BYTE *)this + 4) )
    {
      if ( (unsigned int)dword_180175000 > 5 )
      {
        *(_DWORD *)&v31.Id = 184549376;
        *(_DWORD *)&v31.Level = 5;
        v31.Keyword = 0;
        string = (HSTRING)off_180175008;
        hstringHeader.Reserved.Reserved1 = (PVOID)(*(unsigned __int16 *)off_180175008 | 0x200000000LL);
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &word_18015A1B6;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0x10000002BLL;
        v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &v31, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&string);
      }
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.pbData = v18;
      pDataIn.cbData = pcbBinary;
      *(_QWORD *)&EventDescriptor.Id = 0;
      EventDescriptor.Keyword = 0;
      if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, (DATA_BLOB *)&EventDescriptor) )
        goto LABEL_22;
      Keyword = (unsigned __int8 *)EventDescriptor.Keyword;
      LocalFree(v18);
      v23 = *(_DWORD *)&EventDescriptor.Id;
      pcbBinary = *(_DWORD *)&EventDescriptor.Id;
    }
    else
    {
      Keyword = v18;
      v23 = pcbBinary;
    }
    *a2 = Keyword;
    *a3 = v23;
    goto LABEL_32;
  }
LABEL_22:
  v21 = GetLastError();
  v17 = v21;
  if ( v21 > 0 )
    v17 = (unsigned __int16)v21 | 0x80070000;
  LocalFree(v18);
LABEL_17:
  if ( v26 )
    WindowsDeleteString(v26);
  return v17;
}

```

## disassembly

```asm
0x18004f840  mov     [rsp-8+arg_18], rbx
0x18004f845  push    rbp
0x18004f846  push    rsi
0x18004f847  push    rdi
0x18004f848  push    r12
0x18004f84a  push    r13
0x18004f84c  push    r14
0x18004f84e  push    r15
0x18004f850  lea     rbp, [rsp-20h]
0x18004f855  sub     rsp, 120h
0x18004f85c  mov     rax, cs:__security_cookie
0x18004f863  xor     rax, rsp
0x18004f866  mov     [rbp+50h+var_40], rax
0x18004f86a  mov     r13, r8
0x18004f86d  mov     r12, rdx
0x18004f870  mov     r14, rcx
0x18004f873  cmp     dword ptr [rcx], 2
0x18004f876  jz      loc_18004F9AA
0x18004f87c  mov     eax, cs:dword_180175000
0x18004f882  cmp     eax, 3
0x18004f885  jbe     loc_18004F9A0
0x18004f88b  xor     edx, edx; length
0x18004f88d  mov     rcx, [rcx+10h]; string
0x18004f891  call    cs:__imp_WindowsGetStringRawBuffer
0x18004f897  mov     rcx, rax
0x18004f89a  mov     eax, [r14]
0x18004f89d  mov     [rsp+150h+var_E8], eax
0x18004f8a1  mov     [rsp+150h+var_E4], 8007070Ch
0x18004f8a9  test    rcx, rcx
0x18004f8ac  jz      short loc_18004F8C9
0x18004f8ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004f8b5  lea     rax, [rax+1]
0x18004f8b9  cmp     word ptr [rcx+rax*2], 0
0x18004f8be  jnz     short loc_18004F8B5
0x18004f8c0  lea     eax, ds:2[rax*2]
0x18004f8c7  jmp     short loc_18004F8D5
0x18004f8c9  lea     rcx, word_1801330B0
0x18004f8d0  mov     eax, 2
0x18004f8d5  mov     [rbp+50h+var_50], rcx
0x18004f8d9  mov     [rbp+50h+var_48], eax
0x18004f8dc  xor     edi, edi
0x18004f8de  mov     [rbp+50h+var_44], edi
0x18004f8e1  lea     rax, [rsp+150h+var_E8]
0x18004f8e6  mov     [rbp+50h+var_60], rax
0x18004f8ea  mov     [rbp+50h+var_58], 4
0x18004f8f2  lea     rax, aThePropertyIsN_1; "The property is not an inline bytes val"...
0x18004f8f9  mov     [rbp+50h+var_70], rax
0x18004f8fd  mov     [rbp+50h+var_68], 2Ah ; '*'
0x18004f905  lea     rax, [rsp+150h+var_E4]
0x18004f90a  mov     [rbp+50h+var_80], rax
0x18004f90e  mov     [rbp+50h+var_78], 4
0x18004f916  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18004f91e  movzx   eax, cs:word_18015A1E3
0x18004f925  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18004f929  mov     [rsp+150h+EventDescriptor.Keyword], rdi
0x18004f92e  mov     rax, cs:off_180175008
0x18004f935  mov     [rbp+50h+var_A0.Ptr], rax
0x18004f939  movzx   eax, word ptr [rax]
0x18004f93c  mov     [rbp+50h+var_A0.Size], eax
0x18004f93f  mov     dword ptr [rbp+50h+var_A0.0Ch], 2
0x18004f946  lea     rax, byte_18015A1ED
0x18004f94d  mov     [rbp+50h+var_90], rax
0x18004f951  mov     [rbp+50h+var_88], 51h ; 'Q'
0x18004f958  mov     [rbp+50h+var_84], 1
0x18004f95f  lea     rcx, _TraceLoggingMetadataEnd
0x18004f966  lea     rax, _TraceLoggingMetadata
0x18004f96d  sub     ecx, eax
0x18004f96f  mov     [rsp+150h+var_100], ecx
0x18004f973  mov     ecx, [rsp+150h+var_100]
0x18004f977  lea     rcx, [rbp+50h+var_A0]
0x18004f97b  mov     [rsp+150h+UserData], rcx; UserData
0x18004f980  mov     [rsp+150h+UserDataCount], 6; UserDataCount
0x18004f988  xor     r9d, r9d; RelatedActivityId
0x18004f98b  xor     r8d, r8d; ActivityId
0x18004f98e  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18004f993  mov     rcx, cs:RegHandle; RegHandle
0x18004f99a  call    cs:__imp_EventWriteTransfer
0x18004f9a0  mov     eax, 8007070Ch
0x18004f9a5  jmp     loc_18004FC45
0x18004f9aa  xor     edi, edi
0x18004f9ac  mov     [rsp+150h+var_108], rdi
0x18004f9b1  mov     rbx, [rcx+8]
0x18004f9b5  mov     rax, [rbx]
0x18004f9b8  mov     rsi, [rax+50h]
0x18004f9bc  lea     r9, [rbp+50h+string]; string
0x18004f9c0  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18004f9c4  mov     edx, 5; length
0x18004f9c9  lea     rcx, aValue; "Value"
0x18004f9d0  call    cs:__imp_WindowsCreateStringReference
0x18004f9d6  test    eax, eax
0x18004f9d8  jns     short loc_18004F9F0
0x18004f9da  xor     r9d, r9d; lpArguments
0x18004f9dd  xor     r8d, r8d; nNumberOfArguments
0x18004f9e0  mov     edx, 1; dwExceptionFlags
0x18004f9e5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004f9ea  call    cs:__imp_RaiseException
0x18004f9f0  lea     r8, [rsp+150h+var_108]
0x18004f9f5  mov     rdx, [rbp+50h+string]
0x18004f9f9  mov     rcx, rbx
0x18004f9fc  mov     rax, rsi
0x18004f9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa04  mov     r15d, eax
0x18004fa07  test    eax, eax
0x18004fa09  jns     short loc_18004FA28
0x18004fa0b  mov     rcx, [rbp+58h]; this
0x18004fa0f  mov     r9d, eax; char *
0x18004fa12  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18004fa19  mov     edx, 21Eh; void *
0x18004fa1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fa23  jmp     loc_18004FC32
0x18004fa28  mov     [rsp+150h+pcbBinary], edi
0x18004fa2c  mov     rcx, [rsp+150h+var_108]; string
0x18004fa31  call    cs:__imp_WindowsGetStringLen
0x18004fa37  mov     ebx, eax
0x18004fa39  xor     edx, edx; length
0x18004fa3b  mov     rcx, [rsp+150h+var_108]; string
0x18004fa40  call    cs:__imp_WindowsGetStringRawBuffer
0x18004fa46  mov     [rsp+150h+pdwFlags], rdi; pdwFlags
0x18004fa4b  mov     [rsp+150h+UserData], rdi; pdwSkip
0x18004fa50  lea     rcx, [rsp+150h+pcbBinary]
0x18004fa55  mov     qword ptr [rsp+150h+UserDataCount], rcx; pcbBinary
0x18004fa5a  xor     r9d, r9d; pbBinary
0x18004fa5d  mov     r8d, 6; dwFlags
0x18004fa63  mov     edx, ebx; cchString
0x18004fa65  mov     rcx, rax; pszString
0x18004fa68  call    cs:__imp_CryptStringToBinaryW
0x18004fa6e  test    eax, eax
0x18004fa70  jnz     short loc_18004FA9E
0x18004fa72  call    cs:__imp_GetLastError
0x18004fa78  test    eax, eax
0x18004fa7a  mov     ebx, eax
0x18004fa7c  jle     short loc_18004FA87
0x18004fa7e  movzx   ebx, ax
0x18004fa81  or      ebx, 80070000h
0x18004fa87  mov     rcx, [rsp+150h+var_108]; string
0x18004fa8c  test    rcx, rcx
0x18004fa8f  jz      short loc_18004FA97
0x18004fa91  call    cs:__imp_WindowsDeleteString
0x18004fa97  mov     eax, ebx
0x18004fa99  jmp     loc_18004FC45
0x18004fa9e  mov     edx, [rsp+150h+pcbBinary]; uBytes
0x18004faa2  mov     ecx, 40h ; '@'; uFlags
0x18004faa7  call    cs:__imp_LocalAlloc
0x18004faad  mov     rsi, rax
0x18004fab0  test    rax, rax
0x18004fab3  jz      short loc_18004FA72
0x18004fab5  mov     rcx, [rsp+150h+var_108]; string
0x18004faba  call    cs:__imp_WindowsGetStringLen
0x18004fac0  mov     ebx, eax
0x18004fac2  xor     edx, edx; length
0x18004fac4  mov     rcx, [rsp+150h+var_108]; string
0x18004fac9  call    cs:__imp_WindowsGetStringRawBuffer
0x18004facf  mov     [rsp+150h+pdwFlags], rdi; pdwFlags
0x18004fad4  mov     [rsp+150h+UserData], rdi; pdwSkip
0x18004fad9  lea     rcx, [rsp+150h+pcbBinary]
0x18004fade  mov     qword ptr [rsp+150h+UserDataCount], rcx; pcbBinary
0x18004fae3  mov     r9, rsi; pbBinary
0x18004fae6  mov     r8d, 6; dwFlags
0x18004faec  mov     edx, ebx; cchString
0x18004faee  mov     rcx, rax; pszString
0x18004faf1  call    cs:__imp_CryptStringToBinaryW
0x18004faf7  test    eax, eax
0x18004faf9  jnz     short loc_18004FB1E
0x18004fafb  call    cs:__imp_GetLastError
0x18004fb01  test    eax, eax
0x18004fb03  mov     ebx, eax
0x18004fb05  jle     short loc_18004FB10
0x18004fb07  movzx   ebx, ax
0x18004fb0a  or      ebx, 80070000h
0x18004fb10  mov     rcx, rsi; hMem
0x18004fb13  call    cs:__imp_LocalFree
0x18004fb19  jmp     loc_18004FA87
0x18004fb1e  cmp     byte ptr [r14+4], 0
0x18004fb23  jz      loc_18004FC23
0x18004fb29  mov     eax, cs:dword_180175000
0x18004fb2f  cmp     eax, 5
0x18004fb32  jbe     loc_18004FBC2
0x18004fb38  mov     dword ptr [rsp+150h+var_E0.Id], 0B000000h
0x18004fb40  movzx   eax, cs:word_18015A1AC
0x18004fb47  mov     dword ptr [rsp+150h+var_E0.Level], eax
0x18004fb4b  mov     [rsp+150h+var_E0.Keyword], rdi
0x18004fb50  mov     rax, cs:off_180175008
0x18004fb57  mov     [rbp+50h+string], rax
0x18004fb5b  movzx   eax, word ptr [rax]
0x18004fb5e  mov     dword ptr [rbp+50h+hstringHeader.Reserved], eax
0x18004fb61  mov     dword ptr [rbp+50h+hstringHeader.Reserved+4], 2
0x18004fb68  lea     rax, word_18015A1B6
0x18004fb6f  mov     qword ptr [rbp+50h+hstringHeader.Reserved+8], rax
0x18004fb73  mov     dword ptr [rbp+50h+hstringHeader.Reserved+10h], 2Bh ; '+'
0x18004fb7a  mov     dword ptr [rbp+50h+hstringHeader.Reserved+14h], 1
0x18004fb81  lea     rcx, _TraceLoggingMetadataEnd
0x18004fb88  lea     rax, _TraceLoggingMetadata
0x18004fb8f  sub     ecx, eax
0x18004fb91  mov     [rsp+150h+var_100], ecx
0x18004fb95  mov     eax, [rsp+150h+var_100]
0x18004fb99  lea     rax, [rbp+50h+string]
0x18004fb9d  mov     [rsp+150h+UserData], rax; UserData
0x18004fba2  mov     [rsp+150h+UserDataCount], 2; UserDataCount
0x18004fbaa  xor     r9d, r9d; RelatedActivityId
0x18004fbad  xor     r8d, r8d; ActivityId
0x18004fbb0  lea     rdx, [rsp+150h+var_E0]; EventDescriptor
0x18004fbb5  mov     rcx, cs:RegHandle; RegHandle
0x18004fbbc  call    cs:__imp_EventWriteTransfer
0x18004fbc2  mov     dword ptr [rbp+50h+pDataIn+4], edi
0x18004fbc5  mov     [rbp+50h+pDataIn.pbData], rsi
0x18004fbc9  mov     eax, [rsp+150h+pcbBinary]
0x18004fbcd  mov     [rbp+50h+pDataIn.cbData], eax
0x18004fbd0  mov     qword ptr [rsp+150h+EventDescriptor.Id], rdi
0x18004fbd5  mov     [rsp+150h+EventDescriptor.Keyword], rdi
0x18004fbda  lea     rax, [rsp+150h+EventDescriptor]
0x18004fbdf  mov     [rsp+150h+pdwFlags], rax; pDataOut
0x18004fbe4  mov     dword ptr [rsp+150h+UserData], 1; dwFlags
0x18004fbec  mov     qword ptr [rsp+150h+UserDataCount], rdi; pPromptStruct
0x18004fbf1  xor     r9d, r9d; pvReserved
0x18004fbf4  xor     r8d, r8d; pOptionalEntropy
0x18004fbf7  xor     edx, edx; ppszDataDescr
0x18004fbf9  lea     rcx, [rbp+50h+pDataIn]; pDataIn
0x18004fbfd  call    cs:__imp_CryptUnprotectData
0x18004fc03  test    eax, eax
0x18004fc05  jz      loc_18004FAFB
0x18004fc0b  mov     rbx, [rsp+150h+EventDescriptor.Keyword]
0x18004fc10  mov     rcx, rsi; hMem
0x18004fc13  call    cs:__imp_LocalFree
0x18004fc19  mov     eax, dword ptr [rsp+150h+EventDescriptor.Id]
0x18004fc1d  mov     [rsp+150h+pcbBinary], eax
0x18004fc21  jmp     short loc_18004FC2A
0x18004fc23  mov     rbx, rsi
0x18004fc26  mov     eax, [rsp+150h+pcbBinary]
0x18004fc2a  mov     [r12], rbx
0x18004fc2e  mov     [r13+0], eax
0x18004fc32  mov     rcx, [rsp+150h+var_108]; string
0x18004fc37  test    rcx, rcx
0x18004fc3a  jz      short loc_18004FC42
0x18004fc3c  call    cs:__imp_WindowsDeleteString
0x18004fc42  mov     eax, r15d
0x18004fc45  mov     rcx, [rbp+50h+var_40]
0x18004fc49  xor     rcx, rsp; StackCookie
0x18004fc4c  call    __security_check_cookie
0x18004fc51  mov     rbx, [rsp+150h+arg_18]
0x18004fc59  add     rsp, 120h
0x18004fc60  pop     r15
0x18004fc62  pop     r14
0x18004fc64  pop     r13
0x18004fc66  pop     r12
0x18004fc68  pop     rdi
0x18004fc69  pop     rsi
0x18004fc6a  pop     rbp
0x18004fc6b  retn
```
