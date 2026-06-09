# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback_::_1_::dtor$0

- ea: `0x18001daa0`
- end: `0x18001db08`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback_::_1_::dtor$0`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018238`
- `0x18001daa0`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( *(_WORD *)(*(_QWORD *)(a2 + 48) + 10LL) )
  {
    *(_QWORD *)(a2 + 56) = 48;
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 48);
    operator delete(*(void **)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18001daa0  push    rbp
0x18001daa2  sub     rsp, 20h
0x18001daa6  mov     rbp, rdx
0x18001daa9  mov     rax, [rbp+30h]
0x18001daad  add     rax, 8
0x18001dab1  add     rax, 2
0x18001dab5  movzx   eax, word ptr [rax]
0x18001dab8  test    eax, eax
0x18001daba  jz      short loc_18001DB02
0x18001dabc  mov     eax, 20h ; ' '
0x18001dac1  add     rax, 10h
0x18001dac5  mov     [rbp+38h], rax
0x18001dac9  mov     eax, 10h
0x18001dace  cmp     rax, 10h
0x18001dad2  jbe     short loc_18001DAED
0x18001dad4  mov     eax, 8
0x18001dad9  imul    rcx, rax, -1
0x18001dadd  mov     rax, [rbp+30h]
0x18001dae1  add     rax, rcx
0x18001dae4  mov     rax, [rax]
0x18001dae7  mov     [rbp+40h], rax
0x18001daeb  jmp     short loc_18001DAF5
0x18001daed  mov     rax, [rbp+30h]
0x18001daf1  mov     [rbp+40h], rax
0x18001daf5  mov     rdx, [rbp+38h]; unsigned __int64
0x18001daf9  mov     rcx, [rbp+40h]; void *
0x18001dafd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001db02  add     rsp, 20h
0x18001db06  pop     rbp
0x18001db07  retn
```
