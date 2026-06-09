# SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)

- ea: `0x18002fc80`
- end: `0x18002ff66`
- name: `?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z`
- size: `742`
- prototype: `int(const unsigned __int16 *, struct INamedPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032d54`

## callees

- `0x180006900`
- `0x18000ed08`
- `0x18002fc80`
- `0x180033f30`
- `0x18003c404`
- `0x18003c480`
- `0x18003c4ec`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002ff27`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002ff27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002feff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002feff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fef4`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002fde5`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002fde5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff0a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002fe3d`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002fe3d`

## string_xrefs

- `0x18002fcf3`: `::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SHGetParsingNameFromPropertyStore(
        const unsigned __int16 *a1,
        struct INamedPropertyStore *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // edi
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // r8d
  __int64 v11; // [rsp+30h] [rbp-D0h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *pv; // [rsp+50h] [rbp-B0h]
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT propvar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h]
  _WORD v19[68]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR psz; // [rsp+108h] [rbp+8h]
  int v21; // [rsp+110h] [rbp+10h]
  _WORD v22[68]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v23; // [rsp+1A8h] [rbp+A8h]
  int v24; // [rsp+1B0h] [rbp+B0h]
  wchar_t pszDest; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v26; // [rsp+1C2h] [rbp+C2h]
  __int16 v27; // [rsp+1CAh] [rbp+CAh]

  v12 = 0;
  v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, unsigned int *))a2->lpVtbl->GetNameCount)(a2, &v12);
  if ( v5 >= 0 )
  {
    v19[0] = 0;
    psz = v19;
    v21 = 65;
    ShStrW::Append(
      (ShStrW *)v19,
      L"::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&",
      v6);
    v7 = 0;
    if ( v12 )
    {
      while ( 1 )
      {
        if ( v5 < 0 )
          goto LABEL_24;
        bstrString = 0;
        v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, _QWORD, BSTR *))a2->lpVtbl->GetNameAt)(
               a2,
               v7,
               &bstrString);
        if ( v5 >= 0 )
          break;
LABEL_21:
        if ( ++v7 >= v12 )
        {
          if ( v5 < 0 )
            goto LABEL_24;
          goto LABEL_23;
        }
      }
      *(_OWORD *)propvar = 0;
      v18 = 0;
      v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, BSTR, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
             a2,
             bstrString,
             propvar);
      if ( v5 < 0 )
      {
LABEL_20:
        SysFreeString(bstrString);
        goto LABEL_21;
      }
      pszDest = 0;
      v26 = 0;
      v27 = 0;
      v8 = 0;
      pv = 0;
      ppszOut = 0;
      if ( LOWORD(propvar[0]) == 31 || LOWORD(propvar[0]) == 8 )
      {
        rgIndices[0] = 0;
        v5 = -2147024809;
        if ( ((__int64)propvar[0] & 0xFFF) != 0x1F && ((__int64)propvar[0] & 0xFFF) != 8 )
          goto LABEL_13;
        v8 = (const unsigned __int16 *)propvar[1];
        v5 = 0;
      }
      else
      {
        LODWORD(v11) = LOWORD(propvar[0]);
        StringCchPrintfExW(&pszDest, 6u, 0, 0, 0x800u, L":%04x", v11);
        v5 = PropVariantToStringAlloc(propvar, &ppszOut);
        v8 = ppszOut;
      }
      pv = v8;
LABEL_13:
      if ( v5 >= 0 )
      {
        *(_QWORD *)rgIndices = 0;
        v5 = _EscapeField(v8, (LPWSTR *)rgIndices);
        if ( v5 >= 0 )
        {
          v22[0] = 0;
          v23 = v22;
          v24 = 65;
          v5 = ShStrW::Printf((ShStrW *)v22, L"%s%s=%s&", bstrString, &pszDest, *(_QWORD *)rgIndices);
          if ( v5 >= 0 )
            v5 = ShStrW::Append((ShStrW *)v19, v23, v9);
          CoTaskMemFree(*(LPVOID *)rgIndices);
          ShStrW::Reset((ShStrW *)v22);
        }
        CoTaskMemFree(ppszOut);
      }
      PropVariantClear(propvar);
      goto LABEL_20;
    }
LABEL_23:
    v5 = SHStrDupW(psz, a3);
LABEL_24:
    ShStrW::Reset((ShStrW *)v19);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002fc80  mov     [rsp-8+arg_0], rbx
0x18002fc85  mov     [rsp-8+arg_18], rsi
0x18002fc8a  push    rbp
0x18002fc8b  push    rdi
0x18002fc8c  push    r12
0x18002fc8e  push    r13
0x18002fc90  push    r14
0x18002fc92  lea     rbp, [rsp-0E0h]
0x18002fc9a  sub     rsp, 1E0h
0x18002fca1  mov     rax, cs:__security_cookie
0x18002fca8  xor     rax, rsp
0x18002fcab  mov     [rbp+100h+var_30], rax
0x18002fcb2  mov     r14, r8
0x18002fcb5  mov     rsi, rdx
0x18002fcb8  mov     [rsp+200h+var_1C0], 0
0x18002fcc0  mov     rax, [rdx]
0x18002fcc3  lea     rdx, [rsp+200h+var_1C0]
0x18002fcc8  mov     rcx, rsi
0x18002fccb  mov     rax, [rax+28h]
0x18002fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcd4  mov     ebx, eax
0x18002fcd6  test    eax, eax
0x18002fcd8  js      loc_18002FF39
0x18002fcde  xor     ecx, ecx
0x18002fce0  mov     [rbp+100h+var_180], cx
0x18002fce4  lea     rax, [rbp+100h+var_180]
0x18002fce8  mov     [rbp+100h+psz], rax
0x18002fcec  mov     [rbp+100h+var_F0], 41h ; 'A'
0x18002fcf3  lea     rdx, aD84fa0c2B0b344; "::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a"...
0x18002fcfa  lea     rcx, [rbp+100h+var_180]; this
0x18002fcfe  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x18002fd03  xor     edi, edi
0x18002fd05  cmp     [rsp+200h+var_1C0], edi
0x18002fd09  jbe     loc_18002FF20
0x18002fd0f  lea     r13d, [rdi+1Fh]
0x18002fd13  lea     r12d, [rdi+8]
0x18002fd17  test    ebx, ebx
0x18002fd19  js      loc_18002FF2F
0x18002fd1f  mov     [rsp+200h+bstrString], 0
0x18002fd28  mov     rax, [rsi]
0x18002fd2b  lea     r8, [rsp+200h+bstrString]
0x18002fd30  mov     edx, edi
0x18002fd32  mov     rcx, rsi
0x18002fd35  mov     rax, [rax+30h]
0x18002fd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd3e  mov     ebx, eax
0x18002fd40  test    eax, eax
0x18002fd42  js      loc_18002FF10
0x18002fd48  xorps   xmm0, xmm0
0x18002fd4b  xor     eax, eax
0x18002fd4d  movups  xmmword ptr [rsp+200h+propvar], xmm0
0x18002fd52  mov     [rsp+200h+var_188], rax
0x18002fd57  mov     rax, [rsi]
0x18002fd5a  lea     r8, [rsp+200h+propvar]
0x18002fd5f  mov     rdx, [rsp+200h+bstrString]
0x18002fd64  mov     rcx, rsi
0x18002fd67  mov     rax, [rax+18h]
0x18002fd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd70  mov     ebx, eax
0x18002fd72  test    eax, eax
0x18002fd74  js      loc_18002FF05
0x18002fd7a  xor     eax, eax
0x18002fd7c  mov     [rbp+100h+pszDest], ax
0x18002fd83  mov     [rbp+100h+var_3E], rax
0x18002fd8a  mov     [rbp+100h+var_36], ax
0x18002fd91  xor     ecx, ecx
0x18002fd93  mov     [rsp+200h+pv], rcx
0x18002fd98  mov     [rsp+200h+ppszOut], rax
0x18002fd9d  movzx   eax, word ptr [rsp+200h+propvar]
0x18002fda2  cmp     ax, r13w
0x18002fda6  jz      short loc_18002FDF4
0x18002fda8  cmp     ax, r12w
0x18002fdac  jz      short loc_18002FDF4
0x18002fdae  mov     [rsp+200h+var_1D0], eax
0x18002fdb2  lea     rax, a04x; ":%04x"
0x18002fdb9  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x18002fdbe  mov     [rsp+200h+var_1E0], 800h; unsigned int
0x18002fdc6  xor     r9d, r9d; unsigned __int64 *
0x18002fdc9  xor     r8d, r8d; unsigned __int16 **
0x18002fdcc  lea     edx, [rcx+6]; unsigned __int64
0x18002fdcf  lea     rcx, [rbp+100h+pszDest]; pszDest
0x18002fdd6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18002fddb  lea     rdx, [rsp+200h+ppszOut]; ppszOut
0x18002fde0  lea     rcx, [rsp+200h+propvar]; propvar
0x18002fde5  call    cs:__imp_PropVariantToStringAlloc
0x18002fdeb  mov     ebx, eax
0x18002fded  mov     rcx, [rsp+200h+ppszOut]
0x18002fdf2  jmp     short loc_18002FE5A
0x18002fdf4  mov     [rsp+200h+rgIndices], ecx
0x18002fdf8  mov     r8d, 0FFFh
0x18002fdfe  movzx   edx, ax
0x18002fe01  and     dx, r8w
0x18002fe05  mov     ebx, 80070057h
0x18002fe0a  cmp     r13w, dx
0x18002fe0e  jz      short loc_18002FE16
0x18002fe10  cmp     r12w, dx
0x18002fe14  jnz     short loc_18002FE5F
0x18002fe16  bt      ax, 0Ch
0x18002fe1b  jnb     short loc_18002FE27
0x18002fe1d  mov     rax, [rsp+200h+var_188]
0x18002fe22  mov     rcx, [rax]
0x18002fe25  jmp     short loc_18002FE58
0x18002fe27  bt      ax, 0Dh
0x18002fe2c  jnb     short loc_18002FE4C
0x18002fe2e  lea     r8, [rsp+200h+pv]; pv
0x18002fe33  lea     rdx, [rsp+200h+rgIndices]; rgIndices
0x18002fe38  mov     rcx, [rsp+200h+propvar+8]; psa
0x18002fe3d  call    cs:__imp_SafeArrayGetElement
0x18002fe43  mov     ebx, eax
0x18002fe45  mov     rcx, [rsp+200h+pv]
0x18002fe4a  jmp     short loc_18002FE5F
0x18002fe4c  test    eax, 0FFFFF000h
0x18002fe51  jnz     short loc_18002FE5F
0x18002fe53  mov     rcx, [rsp+200h+propvar+8]; unsigned __int16 *
0x18002fe58  xor     ebx, ebx
0x18002fe5a  mov     [rsp+200h+pv], rcx
0x18002fe5f  test    ebx, ebx
0x18002fe61  js      loc_18002FEFA
0x18002fe67  mov     qword ptr [rsp+200h+rgIndices], 0
0x18002fe70  lea     rdx, [rsp+200h+rgIndices]; ppwsz
0x18002fe75  call    ?_EscapeField@@YAJPEBGPEAPEAG@Z; _EscapeField(ushort const *,ushort * *)
0x18002fe7a  mov     ebx, eax
0x18002fe7c  test    eax, eax
0x18002fe7e  js      short loc_18002FEEF
0x18002fe80  xor     eax, eax
0x18002fe82  mov     [rbp+100h+var_E0], ax
0x18002fe86  lea     rax, [rbp+100h+var_E0]
0x18002fe8a  mov     [rbp+100h+var_58], rax
0x18002fe91  mov     [rbp+100h+var_50], 41h ; 'A'
0x18002fe9b  mov     rax, qword ptr [rsp+200h+rgIndices]
0x18002fea0  mov     qword ptr [rsp+200h+var_1E0], rax
0x18002fea5  lea     r9, [rbp+100h+pszDest]
0x18002feac  mov     r8, [rsp+200h+bstrString]
0x18002feb1  lea     rdx, aSSS; "%s%s=%s&"
0x18002feb8  lea     rcx, [rbp+100h+var_E0]; this
0x18002febc  call    ?Printf@ShStrW@@QEAAJPEBGZZ; ShStrW::Printf(ushort const *,...)
0x18002fec1  mov     ebx, eax
0x18002fec3  test    eax, eax
0x18002fec5  js      short loc_18002FED9
0x18002fec7  mov     rdx, [rbp+100h+var_58]; unsigned __int16 *
0x18002fece  lea     rcx, [rbp+100h+var_180]; this
0x18002fed2  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x18002fed7  mov     ebx, eax
0x18002fed9  mov     rcx, qword ptr [rsp+200h+rgIndices]; pv
0x18002fede  call    cs:__imp_CoTaskMemFree
0x18002fee4  nop
0x18002fee5  lea     rcx, [rbp+100h+var_E0]; this
0x18002fee9  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x18002feee  nop
0x18002feef  mov     rcx, [rsp+200h+ppszOut]; pv
0x18002fef4  call    cs:__imp_CoTaskMemFree
0x18002fefa  lea     rcx, [rsp+200h+propvar]; pvar
0x18002feff  call    cs:__imp_PropVariantClear
0x18002ff05  mov     rcx, [rsp+200h+bstrString]; bstrString
0x18002ff0a  call    cs:__imp_SysFreeString
0x18002ff10  inc     edi
0x18002ff12  cmp     edi, [rsp+200h+var_1C0]
0x18002ff16  jb      loc_18002FD17
0x18002ff1c  test    ebx, ebx
0x18002ff1e  js      short loc_18002FF2F
0x18002ff20  mov     rdx, r14; ppwsz
0x18002ff23  mov     rcx, [rbp+100h+psz]; psz
0x18002ff27  call    cs:__imp_SHStrDupW
0x18002ff2d  mov     ebx, eax
0x18002ff2f  lea     rcx, [rbp+100h+var_180]; this
0x18002ff33  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x18002ff38  nop
0x18002ff39  mov     eax, ebx
0x18002ff3b  mov     rcx, [rbp+100h+var_30]
0x18002ff42  xor     rcx, rsp; StackCookie
0x18002ff45  call    __security_check_cookie
0x18002ff4a  lea     r11, [rsp+200h+var_20]
0x18002ff52  mov     rbx, [r11+30h]
0x18002ff56  mov     rsi, [r11+48h]
0x18002ff5a  mov     rsp, r11
0x18002ff5d  pop     r14
0x18002ff5f  pop     r13
0x18002ff61  pop     r12
0x18002ff63  pop     rdi
0x18002ff64  pop     rbp
0x18002ff65  retn
```
