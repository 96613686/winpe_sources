# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x140005dc8`
- end: `0x140005efc`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(GUID *this, const unsigned __int16 *, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004210`

## callees

- `0x140003334`
- `0x1400034dc`
- `0x140005dc8`
- `0x140013010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140005ee7`
- `OLEAUT32!__imp_SysFreeString` at `0x140005ee7`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140005eb0`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x140005eb0`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  int v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_14001B2E0;
  for ( i = off_14001B2E8; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_14001B2E8;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_14001B2D8, a2, &bstrString, &v10);
  if ( v7 >= 0 )
  {
    libID = 0;
    v7 = ((__int64 (__fastcall *)(struct ITypeLib *, GUID **))v10->lpVtbl->GetLibAttr)(v10, &libID);
    if ( v7 >= 0 )
    {
      v7 = UnRegisterTypeLib(
             libID,
             *(_WORD *)libID[1].Data4,
             *(_WORD *)&libID[1].Data4[2],
             libID[1].Data1,
             *(SYSKIND *)&libID[1].Data2);
      ((void (__fastcall *)(struct ITypeLib *, GUID *))v10->lpVtbl->ReleaseTLibAttr)(v10, libID);
    }
  }
  if ( v10 )
    ((void (__fastcall *)(struct ITypeLib *))v10->lpVtbl->Release)(v10);
  SysFreeString(bstrString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140005dc8  mov     [rsp-18h+arg_8], rbx
0x140005dcd  mov     [rsp-18h+arg_10], r8
0x140005dd2  mov     [rsp-18h+libID], rcx
0x140005dd7  push    rbp
0x140005dd8  push    rsi
0x140005dd9  push    rdi
0x140005dda  mov     rbp, rsp
0x140005ddd  sub     rsp, 30h
0x140005de1  xor     ebx, ebx
0x140005de3  mov     rdi, cs:off_14001B2E0
0x140005dea  mov     rax, cs:off_14001B2E8
0x140005df1  cmp     rdi, rax
0x140005df4  jnb     short loc_140005E4C
0x140005df6  mov     rsi, [rdi]
0x140005df9  test    rsi, rsi
0x140005dfc  jz      short loc_140005E3B
0x140005dfe  mov     rax, [rsi+38h]
0x140005e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e07  xor     r8d, r8d; int
0x140005e0a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x140005e0d  mov     rcx, [rsi]; rguid
0x140005e10  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x140005e15  mov     ebx, eax
0x140005e17  test    eax, eax
0x140005e19  js      loc_140005EED
0x140005e1f  xor     ecx, ecx
0x140005e21  mov     rax, [rsi+8]
0x140005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e2a  mov     ebx, eax
0x140005e2c  test    eax, eax
0x140005e2e  js      loc_140005EED
0x140005e34  mov     rax, cs:off_14001B2E8
0x140005e3b  add     rdi, 8
0x140005e3f  cmp     rdi, rax
0x140005e42  jb      short loc_140005DF6
0x140005e44  test    ebx, ebx
0x140005e46  js      loc_140005EED
0x140005e4c  mov     [rbp+bstrString], 0
0x140005e54  mov     [rbp+arg_10], 0
0x140005e5c  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x140005e60  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140005e64  mov     rcx, cs:off_14001B2D8; HINSTANCE
0x140005e6b  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x140005e70  mov     ebx, eax
0x140005e72  test    eax, eax
0x140005e74  js      short loc_140005ECD
0x140005e76  mov     [rbp+libID], 0
0x140005e7e  mov     rcx, [rbp+arg_10]
0x140005e82  mov     rax, [rcx]
0x140005e85  lea     rdx, [rbp+libID]
0x140005e89  mov     rax, [rax+38h]
0x140005e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e92  mov     ebx, eax
0x140005e94  test    eax, eax
0x140005e96  js      short loc_140005ECD
0x140005e98  mov     rcx, [rbp+libID]; libID
0x140005e9c  mov     eax, [rcx+14h]
0x140005e9f  mov     [rsp+30h+syskind], eax; syskind
0x140005ea3  mov     r9d, [rcx+10h]; lcid
0x140005ea7  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x140005eac  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x140005eb0  call    cs:__imp_UnRegisterTypeLib
0x140005eb6  mov     ebx, eax
0x140005eb8  mov     rcx, [rbp+arg_10]
0x140005ebc  mov     rax, [rcx]
0x140005ebf  mov     rdx, [rbp+libID]
0x140005ec3  mov     rax, [rax+60h]
0x140005ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ecc  nop
0x140005ecd  mov     rcx, [rbp+arg_10]
0x140005ed1  test    rcx, rcx
0x140005ed4  jz      short loc_140005EE3
0x140005ed6  mov     rax, [rcx]
0x140005ed9  mov     rax, [rax+10h]
0x140005edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ee2  nop
0x140005ee3  mov     rcx, [rbp+bstrString]; bstrString
0x140005ee7  call    cs:__imp_SysFreeString
0x140005eed  mov     eax, ebx
0x140005eef  mov     rbx, [rsp+30h+arg_8]
0x140005ef4  add     rsp, 30h
0x140005ef8  pop     rdi
0x140005ef9  pop     rsi
0x140005efa  pop     rbp
0x140005efb  retn
```
