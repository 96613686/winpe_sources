# ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)

- ea: `0x1800a38dc`
- end: `0x1800a3a90`
- name: `?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z`
- size: `436`
- prototype: `__int64 __usercall@<rax>(IID *clsid@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const struct _GUID *, int, HINSTANCE)`
- caller_count: `102`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b7c0`
- `0x180011820`
- `0x1800360c4`
- `0x180036270`
- `0x1800a35d0`
- `0x1800a3b50`
- `0x1800a3d20`
- `0x1800a63e0`
- `0x1800a6cfc`
- `0x1800a71ac`
- `0x1800a8d00`
- `0x1800ae7b0`
- `0x1800aed00`
- `0x1800aee70`
- `0x1800b028c`
- `0x1800b15d0`
- `0x1800b2824`
- `0x1800b3bd0`
- `0x1800b48f0`
- `0x1800b4c80`
- `0x1800b4de0`
- `0x1800b5220`
- `0x1800b52d0`
- `0x1800b5500`
- `0x1800b5630`
- `0x1800b5700`
- `0x1800b5910`
- `0x1800b64b0`
- `0x1800b6f90`
- `0x1800b7110`
- `0x1800b7f80`
- `0x1800b82c0`
- `0x1800b8520`
- `0x1800b8c00`
- `0x1800b8ea0`
- `0x1800bd064`
- `0x1800be710`
- `0x1800bf640`
- `0x1800bf790`
- `0x1800bfd10`
- `0x1800c2ea0`
- `0x1800c35c0`
- `0x1800c3c80`
- `0x1800c53c0`
- `0x1800c6a10`
- `0x1800c6db0`
- `0x1800c8480`
- `0x1800c9670`
- `0x1800c98f0`
- `0x1800cb9a0`

## callees

- `0x180001c20`
- `0x18003e480`
- `0x1800a38dc`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800a395f`
- `msvcrt!wcscpy_s` at `0x1800a395f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a3947`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a3947`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800a3a38`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800a3a38`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800a3992`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800a3992`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800a39ce`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800a39ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a39f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a39f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::AtlSetErrorInfo(
        IID *clsid,
        WCHAR *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        unsigned int a6,
        HINSTANCE hInstance)
{
  WCHAR *v7; // rdi
  int v9; // esi
  unsigned int v10; // ebx
  LPOLESTR v11; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpszProgID; // [rsp+28h] [rbp-D8h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = a2;
  v16 = 0;
  Buffer[0] = 0;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v10 = a6;
  }
  else
  {
    v9 = (unsigned __int16)a2;
    if ( !LoadStringW(hInstance, (unsigned __int16)a2, Buffer, 1024) )
      wcscpy_s(Buffer, 0x400u, L"Unknown Error");
    v7 = Buffer;
    v10 = a6;
    if ( !a6 )
      v10 = v9 | 0x80040000;
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
    ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v7);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
      SetErrorInfo(0, perrinfo);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&perrinfo);
  }
  if ( !v10 )
    v10 = -2147352567;
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&pperrinfo);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v16);
  return v10;
}

```

## disassembly

```asm
0x1800a38dc  mov     [rsp-8+arg_10], rbx
0x1800a38e1  push    rbp
0x1800a38e2  push    rsi
0x1800a38e3  push    rdi
0x1800a38e4  push    r14
0x1800a38e6  push    r15
0x1800a38e8  lea     rbp, [rsp-750h]
0x1800a38f0  sub     rsp, 850h
0x1800a38f7  mov     rax, cs:__security_cookie
0x1800a38fe  xor     rax, rsp
0x1800a3901  mov     [rbp+770h+var_30], rax
0x1800a3908  mov     rdi, rdx
0x1800a390b  mov     r14, rcx
0x1800a390e  mov     r15, [rbp+770h+arg_20]
0x1800a3915  mov     rcx, [rbp+770h+hInstance]; hInstance
0x1800a391c  mov     [rsp+870h+var_838], 0
0x1800a3925  xor     eax, eax
0x1800a3927  mov     [rsp+870h+Buffer], ax
0x1800a392c  cmp     rdx, 10000h
0x1800a3933  jnb     short loc_1800A397E
0x1800a3935  movzx   esi, dx
0x1800a3938  mov     ebx, 400h
0x1800a393d  mov     r9d, ebx; cchBufferMax
0x1800a3940  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x1800a3945  mov     edx, esi; uID
0x1800a3947  call    cs:__imp_LoadStringW
0x1800a394d  test    eax, eax
0x1800a394f  jnz     short loc_1800A3965
0x1800a3951  lea     r8, aUnknownError_0; "Unknown Error"
0x1800a3958  mov     edx, ebx; SizeInWords
0x1800a395a  lea     rcx, [rsp+870h+Buffer]; Destination
0x1800a395f  call    cs:__imp_wcscpy_s
0x1800a3965  lea     rdi, [rsp+870h+Buffer]
0x1800a396a  mov     ebx, [rbp+770h+arg_28]
0x1800a3970  test    ebx, ebx
0x1800a3972  jnz     short loc_1800A3984
0x1800a3974  mov     ebx, esi
0x1800a3976  or      ebx, 80040000h
0x1800a397c  jmp     short loc_1800A3984
0x1800a397e  mov     ebx, [rbp+770h+arg_28]
0x1800a3984  mov     [rsp+870h+pperrinfo], 0
0x1800a398d  lea     rcx, [rsp+870h+pperrinfo]; pperrinfo
0x1800a3992  call    cs:__imp_CreateErrorInfo
0x1800a3998  test    eax, eax
0x1800a399a  js      loc_1800A3A49
0x1800a39a0  mov     [rsp+870h+perrinfo], 0
0x1800a39a9  mov     rcx, [rsp+870h+pperrinfo]
0x1800a39ae  mov     rax, [rcx]
0x1800a39b1  mov     rdx, r15
0x1800a39b4  mov     rax, [rax+18h]
0x1800a39b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39bd  mov     [rsp+870h+lpszProgID], 0
0x1800a39c6  lea     rdx, [rsp+870h+lpszProgID]; lplpszProgID
0x1800a39cb  mov     rcx, r14; clsid
0x1800a39ce  call    cs:__imp_ProgIDFromCLSID
0x1800a39d4  mov     rdx, [rsp+870h+lpszProgID]
0x1800a39d9  test    rdx, rdx
0x1800a39dc  jz      short loc_1800A39F4
0x1800a39de  mov     rcx, [rsp+870h+pperrinfo]
0x1800a39e3  mov     rax, [rcx]
0x1800a39e6  mov     rax, [rax+20h]
0x1800a39ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39ef  mov     rdx, [rsp+870h+lpszProgID]
0x1800a39f4  mov     rcx, rdx; pv
0x1800a39f7  call    cs:__imp_CoTaskMemFree
0x1800a39fd  mov     rcx, [rsp+870h+pperrinfo]
0x1800a3a02  mov     rax, [rcx]
0x1800a3a05  mov     rdx, rdi
0x1800a3a08  mov     rax, [rax+28h]
0x1800a3a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a11  mov     rcx, [rsp+870h+pperrinfo]
0x1800a3a16  mov     rax, [rcx]
0x1800a3a19  lea     r8, [rsp+870h+perrinfo]
0x1800a3a1e  lea     rdx, IID_IErrorInfo
0x1800a3a25  mov     rax, [rax]
0x1800a3a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a2d  test    eax, eax
0x1800a3a2f  js      short loc_1800A3A3F
0x1800a3a31  mov     rdx, [rsp+870h+perrinfo]; perrinfo
0x1800a3a36  xor     ecx, ecx; dwReserved
0x1800a3a38  call    cs:__imp_SetErrorInfo
0x1800a3a3e  nop
0x1800a3a3f  lea     rcx, [rsp+870h+perrinfo]; void *
0x1800a3a44  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a3a49  mov     eax, 80020009h
0x1800a3a4e  test    ebx, ebx
0x1800a3a50  cmovz   ebx, eax
0x1800a3a53  lea     rcx, [rsp+870h+pperrinfo]; void *
0x1800a3a58  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a3a5d  nop
0x1800a3a5e  lea     rcx, [rsp+870h+var_838]
0x1800a3a63  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800a3a68  mov     eax, ebx
0x1800a3a6a  mov     rcx, [rbp+770h+var_30]
0x1800a3a71  xor     rcx, rsp; StackCookie
0x1800a3a74  call    __security_check_cookie
0x1800a3a79  mov     rbx, [rsp+870h+arg_10]
0x1800a3a81  add     rsp, 850h
0x1800a3a88  pop     r15
0x1800a3a8a  pop     r14
0x1800a3a8c  pop     rdi
0x1800a3a8d  pop     rsi
0x1800a3a8e  pop     rbp
0x1800a3a8f  retn
```
