# _AfxOleMakeSymbolTable(CAfxOleSymbolTable &,_GUID const &,ushort const *,ushort const *,ushort const *,int,ushort const *,ushort const *)

- ea: `0x18009c080`
- end: `0x18009c2f6`
- name: `?_AfxOleMakeSymbolTable@@YAHAEAVCAfxOleSymbolTable@@AEBU_GUID@@PEBG22H22@Z`
- size: `630`
- prototype: `__int64 __fastcall(struct CAfxOleSymbolTable *this, IID *rclsid, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, UINT nIconIndex, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009bc20`
- `0x18009bf00`

## callees

- `0x18000a760`
- `0x18000b3a0`
- `0x18000b9e0`
- `0x18000cfe0`
- `0x18000d5a0`
- `0x18000d960`
- `0x180013330`
- `0x180019290`
- `0x180020ac0`
- `0x180038490`
- `0x18009c01c`
- `0x18009c080`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c0e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c0e4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009c0aa`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009c0aa`
- `USER32!DestroyIcon` at `0x18009c17b`
- `USER32!DestroyIcon` at `0x18009c17b`
- `SHELL32!ExtractIconW` at `0x18009c16d`
- `SHELL32!ExtractIconW` at `0x18009c16d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _AfxOleMakeSymbolTable(
        struct CAfxOleSymbolTable *this,
        IID *rclsid,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        UINT nIconIndex,
        unsigned __int16 *a7,
        const unsigned __int16 *a8)
{
  LPOLESTR v11; // rdi
  struct AFX_MODULE_STATE *ModuleState; // rax
  struct AFX_MODULE_STATE *v14; // rax
  UINT v15; // edi
  struct AFX_MODULE_STATE *v16; // rax
  HICON IconW; // rax
  int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned __int16 *v24; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR pszExeFileName; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int16 *v26; // [rsp+30h] [rbp-28h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v28[24]; // [rsp+40h] [rbp-18h] BYREF

  lpsz = 0;
  StringFromCLSID(rclsid, &lpsz);
  v11 = lpsz;
  if ( !lpsz )
    return 0;
  CAfxOleSymbolTable::SetAt(this, 0, lpsz);
  CAfxOleSymbolTable::SetAt(this, 1, a3);
  CoTaskMemFree(v11);
  pszExeFileName = _afxPchNil;
  ModuleState = AfxGetModuleState();
  AfxGetModuleShortFileName(*((HINSTANCE *)ModuleState + 2), (struct CString *)&pszExeFileName);
  CAfxOleSymbolTable::SetAt(this, 2, pszExeFileName);
  CAfxOleSymbolTable::SetAt(this, 3, a4);
  CAfxOleSymbolTable::SetAt(this, 4, a5);
  v14 = AfxGetModuleState();
  CAfxOleSymbolTable::SetAt(this, 5, *((const unsigned __int16 **)v14 + 4));
  v26 = (unsigned __int16 *)_afxPchNil;
  v15 = nIconIndex;
  if ( nIconIndex )
  {
    v16 = AfxGetModuleState();
    IconW = ExtractIconW(*((HINSTANCE *)v16 + 2), pszExeFileName, nIconIndex);
    if ( IconW )
      DestroyIcon(IconW);
    else
      v15 = 0;
  }
  CString::Format((CString *)&v26, (wchar_t *)L"%d", v15);
  CAfxOleSymbolTable::SetAt(this, 6, v26);
  CAfxOleSymbolTable::SetAt(this, 7, a7);
  v24 = (unsigned __int16 *)_afxPchNil;
  if ( a8 && *a8 )
  {
    CString::operator=(&v24, a8);
  }
  else
  {
    CString::operator=(&v24, a7);
    v18 = CString::Find((CString *)&v24, 0x28u, 0);
    if ( v18 == -1 )
      goto LABEL_14;
    v19 = CString::Mid(&v24, v28, (unsigned int)(v18 + 1));
    CString::operator=(&v24, v19);
    CString::~CString((CString *)v28);
    v20 = CString::Find((CString *)&v24, 0x2Eu, 0);
    if ( v20 == -1
      || (v21 = CString::Mid(&v24, v28, v20),
          CString::operator=(&v24, v21),
          CString::~CString((CString *)v28),
          v22 = CString::Find((CString *)&v24, 0x29u, 0),
          v22 == -1) )
    {
LABEL_14:
      CString::Empty((CString *)&v24);
    }
    else
    {
      v23 = CString::Left(&v24, v28, v22);
      CString::operator=(&v24, v23);
      CString::~CString((CString *)v28);
    }
  }
  CAfxOleSymbolTable::SetAt(this, 8, v24);
  CString::~CString((CString *)&v24);
  CString::~CString((CString *)&v26);
  CString::~CString((CString *)&pszExeFileName);
  return 1;
}

```

## disassembly

```asm
0x18009c080  push    rbp
0x18009c082  push    rbx
0x18009c083  push    rsi
0x18009c084  push    rdi
0x18009c085  push    r14
0x18009c087  push    r15
0x18009c089  mov     rbp, rsp
0x18009c08c  sub     rsp, 58h
0x18009c090  mov     rsi, r9
0x18009c093  mov     r14, r8
0x18009c096  mov     rax, rdx
0x18009c099  mov     rbx, rcx
0x18009c09c  xor     r15d, r15d
0x18009c09f  mov     [rbp+lpsz], r15
0x18009c0a3  lea     rdx, [rbp+lpsz]; lplpsz
0x18009c0a7  mov     rcx, rax; rclsid
0x18009c0aa  call    cs:__imp_StringFromCLSID
0x18009c0b0  mov     rdi, [rbp+lpsz]
0x18009c0b4  test    rdi, rdi
0x18009c0b7  jnz     short loc_18009C0C0
0x18009c0b9  xor     eax, eax
0x18009c0bb  jmp     loc_18009C2E9
0x18009c0c0  mov     r8, rdi; unsigned __int16 *
0x18009c0c3  xor     edx, edx; int
0x18009c0c5  mov     rcx, rbx; this
0x18009c0c8  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c0cd  mov     r8, r14; unsigned __int16 *
0x18009c0d0  mov     r14d, 1
0x18009c0d6  mov     edx, r14d; int
0x18009c0d9  mov     rcx, rbx; this
0x18009c0dc  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c0e1  mov     rcx, rdi; pv
0x18009c0e4  call    cs:__imp_CoTaskMemFree
0x18009c0ea  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18009c0f1  mov     [rbp+pszExeFileName], rax
0x18009c0f5  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18009c0fa  lea     rdx, [rbp+pszExeFileName]; struct CString *
0x18009c0fe  mov     rcx, [rax+10h]; HINSTANCE
0x18009c102  call    ?AfxGetModuleShortFileName@@YAXPEAUHINSTANCE__@@AEAVCString@@@Z; AfxGetModuleShortFileName(HINSTANCE__ *,CString &)
0x18009c107  mov     r8, [rbp+pszExeFileName]; unsigned __int16 *
0x18009c10b  lea     edx, [r14+1]; int
0x18009c10f  mov     rcx, rbx; this
0x18009c112  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c117  mov     r8, rsi; unsigned __int16 *
0x18009c11a  lea     edx, [r14+2]; int
0x18009c11e  mov     rcx, rbx; this
0x18009c121  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c126  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x18009c12a  lea     edx, [r14+3]; int
0x18009c12e  mov     rcx, rbx; this
0x18009c131  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c136  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18009c13b  mov     r8, [rax+20h]; unsigned __int16 *
0x18009c13f  lea     edx, [r14+4]; int
0x18009c143  mov     rcx, rbx; this
0x18009c146  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c14b  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18009c152  mov     [rbp+var_28], rax
0x18009c156  mov     edi, [rbp+nIconIndex]
0x18009c159  test    edi, edi
0x18009c15b  jz      short loc_18009C186
0x18009c15d  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18009c162  mov     r8d, edi; nIconIndex
0x18009c165  mov     rdx, [rbp+pszExeFileName]; pszExeFileName
0x18009c169  mov     rcx, [rax+10h]; hInst
0x18009c16d  call    cs:__imp_ExtractIconW
0x18009c173  test    rax, rax
0x18009c176  jz      short loc_18009C183
0x18009c178  mov     rcx, rax; hIcon
0x18009c17b  call    cs:__imp_DestroyIcon
0x18009c181  jmp     short loc_18009C186
0x18009c183  mov     edi, r15d
0x18009c186  mov     r8d, edi
0x18009c189  lea     rdx, aD; "%d"
0x18009c190  lea     rcx, [rbp+var_28]; this
0x18009c194  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x18009c199  mov     r8, [rbp+var_28]; unsigned __int16 *
0x18009c19d  mov     edx, 6; int
0x18009c1a2  mov     rcx, rbx; this
0x18009c1a5  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c1aa  mov     r8, [rbp+arg_30]; unsigned __int16 *
0x18009c1ae  mov     edx, 7; int
0x18009c1b3  mov     rcx, rbx; this
0x18009c1b6  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c1bb  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18009c1c2  mov     [rbp+var_38], rax
0x18009c1c6  mov     rdx, [rbp+arg_38]
0x18009c1ca  test    rdx, rdx
0x18009c1cd  jz      short loc_18009C1E3
0x18009c1cf  cmp     [rdx], r15w
0x18009c1d3  jz      short loc_18009C1E3
0x18009c1d5  lea     rcx, [rbp+var_38]
0x18009c1d9  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18009c1de  jmp     loc_18009C2B7
0x18009c1e3  mov     rdx, [rbp+arg_30]
0x18009c1e7  lea     rcx, [rbp+var_38]
0x18009c1eb  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18009c1f0  mov     edx, 28h ; '('; unsigned __int16
0x18009c1f5  xor     r8d, r8d; int
0x18009c1f8  lea     rcx, [rbp+var_38]; this
0x18009c1fc  call    ?Find@CString@@QEBAHGH@Z; CString::Find(ushort,int)
0x18009c201  cmp     eax, 0FFFFFFFFh
0x18009c204  jz      loc_18009C2AE
0x18009c20a  lea     r8d, [rax+1]
0x18009c20e  lea     rdx, [rbp+var_18]
0x18009c212  lea     rcx, [rbp+var_38]
0x18009c216  call    ?Mid@CString@@QEBA?AV1@H@Z; CString::Mid(int)
0x18009c21b  nop
0x18009c21c  mov     rdx, rax
0x18009c21f  lea     rcx, [rbp+var_38]
0x18009c223  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18009c228  nop
0x18009c229  lea     rcx, [rbp+var_18]; this
0x18009c22d  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c232  mov     edx, 2Eh ; '.'; unsigned __int16
0x18009c237  xor     r8d, r8d; int
0x18009c23a  lea     rcx, [rbp+var_38]; this
0x18009c23e  call    ?Find@CString@@QEBAHGH@Z; CString::Find(ushort,int)
0x18009c243  cmp     eax, 0FFFFFFFFh
0x18009c246  jz      short loc_18009C2AE
0x18009c248  mov     r8d, eax
0x18009c24b  lea     rdx, [rbp+var_18]
0x18009c24f  lea     rcx, [rbp+var_38]
0x18009c253  call    ?Mid@CString@@QEBA?AV1@H@Z; CString::Mid(int)
0x18009c258  nop
0x18009c259  mov     rdx, rax
0x18009c25c  lea     rcx, [rbp+var_38]
0x18009c260  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18009c265  nop
0x18009c266  lea     rcx, [rbp+var_18]; this
0x18009c26a  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c26f  mov     edx, 29h ; ')'; unsigned __int16
0x18009c274  xor     r8d, r8d; int
0x18009c277  lea     rcx, [rbp+var_38]; this
0x18009c27b  call    ?Find@CString@@QEBAHGH@Z; CString::Find(ushort,int)
0x18009c280  cmp     eax, 0FFFFFFFFh
0x18009c283  jz      short loc_18009C2AE
0x18009c285  mov     r8d, eax
0x18009c288  lea     rdx, [rbp+var_18]
0x18009c28c  lea     rcx, [rbp+var_38]
0x18009c290  call    ?Left@CString@@QEBA?AV1@H@Z; CString::Left(int)
0x18009c295  nop
0x18009c296  mov     rdx, rax
0x18009c299  lea     rcx, [rbp+var_38]
0x18009c29d  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18009c2a2  nop
0x18009c2a3  lea     rcx, [rbp+var_18]; this
0x18009c2a7  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c2ac  jmp     short loc_18009C2B7
0x18009c2ae  lea     rcx, [rbp+var_38]; this
0x18009c2b2  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x18009c2b7  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18009c2bb  mov     edx, 8; int
0x18009c2c0  mov     rcx, rbx; this
0x18009c2c3  call    ?SetAt@CAfxOleSymbolTable@@QEAAXHPEBG@Z; CAfxOleSymbolTable::SetAt(int,ushort const *)
0x18009c2c8  nop
0x18009c2c9  lea     rcx, [rbp+var_38]; this
0x18009c2cd  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c2d2  nop
0x18009c2d3  lea     rcx, [rbp+var_28]; this
0x18009c2d7  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c2dc  nop
0x18009c2dd  lea     rcx, [rbp+pszExeFileName]; this
0x18009c2e1  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009c2e6  mov     eax, r14d
0x18009c2e9  add     rsp, 58h
0x18009c2ed  pop     r15
0x18009c2ef  pop     r14
0x18009c2f1  pop     rdi
0x18009c2f2  pop     rsi
0x18009c2f3  pop     rbx
0x18009c2f4  pop     rbp
0x18009c2f5  retn
```
