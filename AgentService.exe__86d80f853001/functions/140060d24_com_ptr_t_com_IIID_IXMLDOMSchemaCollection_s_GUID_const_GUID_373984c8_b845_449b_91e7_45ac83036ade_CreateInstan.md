# _com_ptr_t<_com_IIID<IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::CreateInstance(wchar_t const *,IUnknown *,ulong)

- ea: `0x140060d24`
- end: `0x140060e35`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMSchemaCollection@@$1?_GUID_373984c8_b845_449b_91e7_45ac83036ade@@3U__s_GUID@@B@@@@QEAAJPEB_WPEAUIUnknown@@K@Z`
- size: `273`
- prototype: `__int64 __fastcall(LPVOID *ppv, LPCOLESTR lpszProgID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140063f54`

## callees

- `0x140003e50`
- `0x140060d24`
- `0x14009b010`

## import_xrefs

- `ole32!OleRun` at `0x140060dcc`
- `ole32!OleRun` at `0x140060dcc`
- `ole32!CLSIDFromProgID` at `0x140060d73`
- `ole32!CLSIDFromProgID` at `0x140060d73`
- `ole32!CLSIDFromString` at `0x140060d6b`
- `ole32!CLSIDFromString` at `0x140060d6b`
- `ole32!CoCreateInstance` at `0x140060dbb`
- `ole32!CoCreateInstance` at `0x140060e13`
- `ole32!CoCreateInstance` at `0x140060dbb`
- `ole32!CoCreateInstance` at `0x140060e13`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::CreateInstance(
        LPVOID *ppv,
        LPCOLESTR lpszProgID,
        __int64 a3,
        DWORD a4)
{
  int result; // eax
  HRESULT v7; // ebx
  LPUNKNOWN pUnknown; // [rsp+30h] [rbp-28h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-20h] BYREF

  if ( !lpszProgID )
    return -2147024809;
  pclsid = 0;
  if ( *lpszProgID == 123 )
    result = CLSIDFromString(lpszProgID, &pclsid);
  else
    result = CLSIDFromProgID(lpszProgID, &pclsid);
  if ( result >= 0 )
  {
    if ( *ppv )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
    if ( (a4 & 0x14) == 0 )
      return CoCreateInstance(&pclsid, 0, a4, &GUID_373984c8_b845_449b_91e7_45ac83036ade, ppv);
    pUnknown = 0;
    v7 = CoCreateInstance(&pclsid, 0, a4, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pUnknown);
    if ( v7 >= 0 )
    {
      v7 = OleRun(pUnknown);
      if ( v7 >= 0 )
        v7 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
               pUnknown,
               &GUID_373984c8_b845_449b_91e7_45ac83036ade,
               ppv);
      ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140060d24  mov     [rsp+arg_10], rbx
0x140060d29  push    rdi
0x140060d2a  sub     rsp, 50h
0x140060d2e  mov     rax, cs:__security_cookie
0x140060d35  xor     rax, rsp
0x140060d38  mov     [rsp+58h+var_10], rax
0x140060d3d  mov     ebx, r9d
0x140060d40  mov     rax, rdx
0x140060d43  mov     rdi, rcx
0x140060d46  test    rdx, rdx
0x140060d49  jnz     short loc_140060D55
0x140060d4b  mov     eax, 80070057h
0x140060d50  jmp     loc_140060E1D
0x140060d55  xorps   xmm0, xmm0
0x140060d58  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x140060d5d  mov     rcx, rax; lpszProgID
0x140060d60  cmp     word ptr [rdx], 7Bh ; '{'
0x140060d64  lea     rdx, [rsp+58h+pclsid]; lpclsid
0x140060d69  jnz     short loc_140060D73
0x140060d6b  call    cs:__imp_CLSIDFromString
0x140060d71  jmp     short loc_140060D79
0x140060d73  call    cs:__imp_CLSIDFromProgID
0x140060d79  test    eax, eax
0x140060d7b  js      loc_140060E1D
0x140060d81  mov     rcx, [rdi]
0x140060d84  test    rcx, rcx
0x140060d87  jz      short loc_140060D96
0x140060d89  mov     rax, [rcx]
0x140060d8c  mov     rax, [rax+10h]
0x140060d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060d95  nop
0x140060d96  mov     r8d, ebx; dwClsContext
0x140060d99  xor     edx, edx; pUnkOuter
0x140060d9b  lea     rcx, [rsp+58h+pclsid]; rclsid
0x140060da0  test    bl, 14h
0x140060da3  jz      short loc_140060E07
0x140060da5  mov     [rsp+58h+pUnknown], rdx
0x140060daa  lea     rax, [rsp+58h+pUnknown]
0x140060daf  mov     [rsp+58h+ppv], rax; ppv
0x140060db4  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140060dbb  call    cs:__imp_CoCreateInstance
0x140060dc1  mov     ebx, eax
0x140060dc3  test    eax, eax
0x140060dc5  js      short loc_140060E1B
0x140060dc7  mov     rcx, [rsp+58h+pUnknown]; pUnknown
0x140060dcc  call    cs:__imp_OleRun
0x140060dd2  mov     ebx, eax
0x140060dd4  test    eax, eax
0x140060dd6  js      short loc_140060DF4
0x140060dd8  mov     rcx, [rsp+58h+pUnknown]
0x140060ddd  mov     rax, [rcx]
0x140060de0  mov     r8, rdi
0x140060de3  lea     rdx, _GUID_373984c8_b845_449b_91e7_45ac83036ade
0x140060dea  mov     rax, [rax]
0x140060ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060df2  mov     ebx, eax
0x140060df4  mov     rcx, [rsp+58h+pUnknown]
0x140060df9  mov     rax, [rcx]
0x140060dfc  mov     rax, [rax+10h]
0x140060e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060e05  jmp     short loc_140060E1B
0x140060e07  mov     [rsp+58h+ppv], rdi; ppv
0x140060e0c  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x140060e13  call    cs:__imp_CoCreateInstance
0x140060e19  mov     ebx, eax
0x140060e1b  mov     eax, ebx
0x140060e1d  mov     rcx, [rsp+58h+var_10]
0x140060e22  xor     rcx, rsp; StackCookie
0x140060e25  call    __security_check_cookie
0x140060e2a  mov     rbx, [rsp+58h+arg_10]
0x140060e2f  add     rsp, 50h
0x140060e33  pop     rdi
0x140060e34  retn
```
