# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_1_::dtor$1

- ea: `0x18001db4c`
- end: `0x18001dbc1`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_1_::dtor$1`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018238`
- `0x18001db4c`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnsureModelIsCachedAsync_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  if ( *(_WORD *)(*(_QWORD *)(a2 + 32) + 10LL) )
  {
    *(_QWORD *)(a2 + 56) = 208;
    *(_QWORD *)(a2 + 64) = *(_QWORD *)(a2 + 32) - 112LL;
    operator delete(*(void **)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18001db4c  push    rbp
0x18001db4e  sub     rsp, 20h
0x18001db52  mov     rbp, rdx
0x18001db55  mov     rax, [rbp+20h]
0x18001db59  add     rax, 8
0x18001db5d  add     rax, 2
0x18001db61  movzx   eax, word ptr [rax]
0x18001db64  test    eax, eax
0x18001db66  jz      short loc_18001DBBB
0x18001db68  mov     eax, 40h ; '@'
0x18001db6d  add     rax, 90h
0x18001db73  mov     [rbp+38h], rax
0x18001db77  mov     eax, 10h
0x18001db7c  cmp     rax, 10h
0x18001db80  jbe     short loc_18001DBA2
0x18001db82  mov     rdx, [rbp+20h]
0x18001db86  sub     rdx, 70h ; 'p'
0x18001db8a  mov     eax, 8
0x18001db8f  imul    rcx, rax, -1
0x18001db93  mov     rax, rdx
0x18001db96  add     rax, rcx
0x18001db99  mov     rax, [rax]
0x18001db9c  mov     [rbp+40h], rax
0x18001dba0  jmp     short loc_18001DBAE
0x18001dba2  mov     rax, [rbp+20h]
0x18001dba6  sub     rax, 70h ; 'p'
0x18001dbaa  mov     [rbp+40h], rax
0x18001dbae  mov     rdx, [rbp+38h]; unsigned __int64
0x18001dbb2  mov     rcx, [rbp+40h]; void *
0x18001dbb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dbbb  add     rsp, 20h
0x18001dbbf  pop     rbp
0x18001dbc0  retn
```
