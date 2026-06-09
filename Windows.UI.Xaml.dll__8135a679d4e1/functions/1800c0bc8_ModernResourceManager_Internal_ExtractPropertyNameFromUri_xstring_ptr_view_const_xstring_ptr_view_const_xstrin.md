# ModernResourceManager_Internal::ExtractPropertyNameFromUri(xstring_ptr_view const &,xstring_ptr_view const &,xstring_ptr *)

- ea: `0x1800c0bc8`
- end: `0x1800c0f40`
- name: `?ExtractPropertyNameFromUri@ModernResourceManager_Internal@@YAJAEBVxstring_ptr_view@@0PEAVxstring_ptr@@@Z`
- size: `888`
- prototype: `HRESULT __fastcall(const xstring_ptr_view *strPropertyUri, const xstring_ptr_view *strPropertyBagPath, xstring_ptr *pstrPropertyName)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801e0a40`

## callees

- `0x180004bc0`
- `0x1800c09f8`
- `0x1800c0bc8`
- `0x1800c0f48`
- `0x1804e7328`
- `0x18069f6ac`
- `0x18076e110`
- `0x18076f08c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c0d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c0d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0eb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c0eb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0ed5`

## pseudocode

```c
__int64 __fastcall ModernResourceManager_Internal::ExtractPropertyNameFromUri(
        const xstring_ptr_view *strPropertyUri,
        const xstring_ptr_view *strPropertyBagPath,
        xstring_ptr *pstrPropertyName)
{
  unsigned __int64 RuntimeStringHandleMarker; // rax
  unsigned int m_cBuffer; // r13d
  int v7; // ecx
  const wchar_t *StringRawBuffer; // rsi
  unsigned __int64 v9; // rax
  int v10; // r8d
  wchar_t *v11; // rcx
  UINT32 v12; // r8d
  unsigned int v13; // ebx
  wchar_t *v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rdi
  int v17; // eax
  UINT32 StringLen; // eax
  __int64 v19; // rbx
  unsigned __int64 v20; // rax
  HSTRING v21; // rcx
  bool v22; // zf
  __int64 v23; // r15
  unsigned __int64 v24; // rcx
  int v25; // edi
  UINT32 v26; // edi
  unsigned __int64 v27; // rax
  __int64 v28; // rdi
  PCWSTR v29; // rsi
  wchar_t *m_pBuffer; // rcx
  int v31; // eax
  __int64 v32; // rax
  unsigned int i; // r9d
  HRESULT v34; // eax
  HSTRING v36; // rcx
  PCWSTR v37; // rax
  HSTRING v38; // rcx
  HSTRING v39; // rcx
  HSTRING v40; // rcx
  UINT32 length; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 v42; // [rsp+24h] [rbp-DCh] BYREF
  xstring_ptr *pstrDetachedString; // [rsp+28h] [rbp-D8h]
  TStringBuilder<96> propertyNameBuilder; // [rsp+30h] [rbp-D0h] BYREF

  pstrDetachedString = pstrPropertyName;
  propertyNameBuilder.m_hPreallocatedBuffer = 0;
  propertyNameBuilder.m_pBuffer = propertyNameBuilder.m_inlineBuffer;
  RuntimeStringHandleMarker = strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker;
  v42 = 0;
  m_cBuffer = 96;
  *(_QWORD *)&propertyNameBuilder.m_cBuffer = 96;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v38 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v7 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    StringRawBuffer = *(const wchar_t **)RuntimeStringHandleMarker;
    if ( v7 >= 0 )
    {
      v42 = v7 & 0x3FFFFFFF;
      goto LABEL_4;
    }
    v38 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v38, &v42);
LABEL_4:
  v9 = strPropertyBagPath->m_encodedStorage.RuntimeStringHandleMarker;
  length = 0;
  if ( (v9 & 1) != 0 )
  {
    v11 = (wchar_t *)(v9 & 0xFFFFFFFFFFFFFFFEuLL);
    goto LABEL_47;
  }
  v10 = *(_DWORD *)(v9 + 8);
  v11 = *(wchar_t **)v9;
  if ( v10 < 0 )
  {
LABEL_47:
    v37 = WindowsGetStringRawBuffer((HSTRING)v11, &length);
    v12 = length;
    v11 = (wchar_t *)v37;
    goto LABEL_7;
  }
  v12 = v10 & 0x3FFFFFFF;
  length = v12;
LABEL_7:
  v13 = -2147467259;
  if ( v12 == -1 || v12 > v42 || (v14 = xstrnistr(StringRawBuffer, v11, v12)) == 0 )
  {
    OnFailure_2990_(-2147467259);
    TStringBuilder<16>::~TStringBuilder<16>(&propertyNameBuilder);
    return v13;
  }
  v15 = strPropertyBagPath->m_encodedStorage.RuntimeStringHandleMarker;
  v16 = v14 - StringRawBuffer;
  if ( (strPropertyBagPath->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v39 = (HSTRING)(v15 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v17 = *(_DWORD *)(v15 + 8);
    if ( v17 >= 0 )
    {
      StringLen = v17 & 0x3FFFFFFF;
      goto LABEL_13;
    }
    v39 = *(HSTRING *)v15;
  }
  StringLen = WindowsGetStringLen(v39);
LABEL_13:
  v19 = (unsigned int)v16 + StringLen;
  v20 = strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v21 = (HSTRING)(v20 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v21 = *(HSTRING *)v20;
    if ( *(int *)(v20 + 8) >= 0 )
      goto LABEL_15;
  }
  v21 = (HSTRING)WindowsGetStringRawBuffer(v21, 0);
LABEL_15:
  v22 = *((_WORD *)v21 + v19) == 47;
  v23 = (unsigned int)(v19 + 1);
  v24 = strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker;
  if ( !v22 )
    v23 = (unsigned int)v19;
  if ( (v24 & 1) != 0 )
  {
    v40 = (HSTRING)(v24 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v25 = *(_DWORD *)(v24 + 8);
    if ( v25 >= 0 )
    {
      v26 = v25 & 0x3FFFFFFF;
      goto LABEL_20;
    }
    v40 = *(HSTRING *)v24;
  }
  v26 = WindowsGetStringLen(v40);
LABEL_20:
  v27 = strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker;
  v28 = v26 - (unsigned int)v23;
  if ( (strPropertyUri->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v36 = (HSTRING)(v27 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v29 = *(PCWSTR *)v27;
    if ( *(int *)(v27 + 8) >= 0 )
      goto LABEL_22;
    v36 = *(HSTRING *)v27;
  }
  v29 = WindowsGetStringRawBuffer(v36, 0);
LABEL_22:
  if ( (unsigned int)v28 >= 0x7FFFFF9F )
  {
    v13 = -2147418113;
    OnNewFailure_2955_(v24);
    goto LABEL_41;
  }
  m_pBuffer = propertyNameBuilder.m_pBuffer;
  if ( propertyNameBuilder.m_pBuffer == propertyNameBuilder.m_inlineBuffer )
  {
    m_cBuffer = propertyNameBuilder.m_cBuffer;
  }
  else
  {
    WindowsDeleteStringBuffer(propertyNameBuilder.m_hPreallocatedBuffer);
    m_pBuffer = propertyNameBuilder.m_inlineBuffer;
    propertyNameBuilder.m_hPreallocatedBuffer = 0;
    propertyNameBuilder.m_pBuffer = propertyNameBuilder.m_inlineBuffer;
    propertyNameBuilder.m_cBuffer = 96;
  }
  if ( (int)v28 + 1 > m_cBuffer )
  {
    v31 = WindowsPreallocateStringBuffer(
            v28,
            &propertyNameBuilder.m_pBuffer,
            &propertyNameBuilder.m_hPreallocatedBuffer);
    v13 = v31;
    if ( v31 >= 0 )
    {
      m_pBuffer = propertyNameBuilder.m_pBuffer;
      propertyNameBuilder.m_cBuffer = v28 + 1;
      goto LABEL_28;
    }
    OnFailure_2990_(v31);
LABEL_41:
    OnFailure_2990_(v13);
    OnFailure_2990_(v13);
LABEL_34:
    if ( propertyNameBuilder.m_pBuffer != propertyNameBuilder.m_inlineBuffer )
      WindowsDeleteStringBuffer(propertyNameBuilder.m_hPreallocatedBuffer);
    return v13;
  }
LABEL_28:
  propertyNameBuilder.m_cActual = 0;
  memcpy_0(m_pBuffer, &v29[v23], 2 * v28);
  propertyNameBuilder.m_cActual = v28;
  propertyNameBuilder.m_pBuffer[v28] = 0;
  v32 = 0;
  for ( i = propertyNameBuilder.m_cActual; (unsigned int)v32 < i; v32 = (unsigned int)(v32 + 1) )
  {
    if ( propertyNameBuilder.m_pBuffer[v32] == 47 )
    {
      propertyNameBuilder.m_pBuffer[v32] = 46;
      i = propertyNameBuilder.m_cActual;
    }
  }
  v34 = TStringBuilder<96>::DetachString(&propertyNameBuilder, pstrDetachedString);
  v13 = v34;
  if ( v34 < 0 )
  {
    OnFailure_2990_(v34);
    goto LABEL_34;
  }
  if ( propertyNameBuilder.m_pBuffer != propertyNameBuilder.m_inlineBuffer )
    WindowsDeleteStringBuffer(propertyNameBuilder.m_hPreallocatedBuffer);
  return 0;
}

```

## disassembly

```asm
0x1800c0bc8  mov     [rsp-8+arg_18], rbx
0x1800c0bcd  push    rbp
0x1800c0bce  push    rsi
0x1800c0bcf  push    rdi
0x1800c0bd0  push    r12
0x1800c0bd2  push    r13
0x1800c0bd4  push    r14
0x1800c0bd6  push    r15
0x1800c0bd8  lea     rbp, [rsp-20h]
0x1800c0bdd  sub     rsp, 120h
0x1800c0be4  mov     rax, cs:__security_cookie
0x1800c0beb  xor     rax, rsp
0x1800c0bee  mov     [rbp+50h+var_40], rax
0x1800c0bf2  xor     r15d, r15d
0x1800c0bf5  mov     [rsp+150h+pstrDetachedString], pstrPropertyName
0x1800c0bfa  lea     rax, [rsp+150h+propertyNameBuilder.m_inlineBuffer]
0x1800c0bff  mov     [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer], r15
0x1800c0c04  mov     [rsp+150h+propertyNameBuilder.m_pBuffer], rax
0x1800c0c09  mov     r14, strPropertyBagPath
0x1800c0c0c  mov     rax, [strPropertyUri]
0x1800c0c0f  mov     r12, strPropertyUri
0x1800c0c12  mov     [rsp+150h+var_12C], r15d
0x1800c0c17  lea     r13d, [r15+60h]
0x1800c0c1b  mov     qword ptr [rsp+150h+propertyNameBuilder.m_cBuffer], r13
0x1800c0c20  test    al, 1
0x1800c0c22  jnz     loc_1800C0EA8
0x1800c0c28  mov     ecx, [rax+8]
0x1800c0c2b  mov     rsi, [rax]
0x1800c0c2e  test    ecx, ecx
0x1800c0c30  js      loc_1800C0EF3
0x1800c0c36  and     ecx, 3FFFFFFFh
0x1800c0c3c  mov     [rsp+150h+var_12C], ecx
0x1800c0c40  mov     rax, [r14]
0x1800c0c43  mov     [rsp+150h+length], r15d
0x1800c0c48  test    al, 1
0x1800c0c4a  jnz     loc_1800C0E89
0x1800c0c50  mov     r8d, [rax+8]
0x1800c0c54  mov     strPropertyUri, [rax]
0x1800c0c57  test    r8d, r8d
0x1800c0c5a  js      loc_1800C0E90
0x1800c0c60  and     r8d, 3FFFFFFFh; cChar
0x1800c0c67  mov     [rsp+150h+length], r8d
0x1800c0c6c  or      eax, 0FFFFFFFFh
0x1800c0c6f  mov     ebx, 80004005h
0x1800c0c74  cmp     eax, r8d
0x1800c0c77  jz      loc_1800C0EF8
0x1800c0c7d  cmp     r8d, [rsp+150h+var_12C]
0x1800c0c82  ja      loc_1800C0EF8
0x1800c0c88  mov     strPropertyBagPath, strPropertyUri; pSub
0x1800c0c8b  mov     strPropertyUri, rsi; pSrc
0x1800c0c8e  call    ?xstrnistr@@YAPEAGPEBG0I@Z; xstrnistr(ushort const *,ushort const *,uint)
0x1800c0c93  mov     rdi, rax
0x1800c0c96  test    rax, rax
0x1800c0c99  jz      loc_1800C0EF8
0x1800c0c9f  mov     strPropertyUri, [r14]
0x1800c0ca2  sub     rdi, rsi
0x1800c0ca5  sar     rdi, 1
0x1800c0ca8  test    cl, 1
0x1800c0cab  jnz     loc_1800C0EC2
0x1800c0cb1  mov     eax, [strPropertyUri+8]
0x1800c0cb4  test    eax, eax
0x1800c0cb6  js      loc_1800C0F0E
0x1800c0cbc  and     eax, 3FFFFFFFh
0x1800c0cc1  lea     ebx, [rdi+rax]
0x1800c0cc4  mov     rax, [r12]
0x1800c0cc8  test    al, 1
0x1800c0cca  jnz     loc_1800C0E5B
0x1800c0cd0  mov     strPropertyUri, [rax]
0x1800c0cd3  cmp     [rax+8], r15d
0x1800c0cd7  jl      loc_1800C0E62
0x1800c0cdd  cmp     word ptr [strPropertyUri+rbx*2], 2Fh ; '/'
0x1800c0ce2  lea     r15d, [rbx+1]
0x1800c0ce6  mov     strPropertyUri, [r12]; failedFrameHR
0x1800c0cea  cmovnz  r15d, ebx
0x1800c0cee  test    cl, 1
0x1800c0cf1  jnz     loc_1800C0ED1
0x1800c0cf7  mov     edi, [strPropertyUri+8]
0x1800c0cfa  test    edi, edi
0x1800c0cfc  js      loc_1800C0F13
0x1800c0d02  and     edi, 3FFFFFFFh
0x1800c0d08  mov     rax, [r12]
0x1800c0d0c  sub     edi, r15d
0x1800c0d0f  test    al, 1
0x1800c0d11  jnz     loc_1800C0E72
0x1800c0d17  cmp     dword ptr [rax+8], 0
0x1800c0d1b  mov     rsi, [rax]
0x1800c0d1e  jl      loc_1800C0EEE
0x1800c0d24  cmp     edi, 7FFFFF9Fh
0x1800c0d2a  jnb     loc_1800C0E41
0x1800c0d30  mov     strPropertyUri, [rsp+150h+propertyNameBuilder.m_pBuffer]
0x1800c0d35  lea     rax, [rsp+150h+propertyNameBuilder.m_inlineBuffer]
0x1800c0d3a  lea     r14d, [rdi+1]
0x1800c0d3e  cmp     strPropertyUri, rax
0x1800c0d41  jnz     loc_1800C0F18
0x1800c0d47  mov     r13d, [rsp+150h+propertyNameBuilder.m_cBuffer]
0x1800c0d4c  cmp     r14d, r13d
0x1800c0d4f  jbe     short loc_1800C0D77
0x1800c0d51  lea     pstrPropertyName, [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0d56  mov     ecx, edi; length
0x1800c0d58  lea     strPropertyBagPath, [rsp+150h+propertyNameBuilder]; charBuffer
0x1800c0d5d  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800c0d63  mov     ebx, eax
0x1800c0d65  test    eax, eax
0x1800c0d67  js      loc_1800C0EE2
0x1800c0d6d  mov     strPropertyUri, [rsp+150h+propertyNameBuilder.m_pBuffer]; void *
0x1800c0d72  mov     [rsp+150h+propertyNameBuilder.m_cBuffer], r14d
0x1800c0d77  lea     rbx, [rdi+rdi]
0x1800c0d7b  mov     [rsp+150h+propertyNameBuilder.m_cActual], 0
0x1800c0d83  mov     pstrPropertyName, rbx; Size
0x1800c0d86  lea     strPropertyBagPath, [rsi+r15*2]; Src
0x1800c0d8a  call    memcpy_0
0x1800c0d8f  mov     rax, [rsp+150h+propertyNameBuilder.m_pBuffer]
0x1800c0d94  xor     ecx, ecx
0x1800c0d96  mov     [rsp+150h+propertyNameBuilder.m_cActual], edi
0x1800c0d9a  mov     [rbx+rax], cx
0x1800c0d9e  xor     eax, eax
0x1800c0da0  mov     r9d, [rsp+150h+propertyNameBuilder.m_cActual]
0x1800c0da5  test    r9d, r9d
0x1800c0da8  jz      short loc_1800C0DCA
0x1800c0daa  mov     pstrPropertyName, [rsp+150h+propertyNameBuilder.m_pBuffer]
0x1800c0daf  cmp     word ptr [pstrPropertyName+rax*2], 2Fh ; '/'
0x1800c0db5  jnz     short loc_1800C0DC3
0x1800c0db7  mov     word ptr [pstrPropertyName+rax*2], 2Eh ; '.'
0x1800c0dbe  mov     r9d, [rsp+150h+propertyNameBuilder.m_cActual]
0x1800c0dc3  inc     eax
0x1800c0dc5  cmp     eax, r9d
0x1800c0dc8  jb      short loc_1800C0DAA
0x1800c0dca  mov     strPropertyBagPath, [rsp+150h+pstrDetachedString]; pstrDetachedString
0x1800c0dcf  lea     strPropertyUri, [rsp+150h+propertyNameBuilder]; this
0x1800c0dd4  call    ?DetachString@?$TStringBuilder@$0GA@@@QEAAJPEAVxstring_ptr@@@Z; TStringBuilder<96>::DetachString(xstring_ptr *)
0x1800c0dd9  mov     ebx, eax
0x1800c0ddb  test    eax, eax
0x1800c0ddd  jns     short loc_1800C0E26
0x1800c0ddf  mov     ecx, eax; failedFrameHR
0x1800c0de1  call    OnFailure_2990_
0x1800c0de6  lea     rax, [rsp+150h+propertyNameBuilder.m_inlineBuffer]
0x1800c0deb  cmp     [rsp+150h+propertyNameBuilder.m_pBuffer], rax
0x1800c0df0  jz      short loc_1800C0DFD
0x1800c0df2  mov     strPropertyUri, [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0df7  call    cs:__imp_WindowsDeleteStringBuffer
0x1800c0dfd  mov     eax, ebx
0x1800c0dff  mov     strPropertyUri, [rbp+50h+var_40]
0x1800c0e03  xor     strPropertyUri, rsp; StackCookie
0x1800c0e06  call    __security_check_cookie
0x1800c0e0b  mov     rbx, [rsp+150h+arg_18]
0x1800c0e13  add     rsp, 120h
0x1800c0e1a  pop     r15
0x1800c0e1c  pop     r14
0x1800c0e1e  pop     r13
0x1800c0e20  pop     r12
0x1800c0e22  pop     rdi
0x1800c0e23  pop     rsi
0x1800c0e24  pop     rbp
0x1800c0e25  retn
0x1800c0e26  lea     rax, [rsp+150h+propertyNameBuilder.m_inlineBuffer]
0x1800c0e2b  cmp     [rsp+150h+propertyNameBuilder.m_pBuffer], rax
0x1800c0e30  jz      short loc_1800C0E3D
0x1800c0e32  mov     strPropertyUri, [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0e37  call    cs:__imp_WindowsDeleteStringBuffer
0x1800c0e3d  xor     eax, eax
0x1800c0e3f  jmp     short loc_1800C0DFF
0x1800c0e41  mov     ebx, 8000FFFFh
0x1800c0e46  call    OnNewFailure_2955_
0x1800c0e4b  mov     ecx, ebx; failedFrameHR
0x1800c0e4d  call    OnFailure_2990_
0x1800c0e52  mov     ecx, ebx; failedFrameHR
0x1800c0e54  call    OnFailure_2990_
0x1800c0e59  jmp     short loc_1800C0DE6
0x1800c0e5b  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c0e5f  mov     strPropertyUri, rax; string
0x1800c0e62  xor     edx, edx; length
0x1800c0e64  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0e6a  mov     strPropertyUri, rax
0x1800c0e6d  jmp     loc_1800C0CDD
0x1800c0e72  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c0e76  mov     strPropertyUri, rax; string
0x1800c0e79  xor     edx, edx; length
0x1800c0e7b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0e81  mov     rsi, rax
0x1800c0e84  jmp     loc_1800C0D24
0x1800c0e89  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c0e8d  mov     strPropertyUri, rax; string
0x1800c0e90  lea     strPropertyBagPath, [rsp+150h+length]; length
0x1800c0e95  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0e9b  mov     r8d, [rsp+150h+length]
0x1800c0ea0  mov     strPropertyUri, rax
0x1800c0ea3  jmp     loc_1800C0C6C
0x1800c0ea8  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c0eac  mov     strPropertyUri, rax; string
0x1800c0eaf  lea     strPropertyBagPath, [rsp+150h+var_12C]; length
0x1800c0eb4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0eba  mov     rsi, rax
0x1800c0ebd  jmp     loc_1800C0C40
0x1800c0ec2  and     strPropertyUri, 0FFFFFFFFFFFFFFFEh; string
0x1800c0ec6  call    cs:__imp_WindowsGetStringLen
0x1800c0ecc  jmp     loc_1800C0CC1
0x1800c0ed1  and     strPropertyUri, 0FFFFFFFFFFFFFFFEh; string
0x1800c0ed5  call    cs:__imp_WindowsGetStringLen
0x1800c0edb  mov     edi, eax
0x1800c0edd  jmp     loc_1800C0D08
0x1800c0ee2  mov     ecx, eax; failedFrameHR
0x1800c0ee4  call    OnFailure_2990_
0x1800c0ee9  jmp     loc_1800C0E4B
0x1800c0eee  mov     strPropertyUri, rsi
0x1800c0ef1  jmp     short loc_1800C0E79
0x1800c0ef3  mov     strPropertyUri, rsi
0x1800c0ef6  jmp     short loc_1800C0EAF
0x1800c0ef8  mov     ecx, ebx; failedFrameHR
0x1800c0efa  call    OnFailure_2990_
0x1800c0eff  lea     strPropertyUri, [rsp+150h+propertyNameBuilder]; this
0x1800c0f04  call    ??1?$TStringBuilder@$0BA@@@QEAA@XZ; TStringBuilder<16>::~TStringBuilder<16>(void)
0x1800c0f09  jmp     loc_1800C0DFD
0x1800c0f0e  mov     strPropertyUri, [strPropertyUri]
0x1800c0f11  jmp     short loc_1800C0EC6
0x1800c0f13  mov     strPropertyUri, [strPropertyUri]
0x1800c0f16  jmp     short loc_1800C0ED5
0x1800c0f18  mov     strPropertyUri, [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0f1d  call    cs:__imp_WindowsDeleteStringBuffer
0x1800c0f23  lea     strPropertyUri, [rsp+150h+propertyNameBuilder.m_inlineBuffer]
0x1800c0f28  mov     [rsp+150h+propertyNameBuilder.m_hPreallocatedBuffer], 0
0x1800c0f31  mov     [rsp+150h+propertyNameBuilder.m_pBuffer], strPropertyUri
0x1800c0f36  mov     [rsp+150h+propertyNameBuilder.m_cBuffer], r13d
0x1800c0f3b  jmp     loc_1800C0D4C
```
