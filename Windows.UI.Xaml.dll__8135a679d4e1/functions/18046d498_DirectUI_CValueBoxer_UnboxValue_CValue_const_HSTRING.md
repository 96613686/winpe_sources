# DirectUI::CValueBoxer::UnboxValue(CValue const *,HSTRING__ * *)

- ea: `0x18046d498`
- end: `0x18046d744`
- name: `?UnboxValue@CValueBoxer@DirectUI@@SAJPEBVCValue@@PEAPEAUHSTRING__@@@Z`
- size: `684`
- prototype: `HRESULT __fastcall(const CValue *box, HSTRING__ **value)`
- caller_count: `6`
- callee_count: `13`
- tags: ``

## callers

- `0x180167160`
- `0x18038f2f8`
- `0x18092a0b0`
- `0x1809a5080`
- `0x1809fadc8`
- `0x180bb20d4`

## callees

- `0x180004bc0`
- `0x180065258`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800fe130`
- `0x1801e9130`
- `0x180254ef4`
- `0x18046d498`
- `0x18046d9c4`
- `0x1806877a8`
- `0x180687890`
- `0x180688828`
- `0x18069f6ac`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18046d6ea`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18046d6ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d56c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d6a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d56c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d57d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18046d6a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18046d51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18046d51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18046d64e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18046d70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18046d64e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18046d70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18046d59e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18046d59e`

## pseudocode

```c
__int64 __fastcall DirectUI::CValueBoxer::UnboxValue(CValue *box, HSTRING__ **value)
{
  HSTRING__ *Handle; // rbx
  unsigned int v5; // ecx
  wchar_t **v6; // rax
  int v7; // edx
  wchar_t *v8; // rax
  UINT32 v9; // edx
  int v10; // eax
  HRESULT v11; // edi
  HRESULT v12; // ecx
  HSTRING v14; // rax
  int v15; // eax
  HSTRING StringRawBuffer; // rcx
  const xstring_ptr_storage *Storage; // rcx
  char v18; // dl
  HSTRING__ *v19; // rbx
  CDependencyObject *v20; // rax
  CString *v21; // rax
  HRESULT v22; // eax
  unsigned int v23; // ebx
  xstring_ptr v24; // [rsp+20h] [rbp-10h] BYREF
  CValueDetails::Value length; // [rsp+50h] [rbp+20h] BYREF
  xruntime_string_ptr strRuntimeValue; // [rsp+60h] [rbp+30h] BYREF
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  if ( !box )
  {
    OnNewFailure_1172_(0);
    return 2147500035LL;
  }
  if ( !value )
  {
    OnNewFailure_1172_((HRESULT)box);
    return 2147500035LL;
  }
  Handle = xstring_ptr_constants::c_xencoded_string_ptr_null.Handle;
  v5 = box->m_flags.m_state.m_asOne & 0x3F;
  strRuntimeValue.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
  if ( v5 != 14 )
  {
    if ( v5 != 24 )
    {
      if ( CValue::IsNull(box) )
        goto LABEL_22;
      OnNewFailure_2955_(v12);
      if ( ((__int64)xstring_ptr_constants::c_xencoded_string_ptr_null.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(xstring_ptr_constants::c_xencoded_string_ptr_null.RuntimeStringHandleMarker
                                    & 0xFFFFFFFFFFFFFFFEuLL));
      return 2147549183LL;
    }
    v20 = CValue::As<24>(box);
    v21 = do_pointer_cast<CString>(v20);
    v22 = xstring_ptr_view::Promote(&v21->m_strString, &strRuntimeValue);
    v23 = v22;
    if ( v22 < 0 )
    {
      OnFailure_2990_(v22);
      xencoded_string_ptr::Reset(&strRuntimeValue);
      return v23;
    }
    Handle = strRuntimeValue.m_encodedStorage.Handle;
LABEL_22:
    length.m_any[0] = 0;
    if ( ((unsigned __int8)Handle & 1) != 0 )
    {
      StringRawBuffer = (HSTRING)((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      v15 = *((_DWORD *)Handle + 2);
      StringRawBuffer = *(HSTRING *)Handle;
      if ( v15 >= 0 )
      {
        length.m_any[0] = v15 & 0x3FFFFFFF;
        goto LABEL_25;
      }
    }
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, (UINT32 *)&length);
LABEL_25:
    if ( StringRawBuffer && length.m_any[0] && *(_WORD *)StringRawBuffer )
    {
      Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
      v18 = 0;
    }
    else
    {
      v18 = 1;
      Storage = (const xstring_ptr_storage *)Handle;
    }
    v19 = (HSTRING__ *)((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL);
    if ( v18 )
      v19 = 0;
    *value = v19;
    if ( ((unsigned __int8)Storage & 1) != 0 )
      WindowsDeleteString((HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL));
    return 0;
  }
  length = box->m_value;
  if ( length.m_bool )
  {
    if ( WindowsDuplicateString((HSTRING)(*(_QWORD *)&length & 0xFFFFFFFFFFFFFFFEuLL), &string) < 0 )
    {
      v24.m_encodedStorage.Storage = 0;
      length.m_any[0] = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast((_STOWED_EXCEPTION_INFORMATION_V2 ***)&v24, (unsigned int *)&length);
      RoFailFastWithErrorContextInternal2(
        -2147418113,
        length.m_any[0],
        (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)v24.m_encodedStorage.Storage);
    }
    string = (HSTRING)((unsigned __int64)string | 1);
    xencoded_string_ptr::Reset(&strRuntimeValue);
    Handle = string;
    goto LABEL_22;
  }
  v6 = (wchar_t **)length;
  v24.m_encodedStorage.Storage = (const xstring_ptr_storage *)length;
  if ( !*(_QWORD *)&length )
  {
    v11 = 0;
    v14 = 0;
LABEL_20:
    string = v14;
    xencoded_string_ptr::Reset(&strRuntimeValue);
    Handle = string;
    goto LABEL_21;
  }
  v7 = *(_DWORD *)(*(_QWORD *)&length + 8LL);
  length.m_any[0] = 0;
  v8 = *v6;
  if ( v7 < 0 )
  {
    v8 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v8, (UINT32 *)&length);
    v9 = length.m_any[0];
  }
  else
  {
    v9 = v7 & 0x3FFFFFFF;
    length.m_any[0] = v9;
  }
  v10 = WindowsCreateString(v8, v9, &string);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v14 = (HSTRING)((unsigned __int64)string | 1);
    goto LABEL_20;
  }
  OnFailure_2990_(v10);
  OnFailure_2990_(v11);
LABEL_21:
  xstring_ptr::~xstring_ptr(&v24);
  if ( v11 >= 0 )
    goto LABEL_22;
  OnFailure_2990_(v11);
  OnFailure_2990_(v11);
  if ( ((unsigned __int8)Handle & 1) != 0 )
    WindowsDeleteString((HSTRING)((unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18046d498  mov     [rsp-18h+arg_8], rbx
0x18046d49d  push    rbp
0x18046d49e  push    rsi
0x18046d49f  push    rdi
0x18046d4a0  mov     rbp, rsp
0x18046d4a3  sub     rsp, 30h
0x18046d4a7  mov     rsi, value
0x18046d4aa  mov     rax, box
0x18046d4ad  test    box, box
0x18046d4b0  jz      loc_18046D6F5
0x18046d4b6  test    value, value
0x18046d4b9  jz      loc_18046D73D
0x18046d4bf  mov     ecx, [box+8]
0x18046d4c2  mov     rbx, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18046d4c9  and     ecx, 3Fh
0x18046d4cc  mov     qword ptr [rbp+strRuntimeValue.m_encodedStorage.___u0], rbx
0x18046d4d0  cmp     ecx, 0Eh
0x18046d4d3  jnz     short loc_18046D542
0x18046d4d5  mov     ecx, [rax]
0x18046d4d7  mov     eax, [rax+4]
0x18046d4da  mov     dword ptr [rbp+length+4], eax
0x18046d4dd  mov     dword ptr [rbp+length], ecx
0x18046d4e0  test    cl, 1
0x18046d4e3  jnz     loc_18046D592
0x18046d4e9  mov     rax, [rbp+length]
0x18046d4ed  mov     qword ptr [rbp+var_10.m_encodedStorage.___u0], rax
0x18046d4f1  test    rax, rax
0x18046d4f4  jz      loc_18046D5C0
0x18046d4fa  mov     edx, [rax+8]
0x18046d4fd  mov     dword ptr [rbp+length], 0
0x18046d504  mov     rax, [rax]
0x18046d507  test    edx, edx
0x18046d509  js      loc_18046D704
0x18046d50f  and     edx, 3FFFFFFFh; length
0x18046d515  mov     dword ptr [rbp+length], edx
0x18046d518  lea     r8, [rbp+string]; string
0x18046d51c  mov     box, rax; sourceString
0x18046d51f  call    cs:__imp_WindowsCreateString
0x18046d525  mov     edi, eax
0x18046d527  test    eax, eax
0x18046d529  jns     loc_18046D719
0x18046d52f  mov     ecx, eax; failedFrameHR
0x18046d531  call    OnFailure_2990_
0x18046d536  mov     ecx, edi; failedFrameHR
0x18046d538  call    OnFailure_2990_
0x18046d53d  jmp     loc_18046D5D5
0x18046d542  cmp     ecx, 18h
0x18046d545  mov     box, rax; this
0x18046d548  jz      loc_18046D659
0x18046d54e  call    ?IsNull@CValue@@QEBA_NXZ; CValue::IsNull(void)
0x18046d553  test    al, al
0x18046d555  jnz     loc_18046D5E6
0x18046d55b  call    OnNewFailure_2955_
0x18046d560  test    bl, 1
0x18046d563  jz      short loc_18046D572
0x18046d565  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18046d569  mov     box, rbx; string
0x18046d56c  call    cs:__imp_WindowsDeleteString
0x18046d572  mov     eax, 8000FFFFh
0x18046d577  jmp     short loc_18046D585
0x18046d579  and     box, 0FFFFFFFFFFFFFFFEh; string
0x18046d57d  call    cs:__imp_WindowsDeleteString
0x18046d583  xor     eax, eax
0x18046d585  mov     rbx, [rsp+30h+arg_8]
0x18046d58a  add     rsp, 30h
0x18046d58e  pop     rdi
0x18046d58f  pop     rsi
0x18046d590  pop     rbp
0x18046d591  retn
0x18046d592  mov     box, [rbp+length]
0x18046d596  lea     value, [rbp+string]; newString
0x18046d59a  and     box, 0FFFFFFFFFFFFFFFEh; string
0x18046d59e  call    cs:__imp_WindowsDuplicateString
0x18046d5a4  test    eax, eax
0x18046d5a6  js      loc_18046D6AD
0x18046d5ac  or      [rbp+string], 1
0x18046d5b1  lea     box, [rbp+strRuntimeValue]; this
0x18046d5b5  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18046d5ba  mov     rbx, [rbp+string]
0x18046d5be  jmp     short loc_18046D5E6
0x18046d5c0  xor     edi, edi
0x18046d5c2  xor     eax, eax
0x18046d5c4  lea     box, [rbp+strRuntimeValue]; this
0x18046d5c8  mov     [rbp+string], rax
0x18046d5cc  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18046d5d1  mov     rbx, [rbp+string]
0x18046d5d5  lea     box, [rbp+var_10]; this
0x18046d5d9  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18046d5de  test    edi, edi
0x18046d5e0  js      loc_18046D686
0x18046d5e6  mov     dword ptr [rbp+length], 0
0x18046d5ed  test    bl, 1
0x18046d5f0  jnz     short loc_18046D643
0x18046d5f2  mov     eax, [rbx+8]
0x18046d5f5  mov     box, [rbx]
0x18046d5f8  test    eax, eax
0x18046d5fa  js      short loc_18046D64A
0x18046d5fc  and     eax, 3FFFFFFFh
0x18046d601  mov     dword ptr [rbp+length], eax
0x18046d604  test    box, box
0x18046d607  jz      short loc_18046D63C
0x18046d609  cmp     dword ptr [rbp+length], 0
0x18046d60d  jz      short loc_18046D63C
0x18046d60f  xor     eax, eax
0x18046d611  cmp     ax, [box]
0x18046d614  jz      short loc_18046D63C
0x18046d616  mov     box, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18046d61d  xor     dl, dl
0x18046d61f  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18046d623  xor     eax, eax
0x18046d625  test    dl, dl
0x18046d627  cmovnz  rbx, rax
0x18046d62b  mov     [rsi], rbx
0x18046d62e  test    cl, 1
0x18046d631  jz      loc_18046D583
0x18046d637  jmp     loc_18046D579
0x18046d63c  mov     dl, 1
0x18046d63e  mov     box, rbx
0x18046d641  jmp     short loc_18046D61F
0x18046d643  mov     box, rbx
0x18046d646  and     box, 0FFFFFFFFFFFFFFFEh; string
0x18046d64a  lea     value, [rbp+length]; length
0x18046d64e  call    cs:__imp_WindowsGetStringRawBuffer
0x18046d654  mov     box, rax
0x18046d657  jmp     short loc_18046D604
0x18046d659  call    ??$As@$0BI@@CValue@@QEAAPEAVCDependencyObject@@XZ; CValue::As<24>(void)
0x18046d65e  mov     box, rax; pDO
0x18046d661  call    ??$do_pointer_cast@VCString@@@@YAPEAVCString@@PEAVCDependencyObject@@@Z; do_pointer_cast<CString>(CDependencyObject *)
0x18046d666  lea     value, [rbp+strRuntimeValue]; pstrPromoted
0x18046d66a  lea     box, [rax+60h]; this
0x18046d66e  call    ?Promote@xstring_ptr_view@@QEBAJPEAVxruntime_string_ptr@@@Z; xstring_ptr_view::Promote(xruntime_string_ptr *)
0x18046d673  mov     ebx, eax
0x18046d675  test    eax, eax
0x18046d677  js      loc_18046D726
0x18046d67d  mov     rbx, qword ptr [rbp+strRuntimeValue.m_encodedStorage.___u0]
0x18046d681  jmp     loc_18046D5E6
0x18046d686  mov     ecx, edi; failedFrameHR
0x18046d688  call    OnFailure_2990_
0x18046d68d  mov     ecx, edi; failedFrameHR
0x18046d68f  call    OnFailure_2990_
0x18046d694  test    bl, 1
0x18046d697  jz      short loc_18046D6A6
0x18046d699  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18046d69d  mov     box, rbx; string
0x18046d6a0  call    cs:__imp_WindowsDeleteString
0x18046d6a6  mov     eax, edi
0x18046d6a8  jmp     loc_18046D585
0x18046d6ad  mov     ebx, 8000FFFFh
0x18046d6b2  mov     qword ptr [rbp+var_10.m_encodedStorage.___u0], 0
0x18046d6ba  mov     ecx, ebx; errorCode
0x18046d6bc  mov     dword ptr [rbp+length], 0
0x18046d6c3  call    TraceForFailFast
0x18046d6c8  xor     r8d, r8d; contextRecord
0x18046d6cb  xor     edx, edx; directCallerReturnAddress
0x18046d6cd  mov     ecx, ebx; failedFrameHR
0x18046d6cf  call    OnNewFailureEncountered
0x18046d6d4  lea     value, [rbp+length]; pcStowedExceptions
0x18046d6d8  lea     box, [rbp+var_10]; pppStowedExceptions
0x18046d6dc  call    GetStowedExceptionsForFailFast
0x18046d6e1  mov     r8, qword ptr [rbp+var_10.m_encodedStorage.___u0]
0x18046d6e5  mov     ecx, ebx
0x18046d6e7  mov     edx, dword ptr [rbp+length]
0x18046d6ea  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18046d6f0  jmp     loc_18046D5AC
0x18046d6f5  call    OnNewFailure_1172_
0x18046d6fa  mov     eax, 80004003h
0x18046d6ff  jmp     loc_18046D585
0x18046d704  lea     value, [rbp+length]; length
0x18046d708  mov     box, rax; string
0x18046d70b  call    cs:__imp_WindowsGetStringRawBuffer
0x18046d711  mov     edx, dword ptr [rbp+length]
0x18046d714  jmp     loc_18046D518
0x18046d719  mov     rax, [rbp+string]
0x18046d71d  or      rax, 1
0x18046d721  jmp     loc_18046D5C4
0x18046d726  mov     ecx, ebx; failedFrameHR
0x18046d728  call    OnFailure_2990_
0x18046d72d  lea     box, [rbp+strRuntimeValue]; this
0x18046d731  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x18046d736  mov     eax, ebx
0x18046d738  jmp     loc_18046D585
0x18046d73d  call    OnNewFailure_1172_
0x18046d742  jmp     short loc_18046D6FA
```
