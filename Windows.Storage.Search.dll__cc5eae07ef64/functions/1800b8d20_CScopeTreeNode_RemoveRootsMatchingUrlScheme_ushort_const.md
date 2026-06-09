# CScopeTreeNode::RemoveRootsMatchingUrlScheme(ushort const *)

- ea: `0x1800b8d20`
- end: `0x1800b8e40`
- name: `?RemoveRootsMatchingUrlScheme@CScopeTreeNode@@QEAAJPEBG@Z`
- size: `288`
- prototype: `int(CScopeTreeNode *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b8ca0`

## callees

- `0x180011ce0`
- `0x180046200`
- `0x180047ae0`
- `0x18004c220`
- `0x1800b8d20`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8e1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8e1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800b8de0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800b8de0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8e04`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b8e04`
- `urlmon!CreateUri` at `0x1800b8d9e`
- `urlmon!CreateUri` at `0x1800b8d9e`

## pseudocode

```c
__int64 __fastcall CScopeTreeNode::RemoveRootsMatchingUrlScheme(CScopeTreeNode *this, const unsigned __int16 *a2)
{
  _DWORD *v2; // rbx
  unsigned int v5; // edi
  int i; // ebx
  const struct _ITEMIDLIST_RELATIVE **Ptr; // rax
  CScopeTreeNode *v8; // r14
  const WCHAR *v9; // rdx
  LPCWSTR pszStr2; // [rsp+50h] [rbp+30h] BYREF
  IUri *ppURI; // [rsp+60h] [rbp+40h] BYREF
  LPCWSTR pwzURI; // [rsp+68h] [rbp+48h] BYREF

  v2 = (_DWORD *)*((_QWORD *)this + 3);
  v5 = 1;
  if ( v2 )
  {
    for ( i = *v2 - 1; i >= 0; --i )
    {
      Ptr = (const struct _ITEMIDLIST_RELATIVE **)g_pfn_DPA_GetPtr(*((HDPA *)this + 3), (unsigned int)i);
      pwzURI = 0;
      v8 = (CScopeTreeNode *)Ptr;
      if ( DisplayNameOfAsString(0, Ptr[2], 0x8000u, (unsigned __int16 **)&pwzURI) >= 0 )
      {
        ppURI = 0;
        if ( CreateUri(pwzURI, 0, 0, &ppURI) >= 0 )
        {
          pszStr2 = 0;
          if ( ((int (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &pszStr2) >= 0 )
          {
            v9 = &pszFormat;
            if ( pszStr2 )
              v9 = pszStr2;
            if ( !StrCmpICW(a2, v9) )
            {
              g_pfn_DPA_DeletePtr(*((HDPA *)this + 3), i);
              CScopeTreeNode::Release(v8);
              v5 = 0;
            }
            SysFreeString((BSTR)pszStr2);
          }
          ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        }
        CoTaskMemFree((LPVOID)pwzURI);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800b8d20  mov     [rsp-28h+arg_8], rbx
0x1800b8d25  push    rbp
0x1800b8d26  push    rsi
0x1800b8d27  push    rdi
0x1800b8d28  push    r14
0x1800b8d2a  push    r15
0x1800b8d2c  mov     rbp, rsp
0x1800b8d2f  sub     rsp, 20h
0x1800b8d33  mov     rbx, [rcx+18h]
0x1800b8d37  mov     r15, rdx
0x1800b8d3a  mov     rsi, rcx
0x1800b8d3d  mov     edi, 1
0x1800b8d42  test    rbx, rbx
0x1800b8d45  jz      loc_1800B8E2D
0x1800b8d4b  mov     ebx, [rbx]
0x1800b8d4d  sub     ebx, edi
0x1800b8d4f  js      loc_1800B8E2D
0x1800b8d55  mov     rcx, [rsi+18h]; hdpa
0x1800b8d59  mov     edx, ebx; i
0x1800b8d5b  call    cs:g_pfn_DPA_GetPtr
0x1800b8d61  mov     [rbp+pwzURI], 0
0x1800b8d69  lea     r9, [rbp+pwzURI]; unsigned __int16 **
0x1800b8d6d  mov     r8d, 8000h; unsigned int
0x1800b8d73  xor     ecx, ecx; struct IShellFolder *
0x1800b8d75  mov     r14, rax
0x1800b8d78  mov     rdx, [rax+10h]; struct _ITEMIDLIST_RELATIVE *
0x1800b8d7c  call    ?DisplayNameOfAsString@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@KPEAPEAG@Z; DisplayNameOfAsString(IShellFolder *,_ITEMIDLIST_RELATIVE const *,ulong,ushort * *)
0x1800b8d81  test    eax, eax
0x1800b8d83  js      loc_1800B8E24
0x1800b8d89  mov     rcx, [rbp+pwzURI]; pwzURI
0x1800b8d8d  lea     r9, [rbp+ppURI]; ppURI
0x1800b8d91  xor     r8d, r8d; dwReserved
0x1800b8d94  mov     [rbp+ppURI], 0
0x1800b8d9c  xor     edx, edx; dwFlags
0x1800b8d9e  call    cs:__imp_CreateUri
0x1800b8da4  test    eax, eax
0x1800b8da6  js      short loc_1800B8E1A
0x1800b8da8  mov     rcx, [rbp+ppURI]
0x1800b8dac  lea     rdx, [rbp+pszStr2]
0x1800b8db0  mov     [rbp+pszStr2], 0
0x1800b8db8  mov     rax, [rcx]
0x1800b8dbb  mov     rax, [rax+98h]
0x1800b8dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8dc7  test    eax, eax
0x1800b8dc9  js      short loc_1800B8E0A
0x1800b8dcb  mov     rax, [rbp+pszStr2]
0x1800b8dcf  lea     rdx, pszFormat
0x1800b8dd6  test    rax, rax
0x1800b8dd9  mov     rcx, r15; pszStr1
0x1800b8ddc  cmovnz  rdx, rax; pszStr2
0x1800b8de0  call    cs:__imp_StrCmpICW
0x1800b8de6  test    eax, eax
0x1800b8de8  jnz     short loc_1800B8E00
0x1800b8dea  mov     rcx, [rsi+18h]; hdpa
0x1800b8dee  mov     edx, ebx; i
0x1800b8df0  call    cs:g_pfn_DPA_DeletePtr
0x1800b8df6  mov     rcx, r14; this
0x1800b8df9  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x1800b8dfe  xor     edi, edi
0x1800b8e00  mov     rcx, [rbp+pszStr2]; bstrString
0x1800b8e04  call    cs:__imp_SysFreeString
0x1800b8e0a  mov     rcx, [rbp+ppURI]
0x1800b8e0e  mov     rax, [rcx]
0x1800b8e11  mov     rax, [rax+10h]
0x1800b8e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e1a  mov     rcx, [rbp+pwzURI]; pv
0x1800b8e1e  call    cs:__imp_CoTaskMemFree
0x1800b8e24  sub     ebx, 1
0x1800b8e27  jns     loc_1800B8D55
0x1800b8e2d  mov     rbx, [rsp+20h+arg_8]
0x1800b8e32  mov     eax, edi
0x1800b8e34  add     rsp, 20h
0x1800b8e38  pop     r15
0x1800b8e3a  pop     r14
0x1800b8e3c  pop     rdi
0x1800b8e3d  pop     rsi
0x1800b8e3e  pop     rbp
0x1800b8e3f  retn
```
