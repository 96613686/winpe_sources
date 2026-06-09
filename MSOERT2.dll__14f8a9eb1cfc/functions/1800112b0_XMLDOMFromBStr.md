# XMLDOMFromBStr

- ea: `0x1800112b0`
- end: `0x180011478`
- name: `XMLDOMFromBStr`
- size: `456`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800112b0`
- `0x180014010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180011304`
- `KERNEL32!CompareStringW` at `0x180011304`
- `ole32!CoCreateInstance` at `0x18001132c`
- `ole32!CoCreateInstance` at `0x18001132c`
- `OLEAUT32!__imp_SysFreeString` at `0x180011419`
- `OLEAUT32!__imp_SysFreeString` at `0x180011419`

## string_xrefs

- `0x1800112e4`: `<?xml`

## pseudocode

```c
__int64 __fastcall XMLDOMFromBStr(PCNZWCH lpString1, LPVOID *ppv)
{
  HRESULT Instance; // edi
  LPVOID v5; // rcx
  LPVOID v6; // rcx
  __int64 v7; // rcx
  LPVOID v8; // rcx
  int v10; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  __int16 v14; // [rsp+70h] [rbp+20h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  if ( lpString1 && ppv )
  {
    *ppv = 0;
    Instance = -2147467259;
    if ( CompareStringW(0x7Fu, 1u, lpString1, 5, L"<?xml", 5) == 2 )
    {
      Instance = CoCreateInstance(&CLSID_DOMDocument2, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, ppv);
      if ( Instance >= 0 )
      {
        v5 = *ppv;
        v14 = 0;
        Instance = (*(__int64 (__fastcall **)(LPVOID, PCNZWCH, __int16 *))(*(_QWORD *)v5 + 520LL))(v5, lpString1, &v14);
        if ( Instance < 0 )
        {
LABEL_8:
          v6 = *ppv;
          v12 = 0;
          if ( (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v6 + 480LL))(v6, &v12) >= 0 )
          {
            v15 = -1;
            v16 = -1;
            v10 = -1;
            v11 = -1;
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 56LL))(v12, &v15);
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 104LL))(v12, &v16);
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 88LL))(v12, &v10);
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 96LL))(v12, &v11);
            bstrString[0] = 0;
            if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 72LL))(v12, bstrString) >= 0 )
              SysFreeString(bstrString[0]);
            v7 = v12;
            if ( v12 )
            {
              v12 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
          }
          v8 = *ppv;
          if ( *ppv )
          {
            *ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
          }
          *ppv = 0;
          return (unsigned int)Instance;
        }
        if ( v14 != -1 )
        {
          Instance = -2147467259;
          goto LABEL_8;
        }
      }
    }
    return (unsigned int)Instance;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800112b0  mov     [rsp-18h+arg_8], rbx
0x1800112b5  push    rbp
0x1800112b6  push    rsi
0x1800112b7  push    rdi
0x1800112b8  mov     rbp, rsp
0x1800112bb  sub     rsp, 50h
0x1800112bf  mov     rbx, rdx
0x1800112c2  mov     rsi, rcx
0x1800112c5  test    rcx, rcx
0x1800112c8  jz      loc_180011466
0x1800112ce  test    rdx, rdx
0x1800112d1  jz      loc_180011466
0x1800112d7  mov     r9d, 5; cchCount1
0x1800112dd  mov     qword ptr [rdx], 0
0x1800112e4  lea     rax, aXml; "<?xml"
0x1800112eb  mov     [rsp+50h+cchCount2], r9d; cchCount2
0x1800112f0  mov     r8, rcx; lpString1
0x1800112f3  mov     [rsp+50h+lpString2], rax; lpString2
0x1800112f8  mov     edi, 80004005h
0x1800112fd  lea     edx, [r9-4]; dwCmpFlags
0x180011301  lea     ecx, [rdx+7Eh]; Locale
0x180011304  call    cs:__imp_CompareStringW
0x18001130a  cmp     eax, 2
0x18001130d  jnz     loc_180011462
0x180011313  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18001131a  mov     [rsp+50h+lpString2], rbx; ppv
0x18001131f  xor     edx, edx; pUnkOuter
0x180011321  lea     r8d, [rax-1]; dwClsContext
0x180011325  lea     rcx, CLSID_DOMDocument2; rclsid
0x18001132c  call    cs:__imp_CoCreateInstance
0x180011332  mov     edi, eax
0x180011334  test    eax, eax
0x180011336  js      loc_180011462
0x18001133c  mov     rcx, [rbx]
0x18001133f  lea     r8, [rbp+arg_0]
0x180011343  xor     eax, eax
0x180011345  mov     rdx, rsi
0x180011348  mov     [rbp+arg_0], ax
0x18001134c  mov     rax, [rcx]
0x18001134f  mov     rax, [rax+208h]
0x180011356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001135b  or      esi, 0FFFFFFFFh
0x18001135e  mov     edi, eax
0x180011360  test    eax, eax
0x180011362  js      short loc_180011373
0x180011364  cmp     si, [rbp+arg_0]
0x180011368  jz      loc_180011462
0x18001136e  mov     edi, 80004005h
0x180011373  mov     rcx, [rbx]
0x180011376  lea     rdx, [rbp+var_18]
0x18001137a  mov     [rbp+var_18], 0
0x180011382  mov     rax, [rcx]
0x180011385  mov     rax, [rax+1E0h]
0x18001138c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011391  test    eax, eax
0x180011393  js      loc_180011440
0x180011399  mov     rcx, [rbp+var_18]
0x18001139d  lea     rdx, [rbp+arg_10]
0x1800113a1  mov     [rbp+arg_10], esi
0x1800113a4  mov     [rbp+arg_18], esi
0x1800113a7  mov     [rbp+var_20], esi
0x1800113aa  mov     [rbp+var_1C], esi
0x1800113ad  mov     rax, [rcx]
0x1800113b0  mov     rax, [rax+38h]
0x1800113b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b9  mov     rcx, [rbp+var_18]
0x1800113bd  lea     rdx, [rbp+arg_18]
0x1800113c1  mov     rax, [rcx]
0x1800113c4  mov     rax, [rax+68h]
0x1800113c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113cd  mov     rcx, [rbp+var_18]
0x1800113d1  lea     rdx, [rbp+var_20]
0x1800113d5  mov     rax, [rcx]
0x1800113d8  mov     rax, [rax+58h]
0x1800113dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113e1  mov     rcx, [rbp+var_18]
0x1800113e5  lea     rdx, [rbp+var_1C]
0x1800113e9  mov     rax, [rcx]
0x1800113ec  mov     rax, [rax+60h]
0x1800113f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113f5  mov     rcx, [rbp+var_18]
0x1800113f9  lea     rdx, [rbp+bstrString]
0x1800113fd  mov     [rbp+bstrString], 0
0x180011405  mov     rax, [rcx]
0x180011408  mov     rax, [rax+48h]
0x18001140c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011411  test    eax, eax
0x180011413  js      short loc_18001141F
0x180011415  mov     rcx, [rbp+bstrString]; bstrString
0x180011419  call    cs:__imp_SysFreeString
0x18001141f  mov     rcx, [rbp+var_18]
0x180011423  test    rcx, rcx
0x180011426  jz      short loc_18001143C
0x180011428  mov     [rbp+var_18], 0
0x180011430  mov     rax, [rcx]
0x180011433  mov     rax, [rax+10h]
0x180011437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001143c  test    edi, edi
0x18001143e  jns     short loc_180011462
0x180011440  mov     rcx, [rbx]
0x180011443  test    rcx, rcx
0x180011446  jz      short loc_18001145B
0x180011448  mov     qword ptr [rbx], 0
0x18001144f  mov     rax, [rcx]
0x180011452  mov     rax, [rax+10h]
0x180011456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145b  mov     qword ptr [rbx], 0
0x180011462  mov     eax, edi
0x180011464  jmp     short loc_18001146B
0x180011466  mov     eax, 80070057h
0x18001146b  mov     rbx, [rsp+50h+arg_8]
0x180011470  add     rsp, 50h
0x180011474  pop     rdi
0x180011475  pop     rsi
0x180011476  pop     rbp
0x180011477  retn
```
