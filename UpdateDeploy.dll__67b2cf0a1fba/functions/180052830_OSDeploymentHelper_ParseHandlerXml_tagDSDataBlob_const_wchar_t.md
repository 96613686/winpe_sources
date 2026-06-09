# OSDeploymentHelper::ParseHandlerXml(tagDSDataBlob const &,wchar_t * *)

- ea: `0x180052830`
- end: `0x180052abc`
- name: `?ParseHandlerXml@OSDeploymentHelper@@YAJAEBUtagDSDataBlob@@PEAPEA_W@Z`
- size: `652`
- prototype: `__int64 __fastcall(OSDeploymentHelper *__hidden this, const struct tagDSDataBlob *, wchar_t **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e3e8`
- `0x18003fd7c`

## callees

- `0x180003180`
- `0x180008ca4`
- `0x18004e164`
- `0x180052830`
- `0x180060a30`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052a98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052a98`
- `OLEAUT32!__imp_SysFreeString` at `0x180052886`
- `OLEAUT32!__imp_SysFreeString` at `0x180052898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800528ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800528fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180052969`
- `OLEAUT32!__imp_SysFreeString` at `0x1800529ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180052a24`
- `OLEAUT32!__imp_SysFreeString` at `0x180052886`
- `OLEAUT32!__imp_SysFreeString` at `0x180052898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800528ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800528fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180052969`
- `OLEAUT32!__imp_SysFreeString` at `0x1800529ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180052a24`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800528ba`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800528ba`

## pseudocode

```c
__int64 __fastcall OSDeploymentHelper::ParseHandlerXml(
        OSDeploymentHelper *this,
        const struct tagDSDataBlob *a2,
        wchar_t **a3)
{
  wchar_t *v4; // rbx
  UINT v5; // edx
  const CHAR *v6; // rcx
  BSTR v7; // rdi
  int ElementSet; // edi
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  BOOL v12; // edi
  BSTR v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  LPVOID pv; // [rsp+28h] [rbp-48h] BYREF
  struct IXMLDOMNode *v17; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+38h] [rbp-38h] BYREF
  __int128 v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  pv = 0;
  *(_QWORD *)a2 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v4 = 0;
  v14 = 0;
  v5 = *(_DWORD *)this;
  if ( !*(_DWORD *)this || (v6 = (const CHAR *)*((_QWORD *)this + 1)) == 0 )
  {
    SysFreeString(0);
LABEL_22:
    ElementSet = -2145116151;
    v11 = 383;
    goto LABEL_25;
  }
  v7 = SysAllocStringByteLen(v6, v5);
  if ( v7 )
  {
    SysFreeString(0);
    v4 = v7;
    v14 = v7;
  }
  if ( !v4 )
  {
    ElementSet = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)0x8007000ELL,
      (int)v14);
    SysFreeString(0);
LABEL_18:
    v11 = 381;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)(unsigned int)ElementSet,
      (int)v14);
    goto LABEL_27;
  }
  v9 = DspCreateDOMAndLoadXml(v4, &v17);
  ElementSet = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)v9,
      (int)v14);
    SysFreeString(v4);
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
    goto LABEL_18;
  }
  if ( !v17 )
  {
    ElementSet = -2147467261;
    v10 = 1326;
    goto LABEL_16;
  }
  ElementSet = GetElementSet(v17, &pv, &qword_1800A1840, &v18, v14);
  if ( ElementSet < 0 )
  {
    v10 = 1340;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)ElementSet,
      (int)v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x570,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)ElementSet,
      v15);
    SysFreeString(v4);
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
    goto LABEL_18;
  }
  v12 = HIDWORD(v19) != 0;
  SysFreeString(v4);
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
  if ( !v12 )
    goto LABEL_22;
  v17 = 0;
  ElementSet = SusStrCchDup<wchar_t *,wchar_t *>(pv);
  if ( ElementSet < 0 )
  {
    v11 = 386;
    goto LABEL_25;
  }
  *(_QWORD *)a2 = v17;
  ElementSet = 0;
LABEL_27:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)ElementSet;
}

```

## disassembly

```asm
0x180052830  mov     [rsp-18h+arg_10], rbx
0x180052835  push    rbp
0x180052836  push    rsi
0x180052837  push    rdi
0x180052838  mov     rbp, rsp
0x18005283b  sub     rsp, 70h
0x18005283f  mov     rax, cs:__security_cookie
0x180052846  xor     rax, rsp
0x180052849  mov     [rbp+var_10], rax
0x18005284d  mov     rsi, rdx
0x180052850  mov     [rbp+pv], 0
0x180052858  mov     qword ptr [rdx], 0
0x18005285f  mov     [rbp+var_40], 0
0x180052867  xorps   xmm0, xmm0
0x18005286a  xor     eax, eax
0x18005286c  movups  [rbp+var_38], xmm0
0x180052870  movups  [rbp+var_28], xmm0
0x180052874  mov     [rbp+var_18], rax
0x180052878  xor     ebx, ebx
0x18005287a  mov     [rbp+var_50], rbx
0x18005287e  mov     edx, [rcx]; len
0x180052880  test    edx, edx
0x180052882  jnz     short loc_18005288F
0x180052884  xor     ecx, ecx; bstrString
0x180052886  call    cs:__imp_SysFreeString
0x18005288c  nop
0x18005288d  jmp     short loc_18005289F
0x18005288f  mov     rcx, [rcx+8]; psz
0x180052893  test    rcx, rcx
0x180052896  jnz     short loc_1800528BA
0x180052898  call    cs:__imp_SysFreeString
0x18005289e  nop
0x18005289f  mov     rcx, [rbp+var_40]
0x1800528a3  test    rcx, rcx
0x1800528a6  jz      short loc_1800528B5
0x1800528a8  mov     rax, [rcx]
0x1800528ab  mov     rax, [rax+10h]
0x1800528af  call    _guard_dispatch_icall
0x1800528b4  nop
0x1800528b5  jmp     loc_180052A45
0x1800528ba  call    cs:__imp_SysAllocStringByteLen
0x1800528c0  mov     rdi, rax
0x1800528c3  test    rax, rax
0x1800528c6  jz      short loc_1800528D7
0x1800528c8  xor     ecx, ecx; bstrString
0x1800528ca  call    cs:__imp_SysFreeString
0x1800528d0  mov     rbx, rdi
0x1800528d3  mov     [rbp+var_50], rbx
0x1800528d7  test    rbx, rbx
0x1800528da  jnz     short loc_18005291E
0x1800528dc  mov     rcx, [rbp+18h]; this
0x1800528e0  mov     edi, 8007000Eh
0x1800528e5  mov     r9d, edi; char *
0x1800528e8  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800528ef  mov     edx, 56Dh; void *
0x1800528f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800528f9  nop
0x1800528fa  xor     ecx, ecx; bstrString
0x1800528fc  call    cs:__imp_SysFreeString
0x180052902  nop
0x180052903  mov     rcx, [rbp+var_40]
0x180052907  test    rcx, rcx
0x18005290a  jz      short loc_180052919
0x18005290c  mov     rax, [rcx]
0x18005290f  mov     rax, [rax+10h]
0x180052913  call    _guard_dispatch_icall
0x180052918  nop
0x180052919  jmp     loc_180052A0F
0x18005291e  mov     rcx, [rbp+var_40]
0x180052922  test    rcx, rcx
0x180052925  jz      short loc_18005293B
0x180052927  mov     rax, [rcx]
0x18005292a  mov     rax, [rax+10h]
0x18005292e  call    _guard_dispatch_icall
0x180052933  mov     [rbp+var_40], 0
0x18005293b  lea     rdx, [rbp+var_40]; struct IXMLDOMNode **
0x18005293f  mov     rcx, rbx; wchar_t *
0x180052942  call    ?DspCreateDOMAndLoadXml@@YAJPEA_WPEAPEAUIXMLDOMNode@@@Z; DspCreateDOMAndLoadXml(wchar_t *,IXMLDOMNode * *)
0x180052947  mov     edi, eax
0x180052949  test    eax, eax
0x18005294b  jns     short loc_18005298B
0x18005294d  mov     rcx, [rbp+18h]; this
0x180052951  mov     r9d, eax; char *
0x180052954  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18005295b  mov     edx, 56Fh; void *
0x180052960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052965  nop
0x180052966  mov     rcx, rbx; bstrString
0x180052969  call    cs:__imp_SysFreeString
0x18005296f  nop
0x180052970  mov     rcx, [rbp+var_40]
0x180052974  test    rcx, rcx
0x180052977  jz      short loc_180052986
0x180052979  mov     rax, [rcx]
0x18005297c  mov     rax, [rax+10h]
0x180052980  call    _guard_dispatch_icall
0x180052985  nop
0x180052986  jmp     loc_180052A0F
0x18005298b  mov     rcx, [rbp+var_40]
0x18005298f  test    rcx, rcx
0x180052992  jnz     short loc_1800529A0
0x180052994  mov     edi, 80004003h
0x180052999  mov     edx, 52Eh
0x18005299e  jmp     short loc_1800529BF
0x1800529a0  lea     r9, [rbp+var_38]
0x1800529a4  lea     r8, qword_1800A1840
0x1800529ab  lea     rdx, [rbp+pv]
0x1800529af  call    GetElementSet
0x1800529b4  mov     edi, eax
0x1800529b6  test    eax, eax
0x1800529b8  jns     short loc_180052A16
0x1800529ba  mov     edx, 53Ch; void *
0x1800529bf  mov     r9d, edi; char *
0x1800529c2  mov     rcx, [rbp+18h]; this
0x1800529c6  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800529cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800529d2  mov     rcx, [rbp+18h]; this
0x1800529d6  mov     r9d, edi; char *
0x1800529d9  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800529e0  mov     edx, 570h; void *
0x1800529e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800529ea  nop
0x1800529eb  mov     rcx, rbx; bstrString
0x1800529ee  call    cs:__imp_SysFreeString
0x1800529f4  nop
0x1800529f5  mov     rcx, [rbp+var_40]
0x1800529f9  test    rcx, rcx
0x1800529fc  jz      short loc_180052A0B
0x1800529fe  mov     rax, [rcx]
0x180052a01  mov     rax, [rax+10h]
0x180052a05  call    _guard_dispatch_icall
0x180052a0a  nop
0x180052a0b  test    edi, edi
0x180052a0d  jns     short loc_180052A45
0x180052a0f  mov     edx, 17Dh
0x180052a14  jmp     short loc_180052A71
0x180052a16  xor     edi, edi
0x180052a18  lea     eax, [rdi+1]
0x180052a1b  cmp     dword ptr [rbp+var_28+0Ch], edi
0x180052a1e  cmova   edi, eax
0x180052a21  mov     rcx, rbx; bstrString
0x180052a24  call    cs:__imp_SysFreeString
0x180052a2a  nop
0x180052a2b  mov     rcx, [rbp+var_40]
0x180052a2f  test    rcx, rcx
0x180052a32  jz      short loc_180052A41
0x180052a34  mov     rax, [rcx]
0x180052a37  mov     rax, [rax+10h]
0x180052a3b  call    _guard_dispatch_icall
0x180052a40  nop
0x180052a41  test    edi, edi
0x180052a43  jnz     short loc_180052A51
0x180052a45  mov     edi, 80242009h
0x180052a4a  mov     edx, 17Fh
0x180052a4f  jmp     short loc_180052A71
0x180052a51  mov     [rbp+var_40], 0
0x180052a59  lea     r8, [rbp+var_40]
0x180052a5d  mov     rcx, [rbp+pv]; Src
0x180052a61  call    ??$SusStrCchDup@PEA_WPEA_W@@YAJPEA_WIPEAPEA_W@Z; SusStrCchDup<wchar_t *,wchar_t *>(wchar_t *,uint,wchar_t * *)
0x180052a66  mov     edi, eax
0x180052a68  test    eax, eax
0x180052a6a  jns     short loc_180052A86
0x180052a6c  mov     edx, 182h; void *
0x180052a71  mov     rcx, [rbp+18h]; this
0x180052a75  mov     r9d, edi; char *
0x180052a78  lea     r8, aCW1SSrcClientE_5; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180052a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a84  jmp     short loc_180052A8F
0x180052a86  mov     rax, [rbp+var_40]
0x180052a8a  mov     [rsi], rax
0x180052a8d  xor     edi, edi
0x180052a8f  mov     rcx, [rbp+pv]; pv
0x180052a93  test    rcx, rcx
0x180052a96  jz      short loc_180052A9E
0x180052a98  call    cs:__imp_CoTaskMemFree
0x180052a9e  mov     eax, edi
0x180052aa0  mov     rcx, [rbp+var_10]
0x180052aa4  xor     rcx, rsp; StackCookie
0x180052aa7  call    __security_check_cookie
0x180052aac  mov     rbx, [rsp+70h+arg_10]
0x180052ab4  add     rsp, 70h
0x180052ab8  pop     rdi
0x180052ab9  pop     rsi
0x180052aba  pop     rbp
0x180052abb  retn
```
