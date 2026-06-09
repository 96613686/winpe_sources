# CWinRTContentLinkInfo::SetData(_smartlinkdata *,HSTRING__ *,std::pair<uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const * const)

- ea: `0x1801e2254`
- end: `0x1801e23b1`
- name: `?SetData@CWinRTContentLinkInfo@@QEAAJPEAU_smartlinkdata@@PEAUHSTRING__@@QEBU?$pair@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801e2b30`

## callees

- `0x180021c38`
- `0x180048d5c`
- `0x1800ce2c4`
- `0x180110888`
- `0x18013bad0`
- `0x1801e2254`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e2316`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e2316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e2299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e22d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e232f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e2299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e22d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801e232f`

## string_xrefs

- `0x1801e22e3`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall CWinRTContentLinkInfo::SetData(HSTRING *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int16 *v5; // rcx
  UINT32 v9; // eax
  int i; // ecx
  const WCHAR *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  UINT32 v14; // eax
  __int64 v15; // rsi
  void (__fastcall *v16)(__int64, HSTRING, HSTRING *); // rdi
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h]

  v5 = *(unsigned __int16 **)(a2 + 32);
  string = 0;
  v9 = CW32System::SysStringLen(v5);
  WindowsCreateString(*(PCNZWCH *)(a2 + 32), v9, a1 + 6);
  for ( i = 0; i < 2; ++i )
  {
    if ( *(_DWORD *)(a4 + 40LL * i) == *(_DWORD *)(a2 + 12) )
    {
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4 + 8 + 40LL * i);
      WindowsCreateString(v11, *(_DWORD *)(a4 + 8 * v12 + 24), a1 + 8);
      break;
    }
  }
  v18 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v13 = v21;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  RoGetActivationFactory(v13, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v18);
  v14 = CW32System::SysStringLen(*(unsigned __int16 **)(a2 + 24));
  WindowsCreateString(*(PCNZWCH *)(a2 + 24), v14, &string);
  v15 = v18;
  v16 = *(void (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v18 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 7);
  v16(v15, string, a1 + 7);
  (*((void (__fastcall **)(HSTRING *, _QWORD))*a1 + 7))(a1, *(unsigned int *)(a2 + 16));
  (*((void (__fastcall **)(HSTRING *, __int64))*a1 + 9))(a1, a3);
  WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1801e2254  push    rbp
0x1801e2256  push    rbx
0x1801e2257  push    rsi
0x1801e2258  push    rdi
0x1801e2259  push    r12
0x1801e225b  push    r14
0x1801e225d  push    r15
0x1801e225f  mov     rbp, rsp
0x1801e2262  sub     rsp, 60h
0x1801e2266  mov     rax, cs:__security_cookie
0x1801e226d  xor     rax, rsp
0x1801e2270  mov     [rbp+var_10], rax
0x1801e2274  mov     r15, rcx
0x1801e2277  xor     edi, edi
0x1801e2279  mov     rcx, [rdx+20h]; unsigned __int16 *
0x1801e227d  mov     rbx, r9
0x1801e2280  mov     [rbp+string], rdi
0x1801e2284  mov     r12, r8
0x1801e2287  mov     r14, rdx
0x1801e228a  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1801e228f  mov     rcx, [r14+20h]; sourceString
0x1801e2293  lea     r8, [r15+30h]; string
0x1801e2297  mov     edx, eax; length
0x1801e2299  call    cs:__imp_WindowsCreateString
0x1801e229f  mov     r8d, [r14+0Ch]
0x1801e22a3  mov     ecx, edi
0x1801e22a5  cmp     ecx, 2
0x1801e22a8  jge     short loc_1801E22D9
0x1801e22aa  movsxd  rax, ecx
0x1801e22ad  lea     rdx, [rax+rax*4]
0x1801e22b1  cmp     [rbx+rdx*8], r8d
0x1801e22b5  jz      short loc_1801E22BB
0x1801e22b7  inc     ecx
0x1801e22b9  jmp     short loc_1801E22A5
0x1801e22bb  lea     rcx, [rbx+8]
0x1801e22bf  lea     rcx, [rcx+rdx*8]
0x1801e22c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801e22c8  mov     edx, [rbx+rdx*8+18h]; length
0x1801e22cc  lea     r8, [r15+40h]; string
0x1801e22d0  mov     rcx, rax; sourceString
0x1801e22d3  call    cs:__imp_WindowsCreateString
0x1801e22d9  mov     r9d, 16h; unsigned int
0x1801e22df  mov     [rbp+var_40], rdi
0x1801e22e3  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1801e22ea  mov     [rbp+var_18], rdi
0x1801e22ee  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e22f2  lea     r8d, [r9+1]; unsigned int
0x1801e22f6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e22fb  mov     rbx, [rbp+var_18]
0x1801e22ff  lea     rcx, [rbp+var_40]
0x1801e2303  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e2308  lea     r8, [rbp+var_40]
0x1801e230c  mov     rcx, rbx
0x1801e230f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1801e2316  call    cs:__imp_RoGetActivationFactory
0x1801e231c  mov     rcx, [r14+18h]; unsigned __int16 *
0x1801e2320  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1801e2325  mov     rcx, [r14+18h]; sourceString
0x1801e2329  lea     r8, [rbp+string]; string
0x1801e232d  mov     edx, eax; length
0x1801e232f  call    cs:__imp_WindowsCreateString
0x1801e2335  mov     rsi, [rbp+var_40]
0x1801e2339  lea     rcx, [r15+38h]
0x1801e233d  mov     rax, [rsi]
0x1801e2340  mov     rdi, [rax+30h]
0x1801e2344  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e2349  mov     rdx, [rbp+string]
0x1801e234d  lea     r8, [r15+38h]
0x1801e2351  mov     rcx, rsi
0x1801e2354  mov     rax, rdi
0x1801e2357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e235c  mov     rax, [r15]
0x1801e235f  mov     rcx, r15
0x1801e2362  mov     edx, [r14+10h]
0x1801e2366  mov     rax, [rax+38h]
0x1801e236a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e236f  mov     rax, [r15]
0x1801e2372  mov     rdx, r12
0x1801e2375  mov     rcx, r15
0x1801e2378  mov     rax, [rax+48h]
0x1801e237c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2381  mov     rcx, [rbp+string]; string
0x1801e2385  call    cs:__imp_WindowsDeleteString
0x1801e238b  lea     rcx, [rbp+var_40]
0x1801e238f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e2394  xor     eax, eax
0x1801e2396  mov     rcx, [rbp+var_10]
0x1801e239a  xor     rcx, rsp; StackCookie
0x1801e239d  call    __security_check_cookie
0x1801e23a2  add     rsp, 60h
0x1801e23a6  pop     r15
0x1801e23a8  pop     r14
0x1801e23aa  pop     r12
0x1801e23ac  pop     rdi
0x1801e23ad  pop     rsi
0x1801e23ae  pop     rbx
0x1801e23af  pop     rbp
0x1801e23b0  retn
```
