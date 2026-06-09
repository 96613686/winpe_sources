# CInkRecoAlternate::GetPropertyValue(ushort *,tagVARIANT *)

- ea: `0x1800d31e0`
- end: `0x1800d33c6`
- name: `?GetPropertyValue@CInkRecoAlternate@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `486`
- prototype: `int(CInkRecoAlternate *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800816d4`
- `0x1800825e4`
- `0x1800a38dc`
- `0x1800d31e0`
- `0x180104f30`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800d3238`
- `OLEAUT32!__imp_VariantInit` at `0x1800d3238`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d334b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d334b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d32f6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d32f6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d332d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d332d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d32d7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d32d7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d3246`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d3246`

## pseudocode

```c
__int64 __fastcall CInkRecoAlternate::GetPropertyValue(
        CInkRecoAlternate *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  HRESULT v7; // eax
  unsigned int v8; // r8d
  const unsigned __int16 *v9; // r9
  HRESULT String; // ebx
  int v11; // edi
  int RangePropertyValue; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v14; // rdi
  HRESULT v15; // eax
  ULONG cElements; // [rsp+40h] [rbp-48h] BYREF
  void *ppvData; // [rsp+48h] [rbp-40h] BYREF
  struct tagRECO_RANGE v18; // [rsp+50h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-30h] BYREF

  if ( !a3 )
    return 2147500035LL;
  if ( !a2 )
    return 2147942487LL;
  pclsid = 0;
  cElements = 0;
  LODWORD(ppvData) = 0;
  VariantInit(a3);
  v7 = CLSIDFromString(a2, &pclsid);
  String = v7;
  if ( v7 < 0 )
  {
    if ( v7 == -2147221005 )
    {
      try
      {
        String = ATL::AtlSetErrorInfo(
                   &GUID_NULL,
                   (const unsigned __int16 *)0x46D,
                   v8,
                   v9,
                   &IID_IInkRecognitionAlternate,
                   -2147221005,
                   hInstance);
      }
      catch ( ... )
      {
        return (unsigned int)ReportWispException();
      }
    }
  }
  else
  {
    String = GetString(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), 0, (unsigned int *)&ppvData, 0);
    if ( String >= 0 )
    {
      v18.iwcBegin = 0;
      v11 = (int)ppvData;
      v18.cCount = (unsigned int)ppvData;
      RangePropertyValue = GetRangePropertyValue(
                             *(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL),
                             &pclsid,
                             &v18,
                             &cElements,
                             0);
      String = RangePropertyValue;
      if ( v18.iwcBegin || v18.cCount != v11 )
      {
        return (unsigned int)-2147467259;
      }
      else if ( RangePropertyValue >= 0 )
      {
        Vector = SafeArrayCreateVector(0x11u, 0, cElements);
        v14 = Vector;
        if ( Vector )
        {
          ppvData = 0;
          String = SafeArrayAccessData(Vector, &ppvData);
          if ( String < 0
            || (String = GetRangePropertyValue(
                           *(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL),
                           &pclsid,
                           &v18,
                           &cElements,
                           (unsigned __int8 *)ppvData),
                v15 = SafeArrayUnaccessData(v14),
                String < 0)
            || (String = v15, v15 < 0) )
          {
            SafeArrayDestroy(v14);
          }
          else
          {
            a3->vt = 8209;
            a3->llVal = (LONGLONG)v14;
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800d31e0  mov     [rsp+arg_18], rbx
0x1800d31e5  push    rsi
0x1800d31e6  push    rdi
0x1800d31e7  push    r14
0x1800d31e9  sub     rsp, 70h
0x1800d31ed  mov     rax, cs:__security_cookie
0x1800d31f4  xor     rax, rsp
0x1800d31f7  mov     [rsp+88h+var_20], rax
0x1800d31fc  mov     rsi, r8
0x1800d31ff  mov     rbx, rdx
0x1800d3202  mov     r14, rcx
0x1800d3205  test    r8, r8
0x1800d3208  jz      loc_1800D33A3
0x1800d320e  test    rdx, rdx
0x1800d3211  jnz     short loc_1800D321D
0x1800d3213  mov     eax, 80070057h
0x1800d3218  jmp     loc_1800D33A8
0x1800d321d  xorps   xmm0, xmm0
0x1800d3220  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x1800d3225  mov     [rsp+88h+cElements], 0
0x1800d322d  mov     dword ptr [rsp+88h+ppvData], 0
0x1800d3235  mov     rcx, rsi; pvarg
0x1800d3238  call    cs:__imp_VariantInit
0x1800d323e  lea     rdx, [rsp+88h+pclsid]; pclsid
0x1800d3243  mov     rcx, rbx; lpsz
0x1800d3246  call    cs:__imp_CLSIDFromString
0x1800d324c  mov     ebx, eax
0x1800d324e  test    eax, eax
0x1800d3250  js      loc_1800D3361
0x1800d3256  mov     rcx, [r14+20h]
0x1800d325a  xor     r9d, r9d; unsigned __int16 *
0x1800d325d  lea     r8, [rsp+88h+ppvData]; unsigned int *
0x1800d3262  xor     edx, edx; struct tagRECO_RANGE *
0x1800d3264  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d3268  call    ?GetString@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@PEAKPEAG@Z; GetString(tagWispAlternate *,tagRECO_RANGE *,ulong *,ushort *)
0x1800d326d  mov     ebx, eax
0x1800d326f  test    eax, eax
0x1800d3271  js      loc_1800D3399
0x1800d3277  mov     [rsp+88h+var_38.iwcBegin], 0
0x1800d327f  mov     edi, dword ptr [rsp+88h+ppvData]
0x1800d3283  mov     [rsp+88h+var_38.cCount], edi
0x1800d3287  mov     rcx, [r14+20h]
0x1800d328b  mov     [rsp+88h+var_68], 0; unsigned __int8 *
0x1800d3294  lea     r9, [rsp+88h+cElements]; unsigned int *
0x1800d3299  lea     r8, [rsp+88h+var_38]; struct tagRECO_RANGE *
0x1800d329e  lea     rdx, [rsp+88h+pclsid]; struct _GUID *
0x1800d32a3  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d32a7  call    ?GetRangePropertyValue@@YAJPEAUtagWispAlternate@@PEBU_GUID@@PEAUtagRECO_RANGE@@PEAKPEAE@Z; GetRangePropertyValue(tagWispAlternate *,_GUID const *,tagRECO_RANGE *,ulong *,uchar *)
0x1800d32ac  mov     ebx, eax
0x1800d32ae  cmp     [rsp+88h+var_38.iwcBegin], 0
0x1800d32b3  jnz     loc_1800D335A
0x1800d32b9  cmp     [rsp+88h+var_38.cCount], edi
0x1800d32bd  jnz     loc_1800D335A
0x1800d32c3  test    eax, eax
0x1800d32c5  js      loc_1800D3399
0x1800d32cb  mov     ecx, 11h; vt
0x1800d32d0  mov     r8d, [rsp+88h+cElements]; cElements
0x1800d32d5  xor     edx, edx; lLbound
0x1800d32d7  call    cs:__imp_SafeArrayCreateVector
0x1800d32dd  mov     rdi, rax
0x1800d32e0  test    rax, rax
0x1800d32e3  jz      short loc_1800D3353
0x1800d32e5  mov     [rsp+88h+ppvData], 0
0x1800d32ee  lea     rdx, [rsp+88h+ppvData]; ppvData
0x1800d32f3  mov     rcx, rax; psa
0x1800d32f6  call    cs:__imp_SafeArrayAccessData
0x1800d32fc  mov     ebx, eax
0x1800d32fe  test    eax, eax
0x1800d3300  js      short loc_1800D3348
0x1800d3302  mov     rdx, [rsp+88h+ppvData]
0x1800d3307  mov     rcx, [r14+20h]
0x1800d330b  mov     [rsp+88h+var_68], rdx; unsigned __int8 *
0x1800d3310  lea     r9, [rsp+88h+cElements]; unsigned int *
0x1800d3315  lea     r8, [rsp+88h+var_38]; struct tagRECO_RANGE *
0x1800d331a  lea     rdx, [rsp+88h+pclsid]; struct _GUID *
0x1800d331f  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d3323  call    ?GetRangePropertyValue@@YAJPEAUtagWispAlternate@@PEBU_GUID@@PEAUtagRECO_RANGE@@PEAKPEAE@Z; GetRangePropertyValue(tagWispAlternate *,_GUID const *,tagRECO_RANGE *,ulong *,uchar *)
0x1800d3328  mov     ebx, eax
0x1800d332a  mov     rcx, rdi; psa
0x1800d332d  call    cs:__imp_SafeArrayUnaccessData
0x1800d3333  test    ebx, ebx
0x1800d3335  js      short loc_1800D3348
0x1800d3337  mov     ebx, eax
0x1800d3339  test    eax, eax
0x1800d333b  js      short loc_1800D3348
0x1800d333d  mov     word ptr [rsi], 2011h
0x1800d3342  mov     [rsi+8], rdi
0x1800d3346  jmp     short loc_1800D3399
0x1800d3348  mov     rcx, rdi; psa
0x1800d334b  call    cs:__imp_SafeArrayDestroy
0x1800d3351  jmp     short loc_1800D3399
0x1800d3353  mov     ebx, 8007000Eh
0x1800d3358  jmp     short loc_1800D3399
0x1800d335a  mov     ebx, 80004005h
0x1800d335f  jmp     short loc_1800D3399
0x1800d3361  mov     ecx, 800401F3h
0x1800d3366  cmp     eax, ecx
0x1800d3368  jnz     short loc_1800D3399
0x1800d336a  mov     rax, cs:hInstance
0x1800d3371  mov     [rsp+88h+var_58], rax; HINSTANCE
0x1800d3376  mov     [rsp+88h+var_60], ecx; int
0x1800d337a  lea     rax, IID_IInkRecognitionAlternate
0x1800d3381  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1800d3386  mov     edx, 46Dh; unsigned __int16 *
0x1800d338b  lea     rcx, GUID_NULL; clsid
0x1800d3392  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800d3397  mov     ebx, eax
0x1800d3399  jmp     short loc_1800D339F
0x1800d339b  mov     ebx, dword ptr [rsp+88h+ppvData]
0x1800d339f  mov     eax, ebx
0x1800d33a1  jmp     short loc_1800D33A8
0x1800d33a3  mov     eax, 80004003h
0x1800d33a8  mov     rcx, [rsp+88h+var_20]
0x1800d33ad  xor     rcx, rsp; StackCookie
0x1800d33b0  call    __security_check_cookie
0x1800d33b5  mov     rbx, [rsp+88h+arg_18]
0x1800d33bd  add     rsp, 70h
0x1800d33c1  pop     r14
0x1800d33c3  pop     rdi
0x1800d33c4  pop     rsi
0x1800d33c5  retn
```
