# CNormalizationXsltObject::_CombineUrls(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x18004bc10`
- end: `0x18004bdae`
- name: `?_CombineUrls@CNormalizationXsltObject@@MEAAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(CNormalizationXsltObject *__hidden this, struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006900`
- `0x18000ecc4`
- `0x18004bc10`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004bd3c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004bd3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bd7b`
- `OLEAUT32!__imp_SysStringLen` at `0x18004bce0`
- `OLEAUT32!__imp_SysStringLen` at `0x18004bce0`
- `urlmon!CoInternetCombineUrl` at `0x18004bd15`
- `urlmon!CoInternetCombineUrl` at `0x18004bd15`

## pseudocode

```c
__int64 __fastcall CNormalizationXsltObject::_CombineUrls(
        CNormalizationXsltObject *this,
        struct tagDISPPARAMS *a2,
        struct tagVARIANT *a3)
{
  VARIANTARG *rgvarg; // rdx
  __int64 v7; // rax
  int v8; // edx
  OLECHAR *v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  BSTR v12; // rax
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pwzBaseUrl; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszResult[2088]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2->cArgs != 2 )
    return (unsigned int)-2147352562;
  rgvarg = a2->rgvarg;
  if ( rgvarg->vt != 8 || rgvarg[1].vt != 8 || !a3 )
    return (unsigned int)-2147352568;
  v7 = *(_QWORD *)this;
  pwzBaseUrl = 0;
  pbstr = 0;
  v8 = (*(__int64 (__fastcall **)(CNormalizationXsltObject *, LONGLONG, BSTR *))(v7 + 128))(this, rgvarg->llVal, &pbstr);
  if ( v8 < 0 )
  {
    v9 = 0;
    pbstr = 0;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(CNormalizationXsltObject *, LONGLONG, LPCWSTR *))(*(_QWORD *)this + 128LL))(
           this,
           a2->rgvarg[1].llVal,
           &pwzBaseUrl);
    v9 = pbstr;
  }
  if ( v8 < 0 )
    goto LABEL_19;
  if ( SysStringLen(v9) )
    v10 = CoInternetCombineUrl(pwzBaseUrl, pbstr, 0, pszResult, 0x825u, 0, 0);
  else
    v10 = StringCchCopyW(pszResult, 0x825u, pwzBaseUrl);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 != 1 && v10 >= 0 )
      goto LABEL_17;
    goto LABEL_18;
  }
  v12 = SysAllocString(pszResult);
  if ( !v12 )
  {
LABEL_18:
    v9 = pbstr;
LABEL_19:
    a3->vt = 8;
    v11 = 0;
    a3->llVal = (LONGLONG)v9;
    goto LABEL_20;
  }
  a3->vt = 8;
  a3->llVal = (LONGLONG)v12;
LABEL_17:
  SysFreeString(pbstr);
LABEL_20:
  SysFreeString((BSTR)pwzBaseUrl);
  return v11;
}

```

## disassembly

```asm
0x18004bc10  push    rbp
0x18004bc12  push    rbx
0x18004bc13  push    rsi
0x18004bc14  push    rdi
0x18004bc15  push    r15
0x18004bc17  lea     rbp, [rsp-0FB0h]
0x18004bc1f  mov     eax, 10B0h
0x18004bc24  call    _alloca_probe
0x18004bc29  sub     rsp, rax
0x18004bc2c  mov     rax, cs:__security_cookie
0x18004bc33  xor     rax, rsp
0x18004bc36  mov     [rbp+0FD0h+var_30], rax
0x18004bc3d  cmp     dword ptr [rdx+10h], 2
0x18004bc41  mov     rdi, r8
0x18004bc44  mov     rbx, rdx
0x18004bc47  mov     rsi, rcx
0x18004bc4a  jnz     loc_18004BD8A
0x18004bc50  mov     rdx, [rdx]
0x18004bc53  mov     r15d, 8
0x18004bc59  cmp     [rdx], r15w
0x18004bc5d  jnz     loc_18004BD83
0x18004bc63  cmp     [rdx+18h], r15w
0x18004bc68  jnz     loc_18004BD83
0x18004bc6e  test    r8, r8
0x18004bc71  jz      loc_18004BD83
0x18004bc77  mov     rax, [rcx]
0x18004bc7a  lea     r8, [rsp+10D0h+pbstr]
0x18004bc7f  mov     [rsp+10D0h+pwzBaseUrl], 0
0x18004bc88  mov     [rsp+10D0h+pbstr], 0
0x18004bc91  mov     rdx, [rdx+8]
0x18004bc95  mov     rax, [rax+80h]
0x18004bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bca1  mov     edx, eax
0x18004bca3  test    eax, eax
0x18004bca5  js      short loc_18004BCCE
0x18004bca7  mov     rax, [rsi]
0x18004bcaa  lea     r8, [rsp+10D0h+pwzBaseUrl]
0x18004bcaf  mov     rdx, [rbx]
0x18004bcb2  mov     rcx, rsi
0x18004bcb5  mov     rax, [rax+80h]
0x18004bcbc  mov     rdx, [rdx+20h]
0x18004bcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcc5  mov     edx, eax
0x18004bcc7  mov     rax, [rsp+10D0h+pbstr]
0x18004bccc  jmp     short loc_18004BCD5
0x18004bcce  xor     eax, eax
0x18004bcd0  mov     [rsp+10D0h+pbstr], rax
0x18004bcd5  test    edx, edx
0x18004bcd7  js      loc_18004BD6C
0x18004bcdd  mov     rcx, rax; pbstr
0x18004bce0  call    cs:__imp_SysStringLen
0x18004bce6  test    eax, eax
0x18004bce8  jz      short loc_18004BD1D
0x18004bcea  mov     rdx, [rsp+10D0h+pbstr]; pwzRelativeUrl
0x18004bcef  lea     r9, [rsp+10D0h+pszResult]; pszResult
0x18004bcf4  mov     rcx, [rsp+10D0h+pwzBaseUrl]; pwzBaseUrl
0x18004bcf9  xor     r8d, r8d; dwCombineFlags
0x18004bcfc  mov     [rsp+10D0h+dwReserved], 0; dwReserved
0x18004bd04  mov     [rsp+10D0h+pcchResult], 0; pcchResult
0x18004bd0d  mov     [rsp+10D0h+cchResult], 825h; cchResult
0x18004bd15  call    cs:__imp_CoInternetCombineUrl
0x18004bd1b  jmp     short loc_18004BD31
0x18004bd1d  mov     r8, [rsp+10D0h+pwzBaseUrl]; unsigned __int16 *
0x18004bd22  lea     rcx, [rsp+10D0h+pszResult]; unsigned __int16 *
0x18004bd27  mov     edx, 825h; unsigned __int64
0x18004bd2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bd31  mov     ebx, eax
0x18004bd33  test    eax, eax
0x18004bd35  jnz     short loc_18004BD51
0x18004bd37  lea     rcx, [rsp+10D0h+pszResult]; psz
0x18004bd3c  call    cs:__imp_SysAllocString
0x18004bd42  test    rax, rax
0x18004bd45  jz      short loc_18004BD67
0x18004bd47  mov     [rdi], r15w
0x18004bd4b  mov     [rdi+8], rax
0x18004bd4f  jmp     short loc_18004BD5A
0x18004bd51  cmp     ebx, 1
0x18004bd54  jz      short loc_18004BD67
0x18004bd56  test    ebx, ebx
0x18004bd58  js      short loc_18004BD67
0x18004bd5a  mov     rcx, [rsp+10D0h+pbstr]; bstrString
0x18004bd5f  call    cs:__imp_SysFreeString
0x18004bd65  jmp     short loc_18004BD76
0x18004bd67  mov     rax, [rsp+10D0h+pbstr]
0x18004bd6c  mov     [rdi], r15w
0x18004bd70  xor     ebx, ebx
0x18004bd72  mov     [rdi+8], rax
0x18004bd76  mov     rcx, [rsp+10D0h+pwzBaseUrl]; bstrString
0x18004bd7b  call    cs:__imp_SysFreeString
0x18004bd81  jmp     short loc_18004BD8F
0x18004bd83  mov     ebx, 80020008h
0x18004bd88  jmp     short loc_18004BD8F
0x18004bd8a  mov     ebx, 8002000Eh
0x18004bd8f  mov     eax, ebx
0x18004bd91  mov     rcx, [rbp+0FD0h+var_30]
0x18004bd98  xor     rcx, rsp; StackCookie
0x18004bd9b  call    __security_check_cookie
0x18004bda0  add     rsp, 10B0h
0x18004bda7  pop     r15
0x18004bda9  pop     rdi
0x18004bdaa  pop     rsi
0x18004bdab  pop     rbx
0x18004bdac  pop     rbp
0x18004bdad  retn
```
