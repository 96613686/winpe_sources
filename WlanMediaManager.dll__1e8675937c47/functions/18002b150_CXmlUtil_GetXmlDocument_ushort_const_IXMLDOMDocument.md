# CXmlUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)

- ea: `0x18002b150`
- end: `0x18002b2b2`
- name: `?GetXmlDocument@CXmlUtil@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002abac`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x18002b150`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b18c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b18c`

## string_xrefs

- `0x18002b1cf`: `onecoreuap\private\net\inc\common\utils\XmlUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXmlUtil::GetXmlDocument(const unsigned __int16 *a1, struct IXMLDOMDocument **a2)
{
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  struct IXMLDOMDocument *v10; // rax
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int16 v14; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v15; // [rsp+68h] [rbp+38h] BYREF

  v14 = 0;
  v15 = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &v15);
  v7 = v4;
  if ( v4 >= 0 )
  {
    if ( a1 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 504LL))(v15, 0);
      v7 = v4;
      if ( v4 < 0 )
      {
        v8 = 46;
        goto LABEL_6;
      }
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 544LL))(v15, 0);
      v7 = v4;
      if ( v4 < 0 )
      {
        v8 = 47;
        goto LABEL_6;
      }
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 560LL))(v15, 0);
      v7 = v4;
      if ( v4 < 0 )
      {
        v8 = 48;
        goto LABEL_6;
      }
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 576LL))(v15, 0);
      v7 = v4;
      if ( v4 < 0 )
      {
        v8 = 49;
        goto LABEL_6;
      }
      v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int16 *))(*(_QWORD *)v15 + 520LL))(
             v15,
             a1,
             &v14);
      v7 = v4;
      if ( v4 < 0 )
      {
        v8 = 50;
        goto LABEL_6;
      }
      if ( v14 != -1 )
      {
        v7 = -2147024883;
        v9 = 2147942413LL;
        v8 = 51;
        goto LABEL_7;
      }
    }
    v10 = (struct IXMLDOMDocument *)v15;
    v15 = 0;
    *a2 = v10;
    v7 = 0;
    goto LABEL_19;
  }
  v8 = 42;
LABEL_6:
  v9 = (unsigned int)v4;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\private\\net\\inc\\common\\utils\\XmlUtil.h",
    (const char *)v9,
    ppv);
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15, v5, v6);
  return v7;
}

```

## disassembly

```asm
0x18002b150  mov     [rsp-18h+arg_0], rbx
0x18002b155  push    rbp
0x18002b156  push    rsi
0x18002b157  push    rdi
0x18002b158  mov     rbp, rsp
0x18002b15b  sub     rsp, 30h
0x18002b15f  mov     rsi, rdx
0x18002b162  mov     rdi, rcx
0x18002b165  xor     eax, eax
0x18002b167  mov     [rbp+arg_10], ax
0x18002b16b  mov     [rbp+arg_18], rax
0x18002b16f  lea     rax, [rbp+arg_18]
0x18002b173  mov     qword ptr [rsp+30h+ppv], rax; int
0x18002b178  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18002b17f  xor     edx, edx; pUnkOuter
0x18002b181  lea     r8d, [rdx+1]; dwClsContext
0x18002b185  lea     rcx, CLSID_DOMDocument60; rclsid
0x18002b18c  call    cs:__imp_CoCreateInstance
0x18002b192  mov     ebx, eax
0x18002b194  test    eax, eax
0x18002b196  jns     short loc_18002B19F
0x18002b198  mov     edx, 2Ah ; '*'
0x18002b19d  jmp     short loc_18002B1C8
0x18002b19f  test    rdi, rdi
0x18002b1a2  jz      loc_18002B289
0x18002b1a8  mov     rcx, [rbp+arg_18]
0x18002b1ac  mov     rax, [rcx]
0x18002b1af  xor     edx, edx
0x18002b1b1  mov     rax, [rax+1F8h]
0x18002b1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1bd  mov     ebx, eax
0x18002b1bf  test    eax, eax
0x18002b1c1  jns     short loc_18002B1E0
0x18002b1c3  mov     edx, 2Eh ; '.'; void *
0x18002b1c8  mov     r9d, eax; char *
0x18002b1cb  mov     rcx, [rbp+18h]; this
0x18002b1cf  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x18002b1d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b1db  jmp     loc_18002B29A
0x18002b1e0  mov     rcx, [rbp+arg_18]
0x18002b1e4  mov     rax, [rcx]
0x18002b1e7  xor     edx, edx
0x18002b1e9  mov     rax, [rax+220h]
0x18002b1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1f5  mov     ebx, eax
0x18002b1f7  test    eax, eax
0x18002b1f9  jns     short loc_18002B202
0x18002b1fb  mov     edx, 2Fh ; '/'
0x18002b200  jmp     short loc_18002B1C8
0x18002b202  mov     rcx, [rbp+arg_18]
0x18002b206  mov     rax, [rcx]
0x18002b209  xor     edx, edx
0x18002b20b  mov     rax, [rax+230h]
0x18002b212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b217  mov     ebx, eax
0x18002b219  test    eax, eax
0x18002b21b  jns     short loc_18002B224
0x18002b21d  mov     edx, 30h ; '0'
0x18002b222  jmp     short loc_18002B1C8
0x18002b224  mov     rcx, [rbp+arg_18]
0x18002b228  mov     rax, [rcx]
0x18002b22b  xor     edx, edx
0x18002b22d  mov     rax, [rax+240h]
0x18002b234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b239  mov     ebx, eax
0x18002b23b  test    eax, eax
0x18002b23d  jns     short loc_18002B246
0x18002b23f  mov     edx, 31h ; '1'
0x18002b244  jmp     short loc_18002B1C8
0x18002b246  mov     rcx, [rbp+arg_18]
0x18002b24a  mov     rax, [rcx]
0x18002b24d  lea     r8, [rbp+arg_10]
0x18002b251  mov     rdx, rdi
0x18002b254  mov     rax, [rax+208h]
0x18002b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b260  mov     ebx, eax
0x18002b262  test    eax, eax
0x18002b264  jns     short loc_18002B270
0x18002b266  mov     edx, 32h ; '2'
0x18002b26b  jmp     loc_18002B1C8
0x18002b270  cmp     [rbp+arg_10], 0FFFFh
0x18002b275  jz      short loc_18002B289
0x18002b277  mov     ebx, 8007000Dh
0x18002b27c  mov     r9d, ebx
0x18002b27f  mov     edx, 33h ; '3'
0x18002b284  jmp     loc_18002B1CB
0x18002b289  mov     rax, [rbp+arg_18]
0x18002b28d  mov     [rbp+arg_18], 0
0x18002b295  mov     [rsi], rax
0x18002b298  xor     ebx, ebx
0x18002b29a  lea     rcx, [rbp+arg_18]
0x18002b29e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b2a3  mov     eax, ebx
0x18002b2a5  mov     rbx, [rsp+30h+arg_0]
0x18002b2aa  add     rsp, 30h
0x18002b2ae  pop     rdi
0x18002b2af  pop     rsi
0x18002b2b0  pop     rbp
0x18002b2b1  retn
```
