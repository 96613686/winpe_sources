# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_1_::dtor$2

- ea: `0x18001dc18`
- end: `0x18001dc8d`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_1_::dtor$2`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018238`
- `0x18001dc18`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheModelWithOfflineDriverAsync_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  if ( *(_WORD *)(*(_QWORD *)(a2 + 32) + 10LL) )
  {
    *(_QWORD *)(a2 + 64) = 336;
    *(_QWORD *)(a2 + 72) = *(_QWORD *)(a2 + 32) - 112LL;
    operator delete(*(void **)(a2 + 72));
  }
}

```

## disassembly

```asm
0x18001dc18  push    rbp
0x18001dc1a  sub     rsp, 20h
0x18001dc1e  mov     rbp, rdx
0x18001dc21  mov     rax, [rbp+20h]
0x18001dc25  add     rax, 8
0x18001dc29  add     rax, 2
0x18001dc2d  movzx   eax, word ptr [rax]
0x18001dc30  test    eax, eax
0x18001dc32  jz      short loc_18001DC87
0x18001dc34  mov     eax, 0C0h
0x18001dc39  add     rax, 90h
0x18001dc3f  mov     [rbp+40h], rax
0x18001dc43  mov     eax, 10h
0x18001dc48  cmp     rax, 10h
0x18001dc4c  jbe     short loc_18001DC6E
0x18001dc4e  mov     rdx, [rbp+20h]
0x18001dc52  sub     rdx, 70h ; 'p'
0x18001dc56  mov     eax, 8
0x18001dc5b  imul    rcx, rax, -1
0x18001dc5f  mov     rax, rdx
0x18001dc62  add     rax, rcx
0x18001dc65  mov     rax, [rax]
0x18001dc68  mov     [rbp+48h], rax
0x18001dc6c  jmp     short loc_18001DC7A
0x18001dc6e  mov     rax, [rbp+20h]
0x18001dc72  sub     rax, 70h ; 'p'
0x18001dc76  mov     [rbp+48h], rax
0x18001dc7a  mov     rdx, [rbp+40h]; unsigned __int64
0x18001dc7e  mov     rcx, [rbp+48h]; void *
0x18001dc82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dc87  add     rsp, 20h
0x18001dc8b  pop     rbp
0x18001dc8c  retn
```
