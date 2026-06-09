# ResourceLoader6::SimpleResourceLoader::SimpleResourceLoader(ushort const *,ushort const *)

- ea: `0x180016bf4`
- end: `0x180016e9a`
- name: `??0SimpleResourceLoader@ResourceLoader6@@QEAA@PEBG0@Z`
- size: `678`
- prototype: `struct IUnknown *__fastcall(struct IUnknown *this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001681c`
- `0x180044fb0`

## callees

- `0x180003894`
- `0x180005190`
- `0x180016bf4`
- `0x180019a50`
- `0x180030c5c`
- `0x180032594`
- `0x180035640`
- `0x180036b04`
- `0x18003ed6c`
- `0x180049b2c`
- `0x18009e2c2`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016ca4`
- `OLEAUT32!__imp_SysAllocString` at `0x180016d23`
- `OLEAUT32!__imp_SysAllocString` at `0x180016ca4`
- `OLEAUT32!__imp_SysAllocString` at `0x180016d23`
- `OLEAUT32!__imp_VariantClear` at `0x180016d0f`
- `OLEAUT32!__imp_VariantClear` at `0x180016d94`
- `OLEAUT32!__imp_VariantClear` at `0x180016d0f`
- `OLEAUT32!__imp_VariantClear` at `0x180016d94`

## string_xrefs

- `0x180016cef`: `BinaryPath`
- `0x180016e58`: `BinaryPath`
- `0x180016d74`: `RegistryPath`

## pseudocode

```c
struct IUnknown *__fastcall ResourceLoader6::SimpleResourceLoader::SimpleResourceLoader(
        struct IUnknown *this,
        OLECHAR *psz,
        const unsigned __int16 *a3)
{
  BSTR v4; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  int v6; // eax
  HRESULT v7; // eax
  BSTR v8; // rax
  struct IUnknownVtbl *v9; // rax
  int v10; // eax
  HRESULT v11; // eax
  int v13; // edx
  HINSTANCE v14; // r8
  VARIANTARG v15; // [rsp+20h] [rbp-968h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-948h] BYREF
  VARIANTARG v17; // [rsp+58h] [rbp-930h] BYREF
  __int64 v18; // [rsp+70h] [rbp-918h]
  struct IUnknown *v19; // [rsp+78h] [rbp-910h]
  _BYTE v20[80]; // [rsp+80h] [rbp-908h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+D0h] [rbp-8B8h] BYREF
  _BYTE v22[64]; // [rsp+110h] [rbp-878h] BYREF
  unsigned __int16 v23[1040]; // [rsp+150h] [rbp-838h] BYREF
  const void *retaddr; // [rsp+988h] [rbp+0h]

  v18 = -2;
  v19 = this;
  this->lpVtbl = (struct IUnknownVtbl *)&ResourceLoader6::SimpleResourceLoader::`vftable';
  this[1].lpVtbl = 0;
  this[2].lpVtbl = 0;
  this[3].lpVtbl = 0;
  this[4].lpVtbl = 0;
  this[5].lpVtbl = 0;
  this[6].lpVtbl = 0;
  this[7].lpVtbl = 0;
  LODWORD(this[8].lpVtbl) = 1;
  WORD2(this[8].lpVtbl) = -1;
  this[12].lpVtbl = (struct IUnknownVtbl *)7;
  this[11].lpVtbl = 0;
  LOWORD(this[9].lpVtbl) = 0;
  LODWORD(this[13].lpVtbl) = 0;
  this[17].lpVtbl = (struct IUnknownVtbl *)7;
  this[16].lpVtbl = 0;
  LOWORD(this[14].lpVtbl) = 0;
  this[21].lpVtbl = (struct IUnknownVtbl *)7;
  this[20].lpVtbl = 0;
  LOWORD(this[18].lpVtbl) = 0;
  try
  {
    if ( psz )
    {
      v4 = SysAllocString(psz);
      if ( !v4 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v4;
      lpVtbl = this->lpVtbl;
      *(VARIANTARG *)&v20[32] = pvarg;
      v15 = pvarg;
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, VARIANTARG *))lpVtbl[2].QueryInterface)(
             this,
             L"BinaryPath",
             &v15);
      if ( v6 < 0 )
        _com_issue_errorex(v6, this, &GUID_50c9c43c_9874_4766_959b_47e96bc18012);
      v7 = VariantClear(&pvarg);
      _com_util::CheckError(v7);
    }
    else
    {
      memset_0(v23, 0, sizeof(v23));
      if ( !(unsigned int)NLG::FindProof::GetModuleFilePath(v23, v13, v14) )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      _variant_t::_variant_t((_variant_t *)&v15, v23);
      ResourceLoader6::ILoadResources::PutOption(this, L"BinaryPath", (const struct _variant_t *)&v15);
      _variant_t::~_variant_t((_variant_t *)&v15);
    }
    v8 = SysAllocString(L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language");
    if ( !v8 )
      _com_issue_error(-2147024882);
    v17.vt = 8;
    v17.llVal = (LONGLONG)v8;
    v9 = this->lpVtbl;
    *(VARIANTARG *)&v20[56] = v17;
    *(VARIANTARG *)v20 = v17;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _BYTE *))v9[2].QueryInterface)(
            this,
            L"RegistryPath",
            v20);
    if ( v10 < 0 )
      _com_issue_errorex(v10, this, &GUID_50c9c43c_9874_4766_959b_47e96bc18012);
    v11 = VariantClear(&v17);
    _com_util::CheckError(v11);
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147500037LL, retaddr);
    CNLException::CNLException((CNLException *)v22, -2147467259, retaddr);
    throw (CNLException *)v22;
  }
  if ( psz )
  {
    v4 = SysAllocString(psz);
    if ( !v4 )
      _com_issue_error(-2147024882);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)v4;
    lpVtbl = this->lpVtbl;
    *(VARIANTARG *)&v20[32] = pvarg;
    v15 = pvarg;
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, VARIANTARG *))lpVtbl[2].QueryInterface)(
           this,
           L"BinaryPath",
           &v15);
    if ( v6 < 0 )
      _com_issue_errorex(v6, this, &GUID_50c9c43c_9874_4766_959b_47e96bc18012);
    v7 = VariantClear(&pvarg);
    _com_util::CheckError(v7);
  }
  else
  {
    memset_0(v23, 0, sizeof(v23));
    if ( !(unsigned int)NLG::FindProof::GetModuleFilePath(v23, v13, v14) )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    _variant_t::_variant_t((_variant_t *)&v15, v23);
    ResourceLoader6::ILoadResources::PutOption(this, L"BinaryPath", (const struct _variant_t *)&v15);
    _variant_t::~_variant_t((_variant_t *)&v15);
  }
  v8 = SysAllocString(L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language");
}

```

## disassembly

```asm
0x180016bf4  mov     rax, rsp
0x180016bf7  push    rdi
0x180016bf8  sub     rsp, 980h
0x180016bff  mov     [rsp+988h+var_918], 0FFFFFFFFFFFFFFFEh
0x180016c08  mov     [rax+18h], rbx
0x180016c0c  mov     [rax+20h], rsi
0x180016c10  mov     rax, cs:__security_cookie
0x180016c17  xor     rax, rsp
0x180016c1a  mov     [rsp+988h+var_18], rax
0x180016c22  mov     rbx, rcx
0x180016c25  mov     [rsp+988h+var_910], rcx
0x180016c2a  lea     rax, ??_7SimpleResourceLoader@ResourceLoader6@@6B@; const ResourceLoader6::SimpleResourceLoader::`vftable'
0x180016c31  mov     [rcx], rax
0x180016c34  xor     esi, esi
0x180016c36  mov     [rcx+8], rsi
0x180016c3a  mov     [rcx+10h], rsi
0x180016c3e  mov     [rcx+18h], rsi
0x180016c42  mov     [rcx+20h], rsi
0x180016c46  mov     [rcx+28h], rsi
0x180016c4a  mov     [rcx+30h], rsi
0x180016c4e  mov     [rcx+38h], rsi
0x180016c52  mov     dword ptr [rcx+40h], 1
0x180016c59  mov     word ptr [rcx+44h], 0FFFFh
0x180016c5f  lea     ecx, [rsi+7]
0x180016c62  mov     [rbx+60h], rcx
0x180016c66  mov     [rbx+58h], rsi
0x180016c6a  mov     [rbx+48h], si
0x180016c6e  mov     [rbx+68h], esi
0x180016c71  mov     [rbx+88h], rcx
0x180016c78  mov     [rbx+80h], rsi
0x180016c7f  mov     [rbx+70h], si
0x180016c83  mov     [rbx+0A8h], rcx
0x180016c8a  mov     [rbx+0A0h], rsi
0x180016c91  mov     [rbx+90h], si
0x180016c98  test    rdx, rdx
0x180016c9b  jz      loc_180016DEE
0x180016ca1  mov     rcx, rdx; psz
0x180016ca4  call    cs:__imp_SysAllocString
0x180016caa  test    rax, rax
0x180016cad  jz      loc_180016DD1
0x180016cb3  lea     edi, [rsi+8]
0x180016cb6  mov     word ptr [rsp+988h+pvarg], di
0x180016cbb  mov     qword ptr [rsp+988h+pvarg+8], rax
0x180016cc0  mov     rax, [rbx]
0x180016cc3  movups  xmm1, xmmword ptr [rsp+988h+pvarg]
0x180016cc8  movups  [rsp+988h+var_8E8], xmm1
0x180016cd0  movsd   xmm0, qword ptr [rsp+988h+pvarg+10h]
0x180016cd6  movsd   [rsp+988h+var_8D8], xmm0
0x180016cdf  movaps  [rsp+988h+var_968], xmm1
0x180016ce4  movsd   [rsp+988h+var_958], xmm0
0x180016cea  lea     r8, [rsp+988h+var_968]
0x180016cef  lea     rdx, aBinarypath; "BinaryPath"
0x180016cf6  mov     rcx, rbx
0x180016cf9  mov     rax, [rax+30h]
0x180016cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d02  test    eax, eax
0x180016d04  js      loc_180016DDC
0x180016d0a  lea     rcx, [rsp+988h+pvarg]; pvarg
0x180016d0f  call    cs:__imp_VariantClear
0x180016d15  mov     ecx, eax; int
0x180016d17  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180016d1c  lea     rcx, psz; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180016d23  call    cs:__imp_SysAllocString
0x180016d29  test    rax, rax
0x180016d2c  jz      loc_180016E7C
0x180016d32  mov     word ptr [rsp+988h+var_930], di
0x180016d37  mov     qword ptr [rsp+988h+var_930+8], rax
0x180016d3c  mov     rax, [rbx]
0x180016d3f  movups  xmm1, xmmword ptr [rsp+988h+var_930]
0x180016d44  movups  [rsp+988h+var_8D0], xmm1
0x180016d4c  movsd   xmm0, qword ptr [rsp+988h+var_930+10h]
0x180016d52  movsd   [rsp+988h+var_8C0], xmm0
0x180016d5b  movaps  [rsp+988h+var_908], xmm1
0x180016d63  movsd   [rsp+988h+var_8F8], xmm0
0x180016d6c  lea     r8, [rsp+988h+var_908]
0x180016d74  lea     rdx, aRegistrypath; "RegistryPath"
0x180016d7b  mov     rcx, rbx
0x180016d7e  mov     rax, [rax+30h]
0x180016d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d87  test    eax, eax
0x180016d89  js      loc_180016E87
0x180016d8f  lea     rcx, [rsp+988h+var_930]; pvarg
0x180016d94  call    cs:__imp_VariantClear
0x180016d9a  mov     ecx, eax; int
0x180016d9c  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180016da1  nop
0x180016da2  lock inc cs:dword_1800FB700
0x180016da9  mov     rax, rbx
0x180016dac  mov     rcx, [rsp+988h+var_18]
0x180016db4  xor     rcx, rsp; StackCookie
0x180016db7  call    __security_check_cookie
0x180016dbc  lea     r11, [rsp+988h+var_8]
0x180016dc4  mov     rbx, [r11+20h]
0x180016dc8  mov     rsi, [r11+28h]
0x180016dcc  mov     rsp, r11
0x180016dcf  pop     rdi
0x180016dd0  retn
0x180016dd1  mov     ecx, 8007000Eh; int
0x180016dd6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180016ddc  lea     r8, _GUID_50c9c43c_9874_4766_959b_47e96bc18012; struct _GUID *
0x180016de3  mov     rdx, rbx; struct IUnknown *
0x180016de6  mov     ecx, eax; int
0x180016de8  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180016dee  mov     r8d, 820h; Size
0x180016df4  lea     rcx, [rsp+988h+var_838]; void *
0x180016dfc  call    memset_0
0x180016e01  lea     rcx, [rsp+988h+var_838]; unsigned __int16 *
0x180016e09  call    ?GetModuleFilePath@FindProof@NLG@@SAHPEAGHPEAUHINSTANCE__@@@Z; NLG::FindProof::GetModuleFilePath(ushort *,int,HINSTANCE__ *)
0x180016e0e  test    eax, eax
0x180016e10  jnz     short loc_180016E40
0x180016e12  mov     r8, [rsp+988h]; void *
0x180016e1a  mov     edx, 80004005h; int
0x180016e1f  lea     rcx, [rsp+988h+pExceptionObject]; this
0x180016e27  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180016e2c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180016e33  lea     rcx, [rsp+988h+pExceptionObject]; pExceptionObject
0x180016e3b  call    _CxxThrowException_0
0x180016e40  lea     rdx, [rsp+988h+var_838]; unsigned __int16 *
0x180016e48  lea     rcx, [rsp+988h+var_968]; this
0x180016e4d  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180016e52  nop
0x180016e53  lea     r8, [rsp+988h+var_968]; struct _variant_t *
0x180016e58  lea     rdx, aBinarypath; "BinaryPath"
0x180016e5f  mov     rcx, rbx; this
0x180016e62  call    ?PutOption@ILoadResources@ResourceLoader6@@QEAAXPEAGAEBV_variant_t@@@Z; ResourceLoader6::ILoadResources::PutOption(ushort *,_variant_t const &)
0x180016e67  nop
0x180016e68  lea     rcx, [rsp+988h+var_968]; this
0x180016e6d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180016e72  mov     edi, 8
0x180016e77  jmp     loc_180016D1C
0x180016e7c  mov     ecx, 8007000Eh; int
0x180016e81  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180016e87  lea     r8, _GUID_50c9c43c_9874_4766_959b_47e96bc18012; struct _GUID *
0x180016e8e  mov     rdx, rbx; struct IUnknown *
0x180016e91  mov     ecx, eax; int
0x180016e93  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
