# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1800173c4`
- end: `0x1800174f8`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017da0`

## callees

- `0x180013230`
- `0x1800133d8`
- `0x1800173c4`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800174e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174e3`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800174ac`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800174ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  __int64 *v3; // rdi
  __int64 *i; // rax
  __int64 v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_18004BA20[0];
  for ( i = off_18004BA28; v3 < i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_18004BA28;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18004BA18, a2, &bstrString, &v10);
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
0x1800173c4  mov     [rsp-18h+arg_8], rbx
0x1800173c9  mov     [rsp-18h+arg_10], r8
0x1800173ce  mov     [rsp-18h+libID], rcx
0x1800173d3  push    rbp
0x1800173d4  push    rsi
0x1800173d5  push    rdi
0x1800173d6  mov     rbp, rsp
0x1800173d9  sub     rsp, 30h
0x1800173dd  xor     ebx, ebx
0x1800173df  mov     rdi, cs:off_18004BA20
0x1800173e6  mov     rax, cs:off_18004BA28
0x1800173ed  cmp     rdi, rax
0x1800173f0  jnb     short loc_180017448
0x1800173f2  mov     rsi, [rdi]
0x1800173f5  test    rsi, rsi
0x1800173f8  jz      short loc_180017437
0x1800173fa  mov     rax, [rsi+38h]
0x1800173fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017403  xor     r8d, r8d; int
0x180017406  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180017409  mov     rcx, [rsi]; rguid
0x18001740c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180017411  mov     ebx, eax
0x180017413  test    eax, eax
0x180017415  js      loc_1800174E9
0x18001741b  xor     ecx, ecx
0x18001741d  mov     rax, [rsi+8]
0x180017421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017426  mov     ebx, eax
0x180017428  test    eax, eax
0x18001742a  js      loc_1800174E9
0x180017430  mov     rax, cs:off_18004BA28
0x180017437  add     rdi, 8
0x18001743b  cmp     rdi, rax
0x18001743e  jb      short loc_1800173F2
0x180017440  test    ebx, ebx
0x180017442  js      loc_1800174E9
0x180017448  mov     [rbp+bstrString], 0
0x180017450  mov     [rbp+arg_10], 0
0x180017458  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x18001745c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180017460  mov     rcx, cs:off_18004BA18; HINSTANCE
0x180017467  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x18001746c  mov     ebx, eax
0x18001746e  test    eax, eax
0x180017470  js      short loc_1800174C9
0x180017472  mov     [rbp+libID], 0
0x18001747a  mov     rcx, [rbp+arg_10]
0x18001747e  mov     rax, [rcx]
0x180017481  lea     rdx, [rbp+libID]
0x180017485  mov     rax, [rax+38h]
0x180017489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001748e  mov     ebx, eax
0x180017490  test    eax, eax
0x180017492  js      short loc_1800174C9
0x180017494  mov     rcx, [rbp+libID]; libID
0x180017498  mov     eax, [rcx+14h]
0x18001749b  mov     [rsp+30h+syskind], eax; syskind
0x18001749f  mov     r9d, [rcx+10h]; lcid
0x1800174a3  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x1800174a8  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x1800174ac  call    cs:__imp_UnRegisterTypeLib
0x1800174b2  mov     ebx, eax
0x1800174b4  mov     rcx, [rbp+arg_10]
0x1800174b8  mov     rax, [rcx]
0x1800174bb  mov     rdx, [rbp+libID]
0x1800174bf  mov     rax, [rax+60h]
0x1800174c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c8  nop
0x1800174c9  mov     rcx, [rbp+arg_10]
0x1800174cd  test    rcx, rcx
0x1800174d0  jz      short loc_1800174DF
0x1800174d2  mov     rax, [rcx]
0x1800174d5  mov     rax, [rax+10h]
0x1800174d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174de  nop
0x1800174df  mov     rcx, [rbp+bstrString]; bstrString
0x1800174e3  call    cs:__imp_SysFreeString
0x1800174e9  mov     eax, ebx
0x1800174eb  mov     rbx, [rsp+30h+arg_8]
0x1800174f0  add     rsp, 30h
0x1800174f4  pop     rdi
0x1800174f5  pop     rsi
0x1800174f6  pop     rbp
0x1800174f7  retn
```
