# VBProject::AddReference(tagVARIANT,tagVARIANT,tagVARIANT,tagVARIANT)

- ea: `0x180097e60`
- end: `0x1800980f5`
- name: `?AddReference@VBProject@@UEAAJUtagVARIANT@@000@Z`
- size: `661`
- prototype: `__int64 __fastcall(VBProject *__hidden this, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001b8b0`
- `0x18001bf20`
- `0x18001c154`
- `0x1800411a0`
- `0x180042964`
- `0x18005acac`
- `0x180096978`
- `0x1800969b8`
- `0x180096a0c`
- `0x180096ab0`
- `0x180096b60`
- `0x180096b70`
- `0x180097e60`
- `0x18009c1fc`
- `0x18009c30c`
- `0x1800e34e8`
- `0x18017a58c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180097f74`
- `ole32!CLSIDFromString` at `0x180097f74`
- `OLEAUT32!__imp_SysFreeString` at `0x180097ffb`
- `OLEAUT32!__imp_SysFreeString` at `0x18009800a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800980b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180097ffb`
- `OLEAUT32!__imp_SysFreeString` at `0x18009800a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800980b6`
- `OLEAUT32!__imp_VariantInit` at `0x180097f1a`
- `OLEAUT32!__imp_VariantInit` at `0x180097f1a`
- `OLEAUT32!__imp_VariantClear` at `0x180097ff2`
- `OLEAUT32!__imp_VariantClear` at `0x180097ff2`
- `OLEAUT32!__imp_VariantChangeType` at `0x180097f30`
- `OLEAUT32!__imp_VariantChangeType` at `0x180097f52`
- `OLEAUT32!__imp_VariantChangeType` at `0x180097f30`
- `OLEAUT32!__imp_VariantChangeType` at `0x180097f52`
- `OLEAUT32!__imp_QueryPathOfRegTypeLib` at `0x180097f99`
- `OLEAUT32!__imp_QueryPathOfRegTypeLib` at `0x180097f99`

## pseudocode

```c
__int64 __fastcall VBProject::AddReference(
        Project **this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5)
{
  VBDispatch *v5; // rsi
  OLECHAR *v10; // rdi
  unsigned int v11; // ebx
  HRESULT v12; // eax
  SHORT iVal; // r15
  int v14; // edx
  HRESULT v15; // eax
  unsigned __int64 HProj; // rax
  unsigned int v17; // eax
  const char *NonPrintFullPath; // rax
  unsigned __int64 v19; // rax
  unsigned int v20; // eax
  BSTR bstrPathName; // [rsp+30h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v24[24]; // [rsp+50h] [rbp-21h] BYREF
  CLSID pclsid; // [rsp+68h] [rbp-9h] BYREF

  v5 = (VBDispatch *)(this + 1);
  VBDispatch::EnterOleFunc((VBDispatch *)(this + 1));
  bstrPathName = 0;
  CFileRep::CFileRep((CFileRep *)v24);
  v10 = _BstrFromVariant(a2);
  if ( (int)_PathFromVariant(a5, (struct CFileRep *)v24) < 0 )
  {
    if ( !v10 )
    {
      VBDispatch::m_uArgErr = 3;
      v11 = VBDispatch::RaiseOleException(v5, -2147352571, (wchar_t *)&strIn, 0);
      goto LABEL_28;
    }
LABEL_5:
    VBDispatch::ClearException();
    VariantInit(&pvarg);
    v12 = VariantChangeType(&pvarg, a4, 0, 2u);
    iVal = 0;
    if ( !v12 )
      iVal = pvarg.iVal;
    if ( VariantChangeType(&pvarg, a3, 0, 2u) )
    {
      VBDispatch::m_uArgErr = 2;
      v14 = -2147352571;
    }
    else
    {
      v15 = CLSIDFromString(v10, &pclsid);
      if ( v15 >= 0 )
      {
        v15 = QueryPathOfRegTypeLib(&pclsid, pvarg.uiVal, iVal, 9u, &bstrPathName);
        if ( v15 >= 0 )
        {
          HProj = Project::GetHProj(this[10]);
          v17 = TipAddRefLib(HProj, bstrPathName, 0, 0);
          if ( v17 )
            VBDispatch::RaiseException(v5, v17);
          else
            Project::fSetDirtyFlag(this[10], 1);
LABEL_16:
          VariantClear(&pvarg);
          SysFreeString(v10);
          if ( bstrPathName )
            SysFreeString(bstrPathName);
          if ( !(unsigned int)DispatchExceptionArisen() )
          {
            VBDispatch::ExitOleFunc(v5);
            v11 = 0;
            goto LABEL_28;
          }
          goto LABEL_20;
        }
      }
      v14 = v15;
    }
    VBDispatch::RaiseOleException(v5, v14, (wchar_t *)&strIn, 0);
    goto LABEL_16;
  }
  if ( v10 )
    goto LABEL_5;
LABEL_20:
  if ( (unsigned int)CFileRep::fInitialized((CFileRep *)v24) )
  {
    VBDispatch::EnterOleFunc(v5);
    NonPrintFullPath = CFileRep::GetNonPrintFullPath((CFileRep *)v24);
    bstrPathName = AllocBstrWfromA(NonPrintFullPath);
    if ( bstrPathName )
    {
      v19 = Project::GetHProj(this[10]);
      v20 = TipAddRefLib(v19, bstrPathName, 0, 0);
      if ( v20 )
      {
        VBDispatch::RaiseException(v5, v20);
      }
      else
      {
        Project::fSetDirtyFlag(this[10], 1);
        VBDispatch::ExitOleFunc(v5);
      }
    }
    else
    {
      VBDispatch::RaiseOleException(v5, -2147024882, (wchar_t *)&strIn, 0);
    }
    SysFreeString(bstrPathName);
  }
  VBDispatch::ExitOleFunc(v5);
  v11 = VBDispatch::m_sc;
LABEL_28:
  CFileRep::~CFileRep((CFileRep *)v24);
  return v11;
}

```

## disassembly

```asm
0x180097e60  push    rbp
0x180097e62  push    rbx
0x180097e63  push    rsi
0x180097e64  push    rdi
0x180097e65  push    r12
0x180097e67  push    r13
0x180097e69  push    r14
0x180097e6b  push    r15
0x180097e6d  lea     rbp, [rsp-17h]
0x180097e72  mov     eax, 88h
0x180097e77  call    _alloca_probe
0x180097e7c  sub     rsp, rax
0x180097e7f  mov     rax, cs:__security_cookie
0x180097e86  xor     rax, rsp
0x180097e89  mov     [rbp+4Fh+var_48], rax
0x180097e8d  mov     rbx, [rbp+4Fh+arg_20]
0x180097e91  lea     rsi, [rcx+8]
0x180097e95  mov     r14, rcx
0x180097e98  mov     rcx, rsi; this
0x180097e9b  mov     r15, r9
0x180097e9e  mov     r12, r8
0x180097ea1  mov     rdi, rdx
0x180097ea4  call    ?EnterOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::EnterOleFunc(void)
0x180097ea9  lea     rcx, [rbp+4Fh+var_70]; this
0x180097ead  xor     r13d, r13d
0x180097eb0  mov     [rbp+4Fh+bstrPathName], r13
0x180097eb4  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x180097eb9  mov     rcx, rdi; struct tagVARIANT *
0x180097ebc  call    ?_BstrFromVariant@@YAPEA_WPEAUtagVARIANT@@@Z; _BstrFromVariant(tagVARIANT *)
0x180097ec1  lea     rdx, [rbp+4Fh+var_70]; struct CFileRep *
0x180097ec5  mov     rcx, rbx; struct tagVARIANT *
0x180097ec8  mov     rdi, rax
0x180097ecb  call    ?_PathFromVariant@@YAJAEAUtagVARIANT@@AEAVCFileRep@@@Z; _PathFromVariant(tagVARIANT &,CFileRep &)
0x180097ed0  lea     rbx, strIn
0x180097ed7  test    eax, eax
0x180097ed9  jns     short loc_180097F08
0x180097edb  test    rdi, rdi
0x180097ede  jnz     short loc_180097F11
0x180097ee0  lea     r8, strIn; wchar_t *
0x180097ee7  xor     r9d, r9d; unsigned int
0x180097eea  mov     edx, 80020005h; int
0x180097eef  mov     rcx, rsi; this
0x180097ef2  mov     cs:?m_uArgErr@VBDispatch@@1IA, 3; uint VBDispatch::m_uArgErr
0x180097efc  call    ?RaiseOleException@VBDispatch@@IEAAJJPEA_WK@Z; VBDispatch::RaiseOleException(long,wchar_t *,ulong)
0x180097f01  mov     ebx, eax
0x180097f03  jmp     loc_1800980CA
0x180097f08  test    rdi, rdi
0x180097f0b  jz      loc_180098029
0x180097f11  call    ?ClearException@VBDispatch@@SAXXZ; VBDispatch::ClearException(void)
0x180097f16  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180097f1a  call    cs:__imp_VariantInit
0x180097f20  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x180097f24  mov     r9d, 2; vt
0x180097f2a  xor     r8d, r8d; wFlags
0x180097f2d  mov     rdx, r15; pvarSrc
0x180097f30  call    cs:__imp_VariantChangeType
0x180097f36  movzx   r15d, r13w
0x180097f3a  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x180097f3e  test    eax, eax
0x180097f40  mov     r9d, 2; vt
0x180097f46  mov     rdx, r12; pvarSrc
0x180097f49  cmovz   r15w, word ptr [rbp+4Fh+pvarg+8]
0x180097f4f  xor     r8d, r8d; wFlags
0x180097f52  call    cs:__imp_VariantChangeType
0x180097f58  test    eax, eax
0x180097f5a  jz      short loc_180097F6D
0x180097f5c  mov     cs:?m_uArgErr@VBDispatch@@1IA, 2; uint VBDispatch::m_uArgErr
0x180097f66  mov     edx, 80020005h
0x180097f6b  jmp     short loc_180097FA5
0x180097f6d  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x180097f71  mov     rcx, rdi; lpsz
0x180097f74  call    cs:__imp_CLSIDFromString
0x180097f7a  test    eax, eax
0x180097f7c  js      short loc_180097FA3
0x180097f7e  movzx   edx, word ptr [rbp+4Fh+pvarg+8]; wMaj
0x180097f82  lea     rax, [rbp+4Fh+bstrPathName]
0x180097f86  lea     rcx, [rbp+4Fh+pclsid]; guid
0x180097f8a  mov     r9d, 9; lcid
0x180097f90  movzx   r8d, r15w; wMin
0x180097f94  mov     [rsp+0C0h+lpbstrPathName], rax; lpbstrPathName
0x180097f99  call    cs:__imp_QueryPathOfRegTypeLib
0x180097f9f  test    eax, eax
0x180097fa1  jns     short loc_180097FB5
0x180097fa3  mov     edx, eax; int
0x180097fa5  mov     r8, rbx; wchar_t *
0x180097fa8  xor     r9d, r9d; unsigned int
0x180097fab  mov     rcx, rsi; this
0x180097fae  call    ?RaiseOleException@VBDispatch@@IEAAJJPEA_WK@Z; VBDispatch::RaiseOleException(long,wchar_t *,ulong)
0x180097fb3  jmp     short loc_180097FEE
0x180097fb5  mov     rcx, [r14+50h]; this
0x180097fb9  call    ?GetHProj@Project@@QEAA_KXZ; Project::GetHProj(void)
0x180097fbe  mov     rdx, [rbp+4Fh+bstrPathName]
0x180097fc2  xor     r9d, r9d
0x180097fc5  mov     rcx, rax
0x180097fc8  xor     r8d, r8d
0x180097fcb  call    TipAddRefLib
0x180097fd0  test    eax, eax
0x180097fd2  jz      short loc_180097FE0
0x180097fd4  mov     edx, eax; unsigned int
0x180097fd6  mov     rcx, rsi; this
0x180097fd9  call    ?RaiseException@VBDispatch@@IEAAJI@Z; VBDispatch::RaiseException(uint)
0x180097fde  jmp     short loc_180097FEE
0x180097fe0  mov     rcx, [r14+50h]; this
0x180097fe4  mov     edx, 1; int
0x180097fe9  call    ?fSetDirtyFlag@Project@@QEAAHH@Z; Project::fSetDirtyFlag(int)
0x180097fee  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180097ff2  call    cs:__imp_VariantClear
0x180097ff8  mov     rcx, rdi; bstrString
0x180097ffb  call    cs:__imp_SysFreeString
0x180098001  mov     rcx, [rbp+4Fh+bstrPathName]; bstrString
0x180098005  test    rcx, rcx
0x180098008  jz      short loc_180098010
0x18009800a  call    cs:__imp_SysFreeString
0x180098010  call    ?DispatchExceptionArisen@@YAHXZ; DispatchExceptionArisen(void)
0x180098015  test    eax, eax
0x180098017  jnz     short loc_180098029
0x180098019  mov     rcx, rsi; this
0x18009801c  call    ?ExitOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::ExitOleFunc(void)
0x180098021  mov     ebx, r13d
0x180098024  jmp     loc_1800980CA
0x180098029  lea     rcx, [rbp+4Fh+var_70]; this
0x18009802d  call    ?fInitialized@CFileRep@@QEAAHXZ; CFileRep::fInitialized(void)
0x180098032  test    eax, eax
0x180098034  jz      loc_1800980BC
0x18009803a  mov     rcx, rsi; this
0x18009803d  call    ?EnterOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::EnterOleFunc(void)
0x180098042  lea     rcx, [rbp+4Fh+var_70]; this
0x180098046  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18009804b  mov     rcx, rax; char *
0x18009804e  call    ?AllocBstrWfromA@@YAPEA_WPEBD@Z; AllocBstrWfromA(char const *)
0x180098053  mov     [rbp+4Fh+bstrPathName], rax
0x180098057  test    rax, rax
0x18009805a  jnz     short loc_180098071
0x18009805c  xor     r9d, r9d; unsigned int
0x18009805f  mov     r8, rbx; wchar_t *
0x180098062  mov     edx, 8007000Eh; int
0x180098067  mov     rcx, rsi; this
0x18009806a  call    ?RaiseOleException@VBDispatch@@IEAAJJPEA_WK@Z; VBDispatch::RaiseOleException(long,wchar_t *,ulong)
0x18009806f  jmp     short loc_1800980B2
0x180098071  mov     rcx, [r14+50h]; this
0x180098075  call    ?GetHProj@Project@@QEAA_KXZ; Project::GetHProj(void)
0x18009807a  mov     rdx, [rbp+4Fh+bstrPathName]
0x18009807e  xor     r9d, r9d
0x180098081  mov     rcx, rax
0x180098084  xor     r8d, r8d
0x180098087  call    TipAddRefLib
0x18009808c  test    eax, eax
0x18009808e  jz      short loc_18009809C
0x180098090  mov     edx, eax; unsigned int
0x180098092  mov     rcx, rsi; this
0x180098095  call    ?RaiseException@VBDispatch@@IEAAJI@Z; VBDispatch::RaiseException(uint)
0x18009809a  jmp     short loc_1800980B2
0x18009809c  mov     rcx, [r14+50h]; this
0x1800980a0  mov     edx, 1; int
0x1800980a5  call    ?fSetDirtyFlag@Project@@QEAAHH@Z; Project::fSetDirtyFlag(int)
0x1800980aa  mov     rcx, rsi; this
0x1800980ad  call    ?ExitOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::ExitOleFunc(void)
0x1800980b2  mov     rcx, [rbp+4Fh+bstrPathName]; bstrString
0x1800980b6  call    cs:__imp_SysFreeString
0x1800980bc  mov     rcx, rsi; this
0x1800980bf  call    ?ExitOleFunc@VBDispatch@@QEAAXXZ; VBDispatch::ExitOleFunc(void)
0x1800980c4  mov     ebx, cs:?m_sc@VBDispatch@@1JA; long VBDispatch::m_sc
0x1800980ca  lea     rcx, [rbp+4Fh+var_70]; this
0x1800980ce  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x1800980d3  mov     eax, ebx
0x1800980d5  mov     rcx, [rbp+4Fh+var_48]
0x1800980d9  xor     rcx, rsp; StackCookie
0x1800980dc  call    __security_check_cookie
0x1800980e1  add     rsp, 88h
0x1800980e8  pop     r15
0x1800980ea  pop     r14
0x1800980ec  pop     r13
0x1800980ee  pop     r12
0x1800980f0  pop     rdi
0x1800980f1  pop     rsi
0x1800980f2  pop     rbx
0x1800980f3  pop     rbp
0x1800980f4  retn
```
