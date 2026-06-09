# CWinUriImpl::GetCanonical(xstring_ptr *)

- ea: `0x180093380`
- end: `0x18009376e`
- name: `?GetCanonical@CWinUriImpl@@UEBAJPEAVxstring_ptr@@@Z`
- size: `1006`
- prototype: `HRESULT __fastcall(CWinUriImpl *this, xstring_ptr *pstrCanonical)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004bc0`
- `0x180091d20`
- `0x180093380`
- `0x1800af8e0`
- `0x180363614`
- `0x18069f6ac`
- `0x1806b2e84`
- `0x18076e110`
- `0x18076f08c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009364b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009364b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18009360b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18009360b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180093466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180093466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18009359b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800935e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800936f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18009374b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18009359b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800935e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800936f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18009374b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180093625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180093625`
- `OLEAUT32!__imp_SysFreeString` at `0x180093414`
- `OLEAUT32!__imp_SysFreeString` at `0x1800934fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800936b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009371c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009372c`
- `OLEAUT32!__imp_SysFreeString` at `0x180093414`
- `OLEAUT32!__imp_SysFreeString` at `0x1800934fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800936b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009371c`
- `OLEAUT32!__imp_SysFreeString` at `0x18009372c`
- `OLEAUT32!__imp_SysStringLen` at `0x180093401`
- `OLEAUT32!__imp_SysStringLen` at `0x1800934c8`
- `OLEAUT32!__imp_SysStringLen` at `0x180093401`
- `OLEAUT32!__imp_SysStringLen` at `0x1800934c8`

## pseudocode

```c
__int64 __fastcall CWinUriImpl::GetCanonical(CWinUriImpl *this, xruntime_string_ptr *pstrCanonical)
{
  IUri *m_pUri; // rcx
  HRESULT v5; // eax
  HRESULT v6; // edi
  unsigned int v7; // r14d
  UINT v8; // eax
  HRESULT v9; // ecx
  UINT32 v10; // esi
  HRESULT v11; // ebx
  wchar_t *m_pBuffer; // r8
  unsigned int m_cBuffer; // eax
  int v14; // eax
  IUri *v15; // rcx
  wchar_t *v16; // r12
  HRESULT v17; // eax
  HRESULT v18; // ebx
  UINT v19; // eax
  wchar_t *v20; // rbx
  unsigned int v21; // edi
  UINT32 v22; // eax
  int String; // eax
  HRESULT v24; // esi
  unsigned __int64 v25; // rbx
  int v27; // eax
  UINT32 StringLen; // eax
  HRESULT v29; // eax
  BSTR pbstr; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-C8h]
  TStringBuilder<96> bufferBuilder; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)&bufferBuilder.m_cBuffer = 96;
  bufferBuilder.m_hPreallocatedBuffer = 0;
  m_pUri = this->m_pUri;
  bufferBuilder.m_pBuffer = bufferBuilder.m_inlineBuffer;
  pbstr = 0;
  v5 = m_pUri->GetPropertyBSTR(m_pUri, Uri_PROPERTY_ABSOLUTE_URI, &pbstr, 2u);
  v6 = v5;
  v7 = -2147024882;
  if ( v5 < 0 )
  {
    OnFailure_2990_(v5);
    v9 = (int)pbstr;
    if ( pbstr )
      SysFreeString(pbstr);
    v11 = 0;
    v10 = 0;
    if ( v6 != -2147024882 )
      v11 = v6;
    if ( v11 < 0 )
      goto LABEL_26;
  }
  else
  {
    v8 = SysStringLen(pbstr);
    v9 = (int)pbstr;
    v10 = v8 + 1;
    if ( pbstr )
      SysFreeString(pbstr);
  }
  if ( v10 >= 0x7FFFFF9F )
  {
    v11 = -2147418113;
    OnNewFailure_2955_(v9);
    goto LABEL_37;
  }
  m_pBuffer = bufferBuilder.m_pBuffer;
  if ( bufferBuilder.m_pBuffer == bufferBuilder.m_inlineBuffer )
  {
    m_cBuffer = bufferBuilder.m_cBuffer;
  }
  else
  {
    WindowsDeleteStringBuffer(bufferBuilder.m_hPreallocatedBuffer);
    m_pBuffer = bufferBuilder.m_inlineBuffer;
    bufferBuilder.m_hPreallocatedBuffer = 0;
    m_cBuffer = 96;
    bufferBuilder.m_pBuffer = bufferBuilder.m_inlineBuffer;
    bufferBuilder.m_cBuffer = 96;
  }
  if ( v10 + 1 > m_cBuffer )
  {
    v14 = WindowsPreallocateStringBuffer(v10, &bufferBuilder.m_pBuffer, &bufferBuilder.m_hPreallocatedBuffer);
    v11 = v14;
    if ( v14 >= 0 )
    {
      m_pBuffer = bufferBuilder.m_pBuffer;
      bufferBuilder.m_cBuffer = v10 + 1;
      goto LABEL_13;
    }
    OnFailure_2990_(v14);
LABEL_37:
    OnFailure_2990_(v11);
    OnFailure_2990_(v11);
    goto LABEL_27;
  }
LABEL_13:
  m_pBuffer[v10 - 1] = 0;
  v15 = this->m_pUri;
  v16 = bufferBuilder.m_pBuffer;
  bufferBuilder.m_cActual = v10 - 1;
  pbstr = 0;
  v17 = v15->GetPropertyBSTR(v15, Uri_PROPERTY_ABSOLUTE_URI, &pbstr, 2u);
  v18 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
    if ( pbstr )
      SysFreeString(pbstr);
    v7 = v18;
  }
  else
  {
    v19 = SysStringLen(pbstr);
    v20 = pbstr;
    v21 = v19;
    if ( !v16 )
      goto LABEL_17;
    v22 = v19 + 1;
    if ( v10 >= v22 )
    {
      memcpy_0(v16, pbstr, 2LL * v22);
LABEL_17:
      if ( v20 )
        SysFreeString(v20);
      bufferBuilder.m_cActual = v21;
      if ( v21 )
      {
        if ( bufferBuilder.m_pBuffer == bufferBuilder.m_inlineBuffer )
        {
          pbstr = 0;
          v31 = 0;
          if ( v21 > 0x3FFFFFFF )
          {
            v11 = -2147467259;
            v24 = -2147467259;
            OnNewFailure_1208_((HRESULT)bufferBuilder.m_pBuffer);
          }
          else
          {
            String = WindowsCreateString(bufferBuilder.m_pBuffer, v21, (HSTRING *)&pbstr);
            v24 = String;
            if ( String >= 0 )
            {
              v25 = (unsigned __int64)pbstr | 1;
              v31 = v21 & 0x3FFFFFFF | 0x80000000;
              xencoded_string_ptr::Reset(pstrCanonical);
              pstrCanonical->m_encodedStorage.RuntimeStringHandleMarker = v25;
              v11 = v24;
              goto LABEL_24;
            }
            OnFailure_2990_(String);
            v11 = v24;
          }
          OnFailure_2990_(v24);
LABEL_26:
          OnFailure_2990_(v11);
LABEL_27:
          if ( bufferBuilder.m_pBuffer != bufferBuilder.m_inlineBuffer )
            WindowsDeleteStringBuffer(bufferBuilder.m_hPreallocatedBuffer);
          return (unsigned int)v11;
        }
        pbstr = 0;
        v27 = WindowsPromoteStringBuffer(bufferBuilder.m_hPreallocatedBuffer, (HSTRING *)&pbstr);
        v11 = v27;
        if ( v27 < 0 )
        {
          OnFailure_2990_(v27);
          goto LABEL_26;
        }
        bufferBuilder.m_hPreallocatedBuffer = 0;
        StringLen = WindowsGetStringLen((HSTRING)pbstr);
        if ( StringLen == bufferBuilder.m_cActual )
          v29 = xstring_ptr::CloneRuntimeStringHandle((HSTRING__ *)pbstr, (xstring_ptr *)pstrCanonical);
        else
          v29 = xstring_ptr::CloneBuffer(bufferBuilder.m_pBuffer, bufferBuilder.m_cActual, (xstring_ptr *)pstrCanonical);
        v11 = v29;
        WindowsDeleteString((HSTRING)pbstr);
        if ( v11 < 0 )
        {
          OnFailure_2990_(v11);
          goto LABEL_26;
        }
      }
      else
      {
        v11 = 0;
        xencoded_string_ptr::Reset(pstrCanonical);
      }
LABEL_24:
      *(_QWORD *)&bufferBuilder.m_cBuffer = 96;
      bufferBuilder.m_pBuffer = bufferBuilder.m_inlineBuffer;
      if ( v11 >= 0 )
        return 0;
      goto LABEL_26;
    }
    if ( pbstr )
      SysFreeString(pbstr);
  }
  OnFailure_2990_(v7);
  if ( bufferBuilder.m_pBuffer != bufferBuilder.m_inlineBuffer )
    WindowsDeleteStringBuffer(bufferBuilder.m_hPreallocatedBuffer);
  return v7;
}

```

## disassembly

```asm
0x180093380  mov     [rsp-8+arg_10], rbx
0x180093385  push    rbp
0x180093386  push    rsi
0x180093387  push    rdi
0x180093388  push    r12
0x18009338a  push    r13
0x18009338c  push    r14
0x18009338e  push    r15
0x180093390  lea     rbp, [rsp-30h]
0x180093395  sub     rsp, 130h
0x18009339c  mov     rax, cs:__security_cookie
0x1800933a3  xor     rax, rsp
0x1800933a6  mov     [rbp+60h+var_40], rax
0x1800933aa  xor     r12d, r12d
0x1800933ad  mov     qword ptr [rsp+160h+bufferBuilder.m_cBuffer], 60h ; '`'
0x1800933b6  mov     r13, this
0x1800933b9  mov     [rsp+160h+bufferBuilder.m_hPreallocatedBuffer], r12
0x1800933be  mov     this, [this+18h]
0x1800933c2  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x1800933c7  mov     [rsp+160h+bufferBuilder.m_pBuffer], rax
0x1800933cc  lea     r8, [rsp+160h+pbstr]
0x1800933d1  mov     [rsp+160h+pbstr], r12
0x1800933d6  lea     r9d, [r12+2]
0x1800933db  mov     r15, pstrCanonical
0x1800933de  xor     edx, edx
0x1800933e0  mov     rax, [this]
0x1800933e3  mov     rax, [rax+18h]
0x1800933e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800933ec  mov     edi, eax
0x1800933ee  mov     r14d, 8007000Eh
0x1800933f4  test    eax, eax
0x1800933f6  js      loc_1800936A4
0x1800933fc  mov     this, [rsp+160h+pbstr]; pbstr
0x180093401  call    cs:__imp_SysStringLen
0x180093407  mov     this, [rsp+160h+pbstr]; bstrString
0x18009340c  lea     esi, [rax+1]
0x18009340f  test    this, this
0x180093412  jz      short loc_180093430
0x180093414  call    cs:__imp_SysFreeString
0x18009341a  jmp     short loc_180093430
0x18009341c  cmp     edi, r14d
0x18009341f  mov     ebx, r12d
0x180093422  mov     esi, r12d
0x180093425  cmovnz  ebx, edi
0x180093428  test    ebx, ebx
0x18009342a  js      loc_1800935CA
0x180093430  cmp     esi, 7FFFFF9Fh
0x180093436  jnb     loc_180093662
0x18009343c  mov     r8, [rsp+160h+bufferBuilder.m_pBuffer]
0x180093441  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x180093446  lea     edi, [rsi+1]
0x180093449  cmp     r8, rax
0x18009344c  jnz     loc_180093746
0x180093452  mov     eax, [rsp+160h+bufferBuilder.m_cBuffer]
0x180093456  cmp     edi, eax
0x180093458  jbe     short loc_18009347F
0x18009345a  lea     r8, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18009345f  mov     ecx, esi; length
0x180093461  lea     pstrCanonical, [rsp+160h+bufferBuilder]; charBuffer
0x180093466  call    cs:__imp_WindowsPreallocateStringBuffer
0x18009346c  mov     ebx, eax
0x18009346e  test    eax, eax
0x180093470  js      loc_18009369B
0x180093476  mov     r8, [rsp+160h+bufferBuilder.m_pBuffer]
0x18009347b  mov     [rsp+160h+bufferBuilder.m_cBuffer], edi
0x18009347f  lea     edx, [rsi-1]
0x180093482  mov     r9d, 2
0x180093488  mov     [r8+pstrCanonical*2], r12w
0x18009348d  lea     r8, [rsp+160h+pbstr]
0x180093492  mov     this, [r13+18h]
0x180093496  mov     r12, [rsp+160h+bufferBuilder.m_pBuffer]
0x18009349b  mov     [rsp+160h+bufferBuilder.m_cActual], edx
0x18009349f  xor     edx, edx
0x1800934a1  mov     [rsp+160h+pbstr], 0
0x1800934aa  mov     rax, [this]
0x1800934ad  mov     rax, [rax+18h]
0x1800934b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934b6  xor     r13d, r13d
0x1800934b9  mov     ebx, eax
0x1800934bb  test    eax, eax
0x1800934bd  js      loc_1800936C4
0x1800934c3  mov     this, [rsp+160h+pbstr]; pbstr
0x1800934c8  call    cs:__imp_SysStringLen
0x1800934ce  mov     rbx, [rsp+160h+pbstr]
0x1800934d3  mov     edi, eax
0x1800934d5  test    r12, r12
0x1800934d8  jz      short loc_1800934F5
0x1800934da  inc     eax
0x1800934dc  cmp     esi, eax
0x1800934de  jb      loc_180093724
0x1800934e4  mov     r8d, eax
0x1800934e7  mov     pstrCanonical, rbx; Src
0x1800934ea  add     r8, r8; Size
0x1800934ed  mov     this, r12; void *
0x1800934f0  call    memcpy_0
0x1800934f5  test    rbx, rbx
0x1800934f8  jz      short loc_180093503
0x1800934fa  mov     this, rbx; bstrString
0x1800934fd  call    cs:__imp_SysFreeString
0x180093503  mov     [rsp+160h+bufferBuilder.m_cActual], edi
0x180093507  test    edi, edi
0x180093509  jz      loc_1800935EC
0x18009350f  mov     this, [rsp+160h+bufferBuilder.m_pBuffer]; failedFrameHR
0x180093514  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x180093519  cmp     this, rax
0x18009351c  jnz     loc_1800935FC
0x180093522  xor     eax, eax
0x180093524  mov     ebx, 3FFFFFFFh
0x180093529  mov     [rsp+160h+pbstr], rax
0x18009352e  mov     [rsp+160h+var_128], eax
0x180093532  cmp     edi, ebx
0x180093534  ja      loc_1800936FF
0x18009353a  lea     r8, [rsp+160h+pbstr]; string
0x18009353f  mov     edx, edi; length
0x180093541  call    cs:__imp_WindowsCreateString
0x180093547  mov     esi, eax
0x180093549  test    eax, eax
0x18009354b  js      loc_18009367F
0x180093551  and     edi, ebx
0x180093553  mov     this, r15; this
0x180093556  mov     rbx, [rsp+160h+pbstr]
0x18009355b  bts     edi, 1Fh
0x18009355f  or      rbx, 1
0x180093563  mov     [rsp+160h+var_128], edi
0x180093567  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18009356c  mov     [r15], rbx
0x18009356f  mov     ebx, esi
0x180093571  lea     this, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x180093576  mov     qword ptr [rsp+160h+bufferBuilder.m_cBuffer], 60h ; '`'
0x18009357f  mov     [rsp+160h+bufferBuilder.m_pBuffer], this
0x180093584  test    ebx, ebx
0x180093586  js      loc_18009368F
0x18009358c  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x180093591  cmp     this, rax
0x180093594  jz      short loc_1800935A1
0x180093596  mov     this, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18009359b  call    cs:__imp_WindowsDeleteStringBuffer
0x1800935a1  xor     eax, eax
0x1800935a3  mov     this, [rbp+60h+var_40]
0x1800935a7  xor     this, rsp; StackCookie
0x1800935aa  call    __security_check_cookie
0x1800935af  mov     rbx, [rsp+160h+arg_10]
0x1800935b7  add     rsp, 130h
0x1800935be  pop     r15
0x1800935c0  pop     r14
0x1800935c2  pop     r13
0x1800935c4  pop     r12
0x1800935c6  pop     rdi
0x1800935c7  pop     rsi
0x1800935c8  pop     rbp
0x1800935c9  retn
0x1800935ca  mov     ecx, ebx; failedFrameHR
0x1800935cc  call    OnFailure_2990_
0x1800935d1  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x1800935d6  cmp     [rsp+160h+bufferBuilder.m_pBuffer], rax
0x1800935db  jz      short loc_1800935E8
0x1800935dd  mov     this, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800935e2  call    cs:__imp_WindowsDeleteStringBuffer
0x1800935e8  mov     eax, ebx
0x1800935ea  jmp     short loc_1800935A3
0x1800935ec  mov     this, r15; this
0x1800935ef  mov     ebx, r13d
0x1800935f2  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800935f7  jmp     loc_180093571
0x1800935fc  mov     this, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x180093601  lea     pstrCanonical, [rsp+160h+pbstr]; string
0x180093606  mov     [rsp+160h+pbstr], r13
0x18009360b  call    cs:__imp_WindowsPromoteStringBuffer
0x180093611  mov     ebx, eax
0x180093613  test    eax, eax
0x180093615  js      loc_180093710
0x18009361b  mov     this, [rsp+160h+pbstr]; string
0x180093620  mov     [rsp+160h+bufferBuilder.m_hPreallocatedBuffer], r13
0x180093625  call    cs:__imp_WindowsGetStringLen
0x18009362b  mov     edx, [rsp+160h+bufferBuilder.m_cActual]; count
0x18009362f  cmp     eax, edx
0x180093631  jz      loc_180093734
0x180093637  mov     this, [rsp+160h+bufferBuilder.m_pBuffer]; buffer
0x18009363c  mov     r8, r15; pstrCloned
0x18009363f  call    ?CloneBuffer@xstring_ptr@@SAJPEBGIPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,uint,xstring_ptr *)
0x180093644  mov     this, [rsp+160h+pbstr]; string
0x180093649  mov     ebx, eax
0x18009364b  call    cs:__imp_WindowsDeleteString
0x180093651  test    ebx, ebx
0x180093653  jns     loc_180093571
0x180093659  mov     ecx, ebx; failedFrameHR
0x18009365b  call    OnFailure_2990_
0x180093660  jmp     short loc_18009368F
0x180093662  mov     ebx, 8000FFFFh
0x180093667  call    OnNewFailure_2955_
0x18009366c  mov     ecx, ebx; failedFrameHR
0x18009366e  call    OnFailure_2990_
0x180093673  mov     ecx, ebx; failedFrameHR
0x180093675  call    OnFailure_2990_
0x18009367a  jmp     loc_1800935D1
0x18009367f  mov     ecx, esi; failedFrameHR
0x180093681  call    OnFailure_2990_
0x180093686  mov     ebx, esi
0x180093688  mov     ecx, esi; failedFrameHR
0x18009368a  call    OnFailure_2990_
0x18009368f  mov     ecx, ebx; failedFrameHR
0x180093691  call    OnFailure_2990_
0x180093696  jmp     loc_1800935D1
0x18009369b  mov     ecx, eax; failedFrameHR
0x18009369d  call    OnFailure_2990_
0x1800936a2  jmp     short loc_18009366C
0x1800936a4  mov     ecx, edi; failedFrameHR
0x1800936a6  call    OnFailure_2990_
0x1800936ab  mov     this, [rsp+160h+pbstr]; bstrString
0x1800936b0  test    this, this
0x1800936b3  jz      loc_18009341C
0x1800936b9  call    cs:__imp_SysFreeString
0x1800936bf  jmp     loc_18009341C
0x1800936c4  mov     ecx, ebx; failedFrameHR
0x1800936c6  call    OnFailure_2990_
0x1800936cb  mov     this, [rsp+160h+pbstr]; bstrString
0x1800936d0  test    this, this
0x1800936d3  jnz     short loc_18009371C
0x1800936d5  mov     r14d, ebx
0x1800936d8  mov     ecx, r14d; failedFrameHR
0x1800936db  call    OnFailure_2990_
0x1800936e0  lea     rax, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x1800936e5  cmp     [rsp+160h+bufferBuilder.m_pBuffer], rax
0x1800936ea  jz      short loc_1800936F7
0x1800936ec  mov     this, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800936f1  call    cs:__imp_WindowsDeleteStringBuffer
0x1800936f7  mov     eax, r14d
0x1800936fa  jmp     loc_1800935A3
0x1800936ff  mov     ebx, 80004005h
0x180093704  mov     esi, ebx
0x180093706  call    OnNewFailure_1208_
0x18009370b  jmp     loc_180093688
0x180093710  mov     ecx, eax; failedFrameHR
0x180093712  call    OnFailure_2990_
0x180093717  jmp     loc_18009368F
0x18009371c  call    cs:__imp_SysFreeString
0x180093722  jmp     short loc_1800936D5
0x180093724  test    rbx, rbx
0x180093727  jz      short loc_1800936D8
0x180093729  mov     this, rbx; bstrString
0x18009372c  call    cs:__imp_SysFreeString
0x180093732  jmp     short loc_1800936D8
0x180093734  mov     this, [rsp+160h+pbstr]; handle
0x180093739  mov     pstrCanonical, r15; pstrCloned
0x18009373c  call    ?CloneRuntimeStringHandle@xstring_ptr@@SAJPEAUHSTRING__@@PEAV1@@Z; xstring_ptr::CloneRuntimeStringHandle(HSTRING__ *,xstring_ptr *)
0x180093741  jmp     loc_180093644
0x180093746  mov     this, [rsp+160h+bufferBuilder.m_hPreallocatedBuffer]; bufferHandle
0x18009374b  call    cs:__imp_WindowsDeleteStringBuffer
0x180093751  lea     r8, [rsp+160h+bufferBuilder.m_inlineBuffer]
0x180093756  mov     [rsp+160h+bufferBuilder.m_hPreallocatedBuffer], r12
0x18009375b  mov     eax, 60h ; '`'
0x180093760  mov     [rsp+160h+bufferBuilder.m_pBuffer], r8
0x180093765  mov     [rsp+160h+bufferBuilder.m_cBuffer], eax
0x180093769  jmp     loc_180093456
```
