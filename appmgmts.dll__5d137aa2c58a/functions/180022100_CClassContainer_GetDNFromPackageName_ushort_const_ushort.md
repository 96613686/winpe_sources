# CClassContainer::GetDNFromPackageName(ushort const *,ushort * *)

- ea: `0x180022100`
- end: `0x1800222e5`
- name: `?GetDNFromPackageName@CClassContainer@@UEAAJPEBGPEAPEAG@Z`
- size: `485`
- prototype: `__int64 __fastcall(CClassContainer *this, const unsigned __int16 *, HLOCAL *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800016d0`
- `0x18001e754`
- `0x180022100`
- `0x1800234b0`
- `0x1800240b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800221ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800221ae`
- `adsldpc!ADSIExecuteSearch` at `0x1800221a2`
- `adsldpc!ADSIExecuteSearch` at `0x1800221a2`
- `adsldpc!ADSIGetNextRow` at `0x180022261`
- `adsldpc!ADSIGetNextRow` at `0x180022261`
- `adsldpc!ADSICloseSearchHandle` at `0x1800222ba`
- `adsldpc!ADSICloseSearchHandle` at `0x1800222ba`
- `adsldpc!ADSIGetFirstRow` at `0x1800221c7`
- `adsldpc!ADSIGetFirstRow` at `0x1800221c7`
- `adsldpc!ADSIFreeColumn` at `0x180022220`
- `adsldpc!ADSIFreeColumn` at `0x1800222a4`
- `adsldpc!ADSIFreeColumn` at `0x180022220`
- `adsldpc!ADSIFreeColumn` at `0x1800222a4`

## string_xrefs

- `0x180022156`: `ADsPath`

## pseudocode

```c
__int64 __fastcall CClassContainer::GetDNFromPackageName(CClassContainer *this, const unsigned __int16 *a2, HLOCAL *a3)
{
  __int64 result; // rax
  int v6; // ebx
  int i; // eax
  ADS_BOOLEAN Boolean; // ebx
  void *v9; // [rsp+30h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-51h] BYREF
  struct ads_search_column v11; // [rsp+40h] [rbp-49h] BYREF
  struct ads_search_column v12; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v13[3]; // [rsp+A0h] [rbp+17h] BYREF

  v9 = 0;
  v13[0] = L"objectclass";
  v13[1] = L"packageFlags";
  v11.hReserved = 0;
  *a3 = 0;
  hMem = 0;
  v13[2] = L"ADsPath";
  memset(&v11, 0, 32);
  result = GetEscapedNameFilter(a2, (unsigned __int16 **)&hMem);
  if ( (int)result >= 0 )
  {
    v6 = ADSIExecuteSearch(*((_QWORD *)this + 70), hMem, v13, 3, &v9);
    LocalFree(hMem);
    if ( v6 >= 0 )
    {
      for ( i = ADSIGetFirstRow(*((_QWORD *)this + 70), v9); ; i = ADSIGetNextRow(*((_QWORD *)this + 70), v9) )
      {
        v6 = i;
        if ( i < 0 || i == 20498 )
          break;
        if ( (int)DSGetAndValidateColumn(*((void **)this + 70), v9, ADSTYPE_INTEGER, L"packageFlags", &v11) >= 0 )
        {
          if ( v11.dwNumValues )
            Boolean = v11.pADsValues->Boolean;
          else
            LOWORD(Boolean) = 0;
          ADSIFreeColumn(*((_QWORD *)this + 70), &v11);
          if ( (Boolean & 0x180) == 0 )
          {
            v6 = DSGetAndValidateColumn(*((void **)this + 70), v9, ADSTYPE_CASE_IGNORE_STRING, L"ADsPath", &v11);
            if ( v6 >= 0 )
            {
              v12 = v11;
              UnpackStrAllocFrom<_ads_attr_info>((__int64)&v12, a3);
              ADSIFreeColumn(*((_QWORD *)this + 70), &v11);
              break;
            }
          }
        }
      }
      if ( v9 )
        ADSICloseSearchHandle(*((_QWORD *)this + 70));
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180022100  mov     [rsp-8+arg_18], rbx
0x180022105  push    rbp
0x180022106  push    rsi
0x180022107  push    rdi
0x180022108  push    r12
0x18002210a  push    r13
0x18002210c  lea     rbp, [rsp-37h]
0x180022111  sub     rsp, 0C0h
0x180022118  mov     rax, cs:__security_cookie
0x18002211f  xor     rax, rsp
0x180022122  mov     [rbp+57h+var_28], rax
0x180022126  mov     rdi, rcx
0x180022129  mov     [rbp+57h+var_B0], 0
0x180022131  mov     rax, rdx
0x180022134  lea     rcx, aObjectclass; "objectclass"
0x18002213b  mov     [rbp+57h+var_40], rcx
0x18002213f  lea     r12, aPackageflags; "packageFlags"
0x180022146  xor     ecx, ecx
0x180022148  mov     [rbp+57h+var_38], r12
0x18002214c  xorps   xmm0, xmm0
0x18002214f  mov     [rbp+57h+var_A0.hReserved], rcx
0x180022153  mov     [r8], rcx
0x180022156  lea     r13, aAdspath; "ADsPath"
0x18002215d  mov     [rbp+57h+hMem], rcx
0x180022161  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x180022165  mov     rcx, rax; unsigned __int16 *
0x180022168  mov     [rbp+57h+var_30], r13
0x18002216c  mov     rsi, r8
0x18002216f  movups  xmmword ptr [rbp+57h+var_A0.pszAttrName], xmm0
0x180022173  movups  xmmword ptr [rbp+57h+var_A0.pADsValues], xmm0
0x180022177  call    ?GetEscapedNameFilter@@YAJPEBGPEAPEAG@Z; GetEscapedNameFilter(ushort const *,ushort * *)
0x18002217c  test    eax, eax
0x18002217e  js      loc_1800222C2
0x180022184  mov     rdx, [rbp+57h+hMem]
0x180022188  lea     rax, [rbp+57h+var_B0]
0x18002218c  mov     rcx, [rdi+230h]
0x180022193  lea     r8, [rbp+57h+var_40]
0x180022197  mov     r9d, 3
0x18002219d  mov     [rsp+0E0h+var_C0], rax
0x1800221a2  call    cs:__imp_ADSIExecuteSearch
0x1800221a8  mov     rcx, [rbp+57h+hMem]; hMem
0x1800221ac  mov     ebx, eax
0x1800221ae  call    cs:__imp_LocalFree
0x1800221b4  test    ebx, ebx
0x1800221b6  js      loc_1800222C0
0x1800221bc  mov     rdx, [rbp+57h+var_B0]
0x1800221c0  mov     rcx, [rdi+230h]
0x1800221c7  call    cs:__imp_ADSIGetFirstRow
0x1800221cd  jmp     loc_180022267
0x1800221d2  cmp     ebx, 5012h
0x1800221d8  jz      loc_1800222AA
0x1800221de  mov     rdx, [rbp+57h+var_B0]; void *
0x1800221e2  lea     rax, [rbp+57h+var_A0]
0x1800221e6  mov     rcx, [rdi+230h]; void *
0x1800221ed  mov     r9, r12; unsigned __int16 *
0x1800221f0  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800221f6  mov     [rsp+0E0h+var_C0], rax; struct ads_search_column *
0x1800221fb  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180022200  test    eax, eax
0x180022202  js      short loc_180022256
0x180022204  cmp     [rbp+57h+var_A0.dwNumValues], 0
0x180022208  jz      short loc_180022213
0x18002220a  mov     rax, [rbp+57h+var_A0.pADsValues]
0x18002220e  mov     ebx, [rax+8]
0x180022211  jmp     short loc_180022215
0x180022213  xor     ebx, ebx
0x180022215  mov     rcx, [rdi+230h]
0x18002221c  lea     rdx, [rbp+57h+var_A0]
0x180022220  call    cs:__imp_ADSIFreeColumn
0x180022226  test    ebx, 180h
0x18002222c  jnz     short loc_180022256
0x18002222e  mov     rdx, [rbp+57h+var_B0]; void *
0x180022232  lea     rax, [rbp+57h+var_A0]
0x180022236  mov     rcx, [rdi+230h]; void *
0x18002223d  mov     r9, r13; unsigned __int16 *
0x180022240  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180022246  mov     [rsp+0E0h+var_C0], rax; struct ads_search_column *
0x18002224b  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180022250  mov     ebx, eax
0x180022252  test    eax, eax
0x180022254  jns     short loc_180022273
0x180022256  mov     rdx, [rbp+57h+var_B0]
0x18002225a  mov     rcx, [rdi+230h]
0x180022261  call    cs:__imp_ADSIGetNextRow
0x180022267  mov     ebx, eax
0x180022269  test    eax, eax
0x18002226b  jns     loc_1800221D2
0x180022271  jmp     short loc_1800222AA
0x180022273  movups  xmm0, xmmword ptr [rbp+57h+var_A0.pszAttrName]
0x180022277  mov     rdx, rsi
0x18002227a  lea     rcx, [rbp+57h+var_70]
0x18002227e  movups  xmm1, xmmword ptr [rbp+57h+var_A0.pADsValues]
0x180022282  movaps  [rbp+57h+var_70], xmm0
0x180022286  movsd   xmm0, [rbp+57h+var_A0.hReserved]
0x18002228b  movsd   [rbp+57h+var_50], xmm0
0x180022290  movaps  [rbp+57h+var_60], xmm1
0x180022294  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x180022299  mov     rcx, [rdi+230h]
0x1800222a0  lea     rdx, [rbp+57h+var_A0]
0x1800222a4  call    cs:__imp_ADSIFreeColumn
0x1800222aa  mov     rdx, [rbp+57h+var_B0]
0x1800222ae  test    rdx, rdx
0x1800222b1  jz      short loc_1800222C0
0x1800222b3  mov     rcx, [rdi+230h]
0x1800222ba  call    cs:__imp_ADSICloseSearchHandle
0x1800222c0  mov     eax, ebx
0x1800222c2  mov     rcx, [rbp+57h+var_28]
0x1800222c6  xor     rcx, rsp; StackCookie
0x1800222c9  call    __security_check_cookie
0x1800222ce  mov     rbx, [rsp+0E0h+arg_18]
0x1800222d6  add     rsp, 0C0h
0x1800222dd  pop     r13
0x1800222df  pop     r12
0x1800222e1  pop     rdi
0x1800222e2  pop     rsi
0x1800222e3  pop     rbp
0x1800222e4  retn
```
