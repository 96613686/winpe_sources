# NLG::RegistryKey::RawValue(ushort const *)

- ea: `0x18004b4f8`
- end: `0x18004b9b1`
- name: `?RawValue@RegistryKey@NLG@@QEBA?AV_variant_t@@PEBG@Z`
- size: `1209`
- prototype: `struct _variant_t __high(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004997c`
- `0x180049e8c`

## callees

- `0x18001a0d8`
- `0x18002ee48`
- `0x180030c5c`
- `0x180035640`
- `0x18003ed6c`
- `0x180041364`
- `0x18004b4f8`
- `0x18009e300`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b73c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b807`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b89e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b73c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b807`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b89e`
- `OLEAUT32!__imp_VariantInit` at `0x18004b981`
- `OLEAUT32!__imp_VariantInit` at `0x18004b981`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b564`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b62f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b6a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b712`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b79d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b87b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b564`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b62f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b6a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b712`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b79d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b87b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b8ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
VARIANTARG *__fastcall NLG::RegistryKey::RawValue(HKEY *a1, VARIANTARG *a2, const WCHAR *a3)
{
  LONG v6; // eax
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rax
  BYTE *v9; // r14
  unsigned int v10; // edx
  unsigned int v11; // edx
  volatile signed __int32 **p_cbData; // rcx
  const unsigned __int16 *v13; // rax
  LSTATUS Value; // eax
  const unsigned __int16 *v15; // rax
  BYTE *v16; // r14
  unsigned int v17; // edx
  _bstr_t *v18; // rax
  BYTE lpData[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  volatile signed __int32 *cbData; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  VARIANTARG *v27; // [rsp+98h] [rbp-68h]
  OLECHAR v28[1024]; // [rsp+A0h] [rbp-60h] BYREF
  const void *retaddr; // [rsp+8D8h] [rbp+7D8h]

  v26 = -2;
  v27 = a2;
  v21 = 0;
  Type = 0;
  if ( RegQueryValueExW(*a1, a3, 0, &Type, 0, 0) )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  if ( !Type )
  {
    VariantInit(a2);
LABEL_40:
    v21 = 1;
    return a2;
  }
  if ( Type == 1 || Type == 2 )
  {
    LODWORD(cbData) = 0;
    *(_DWORD *)lpData = 2048;
    Value = RegQueryValueExW(*a1, a3, 0, (LPDWORD)&cbData, (LPBYTE)v28, (LPDWORD)lpData);
    if ( Value )
    {
      if ( Value == 234 )
      {
        v15 = SysAllocStringLen(v28, *(_DWORD *)lpData >> 1);
        v16 = (BYTE *)v15;
        if ( !v15 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        _bstr_t::_bstr_t((_bstr_t *)Data, v15);
        if ( !RegQueryValueExW(*a1, a3, 0, (LPDWORD)&cbData, v16, (LPDWORD)lpData) )
        {
          _variant_t::_variant_t((_variant_t *)a2, (const struct _bstr_t *)Data);
          v21 = 1;
LABEL_35:
          p_cbData = (volatile signed __int32 **)Data;
          goto LABEL_23;
        }
        _bstr_t::_Free((volatile signed __int32 **)Data, v17);
      }
      CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    v18 = _bstr_t::_bstr_t((_bstr_t *)Data, v28);
    _variant_t::_variant_t((_variant_t *)a2, v18);
    v21 = 1;
    goto LABEL_35;
  }
  if ( Type != 3 )
  {
    if ( Type == 4 )
    {
      *(_DWORD *)lpData = 0;
      LODWORD(cbData) = 4;
      if ( RegQueryValueExW(*a1, a3, 0, &Type, lpData, (LPDWORD)&cbData) )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v6 = *(_DWORD *)lpData;
      a2->vt = 3;
      a2->lVal = v6;
      goto LABEL_40;
    }
    if ( Type != 7 )
    {
      if ( Type != 11 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      *(_QWORD *)Data = 0;
      LODWORD(cbData) = 8;
      if ( RegQueryValueExW(*a1, a3, 0, &Type, Data, (LPDWORD)&cbData) )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      a2->vt = 20;
      a2->llVal = *(_QWORD *)Data;
      goto LABEL_40;
    }
  }
  *(_DWORD *)lpData = 2048;
  v7 = RegQueryValueExW(*a1, a3, 0, &Type, (LPBYTE)v28, (LPDWORD)lpData);
  if ( !v7 )
  {
    v13 = SysAllocStringLen(v28, *(_DWORD *)lpData >> 1);
    if ( !v13 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    _variant_t::_variant_t((_variant_t *)a2, v13);
    goto LABEL_40;
  }
  if ( v7 != 234 )
  {
LABEL_25:
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  *(_DWORD *)lpData += 2;
  v8 = SysAllocStringLen(v28, *(_DWORD *)lpData >> 1);
  v9 = (BYTE *)v8;
  if ( !v8 )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  _bstr_t::_bstr_t((_bstr_t *)&cbData, v8);
  if ( RegQueryValueExW(*a1, a3, 0, &Type, v9, (LPDWORD)lpData) )
  {
    _bstr_t::_Free(&cbData, v10);
    goto LABEL_25;
  }
  _variant_t::_variant_t((_variant_t *)a2, (const struct _bstr_t *)&cbData);
  v21 = 1;
  p_cbData = &cbData;
LABEL_23:
  _bstr_t::_Free(p_cbData, v11);
  return a2;
}

```

## disassembly

```asm
0x18004b4f8  push    rbp
0x18004b4fa  push    rbx
0x18004b4fb  push    rsi
0x18004b4fc  push    rdi
0x18004b4fd  push    r14
0x18004b4ff  lea     rbp, [rsp-7B0h]
0x18004b507  sub     rsp, 8B0h
0x18004b50e  mov     [rbp+7D0h+var_840], 0FFFFFFFFFFFFFFFEh
0x18004b516  mov     rax, cs:__security_cookie
0x18004b51d  xor     rax, rsp
0x18004b520  mov     [rbp+7D0h+var_30], rax
0x18004b527  mov     rsi, r8
0x18004b52a  mov     rbx, rdx
0x18004b52d  mov     rdi, rcx
0x18004b530  mov     [rbp+7D0h+var_838], rdx
0x18004b534  mov     [rsp+8D0h+var_89C], 0
0x18004b53c  mov     [rsp+8D0h+Type], 0
0x18004b544  mov     [rsp+8D0h+lpcbData], 0; lpcbData
0x18004b54d  mov     [rsp+8D0h+lpData], 0; lpData
0x18004b556  lea     r9, [rsp+8D0h+Type]; lpType
0x18004b55b  xor     r8d, r8d; lpReserved
0x18004b55e  mov     rdx, rsi; lpValueName
0x18004b561  mov     rcx, [rcx]; hKey
0x18004b564  call    cs:__imp_RegQueryValueExW
0x18004b56a  test    eax, eax
0x18004b56c  jz      short loc_18004B596
0x18004b56e  mov     r8, [rbp+7D8h]; void *
0x18004b575  mov     edx, 80004005h; int
0x18004b57a  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b57f  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b584  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b58b  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b590  call    _CxxThrowException_0
0x18004b596  mov     eax, [rsp+8D0h+Type]
0x18004b59a  test    eax, eax
0x18004b59c  jz      loc_18004B97E
0x18004b5a2  sub     eax, 1
0x18004b5a5  jz      loc_18004B84A
0x18004b5ab  sub     eax, 1
0x18004b5ae  jz      loc_18004B84A
0x18004b5b4  sub     eax, 1
0x18004b5b7  jz      loc_18004B6E9
0x18004b5bd  sub     eax, 1
0x18004b5c0  jz      loc_18004B674
0x18004b5c6  sub     eax, 3
0x18004b5c9  jz      loc_18004B6E9
0x18004b5cf  cmp     eax, 4
0x18004b5d2  jz      short loc_18004B5FC
0x18004b5d4  mov     r8, [rbp+7D8h]; void *
0x18004b5db  mov     edx, 80004005h; int
0x18004b5e0  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b5e5  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b5ea  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b5f1  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b5f6  call    _CxxThrowException_0
0x18004b5fc  mov     qword ptr [rsp+8D0h+Data], 0
0x18004b605  mov     dword ptr [rsp+8D0h+cbData], 8
0x18004b60d  lea     rax, [rsp+8D0h+cbData]
0x18004b612  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b617  lea     rax, [rsp+8D0h+Data]
0x18004b61c  mov     [rsp+8D0h+lpData], rax; lpData
0x18004b621  lea     r9, [rsp+8D0h+Type]; lpType
0x18004b626  xor     r8d, r8d; lpReserved
0x18004b629  mov     rdx, rsi; lpValueName
0x18004b62c  mov     rcx, [rdi]; hKey
0x18004b62f  call    cs:__imp_RegQueryValueExW
0x18004b635  test    eax, eax
0x18004b637  jz      short loc_18004B661
0x18004b639  mov     r8, [rbp+7D8h]; void *
0x18004b640  mov     edx, 80004005h; int
0x18004b645  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b64a  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b64f  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b656  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b65b  call    _CxxThrowException_0
0x18004b661  mov     word ptr [rbx], 14h
0x18004b666  mov     rcx, qword ptr [rsp+8D0h+Data]
0x18004b66b  mov     [rbx+8], rcx
0x18004b66f  jmp     loc_18004B988
0x18004b674  mov     dword ptr [rsp+8D0h+var_8A0], 0
0x18004b67c  mov     dword ptr [rsp+8D0h+cbData], 4
0x18004b684  lea     rax, [rsp+8D0h+cbData]
0x18004b689  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b68e  lea     rax, [rsp+8D0h+var_8A0]
0x18004b693  mov     [rsp+8D0h+lpData], rax; lpData
0x18004b698  lea     r9, [rsp+8D0h+Type]; lpType
0x18004b69d  xor     r8d, r8d; lpReserved
0x18004b6a0  mov     rdx, rsi; lpValueName
0x18004b6a3  mov     rcx, [rdi]; hKey
0x18004b6a6  call    cs:__imp_RegQueryValueExW
0x18004b6ac  test    eax, eax
0x18004b6ae  jz      short loc_18004B6D8
0x18004b6b0  mov     r8, [rbp+7D8h]; void *
0x18004b6b7  mov     edx, 80004005h; int
0x18004b6bc  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b6c1  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b6c6  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b6cd  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b6d2  call    _CxxThrowException_0
0x18004b6d8  mov     eax, dword ptr [rsp+8D0h+var_8A0]
0x18004b6dc  mov     word ptr [rbx], 3
0x18004b6e1  mov     [rbx+8], eax
0x18004b6e4  jmp     loc_18004B988
0x18004b6e9  mov     dword ptr [rsp+8D0h+var_8A0], 800h
0x18004b6f1  lea     rax, [rsp+8D0h+var_8A0]
0x18004b6f6  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b6fb  lea     rax, [rbp+7D0h+var_830]
0x18004b6ff  mov     [rsp+8D0h+lpData], rax; lpData
0x18004b704  lea     r9, [rsp+8D0h+Type]; lpType
0x18004b709  xor     r8d, r8d; lpReserved
0x18004b70c  mov     rdx, rsi; lpValueName
0x18004b70f  mov     rcx, [rdi]; hKey
0x18004b712  call    cs:__imp_RegQueryValueExW
0x18004b718  test    eax, eax
0x18004b71a  jz      loc_18004B7FD
0x18004b720  cmp     eax, 0EAh
0x18004b725  jnz     loc_18004B7D5
0x18004b72b  mov     edx, dword ptr [rsp+8D0h+var_8A0]
0x18004b72f  add     edx, 2
0x18004b732  mov     dword ptr [rsp+8D0h+var_8A0], edx
0x18004b736  shr     edx, 1; ui
0x18004b738  lea     rcx, [rbp+7D0h+var_830]; strIn
0x18004b73c  call    cs:__imp_SysAllocStringLen
0x18004b742  mov     r14, rax
0x18004b745  test    rax, rax
0x18004b748  jnz     short loc_18004B772
0x18004b74a  mov     r8, [rbp+7D8h]; void *
0x18004b751  mov     edx, 8007000Eh; int
0x18004b756  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b75b  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b760  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b767  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b76c  call    _CxxThrowException_0
0x18004b772  mov     rdx, r14; unsigned __int16 *
0x18004b775  lea     rcx, [rsp+8D0h+cbData]; this
0x18004b77a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b77f  nop
0x18004b780  lea     rax, [rsp+8D0h+var_8A0]
0x18004b785  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b78a  mov     [rsp+8D0h+lpData], r14; lpData
0x18004b78f  lea     r9, [rsp+8D0h+Type]; lpType
0x18004b794  xor     r8d, r8d; lpReserved
0x18004b797  mov     rdx, rsi; lpValueName
0x18004b79a  mov     rcx, [rdi]; hKey
0x18004b79d  call    cs:__imp_RegQueryValueExW
0x18004b7a3  test    eax, eax
0x18004b7a5  jnz     short loc_18004B7CB
0x18004b7a7  lea     rdx, [rsp+8D0h+cbData]; struct _bstr_t *
0x18004b7ac  mov     rcx, rbx; this
0x18004b7af  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x18004b7b4  mov     [rsp+8D0h+var_89C], 1
0x18004b7bc  lea     rcx, [rsp+8D0h+cbData]; this
0x18004b7c1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b7c6  jmp     loc_18004B990
0x18004b7cb  lea     rcx, [rsp+8D0h+cbData]; this
0x18004b7d0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b7d5  mov     r8, [rbp+7D8h]; void *
0x18004b7dc  mov     edx, 80004005h; int
0x18004b7e1  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b7e6  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b7eb  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b7f2  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b7f7  call    _CxxThrowException_0
0x18004b7fd  mov     edx, dword ptr [rsp+8D0h+var_8A0]
0x18004b801  shr     edx, 1; ui
0x18004b803  lea     rcx, [rbp+7D0h+var_830]; strIn
0x18004b807  call    cs:__imp_SysAllocStringLen
0x18004b80d  test    rax, rax
0x18004b810  jnz     short loc_18004B83A
0x18004b812  mov     r8, [rbp+7D8h]; void *
0x18004b819  mov     edx, 8007000Eh; int
0x18004b81e  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b823  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b828  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b82f  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b834  call    _CxxThrowException_0
0x18004b83a  mov     rdx, rax; unsigned __int16 *
0x18004b83d  mov     rcx, rbx; this
0x18004b840  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004b845  jmp     loc_18004B988
0x18004b84a  mov     dword ptr [rsp+8D0h+cbData], 0
0x18004b852  mov     dword ptr [rsp+8D0h+var_8A0], 800h
0x18004b85a  lea     rax, [rsp+8D0h+var_8A0]
0x18004b85f  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b864  lea     rax, [rbp+7D0h+var_830]
0x18004b868  mov     [rsp+8D0h+lpData], rax; lpData
0x18004b86d  lea     r9, [rsp+8D0h+cbData]; lpType
0x18004b872  xor     r8d, r8d; lpReserved
0x18004b875  mov     rdx, rsi; lpValueName
0x18004b878  mov     rcx, [rdi]; hKey
0x18004b87b  call    cs:__imp_RegQueryValueExW
0x18004b881  test    eax, eax
0x18004b883  jz      loc_18004B95A
0x18004b889  cmp     eax, 0EAh
0x18004b88e  jnz     loc_18004B932
0x18004b894  mov     edx, dword ptr [rsp+8D0h+var_8A0]
0x18004b898  shr     edx, 1; ui
0x18004b89a  lea     rcx, [rbp+7D0h+var_830]; strIn
0x18004b89e  call    cs:__imp_SysAllocStringLen
0x18004b8a4  mov     r14, rax
0x18004b8a7  test    rax, rax
0x18004b8aa  jnz     short loc_18004B8D4
0x18004b8ac  mov     r8, [rbp+7D8h]; void *
0x18004b8b3  mov     edx, 8007000Eh; int
0x18004b8b8  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b8bd  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b8c2  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b8c9  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b8ce  call    _CxxThrowException_0
0x18004b8d4  mov     rdx, r14; unsigned __int16 *
0x18004b8d7  lea     rcx, [rsp+8D0h+Data]; this
0x18004b8dc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b8e1  nop
0x18004b8e2  lea     rax, [rsp+8D0h+var_8A0]
0x18004b8e7  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18004b8ec  mov     [rsp+8D0h+lpData], r14; lpData
0x18004b8f1  lea     r9, [rsp+8D0h+cbData]; lpType
0x18004b8f6  xor     r8d, r8d; lpReserved
0x18004b8f9  mov     rdx, rsi; lpValueName
0x18004b8fc  mov     rcx, [rdi]; hKey
0x18004b8ff  call    cs:__imp_RegQueryValueExW
0x18004b905  test    eax, eax
0x18004b907  jnz     short loc_18004B928
0x18004b909  lea     rdx, [rsp+8D0h+Data]; struct _bstr_t *
0x18004b90e  mov     rcx, rbx; this
0x18004b911  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x18004b916  mov     [rsp+8D0h+var_89C], 1
0x18004b91e  lea     rcx, [rsp+8D0h+Data]
0x18004b923  jmp     loc_18004B7C1
0x18004b928  lea     rcx, [rsp+8D0h+Data]; this
0x18004b92d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b932  mov     r8, [rbp+7D8h]; void *
0x18004b939  mov     edx, 80004005h; int
0x18004b93e  lea     rcx, [rsp+8D0h+pExceptionObject]; this
0x18004b943  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b948  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b94f  lea     rcx, [rsp+8D0h+pExceptionObject]; pExceptionObject
0x18004b954  call    _CxxThrowException_0
0x18004b95a  lea     rdx, [rbp+7D0h+var_830]; unsigned __int16 *
0x18004b95e  lea     rcx, [rsp+8D0h+Data]; this
0x18004b963  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b968  nop
0x18004b969  mov     rdx, rax; struct _bstr_t *
0x18004b96c  mov     rcx, rbx; this
0x18004b96f  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x18004b974  mov     [rsp+8D0h+var_89C], 1
0x18004b97c  jmp     short loc_18004B91E
0x18004b97e  mov     rcx, rbx; pvarg
0x18004b981  call    cs:__imp_VariantInit
0x18004b987  nop
0x18004b988  mov     [rsp+8D0h+var_89C], 1
0x18004b990  mov     rax, rbx
0x18004b993  mov     rcx, [rbp+7D0h+var_30]
0x18004b99a  xor     rcx, rsp; StackCookie
0x18004b99d  call    __security_check_cookie
0x18004b9a2  add     rsp, 8B0h
0x18004b9a9  pop     r14
0x18004b9ab  pop     rdi
0x18004b9ac  pop     rsi
0x18004b9ad  pop     rbx
0x18004b9ae  pop     rbp
0x18004b9af  retn
```
