# CProfilesHandlerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180019f80`
- end: `0x18001a01f`
- name: `?CreateInstance@CProfilesHandlerClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `159`
- prototype: `__int64 __fastcall(CProfilesHandlerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180019f80`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019fbb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019fbb`

## pseudocode

```c
__int64 __fastcall CProfilesHandlerClassFactory::CreateInstance(
        CProfilesHandlerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = LocalAlloc(0, 0x10u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[2] = 1;
  *(_QWORD *)v7 = &CProfilesHandler::`vftable';
  _InterlockedIncrement(&g_cRefThisDll);
  v9 = (**(__int64 (__fastcall ***)(HLOCAL, const struct _GUID *, void **))v7)(v7, a3, a4);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180019f80  mov     [rsp+arg_0], rbx
0x180019f85  mov     [rsp+arg_8], rsi
0x180019f8a  push    rdi
0x180019f8b  sub     rsp, 20h
0x180019f8f  mov     rbx, r9
0x180019f92  mov     rsi, r8
0x180019f95  test    r9, r9
0x180019f98  jnz     short loc_180019FA1
0x180019f9a  mov     eax, 80004003h
0x180019f9f  jmp     short loc_18001A00F
0x180019fa1  mov     qword ptr [r9], 0
0x180019fa8  test    rdx, rdx
0x180019fab  jz      short loc_180019FB4
0x180019fad  mov     eax, 80040110h
0x180019fb2  jmp     short loc_18001A00F
0x180019fb4  mov     edx, 10h; uBytes
0x180019fb9  xor     ecx, ecx; uFlags
0x180019fbb  call    cs:__imp_LocalAlloc
0x180019fc1  mov     rdi, rax
0x180019fc4  test    rax, rax
0x180019fc7  jz      short loc_18001A00A
0x180019fc9  lea     rax, ??_7CProfilesHandler@@6B@; const CProfilesHandler::`vftable'
0x180019fd0  mov     dword ptr [rdi+8], 1
0x180019fd7  mov     [rdi], rax
0x180019fda  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180019fe1  mov     rcx, [rdi]
0x180019fe4  mov     r8, rbx
0x180019fe7  mov     rdx, rsi
0x180019fea  mov     rax, [rcx]
0x180019fed  mov     rcx, rdi
0x180019ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff5  mov     rcx, [rdi]
0x180019ff8  mov     ebx, eax
0x180019ffa  mov     rax, [rcx+10h]
0x180019ffe  mov     rcx, rdi
0x18001a001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a006  mov     eax, ebx
0x18001a008  jmp     short loc_18001A00F
0x18001a00a  mov     eax, 8007000Eh
0x18001a00f  mov     rbx, [rsp+28h+arg_0]
0x18001a014  mov     rsi, [rsp+28h+arg_8]
0x18001a019  add     rsp, 20h
0x18001a01d  pop     rdi
0x18001a01e  retn
```
