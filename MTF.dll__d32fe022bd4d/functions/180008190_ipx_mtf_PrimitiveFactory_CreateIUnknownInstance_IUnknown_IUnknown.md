# ipx::mtf::PrimitiveFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180008190`
- end: `0x180008238`
- name: `?_CreateIUnknownInstance@PrimitiveFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `168`
- prototype: `__int64 __fastcall(ipx::mtf::PrimitiveFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180008190`

## pseudocode

```c
__int64 __fastcall ipx::mtf::PrimitiveFactory::_CreateIUnknownInstance(
        ipx::mtf::PrimitiveFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  struct IUnknown *v5; // rax
  struct IUnknown *v6; // rcx

  if ( a2 )
    return 2147746064LL;
  v5 = (struct IUnknown *)operator new(0x50u);
  v6 = v5;
  if ( v5 )
  {
    v5[4].lpVtbl = 0;
    v5->lpVtbl = (struct IUnknownVtbl *)&MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'};
    v5[1].lpVtbl = (struct IUnknownVtbl *)&MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'};
    v5[2].lpVtbl = (struct IUnknownVtbl *)&MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'};
    v5[3].lpVtbl = (struct IUnknownVtbl *)&MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'};
    WORD2(v5[9].lpVtbl) = -1;
    v5[5].lpVtbl = 0;
    v5[6].lpVtbl = 0;
    v5[7].lpVtbl = (struct IUnknownVtbl *)1;
    v5[8].lpVtbl = 0;
    LODWORD(v5[9].lpVtbl) = -65536;
    _InterlockedIncrement(&g_cRefDll);
  }
  else
  {
    v6 = 0;
  }
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x180008190  push    rbx
0x180008192  sub     rsp, 20h
0x180008196  mov     rbx, r8
0x180008199  test    rdx, rdx
0x18000819c  jz      short loc_1800081A8
0x18000819e  mov     eax, 80040110h
0x1800081a3  jmp     loc_180008232
0x1800081a8  mov     ecx, 50h ; 'P'; Size
0x1800081ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081b2  mov     [rsp+28h+arg_8], rax
0x1800081b7  mov     rcx, rax
0x1800081ba  test    rax, rax
0x1800081bd  jz      short loc_18000822B
0x1800081bf  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionListElement@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'}
0x1800081c6  mov     qword ptr [rcx+20h], 0
0x1800081ce  mov     [rcx], rax
0x1800081d1  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionCandidatePrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'}
0x1800081d8  mov     [rcx+8], rax
0x1800081dc  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfPrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'}
0x1800081e3  mov     [rcx+10h], rax
0x1800081e7  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSerializable@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'}
0x1800081ee  mov     [rcx+18h], rax
0x1800081f2  mov     eax, 0FFFFh
0x1800081f7  mov     [rcx+4Ch], ax
0x1800081fb  mov     qword ptr [rcx+28h], 0
0x180008203  mov     qword ptr [rcx+30h], 0
0x18000820b  mov     qword ptr [rcx+38h], 1
0x180008213  mov     qword ptr [rcx+40h], 0
0x18000821b  mov     dword ptr [rcx+48h], 0FFFF0000h
0x180008222  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180008229  jmp     short loc_18000822D
0x18000822b  xor     ecx, ecx
0x18000822d  mov     [rbx], rcx
0x180008230  xor     eax, eax
0x180008232  add     rsp, 20h
0x180008236  pop     rbx
0x180008237  retn
```
