# _LogDom(IXMLDOMDocument *,ushort const *,int,int)

- ea: `0x18004d0b0`
- end: `0x18004d1c4`
- name: `?_LogDom@@YAXPEAUIXMLDOMDocument@@PEBGHH@Z`
- size: `276`
- prototype: `void __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ca14`

## callees

- `0x180006900`
- `0x18004d0b0`
- `0x18004d348`
- `0x180051010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004d150`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d150`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d187`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d192`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d187`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d192`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18004d0f3`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18004d0f3`

## pseudocode

```c
void __fastcall _LogDom(struct IXMLDOMDocument *a1, const unsigned __int16 *a2)
{
  BSTR v3; // rax
  struct IXMLDOMDocumentVtbl *lpVtbl; // rdx
  OLECHAR *v5; // rbx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+50h] [rbp-B0h]
  OLECHAR psz[264]; // [rsp+60h] [rbp-A0h] BYREF

  ppURI = 0;
  if ( CreateUri(0, 0x3002B80u, 0, &ppURI) >= 0 )
  {
    bstrString = 0;
    if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetHost)(ppURI, &bstrString) >= 0 )
    {
      if ( (unsigned int)s_GetLogPath(bstrString) )
      {
        v8 = 0;
        LOWORD(v8) = 8;
        v3 = SysAllocString(psz);
        lpVtbl = a1->lpVtbl;
        *((_QWORD *)&v8 + 1) = v3;
        v5 = v3;
        v9 = 0;
        ((void (__fastcall *)(struct IXMLDOMDocument *, __int128 *))lpVtbl->save)(a1, &v8);
        SysFreeString(v5);
      }
      SysFreeString(bstrString);
    }
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  }
}

```

## disassembly

```asm
0x18004d0b0  push    rbp
0x18004d0b2  push    rbx
0x18004d0b3  push    rsi
0x18004d0b4  push    rdi
0x18004d0b5  lea     rbp, [rsp-188h]
0x18004d0bd  sub     rsp, 288h
0x18004d0c4  mov     rax, cs:__security_cookie
0x18004d0cb  xor     rax, rsp
0x18004d0ce  mov     [rbp+1A0h+var_30], rax
0x18004d0d5  mov     ebx, r8d
0x18004d0d8  mov     [rsp+2A0h+ppURI], 0
0x18004d0e1  mov     rdi, rcx
0x18004d0e4  lea     r9, [rsp+2A0h+ppURI]; ppURI
0x18004d0e9  xor     r8d, r8d; dwReserved
0x18004d0ec  xor     ecx, ecx; pwzURI
0x18004d0ee  mov     edx, 3002B80h; dwFlags
0x18004d0f3  call    cs:__imp_CreateUri
0x18004d0f9  test    eax, eax
0x18004d0fb  js      loc_18004D1A9
0x18004d101  mov     rcx, [rsp+2A0h+ppURI]
0x18004d106  lea     rdx, [rsp+2A0h+bstrString]
0x18004d10b  mov     [rsp+2A0h+bstrString], 0
0x18004d114  mov     rax, [rcx]
0x18004d117  mov     rax, [rax+68h]
0x18004d11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d120  test    eax, eax
0x18004d122  js      short loc_18004D198
0x18004d124  mov     rcx, [rsp+2A0h+bstrString]; pszMore
0x18004d129  lea     r9, [rsp+2A0h+psz]
0x18004d12e  mov     edx, ebx
0x18004d130  call    s_GetLogPath
0x18004d135  test    eax, eax
0x18004d137  jz      short loc_18004D18D
0x18004d139  xorps   xmm0, xmm0
0x18004d13c  lea     rcx, [rsp+2A0h+psz]; psz
0x18004d141  movups  [rsp+2A0h+var_260], xmm0
0x18004d146  xor     esi, esi
0x18004d148  lea     eax, [rsi+8]
0x18004d14b  mov     word ptr [rsp+2A0h+var_260], ax
0x18004d150  call    cs:__imp_SysAllocString
0x18004d156  mov     rdx, [rdi]
0x18004d159  mov     rcx, rdi
0x18004d15c  mov     qword ptr [rsp+2A0h+var_260+8], rax
0x18004d161  mov     rbx, rax
0x18004d164  movups  xmm0, [rsp+2A0h+var_260]
0x18004d169  mov     [rsp+2A0h+var_250], rsi
0x18004d16e  mov     rax, [rdx+210h]
0x18004d175  lea     rdx, [rsp+2A0h+var_260]
0x18004d17a  movaps  [rsp+2A0h+var_260], xmm0
0x18004d17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d184  mov     rcx, rbx; bstrString
0x18004d187  call    cs:__imp_SysFreeString
0x18004d18d  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x18004d192  call    cs:__imp_SysFreeString
0x18004d198  mov     rcx, [rsp+2A0h+ppURI]
0x18004d19d  mov     rax, [rcx]
0x18004d1a0  mov     rax, [rax+10h]
0x18004d1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1a9  mov     rcx, [rbp+1A0h+var_30]
0x18004d1b0  xor     rcx, rsp; StackCookie
0x18004d1b3  call    __security_check_cookie
0x18004d1b8  add     rsp, 288h
0x18004d1bf  pop     rdi
0x18004d1c0  pop     rsi
0x18004d1c1  pop     rbx
0x18004d1c2  pop     rbp
0x18004d1c3  retn
```
