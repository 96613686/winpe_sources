# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x18000be14`
- end: `0x18000bf50`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(GUID *this, const wchar_t *, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c1f0`

## callees

- `0x18000abac`
- `0x18000ad54`
- `0x18000be14`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000bf3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf3b`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000bf04`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000bf04`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const wchar_t *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+60h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_180025520;
  for ( i = off_180025528; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
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
      i = off_180025528;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_180025518, a2, &bstrString, &v10);
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
0x18000be14  mov     [rsp-18h+arg_10], r8
0x18000be19  mov     [rsp-18h+libID], rcx
0x18000be1e  push    rbp
0x18000be1f  push    rsi
0x18000be20  push    rdi
0x18000be21  mov     rbp, rsp
0x18000be24  sub     rsp, 40h
0x18000be28  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18000be30  mov     [rsp+40h+arg_8], rbx
0x18000be35  xor     ebx, ebx
0x18000be37  mov     rdi, cs:off_180025520
0x18000be3e  mov     rax, cs:off_180025528
0x18000be45  cmp     rdi, rax
0x18000be48  jnb     short loc_18000BEA0
0x18000be4a  mov     rsi, [rdi]
0x18000be4d  test    rsi, rsi
0x18000be50  jz      short loc_18000BE8F
0x18000be52  mov     rax, [rsi+38h]
0x18000be56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5b  xor     r8d, r8d; int
0x18000be5e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000be61  mov     rcx, [rsi]; rguid
0x18000be64  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000be69  mov     ebx, eax
0x18000be6b  test    eax, eax
0x18000be6d  js      loc_18000BF41
0x18000be73  xor     ecx, ecx
0x18000be75  mov     rax, [rsi+8]
0x18000be79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7e  mov     ebx, eax
0x18000be80  test    eax, eax
0x18000be82  js      loc_18000BF41
0x18000be88  mov     rax, cs:off_180025528
0x18000be8f  add     rdi, 8
0x18000be93  cmp     rdi, rax
0x18000be96  jb      short loc_18000BE4A
0x18000be98  test    ebx, ebx
0x18000be9a  js      loc_18000BF41
0x18000bea0  mov     [rbp+bstrString], 0
0x18000bea8  mov     [rbp+arg_10], 0
0x18000beb0  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x18000beb4  lea     r8, [rbp+bstrString]; wchar_t **
0x18000beb8  mov     rcx, cs:off_180025518; HINSTANCE
0x18000bebf  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_WPEAPEA_WPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,wchar_t const *,wchar_t * *,ITypeLib * *)
0x18000bec4  mov     ebx, eax
0x18000bec6  test    eax, eax
0x18000bec8  js      short loc_18000BF21
0x18000beca  mov     [rbp+libID], 0
0x18000bed2  mov     rcx, [rbp+arg_10]
0x18000bed6  mov     rax, [rcx]
0x18000bed9  lea     rdx, [rbp+libID]
0x18000bedd  mov     rax, [rax+38h]
0x18000bee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee6  mov     ebx, eax
0x18000bee8  test    eax, eax
0x18000beea  js      short loc_18000BF21
0x18000beec  mov     rcx, [rbp+libID]; libID
0x18000bef0  mov     eax, [rcx+14h]
0x18000bef3  mov     [rsp+40h+syskind], eax; syskind
0x18000bef7  mov     r9d, [rcx+10h]; lcid
0x18000befb  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x18000bf00  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x18000bf04  call    cs:__imp_UnRegisterTypeLib
0x18000bf0a  mov     ebx, eax
0x18000bf0c  mov     rcx, [rbp+arg_10]
0x18000bf10  mov     rax, [rcx]
0x18000bf13  mov     rdx, [rbp+libID]
0x18000bf17  mov     rax, [rax+60h]
0x18000bf1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf20  nop
0x18000bf21  mov     rcx, [rbp+arg_10]
0x18000bf25  test    rcx, rcx
0x18000bf28  jz      short loc_18000BF37
0x18000bf2a  mov     rax, [rcx]
0x18000bf2d  mov     rax, [rax+10h]
0x18000bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf36  nop
0x18000bf37  mov     rcx, [rbp+bstrString]; bstrString
0x18000bf3b  call    cs:__imp_SysFreeString
0x18000bf41  mov     eax, ebx
0x18000bf43  mov     rbx, [rsp+40h+arg_8]
0x18000bf48  add     rsp, 40h
0x18000bf4c  pop     rdi
0x18000bf4d  pop     rsi
0x18000bf4e  pop     rbp
0x18000bf4f  retn
```
