# DllRegisterServer

- ea: `0x180006b20`
- end: `0x180006c12`
- name: `DllRegisterServer`
- size: `242`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003c7c`
- `0x180004144`
- `0x180006b20`
- `0x18000c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  __int64 *v4; // rbx
  __int64 *i; // rcx
  __int64 v6; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  v1 = qword_180013A08;
  if ( qword_180013A08 )
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
  v4 = (__int64 *)off_180013110[0];
  for ( i = (__int64 *)off_180013118; v4 < i; ++v4 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v6 + 8))(1);
      if ( result < 0 )
        return result;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
      if ( result < 0 )
        return result;
      i = (__int64 *)off_180013118;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_180013108, v0);
  if ( result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
  }
  return result;
}

```

## disassembly

```asm
0x180006b20  mov     [rsp+arg_0], rbx
0x180006b25  push    rdi
0x180006b26  sub     rsp, 20h
0x180006b2a  mov     rbx, cs:qword_180013A08
0x180006b31  test    rbx, rbx
0x180006b34  jz      short loc_180006B7A
0x180006b36  jmp     short loc_180006B74
0x180006b38  mov     ecx, 1
0x180006b3d  mov     rax, [rbx+8]
0x180006b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b46  test    eax, eax
0x180006b48  js      loc_180006C07
0x180006b4e  mov     rax, [rbx+38h]
0x180006b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b57  mov     r8d, 1; int
0x180006b5d  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006b60  mov     rcx, [rbx]; rguid
0x180006b63  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006b68  test    eax, eax
0x180006b6a  js      loc_180006C07
0x180006b70  add     rbx, 48h ; 'H'
0x180006b74  cmp     qword ptr [rbx], 0
0x180006b78  jnz     short loc_180006B38
0x180006b7a  xor     eax, eax
0x180006b7c  mov     rbx, cs:off_180013110
0x180006b83  mov     rcx, cs:off_180013118
0x180006b8a  cmp     rbx, rcx
0x180006b8d  jnb     short loc_180006BDB
0x180006b8f  mov     rdi, [rbx]
0x180006b92  test    rdi, rdi
0x180006b95  jz      short loc_180006BCE
0x180006b97  mov     ecx, 1
0x180006b9c  mov     rax, [rdi+8]
0x180006ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba5  test    eax, eax
0x180006ba7  js      short loc_180006C07
0x180006ba9  mov     rax, [rdi+38h]
0x180006bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb2  mov     r8d, 1; int
0x180006bb8  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006bbb  mov     rcx, [rdi]; rguid
0x180006bbe  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006bc3  test    eax, eax
0x180006bc5  js      short loc_180006C07
0x180006bc7  mov     rcx, cs:off_180013118
0x180006bce  add     rbx, 8
0x180006bd2  cmp     rbx, rcx
0x180006bd5  jb      short loc_180006B8F
0x180006bd7  test    eax, eax
0x180006bd9  js      short loc_180006C07
0x180006bdb  mov     rcx, cs:off_180013108; HINSTANCE
0x180006be2  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180006be7  test    eax, eax
0x180006be9  js      short loc_180006C07
0x180006beb  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180006bf2  test    rdx, rdx
0x180006bf5  jz      short loc_180006C07
0x180006bf7  mov     rcx, cs:hInstance
0x180006bfe  mov     rax, rdx
0x180006c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c06  nop
0x180006c07  mov     rbx, [rsp+28h+arg_0]
0x180006c0c  add     rsp, 20h
0x180006c10  pop     rdi
0x180006c11  retn
```
