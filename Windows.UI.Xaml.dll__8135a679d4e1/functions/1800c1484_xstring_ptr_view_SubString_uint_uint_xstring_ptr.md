# xstring_ptr_view::SubString(uint,uint,xstring_ptr *)

- ea: `0x1800c1484`
- end: `0x1800c1701`
- name: `?SubString@xstring_ptr_view@@QEBAJIIPEAVxstring_ptr@@@Z`
- size: `637`
- prototype: `HRESULT __fastcall(xstring_ptr_view *this, unsigned int startIndex, unsigned int endIndex, xstring_ptr *pstrSubstring)`
- caller_count: `21`
- callee_count: `6`
- tags: ``

## callers

- `0x18007171c`
- `0x18008e8b4`
- `0x180092a80`
- `0x1800946ac`
- `0x1800a3268`
- `0x1800c039c`
- `0x1800d1678`
- `0x1800d4de4`
- `0x18017389c`
- `0x180174078`
- `0x1802f8c00`
- `0x18038f768`
- `0x1804c5190`
- `0x180529920`
- `0x180598bc0`
- `0x1806aa154`
- `0x180732c80`
- `0x18074fbcc`
- `0x18077979c`
- `0x1807979dc`
- `0x1808078b4`

## callees

- `0x180004bc0`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800c1484`
- `0x1806877a8`
- `0x180687890`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c16f2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800c16f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c15cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c161e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c15cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c161e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c15a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800c15a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c168f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c168f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c1634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c1634`

## pseudocode

```c
__int64 __fastcall xstring_ptr_view::SubString(
        xstring_ptr_view *this,
        unsigned int startIndex,
        unsigned int endIndex,
        xstring_ptr *pstrSubstring)
{
  unsigned __int64 RuntimeStringHandleMarker; // rax
  xstring_ptr_storage *v5; // rbx
  __int64 v6; // rsi
  int v9; // ecx
  HSTRING v10; // r14
  unsigned int v11; // ecx
  unsigned int v12; // edi
  const wchar_t *v13; // rcx
  unsigned int v14; // edi
  unsigned __int64 p_m_ephemeralStorage; // rax
  int v16; // ecx
  wchar_t *v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  unsigned __int64 v21; // rcx
  HSTRING v22; // rcx
  PCWSTR StringRawBuffer; // rax
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+20h] [rbp-40h] BYREF
  xstring_ptr_storage *v25; // [rsp+28h] [rbp-38h]
  const wchar_t *v26; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-28h]
  xephemeral_string_ptr localSubstring; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string; // [rsp+90h] [rbp+30h] BYREF
  UINT32 length; // [rsp+98h] [rbp+38h] BYREF

  RuntimeStringHandleMarker = this->m_encodedStorage.RuntimeStringHandleMarker;
  v5 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v6 = startIndex;
  localSubstring.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  length = 0;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v22 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_33:
    StringRawBuffer = WindowsGetStringRawBuffer(v22, &length);
    v11 = length;
    v10 = (HSTRING)StringRawBuffer;
    goto LABEL_4;
  }
  v9 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
  v10 = *(HSTRING *)RuntimeStringHandleMarker;
  if ( v9 < 0 )
  {
    v22 = *(HSTRING *)RuntimeStringHandleMarker;
    goto LABEL_33;
  }
  v11 = v9 & 0x3FFFFFFF;
  length = v11;
LABEL_4:
  if ( (unsigned int)v6 > endIndex || endIndex > v11 || (unsigned int)v6 > v11 )
  {
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&localSubstring);
    p_m_ephemeralStorage = localSubstring.m_encodedStorage.RuntimeStringHandleMarker;
  }
  else
  {
    v12 = endIndex - v6;
    v25 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( v12 > 0x3FFFFFFF )
    {
      pppStowedExceptions = 0;
      LODWORD(string) = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&string);
      RoFailFastWithErrorContextInternal2(-2147418113, (unsigned int)string, pppStowedExceptions);
      v5 = v25;
    }
    v13 = (const wchar_t *)v10 + v6;
    v26 = v13;
    v14 = v12 & 0x3FFFFFFF | 0x40000000;
    v27 = v14;
    if ( ((unsigned __int8)v5 & 1) != 0 )
    {
      WindowsDeleteString((HSTRING)((unsigned __int64)v5 & 0xFFFFFFFFFFFFFFFEuLL));
      v13 = v26;
      v14 = v27;
    }
    v25 = (xstring_ptr_storage *)&v26;
    if ( ((unsigned __int8)&v26 & 1) != 0 )
    {
      LODWORD(string) = 0;
      localSubstring.m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer((HSTRING)&v26, (UINT32 *)&string);
      v14 = (unsigned int)string & 0x3FFFFFFF;
    }
    else
    {
      localSubstring.m_ephemeralStorage.Buffer = v13;
    }
    *((_DWORD *)&localSubstring.m_ephemeralStorage + 2) = v14 & 0x3FFFFFFF | 0x40000000;
    if ( ((__int64)localSubstring.m_encodedStorage.Storage & 1) != 0 )
      WindowsDeleteString((HSTRING)(localSubstring.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
    p_m_ephemeralStorage = (unsigned __int64)&localSubstring.m_ephemeralStorage;
    localSubstring.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&localSubstring.m_ephemeralStorage;
  }
  if ( ((__int64)localSubstring.m_encodedStorage.Storage & 1) != 0 )
  {
    v18 = WindowsDuplicateString((HSTRING)(p_m_ephemeralStorage & 0xFFFFFFFFFFFFFFFEuLL), &string);
    v19 = v18;
    if ( v18 < 0 )
      goto LABEL_23;
LABEL_31:
    p_m_ephemeralStorage = (unsigned __int64)string | 1;
    goto LABEL_27;
  }
  if ( p_m_ephemeralStorage && (*(_DWORD *)(p_m_ephemeralStorage + 8) & 0x40000000) != 0 )
  {
    length = 0;
    if ( (p_m_ephemeralStorage & 1) != 0 )
    {
      v17 = (wchar_t *)(p_m_ephemeralStorage & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      v16 = *(_DWORD *)(p_m_ephemeralStorage + 8);
      v17 = *(wchar_t **)p_m_ephemeralStorage;
      if ( v16 >= 0 )
      {
        length = v16 & 0x3FFFFFFF;
        goto LABEL_22;
      }
    }
    v17 = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)v17, &length);
LABEL_22:
    v18 = WindowsCreateString(v17, length, &string);
    v19 = v18;
    if ( v18 < 0 )
    {
LABEL_23:
      OnFailure_2990_(v18);
      OnFailure_2990_(v19);
      return v19;
    }
    goto LABEL_31;
  }
  v19 = 0;
LABEL_27:
  v21 = pstrSubstring->m_encodedStorage.RuntimeStringHandleMarker;
  string = (HSTRING)p_m_ephemeralStorage;
  if ( (v21 & 1) != 0 )
  {
    WindowsDeleteString((HSTRING)(v21 & 0xFFFFFFFFFFFFFFFEuLL));
    p_m_ephemeralStorage = (unsigned __int64)string;
  }
  pstrSubstring->m_encodedStorage.RuntimeStringHandleMarker = p_m_ephemeralStorage;
  return v19;
}

```

## disassembly

```asm
0x1800c1484  mov     [rsp-28h+arg_10], rbx
0x1800c1489  mov     [rsp-28h+arg_18], rsi
0x1800c148e  push    rbp
0x1800c148f  push    rdi
0x1800c1490  push    r13
0x1800c1492  push    r14
0x1800c1494  push    r15
0x1800c1496  mov     rbp, rsp
0x1800c1499  sub     rsp, 60h
0x1800c149d  mov     rax, [this]
0x1800c14a0  lea     rbx, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800c14a7  mov     esi, startIndex
0x1800c14a9  mov     r15, pstrSubstring
0x1800c14ac  mov     qword ptr [rbp+localSubstring.m_encodedStorage.___u0], rbx
0x1800c14b0  mov     edi, endIndex
0x1800c14b3  mov     [rbp+length], 0
0x1800c14ba  mov     r13d, 3FFFFFFFh
0x1800c14c0  test    al, 1
0x1800c14c2  jnz     loc_1800C164A
0x1800c14c8  mov     ecx, [rax+8]
0x1800c14cb  mov     r14, [rax]
0x1800c14ce  test    ecx, ecx
0x1800c14d0  js      loc_1800C16A4
0x1800c14d6  and     ecx, r13d
0x1800c14d9  mov     [rbp+length], ecx
0x1800c14dc  cmp     esi, edi
0x1800c14de  ja      loc_1800C1603
0x1800c14e4  cmp     edi, ecx
0x1800c14e6  ja      loc_1800C1603
0x1800c14ec  cmp     esi, ecx
0x1800c14ee  ja      loc_1800C1603
0x1800c14f4  sub     edi, esi
0x1800c14f6  mov     [rbp+var_38], rbx
0x1800c14fa  cmp     edi, r13d
0x1800c14fd  ja      loc_1800C16B5
0x1800c1503  lea     this, [r14+rsi*2]
0x1800c1507  and     edi, r13d
0x1800c150a  mov     esi, 40000000h
0x1800c150f  mov     [rbp+var_30], this
0x1800c1513  or      edi, esi
0x1800c1515  mov     [rbp+var_28], edi
0x1800c1518  test    bl, 1
0x1800c151b  jz      short loc_1800C1531
0x1800c151d  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800c1521  mov     this, rbx; string
0x1800c1524  call    cs:__imp_WindowsDeleteString
0x1800c152a  mov     this, [rbp+var_30]
0x1800c152e  mov     edi, [rbp+var_28]
0x1800c1531  lea     rax, [rbp+var_30]
0x1800c1535  mov     [rbp+var_38], rax
0x1800c1539  lea     rax, [rbp+var_30]
0x1800c153d  test    al, 1
0x1800c153f  jnz     loc_1800C167C
0x1800c1545  mov     qword ptr [rbp+localSubstring.m_ephemeralStorage.___u0], this
0x1800c1549  mov     this, qword ptr [rbp+localSubstring.m_encodedStorage.___u0]
0x1800c154d  and     edi, r13d
0x1800c1550  or      edi, esi
0x1800c1552  mov     dword ptr [rbp+localSubstring.m_ephemeralStorage.Count], edi
0x1800c1555  test    cl, 1
0x1800c1558  jnz     loc_1800C161A
0x1800c155e  lea     rax, [rbp+localSubstring.m_ephemeralStorage]
0x1800c1562  mov     qword ptr [rbp+localSubstring.m_encodedStorage.___u0], rax
0x1800c1566  test    byte ptr [rbp+localSubstring.m_encodedStorage.___u0], 1
0x1800c156a  jnz     loc_1800C1629
0x1800c1570  test    rax, rax
0x1800c1573  jz      short loc_1800C15F3
0x1800c1575  test    [rax+8], esi
0x1800c1578  jz      short loc_1800C15F3
0x1800c157a  mov     [rbp+length], 0
0x1800c1581  test    al, 1
0x1800c1583  jnz     loc_1800C1666
0x1800c1589  mov     ecx, [rax+8]
0x1800c158c  mov     rax, [rax]
0x1800c158f  test    ecx, ecx
0x1800c1591  js      loc_1800C166A
0x1800c1597  and     ecx, r13d
0x1800c159a  mov     [rbp+length], ecx
0x1800c159d  mov     startIndex, [rbp+length]; length
0x1800c15a0  lea     r8, [rbp+string]; string
0x1800c15a4  mov     this, rax; sourceString
0x1800c15a7  call    cs:__imp_WindowsCreateString
0x1800c15ad  mov     ebx, eax
0x1800c15af  test    eax, eax
0x1800c15b1  jns     loc_1800C1640
0x1800c15b7  mov     ecx, eax; failedFrameHR
0x1800c15b9  call    OnFailure_2990_
0x1800c15be  mov     ecx, ebx; failedFrameHR
0x1800c15c0  call    OnFailure_2990_
0x1800c15c5  jmp     short loc_1800C15D8
0x1800c15c7  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c15cb  call    cs:__imp_WindowsDeleteString
0x1800c15d1  mov     rax, [rbp+string]
0x1800c15d5  mov     [r15], rax
0x1800c15d8  lea     r11, [rsp+60h+var_s0]
0x1800c15dd  mov     eax, ebx
0x1800c15df  mov     rbx, [r11+40h]
0x1800c15e3  mov     rsi, [r11+48h]
0x1800c15e7  mov     rsp, r11
0x1800c15ea  pop     r15
0x1800c15ec  pop     r14
0x1800c15ee  pop     r13
0x1800c15f0  pop     rdi
0x1800c15f1  pop     rbp
0x1800c15f2  retn
0x1800c15f3  xor     ebx, ebx
0x1800c15f5  mov     this, [r15]
0x1800c15f8  mov     [rbp+string], rax
0x1800c15fc  test    cl, 1
0x1800c15ff  jz      short loc_1800C15D5
0x1800c1601  jmp     short loc_1800C15C7
0x1800c1603  lea     this, [rbp+localSubstring]; this
0x1800c1607  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c160c  mov     rax, qword ptr [rbp+localSubstring.m_encodedStorage.___u0]
0x1800c1610  mov     esi, 40000000h
0x1800c1615  jmp     loc_1800C1566
0x1800c161a  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c161e  call    cs:__imp_WindowsDeleteString
0x1800c1624  jmp     loc_1800C155E
0x1800c1629  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c162d  lea     rdx, [rbp+string]; newString
0x1800c1631  mov     this, rax; string
0x1800c1634  call    cs:__imp_WindowsDuplicateString
0x1800c163a  mov     ebx, eax
0x1800c163c  test    eax, eax
0x1800c163e  js      short loc_1800C16A9
0x1800c1640  mov     rax, [rbp+string]
0x1800c1644  or      rax, 1
0x1800c1648  jmp     short loc_1800C15F5
0x1800c164a  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c164e  mov     this, rax; string
0x1800c1651  lea     rdx, [rbp+length]; length
0x1800c1655  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c165b  mov     ecx, [rbp+length]
0x1800c165e  mov     r14, rax
0x1800c1661  jmp     loc_1800C14DC
0x1800c1666  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c166a  lea     rdx, [rbp+length]; length
0x1800c166e  mov     this, rax; string
0x1800c1671  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1677  jmp     loc_1800C159D
0x1800c167c  lea     this, [rbp+var_30]
0x1800c1680  mov     dword ptr [rbp+string], 0
0x1800c1687  and     this, 0FFFFFFFFFFFFFFFEh; string
0x1800c168b  lea     rdx, [rbp+string]; length
0x1800c168f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1695  mov     edi, dword ptr [rbp+string]
0x1800c1698  mov     qword ptr [rbp+localSubstring.m_ephemeralStorage.___u0], rax
0x1800c169c  and     edi, r13d
0x1800c169f  jmp     loc_1800C1549
0x1800c16a4  mov     this, r14
0x1800c16a7  jmp     short loc_1800C1651
0x1800c16a9  mov     ecx, eax; failedFrameHR
0x1800c16ab  call    OnFailure_2990_
0x1800c16b0  jmp     loc_1800C15BE
0x1800c16b5  mov     ebx, 8000FFFFh
0x1800c16ba  mov     [rbp+pppStowedExceptions], 0
0x1800c16c2  mov     ecx, ebx; errorCode
0x1800c16c4  mov     dword ptr [rbp+string], 0
0x1800c16cb  call    TraceForFailFast
0x1800c16d0  xor     endIndex, endIndex; contextRecord
0x1800c16d3  xor     startIndex, startIndex; directCallerReturnAddress
0x1800c16d5  mov     ecx, ebx; failedFrameHR
0x1800c16d7  call    OnNewFailureEncountered
0x1800c16dc  lea     rdx, [rbp+string]; pcStowedExceptions
0x1800c16e0  lea     this, [rbp+pppStowedExceptions]; pppStowedExceptions
0x1800c16e4  call    GetStowedExceptionsForFailFast
0x1800c16e9  mov     r8, [rbp+pppStowedExceptions]
0x1800c16ed  mov     ecx, ebx
0x1800c16ef  mov     startIndex, dword ptr [rbp+string]
0x1800c16f2  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1800c16f8  mov     rbx, [rbp+var_38]
0x1800c16fc  jmp     loc_1800C1503
```
