# ATL::AtlSetErrorInfo(_GUID const &,wchar_t const *,ulong,wchar_t const *,_GUID const &,long,HINSTANCE__ *)

- ea: `0x180135924`
- end: `0x180135ad8`
- name: `?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEB_WK10JPEAUHINSTANCE__@@@Z`
- size: `436`
- prototype: `__int64 __usercall@<rax>(IID *clsid@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, const struct _GUID *, int, HINSTANCE)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180079b74`
- `0x18007f6bc`
- `0x18007fcd0`
- `0x18008b800`
- `0x180166990`

## callees

- `0x18002e44c`
- `0x18005bf7c`
- `0x1801244c0`
- `0x180132bb0`
- `0x180135924`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801359a2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801359a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18013598a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18013598a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180135a82`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180135a82`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1801359dc`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1801359dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135a41`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180135a18`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180135a18`

## pseudocode

```c
__int64 __fastcall ATL::AtlSetErrorInfo(
        IID *clsid,
        WCHAR *a2,
        __int64 a3,
        const wchar_t *a4,
        const struct _GUID *a5,
        unsigned int a6)
{
  WCHAR *v6; // rdi
  int v8; // esi
  int v9; // eax
  unsigned int v10; // ebx
  LPOLESTR v11; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpszProgID; // [rsp+28h] [rbp-D8h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v16 = 0;
  v6 = a2;
  Buffer[0] = 0;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v10 = a6;
  }
  else
  {
    v8 = (unsigned __int16)a2;
    if ( !LoadStringW(0, (unsigned __int16)a2, Buffer, 1024) )
    {
      v9 = _o_wcscpy_s(Buffer, 1024, L"Unknown Error");
      ATL::AtlCrtErrorCheck(v9);
    }
    v10 = a6;
    v6 = Buffer;
    if ( !a6 )
      v10 = v8 | 0x80040000;
  }
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    perrinfo = 0;
    ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a5);
    lpszProgID = 0;
    ProgIDFromCLSID(clsid, &lpszProgID);
    v11 = lpszProgID;
    if ( lpszProgID )
    {
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->SetSource)(pperrinfo);
      v11 = lpszProgID;
    }
    CoTaskMemFree(v11);
    ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v6);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
           &perrinfo) >= 0 )
      SetErrorInfo(0, perrinfo);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&perrinfo);
  }
  if ( !v10 )
    v10 = -2147352567;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pperrinfo);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v16);
  return v10;
}

```

## disassembly

```asm
0x180135924  mov     [rsp-8+arg_10], rbx
0x180135929  push    rbp
0x18013592a  push    rsi
0x18013592b  push    rdi
0x18013592c  push    r14
0x18013592e  push    r15
0x180135930  lea     rbp, [rsp-750h]
0x180135938  sub     rsp, 850h
0x18013593f  mov     rax, cs:__security_cookie
0x180135946  xor     rax, rsp
0x180135949  mov     [rbp+770h+var_30], rax
0x180135950  mov     r15, [rbp+770h+arg_20]
0x180135957  xor     eax, eax
0x180135959  mov     [rsp+870h+var_838], 0
0x180135962  mov     rdi, rdx
0x180135965  mov     [rsp+870h+Buffer], ax
0x18013596a  mov     r14, rcx
0x18013596d  cmp     rdx, 10000h
0x180135974  jnb     short loc_1801359C8
0x180135976  movzx   esi, dx
0x180135979  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x18013597e  mov     ebx, 400h
0x180135983  mov     edx, esi; uID
0x180135985  mov     r9d, ebx; cchBufferMax
0x180135988  xor     ecx, ecx; hInstance
0x18013598a  call    cs:__imp_LoadStringW
0x180135990  test    eax, eax
0x180135992  jnz     short loc_1801359AF
0x180135994  lea     r8, aUnknownError; "Unknown Error"
0x18013599b  mov     edx, ebx
0x18013599d  lea     rcx, [rsp+870h+Buffer]
0x1801359a2  call    cs:__imp__o_wcscpy_s
0x1801359a8  mov     ecx, eax; int
0x1801359aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1801359af  mov     ebx, [rbp+770h+arg_28]
0x1801359b5  lea     rdi, [rsp+870h+Buffer]
0x1801359ba  test    ebx, ebx
0x1801359bc  jnz     short loc_1801359CE
0x1801359be  mov     ebx, esi
0x1801359c0  or      ebx, 80040000h
0x1801359c6  jmp     short loc_1801359CE
0x1801359c8  mov     ebx, [rbp+770h+arg_28]
0x1801359ce  lea     rcx, [rsp+870h+pperrinfo]; pperrinfo
0x1801359d3  mov     [rsp+870h+pperrinfo], 0
0x1801359dc  call    cs:__imp_CreateErrorInfo
0x1801359e2  test    eax, eax
0x1801359e4  js      loc_180135A92
0x1801359ea  mov     rcx, [rsp+870h+pperrinfo]
0x1801359ef  mov     rdx, r15
0x1801359f2  mov     [rsp+870h+perrinfo], 0
0x1801359fb  mov     rax, [rcx]
0x1801359fe  mov     rax, [rax+18h]
0x180135a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a07  lea     rdx, [rsp+870h+lpszProgID]; lplpszProgID
0x180135a0c  mov     [rsp+870h+lpszProgID], 0
0x180135a15  mov     rcx, r14; clsid
0x180135a18  call    cs:__imp_ProgIDFromCLSID
0x180135a1e  mov     rdx, [rsp+870h+lpszProgID]
0x180135a23  test    rdx, rdx
0x180135a26  jz      short loc_180135A3E
0x180135a28  mov     rcx, [rsp+870h+pperrinfo]
0x180135a2d  mov     rax, [rcx]
0x180135a30  mov     rax, [rax+20h]
0x180135a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a39  mov     rdx, [rsp+870h+lpszProgID]
0x180135a3e  mov     rcx, rdx; pv
0x180135a41  call    cs:__imp_CoTaskMemFree
0x180135a47  mov     rcx, [rsp+870h+pperrinfo]
0x180135a4c  mov     rdx, rdi
0x180135a4f  mov     rax, [rcx]
0x180135a52  mov     rax, [rax+28h]
0x180135a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a5b  mov     rcx, [rsp+870h+pperrinfo]
0x180135a60  lea     r8, [rsp+870h+perrinfo]
0x180135a65  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x180135a6c  mov     rax, [rcx]
0x180135a6f  mov     rax, [rax]
0x180135a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a77  test    eax, eax
0x180135a79  js      short loc_180135A88
0x180135a7b  mov     rdx, [rsp+870h+perrinfo]; perrinfo
0x180135a80  xor     ecx, ecx; dwReserved
0x180135a82  call    cs:__imp_SetErrorInfo
0x180135a88  lea     rcx, [rsp+870h+perrinfo]
0x180135a8d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180135a92  mov     eax, 80020009h
0x180135a97  lea     rcx, [rsp+870h+pperrinfo]
0x180135a9c  test    ebx, ebx
0x180135a9e  cmovz   ebx, eax
0x180135aa1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180135aa6  lea     rcx, [rsp+870h+var_838]
0x180135aab  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180135ab0  mov     eax, ebx
0x180135ab2  mov     rcx, [rbp+770h+var_30]
0x180135ab9  xor     rcx, rsp; StackCookie
0x180135abc  call    __security_check_cookie
0x180135ac1  mov     rbx, [rsp+870h+arg_10]
0x180135ac9  add     rsp, 850h
0x180135ad0  pop     r15
0x180135ad2  pop     r14
0x180135ad4  pop     rdi
0x180135ad5  pop     rsi
0x180135ad6  pop     rbp
0x180135ad7  retn
```
