# _ResolveMetaTagUrl

- ea: `0x1400128d4`
- end: `0x140012a25`
- name: `_ResolveMetaTagUrl`
- size: `337`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011aa4`

## callees

- `0x14000cbf4`
- `0x14000cca0`
- `0x14000d214`
- `0x1400128d4`
- `0x140014010`

## import_xrefs

- `urlmon!CreateUri` at `0x140012914`
- `urlmon!CreateUri` at `0x140012933`
- `urlmon!CreateUri` at `0x140012914`
- `urlmon!CreateUri` at `0x140012933`
- `urlmon!CoInternetCombineIUri` at `0x140012957`
- `urlmon!CoInternetCombineIUri` at `0x140012957`

## pseudocode

```c
__int64 __fastcall ResolveMetaTagUrl(const WCHAR *a1, const WCHAR *a2, __int64 *a3)
{
  HRESULT Uri; // ebx
  IUri *ppURI[2]; // [rsp+30h] [rbp-10h] BYREF
  IUri *ppCombinedUri; // [rsp+70h] [rbp+30h] BYREF
  IUri *pRelativeUri; // [rsp+78h] [rbp+38h] BYREF

  ppURI[0] = 0;
  pRelativeUri = 0;
  ppCombinedUri = 0;
  *a3 = 0;
  Uri = CreateUri(a1, 0x2000u, 0, ppURI);
  if ( Uri < 0
    || (Uri = CreateUri(a2, 0x2001u, 0, &pRelativeUri), Uri < 0)
    || (Uri = CoInternetCombineIUri(ppURI[0], pRelativeUri, 0, &ppCombinedUri, 0), Uri < 0)
    || (Uri = ((__int64 (__fastcall *)(IUri *, __int64 *))ppCombinedUri->lpVtbl->GetAbsoluteUri)(ppCombinedUri, a3),
        Uri < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        (unsigned int)&WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
        (_DWORD)a2,
        Uri);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      10,
      (unsigned int)&WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
      (_DWORD)a2,
      *a3);
  }
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&ppCombinedUri);
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(&pRelativeUri);
  ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(ppURI);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1400128d4  mov     [rsp-18h+arg_0], rbx
0x1400128d9  push    rbp
0x1400128da  push    rsi
0x1400128db  push    rdi
0x1400128dc  mov     rbp, rsp
0x1400128df  sub     rsp, 40h
0x1400128e3  mov     rsi, r8
0x1400128e6  mov     rdi, rdx
0x1400128e9  mov     [rbp+ppURI], 0
0x1400128f1  mov     [rbp+pRelativeUri], 0
0x1400128f9  mov     [rbp+ppCombinedUri], 0
0x140012901  mov     qword ptr [r8], 0
0x140012908  lea     r9, [rbp+ppURI]; ppURI
0x14001290c  xor     r8d, r8d; dwReserved
0x14001290f  mov     edx, 2000h; dwFlags
0x140012914  call    cs:__imp_CreateUri
0x14001291a  mov     ebx, eax
0x14001291c  test    eax, eax
0x14001291e  js      loc_1400129BD
0x140012924  lea     r9, [rbp+pRelativeUri]; ppURI
0x140012928  xor     r8d, r8d; dwReserved
0x14001292b  mov     edx, 2001h; dwFlags
0x140012930  mov     rcx, rdi; pwzURI
0x140012933  call    cs:__imp_CreateUri
0x140012939  mov     ebx, eax
0x14001293b  test    eax, eax
0x14001293d  js      short loc_1400129BD
0x14001293f  mov     [rsp+40h+dwReserved], 0; dwReserved
0x140012948  lea     r9, [rbp+ppCombinedUri]; ppCombinedUri
0x14001294c  xor     r8d, r8d; dwCombineFlags
0x14001294f  mov     rdx, [rbp+pRelativeUri]; pRelativeUri
0x140012953  mov     rcx, [rbp+ppURI]; pBaseUri
0x140012957  call    cs:__imp_CoInternetCombineIUri
0x14001295d  mov     ebx, eax
0x14001295f  test    eax, eax
0x140012961  js      short loc_1400129BD
0x140012963  mov     rcx, [rbp+ppCombinedUri]
0x140012967  mov     rax, [rcx]
0x14001296a  mov     rdx, rsi
0x14001296d  mov     rax, [rax+38h]
0x140012971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012976  mov     ebx, eax
0x140012978  test    eax, eax
0x14001297a  js      short loc_1400129BD
0x14001297c  lea     rax, WPP_GLOBAL_Control
0x140012983  mov     rcx, cs:WPP_GLOBAL_Control
0x14001298a  cmp     rcx, rax
0x14001298d  jz      short loc_1400129F9
0x14001298f  test    byte ptr [rcx+44h], 4
0x140012993  jz      short loc_1400129F9
0x140012995  cmp     byte ptr [rcx+41h], 5
0x140012999  jb      short loc_1400129F9
0x14001299b  mov     edx, 0Ah
0x1400129a0  mov     rax, [rsi]
0x1400129a3  mov     [rsp+40h+dwReserved], rax
0x1400129a8  mov     r9, rdi
0x1400129ab  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x1400129b2  mov     rcx, [rcx+38h]
0x1400129b6  call    WPP_SF_SS
0x1400129bb  jmp     short loc_1400129F9
0x1400129bd  lea     rax, WPP_GLOBAL_Control
0x1400129c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129cb  cmp     rcx, rax
0x1400129ce  jz      short loc_1400129F9
0x1400129d0  test    byte ptr [rcx+44h], 4
0x1400129d4  jz      short loc_1400129F9
0x1400129d6  cmp     byte ptr [rcx+41h], 2
0x1400129da  jb      short loc_1400129F9
0x1400129dc  mov     edx, 0Bh
0x1400129e1  mov     dword ptr [rsp+40h+dwReserved], ebx
0x1400129e5  mov     r9, rdi
0x1400129e8  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x1400129ef  mov     rcx, [rcx+38h]
0x1400129f3  call    WPP_SF_Sd
0x1400129f8  nop
0x1400129f9  lea     rcx, [rbp+ppCombinedUri]
0x1400129fd  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x140012a02  nop
0x140012a03  lea     rcx, [rbp+pRelativeUri]
0x140012a07  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x140012a0c  nop
0x140012a0d  lea     rcx, [rbp+ppURI]
0x140012a11  call    ??1?$CComPtr@UIHTMLFormElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IHTMLFormElement>::~CComPtr<IHTMLFormElement>(void)
0x140012a16  mov     eax, ebx
0x140012a18  mov     rbx, [rsp+40h+arg_0]
0x140012a1d  add     rsp, 40h
0x140012a21  pop     rdi
0x140012a22  pop     rsi
0x140012a23  pop     rbp
0x140012a24  retn
```
