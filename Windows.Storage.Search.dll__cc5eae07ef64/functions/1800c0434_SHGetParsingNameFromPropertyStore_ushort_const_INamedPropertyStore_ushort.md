# SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)

- ea: `0x1800c0434`
- end: `0x1800c06a8`
- name: `?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z`
- size: `628`
- prototype: `int(const unsigned __int16 *, struct INamedPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2be0`

## callees

- `0x18002d8a8`
- `0x1800526d4`
- `0x18006ce00`
- `0x180071dc0`
- `0x180076f18`
- `0x1800bf510`
- `0x1800c0434`
- `0x1800c06b0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x1800c066e`
- `SHCORE!SHStrDupW` at `0x1800c066e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0638`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0643`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c0643`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800c0580`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800c0580`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c064e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c064e`

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
  HRESULT StringElemCast; // eax
  unsigned __int16 *v12; // rcx
  __int64 v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-A0h] BYREF
  struct tagPROPVARIANT propvar; // [rsp+68h] [rbp-98h] BYREF
  _WORD v21[68]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpString; // [rsp+108h] [rbp+8h]
  int v23; // [rsp+110h] [rbp+10h]
  _WORD v24[68]; // [rsp+120h] [rbp+20h] BYREF
  LPCWSTR psz; // [rsp+1A8h] [rbp+A8h]
  int v26; // [rsp+1B0h] [rbp+B0h]
  wchar_t pszDest; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v28; // [rsp+1C2h] [rbp+C2h]
  __int16 v29; // [rsp+1CAh] [rbp+CAh]

  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, unsigned int *))lpVtbl->GetNameCount)(a2, &v15);
  if ( v6 >= 0 )
  {
    v26 = 65;
    v24[0] = 0;
    v7 = 0;
    v8 = v24;
    psz = v24;
    if ( v15 )
    {
      while ( v6 >= 0 )
      {
        v9 = a2->lpVtbl;
        bstrString = 0;
        v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, _QWORD, BSTR *))v9->GetNameAt)(a2, v7, &bstrString);
        if ( v6 >= 0 )
        {
          v10 = a2->lpVtbl;
          memset(&propvar, 0, sizeof(propvar));
          v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, BSTR, struct tagPROPVARIANT *))v10->GetNamedValue)(
                 a2,
                 bstrString,
                 &propvar);
          if ( v6 >= 0 )
          {
            pszDest = 0;
            v28 = 0;
            v29 = 0;
            v17 = 0;
            ppszOut = 0;
            if ( propvar.vt == 31 || propvar.vt == 8 )
            {
              StringElemCast = PropVariantGetStringElemCast(&propvar, 0, (const unsigned __int16 **)&v17);
              v12 = v17;
            }
            else
            {
              LODWORD(v14) = propvar.vt;
              StringCchPrintfExW(&pszDest, 6u, 0, 0, 0x800u, L":%04x", v14);
              StringElemCast = PropVariantToStringAlloc((const PROPVARIANT *const)&propvar, &ppszOut);
              v12 = ppszOut;
              v17 = ppszOut;
            }
            v6 = StringElemCast;
            if ( StringElemCast >= 0 )
            {
              pv = 0;
              v6 = _EscapeField(v12, (LPWSTR *)&pv);
              if ( v6 >= 0 )
              {
                v23 = 65;
                v21[0] = 0;
                lpString = v21;
                v6 = ShStrW::Printf((ShStrW *)v21, L"%s%s=%s&", bstrString, &pszDest, pv);
                if ( v6 >= 0 )
                  v6 = ShStrW::Append((ShStrW *)v24, lpString, 0xFFFFFFFF);
                CoTaskMemFree(pv);
                ShStrW::~ShStrW((ShStrW *)v21);
              }
              CoTaskMemFree(ppszOut);
            }
            PropVariantClear((PROPVARIANT *)&propvar);
          }
          SysFreeString(bstrString);
        }
        if ( ++v7 >= v15 )
        {
          if ( v6 < 0 )
            break;
          v8 = psz;
          goto LABEL_21;
        }
      }
    }
    else
    {
LABEL_21:
      v6 = SHStrDupW(v8, a3);
    }
    ShStrW::~ShStrW((ShStrW *)v24);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c0434  mov     [rsp-8+arg_0], rbx
0x1800c0439  mov     [rsp-8+arg_18], rsi
0x1800c043e  push    rbp
0x1800c043f  push    rdi
0x1800c0440  push    r14
0x1800c0442  lea     rbp, [rsp-0E0h]
0x1800c044a  sub     rsp, 1E0h
0x1800c0451  mov     rax, cs:__security_cookie
0x1800c0458  xor     rax, rsp
0x1800c045b  mov     [rbp+0F0h+var_20], rax
0x1800c0462  mov     rax, [rdx]
0x1800c0465  mov     rsi, rdx
0x1800c0468  lea     rdx, [rsp+1F0h+var_1B0]
0x1800c046d  mov     [rsp+1F0h+var_1B0], 0
0x1800c0475  mov     rcx, rsi
0x1800c0478  mov     r14, r8
0x1800c047b  mov     rax, [rax+28h]
0x1800c047f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0484  mov     ebx, eax
0x1800c0486  test    eax, eax
0x1800c0488  js      loc_1800C067F
0x1800c048e  xor     ecx, ecx
0x1800c0490  mov     [rbp+0F0h+var_40], 41h ; 'A'
0x1800c049a  mov     [rbp+0F0h+var_D0], cx
0x1800c049e  xor     edi, edi
0x1800c04a0  lea     rcx, [rbp+0F0h+var_D0]
0x1800c04a4  mov     [rbp+0F0h+psz], rcx
0x1800c04ab  cmp     [rsp+1F0h+var_1B0], edi
0x1800c04af  jbe     loc_1800C066B
0x1800c04b5  test    ebx, ebx
0x1800c04b7  js      loc_1800C0676
0x1800c04bd  mov     rax, [rsi]
0x1800c04c0  lea     r8, [rsp+1F0h+bstrString]
0x1800c04c5  mov     edx, edi
0x1800c04c7  mov     [rsp+1F0h+bstrString], 0
0x1800c04d0  mov     rcx, rsi
0x1800c04d3  mov     rax, [rax+30h]
0x1800c04d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c04dc  mov     ebx, eax
0x1800c04de  test    eax, eax
0x1800c04e0  js      loc_1800C0654
0x1800c04e6  mov     rdx, [rsp+1F0h+bstrString]
0x1800c04eb  lea     r8, [rsp+1F0h+propvar]
0x1800c04f0  xor     eax, eax
0x1800c04f2  xorps   xmm0, xmm0
0x1800c04f5  mov     [rsp+1F0h+var_178], rax
0x1800c04fa  mov     rcx, rsi
0x1800c04fd  mov     rax, [rsi]
0x1800c0500  movups  xmmword ptr [rsp+1F0h+propvar], xmm0
0x1800c0505  mov     rax, [rax+18h]
0x1800c0509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c050e  mov     ebx, eax
0x1800c0510  test    eax, eax
0x1800c0512  js      loc_1800C0649
0x1800c0518  xor     eax, eax
0x1800c051a  mov     [rbp+0F0h+pszDest], ax
0x1800c0521  mov     [rbp+0F0h+var_2E], rax
0x1800c0528  mov     [rbp+0F0h+var_26], ax
0x1800c052f  mov     [rsp+1F0h+var_1A0], rax
0x1800c0534  mov     [rsp+1F0h+ppszOut], rax
0x1800c0539  movzx   eax, word ptr [rsp+1F0h+propvar]
0x1800c053e  cmp     eax, 1Fh
0x1800c0541  jz      short loc_1800C0592
0x1800c0543  cmp     eax, 8
0x1800c0546  jz      short loc_1800C0592
0x1800c0548  mov     [rsp+1F0h+var_1C0], eax
0x1800c054c  lea     rcx, [rbp+0F0h+pszDest]; pszDest
0x1800c0553  xor     r9d, r9d; unsigned __int64 *
0x1800c0556  lea     rax, a04x; ":%04x"
0x1800c055d  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x1800c0562  xor     r8d, r8d; unsigned __int16 **
0x1800c0565  mov     [rsp+1F0h+var_1D0], 800h; unsigned int
0x1800c056d  lea     edx, [r9+6]; unsigned __int64
0x1800c0571  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800c0576  lea     rdx, [rsp+1F0h+ppszOut]; ppszOut
0x1800c057b  lea     rcx, [rsp+1F0h+propvar]; propvar
0x1800c0580  call    cs:__imp_PropVariantToStringAlloc
0x1800c0586  mov     rcx, [rsp+1F0h+ppszOut]
0x1800c058b  mov     [rsp+1F0h+var_1A0], rcx
0x1800c0590  jmp     short loc_1800C05A8
0x1800c0592  lea     r8, [rsp+1F0h+var_1A0]; unsigned __int16 **
0x1800c0597  xor     edx, edx; unsigned int
0x1800c0599  lea     rcx, [rsp+1F0h+propvar]; struct tagPROPVARIANT *
0x1800c059e  call    ?PropVariantGetStringElemCast@@YAJAEBUtagPROPVARIANT@@KPEAPEBG@Z; PropVariantGetStringElemCast(tagPROPVARIANT const &,ulong,ushort const * *)
0x1800c05a3  mov     rcx, [rsp+1F0h+var_1A0]; unsigned __int16 *
0x1800c05a8  mov     ebx, eax
0x1800c05aa  test    eax, eax
0x1800c05ac  js      loc_1800C063E
0x1800c05b2  lea     rdx, [rsp+1F0h+pv]; ppwsz
0x1800c05b7  mov     [rsp+1F0h+pv], 0
0x1800c05c0  call    ?_EscapeField@@YAJPEBGPEAPEAG@Z; _EscapeField(ushort const *,ushort * *)
0x1800c05c5  mov     ebx, eax
0x1800c05c7  test    eax, eax
0x1800c05c9  js      short loc_1800C0633
0x1800c05cb  mov     r8, [rsp+1F0h+bstrString]
0x1800c05d0  lea     r9, [rbp+0F0h+pszDest]
0x1800c05d7  xor     eax, eax
0x1800c05d9  mov     [rbp+0F0h+var_E0], 41h ; 'A'
0x1800c05e0  mov     [rbp+0F0h+var_170], ax
0x1800c05e4  lea     rdx, aSSS; "%s%s=%s&"
0x1800c05eb  lea     rax, [rbp+0F0h+var_170]
0x1800c05ef  mov     [rbp+0F0h+lpString], rax
0x1800c05f3  lea     rcx, [rbp+0F0h+var_170]; this
0x1800c05f7  mov     rax, [rsp+1F0h+pv]
0x1800c05fc  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1800c0601  call    ?Printf@ShStrW@@QEAAJPEBGZZ; ShStrW::Printf(ushort const *,...)
0x1800c0606  mov     ebx, eax
0x1800c0608  test    eax, eax
0x1800c060a  js      short loc_1800C061F
0x1800c060c  mov     rdx, [rbp+0F0h+lpString]; lpString
0x1800c0610  lea     rcx, [rbp+0F0h+var_D0]; this
0x1800c0614  or      r8d, 0FFFFFFFFh; unsigned int
0x1800c0618  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x1800c061d  mov     ebx, eax
0x1800c061f  mov     rcx, [rsp+1F0h+pv]; pv
0x1800c0624  call    cs:__imp_CoTaskMemFree
0x1800c062a  lea     rcx, [rbp+0F0h+var_170]; this
0x1800c062e  call    ??1ShStrW@@QEAA@XZ; ShStrW::~ShStrW(void)
0x1800c0633  mov     rcx, [rsp+1F0h+ppszOut]; pv
0x1800c0638  call    cs:__imp_CoTaskMemFree
0x1800c063e  lea     rcx, [rsp+1F0h+propvar]; pvar
0x1800c0643  call    cs:__imp_PropVariantClear
0x1800c0649  mov     rcx, [rsp+1F0h+bstrString]; bstrString
0x1800c064e  call    cs:__imp_SysFreeString
0x1800c0654  inc     edi
0x1800c0656  cmp     edi, [rsp+1F0h+var_1B0]
0x1800c065a  jb      loc_1800C04B5
0x1800c0660  test    ebx, ebx
0x1800c0662  js      short loc_1800C0676
0x1800c0664  mov     rcx, [rbp+0F0h+psz]; psz
0x1800c066b  mov     rdx, r14; ppwsz
0x1800c066e  call    cs:__imp_SHStrDupW
0x1800c0674  mov     ebx, eax
0x1800c0676  lea     rcx, [rbp+0F0h+var_D0]; this
0x1800c067a  call    ??1ShStrW@@QEAA@XZ; ShStrW::~ShStrW(void)
0x1800c067f  mov     eax, ebx
0x1800c0681  mov     rcx, [rbp+0F0h+var_20]
0x1800c0688  xor     rcx, rsp; StackCookie
0x1800c068b  call    __security_check_cookie
0x1800c0690  lea     r11, [rsp+1F0h+var_10]
0x1800c0698  mov     rbx, [r11+20h]
0x1800c069c  mov     rsi, [r11+38h]
0x1800c06a0  mov     rsp, r11
0x1800c06a3  pop     r14
0x1800c06a5  pop     rdi
0x1800c06a6  pop     rbp
0x1800c06a7  retn
```
