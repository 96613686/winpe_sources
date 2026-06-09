# _GetUrlDomain

- ea: `0x1400127b0`
- end: `0x1400128ce`
- name: `_GetUrlDomain`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011aa4`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x14000d214`
- `0x1400127b0`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001282b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001282b`
- `urlmon!CreateUri` at `0x1400127d6`
- `urlmon!CreateUri` at `0x1400127d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUrlDomain(const WCHAR *a1, BSTR *a2)
{
  HRESULT v3; // ebx
  unsigned int i; // edi
  struct IUriVtbl *lpVtbl; // rax
  int v6; // eax
  BSTR v7; // r9
  BSTR bstrString; // [rsp+48h] [rbp+10h] BYREF
  IUri *ppURI; // [rsp+50h] [rbp+18h] BYREF

  ppURI = 0;
  *a2 = 0;
  v3 = CreateUri(a1, 0x2000u, 0, &ppURI);
  if ( v3 < 0 )
    goto LABEL_17;
  bstrString = 0;
  for ( i = 0; i <= 1; ++i )
  {
    lpVtbl = ppURI->lpVtbl;
    if ( i )
      v6 = ((__int64 (__fastcall *)(IUri *, BSTR *))lpVtbl->GetHost)(ppURI, &bstrString);
    else
      v6 = ((__int64 (__fastcall *)(IUri *, BSTR *))lpVtbl->GetDomain)(ppURI, &bstrString);
    v3 = v6;
    v7 = bstrString;
    if ( v6 >= 0 )
    {
      if ( !bstrString )
        continue;
      if ( *bstrString )
        break;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      v7 = 0;
      bstrString = 0;
    }
  }
  *a2 = v7;
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, v7);
    }
    goto LABEL_21;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      13,
      &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
      (unsigned int)v3);
  }
LABEL_21:
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&ppURI);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400127b0  mov     [rsp+arg_0], rbx
0x1400127b5  push    rbp
0x1400127b6  push    rsi
0x1400127b7  push    rdi
0x1400127b8  sub     rsp, 20h
0x1400127bc  mov     rsi, rdx
0x1400127bf  xor     ebp, ebp
0x1400127c1  mov     [rsp+38h+ppURI], rbp
0x1400127c6  mov     [rdx], rbp
0x1400127c9  lea     r9, [rsp+38h+ppURI]; ppURI
0x1400127ce  xor     r8d, r8d; dwReserved
0x1400127d1  mov     edx, 2000h; dwFlags
0x1400127d6  call    cs:__imp_CreateUri
0x1400127dc  mov     ebx, eax
0x1400127de  test    eax, eax
0x1400127e0  js      loc_14001287D
0x1400127e6  mov     [rsp+38h+bstrString], rbp
0x1400127eb  mov     edi, ebp
0x1400127ed  mov     rcx, [rsp+38h+ppURI]
0x1400127f2  lea     rdx, [rsp+38h+bstrString]
0x1400127f7  mov     rax, [rcx]
0x1400127fa  test    edi, edi
0x1400127fc  jnz     short loc_140012804
0x1400127fe  mov     rax, [rax+50h]
0x140012802  jmp     short loc_140012808
0x140012804  mov     rax, [rax+68h]
0x140012808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001280d  mov     ebx, eax
0x14001280f  mov     r9, [rsp+38h+bstrString]
0x140012814  test    eax, eax
0x140012816  js      short loc_140012823
0x140012818  test    r9, r9
0x14001281b  jz      short loc_140012839
0x14001281d  cmp     [r9], bp
0x140012821  jnz     short loc_140012840
0x140012823  test    r9, r9
0x140012826  jz      short loc_140012839
0x140012828  mov     rcx, r9; bstrString
0x14001282b  call    cs:__imp_SysFreeString
0x140012831  mov     r9, rbp
0x140012834  mov     [rsp+38h+bstrString], rbp
0x140012839  inc     edi
0x14001283b  cmp     edi, 1
0x14001283e  jbe     short loc_1400127ED
0x140012840  mov     [rsi], r9
0x140012843  test    ebx, ebx
0x140012845  js      short loc_14001287D
0x140012847  lea     rax, WPP_GLOBAL_Control
0x14001284e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012855  cmp     rcx, rax
0x140012858  jz      short loc_1400128B5
0x14001285a  test    byte ptr [rcx+44h], 4
0x14001285e  jz      short loc_1400128B5
0x140012860  cmp     byte ptr [rcx+41h], 5
0x140012864  jb      short loc_1400128B5
0x140012866  mov     edx, 0Ch
0x14001286b  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x140012872  mov     rcx, [rcx+38h]
0x140012876  call    WPP_SF_S
0x14001287b  jmp     short loc_1400128B5
0x14001287d  lea     rax, WPP_GLOBAL_Control
0x140012884  mov     rcx, cs:WPP_GLOBAL_Control
0x14001288b  cmp     rcx, rax
0x14001288e  jz      short loc_1400128B5
0x140012890  test    byte ptr [rcx+44h], 4
0x140012894  jz      short loc_1400128B5
0x140012896  cmp     byte ptr [rcx+41h], 2
0x14001289a  jb      short loc_1400128B5
0x14001289c  mov     edx, 0Dh
0x1400128a1  mov     r9d, ebx
0x1400128a4  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x1400128ab  mov     rcx, [rcx+38h]
0x1400128af  call    WPP_SF_d
0x1400128b4  nop
0x1400128b5  lea     rcx, [rsp+38h+ppURI]
0x1400128ba  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x1400128bf  mov     eax, ebx
0x1400128c1  mov     rbx, [rsp+38h+arg_0]
0x1400128c6  add     rsp, 20h
0x1400128ca  pop     rdi
0x1400128cb  pop     rsi
0x1400128cc  pop     rbp
0x1400128cd  retn
```
