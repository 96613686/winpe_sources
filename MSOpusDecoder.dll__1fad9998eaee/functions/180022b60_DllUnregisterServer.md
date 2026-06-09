# DllUnregisterServer

- ea: `0x180022b60`
- end: `0x180022c44`
- name: `DllUnregisterServer`
- size: `228`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001fcb0`
- `0x180022b60`
- `0x180024010`

## import_xrefs

- `MFPlat!MFTUnregister` at `0x180022b7c`
- `MFPlat!MFTUnregister` at `0x180022b7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  __int64 *v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  CLSID clsidMFT; // [rsp+20h] [rbp-18h] BYREF

  clsidMFT = CLSID_CMSOpusDecMFT;
  result = MFTUnregister(&clsidMFT);
  if ( result >= 0 )
  {
    v1 = qword_1800353C8;
    if ( qword_1800353C8 )
    {
      while ( *(_QWORD *)v1 )
      {
        v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v1 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v1, v2, 0);
        if ( result < 0 )
          return result;
        result = (*(__int64 (__fastcall **)(_QWORD))(v1 + 8))(0);
        if ( result < 0 )
          return result;
        v1 += 72;
      }
    }
    if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
    {
      result = 0;
      v3 = off_1800350E0[0];
      v4 = off_1800350E8;
      while ( v3 < v4 )
      {
        v5 = *v3;
        if ( *v3 )
        {
          v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
          result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
          if ( result < 0 )
            return result;
          result = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
          if ( result < 0 )
            return result;
          v4 = off_1800350E8;
        }
        ++v3;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022b60  mov     [rsp+arg_0], rbx
0x180022b65  push    rdi
0x180022b66  sub     rsp, 30h
0x180022b6a  movups  xmm0, xmmword ptr cs:CLSID_CMSOpusDecMFT.Data1
0x180022b71  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x180022b77  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x180022b7c  call    cs:__imp_MFTUnregister
0x180022b82  test    eax, eax
0x180022b84  js      loc_180022C39
0x180022b8a  mov     rbx, cs:qword_1800353C8
0x180022b91  test    rbx, rbx
0x180022b94  jz      short loc_180022BD0
0x180022b96  jmp     short loc_180022BCA
0x180022b98  mov     rax, [rbx+38h]
0x180022b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ba1  xor     r8d, r8d; int
0x180022ba4  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180022ba7  mov     rcx, [rbx]; rguid
0x180022baa  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180022baf  test    eax, eax
0x180022bb1  js      loc_180022C39
0x180022bb7  xor     ecx, ecx
0x180022bb9  mov     rax, [rbx+8]
0x180022bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bc2  test    eax, eax
0x180022bc4  js      short loc_180022C39
0x180022bc6  add     rbx, 48h ; 'H'
0x180022bca  cmp     qword ptr [rbx], 0
0x180022bce  jnz     short loc_180022B98
0x180022bd0  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180022bd7  test    rax, rax
0x180022bda  jz      short loc_180022BE5
0x180022bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022be1  test    eax, eax
0x180022be3  js      short loc_180022C39
0x180022be5  xor     eax, eax
0x180022be7  mov     rbx, cs:off_1800350E0
0x180022bee  mov     rcx, cs:off_1800350E8
0x180022bf5  jmp     short loc_180022C34
0x180022bf7  mov     rdi, [rbx]
0x180022bfa  test    rdi, rdi
0x180022bfd  jz      short loc_180022C30
0x180022bff  mov     rax, [rdi+38h]
0x180022c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c08  xor     r8d, r8d; int
0x180022c0b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180022c0e  mov     rcx, [rdi]; rguid
0x180022c11  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180022c16  test    eax, eax
0x180022c18  js      short loc_180022C39
0x180022c1a  xor     ecx, ecx
0x180022c1c  mov     rax, [rdi+8]
0x180022c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c25  test    eax, eax
0x180022c27  js      short loc_180022C39
0x180022c29  mov     rcx, cs:off_1800350E8
0x180022c30  add     rbx, 8
0x180022c34  cmp     rbx, rcx
0x180022c37  jb      short loc_180022BF7
0x180022c39  mov     rbx, [rsp+38h+arg_0]
0x180022c3e  add     rsp, 30h
0x180022c42  pop     rdi
0x180022c43  retn
```
