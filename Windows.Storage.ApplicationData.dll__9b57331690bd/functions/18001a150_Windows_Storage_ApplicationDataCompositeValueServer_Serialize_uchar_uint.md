# Windows::Storage::ApplicationDataCompositeValueServer::Serialize(uchar * *,uint *)

- ea: `0x18001a150`
- end: `0x18001a30c`
- name: `?Serialize@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAPEAEPEAI@Z`
- size: `444`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, unsigned __int8 **value, unsigned int *valueBytes)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x18001a150`
- `0x180021fc4`
- `0x180024fc4`
- `0x180025004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2f6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSerializedAtomBytes` at `0x18001a17d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSerializedAtomBytes` at `0x18001a1c9`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSerializedAtomBytes` at `0x18001a17d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetSerializedAtomBytes` at `0x18001a1c9`

## string_xrefs

- `0x18001a21a`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18001a2a1`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Serialize(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        unsigned __int8 **value,
        unsigned int *valueBytes)
{
  void *v6; // rbx
  __int64 v7; // rcx
  void *v8; // rdi
  unsigned int v9; // eax
  HRESULT v11; // ebx
  signed int LastError; // eax
  HRESULT v13; // edi
  signed int v14; // eax
  void *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int bufferSize; // [rsp+50h] [rbp+8h] BYREF

  bufferSize = 0;
  if ( (unsigned int)GetSerializedAtomBytes(this->atomHandle, 0, &bufferSize) )
  {
    if ( bufferSize )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      Windows::Storage::StateABIHelpers::ReportError(v11, 0x15u);
      if ( v11 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x25Eu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
          v11,
          "GetSerializedAtomBytes %u",
          bufferSize);
    }
    else
    {
      *value = 0;
      v11 = 0;
      *valueBytes = 0;
    }
LABEL_10:
    operator delete(0);
    return (unsigned int)v11;
  }
  else
  {
    v6 = 0;
    if ( GetLastError() != 122 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    do
    {
      v8 = operator new(bufferSize);
      if ( v6 != v8 )
      {
        operator delete(v6);
        v6 = v8;
      }
      if ( !v6 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x26Cu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
          -2147024882,
          "new %u",
          bufferSize);
        goto LABEL_10;
      }
      if ( (unsigned int)GetSerializedAtomBytes(this->atomHandle, v6, &bufferSize) )
      {
        v9 = bufferSize;
        *value = (unsigned __int8 *)v6;
        *valueBytes = v9;
        operator delete(0);
        return 0;
      }
      v14 = GetLastError();
      v13 = v14;
    }
    while ( v14 == 122 );
    if ( v14 > 0 )
      v13 = (unsigned __int16)v14 | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v13, 0x15u);
    if ( v13 < 0 )
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x27Fu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v13,
        "GetSerializedAtomBytes %u",
        bufferSize);
    operator delete(v6);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18001a150  mov     rax, rsp
0x18001a153  mov     [rax+10h], rbx
0x18001a157  mov     [rax+18h], rbp
0x18001a15b  push    rsi
0x18001a15c  push    rdi
0x18001a15d  push    r14
0x18001a15f  sub     rsp, 30h
0x18001a163  mov     rsi, valueBytes
0x18001a166  mov     dword ptr [rax+8], 0
0x18001a16d  mov     r14, value
0x18001a170  lea     valueBytes, [rax+8]
0x18001a174  mov     rbp, this
0x18001a177  xor     edx, edx
0x18001a179  mov     this, [this+60h]
0x18001a17d  call    cs:__imp_GetSerializedAtomBytes
0x18001a183  test    eax, eax
0x18001a185  jnz     loc_18001A2CD
0x18001a18b  xor     ebx, ebx
0x18001a18d  call    cs:__imp_GetLastError
0x18001a193  cmp     eax, 7Ah ; 'z'
0x18001a196  jnz     loc_18001A2EC
0x18001a19c  mov     ecx, [rsp+48h+bufferSize]; cb
0x18001a1a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a1a5  mov     rdi, rax
0x18001a1a8  cmp     rbx, rax
0x18001a1ab  jz      short loc_18001A1B8
0x18001a1ad  mov     this, rbx; p
0x18001a1b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a1b5  mov     rbx, rdi
0x18001a1b8  test    rbx, rbx
0x18001a1bb  jz      short loc_18001A1FC
0x18001a1bd  mov     this, [rbp+60h]
0x18001a1c1  lea     valueBytes, [rsp+48h+bufferSize]
0x18001a1c6  mov     value, rbx
0x18001a1c9  call    cs:__imp_GetSerializedAtomBytes
0x18001a1cf  test    eax, eax
0x18001a1d1  jz      loc_18001A2F6
0x18001a1d7  mov     eax, [rsp+48h+bufferSize]
0x18001a1db  xor     ecx, ecx; p
0x18001a1dd  mov     [r14], rbx
0x18001a1e0  mov     [rsi], eax
0x18001a1e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a1e7  xor     eax, eax
0x18001a1e9  mov     rbx, [rsp+48h+arg_8]
0x18001a1ee  mov     rbp, [rsp+48h+arg_10]
0x18001a1f3  add     rsp, 30h
0x18001a1f7  pop     r14
0x18001a1f9  pop     rdi
0x18001a1fa  pop     rsi
0x18001a1fb  retn
0x18001a1fc  mov     eax, [rsp+48h+bufferSize]
0x18001a200  mov     ebx, 8007000Eh
0x18001a205  mov     [rsp+48h+var_20], eax
0x18001a209  mov     edx, 26Ch; lineNumber
0x18001a20e  lea     rax, aNewU; "new %u"
0x18001a215  mov     this, [rsp+48h]; callerReturnAddress
0x18001a21a  lea     valueBytes, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001a221  mov     r9d, ebx; hr
0x18001a224  mov     [rsp+48h+formatString], rax; formatString
0x18001a229  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a22e  xor     ecx, ecx; p
0x18001a230  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a235  mov     eax, ebx
0x18001a237  jmp     short loc_18001A1E9
0x18001a239  call    cs:__imp_GetLastError
0x18001a23f  mov     ebx, eax
0x18001a241  test    eax, eax
0x18001a243  jle     short loc_18001A24E
0x18001a245  movzx   ebx, ax
0x18001a248  or      ebx, 80070000h
0x18001a24e  mov     edx, 15h; idsValue
0x18001a253  mov     ecx, ebx; hr
0x18001a255  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18001a25a  test    ebx, ebx
0x18001a25c  jns     short loc_18001A22E
0x18001a25e  mov     eax, [rsp+48h+bufferSize]
0x18001a262  mov     edx, 25Eh
0x18001a267  mov     [rsp+48h+var_20], eax
0x18001a26b  lea     rax, aGetserializeda_0; "GetSerializedAtomBytes %u"
0x18001a272  jmp     short loc_18001A215
0x18001a274  test    eax, eax
0x18001a276  jle     short loc_18001A281
0x18001a278  movzx   edi, ax
0x18001a27b  or      edi, 80070000h
0x18001a281  mov     edx, 15h; idsValue
0x18001a286  mov     ecx, edi; hr
0x18001a288  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18001a28d  test    edi, edi
0x18001a28f  jns     short loc_18001A2BE
0x18001a291  mov     edx, [rsp+48h+bufferSize]
0x18001a295  lea     rax, aGetserializeda_0; "GetSerializedAtomBytes %u"
0x18001a29c  mov     this, [rsp+48h]; callerReturnAddress
0x18001a2a1  lea     valueBytes, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001a2a8  mov     [rsp+48h+var_20], edx
0x18001a2ac  mov     r9d, edi; hr
0x18001a2af  mov     edx, 27Fh; lineNumber
0x18001a2b4  mov     [rsp+48h+formatString], rax; formatString
0x18001a2b9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a2be  mov     this, rbx; p
0x18001a2c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a2c6  mov     eax, edi
0x18001a2c8  jmp     loc_18001A1E9
0x18001a2cd  cmp     [rsp+48h+bufferSize], 0
0x18001a2d2  jnz     loc_18001A239
0x18001a2d8  mov     qword ptr [r14], 0
0x18001a2df  xor     ebx, ebx
0x18001a2e1  mov     dword ptr [rsi], 0
0x18001a2e7  jmp     loc_18001A22E
0x18001a2ec  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "GetLastError() == ERROR_INSUFFICIENT_BUFFER")
0x18001a2f1  jmp     loc_18001A19C
0x18001a2f6  call    cs:__imp_GetLastError
0x18001a2fc  mov     edi, eax
0x18001a2fe  cmp     eax, 7Ah ; 'z'
0x18001a301  jz      loc_18001A19C
0x18001a307  jmp     loc_18001A274
```
