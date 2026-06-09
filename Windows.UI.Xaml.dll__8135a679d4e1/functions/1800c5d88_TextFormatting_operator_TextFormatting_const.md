# TextFormatting::operator=(TextFormatting const &)

- ea: `0x1800c5d88`
- end: `0x1800c612f`
- name: `??4TextFormatting@@QEAAAEAV0@AEBV0@@Z`
- size: `935`
- prototype: `TextFormatting *__fastcall(TextFormatting *this, const TextFormatting *__that)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800c5b5c`
- `0x1800c5ce8`

## callees

- `0x180004bc0`
- `0x1800ab600`
- `0x1800c5d88`
- `0x1806877a8`
- `0x180687890`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c5e64`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c5f63`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c6026`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c5e64`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c5f63`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c6026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6038`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6038`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5fd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c5fd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c60fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c6076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c6099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c60b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c6076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c6099`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c60b8`

## pseudocode

```c
TextFormatting *__fastcall TextFormatting::operator=(TextFormatting *this, const TextFormatting *__that)
{
  xstring_ptr *p_m_strLanguageString; // rsi
  const xstring_ptr_storage *Storage; // rax
  int v6; // edx
  wchar_t *Buffer; // rax
  unsigned int v8; // edx
  int v9; // eax
  xstring_ptr *p_m_strResolvedLanguageString; // rsi
  const xstring_ptr_storage *v11; // rax
  int v12; // edx
  wchar_t *StringRawBuffer; // rax
  unsigned int v14; // edx
  int v15; // eax
  xstring_ptr *p_m_strResolvedLanguageListString; // rax
  xstring_ptr *v17; // rdi
  unsigned __int64 RuntimeStringHandleMarker; // rax
  int v19; // edx
  wchar_t *v20; // rax
  unsigned int v21; // edx
  int v22; // eax
  unsigned int pcStowedExceptions; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+60h] [rbp+40h] BYREF

  p_m_strLanguageString = &this->m_strLanguageString;
  this->m_cReferences = __that->m_cReferences;
  this->m_pFontFamily = __that->m_pFontFamily;
  this->m_pForeground = __that->m_pForeground;
  this->m_pCoreInheritedPropGenerationCounter = __that->m_pCoreInheritedPropGenerationCounter;
  if ( &this->m_strLanguageString == &__that->m_strLanguageString )
    goto LABEL_12;
  Storage = __that->m_strLanguageString.m_encodedStorage.Storage;
  if ( ((unsigned __int8)Storage & 1) != 0 )
  {
    v9 = WindowsDuplicateString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL), &string);
    if ( v9 < 0 )
      goto LABEL_8;
LABEL_39:
    string = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_9;
  }
  if ( !Storage || (v6 = *((_DWORD *)Storage + 2), (v6 & 0x40000000) == 0) )
  {
    string = (HSTRING)Storage;
    goto LABEL_9;
  }
  pcStowedExceptions = 0;
  Buffer = (wchar_t *)Storage->Buffer;
  if ( v6 < 0 )
  {
    Buffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)Buffer, &pcStowedExceptions);
    v8 = pcStowedExceptions;
  }
  else
  {
    v8 = v6 & 0x3FFFFFFF;
    pcStowedExceptions = v8;
  }
  v9 = WindowsCreateString(Buffer, v8, &string);
  if ( v9 >= 0 )
    goto LABEL_39;
LABEL_8:
  OnFailure_2990_(v9);
  pppStowedExceptions = 0;
  pcStowedExceptions = 0;
  TraceForFailFast(-2147418113);
  OnNewFailureEncountered(-2147418113, 0, 0);
  GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
  RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions, pppStowedExceptions);
LABEL_9:
  if ( (p_m_strLanguageString->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
    WindowsDeleteString((HSTRING)(p_m_strLanguageString->m_encodedStorage.RuntimeStringHandleMarker
                                & 0xFFFFFFFFFFFFFFFEuLL));
  p_m_strLanguageString->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
LABEL_12:
  p_m_strResolvedLanguageString = &this->m_strResolvedLanguageString;
  this->m_cGenerationCounter = __that->m_cGenerationCounter;
  this->m_eFontSize = __that->m_eFontSize;
  this->m_nCharacterSpacing = __that->m_nCharacterSpacing;
  this->m_nFontWeight = __that->m_nFontWeight;
  this->m_nFontStyle[0] = __that->m_nFontStyle[0];
  this->m_nFontStretch[0] = __that->m_nFontStretch[0];
  this->m_nTextDecorations[0] = __that->m_nTextDecorations[0];
  this->m_nFlowDirection[0] = __that->m_nFlowDirection[0];
  this->m_isTextScaleFactorEnabled = __that->m_isTextScaleFactorEnabled;
  this->m_freezeForeground = __that->m_freezeForeground;
  if ( &this->m_strResolvedLanguageString == &__that->m_strResolvedLanguageString )
    goto LABEL_23;
  v11 = __that->m_strResolvedLanguageString.m_encodedStorage.Storage;
  if ( ((unsigned __int8)v11 & 1) != 0 )
  {
    v15 = WindowsDuplicateString((HSTRING)((unsigned __int64)v11 & 0xFFFFFFFFFFFFFFFEuLL), &string);
    if ( v15 < 0 )
      goto LABEL_19;
LABEL_41:
    string = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_20;
  }
  if ( !v11 || (v12 = *((_DWORD *)v11 + 2), (v12 & 0x40000000) == 0) )
  {
    string = __that->m_strResolvedLanguageString.m_encodedStorage.Handle;
    goto LABEL_20;
  }
  pcStowedExceptions = 0;
  StringRawBuffer = (wchar_t *)v11->Buffer;
  if ( v12 < 0 )
  {
    StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)StringRawBuffer, &pcStowedExceptions);
    v14 = pcStowedExceptions;
  }
  else
  {
    v14 = v12 & 0x3FFFFFFF;
    pcStowedExceptions = v14;
  }
  v15 = WindowsCreateString(StringRawBuffer, v14, &string);
  if ( v15 >= 0 )
    goto LABEL_41;
LABEL_19:
  OnFailure_2990_(v15);
  pppStowedExceptions = 0;
  pcStowedExceptions = 0;
  TraceForFailFast(-2147418113);
  OnNewFailureEncountered(-2147418113, 0, 0);
  GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
  RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions, pppStowedExceptions);
LABEL_20:
  if ( (p_m_strResolvedLanguageString->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
    WindowsDeleteString((HSTRING)(p_m_strResolvedLanguageString->m_encodedStorage.RuntimeStringHandleMarker
                                & 0xFFFFFFFFFFFFFFFEuLL));
  p_m_strResolvedLanguageString->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
LABEL_23:
  p_m_strResolvedLanguageListString = &__that->m_strResolvedLanguageListString;
  v17 = &this->m_strResolvedLanguageListString;
  if ( &this->m_strResolvedLanguageListString == p_m_strResolvedLanguageListString )
    return this;
  RuntimeStringHandleMarker = p_m_strResolvedLanguageListString->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v22 = WindowsDuplicateString((HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL), &string);
    if ( v22 < 0 )
      goto LABEL_30;
LABEL_43:
    string = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_31;
  }
  if ( !RuntimeStringHandleMarker || (v19 = *(_DWORD *)(RuntimeStringHandleMarker + 8), (v19 & 0x40000000) == 0) )
  {
    string = (HSTRING)RuntimeStringHandleMarker;
    goto LABEL_31;
  }
  pcStowedExceptions = 0;
  v20 = *(wchar_t **)RuntimeStringHandleMarker;
  if ( v19 < 0 )
  {
    v20 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v20, &pcStowedExceptions);
    v21 = pcStowedExceptions;
  }
  else
  {
    v21 = v19 & 0x3FFFFFFF;
    pcStowedExceptions = v21;
  }
  v22 = WindowsCreateString(v20, v21, &string);
  if ( v22 >= 0 )
    goto LABEL_43;
LABEL_30:
  OnFailure_2990_(v22);
  pppStowedExceptions = 0;
  pcStowedExceptions = 0;
  TraceForFailFast(-2147418113);
  OnNewFailureEncountered(-2147418113, 0, 0);
  GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
  RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions, pppStowedExceptions);
LABEL_31:
  if ( (v17->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
    WindowsDeleteString((HSTRING)(v17->m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
  v17->m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)string;
  return this;
}

```

## disassembly

```asm
0x1800c5d88  push    rbp
0x1800c5d8a  push    rbx
0x1800c5d8b  push    rsi
0x1800c5d8c  push    rdi
0x1800c5d8d  push    r15
0x1800c5d8f  mov     rbp, rsp
0x1800c5d92  sub     rsp, 20h
0x1800c5d96  mov     eax, [__that+8]
0x1800c5d99  lea     rsi, [this+28h]
0x1800c5d9d  mov     [this+8], eax
0x1800c5da0  mov     rdi, __that
0x1800c5da3  mov     rax, [__that+10h]
0x1800c5da7  mov     rbx, this
0x1800c5daa  mov     [this+10h], rax
0x1800c5dae  mov     r15d, 8000FFFFh
0x1800c5db4  mov     rax, [__that+18h]
0x1800c5db8  mov     [this+18h], rax
0x1800c5dbc  mov     rax, [__that+20h]
0x1800c5dc0  mov     [this+20h], rax
0x1800c5dc4  lea     rax, [__that+28h]
0x1800c5dc8  cmp     rsi, rax
0x1800c5dcb  jz      loc_1800C5E83
0x1800c5dd1  mov     rax, [rax]
0x1800c5dd4  test    al, 1
0x1800c5dd6  jnz     loc_1800C606B
0x1800c5ddc  test    rax, rax
0x1800c5ddf  jz      loc_1800C6053
0x1800c5de5  mov     edx, [rax+8]
0x1800c5de8  bt      edx, 1Eh
0x1800c5dec  jnb     loc_1800C6053
0x1800c5df2  mov     [rbp+pcStowedExceptions], 0
0x1800c5df9  mov     rax, [rax]
0x1800c5dfc  test    edx, edx
0x1800c5dfe  js      loc_1800C60CC
0x1800c5e04  and     edx, 3FFFFFFFh; length
0x1800c5e0a  mov     [rbp+pcStowedExceptions], edx
0x1800c5e0d  lea     r8, [rbp+string]; string
0x1800c5e11  mov     this, rax; sourceString
0x1800c5e14  call    cs:__imp_WindowsCreateString
0x1800c5e1a  test    eax, eax
0x1800c5e1c  jns     loc_1800C6084
0x1800c5e22  mov     ecx, eax; failedFrameHR
0x1800c5e24  call    OnFailure_2990_
0x1800c5e29  mov     ecx, r15d; errorCode
0x1800c5e2c  mov     [rbp+pppStowedExceptions], 0
0x1800c5e34  mov     [rbp+pcStowedExceptions], 0
0x1800c5e3b  call    TraceForFailFast
0x1800c5e40  xor     r8d, r8d; contextRecord
0x1800c5e43  xor     edx, edx; directCallerReturnAddress
0x1800c5e45  mov     ecx, r15d; failedFrameHR
0x1800c5e48  call    OnNewFailureEncountered
0x1800c5e4d  lea     __that, [rbp+pcStowedExceptions]; pcStowedExceptions
0x1800c5e51  lea     this, [rbp+pppStowedExceptions]; pppStowedExceptions
0x1800c5e55  call    GetStowedExceptionsForFailFast
0x1800c5e5a  mov     r8, [rbp+pppStowedExceptions]
0x1800c5e5e  mov     ecx, r15d
0x1800c5e61  mov     edx, [rbp+pcStowedExceptions]
0x1800c5e64  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800c5e6a  mov     this, [rsi]
0x1800c5e6d  test    cl, 1
0x1800c5e70  jz      short loc_1800C5E7C
0x1800c5e72  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c5e76  call    cs:__imp_WindowsDeleteString
0x1800c5e7c  mov     rax, [rbp+string]
0x1800c5e80  mov     [rsi], rax
0x1800c5e83  mov     eax, [rdi+30h]
0x1800c5e86  lea     rsi, [rbx+48h]
0x1800c5e8a  mov     [rbx+30h], eax
0x1800c5e8d  mov     eax, [rdi+34h]
0x1800c5e90  mov     [rbx+34h], eax
0x1800c5e93  mov     eax, [rdi+38h]
0x1800c5e96  mov     [rbx+38h], eax
0x1800c5e99  mov     eax, [rdi+3Ch]
0x1800c5e9c  mov     [rbx+3Ch], eax
0x1800c5e9f  mov     al, [rdi+40h]
0x1800c5ea2  mov     [rbx+40h], al
0x1800c5ea5  mov     al, [rdi+41h]
0x1800c5ea8  mov     [rbx+41h], al
0x1800c5eab  mov     al, [rdi+42h]
0x1800c5eae  mov     [rbx+42h], al
0x1800c5eb1  mov     al, [rdi+43h]
0x1800c5eb4  mov     [rbx+43h], al
0x1800c5eb7  mov     al, [rdi+44h]
0x1800c5eba  mov     [rbx+44h], al
0x1800c5ebd  mov     al, [rdi+45h]
0x1800c5ec0  mov     [rbx+45h], al
0x1800c5ec3  lea     rax, [rdi+48h]
0x1800c5ec7  cmp     rsi, rax
0x1800c5eca  jz      loc_1800C5F82
0x1800c5ed0  mov     rax, [rax]
0x1800c5ed3  test    al, 1
0x1800c5ed5  jnz     loc_1800C608E
0x1800c5edb  test    rax, rax
0x1800c5ede  jz      loc_1800C605C
0x1800c5ee4  mov     edx, [rax+8]
0x1800c5ee7  bt      edx, 1Eh
0x1800c5eeb  jnb     loc_1800C605C
0x1800c5ef1  mov     [rbp+pcStowedExceptions], 0
0x1800c5ef8  mov     rax, [rax]
0x1800c5efb  test    edx, edx
0x1800c5efd  js      loc_1800C60E1
0x1800c5f03  and     edx, 3FFFFFFFh; length
0x1800c5f09  mov     [rbp+pcStowedExceptions], edx
0x1800c5f0c  lea     r8, [rbp+string]; string
0x1800c5f10  mov     this, rax; sourceString
0x1800c5f13  call    cs:__imp_WindowsCreateString
0x1800c5f19  test    eax, eax
0x1800c5f1b  jns     loc_1800C60A3
0x1800c5f21  mov     ecx, eax; failedFrameHR
0x1800c5f23  call    OnFailure_2990_
0x1800c5f28  mov     ecx, r15d; errorCode
0x1800c5f2b  mov     [rbp+pppStowedExceptions], 0
0x1800c5f33  mov     [rbp+pcStowedExceptions], 0
0x1800c5f3a  call    TraceForFailFast
0x1800c5f3f  xor     r8d, r8d; contextRecord
0x1800c5f42  xor     edx, edx; directCallerReturnAddress
0x1800c5f44  mov     ecx, r15d; failedFrameHR
0x1800c5f47  call    OnNewFailureEncountered
0x1800c5f4c  lea     __that, [rbp+pcStowedExceptions]; pcStowedExceptions
0x1800c5f50  lea     this, [rbp+pppStowedExceptions]; pppStowedExceptions
0x1800c5f54  call    GetStowedExceptionsForFailFast
0x1800c5f59  mov     r8, [rbp+pppStowedExceptions]
0x1800c5f5d  mov     ecx, r15d
0x1800c5f60  mov     edx, [rbp+pcStowedExceptions]
0x1800c5f63  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800c5f69  mov     this, [rsi]
0x1800c5f6c  test    cl, 1
0x1800c5f6f  jz      short loc_1800C5F7B
0x1800c5f71  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c5f75  call    cs:__imp_WindowsDeleteString
0x1800c5f7b  mov     rax, [rbp+string]
0x1800c5f7f  mov     [rsi], rax
0x1800c5f82  lea     rax, [rdi+50h]
0x1800c5f86  lea     rdi, [rbx+50h]
0x1800c5f8a  cmp     rdi, rax
0x1800c5f8d  jz      loc_1800C6045
0x1800c5f93  mov     rax, [rax]
0x1800c5f96  test    al, 1
0x1800c5f98  jnz     loc_1800C60AD
0x1800c5f9e  test    rax, rax
0x1800c5fa1  jz      loc_1800C6065
0x1800c5fa7  mov     edx, [rax+8]
0x1800c5faa  bt      edx, 1Eh
0x1800c5fae  jnb     loc_1800C6065
0x1800c5fb4  mov     [rbp+pcStowedExceptions], 0
0x1800c5fbb  mov     rax, [rax]
0x1800c5fbe  test    edx, edx
0x1800c5fc0  js      loc_1800C60F6
0x1800c5fc6  and     edx, 3FFFFFFFh; length
0x1800c5fcc  mov     [rbp+pcStowedExceptions], edx
0x1800c5fcf  lea     r8, [rbp+string]; string
0x1800c5fd3  mov     this, rax; sourceString
0x1800c5fd6  call    cs:__imp_WindowsCreateString
0x1800c5fdc  test    eax, eax
0x1800c5fde  jns     loc_1800C60C2
0x1800c5fe4  mov     ecx, eax; failedFrameHR
0x1800c5fe6  call    OnFailure_2990_
0x1800c5feb  mov     ecx, r15d; errorCode
0x1800c5fee  mov     [rbp+pppStowedExceptions], 0
0x1800c5ff6  mov     [rbp+pcStowedExceptions], 0
0x1800c5ffd  call    TraceForFailFast
0x1800c6002  xor     r8d, r8d; contextRecord
0x1800c6005  xor     edx, edx; directCallerReturnAddress
0x1800c6007  mov     ecx, r15d; failedFrameHR
0x1800c600a  call    OnNewFailureEncountered
0x1800c600f  lea     __that, [rbp+pcStowedExceptions]; pcStowedExceptions
0x1800c6013  lea     this, [rbp+pppStowedExceptions]; pppStowedExceptions
0x1800c6017  call    GetStowedExceptionsForFailFast
0x1800c601c  mov     r8, [rbp+pppStowedExceptions]
0x1800c6020  mov     ecx, r15d
0x1800c6023  mov     edx, [rbp+pcStowedExceptions]
0x1800c6026  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800c602c  mov     this, [rdi]
0x1800c602f  test    cl, 1
0x1800c6032  jz      short loc_1800C603E
0x1800c6034  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c6038  call    cs:__imp_WindowsDeleteString
0x1800c603e  mov     rax, [rbp+string]
0x1800c6042  mov     [rdi], rax
0x1800c6045  mov     rax, rbx
0x1800c6048  add     rsp, 20h
0x1800c604c  pop     r15
0x1800c604e  pop     rdi
0x1800c604f  pop     rsi
0x1800c6050  pop     rbx
0x1800c6051  pop     rbp
0x1800c6052  retn
0x1800c6053  mov     [rbp+string], rax
0x1800c6057  jmp     loc_1800C5E6A
0x1800c605c  mov     [rbp+string], rax
0x1800c6060  jmp     loc_1800C5F69
0x1800c6065  mov     [rbp+string], rax
0x1800c6069  jmp     short loc_1800C602C
0x1800c606b  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c606f  lea     __that, [rbp+string]; newString
0x1800c6073  mov     this, rax; string
0x1800c6076  call    cs:__imp_WindowsDuplicateString
0x1800c607c  test    eax, eax
0x1800c607e  js      loc_1800C610B
0x1800c6084  or      [rbp+string], 1
0x1800c6089  jmp     loc_1800C5E6A
0x1800c608e  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c6092  lea     __that, [rbp+string]; newString
0x1800c6096  mov     this, rax; string
0x1800c6099  call    cs:__imp_WindowsDuplicateString
0x1800c609f  test    eax, eax
0x1800c60a1  js      short loc_1800C6117
0x1800c60a3  or      [rbp+string], 1
0x1800c60a8  jmp     loc_1800C5F69
0x1800c60ad  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c60b1  lea     __that, [rbp+string]; newString
0x1800c60b5  mov     this, rax; string
0x1800c60b8  call    cs:__imp_WindowsDuplicateString
0x1800c60be  test    eax, eax
0x1800c60c0  js      short loc_1800C6123
0x1800c60c2  or      [rbp+string], 1
0x1800c60c7  jmp     loc_1800C602C
0x1800c60cc  lea     __that, [rbp+pcStowedExceptions]; length
0x1800c60d0  mov     this, rax; string
0x1800c60d3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c60d9  mov     edx, [rbp+pcStowedExceptions]
0x1800c60dc  jmp     loc_1800C5E0D
0x1800c60e1  lea     __that, [rbp+pcStowedExceptions]; length
0x1800c60e5  mov     this, rax; string
0x1800c60e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c60ee  mov     edx, [rbp+pcStowedExceptions]
0x1800c60f1  jmp     loc_1800C5F0C
0x1800c60f6  lea     __that, [rbp+pcStowedExceptions]; length
0x1800c60fa  mov     this, rax; string
0x1800c60fd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6103  mov     edx, [rbp+pcStowedExceptions]
0x1800c6106  jmp     loc_1800C5FCF
0x1800c610b  mov     ecx, eax; failedFrameHR
0x1800c610d  call    OnFailure_2990_
0x1800c6112  jmp     loc_1800C5E29
0x1800c6117  mov     ecx, eax; failedFrameHR
0x1800c6119  call    OnFailure_2990_
0x1800c611e  jmp     loc_1800C5F28
0x1800c6123  mov     ecx, eax; failedFrameHR
0x1800c6125  call    OnFailure_2990_
0x1800c612a  jmp     loc_1800C5FEB
```
