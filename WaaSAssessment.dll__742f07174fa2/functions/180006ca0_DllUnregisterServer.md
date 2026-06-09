# DllUnregisterServer

- ea: `0x180006ca0`
- end: `0x180006d09`
- name: `DllUnregisterServer`
- size: `105`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004098`
- `0x180006234`
- `0x180006ca0`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllUnregisterServer()
{
  const unsigned __int16 *v0; // rdx
  GUID *v1; // rcx
  struct ITypeLib *v2; // r8
  __int64 v3; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax
  HRESULT result; // eax

  v3 = qword_180027D28;
  if ( qword_180027D28 )
  {
    while ( *(_QWORD *)v3 )
    {
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 0);
      if ( result < 0 )
        return result;
      result = (*(__int64 (__fastcall **)(_QWORD))(v3 + 8))(0);
      if ( result < 0 )
        return result;
      v3 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc )
    return ATL::CAtlComModule::UnregisterServer(v1, v0, v2);
  result = ATL::_pPerfUnRegFunc();
  if ( result >= 0 )
    return ATL::CAtlComModule::UnregisterServer(v1, v0, v2);
  return result;
}

```

## disassembly

```asm
0x180006ca0  push    rbx
0x180006ca2  sub     rsp, 20h
0x180006ca6  mov     rbx, cs:qword_180027D28
0x180006cad  test    rbx, rbx
0x180006cb0  jz      short loc_180006CE8
0x180006cb2  jmp     short loc_180006CE2
0x180006cb4  mov     rax, [rbx+38h]
0x180006cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbd  xor     r8d, r8d; int
0x180006cc0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006cc3  mov     rcx, [rbx]; rguid
0x180006cc6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006ccb  test    eax, eax
0x180006ccd  js      short loc_180006D03
0x180006ccf  xor     ecx, ecx
0x180006cd1  mov     rax, [rbx+8]
0x180006cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cda  test    eax, eax
0x180006cdc  js      short loc_180006D03
0x180006cde  add     rbx, 48h ; 'H'
0x180006ce2  cmp     qword ptr [rbx], 0
0x180006ce6  jnz     short loc_180006CB4
0x180006ce8  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180006cef  test    rax, rax
0x180006cf2  jz      short loc_180006CFD
0x180006cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf9  test    eax, eax
0x180006cfb  js      short loc_180006D03
0x180006cfd  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180006d02  nop
0x180006d03  add     rsp, 20h
0x180006d07  pop     rbx
0x180006d08  retn
```
