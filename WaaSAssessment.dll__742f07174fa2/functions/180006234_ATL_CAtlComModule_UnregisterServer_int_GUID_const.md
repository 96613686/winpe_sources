# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180006234`
- end: `0x180006368`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006ca0`

## callees

- `0x180003ef0`
- `0x180004098`
- `0x180006234`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006353`
- `OLEAUT32!__imp_SysFreeString` at `0x180006353`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000631c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000631c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_1800270D0;
  for ( i = off_1800270D8; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
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
      i = off_1800270D8;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_1800270C8, a2, &bstrString, &v10);
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
0x180006234  mov     [rsp-18h+arg_8], rbx
0x180006239  mov     [rsp-18h+arg_10], r8
0x18000623e  mov     [rsp-18h+libID], rcx
0x180006243  push    rbp
0x180006244  push    rsi
0x180006245  push    rdi
0x180006246  mov     rbp, rsp
0x180006249  sub     rsp, 30h
0x18000624d  xor     ebx, ebx
0x18000624f  mov     rdi, cs:off_1800270D0
0x180006256  mov     rax, cs:off_1800270D8
0x18000625d  cmp     rdi, rax
0x180006260  jnb     short loc_1800062B8
0x180006262  mov     rsi, [rdi]
0x180006265  test    rsi, rsi
0x180006268  jz      short loc_1800062A7
0x18000626a  mov     rax, [rsi+38h]
0x18000626e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006273  xor     r8d, r8d; int
0x180006276  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006279  mov     rcx, [rsi]; rguid
0x18000627c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006281  mov     ebx, eax
0x180006283  test    eax, eax
0x180006285  js      loc_180006359
0x18000628b  xor     ecx, ecx
0x18000628d  mov     rax, [rsi+8]
0x180006291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006296  mov     ebx, eax
0x180006298  test    eax, eax
0x18000629a  js      loc_180006359
0x1800062a0  mov     rax, cs:off_1800270D8
0x1800062a7  add     rdi, 8
0x1800062ab  cmp     rdi, rax
0x1800062ae  jb      short loc_180006262
0x1800062b0  test    ebx, ebx
0x1800062b2  js      loc_180006359
0x1800062b8  mov     [rbp+bstrString], 0
0x1800062c0  mov     [rbp+arg_10], 0
0x1800062c8  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x1800062cc  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800062d0  mov     rcx, cs:off_1800270C8; HINSTANCE
0x1800062d7  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x1800062dc  mov     ebx, eax
0x1800062de  test    eax, eax
0x1800062e0  js      short loc_180006339
0x1800062e2  mov     [rbp+libID], 0
0x1800062ea  mov     rcx, [rbp+arg_10]
0x1800062ee  mov     rax, [rcx]
0x1800062f1  lea     rdx, [rbp+libID]
0x1800062f5  mov     rax, [rax+38h]
0x1800062f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fe  mov     ebx, eax
0x180006300  test    eax, eax
0x180006302  js      short loc_180006339
0x180006304  mov     rcx, [rbp+libID]; libID
0x180006308  mov     eax, [rcx+14h]
0x18000630b  mov     [rsp+30h+syskind], eax; syskind
0x18000630f  mov     r9d, [rcx+10h]; lcid
0x180006313  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180006318  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x18000631c  call    cs:__imp_UnRegisterTypeLib
0x180006322  mov     ebx, eax
0x180006324  mov     rcx, [rbp+arg_10]
0x180006328  mov     rax, [rcx]
0x18000632b  mov     rdx, [rbp+libID]
0x18000632f  mov     rax, [rax+60h]
0x180006333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006338  nop
0x180006339  mov     rcx, [rbp+arg_10]
0x18000633d  test    rcx, rcx
0x180006340  jz      short loc_18000634F
0x180006342  mov     rax, [rcx]
0x180006345  mov     rax, [rax+10h]
0x180006349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634e  nop
0x18000634f  mov     rcx, [rbp+bstrString]; bstrString
0x180006353  call    cs:__imp_SysFreeString
0x180006359  mov     eax, ebx
0x18000635b  mov     rbx, [rsp+30h+arg_8]
0x180006360  add     rsp, 30h
0x180006364  pop     rdi
0x180006365  pop     rsi
0x180006366  pop     rbp
0x180006367  retn
```
