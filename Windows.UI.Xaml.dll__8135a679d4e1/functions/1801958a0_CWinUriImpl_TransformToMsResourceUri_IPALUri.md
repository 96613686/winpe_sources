# CWinUriImpl::TransformToMsResourceUri(IPALUri * *)

- ea: `0x1801958a0`
- end: `0x180195d9d`
- name: `?TransformToMsResourceUri@CWinUriImpl@@UEBAJPEAPEAUIPALUri@@@Z`
- size: `1277`
- prototype: `HRESULT __fastcall(CWinUriImpl *this, IPALUri **ppUri)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800913b4`
- `0x1800fe130`
- `0x180194584`
- `0x1801958a0`
- `0x180196fcc`
- `0x1801eb6f4`
- `0x18020a400`
- `0x1804e7328`
- `0x18069f6ac`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1801959ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1801959ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195c6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195cbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195c6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195cbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180195d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180195c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180195c1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180195c0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180195c1f`
- `ext-ms-win-core-iuri-l1-1-0!CreateIUriBuilder` at `0x180195932`
- `ext-ms-win-core-iuri-l1-1-0!CreateIUriBuilder` at `0x180195932`

## pseudocode

```c
__int64 __fastcall CWinUriImpl::TransformToMsResourceUri(CWinUriImpl *this, CWinUriImpl **ppUri)
{
  unsigned int m_cBuffer; // edi
  int IUriBuilder; // eax
  unsigned int v6; // esi
  HRESULT v7; // eax
  HRESULT v8; // esi
  UINT32 StringLen; // ecx
  UINT32 v10; // ebx
  unsigned int v11; // esi
  int v12; // eax
  unsigned int v13; // ebx
  HRESULT v14; // eax
  unsigned int v15; // r8d
  const xstring_ptr_view *v16; // rax
  HRESULT appended; // eax
  CWinUriImpl *m_ptr; // rbx
  HRESULT v19; // eax
  HRESULT v20; // edi
  IUriBuilder *v21; // rcx
  IUriBuilder *ptr; // rcx
  IUriBuilder *v24; // rcx
  IUriBuilder *v25; // rcx
  IUriBuilder *v26; // rcx
  IUriBuilder *v27; // rcx
  Microsoft::WRL::ComPtr<IUriBuilder> spUriBuilder; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int dwPathLen; // [rsp+38h] [rbp-C8h] BYREF
  xref_ptr<CWinUriImpl> spUri; // [rsp+40h] [rbp-C0h] BYREF
  xstring_ptr c_strFilesPrefix; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *wszPath; // [rsp+50h] [rbp-B0h] BYREF
  xstring_ptr c_strScheme; // [rsp+58h] [rbp-A8h] BYREF
  xephemeral_string_ptr v34; // [rsp+60h] [rbp-A0h] BYREF
  TStringBuilder<96> adjustedPathBuilder; // [rsp+80h] [rbp-80h] BYREF

  c_strScheme.m_encodedStorage.Storage = &sc_strSchemeStorage;
  if ( ((unsigned __int8)&sc_strSchemeStorage & 1) != 0 )
    WindowsGetStringLen((HSTRING)((unsigned __int64)&sc_strSchemeStorage & 0xFFFFFFFFFFFFFFFEuLL));
  adjustedPathBuilder.m_pBuffer = adjustedPathBuilder.m_inlineBuffer;
  c_strFilesPrefix.m_encodedStorage.Storage = &sc_strFilesPrefixStorage;
  adjustedPathBuilder.m_hPreallocatedBuffer = 0;
  m_cBuffer = 96;
  spUriBuilder.ptr_ = 0;
  *(_QWORD *)&adjustedPathBuilder.m_cBuffer = 96;
  wszPath = 0;
  dwPathLen = 0;
  make_xref<CWinUriImpl,>(&spUri);
  IUriBuilder = CreateIUriBuilder(this->m_pUri, 0, 0, &spUriBuilder.ptr_);
  v6 = IUriBuilder;
  if ( IUriBuilder >= 0 )
  {
    v7 = spUriBuilder.ptr_->SetSchemeName(spUriBuilder.ptr_, L"ms-resource");
    v8 = v7;
    if ( v7 < 0 || (v7 = spUriBuilder.ptr_->GetPath(spUriBuilder.ptr_, &dwPathLen, &wszPath), v8 = v7, v7 < 0) )
    {
      OnFailure_2990_(v7);
      if ( spUri.m_ptr )
        CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&spUri.m_ptr->CInterlockedReferenceCount);
      ptr = spUriBuilder.ptr_;
      if ( spUriBuilder.ptr_ )
      {
        spUriBuilder.ptr_ = 0;
        ptr->Release(ptr);
      }
      if ( adjustedPathBuilder.m_pBuffer != adjustedPathBuilder.m_inlineBuffer )
      {
        WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
        adjustedPathBuilder.m_hPreallocatedBuffer = 0;
      }
      v13 = v8;
      goto LABEL_32;
    }
    if ( ((unsigned __int8)&sc_strFilesPrefixStorage & 1) != 0 )
      StringLen = WindowsGetStringLen((HSTRING)((unsigned __int64)&sc_strFilesPrefixStorage & 0xFFFFFFFFFFFFFFFEuLL));
    else
      StringLen = 6;
    v10 = StringLen + dwPathLen + 1;
    if ( v10 >= 0x7FFFFF9F )
    {
      v13 = -2147418113;
      OnNewFailure_2955_(StringLen);
    }
    else
    {
      v11 = v10 + 1;
      if ( adjustedPathBuilder.m_pBuffer == adjustedPathBuilder.m_inlineBuffer )
      {
        m_cBuffer = adjustedPathBuilder.m_cBuffer;
      }
      else
      {
        WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
        adjustedPathBuilder.m_hPreallocatedBuffer = 0;
        adjustedPathBuilder.m_pBuffer = adjustedPathBuilder.m_inlineBuffer;
        adjustedPathBuilder.m_cBuffer = 96;
      }
      if ( v11 <= m_cBuffer )
      {
LABEL_14:
        adjustedPathBuilder.m_cActual = 0;
        v14 = TStringBuilder<96>::Append(&adjustedPathBuilder, &c_strFilesPrefix);
        v13 = v14;
        if ( v14 < 0 )
        {
LABEL_68:
          OnFailure_2990_(v14);
          goto LABEL_43;
        }
        v15 = dwPathLen;
        if ( dwPathLen && *wszPath != 47 )
        {
          appended = TStringBuilder<96>::AppendChar(&adjustedPathBuilder, 0x2Fu);
          v13 = appended;
          if ( appended < 0 )
          {
LABEL_49:
            OnFailure_2990_(appended);
            if ( spUri.m_ptr )
              CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&spUri.m_ptr->CInterlockedReferenceCount);
            v26 = spUriBuilder.ptr_;
            if ( spUriBuilder.ptr_ )
            {
              spUriBuilder.ptr_ = 0;
              v26->Release(v26);
            }
            if ( adjustedPathBuilder.m_pBuffer != adjustedPathBuilder.m_inlineBuffer )
            {
              WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
              adjustedPathBuilder.m_hPreallocatedBuffer = 0;
            }
LABEL_32:
            adjustedPathBuilder.m_pBuffer = 0;
LABEL_33:
            xstring_ptr::~xstring_ptr(&c_strFilesPrefix);
            xstring_ptr::~xstring_ptr(&c_strScheme);
            return v13;
          }
          v15 = dwPathLen;
        }
        xephemeral_string_ptr::xephemeral_string_ptr(&v34, wszPath, v15);
        appended = TStringBuilder<96>::Append(&adjustedPathBuilder, v16);
        v13 = appended;
        if ( appended >= 0 )
        {
          v14 = spUriBuilder.ptr_->SetPath(spUriBuilder.ptr_, adjustedPathBuilder.m_pBuffer);
          v13 = v14;
          if ( v14 >= 0 )
          {
            m_ptr = spUri.m_ptr;
            v19 = spUriBuilder.ptr_->CreateUri(spUriBuilder.ptr_, 0, 0, 0, &spUri.m_ptr->m_pUri);
            v20 = v19;
            if ( v19 >= 0 )
            {
              *(_DWORD *)m_ptr->m_componentResourceLocation = *(_DWORD *)this->m_componentResourceLocation;
              v21 = spUriBuilder.ptr_;
              *ppUri = m_ptr;
              if ( v21 )
              {
                spUriBuilder.ptr_ = 0;
                v21->Release(v21);
              }
              if ( adjustedPathBuilder.m_pBuffer != adjustedPathBuilder.m_inlineBuffer )
              {
                WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
                adjustedPathBuilder.m_hPreallocatedBuffer = 0;
              }
              adjustedPathBuilder.m_pBuffer = 0;
              xstring_ptr::~xstring_ptr(&c_strFilesPrefix);
              xstring_ptr::~xstring_ptr(&c_strScheme);
              return 0;
            }
            OnFailure_2990_(v19);
            if ( m_ptr )
              CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&m_ptr->CInterlockedReferenceCount);
            v24 = spUriBuilder.ptr_;
            if ( spUriBuilder.ptr_ )
            {
              spUriBuilder.ptr_ = 0;
              v24->Release(v24);
            }
            if ( adjustedPathBuilder.m_pBuffer != adjustedPathBuilder.m_inlineBuffer )
            {
              WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
              adjustedPathBuilder.m_hPreallocatedBuffer = 0;
            }
            v13 = v20;
            goto LABEL_32;
          }
          goto LABEL_68;
        }
        goto LABEL_49;
      }
      v12 = WindowsPreallocateStringBuffer(
              v10,
              &adjustedPathBuilder.m_pBuffer,
              &adjustedPathBuilder.m_hPreallocatedBuffer);
      v13 = v12;
      if ( v12 >= 0 )
      {
        adjustedPathBuilder.m_cBuffer = v11;
        goto LABEL_14;
      }
      OnFailure_2990_(v12);
    }
    OnFailure_2990_(v13);
LABEL_43:
    if ( spUri.m_ptr )
      CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&spUri.m_ptr->CInterlockedReferenceCount);
    v25 = spUriBuilder.ptr_;
    if ( spUriBuilder.ptr_ )
    {
      spUriBuilder.ptr_ = 0;
      v25->Release(v25);
    }
    TStringBuilder<16>::~TStringBuilder<16>(&adjustedPathBuilder);
    goto LABEL_33;
  }
  OnFailure_2990_(IUriBuilder);
  if ( spUri.m_ptr )
    CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&spUri.m_ptr->CInterlockedReferenceCount);
  v27 = spUriBuilder.ptr_;
  if ( spUriBuilder.ptr_ )
  {
    spUriBuilder.ptr_ = 0;
    v27->Release(v27);
  }
  if ( adjustedPathBuilder.m_pBuffer != adjustedPathBuilder.m_inlineBuffer )
  {
    WindowsDeleteStringBuffer(adjustedPathBuilder.m_hPreallocatedBuffer);
    adjustedPathBuilder.m_hPreallocatedBuffer = 0;
  }
  adjustedPathBuilder.m_pBuffer = 0;
  xstring_ptr::~xstring_ptr(&c_strFilesPrefix);
  xstring_ptr::~xstring_ptr(&c_strScheme);
  return v6;
}

```

## disassembly

```asm
0x1801958a0  mov     [rsp-8+arg_10], rbx
0x1801958a5  mov     [rsp-8+arg_18], rsi
0x1801958aa  push    rbp
0x1801958ab  push    rdi
0x1801958ac  push    r12
0x1801958ae  push    r14
0x1801958b0  push    r15
0x1801958b2  lea     rbp, [rsp-70h]
0x1801958b7  sub     rsp, 170h
0x1801958be  mov     rax, cs:__security_cookie
0x1801958c5  xor     rax, rsp
0x1801958c8  mov     [rbp+90h+var_30], rax
0x1801958cc  mov     r14, this
0x1801958cf  mov     r15, ppUri
0x1801958d2  lea     this, sc_strSchemeStorage
0x1801958d9  mov     qword ptr [rsp+190h+c_strScheme.m_encodedStorage.___u0], this
0x1801958de  test    cl, 1
0x1801958e1  jnz     loc_180195C09
0x1801958e7  xor     r12d, r12d
0x1801958ea  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x1801958ee  lea     rbx, sc_strFilesPrefixStorage
0x1801958f5  mov     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x1801958f9  lea     this, [rsp+190h+spUri]; result
0x1801958fe  mov     qword ptr [rsp+190h+c_strFilesPrefix.m_encodedStorage.___u0], rbx
0x180195903  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195907  lea     edi, [r12+60h]
0x18019590c  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195911  mov     qword ptr [rbp+90h+adjustedPathBuilder.m_cBuffer], rdi
0x180195915  mov     [rsp+190h+wszPath], r12
0x18019591a  mov     [rsp+190h+dwPathLen], r12d
0x18019591f  call    ??$make_xref@VCWinUriImpl@@$$V@@YA?AV?$xref_ptr@VCWinUriImpl@@@@XZ; make_xref<CWinUriImpl,>(void)
0x180195924  mov     this, [r14+18h]; pIUri
0x180195928  lea     r9, [rsp+190h+spUriBuilder]; ppIUriBuilder
0x18019592d  xor     r8d, r8d; dwReserved
0x180195930  xor     edx, edx; dwFlags
0x180195932  call    cs:__imp_CreateIUriBuilder
0x180195938  mov     esi, eax
0x18019593a  test    eax, eax
0x18019593c  js      loc_180195C7D
0x180195942  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195947  lea     ppUri, aMsResource_0; "ms-resource"
0x18019594e  mov     rax, [this]
0x180195951  mov     rax, [rax+0B0h]
0x180195958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019595d  mov     esi, eax
0x18019595f  test    eax, eax
0x180195961  js      loc_180195CE4
0x180195967  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x18019596c  lea     r8, [rsp+190h+wszPath]
0x180195971  lea     ppUri, [rsp+190h+dwPathLen]
0x180195976  mov     rax, [this]
0x180195979  mov     rax, [rax+58h]
0x18019597d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195982  mov     esi, eax
0x180195984  test    eax, eax
0x180195986  js      loc_180195B11
0x18019598c  test    bl, 1
0x18019598f  jnz     loc_180195C18
0x180195995  lea     ecx, [rdi-5Ah]; failedFrameHR
0x180195998  mov     ebx, [rsp+190h+dwPathLen]
0x18019599c  inc     ebx
0x18019599e  add     ebx, ecx
0x1801959a0  cmp     ebx, 7FFFFF9Fh
0x1801959a6  jnb     loc_180195BC1
0x1801959ac  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x1801959b0  lea     esi, [rbx+1]
0x1801959b3  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x1801959b7  jnz     loc_180195D17
0x1801959bd  mov     edi, [rbp+90h+adjustedPathBuilder.m_cBuffer]
0x1801959c0  cmp     esi, edi
0x1801959c2  jbe     short loc_1801959E1
0x1801959c4  lea     r8, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1801959c8  mov     ecx, ebx; length
0x1801959ca  lea     ppUri, [rbp+90h+adjustedPathBuilder]; charBuffer
0x1801959ce  call    cs:__imp_WindowsPreallocateStringBuffer
0x1801959d4  mov     ebx, eax
0x1801959d6  test    eax, eax
0x1801959d8  js      loc_180195D0B
0x1801959de  mov     [rbp+90h+adjustedPathBuilder.m_cBuffer], esi
0x1801959e1  lea     ppUri, [rsp+190h+c_strFilesPrefix]; strToAppend
0x1801959e6  mov     [rbp+90h+adjustedPathBuilder.m_cActual], r12d
0x1801959ea  lea     this, [rbp+90h+adjustedPathBuilder]; this
0x1801959ee  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x1801959f3  mov     ebx, eax
0x1801959f5  test    eax, eax
0x1801959f7  js      loc_180195D67
0x1801959fd  mov     r8d, [rsp+190h+dwPathLen]; count
0x180195a02  test    r8d, r8d
0x180195a05  jz      short loc_180195A1A
0x180195a07  mov     rax, [rsp+190h+wszPath]
0x180195a0c  mov     edx, 2Fh ; '/'; ch
0x180195a11  cmp     [rax], dx
0x180195a14  jnz     loc_180195CF0
0x180195a1a  mov     ppUri, [rsp+190h+wszPath]; buffer
0x180195a1f  lea     this, [rsp+190h+var_130]; this
0x180195a24  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180195a29  mov     ppUri, rax; strToAppend
0x180195a2c  lea     this, [rbp+90h+adjustedPathBuilder]; this
0x180195a30  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180195a35  mov     ebx, eax
0x180195a37  test    eax, eax
0x180195a39  js      loc_180195C2C
0x180195a3f  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195a44  mov     ppUri, [rbp+90h+adjustedPathBuilder.m_pBuffer]
0x180195a48  mov     rax, [this]
0x180195a4b  mov     rax, [rax+98h]
0x180195a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195a57  mov     ebx, eax
0x180195a59  test    eax, eax
0x180195a5b  js      loc_180195D5B
0x180195a61  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195a66  xor     r9d, r9d
0x180195a69  mov     rbx, [rsp+190h+spUri.m_ptr]
0x180195a6e  xor     r8d, r8d
0x180195a71  mov     rax, [this]
0x180195a74  lea     ppUri, [rbx+18h]
0x180195a78  mov     [rsp+190h+var_170], ppUri
0x180195a7d  xor     edx, edx
0x180195a7f  mov     rax, [rax+20h]
0x180195a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195a88  mov     edi, eax
0x180195a8a  test    eax, eax
0x180195a8c  js      loc_180195B7A
0x180195a92  mov     eax, [r14+20h]
0x180195a96  mov     [rbx+20h], eax
0x180195a99  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195a9e  mov     [r15], rbx
0x180195aa1  test    this, this
0x180195aa4  jz      short loc_180195AB7
0x180195aa6  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195aab  mov     rax, [this]
0x180195aae  mov     rax, [rax+10h]
0x180195ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195ab7  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195abb  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195abf  jz      short loc_180195ACF
0x180195ac1  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195ac5  call    cs:__imp_WindowsDeleteStringBuffer
0x180195acb  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195acf  lea     this, [rsp+190h+c_strFilesPrefix]; this
0x180195ad4  mov     [rbp+90h+adjustedPathBuilder.m_pBuffer], r12
0x180195ad8  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195add  lea     this, [rsp+190h+c_strScheme]; this
0x180195ae2  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195ae7  xor     eax, eax
0x180195ae9  mov     this, [rbp+90h+var_30]
0x180195aed  xor     this, rsp; StackCookie
0x180195af0  call    __security_check_cookie
0x180195af5  lea     r11, [rsp+190h+var_20]
0x180195afd  mov     rbx, [r11+40h]
0x180195b01  mov     rsi, [r11+48h]
0x180195b05  mov     rsp, r11
0x180195b08  pop     r15
0x180195b0a  pop     r14
0x180195b0c  pop     r12
0x180195b0e  pop     rdi
0x180195b0f  pop     rbp
0x180195b10  retn
0x180195b11  mov     ecx, esi; failedFrameHR
0x180195b13  call    OnFailure_2990_
0x180195b18  mov     this, [rsp+190h+spUri.m_ptr]
0x180195b1d  test    this, this
0x180195b20  jnz     loc_180195D81
0x180195b26  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195b2b  test    this, this
0x180195b2e  jz      short loc_180195B41
0x180195b30  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195b35  mov     rax, [this]
0x180195b38  mov     rax, [rax+10h]
0x180195b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195b41  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195b45  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195b49  jz      short loc_180195B59
0x180195b4b  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195b4f  call    cs:__imp_WindowsDeleteStringBuffer
0x180195b55  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195b59  mov     ebx, esi
0x180195b5b  mov     [rbp+90h+adjustedPathBuilder.m_pBuffer], r12
0x180195b5f  lea     this, [rsp+190h+c_strFilesPrefix]; this
0x180195b64  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195b69  lea     this, [rsp+190h+c_strScheme]; this
0x180195b6e  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195b73  mov     eax, ebx
0x180195b75  jmp     loc_180195AE9
0x180195b7a  mov     ecx, edi; failedFrameHR
0x180195b7c  call    OnFailure_2990_
0x180195b81  test    rbx, rbx
0x180195b84  jnz     loc_180195D4D
0x180195b8a  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195b8f  test    this, this
0x180195b92  jz      short loc_180195BA5
0x180195b94  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195b99  mov     rax, [this]
0x180195b9c  mov     rax, [rax+10h]
0x180195ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195ba5  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195ba9  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195bad  jz      short loc_180195BBD
0x180195baf  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195bb3  call    cs:__imp_WindowsDeleteStringBuffer
0x180195bb9  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195bbd  mov     ebx, edi
0x180195bbf  jmp     short loc_180195B5B
0x180195bc1  mov     ebx, 8000FFFFh
0x180195bc6  call    OnNewFailure_2955_
0x180195bcb  mov     ecx, ebx; failedFrameHR
0x180195bcd  call    OnFailure_2990_
0x180195bd2  mov     this, [rsp+190h+spUri.m_ptr]
0x180195bd7  test    this, this
0x180195bda  jnz     loc_180195D73
0x180195be0  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195be5  test    this, this
0x180195be8  jz      short loc_180195BFB
0x180195bea  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195bef  mov     rax, [this]
0x180195bf2  mov     rax, [rax+10h]
0x180195bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195bfb  lea     this, [rbp+90h+adjustedPathBuilder]; this
0x180195bff  call    ??1?$TStringBuilder@$0BA@@@QEAA@XZ; TStringBuilder<16>::~TStringBuilder<16>(void)
0x180195c04  jmp     loc_180195B5F
0x180195c09  and     this, 0FFFFFFFFFFFFFFFEh; string
0x180195c0d  call    cs:__imp_WindowsGetStringLen
0x180195c13  jmp     loc_1801958E7
0x180195c18  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180195c1c  mov     this, rbx; string
0x180195c1f  call    cs:__imp_WindowsGetStringLen
0x180195c25  mov     ecx, eax
0x180195c27  jmp     loc_180195998
0x180195c2c  mov     ecx, eax; failedFrameHR
0x180195c2e  call    OnFailure_2990_
0x180195c33  mov     this, [rsp+190h+spUri.m_ptr]
0x180195c38  test    this, this
0x180195c3b  jnz     loc_180195D35
0x180195c41  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195c46  test    this, this
0x180195c49  jz      short loc_180195C5C
0x180195c4b  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195c50  mov     rax, [this]
0x180195c53  mov     rax, [rax+10h]
0x180195c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195c5c  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195c60  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195c64  jz      loc_180195B5B
0x180195c6a  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195c6e  call    cs:__imp_WindowsDeleteStringBuffer
0x180195c74  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195c78  jmp     loc_180195B5B
0x180195c7d  mov     ecx, esi; failedFrameHR
0x180195c7f  call    OnFailure_2990_
0x180195c84  mov     this, [rsp+190h+spUri.m_ptr]
0x180195c89  test    this, this
0x180195c8c  jnz     loc_180195D8F
0x180195c92  mov     this, [rsp+190h+spUriBuilder.ptr_]
0x180195c97  test    this, this
0x180195c9a  jz      short loc_180195CAD
0x180195c9c  mov     [rsp+190h+spUriBuilder.ptr_], r12
0x180195ca1  mov     rax, [this]
0x180195ca4  mov     rax, [rax+10h]
0x180195ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195cad  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195cb1  cmp     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195cb5  jz      short loc_180195CC5
0x180195cb7  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195cbb  call    cs:__imp_WindowsDeleteStringBuffer
0x180195cc1  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195cc5  lea     this, [rsp+190h+c_strFilesPrefix]; this
0x180195cca  mov     [rbp+90h+adjustedPathBuilder.m_pBuffer], r12
0x180195cce  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195cd3  lea     this, [rsp+190h+c_strScheme]; this
0x180195cd8  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180195cdd  mov     eax, esi
0x180195cdf  jmp     loc_180195AE9
0x180195ce4  mov     ecx, esi; failedFrameHR
0x180195ce6  call    OnFailure_2990_
0x180195ceb  jmp     loc_180195B18
0x180195cf0  lea     this, [rbp+90h+adjustedPathBuilder]; this
0x180195cf4  call    ?AppendChar@?$TStringBuilder@$0GA@@@QEAAJG@Z; TStringBuilder<96>::AppendChar(ushort)
0x180195cf9  mov     ebx, eax
0x180195cfb  test    eax, eax
0x180195cfd  jns     short loc_180195D43
0x180195cff  mov     ecx, eax; failedFrameHR
0x180195d01  call    OnFailure_2990_
0x180195d06  jmp     loc_180195C33
0x180195d0b  mov     ecx, eax; failedFrameHR
0x180195d0d  call    OnFailure_2990_
0x180195d12  jmp     loc_180195BCB
0x180195d17  mov     this, [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180195d1b  call    cs:__imp_WindowsDeleteStringBuffer
0x180195d21  lea     rax, [rbp+90h+adjustedPathBuilder.m_inlineBuffer]
0x180195d25  mov     [rbp+90h+adjustedPathBuilder.m_hPreallocatedBuffer], r12
0x180195d29  mov     [rbp+90h+adjustedPathBuilder.m_pBuffer], rax
0x180195d2d  mov     [rbp+90h+adjustedPathBuilder.m_cBuffer], edi
0x180195d30  jmp     loc_1801959C0
0x180195d35  add     this, 8; this
0x180195d39  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x180195d3e  jmp     loc_180195C41
0x180195d43  mov     r8d, [rsp+190h+dwPathLen]
0x180195d48  jmp     loc_180195A1A
0x180195d4d  lea     this, [rbx+8]; this
0x180195d51  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
  ... truncated ...
```
