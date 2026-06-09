# DllRegisterServer

- ea: `0x180006ba0`
- end: `0x180006c92`
- name: `DllRegisterServer`
- size: `242`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004098`
- `0x18000455c`
- `0x180006ba0`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  v1 = qword_180027D28;
  if ( qword_180027D28 )
  {
    while ( *(_QWORD *)v1 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v1 + 8))(1);
      if ( result < 0 )
        return result;
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v3, 1);
      if ( result < 0 )
        return result;
      v1 += 72;
    }
  }
  v4 = off_1800270D0;
  for ( i = off_1800270D8; v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      result = (*((__int64 (__fastcall **)(__int64))v6 + 1))(1);
      if ( result < 0 )
        return result;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v6 + 7))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
      if ( result < 0 )
        return result;
      i = off_1800270D8;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_1800270C8, v0);
  if ( result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  }
  return result;
}

```

## disassembly

```asm
0x180006ba0  mov     [rsp+arg_0], rbx
0x180006ba5  push    rdi
0x180006ba6  sub     rsp, 20h
0x180006baa  mov     rbx, cs:qword_180027D28
0x180006bb1  test    rbx, rbx
0x180006bb4  jz      short loc_180006BFA
0x180006bb6  jmp     short loc_180006BF4
0x180006bb8  mov     ecx, 1
0x180006bbd  mov     rax, [rbx+8]
0x180006bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc6  test    eax, eax
0x180006bc8  js      loc_180006C87
0x180006bce  mov     rax, [rbx+38h]
0x180006bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd7  mov     r8d, 1; int
0x180006bdd  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006be0  mov     rcx, [rbx]; rguid
0x180006be3  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006be8  test    eax, eax
0x180006bea  js      loc_180006C87
0x180006bf0  add     rbx, 48h ; 'H'
0x180006bf4  cmp     qword ptr [rbx], 0
0x180006bf8  jnz     short loc_180006BB8
0x180006bfa  xor     eax, eax
0x180006bfc  mov     rbx, cs:off_1800270D0
0x180006c03  mov     rcx, cs:off_1800270D8
0x180006c0a  cmp     rbx, rcx
0x180006c0d  jnb     short loc_180006C5B
0x180006c0f  mov     rdi, [rbx]
0x180006c12  test    rdi, rdi
0x180006c15  jz      short loc_180006C4E
0x180006c17  mov     ecx, 1
0x180006c1c  mov     rax, [rdi+8]
0x180006c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c25  test    eax, eax
0x180006c27  js      short loc_180006C87
0x180006c29  mov     rax, [rdi+38h]
0x180006c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c32  mov     r8d, 1; int
0x180006c38  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006c3b  mov     rcx, [rdi]; rguid
0x180006c3e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006c43  test    eax, eax
0x180006c45  js      short loc_180006C87
0x180006c47  mov     rcx, cs:off_1800270D8
0x180006c4e  add     rbx, 8
0x180006c52  cmp     rbx, rcx
0x180006c55  jb      short loc_180006C0F
0x180006c57  test    eax, eax
0x180006c59  js      short loc_180006C87
0x180006c5b  mov     rcx, cs:off_1800270C8; HINSTANCE
0x180006c62  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180006c67  test    eax, eax
0x180006c69  js      short loc_180006C87
0x180006c6b  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180006c72  test    rdx, rdx
0x180006c75  jz      short loc_180006C87
0x180006c77  mov     rcx, cs:hModule
0x180006c7e  mov     rax, rdx
0x180006c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c86  nop
0x180006c87  mov     rbx, [rsp+28h+arg_0]
0x180006c8c  add     rsp, 20h
0x180006c90  pop     rdi
0x180006c91  retn
```
