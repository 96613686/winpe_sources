# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180009b74`
- end: `0x180009ca8`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009f30`

## callees

- `0x180009250`
- `0x1800093f8`
- `0x180009b74`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009c93`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c93`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180009c5c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180009c5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v3 = off_18001B110;
  v4 = (__int64 *)off_18001B118;
  if ( off_18001B110 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18001B118 )
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
        v4 = (__int64 *)off_18001B118;
      }
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v3 + 8);
    }
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 );
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18001B108, a2, &bstrString, &v10);
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
0x180009b74  mov     [rsp-18h+arg_8], rbx
0x180009b79  mov     [rsp-18h+arg_10], r8
0x180009b7e  mov     [rsp-18h+libID], rcx
0x180009b83  push    rbp
0x180009b84  push    rsi
0x180009b85  push    rdi
0x180009b86  mov     rbp, rsp
0x180009b89  sub     rsp, 30h
0x180009b8d  xor     ebx, ebx
0x180009b8f  mov     rdi, cs:off_18001B110
0x180009b96  mov     rax, cs:off_18001B118
0x180009b9d  cmp     rdi, rax
0x180009ba0  jnb     short loc_180009BF8
0x180009ba2  mov     rsi, [rdi]
0x180009ba5  test    rsi, rsi
0x180009ba8  jz      short loc_180009BE7
0x180009baa  mov     rax, [rsi+38h]
0x180009bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb3  xor     r8d, r8d; int
0x180009bb6  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009bb9  mov     rcx, [rsi]; rguid
0x180009bbc  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009bc1  mov     ebx, eax
0x180009bc3  test    eax, eax
0x180009bc5  js      loc_180009C99
0x180009bcb  xor     ecx, ecx
0x180009bcd  mov     rax, [rsi+8]
0x180009bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd6  mov     ebx, eax
0x180009bd8  test    eax, eax
0x180009bda  js      loc_180009C99
0x180009be0  mov     rax, cs:off_18001B118
0x180009be7  add     rdi, 8
0x180009beb  cmp     rdi, rax
0x180009bee  jb      short loc_180009BA2
0x180009bf0  test    ebx, ebx
0x180009bf2  js      loc_180009C99
0x180009bf8  mov     [rbp+bstrString], 0
0x180009c00  mov     [rbp+arg_10], 0
0x180009c08  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x180009c0c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180009c10  mov     rcx, cs:off_18001B108; HINSTANCE
0x180009c17  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x180009c1c  mov     ebx, eax
0x180009c1e  test    eax, eax
0x180009c20  js      short loc_180009C79
0x180009c22  mov     [rbp+libID], 0
0x180009c2a  mov     rcx, [rbp+arg_10]
0x180009c2e  mov     rax, [rcx]
0x180009c31  lea     rdx, [rbp+libID]
0x180009c35  mov     rax, [rax+38h]
0x180009c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3e  mov     ebx, eax
0x180009c40  test    eax, eax
0x180009c42  js      short loc_180009C79
0x180009c44  mov     rcx, [rbp+libID]; libID
0x180009c48  mov     eax, [rcx+14h]
0x180009c4b  mov     [rsp+30h+syskind], eax; syskind
0x180009c4f  mov     r9d, [rcx+10h]; lcid
0x180009c53  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180009c58  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x180009c5c  call    cs:__imp_UnRegisterTypeLib
0x180009c62  mov     ebx, eax
0x180009c64  mov     rcx, [rbp+arg_10]
0x180009c68  mov     rax, [rcx]
0x180009c6b  mov     rdx, [rbp+libID]
0x180009c6f  mov     rax, [rax+60h]
0x180009c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c78  nop
0x180009c79  mov     rcx, [rbp+arg_10]
0x180009c7d  test    rcx, rcx
0x180009c80  jz      short loc_180009C8F
0x180009c82  mov     rax, [rcx]
0x180009c85  mov     rax, [rax+10h]
0x180009c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c8e  nop
0x180009c8f  mov     rcx, [rbp+bstrString]; bstrString
0x180009c93  call    cs:__imp_SysFreeString
0x180009c99  mov     eax, ebx
0x180009c9b  mov     rbx, [rsp+30h+arg_8]
0x180009ca0  add     rsp, 30h
0x180009ca4  pop     rdi
0x180009ca5  pop     rsi
0x180009ca6  pop     rbp
0x180009ca7  retn
```
