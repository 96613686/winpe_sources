# Microsoft::Resources::Runtime::CMrtUriParser::IsMrtUriReference(ushort const *,bool *,Microsoft::Resources::StringResult *)

- ea: `0x180034528`
- end: `0x18003464a`
- name: `?IsMrtUriReference@CMrtUriParser@Runtime@Resources@Microsoft@@SAJPEBGPEA_NPEAVStringResult@34@@Z`
- size: `290`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, struct Microsoft::Resources::StringResult *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180032b50`
- `0x180035238`
- `0x180072260`
- `0x180074e60`
- `0x1800777a0`

## callees

- `0x180028510`
- `0x180034528`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800345bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800345bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003460d`
- `OLEAUT32!__imp_SysFreeString` at `0x180034616`
- `OLEAUT32!__imp_SysFreeString` at `0x18003460d`
- `OLEAUT32!__imp_SysFreeString` at `0x180034616`
- `OLEAUT32!__imp_SysStringLen` at `0x180034599`
- `OLEAUT32!__imp_SysStringLen` at `0x1800345f7`
- `OLEAUT32!__imp_SysStringLen` at `0x180034599`
- `OLEAUT32!__imp_SysStringLen` at `0x1800345f7`
- `iertutil!CreateUri` at `0x180034554`
- `iertutil!CreateUri` at `0x180034554`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CMrtUriParser::IsMrtUriReference(
        const unsigned __int16 *a1,
        bool *a2,
        struct Microsoft::Resources::StringResult *a3)
{
  WCHAR *v5; // rdi
  OLECHAR *v6; // rbx
  BSTR bstrString[5]; // [rsp+30h] [rbp-28h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  ppURI = 0;
  if ( CreateUri(a1, 0x4B84u, 0, &ppURI) >= 0 )
  {
    pbstr = 0;
    if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &pbstr) >= 0 )
    {
      v5 = pbstr;
      if ( pbstr )
      {
        if ( SysStringLen(pbstr) == 11 && CompareStringOrdinal(v5, -1, L"ms-resource", -1, 1) == 2 )
        {
          bstrString[0] = 0;
          if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetPath)(ppURI, bstrString) >= 0 )
          {
            v6 = bstrString[0];
            if ( bstrString[0] )
            {
              if ( SysStringLen(bstrString[0]) )
              {
                *a2 = 1;
                if ( a3 )
                  DefStringResult_SetCopy(*(_QWORD *)a3, v6);
              }
            }
            SysFreeString(v6);
          }
        }
      }
      SysFreeString(v5);
    }
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  }
  return 0;
}

```

## disassembly

```asm
0x180034528  mov     [rsp+arg_0], rbx
0x18003452d  push    rsi
0x18003452e  push    rdi
0x18003452f  push    r14
0x180034531  sub     rsp, 40h
0x180034535  mov     rsi, r8
0x180034538  mov     byte ptr [rdx], 0
0x18003453b  mov     r14, rdx
0x18003453e  mov     [rsp+58h+ppURI], 0
0x180034547  xor     r8d, r8d; dwReserved
0x18003454a  lea     r9, [rsp+58h+ppURI]; ppURI
0x18003454f  mov     edx, 4B84h; dwFlags
0x180034554  call    cs:__imp_CreateUri
0x18003455a  test    eax, eax
0x18003455c  js      loc_18003462D
0x180034562  mov     rcx, [rsp+58h+ppURI]
0x180034567  lea     rdx, [rsp+58h+pbstr]
0x18003456c  mov     [rsp+58h+pbstr], 0
0x180034575  mov     rax, [rcx]
0x180034578  mov     rax, [rax+98h]
0x18003457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034584  test    eax, eax
0x180034586  js      loc_18003461C
0x18003458c  mov     rdi, [rsp+58h+pbstr]
0x180034591  test    rdi, rdi
0x180034594  jz      short loc_180034613
0x180034596  mov     rcx, rdi; pbstr
0x180034599  call    cs:__imp_SysStringLen
0x18003459f  cmp     eax, 0Bh
0x1800345a2  jnz     short loc_180034613
0x1800345a4  or      edx, 0FFFFFFFFh; cchCount1
0x1800345a7  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800345af  mov     r9d, edx; cchCount2
0x1800345b2  lea     r8, aMsResource_0; "ms-resource"
0x1800345b9  mov     rcx, rdi; lpString1
0x1800345bc  call    cs:__imp_CompareStringOrdinal
0x1800345c2  cmp     eax, 2
0x1800345c5  jnz     short loc_180034613
0x1800345c7  mov     rcx, [rsp+58h+ppURI]
0x1800345cc  lea     rdx, [rsp+58h+bstrString]
0x1800345d1  mov     [rsp+58h+bstrString], 0
0x1800345da  mov     rax, [rcx]
0x1800345dd  mov     rax, [rax+78h]
0x1800345e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345e6  test    eax, eax
0x1800345e8  js      short loc_180034613
0x1800345ea  mov     rbx, [rsp+58h+bstrString]
0x1800345ef  test    rbx, rbx
0x1800345f2  jz      short loc_18003460A
0x1800345f4  mov     rcx, rbx; pbstr
0x1800345f7  call    cs:__imp_SysStringLen
0x1800345fd  test    eax, eax
0x1800345ff  jz      short loc_18003460A
0x180034601  mov     byte ptr [r14], 1
0x180034605  test    rsi, rsi
0x180034608  jnz     short loc_18003463D
0x18003460a  mov     rcx, rbx; bstrString
0x18003460d  call    cs:__imp_SysFreeString
0x180034613  mov     rcx, rdi; bstrString
0x180034616  call    cs:__imp_SysFreeString
0x18003461c  mov     rcx, [rsp+58h+ppURI]
0x180034621  mov     rax, [rcx]
0x180034624  mov     rax, [rax+10h]
0x180034628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003462d  mov     rbx, [rsp+58h+arg_0]
0x180034632  xor     eax, eax
0x180034634  add     rsp, 40h
0x180034638  pop     r14
0x18003463a  pop     rdi
0x18003463b  pop     rsi
0x18003463c  retn
0x18003463d  mov     rcx, [rsi]
0x180034640  mov     rdx, rbx
0x180034643  call    DefStringResult_SetCopy
0x180034648  jmp     short loc_18003460A
```
