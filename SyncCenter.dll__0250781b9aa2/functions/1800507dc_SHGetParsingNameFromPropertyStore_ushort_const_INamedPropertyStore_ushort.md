# SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)

- ea: `0x1800507dc`
- end: `0x180050ab3`
- name: `?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z`
- size: `727`
- prototype: `int(const unsigned __int16 *, struct INamedPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050ee0`

## callees

- `0x180003b40`
- `0x18004f89c`
- `0x18004f920`
- `0x18004f98c`
- `0x1800507dc`
- `0x180050d24`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180050a75`
- `SHLWAPI!SHStrDupW` at `0x180050a75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a3f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050a4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050a4a`
- `PROPSYS!PropVariantToStringAlloc` at `0x180050937`
- `PROPSYS!PropVariantToStringAlloc` at `0x180050937`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a55`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a55`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18005098f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18005098f`

## pseudocode

```c
__int64 __fastcall SHGetParsingNameFromPropertyStore(
        const unsigned __int16 *a1,
        struct INamedPropertyStore *a2,
        unsigned __int16 **a3)
{
  struct INamedPropertyStoreVtbl *lpVtbl; // rax
  HRESULT v6; // ebx
  unsigned int v7; // edi
  const WCHAR *v8; // rcx
  struct INamedPropertyStoreVtbl *v9; // rax
  struct INamedPropertyStoreVtbl *v10; // rax
  const unsigned __int16 *v11; // rcx
  HRESULT v12; // eax
  __int64 v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *pv; // [rsp+50h] [rbp-B0h]
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT propvar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  _WORD v22[68]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v23; // [rsp+108h] [rbp+8h]
  int v24; // [rsp+110h] [rbp+10h]
  _WORD v25[68]; // [rsp+120h] [rbp+20h] BYREF
  LPCWSTR psz; // [rsp+1A8h] [rbp+A8h]
  int v27; // [rsp+1B0h] [rbp+B0h]
  wchar_t pszDest; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v29; // [rsp+1C2h] [rbp+C2h]
  __int16 v30; // [rsp+1CAh] [rbp+CAh]

  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, unsigned int *))lpVtbl->GetNameCount)(a2, &v15);
  if ( v6 >= 0 )
  {
    v27 = 65;
    v25[0] = 0;
    v7 = 0;
    v8 = v25;
    psz = v25;
    if ( v15 )
    {
      while ( 1 )
      {
        if ( v6 < 0 )
          goto LABEL_25;
        v9 = a2->lpVtbl;
        bstrString = 0;
        v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, _QWORD, BSTR *))v9->GetNameAt)(a2, v7, &bstrString);
        if ( v6 >= 0 )
          break;
LABEL_21:
        if ( ++v7 >= v15 )
        {
          if ( v6 < 0 )
            goto LABEL_25;
          v8 = psz;
          goto LABEL_24;
        }
      }
      v21 = 0;
      v10 = a2->lpVtbl;
      *(_OWORD *)propvar = 0;
      v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, BSTR, PROPVARIANT *))v10->GetNamedValue)(
             a2,
             bstrString,
             propvar);
      if ( v6 < 0 )
      {
LABEL_20:
        SysFreeString(bstrString);
        goto LABEL_21;
      }
      v11 = 0;
      pszDest = 0;
      v29 = 0;
      v30 = 0;
      ppszOut = 0;
      pv = 0;
      if ( LOWORD(propvar[0]) == 31 || LOWORD(propvar[0]) == 8 )
      {
        rgIndices[0] = 0;
        v6 = -2147024809;
        if ( ((__int64)propvar[0] & 0xFFF) != 0x1F && ((__int64)propvar[0] & 0xFFF) != 8 )
          goto LABEL_13;
        v11 = (const unsigned __int16 *)propvar[1];
        v6 = 0;
      }
      else
      {
        LODWORD(v14) = LOWORD(propvar[0]);
        StringCchPrintfExW(&pszDest, 6u, 0, 0, 0x800u, L":%04x", v14);
        v12 = PropVariantToStringAlloc(propvar, &ppszOut);
        v11 = ppszOut;
        v6 = v12;
      }
      pv = v11;
LABEL_13:
      if ( v6 >= 0 )
      {
        *(_QWORD *)rgIndices = 0;
        v6 = _EscapeField(v11, (LPWSTR *)rgIndices);
        if ( v6 >= 0 )
        {
          v24 = 65;
          v22[0] = 0;
          v23 = v22;
          v6 = ShStrW::Printf((ShStrW *)v22, L"%s%s=%s&", bstrString, &pszDest, *(_QWORD *)rgIndices);
          if ( v6 >= 0 )
            v6 = ShStrW::Append((ShStrW *)v25, v23, 0xFFFFFFFF);
          CoTaskMemFree(*(LPVOID *)rgIndices);
          ShStrW::Reset((ShStrW *)v22);
        }
        CoTaskMemFree(ppszOut);
      }
      PropVariantClear(propvar);
      goto LABEL_20;
    }
LABEL_24:
    v6 = SHStrDupW(v8, a3);
LABEL_25:
    ShStrW::Reset((ShStrW *)v25);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800507dc  mov     [rsp-8+arg_0], rbx
0x1800507e1  mov     [rsp-8+arg_18], rsi
0x1800507e6  push    rbp
0x1800507e7  push    rdi
0x1800507e8  push    r12
0x1800507ea  push    r13
0x1800507ec  push    r14
0x1800507ee  lea     rbp, [rsp-0E0h]
0x1800507f6  sub     rsp, 1E0h
0x1800507fd  mov     rax, cs:__security_cookie
0x180050804  xor     rax, rsp
0x180050807  mov     [rbp+100h+var_30], rax
0x18005080e  mov     rax, [rdx]
0x180050811  mov     rsi, rdx
0x180050814  lea     rdx, [rsp+200h+var_1C0]
0x180050819  mov     [rsp+200h+var_1C0], 0
0x180050821  mov     rcx, rsi
0x180050824  mov     r14, r8
0x180050827  mov     rax, [rax+28h]
0x18005082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050830  mov     ebx, eax
0x180050832  test    eax, eax
0x180050834  js      loc_180050A86
0x18005083a  xor     ecx, ecx
0x18005083c  mov     [rbp+100h+var_50], 41h ; 'A'
0x180050846  mov     [rbp+100h+var_E0], cx
0x18005084a  xor     edi, edi
0x18005084c  lea     rcx, [rbp+100h+var_E0]
0x180050850  mov     [rbp+100h+psz], rcx
0x180050857  cmp     [rsp+200h+var_1C0], edi
0x18005085b  jbe     loc_180050A72
0x180050861  lea     r13d, [rdi+1Fh]
0x180050865  lea     r12d, [rdi+8]
0x180050869  test    ebx, ebx
0x18005086b  js      loc_180050A7D
0x180050871  mov     rax, [rsi]
0x180050874  lea     r8, [rsp+200h+bstrString]
0x180050879  mov     edx, edi
0x18005087b  mov     [rsp+200h+bstrString], 0
0x180050884  mov     rcx, rsi
0x180050887  mov     rax, [rax+30h]
0x18005088b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050890  mov     ebx, eax
0x180050892  test    eax, eax
0x180050894  js      loc_180050A5B
0x18005089a  mov     rdx, [rsp+200h+bstrString]
0x18005089f  lea     r8, [rsp+200h+propvar]
0x1800508a4  xor     eax, eax
0x1800508a6  xorps   xmm0, xmm0
0x1800508a9  mov     [rsp+200h+var_188], rax
0x1800508ae  mov     rcx, rsi
0x1800508b1  mov     rax, [rsi]
0x1800508b4  movups  xmmword ptr [rsp+200h+propvar], xmm0
0x1800508b9  mov     rax, [rax+18h]
0x1800508bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508c2  mov     ebx, eax
0x1800508c4  test    eax, eax
0x1800508c6  js      loc_180050A50
0x1800508cc  xor     eax, eax
0x1800508ce  xor     ecx, ecx
0x1800508d0  mov     [rbp+100h+pszDest], ax
0x1800508d7  mov     [rbp+100h+var_3E], rax
0x1800508de  mov     [rbp+100h+var_36], ax
0x1800508e5  mov     [rsp+200h+ppszOut], rax
0x1800508ea  movzx   eax, word ptr [rsp+200h+propvar]
0x1800508ef  mov     [rsp+200h+pv], rcx
0x1800508f4  cmp     ax, r13w
0x1800508f8  jz      short loc_180050946
0x1800508fa  cmp     ax, r12w
0x1800508fe  jz      short loc_180050946
0x180050900  mov     [rsp+200h+var_1D0], eax
0x180050904  lea     edx, [rcx+6]; unsigned __int64
0x180050907  lea     rax, a04x; ":%04x"
0x18005090e  xor     r9d, r9d; unsigned __int64 *
0x180050911  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x180050916  lea     rcx, [rbp+100h+pszDest]; pszDest
0x18005091d  xor     r8d, r8d; unsigned __int16 **
0x180050920  mov     [rsp+200h+var_1E0], 800h; unsigned int
0x180050928  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18005092d  lea     rdx, [rsp+200h+ppszOut]; ppszOut
0x180050932  lea     rcx, [rsp+200h+propvar]; propvar
0x180050937  call    cs:__imp_PropVariantToStringAlloc
0x18005093d  mov     rcx, [rsp+200h+ppszOut]
0x180050942  mov     ebx, eax
0x180050944  jmp     short loc_1800509AC
0x180050946  mov     r8d, 0FFFh
0x18005094c  mov     [rsp+200h+rgIndices], ecx
0x180050950  movzx   edx, ax
0x180050953  mov     ebx, 80070057h
0x180050958  and     dx, r8w
0x18005095c  cmp     r13w, dx
0x180050960  jz      short loc_180050968
0x180050962  cmp     r12w, dx
0x180050966  jnz     short loc_1800509B1
0x180050968  bt      ax, 0Ch
0x18005096d  jnb     short loc_180050979
0x18005096f  mov     rax, [rsp+200h+var_188]
0x180050974  mov     rcx, [rax]
0x180050977  jmp     short loc_1800509AA
0x180050979  bt      ax, 0Dh
0x18005097e  jnb     short loc_18005099E
0x180050980  mov     rcx, [rsp+200h+propvar+8]; psa
0x180050985  lea     r8, [rsp+200h+pv]; pv
0x18005098a  lea     rdx, [rsp+200h+rgIndices]; rgIndices
0x18005098f  call    cs:__imp_SafeArrayGetElement
0x180050995  mov     rcx, [rsp+200h+pv]
0x18005099a  mov     ebx, eax
0x18005099c  jmp     short loc_1800509B1
0x18005099e  test    eax, 0FFFFF000h
0x1800509a3  jnz     short loc_1800509B1
0x1800509a5  mov     rcx, [rsp+200h+propvar+8]; unsigned __int16 *
0x1800509aa  xor     ebx, ebx
0x1800509ac  mov     [rsp+200h+pv], rcx
0x1800509b1  test    ebx, ebx
0x1800509b3  js      loc_180050A45
0x1800509b9  lea     rdx, [rsp+200h+rgIndices]; ppwsz
0x1800509be  mov     qword ptr [rsp+200h+rgIndices], 0
0x1800509c7  call    ?_EscapeField@@YAJPEBGPEAPEAG@Z; _EscapeField(ushort const *,ushort * *)
0x1800509cc  mov     ebx, eax
0x1800509ce  test    eax, eax
0x1800509d0  js      short loc_180050A3A
0x1800509d2  mov     r8, [rsp+200h+bstrString]
0x1800509d7  lea     r9, [rbp+100h+pszDest]
0x1800509de  xor     eax, eax
0x1800509e0  mov     [rbp+100h+var_F0], 41h ; 'A'
0x1800509e7  mov     [rbp+100h+var_180], ax
0x1800509eb  lea     rdx, aSSS; "%s%s=%s&"
0x1800509f2  lea     rax, [rbp+100h+var_180]
0x1800509f6  mov     [rbp+100h+var_F8], rax
0x1800509fa  lea     rcx, [rbp+100h+var_180]; this
0x1800509fe  mov     rax, qword ptr [rsp+200h+rgIndices]
0x180050a03  mov     qword ptr [rsp+200h+var_1E0], rax
0x180050a08  call    ?Printf@ShStrW@@QEAAJPEBGZZ; ShStrW::Printf(ushort const *,...)
0x180050a0d  mov     ebx, eax
0x180050a0f  test    eax, eax
0x180050a11  js      short loc_180050A26
0x180050a13  mov     rdx, [rbp+100h+var_F8]; unsigned __int16 *
0x180050a17  lea     rcx, [rbp+100h+var_E0]; this
0x180050a1b  or      r8d, 0FFFFFFFFh; unsigned int
0x180050a1f  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x180050a24  mov     ebx, eax
0x180050a26  mov     rcx, qword ptr [rsp+200h+rgIndices]; pv
0x180050a2b  call    cs:__imp_CoTaskMemFree
0x180050a31  lea     rcx, [rbp+100h+var_180]; this
0x180050a35  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x180050a3a  mov     rcx, [rsp+200h+ppszOut]; pv
0x180050a3f  call    cs:__imp_CoTaskMemFree
0x180050a45  lea     rcx, [rsp+200h+propvar]; pvar
0x180050a4a  call    cs:__imp_PropVariantClear
0x180050a50  mov     rcx, [rsp+200h+bstrString]; bstrString
0x180050a55  call    cs:__imp_SysFreeString
0x180050a5b  inc     edi
0x180050a5d  cmp     edi, [rsp+200h+var_1C0]
0x180050a61  jb      loc_180050869
0x180050a67  test    ebx, ebx
0x180050a69  js      short loc_180050A7D
0x180050a6b  mov     rcx, [rbp+100h+psz]; psz
0x180050a72  mov     rdx, r14; ppwsz
0x180050a75  call    cs:__imp_SHStrDupW
0x180050a7b  mov     ebx, eax
0x180050a7d  lea     rcx, [rbp+100h+var_E0]; this
0x180050a81  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x180050a86  mov     eax, ebx
0x180050a88  mov     rcx, [rbp+100h+var_30]
0x180050a8f  xor     rcx, rsp; StackCookie
0x180050a92  call    __security_check_cookie
0x180050a97  lea     r11, [rsp+200h+var_20]
0x180050a9f  mov     rbx, [r11+30h]
0x180050aa3  mov     rsi, [r11+48h]
0x180050aa7  mov     rsp, r11
0x180050aaa  pop     r14
0x180050aac  pop     r13
0x180050aae  pop     r12
0x180050ab0  pop     rdi
0x180050ab1  pop     rbp
0x180050ab2  retn
```
