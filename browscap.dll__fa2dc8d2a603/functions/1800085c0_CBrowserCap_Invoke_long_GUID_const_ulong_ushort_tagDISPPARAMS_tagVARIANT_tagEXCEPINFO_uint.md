# CBrowserCap::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800085c0`
- end: `0x180008884`
- name: `?Invoke@CBrowserCap@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `708`
- prototype: `__int64 __fastcall(CBrowserCap *this, __int64, const struct _GUID *, __int64, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000851c`
- `0x1800085c0`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180008654`
- `msvcrt!strcpy_s` at `0x18000868b`
- `msvcrt!strcpy_s` at `0x180008654`
- `msvcrt!strcpy_s` at `0x18000868b`
- `KERNEL32!MultiByteToWideChar` at `0x180008708`
- `KERNEL32!MultiByteToWideChar` at `0x18000878c`
- `KERNEL32!MultiByteToWideChar` at `0x180008708`
- `KERNEL32!MultiByteToWideChar` at `0x18000878c`
- `KERNEL32!LeaveCriticalSection` at `0x180008829`
- `KERNEL32!LeaveCriticalSection` at `0x180008829`
- `KERNEL32!EnterCriticalSection` at `0x1800087b9`
- `KERNEL32!EnterCriticalSection` at `0x1800087b9`
- `USER32!LoadStringA` at `0x18000863b`
- `USER32!LoadStringA` at `0x180008670`
- `USER32!LoadStringA` at `0x18000863b`
- `USER32!LoadStringA` at `0x180008670`
- `OLEAUT32!__imp_SysAllocString` at `0x18000871b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000879d`
- `OLEAUT32!__imp_SysAllocString` at `0x180008819`
- `OLEAUT32!__imp_SysAllocString` at `0x18000871b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000879d`
- `OLEAUT32!__imp_SysAllocString` at `0x180008819`
- `OLEAUT32!__imp_VariantCopy` at `0x180008803`
- `OLEAUT32!__imp_VariantCopy` at `0x180008803`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBrowserCap::Invoke(
        CBrowserCap *this,
        __int64 a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        VARIANTARG *pvargDest,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  int v9; // r15d
  const OLECHAR *v11; // rbx
  __int64 v12; // rax
  int v13; // edx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  const OLECHAR *v19; // rcx
  __int64 v20; // rax
  int v21; // edx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  __int64 v28; // r9
  unsigned __int64 v29; // r8
  unsigned int v30; // ebx
  _BYTE v31[32]; // [rsp+0h] [rbp-50h] BYREF
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-30h]
  int cchWideChar[2]; // [rsp+28h] [rbp-28h]
  VARIANTARG *v34; // [rsp+30h] [rbp-20h]
  struct tagEXCEPINFO *v35; // [rsp+38h] [rbp-18h]
  unsigned int *v36; // [rsp+40h] [rbp-10h]
  WCHAR WideCharStr[2]; // [rsp+50h] [rbp+0h] BYREF
  _com_error *v38; // [rsp+58h] [rbp+8h] BYREF
  CHAR Buffer[512]; // [rsp+60h] [rbp+10h] BYREF
  CHAR Destination[512]; // [rsp+260h] [rbp+210h] BYREF

  v9 = a2;
  if ( (int)a2 < 10000 )
  {
    v36 = a9;
    v35 = a8;
    v34 = pvargDest;
    *(_QWORD *)cchWideChar = a6;
    LOWORD(lpWideCharStr) = a5;
    return (unsigned int)ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::Invoke(
                           this,
                           a2,
                           a3);
  }
  if ( (a5 & 0xC) == 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v28 = *((_QWORD *)this + 10);
    v29 = (unsigned int)(v9 - 10000);
    if ( v29 >= (*((_QWORD *)this + 11) - v28) / 40 )
    {
      pvargDest->vt = 8;
      pvargDest->llVal = (LONGLONG)SysAllocString(L"unknown");
      v30 = 0;
    }
    else
    {
      v30 = VariantCopy(pvargDest, (const VARIANTARG *)(v28 + 8 * (v29 + 4 * v29 + 2)));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    return v30;
  }
  v11 = 0;
  if ( !LoadStringA(hInstance, 0x67u, Buffer, 512) )
    strcpy_s(Buffer, 0x200u, "?? Unknown (Can't find resource)");
  if ( !LoadStringA(hInstance, 0x68u, Destination, 512) )
    strcpy_s(Destination, 0x200u, "?? Unknown (Can't find resource)");
  a8->scode = -2147467259;
  v12 = -1;
  do
    ++v12;
  while ( Buffer[v12] );
  v13 = v12 + 1;
  if ( (int)v12 + 1 > 0x3FFFFFFF )
    goto LABEL_14;
  v14 = 2LL * (int)v12 + 2;
  v15 = v14 + 15;
  if ( v14 + 15 < v14 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  try
  {
    v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
    v17 = alloca(v16);
    v18 = alloca(v16);
  }
  catch ( _com_error *v38 )
  {
    *(_DWORD *)WideCharStr = *((_DWORD *)v38 + 2);
    return *(unsigned int *)WideCharStr;
  }
  catch ( ... )
  {
    *(_DWORD *)WideCharStr = -2147467259;
    return *(unsigned int *)WideCharStr;
  }
  if ( v31 == (_BYTE *)-80LL )
  {
LABEL_14:
    v19 = 0;
  }
  else
  {
    WideCharStr[0] = 0;
    v19 = (const OLECHAR *)((unsigned __int64)WideCharStr
                          & -(__int64)(MultiByteToWideChar(3u, 0, Buffer, -1, WideCharStr, v13) != 0));
  }
  a8->bstrSource = SysAllocString(v19);
  v20 = -1;
  do
    ++v20;
  while ( Destination[v20] );
  v21 = v20 + 1;
  if ( (int)v20 + 1 <= 0x3FFFFFFF )
  {
    v22 = 2LL * (int)v20 + 2;
    v23 = v22 + 15;
    if ( v22 + 15 < v22 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
    v25 = alloca(v24);
    v26 = alloca(v24);
    if ( v31 != (_BYTE *)-80LL )
    {
      WideCharStr[0] = 0;
      v11 = (const OLECHAR *)((unsigned __int64)WideCharStr
                            & -(__int64)(MultiByteToWideChar(3u, 0, Destination, -1, WideCharStr, v21) != 0));
    }
  }
  a8->bstrDescription = SysAllocString(v11);
  a8->wCode = v9;
  return 2147614729LL;
}

```

## disassembly

```asm
0x1800085c0  push    rbp
0x1800085c2  push    rbx
0x1800085c3  push    rsi
0x1800085c4  push    rdi
0x1800085c5  push    r12
0x1800085c7  push    r14
0x1800085c9  push    r15
0x1800085cb  sub     rsp, 470h
0x1800085d2  lea     rbp, [rsp+50h]
0x1800085d7  mov     rax, cs:__security_cookie
0x1800085de  xor     rax, rbp
0x1800085e1  mov     [rbp+450h+var_40], rax
0x1800085e8  mov     r15d, edx
0x1800085eb  mov     rdi, rcx
0x1800085ee  mov     rbx, [rbp+450h+pvargDest]
0x1800085f5  mov     r14, [rbp+450h+arg_38]
0x1800085fc  mov     rax, [rbp+450h+arg_28]
0x180008603  mov     rcx, [rbp+450h+arg_40]
0x18000860a  cmp     edx, 2710h
0x180008610  jl      loc_180008831
0x180008616  test    byte ptr [rbp+450h+arg_20], 0Ch
0x18000861d  jz      loc_1800087B5
0x180008623  mov     edi, 200h
0x180008628  mov     r9d, edi; cchBufferMax
0x18000862b  lea     r8, [rbp+450h+Buffer]; lpBuffer
0x18000862f  mov     edx, 67h ; 'g'; uID
0x180008634  mov     rcx, cs:hInstance; hInstance
0x18000863b  call    cs:__imp_LoadStringA
0x180008641  xor     ebx, ebx
0x180008643  test    eax, eax
0x180008645  jnz     short loc_18000865A
0x180008647  lea     r8, Source; "?? Unknown (Can't find resource)"
0x18000864e  mov     edx, edi; SizeInBytes
0x180008650  lea     rcx, [rbp+450h+Buffer]; Destination
0x180008654  call    cs:__imp_strcpy_s
0x18000865a  mov     r9d, edi; cchBufferMax
0x18000865d  lea     r8, [rbp+450h+Destination]; lpBuffer
0x180008664  mov     edx, 68h ; 'h'; uID
0x180008669  mov     rcx, cs:hInstance; hInstance
0x180008670  call    cs:__imp_LoadStringA
0x180008676  test    eax, eax
0x180008678  jnz     short loc_180008691
0x18000867a  lea     r8, Source; "?? Unknown (Can't find resource)"
0x180008681  mov     rdx, rdi; SizeInBytes
0x180008684  lea     rcx, [rbp+450h+Destination]; Destination
0x18000868b  call    cs:__imp_strcpy_s
0x180008691  mov     dword ptr [r14+38h], 80004005h
0x180008699  lea     rcx, [rbp+450h+Buffer]
0x18000869d  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800086a1  mov     rax, r12
0x1800086a4  inc     rax
0x1800086a7  cmp     [rcx+rax], bl
0x1800086aa  jnz     short loc_1800086A4
0x1800086ac  lea     edx, [rax+1]
0x1800086af  mov     rdi, 0FFFFFFFFFFFFFF0h
0x1800086b9  cmp     edx, 3FFFFFFFh
0x1800086bf  jg      short loc_180008718
0x1800086c1  cdqe
0x1800086c3  lea     rax, ds:2[rax*2]
0x1800086cb  lea     rcx, [rax+0Fh]
0x1800086cf  cmp     rcx, rax
0x1800086d2  ja      short loc_1800086D7
0x1800086d4  mov     rcx, rdi
0x1800086d7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800086db  mov     rax, rcx
0x1800086de  call    _alloca_probe
0x1800086e3  sub     rsp, rcx
0x1800086e6  lea     rsi, [rsp+4A0h+WideCharStr]
0x1800086eb  test    rsi, rsi
0x1800086ee  jz      short loc_180008718
0x1800086f0  mov     [rsi], bx
0x1800086f3  mov     [rsp+4A0h+cchWideChar], edx; cchWideChar
0x1800086f7  mov     [rsp+4A0h+lpWideCharStr], rsi; lpWideCharStr
0x1800086fc  mov     r9d, r12d; cbMultiByte
0x1800086ff  lea     r8, [rbp+450h+Buffer]; lpMultiByteStr
0x180008703  xor     edx, edx; dwFlags
0x180008705  lea     ecx, [rdx+3]; CodePage
0x180008708  call    cs:__imp_MultiByteToWideChar
0x18000870e  neg     eax
0x180008710  sbb     rcx, rcx
0x180008713  and     rcx, rsi
0x180008716  jmp     short loc_18000871B
0x180008718  mov     rcx, rbx; psz
0x18000871b  call    cs:__imp_SysAllocString
0x180008721  mov     [r14+8], rax
0x180008725  lea     rcx, [rbp+450h+Destination]
0x18000872c  mov     rax, r12
0x18000872f  inc     rax
0x180008732  cmp     [rcx+rax], bl
0x180008735  jnz     short loc_18000872F
0x180008737  lea     edx, [rax+1]
0x18000873a  cmp     edx, 3FFFFFFFh
0x180008740  jg      short loc_18000879A
0x180008742  cdqe
0x180008744  lea     rax, ds:2[rax*2]
0x18000874c  lea     rcx, [rax+0Fh]
0x180008750  cmp     rcx, rax
0x180008753  ja      short loc_180008758
0x180008755  mov     rcx, rdi
0x180008758  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000875c  mov     rax, rcx
0x18000875f  call    _alloca_probe
0x180008764  sub     rsp, rcx
0x180008767  lea     rdi, [rsp+4A0h+WideCharStr]
0x18000876c  test    rdi, rdi
0x18000876f  jz      short loc_18000879A
0x180008771  mov     [rdi], bx
0x180008774  mov     [rsp+4A0h+cchWideChar], edx; cchWideChar
0x180008778  mov     [rsp+4A0h+lpWideCharStr], rdi; lpWideCharStr
0x18000877d  mov     r9d, r12d; cbMultiByte
0x180008780  lea     r8, [rbp+450h+Destination]; lpMultiByteStr
0x180008787  xor     edx, edx; dwFlags
0x180008789  lea     ecx, [rdx+3]; CodePage
0x18000878c  call    cs:__imp_MultiByteToWideChar
0x180008792  neg     eax
0x180008794  sbb     rbx, rbx
0x180008797  and     rbx, rdi
0x18000879a  mov     rcx, rbx; psz
0x18000879d  call    cs:__imp_SysAllocString
0x1800087a3  mov     [r14+10h], rax
0x1800087a7  mov     [r14], r15w
0x1800087ab  mov     eax, 80020009h
0x1800087b0  jmp     loc_180008862
0x1800087b5  lea     rcx, [rdi+60h]; lpCriticalSection
0x1800087b9  call    cs:__imp_EnterCriticalSection
0x1800087bf  mov     r9, [rdi+50h]
0x1800087c3  lea     r8d, [r15-2710h]
0x1800087ca  mov     rcx, [rdi+58h]
0x1800087ce  sub     rcx, r9
0x1800087d1  mov     rax, 6666666666666667h
0x1800087db  imul    rcx
0x1800087de  sar     rdx, 4
0x1800087e2  mov     rax, rdx
0x1800087e5  shr     rax, 3Fh
0x1800087e9  add     rdx, rax
0x1800087ec  cmp     r8, rdx
0x1800087ef  jnb     short loc_18000880D
0x1800087f1  lea     rax, ds:2[r8*4]
0x1800087f9  add     rax, r8
0x1800087fc  lea     rdx, [r9+rax*8]; pvargSrc
0x180008800  mov     rcx, rbx; pvargDest
0x180008803  call    cs:__imp_VariantCopy
0x180008809  mov     ebx, eax
0x18000880b  jmp     short loc_180008825
0x18000880d  mov     word ptr [rbx], 8
0x180008812  lea     rcx, aUnknown; "unknown"
0x180008819  call    cs:__imp_SysAllocString
0x18000881f  mov     [rbx+8], rax
0x180008823  xor     ebx, ebx
0x180008825  lea     rcx, [rdi+60h]; lpCriticalSection
0x180008829  call    cs:__imp_LeaveCriticalSection
0x18000882f  jmp     short loc_18000885B
0x180008831  mov     [rsp+4A0h+var_460], rcx
0x180008836  mov     [rsp+4A0h+var_468], r14
0x18000883b  mov     [rsp+4A0h+var_470], rbx
0x180008840  mov     qword ptr [rsp+4A0h+cchWideChar], rax
0x180008845  movzx   eax, [rbp+450h+arg_20]
0x18000884c  mov     word ptr [rsp+4A0h+lpWideCharStr], ax
0x180008851  mov     rcx, rdi
0x180008854  call    ?Invoke@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180008859  mov     ebx, eax
0x18000885b  jmp     short loc_180008860
0x18000885d  mov     ebx, dword ptr [rbp+450h+WideCharStr]
0x180008860  mov     eax, ebx
0x180008862  mov     rcx, [rbp+450h+var_40]
0x180008869  xor     rcx, rbp; StackCookie
0x18000886c  call    __security_check_cookie
0x180008871  lea     rsp, [rbp+420h]
0x180008878  pop     r15
0x18000887a  pop     r14
0x18000887c  pop     r12
0x18000887e  pop     rdi
0x18000887f  pop     rsi
0x180008880  pop     rbx
0x180008881  pop     rbp
0x180008882  retn
```
