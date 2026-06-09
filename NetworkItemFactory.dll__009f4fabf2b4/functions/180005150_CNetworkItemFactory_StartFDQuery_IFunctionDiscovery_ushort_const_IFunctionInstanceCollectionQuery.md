# CNetworkItemFactory::_StartFDQuery(IFunctionDiscovery *,ushort const *,IFunctionInstanceCollectionQuery * *)

- ea: `0x180005150`
- end: `0x1800052be`
- name: `?_StartFDQuery@CNetworkItemFactory@@AEAAJPEAUIFunctionDiscovery@@PEBGPEAPEAUIFunctionInstanceCollectionQuery@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(CNetworkItemFactory *this, struct IFunctionDiscovery *, const unsigned __int16 *, struct IFunctionInstanceCollectionQuery **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005740`

## callees

- `0x180005150`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800051e1`
- `KERNEL32!CompareStringW` at `0x1800051e1`

## string_xrefs

- `0x1800051f8`: `COMClsContext`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_StartFDQuery(
        CNetworkItemFactory *this,
        struct IFunctionDiscovery *a2,
        const unsigned __int16 *a3,
        struct IFunctionInstanceCollectionQuery **a4)
{
  struct IFunctionDiscoveryVtbl *lpVtbl; // rax
  int v8; // ebx
  int v9; // edi
  int v10; // eax
  struct IFunctionInstanceCollectionQuery *v11; // rcx
  struct IFunctionInstanceCollectionQuery *v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  *a4 = 0;
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(struct IFunctionDiscovery *, const unsigned __int16 *, _QWORD, __int64, _QWORD, _QWORD, struct IFunctionInstanceCollectionQuery **))lpVtbl->CreateInstanceCollectionQuery)(
         a2,
         a3,
         0,
         1,
         *((_QWORD *)this + 16),
         0,
         &v13);
  if ( v8 >= 0 )
  {
    v9 = 0;
    if ( CompareStringW(0x7Fu, 0, a3, -1, L"Provider\\Microsoft.Networking.Netbios", -1) == 2 )
    {
      ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *, const wchar_t *, const wchar_t *))v13->lpVtbl->AddQueryConstraint)(
        v13,
        L"COMClsContext",
        L"1");
      ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *, const wchar_t *, const wchar_t *))v13->lpVtbl->AddQueryConstraint)(
        v13,
        L"Properties",
        L"All");
      v9 = 1;
    }
    v14 = 0;
    v10 = ((__int64 (__fastcall *)(struct IFunctionInstanceCollectionQuery *, __int64 *))v13->lpVtbl->Execute)(
            v13,
            &v14);
    v8 = 0;
    if ( v10 != -2147483638 )
      v8 = v10;
    if ( v14 )
      (*(void (**)(void))(*(_QWORD *)v14 + 16LL))();
    if ( v8 < 0 )
    {
      v11 = v13;
    }
    else
    {
      if ( v9 )
        *((_DWORD *)this + 16) = 1;
      ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *))v13->lpVtbl->AddRef)(v13);
      v11 = v13;
      *a4 = v13;
    }
    ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *))v11->lpVtbl->Release)(v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005150  mov     [rsp+arg_10], rbx
0x180005155  mov     [rsp+arg_18], rbp
0x18000515a  push    rsi
0x18000515b  push    rdi
0x18000515c  push    r14
0x18000515e  sub     rsp, 40h
0x180005162  mov     rax, [rdx]
0x180005165  mov     rbp, rcx
0x180005168  mov     rsi, r8
0x18000516b  mov     qword ptr [r9], 0
0x180005172  mov     r11, rdx
0x180005175  mov     [rsp+58h+arg_0], 0
0x18000517e  lea     rcx, [rsp+58h+arg_0]
0x180005183  mov     r14, r9
0x180005186  mov     r10, [rbp+80h]
0x18000518d  mov     r9d, 1
0x180005193  mov     rax, [rax+28h]
0x180005197  xor     r8d, r8d
0x18000519a  mov     [rsp+58h+var_28], rcx
0x18000519f  mov     rdx, rsi
0x1800051a2  mov     qword ptr [rsp+58h+cchCount2], 0
0x1800051ab  mov     rcx, r11
0x1800051ae  mov     [rsp+58h+lpString2], r10
0x1800051b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b8  mov     ebx, eax
0x1800051ba  test    eax, eax
0x1800051bc  js      loc_1800052A9
0x1800051c2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800051c6  lea     rax, aProviderMicros_0; "Provider\\Microsoft.Networking.Netbios"
0x1800051cd  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x1800051d2  xor     edi, edi
0x1800051d4  mov     r8, rsi; lpString1
0x1800051d7  mov     [rsp+58h+lpString2], rax; lpString2
0x1800051dc  xor     edx, edx; dwCmpFlags
0x1800051de  lea     ecx, [rdi+7Fh]; Locale
0x1800051e1  call    cs:__imp_CompareStringW
0x1800051e7  cmp     eax, 2
0x1800051ea  jnz     short loc_18000522F
0x1800051ec  mov     rcx, [rsp+58h+arg_0]
0x1800051f1  lea     r8, a1; "1"
0x1800051f8  lea     rdx, aComclscontext; "COMClsContext"
0x1800051ff  mov     rax, [rcx]
0x180005202  mov     rax, [rax+18h]
0x180005206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000520b  mov     rcx, [rsp+58h+arg_0]
0x180005210  lea     r8, aAll; "All"
0x180005217  lea     rdx, aProperties; "Properties"
0x18000521e  mov     rax, [rcx]
0x180005221  mov     rax, [rax+18h]
0x180005225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522a  mov     edi, 1
0x18000522f  mov     rcx, [rsp+58h+arg_0]
0x180005234  lea     rdx, [rsp+58h+arg_8]
0x180005239  mov     [rsp+58h+arg_8], 0
0x180005242  mov     rax, [rcx]
0x180005245  mov     rax, [rax+28h]
0x180005249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524e  mov     rcx, [rsp+58h+arg_8]
0x180005253  xor     ebx, ebx
0x180005255  cmp     eax, 8000000Ah
0x18000525a  cmovnz  ebx, eax
0x18000525d  test    rcx, rcx
0x180005260  jz      short loc_18000526E
0x180005262  mov     rax, [rcx]
0x180005265  mov     rax, [rax+10h]
0x180005269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526e  test    ebx, ebx
0x180005270  js      short loc_180005298
0x180005272  test    edi, edi
0x180005274  jz      short loc_18000527D
0x180005276  mov     dword ptr [rbp+40h], 1
0x18000527d  mov     rcx, [rsp+58h+arg_0]
0x180005282  mov     rax, [rcx]
0x180005285  mov     rax, [rax+8]
0x180005289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528e  mov     rcx, [rsp+58h+arg_0]
0x180005293  mov     [r14], rcx
0x180005296  jmp     short loc_18000529D
0x180005298  mov     rcx, [rsp+58h+arg_0]
0x18000529d  mov     rax, [rcx]
0x1800052a0  mov     rax, [rax+10h]
0x1800052a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a9  mov     rbp, [rsp+58h+arg_18]
0x1800052ae  mov     eax, ebx
0x1800052b0  mov     rbx, [rsp+58h+arg_10]
0x1800052b5  add     rsp, 40h
0x1800052b9  pop     r14
0x1800052bb  pop     rdi
0x1800052bc  pop     rsi
0x1800052bd  retn
```
