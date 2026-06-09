# ?__abi_Release@?QObject@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAKXZ

- ea: `0x140008550`
- end: `0x1400085fc`
- name: `?__abi_Release@?QObject@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAKXZ`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140008610`
- `0x140008620`
- `0x140008630`

## callees

- `0x1400039b6`
- `0x14000614c`
- `0x140008550`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x1400085c0`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x1400085c0`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400085dc`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400085dc`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400085e4`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400085e4`

## pseudocode

```c
__int64 __fastcall ___abi_Release__QObject_Platform__CssTemplateInfo_CHXSmartScreen__UE_AAAKXZ(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rbx

  v2 = __abi_FTMWeakRefData::Decrement(a1 + 96);
  if ( !v2 )
  {
    WindowsDeleteString_0(*(HSTRING *)(a1 + 88));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 80));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 72));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 64));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 56));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 48));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 40));
    WindowsDeleteString_0(*(HSTRING *)(a1 + 32));
    v3 = *(_QWORD *)(a1 + 96);
    Platform::Details::ControlBlock::ReleaseTarget((Platform::Details::ControlBlock *)v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF) == 1 )
    {
      if ( *(_BYTE *)(v3 + 25) )
        Platform::Details::Heap::AlignedFree((void *)v3);
      else
        Platform::Details::Heap::Free((void *)v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140008550  mov     [rsp+arg_8], rbx
0x140008555  mov     [rsp+arg_10], rsi
0x14000855a  push    rdi
0x14000855b  sub     rsp, 20h
0x14000855f  mov     rbx, rcx
0x140008562  add     rcx, 60h ; '`'
0x140008566  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x14000856b  mov     edi, eax
0x14000856d  test    eax, eax
0x14000856f  jnz     short loc_1400085EA
0x140008571  mov     rcx, [rbx+58h]; string
0x140008575  call    WindowsDeleteString_0
0x14000857a  mov     rcx, [rbx+50h]; string
0x14000857e  call    WindowsDeleteString_0
0x140008583  mov     rcx, [rbx+48h]; string
0x140008587  call    WindowsDeleteString_0
0x14000858c  mov     rcx, [rbx+40h]; string
0x140008590  call    WindowsDeleteString_0
0x140008595  mov     rcx, [rbx+38h]; string
0x140008599  call    WindowsDeleteString_0
0x14000859e  mov     rcx, [rbx+30h]; string
0x1400085a2  call    WindowsDeleteString_0
0x1400085a7  mov     rcx, [rbx+28h]; string
0x1400085ab  call    WindowsDeleteString_0
0x1400085b0  mov     rcx, [rbx+20h]; string
0x1400085b4  call    WindowsDeleteString_0
0x1400085b9  mov     rbx, [rbx+60h]
0x1400085bd  mov     rcx, rbx
0x1400085c0  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x1400085c6  or      eax, 0FFFFFFFFh
0x1400085c9  lock xadd [rbx+8], eax
0x1400085ce  cmp     eax, 1
0x1400085d1  jnz     short loc_1400085EA
0x1400085d3  mov     rcx, rbx
0x1400085d6  cmp     [rbx+19h], dil
0x1400085da  jz      short loc_1400085E4
0x1400085dc  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x1400085e2  jmp     short loc_1400085EA
0x1400085e4  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x1400085ea  mov     rbx, [rsp+28h+arg_8]
0x1400085ef  mov     eax, edi
0x1400085f1  mov     rsi, [rsp+28h+arg_10]
0x1400085f6  add     rsp, 20h
0x1400085fa  pop     rdi
0x1400085fb  retn
```
