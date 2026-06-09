# CWiaExtensionHost64Factory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001e70`
- end: `0x180001f1b`
- name: `?CreateInstance@CWiaExtensionHost64Factory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `171`
- prototype: `__int64 __fastcall(CWiaExtensionHost64Factory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x180001e70`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64Factory::CreateInstance(
        CWiaExtensionHost64Factory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x10u);
      v8 = v7;
      if ( v7 )
      {
        *(_QWORD *)v7 = &CWiaExtensionHost64::`vftable';
        v7[2] = 0;
        _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 8LL))(v7);
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v8)(v8, a3, a4);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x180001e70  mov     [rsp+arg_0], rbx
0x180001e75  mov     [rsp+arg_8], rsi
0x180001e7a  push    rdi
0x180001e7b  sub     rsp, 20h
0x180001e7f  mov     rbx, r9
0x180001e82  mov     rsi, r8
0x180001e85  test    r9, r9
0x180001e88  jnz     short loc_180001E91
0x180001e8a  mov     ebx, 80004003h
0x180001e8f  jmp     short loc_180001F09
0x180001e91  mov     qword ptr [r9], 0
0x180001e98  test    rdx, rdx
0x180001e9b  jz      short loc_180001EA4
0x180001e9d  mov     ebx, 80040110h
0x180001ea2  jmp     short loc_180001F09
0x180001ea4  mov     ecx, 10h; Size
0x180001ea9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001eae  mov     rdi, rax
0x180001eb1  test    rax, rax
0x180001eb4  jz      short loc_180001F04
0x180001eb6  lea     rax, ??_7CWiaExtensionHost64@@6B@; const CWiaExtensionHost64::`vftable'
0x180001ebd  mov     [rdi], rax
0x180001ec0  mov     dword ptr [rdi+8], 0
0x180001ec7  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180001ece  mov     rax, [rdi]
0x180001ed1  mov     rcx, rdi
0x180001ed4  mov     rax, [rax+8]
0x180001ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001edd  mov     rax, [rdi]
0x180001ee0  mov     r8, rbx
0x180001ee3  mov     rdx, rsi
0x180001ee6  mov     rcx, rdi
0x180001ee9  mov     rax, [rax]
0x180001eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef1  mov     rcx, [rdi]
0x180001ef4  mov     ebx, eax
0x180001ef6  mov     rax, [rcx+10h]
0x180001efa  mov     rcx, rdi
0x180001efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f02  jmp     short loc_180001F09
0x180001f04  mov     ebx, 8007000Eh
0x180001f09  mov     rsi, [rsp+28h+arg_8]
0x180001f0e  mov     eax, ebx
0x180001f10  mov     rbx, [rsp+28h+arg_0]
0x180001f15  add     rsp, 20h
0x180001f19  pop     rdi
0x180001f1a  retn
```
