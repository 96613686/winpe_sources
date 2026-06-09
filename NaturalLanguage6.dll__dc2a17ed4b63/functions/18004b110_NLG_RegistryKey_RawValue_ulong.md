# NLG::RegistryKey::RawValue(ulong)

- ea: `0x18004b110`
- end: `0x18004b4f1`
- name: `?RawValue@RegistryKey@NLG@@QEBA?AV_variant_t@@K@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180049e50`

## callees

- `0x18001a0d8`
- `0x18002ee48`
- `0x180030c5c`
- `0x180035640`
- `0x18003ed6c`
- `0x180041364`
- `0x18004b110`
- `0x18009e300`
- `0x18009e3c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b312`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b443`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b312`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b443`
- `OLEAUT32!__imp_VariantInit` at `0x18004b4b2`
- `OLEAUT32!__imp_VariantInit` at `0x18004b4bd`
- `OLEAUT32!__imp_VariantInit` at `0x18004b4b2`
- `OLEAUT32!__imp_VariantInit` at `0x18004b4bd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b1a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b287`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b378`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b1a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b287`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b378`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
VARIANTARG *__fastcall NLG::RegistryKey::RawValue(HKEY *a1, VARIANTARG *a2, DWORD a3)
{
  BYTE *lpData; // rax
  LSTATUS v7; // eax
  BYTE *v8; // rdi
  const unsigned __int16 *v9; // rdx
  LONG v10; // eax
  BSTR v11; // rax
  _bstr_t *v12; // rax
  unsigned int v13; // edx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh]
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  LONG v19; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v21; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-58h]
  VARIANTARG *v24; // [rsp+B0h] [rbp-50h]
  WCHAR ValueName[256]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR strIn[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF
  const void *retaddr; // [rsp+2308h] [rbp+2208h]

  v23 = -2;
  v24 = a2;
  v16 = 0;
  Type = 0;
  cbData = 0;
  v19 = 0;
  *(_QWORD *)Data = 0;
  cchValueName = 256;
  if ( RegEnumValueW(*a1, a3, ValueName, &cchValueName, 0, &Type, 0, 0) )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  switch ( Type )
  {
    case 0u:
      VariantInit(a2);
      goto LABEL_44;
    case 1u:
    case 2u:
    case 3u:
      goto LABEL_13;
    case 4u:
      lpData = (BYTE *)&v19;
      cbData = 4;
      break;
    case 7u:
LABEL_13:
      cbData = 0x2000;
      lpData = (BYTE *)strIn;
      break;
    case 0xBu:
      lpData = Data;
      cbData = 8;
      break;
    default:
      CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
      throw (CNLException *)pExceptionObject;
  }
  cchValueName = 256;
  v7 = RegEnumValueW(*a1, a3, ValueName, &cchValueName, 0, 0, lpData, &cbData);
  if ( v7 )
  {
    if ( v7 != 234 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    if ( Type != 1 && Type != 2 && Type != 3 && Type != 7 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    cbData += 2;
    v8 = (BYTE *)SysAllocStringLen(0, cbData >> 1);
    cchValueName = 256;
    if ( !v8 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    if ( RegEnumValueW(*a1, a3, ValueName, &cchValueName, 0, 0, v8, &cbData) )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    v9 = (const unsigned __int16 *)v8;
    goto LABEL_26;
  }
  if ( !Type )
  {
    VariantInit(a2);
    goto LABEL_44;
  }
  if ( Type != 1 && Type != 2 )
  {
    if ( Type != 3 )
    {
      if ( Type == 4 )
      {
        v10 = v19;
        a2->vt = 3;
        a2->lVal = v10;
        goto LABEL_44;
      }
      if ( Type != 7 )
      {
        if ( Type != 11 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        a2->vt = 20;
        a2->llVal = *(_QWORD *)Data;
        goto LABEL_44;
      }
    }
    v11 = SysAllocStringLen(strIn, cbData >> 1);
    if ( !v11 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    v9 = v11;
LABEL_26:
    _variant_t::_variant_t((_variant_t *)a2, v9);
LABEL_44:
    v16 = 1;
    return a2;
  }
  v12 = _bstr_t::_bstr_t((_bstr_t *)&v21, strIn);
  _variant_t::_variant_t((_variant_t *)a2, v12);
  v16 = 1;
  _bstr_t::_Free(&v21, v13);
  return a2;
}

```

## disassembly

```asm
0x18004b110  push    rbp
0x18004b112  push    rbx
0x18004b113  push    rsi
0x18004b114  push    rdi
0x18004b115  push    r12
0x18004b117  push    r14
0x18004b119  push    r15
0x18004b11b  lea     rbp, [rsp-21D0h]
0x18004b123  mov     eax, 22D0h
0x18004b128  call    _alloca_probe
0x18004b12d  sub     rsp, rax
0x18004b130  mov     [rbp+2200h+var_2258], 0FFFFFFFFFFFFFFFEh
0x18004b138  mov     rax, cs:__security_cookie
0x18004b13f  xor     rax, rsp
0x18004b142  mov     [rbp+2200h+var_40], rax
0x18004b149  mov     r14d, r8d
0x18004b14c  mov     rbx, rdx
0x18004b14f  mov     rsi, rcx
0x18004b152  mov     [rbp+2200h+var_2250], rdx
0x18004b156  xor     r15d, r15d
0x18004b159  mov     [rsp+2300h+var_22BC], r15d
0x18004b15e  mov     [rsp+2300h+Type], r15d
0x18004b163  mov     [rsp+2300h+cbData], r15d
0x18004b168  mov     [rsp+2300h+var_22B0], r15d
0x18004b16d  mov     qword ptr [rsp+2300h+Data], r15
0x18004b172  mov     [rsp+2300h+cchValueName], 100h
0x18004b17a  mov     [rsp+2300h+lpcbData], r15; lpcbData
0x18004b17f  mov     [rsp+2300h+lpData], r15; lpData
0x18004b184  lea     rax, [rsp+2300h+Type]
0x18004b189  mov     [rsp+2300h+lpType], rax; lpType
0x18004b18e  mov     [rsp+2300h+lpReserved], r15; lpReserved
0x18004b193  lea     r9, [rsp+2300h+cchValueName]; lpcchValueName
0x18004b198  lea     r8, [rbp+2200h+ValueName]; lpValueName
0x18004b19c  mov     edx, r14d; dwIndex
0x18004b19f  mov     rcx, [rcx]; hKey
0x18004b1a2  call    cs:__imp_RegEnumValueW
0x18004b1a8  test    eax, eax
0x18004b1aa  jz      short loc_18004B1D4
0x18004b1ac  mov     r8, [rbp+2208h]; void *
0x18004b1b3  mov     edx, 80004005h; int
0x18004b1b8  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b1bd  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b1c2  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b1c9  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b1ce  call    _CxxThrowException_0
0x18004b1d4  mov     eax, [rsp+2300h+Type]
0x18004b1d8  test    eax, eax
0x18004b1da  jz      loc_18004B4BA
0x18004b1e0  mov     edi, 4
0x18004b1e5  lea     r12d, [rdi-1]
0x18004b1e9  sub     eax, 1
0x18004b1ec  jz      short loc_18004B248
0x18004b1ee  sub     eax, 1
0x18004b1f1  jz      short loc_18004B248
0x18004b1f3  sub     eax, 1
0x18004b1f6  jz      short loc_18004B248
0x18004b1f8  sub     eax, 1
0x18004b1fb  jz      short loc_18004B23D
0x18004b1fd  sub     eax, r12d
0x18004b200  jz      short loc_18004B248
0x18004b202  cmp     eax, edi
0x18004b204  jz      short loc_18004B22E
0x18004b206  mov     r8, [rbp+2208h]; void *
0x18004b20d  mov     edx, 80004005h; int
0x18004b212  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b217  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b21c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b223  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b228  call    _CxxThrowException_0
0x18004b22e  lea     rax, [rsp+2300h+Data]
0x18004b233  mov     [rsp+2300h+cbData], 8
0x18004b23b  jmp     short loc_18004B257
0x18004b23d  lea     rax, [rsp+2300h+var_22B0]
0x18004b242  mov     [rsp+2300h+cbData], edi
0x18004b246  jmp     short loc_18004B257
0x18004b248  mov     [rsp+2300h+cbData], 2000h
0x18004b250  lea     rax, [rbp+2200h+strIn]
0x18004b257  mov     [rsp+2300h+cchValueName], 100h
0x18004b25f  lea     rcx, [rsp+2300h+cbData]
0x18004b264  mov     [rsp+2300h+lpcbData], rcx; lpcbData
0x18004b269  mov     [rsp+2300h+lpData], rax; lpData
0x18004b26e  mov     [rsp+2300h+lpType], r15; lpType
0x18004b273  mov     [rsp+2300h+lpReserved], r15; lpReserved
0x18004b278  lea     r9, [rsp+2300h+cchValueName]; lpcchValueName
0x18004b27d  lea     r8, [rbp+2200h+ValueName]; lpValueName
0x18004b281  mov     edx, r14d; dwIndex
0x18004b284  mov     rcx, [rsi]; hKey
0x18004b287  call    cs:__imp_RegEnumValueW
0x18004b28d  test    eax, eax
0x18004b28f  jz      loc_18004B3BA
0x18004b295  cmp     eax, 0EAh
0x18004b29a  jz      short loc_18004B2C4
0x18004b29c  mov     r8, [rbp+2208h]; void *
0x18004b2a3  mov     edx, 80004005h; int
0x18004b2a8  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b2ad  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b2b2  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b2b9  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b2be  call    _CxxThrowException_0
0x18004b2c4  mov     eax, [rsp+2300h+Type]
0x18004b2c8  sub     eax, 1
0x18004b2cb  jz      short loc_18004B303
0x18004b2cd  sub     eax, 1
0x18004b2d0  jz      short loc_18004B303
0x18004b2d2  sub     eax, 1
0x18004b2d5  jz      short loc_18004B303
0x18004b2d7  cmp     eax, edi
0x18004b2d9  jz      short loc_18004B303
0x18004b2db  mov     r8, [rbp+2208h]; void *
0x18004b2e2  mov     edx, 80004005h; int
0x18004b2e7  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b2ec  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b2f1  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b2f8  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b2fd  call    _CxxThrowException_0
0x18004b303  mov     edx, [rsp+2300h+cbData]
0x18004b307  add     edx, 2
0x18004b30a  mov     [rsp+2300h+cbData], edx
0x18004b30e  shr     edx, 1; ui
0x18004b310  xor     ecx, ecx; strIn
0x18004b312  call    cs:__imp_SysAllocStringLen
0x18004b318  mov     rdi, rax
0x18004b31b  mov     [rsp+2300h+cchValueName], 100h
0x18004b323  test    rax, rax
0x18004b326  jnz     short loc_18004B350
0x18004b328  mov     r8, [rbp+2208h]; void *
0x18004b32f  mov     edx, 8007000Eh; int
0x18004b334  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b339  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b33e  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b345  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b34a  call    _CxxThrowException_0
0x18004b350  lea     rax, [rsp+2300h+cbData]
0x18004b355  mov     [rsp+2300h+lpcbData], rax; lpcbData
0x18004b35a  mov     [rsp+2300h+lpData], rdi; lpData
0x18004b35f  mov     [rsp+2300h+lpType], r15; lpType
0x18004b364  mov     [rsp+2300h+lpReserved], r15; lpReserved
0x18004b369  lea     r9, [rsp+2300h+cchValueName]; lpcchValueName
0x18004b36e  lea     r8, [rbp+2200h+ValueName]; lpValueName
0x18004b372  mov     edx, r14d; dwIndex
0x18004b375  mov     rcx, [rsi]; hKey
0x18004b378  call    cs:__imp_RegEnumValueW
0x18004b37e  test    eax, eax
0x18004b380  jnz     short loc_18004B392
0x18004b382  mov     rdx, rdi; unsigned __int16 *
0x18004b385  mov     rcx, rbx; this
0x18004b388  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004b38d  jmp     loc_18004B4C4
0x18004b392  mov     r8, [rbp+2208h]; void *
0x18004b399  mov     edx, 80004005h; int
0x18004b39e  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b3a3  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b3a8  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b3af  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b3b4  call    _CxxThrowException_0
0x18004b3ba  mov     eax, [rsp+2300h+Type]
0x18004b3be  test    eax, eax
0x18004b3c0  jz      loc_18004B4AF
0x18004b3c6  sub     eax, 1
0x18004b3c9  jz      loc_18004B47E
0x18004b3cf  sub     eax, 1
0x18004b3d2  jz      loc_18004B47E
0x18004b3d8  sub     eax, 1
0x18004b3db  jz      short loc_18004B436
0x18004b3dd  sub     eax, 1
0x18004b3e0  jz      short loc_18004B426
0x18004b3e2  sub     eax, r12d
0x18004b3e5  jz      short loc_18004B436
0x18004b3e7  cmp     eax, edi
0x18004b3e9  jz      short loc_18004B413
0x18004b3eb  mov     r8, [rbp+2208h]; void *
0x18004b3f2  mov     edx, 80004005h; int
0x18004b3f7  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b3fc  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b401  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b408  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b40d  call    _CxxThrowException_0
0x18004b413  mov     word ptr [rbx], 14h
0x18004b418  mov     rax, qword ptr [rsp+2300h+Data]
0x18004b41d  mov     [rbx+8], rax
0x18004b421  jmp     loc_18004B4C4
0x18004b426  mov     eax, [rsp+2300h+var_22B0]
0x18004b42a  mov     [rbx], r12w
0x18004b42e  mov     [rbx+8], eax
0x18004b431  jmp     loc_18004B4C4
0x18004b436  mov     edx, [rsp+2300h+cbData]
0x18004b43a  shr     edx, 1; ui
0x18004b43c  lea     rcx, [rbp+2200h+strIn]; strIn
0x18004b443  call    cs:__imp_SysAllocStringLen
0x18004b449  test    rax, rax
0x18004b44c  jnz     short loc_18004B476
0x18004b44e  mov     r8, [rbp+2208h]; void *
0x18004b455  mov     edx, 8007000Eh; int
0x18004b45a  lea     rcx, [rsp+2300h+pExceptionObject]; this
0x18004b45f  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004b464  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004b46b  lea     rcx, [rsp+2300h+pExceptionObject]; pExceptionObject
0x18004b470  call    _CxxThrowException_0
0x18004b476  mov     rdx, rax
0x18004b479  jmp     loc_18004B385
0x18004b47e  lea     rdx, [rbp+2200h+strIn]; unsigned __int16 *
0x18004b485  lea     rcx, [rsp+2300h+var_22A0]; this
0x18004b48a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004b48f  nop
0x18004b490  mov     rdx, rax; struct _bstr_t *
0x18004b493  mov     rcx, rbx; this
0x18004b496  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x18004b49b  mov     [rsp+2300h+var_22BC], 1
0x18004b4a3  lea     rcx, [rsp+2300h+var_22A0]; this
0x18004b4a8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004b4ad  jmp     short loc_18004B4CC
0x18004b4af  mov     rcx, rbx; pvarg
0x18004b4b2  call    cs:__imp_VariantInit
0x18004b4b8  jmp     short loc_18004B4C4
0x18004b4ba  mov     rcx, rbx; pvarg
0x18004b4bd  call    cs:__imp_VariantInit
0x18004b4c3  nop
0x18004b4c4  mov     [rsp+2300h+var_22BC], 1
0x18004b4cc  mov     rax, rbx
0x18004b4cf  mov     rcx, [rbp+2200h+var_40]
0x18004b4d6  xor     rcx, rsp; StackCookie
0x18004b4d9  call    __security_check_cookie
0x18004b4de  add     rsp, 22D0h
0x18004b4e5  pop     r15
0x18004b4e7  pop     r14
0x18004b4e9  pop     r12
0x18004b4eb  pop     rdi
0x18004b4ec  pop     rsi
0x18004b4ed  pop     rbx
0x18004b4ee  pop     rbp
0x18004b4ef  retn
```
