# _com_ptr_t<_com_IIID<IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(wchar_t const *,IUnknown *,ulong)

- ea: `0x140060c0c`
- end: `0x140060d1d`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJPEB_WPEAUIUnknown@@K@Z`
- size: `273`
- prototype: `__int64 __fastcall(LPVOID *ppv, LPCOLESTR lpszProgID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140063f54`

## callees

- `0x140003e50`
- `0x140060c0c`
- `0x14009b010`

## import_xrefs

- `ole32!OleRun` at `0x140060cb4`
- `ole32!OleRun` at `0x140060cb4`
- `ole32!CLSIDFromProgID` at `0x140060c5b`
- `ole32!CLSIDFromProgID` at `0x140060c5b`
- `ole32!CLSIDFromString` at `0x140060c53`
- `ole32!CLSIDFromString` at `0x140060c53`
- `ole32!CoCreateInstance` at `0x140060ca3`
- `ole32!CoCreateInstance` at `0x140060cfb`
- `ole32!CoCreateInstance` at `0x140060ca3`
- `ole32!CoCreateInstance` at `0x140060cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall _com_ptr_t<_com_IIID<IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(
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
      return CoCreateInstance(&pclsid, 0, a4, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, ppv);
    pUnknown = 0;
    v7 = CoCreateInstance(&pclsid, 0, a4, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pUnknown);
    if ( v7 >= 0 )
    {
      v7 = OleRun(pUnknown);
      if ( v7 >= 0 )
        v7 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
               pUnknown,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
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
0x140060c0c  mov     [rsp+arg_10], rbx
0x140060c11  push    rdi
0x140060c12  sub     rsp, 50h
0x140060c16  mov     rax, cs:__security_cookie
0x140060c1d  xor     rax, rsp
0x140060c20  mov     [rsp+58h+var_10], rax
0x140060c25  mov     ebx, r9d
0x140060c28  mov     rax, rdx
0x140060c2b  mov     rdi, rcx
0x140060c2e  test    rdx, rdx
0x140060c31  jnz     short loc_140060C3D
0x140060c33  mov     eax, 80070057h
0x140060c38  jmp     loc_140060D05
0x140060c3d  xorps   xmm0, xmm0
0x140060c40  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x140060c45  mov     rcx, rax; lpszProgID
0x140060c48  cmp     word ptr [rdx], 7Bh ; '{'
0x140060c4c  lea     rdx, [rsp+58h+pclsid]; lpclsid
0x140060c51  jnz     short loc_140060C5B
0x140060c53  call    cs:__imp_CLSIDFromString
0x140060c59  jmp     short loc_140060C61
0x140060c5b  call    cs:__imp_CLSIDFromProgID
0x140060c61  test    eax, eax
0x140060c63  js      loc_140060D05
0x140060c69  mov     rcx, [rdi]
0x140060c6c  test    rcx, rcx
0x140060c6f  jz      short loc_140060C7E
0x140060c71  mov     rax, [rcx]
0x140060c74  mov     rax, [rax+10h]
0x140060c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060c7d  nop
0x140060c7e  mov     r8d, ebx; dwClsContext
0x140060c81  xor     edx, edx; pUnkOuter
0x140060c83  lea     rcx, [rsp+58h+pclsid]; rclsid
0x140060c88  test    bl, 14h
0x140060c8b  jz      short loc_140060CEF
0x140060c8d  mov     [rsp+58h+pUnknown], rdx
0x140060c92  lea     rax, [rsp+58h+pUnknown]
0x140060c97  mov     [rsp+58h+ppv], rax; ppv
0x140060c9c  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140060ca3  call    cs:__imp_CoCreateInstance
0x140060ca9  mov     ebx, eax
0x140060cab  test    eax, eax
0x140060cad  js      short loc_140060D03
0x140060caf  mov     rcx, [rsp+58h+pUnknown]; pUnknown
0x140060cb4  call    cs:__imp_OleRun
0x140060cba  mov     ebx, eax
0x140060cbc  test    eax, eax
0x140060cbe  js      short loc_140060CDC
0x140060cc0  mov     rcx, [rsp+58h+pUnknown]
0x140060cc5  mov     rax, [rcx]
0x140060cc8  mov     r8, rdi
0x140060ccb  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140060cd2  mov     rax, [rax]
0x140060cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060cda  mov     ebx, eax
0x140060cdc  mov     rcx, [rsp+58h+pUnknown]
0x140060ce1  mov     rax, [rcx]
0x140060ce4  mov     rax, [rax+10h]
0x140060ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060ced  jmp     short loc_140060D03
0x140060cef  mov     [rsp+58h+ppv], rdi; ppv
0x140060cf4  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x140060cfb  call    cs:__imp_CoCreateInstance
0x140060d01  mov     ebx, eax
0x140060d03  mov     eax, ebx
0x140060d05  mov     rcx, [rsp+58h+var_10]
0x140060d0a  xor     rcx, rsp; StackCookie
0x140060d0d  call    __security_check_cookie
0x140060d12  mov     rbx, [rsp+58h+arg_10]
0x140060d17  add     rsp, 50h
0x140060d1b  pop     rdi
0x140060d1c  retn
```
