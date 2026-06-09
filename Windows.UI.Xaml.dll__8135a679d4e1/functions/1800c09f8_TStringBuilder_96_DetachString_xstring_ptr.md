# TStringBuilder<96>::DetachString(xstring_ptr *)

- ea: `0x1800c09f8`
- end: `0x1800c0bc1`
- name: `?DetachString@?$TStringBuilder@$0GA@@@QEAAJPEAVxstring_ptr@@@Z`
- size: `457`
- prototype: `HRESULT __fastcall(TStringBuilder<96> *this, xstring_ptr *pstrDetachedString)`
- caller_count: `41`
- callee_count: `4`
- tags: ``

## callers

- `0x1800947dc`
- `0x1800bf8e0`
- `0x1800c039c`
- `0x1800c0bc8`
- `0x1800c0fdc`
- `0x180181db0`
- `0x180182860`
- `0x180183414`
- `0x180193888`
- `0x1801953d8`
- `0x180195524`
- `0x1801d5170`
- `0x18030798c`
- `0x1803091bc`
- `0x18037a5b0`
- `0x1804b1c50`
- `0x1804b9c80`
- `0x1804c52f0`
- `0x180519890`
- `0x180519c78`
- `0x180560360`
- `0x1805da6f4`
- `0x1805e56dc`
- `0x180646e30`
- `0x1806bfdc0`
- `0x180778b18`
- `0x1807795d0`
- `0x1807972e8`
- `0x1808029e4`
- `0x1808037f0`
- `0x180806a98`
- `0x180807b40`
- `0x180807d10`
- `0x1808142a0`
- `0x1809a9d1c`
- `0x1809cf240`
- `0x1809d3dc0`
- `0x1809d44e0`
- `0x1809d46d0`
- `0x180a229c0`
- `0x180a29dfc`

## callees

- `0x180004bc0`
- `0x1800c09f8`
- `0x180363614`
- `0x1806b2e84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0b46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0b46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c0a44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c0b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c0a44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c0b19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1800c0ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x1800c0ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0aed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0aed`

## pseudocode

```c
__int64 __fastcall TStringBuilder<96>::DetachString(TStringBuilder<96> *this, xstring_ptr *pstrDetachedString)
{
  UINT32 m_cActual; // ebx
  wchar_t *m_inlineBuffer; // r15
  int v6; // eax
  HRESULT v7; // esi
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  unsigned __int64 v9; // rbx
  unsigned int v10; // ebx
  HSTRING_BUFFER__ *m_hPreallocatedBuffer; // rcx
  int v13; // eax
  HSTRING__ *v14; // rcx
  UINT32 v15; // esi
  HRESULT v16; // ecx
  int v17; // eax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rsi
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-10h]
  HSTRING__ *promotedBufferHandle; // [rsp+70h] [rbp+38h] BYREF

  m_cActual = this->m_cActual;
  if ( !m_cActual )
  {
    v10 = 0;
    if ( (pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
      WindowsDeleteString((HSTRING)(pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker
                                  & 0xFFFFFFFFFFFFFFFEuLL));
    m_inlineBuffer = this->m_inlineBuffer;
    pstrDetachedString->m_encodedStorage = xstring_ptr_constants::c_xencoded_string_ptr_null;
    goto LABEL_8;
  }
  m_inlineBuffer = this->m_inlineBuffer;
  if ( this->m_pBuffer == this->m_inlineBuffer )
  {
    string = 0;
    v21 = 0;
    if ( m_cActual > 0x3FFFFFFF )
    {
      v10 = -2147467259;
      v7 = -2147467259;
      OnNewFailure_1208_((HRESULT)this);
    }
    else
    {
      v6 = WindowsCreateString(this->m_pBuffer, m_cActual, &string);
      v7 = v6;
      if ( v6 >= 0 )
      {
        RuntimeStringHandleMarker = pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker;
        v21 = m_cActual & 0x3FFFFFFF | 0x80000000;
        v9 = (unsigned __int64)string | 1;
        if ( (RuntimeStringHandleMarker & 1) != 0 )
          WindowsDeleteString((HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
        pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker = v9;
        v10 = v7;
        goto LABEL_8;
      }
      OnFailure_2990_(v6);
      v10 = v7;
    }
    OnFailure_2990_(v7);
    return v10;
  }
  m_hPreallocatedBuffer = this->m_hPreallocatedBuffer;
  promotedBufferHandle = 0;
  v13 = WindowsPromoteStringBuffer(m_hPreallocatedBuffer, &promotedBufferHandle);
  v10 = v13;
  if ( v13 < 0 )
  {
    OnFailure_2990_(v13);
    return v10;
  }
  v14 = promotedBufferHandle;
  v15 = this->m_cActual;
  this->m_hPreallocatedBuffer = 0;
  if ( WindowsGetStringLen(v14) == v15 )
  {
    v10 = xstring_ptr::CloneRuntimeStringHandle(promotedBufferHandle, pstrDetachedString);
  }
  else
  {
    string = 0;
    v21 = 0;
    if ( v15 > 0x3FFFFFFF )
    {
      v10 = -2147467259;
      OnNewFailure_1208_(v16);
    }
    else
    {
      v17 = WindowsCreateString(this->m_pBuffer, v15, &string);
      v10 = v17;
      if ( v17 < 0 )
      {
        OnFailure_2990_(v17);
      }
      else
      {
        v18 = pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker;
        v21 = v15 & 0x3FFFFFFF | 0x80000000;
        v19 = (unsigned __int64)string | 1;
        if ( (v18 & 1) != 0 )
          WindowsDeleteString((HSTRING)(v18 & 0xFFFFFFFFFFFFFFFEuLL));
        pstrDetachedString->m_encodedStorage.RuntimeStringHandleMarker = v19;
      }
    }
  }
  WindowsDeleteString(promotedBufferHandle);
  if ( (v10 & 0x80000000) != 0 )
  {
    OnFailure_2990_(v10);
    return v10;
  }
LABEL_8:
  this->m_pBuffer = m_inlineBuffer;
  *(_QWORD *)&this->m_cBuffer = 96;
  return v10;
}

```

## disassembly

```asm
0x1800c09f8  push    rbp
0x1800c09fa  push    rbx
0x1800c09fb  push    rsi
0x1800c09fc  push    rdi
0x1800c09fd  push    r14
0x1800c09ff  push    r15
0x1800c0a01  mov     rbp, rsp
0x1800c0a04  sub     rsp, 38h
0x1800c0a08  mov     ebx, [this+14h]
0x1800c0a0b  mov     r14, pstrDetachedString
0x1800c0a0e  mov     rdi, this
0x1800c0a11  test    ebx, ebx
0x1800c0a13  jz      loc_1800C0A9A
0x1800c0a19  lea     r15, [this+18h]
0x1800c0a1d  cmp     [this], r15
0x1800c0a20  jnz     loc_1800C0ABE
0x1800c0a26  xor     eax, eax
0x1800c0a28  mov     [rbp+string], rax
0x1800c0a2c  mov     [rbp+var_10], eax
0x1800c0a2f  cmp     ebx, 3FFFFFFFh
0x1800c0a35  ja      loc_1800C0B8B
0x1800c0a3b  mov     this, [this]; sourceString
0x1800c0a3e  lea     r8, [rbp+string]; string
0x1800c0a42  mov     edx, ebx; length
0x1800c0a44  call    cs:__imp_WindowsCreateString
0x1800c0a4a  mov     esi, eax
0x1800c0a4c  test    eax, eax
0x1800c0a4e  js      loc_1800C0B6D
0x1800c0a54  mov     this, [r14]
0x1800c0a57  and     ebx, 3FFFFFFFh
0x1800c0a5d  bts     ebx, 1Fh
0x1800c0a61  mov     [rbp+var_10], ebx
0x1800c0a64  mov     rbx, [rbp+string]
0x1800c0a68  or      rbx, 1
0x1800c0a6c  test    cl, 1
0x1800c0a6f  jz      short loc_1800C0A7B
0x1800c0a71  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c0a75  call    cs:__imp_WindowsDeleteString
0x1800c0a7b  mov     [r14], rbx
0x1800c0a7e  mov     ebx, esi
0x1800c0a80  mov     [rdi], r15
0x1800c0a83  mov     qword ptr [rdi+10h], 60h ; '`'
0x1800c0a8b  mov     eax, ebx
0x1800c0a8d  add     rsp, 38h
0x1800c0a91  pop     r15
0x1800c0a93  pop     r14
0x1800c0a95  pop     rdi
0x1800c0a96  pop     rsi
0x1800c0a97  pop     rbx
0x1800c0a98  pop     rbp
0x1800c0a99  retn
0x1800c0a9a  mov     this, [pstrDetachedString]
0x1800c0a9d  xor     ebx, ebx
0x1800c0a9f  test    cl, 1
0x1800c0aa2  jz      short loc_1800C0AAE
0x1800c0aa4  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c0aa8  call    cs:__imp_WindowsDeleteString
0x1800c0aae  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x1800c0ab5  lea     r15, [rdi+18h]
0x1800c0ab9  mov     [r14], rax
0x1800c0abc  jmp     short loc_1800C0A80
0x1800c0abe  mov     this, [this+8]; bufferHandle
0x1800c0ac2  lea     pstrDetachedString, [rbp+promotedBufferHandle]; string
0x1800c0ac6  mov     [rbp+promotedBufferHandle], 0
0x1800c0ace  call    cs:__imp_WindowsPromoteStringBuffer
0x1800c0ad4  mov     ebx, eax
0x1800c0ad6  test    eax, eax
0x1800c0ad8  js      loc_1800C0B99
0x1800c0ade  mov     this, [rbp+promotedBufferHandle]; string
0x1800c0ae2  mov     esi, [rdi+14h]
0x1800c0ae5  mov     qword ptr [rdi+8], 0
0x1800c0aed  call    cs:__imp_WindowsGetStringLen
0x1800c0af3  cmp     eax, esi
0x1800c0af5  jz      loc_1800C0BB1
0x1800c0afb  xor     eax, eax
0x1800c0afd  mov     [rbp+string], rax
0x1800c0b01  mov     [rbp+var_10], eax
0x1800c0b04  cmp     esi, 3FFFFFFFh
0x1800c0b0a  ja      loc_1800C0BA5
0x1800c0b10  mov     this, [rdi]; sourceString
0x1800c0b13  lea     r8, [rbp+string]; string
0x1800c0b17  mov     edx, esi; length
0x1800c0b19  call    cs:__imp_WindowsCreateString
0x1800c0b1f  mov     ebx, eax
0x1800c0b21  test    eax, eax
0x1800c0b23  js      short loc_1800C0B82
0x1800c0b25  mov     this, [r14]
0x1800c0b28  and     esi, 3FFFFFFFh
0x1800c0b2e  bts     esi, 1Fh
0x1800c0b32  mov     [rbp+var_10], esi
0x1800c0b35  mov     rsi, [rbp+string]
0x1800c0b39  or      rsi, 1
0x1800c0b3d  test    cl, 1
0x1800c0b40  jz      short loc_1800C0B4C
0x1800c0b42  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c0b46  call    cs:__imp_WindowsDeleteString
0x1800c0b4c  mov     [r14], rsi
0x1800c0b4f  mov     this, [rbp+promotedBufferHandle]; string
0x1800c0b53  call    cs:__imp_WindowsDeleteString
0x1800c0b59  test    ebx, ebx
0x1800c0b5b  jns     loc_1800C0A80
0x1800c0b61  mov     ecx, ebx; failedFrameHR
0x1800c0b63  call    OnFailure_2990_
0x1800c0b68  jmp     $Cleanup_373
0x1800c0b6d  mov     ecx, esi; failedFrameHR
0x1800c0b6f  call    OnFailure_2990_
0x1800c0b74  mov     ebx, esi
0x1800c0b76  mov     ecx, esi; failedFrameHR
0x1800c0b78  call    OnFailure_2990_
0x1800c0b7d  jmp     $Cleanup_373
0x1800c0b82  mov     ecx, eax; failedFrameHR
0x1800c0b84  call    OnFailure_2990_
0x1800c0b89  jmp     short loc_1800C0B4F
0x1800c0b8b  mov     ebx, 80004005h
0x1800c0b90  mov     esi, ebx
0x1800c0b92  call    OnNewFailure_1208_
0x1800c0b97  jmp     short loc_1800C0B76
0x1800c0b99  mov     ecx, eax; failedFrameHR
0x1800c0b9b  call    OnFailure_2990_
0x1800c0ba0  jmp     $Cleanup_373
0x1800c0ba5  mov     ebx, 80004005h
0x1800c0baa  call    OnNewFailure_1208_
0x1800c0baf  jmp     short loc_1800C0B4F
0x1800c0bb1  mov     this, [rbp+promotedBufferHandle]; handle
0x1800c0bb5  mov     pstrDetachedString, r14; pstrCloned
0x1800c0bb8  call    ?CloneRuntimeStringHandle@xstring_ptr@@SAJPEAUHSTRING__@@PEAV1@@Z; xstring_ptr::CloneRuntimeStringHandle(HSTRING__ *,xstring_ptr *)
0x1800c0bbd  mov     ebx, eax
0x1800c0bbf  jmp     short loc_1800C0B4F
```
