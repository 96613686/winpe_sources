# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180004a74`
- end: `0x180004ba6`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800050a0`

## callees

- `0x180002d14`
- `0x180002ebc`
- `0x180004a74`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004b91`
- `OLEAUT32!__imp_SysFreeString` at `0x180004b91`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180004b5c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180004b5c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v3; // rdi
  __int64 *v4; // rax
  __int64 v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_18000B0B0;
  v4 = (__int64 *)off_18000B0B8;
  if ( off_18000B0B0 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18000B0B8 )
  {
    do
    {
      v5 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v7 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v4 = (__int64 *)off_18000B0B8;
      }
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v3 + 8);
    }
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 );
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18000B0A8, a2, &bstrString, &v10);
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
0x180004a74  mov     [rsp-18h+arg_8], rbx
0x180004a79  mov     [rsp-18h+arg_10], r8
0x180004a7e  mov     [rsp-18h+libID], rcx
0x180004a83  push    rbp
0x180004a84  push    rsi
0x180004a85  push    rdi
0x180004a86  mov     rbp, rsp
0x180004a89  sub     rsp, 30h
0x180004a8d  mov     rdi, cs:off_18000B0B0
0x180004a94  xor     ebx, ebx
0x180004a96  mov     rax, cs:off_18000B0B8
0x180004a9d  cmp     rdi, rax
0x180004aa0  jnb     short loc_180004AF8
0x180004aa2  mov     rsi, [rdi]
0x180004aa5  test    rsi, rsi
0x180004aa8  jz      short loc_180004AE7
0x180004aaa  mov     rax, [rsi+38h]
0x180004aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab3  mov     rcx, [rsi]; rguid
0x180004ab6  xor     r8d, r8d; int
0x180004ab9  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180004abc  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180004ac1  mov     ebx, eax
0x180004ac3  test    eax, eax
0x180004ac5  js      loc_180004B97
0x180004acb  mov     rax, [rsi+8]
0x180004acf  xor     ecx, ecx
0x180004ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad6  mov     ebx, eax
0x180004ad8  test    eax, eax
0x180004ada  js      loc_180004B97
0x180004ae0  mov     rax, cs:off_18000B0B8
0x180004ae7  add     rdi, 8
0x180004aeb  cmp     rdi, rax
0x180004aee  jb      short loc_180004AA2
0x180004af0  test    ebx, ebx
0x180004af2  js      loc_180004B97
0x180004af8  mov     rcx, cs:off_18000B0A8; HINSTANCE
0x180004aff  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x180004b03  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180004b07  mov     [rbp+bstrString], 0
0x180004b0f  mov     [rbp+arg_10], 0
0x180004b17  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x180004b1c  mov     ebx, eax
0x180004b1e  test    eax, eax
0x180004b20  js      short loc_180004B78
0x180004b22  mov     rcx, [rbp+arg_10]
0x180004b26  lea     rdx, [rbp+libID]
0x180004b2a  mov     [rbp+libID], 0
0x180004b32  mov     rax, [rcx]
0x180004b35  mov     rax, [rax+38h]
0x180004b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3e  mov     ebx, eax
0x180004b40  test    eax, eax
0x180004b42  js      short loc_180004B78
0x180004b44  mov     rcx, [rbp+libID]; libID
0x180004b48  mov     eax, [rcx+14h]
0x180004b4b  mov     r9d, [rcx+10h]; lcid
0x180004b4f  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180004b54  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x180004b58  mov     [rsp+30h+syskind], eax; syskind
0x180004b5c  call    cs:__imp_UnRegisterTypeLib
0x180004b62  mov     rcx, [rbp+arg_10]
0x180004b66  mov     ebx, eax
0x180004b68  mov     rdx, [rbp+libID]
0x180004b6c  mov     rax, [rcx]
0x180004b6f  mov     rax, [rax+60h]
0x180004b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b78  mov     rcx, [rbp+arg_10]
0x180004b7c  test    rcx, rcx
0x180004b7f  jz      short loc_180004B8D
0x180004b81  mov     rax, [rcx]
0x180004b84  mov     rax, [rax+10h]
0x180004b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8d  mov     rcx, [rbp+bstrString]; bstrString
0x180004b91  call    cs:__imp_SysFreeString
0x180004b97  mov     eax, ebx
0x180004b99  mov     rbx, [rsp+30h+arg_8]
0x180004b9e  add     rsp, 30h
0x180004ba2  pop     rdi
0x180004ba3  pop     rsi
0x180004ba4  pop     rbp
0x180004ba5  retn
```
