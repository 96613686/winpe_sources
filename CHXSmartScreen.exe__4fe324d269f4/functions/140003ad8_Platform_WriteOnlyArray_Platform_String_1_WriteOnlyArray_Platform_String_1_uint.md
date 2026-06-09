# Platform::WriteOnlyArray<Platform::String *,1>::WriteOnlyArray<Platform::String *,1>(uint)

- ea: `0x140003ad8`
- end: `0x140003bb5`
- name: `??0?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@IE$AAA@I@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003a18`

## callees

- `0x1400028a4`
- `0x1400028bc`
- `0x1400028c8`
- `0x14000342d`
- `0x140003ad8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140003b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140003b7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Platform::WriteOnlyArray<Platform::String __gc *,1>::WriteOnlyArray<Platform::String __gc *,1>(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // rsi
  void *v4; // rax
  void *v5; // rbp

  v2 = a2;
  Platform::Object::Object(a1 + 16);
  *(_QWORD *)a1 = ___7__WriteOnlyArray_PE_AAVString_Platform___00_Platform__6B__I__WriteOnlyArray_PE_AAVString_Platform___00PublicNonVirtuals_1__;
  *(_QWORD *)(a1 + 8) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::IDisposable'};
  *(_QWORD *)(a1 + 16) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::Object'};
  *(_QWORD *)(a1 + 24) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `__abi_IUnknown'};
  *(_QWORD *)(a1 + 32) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  *(_QWORD *)(a1 + 64) = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  *(_DWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 44) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  if ( (_DWORD)v2 )
  {
    if ( (unsigned int)v2 <= 0x1FFFFFFF )
    {
      v4 = CoTaskMemAlloc(8 * v2);
      v5 = v4;
      if ( v4 )
      {
        memset_0(v4, 0, 8 * v2);
        *(_QWORD *)(a1 + 48) = v5;
        *(_DWORD *)(a1 + 40) = v2;
        return a1;
      }
      __abi_WinRTraiseOutOfMemoryException();
    }
    __abi_WinRTraiseInvalidCastException();
    JUMPOUT(0x140003BB4LL);
  }
  return a1;
}

```

## disassembly

```asm
0x140003ad8  mov     [rsp+arg_0], rcx
0x140003add  push    rbx
0x140003ade  push    rbp
0x140003adf  push    rsi
0x140003ae0  push    rdi
0x140003ae1  sub     rsp, 38h
0x140003ae5  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140003aee  mov     esi, edx
0x140003af0  mov     rdi, rcx
0x140003af3  add     rcx, 10h
0x140003af7  call    ??0Object@Platform@@QE$AAA@XZ_0; Platform::Object::Object(void)
0x140003afc  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6B__I?$WriteOnlyArray@PE$AAVString@Platform@@$00PublicNonVirtuals@1@@
0x140003b03  mov     [rdi], rax
0x140003b06  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BIDisposable@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::IDisposable'}
0x140003b0d  mov     [rdi+8], rax
0x140003b11  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BObject@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::Object'}
0x140003b18  mov     [rdi+10h], rax
0x140003b1c  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6B__abi_IUnknown@@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `__abi_IUnknown'}
0x140003b23  mov     [rdi+18h], rax
0x140003b27  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x140003b2e  mov     [rdi+20h], rax
0x140003b32  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x140003b3a  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140003b41  test    rcx, rcx
0x140003b44  jz      short loc_140003B52
0x140003b46  mov     rax, [rcx]
0x140003b49  mov     rax, [rax]
0x140003b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b51  nop
0x140003b52  mov     dword ptr [rdi+28h], 0
0x140003b59  mov     byte ptr [rdi+2Ch], 0
0x140003b5d  mov     qword ptr [rdi+30h], 0
0x140003b65  test    esi, esi
0x140003b67  jz      short loc_140003B9D
0x140003b69  cmp     esi, 1FFFFFFFh
0x140003b6f  ja      short loc_140003BAF
0x140003b71  mov     rbx, rsi
0x140003b74  shl     rbx, 3
0x140003b78  mov     rcx, rbx; cb
0x140003b7b  call    cs:__imp_CoTaskMemAlloc
0x140003b81  mov     rbp, rax
0x140003b84  test    rax, rax
0x140003b87  jz      short loc_140003BA9
0x140003b89  mov     r8, rbx; Size
0x140003b8c  xor     edx, edx; Val
0x140003b8e  mov     rcx, rax; void *
0x140003b91  call    memset_0
0x140003b96  mov     [rdi+30h], rbp
0x140003b9a  mov     [rdi+28h], esi
0x140003b9d  mov     rax, rdi
0x140003ba0  add     rsp, 38h
0x140003ba4  pop     rdi
0x140003ba5  pop     rsi
0x140003ba6  pop     rbp
0x140003ba7  pop     rbx
0x140003ba8  retn
0x140003ba9  call    ?__abi_WinRTraiseOutOfMemoryException@@YAXXZ_0; __abi_WinRTraiseOutOfMemoryException(void)
0x140003bae  nop
0x140003baf  call    ?__abi_WinRTraiseInvalidCastException@@YAXXZ_0; __abi_WinRTraiseInvalidCastException(void)
```
