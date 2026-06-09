# CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180004790`
- end: `0x1800047cd`
- name: `?_AddRefRecord@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004790`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(
        __int64 a1,
        int a2)
{
  __int64 result; // rax

  if ( a2 == 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 12));
  }
  else if ( a2 == -1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 12), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      if ( a1 )
        return (**(__int64 (__fastcall ***)(__int64, __int64))a1)(a1, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004790  sub     rsp, 28h
0x180004794  cmp     edx, 1
0x180004797  jnz     short loc_1800047A2
0x180004799  lock inc dword ptr [rcx+0Ch]
0x18000479d  add     rsp, 28h
0x1800047a1  retn
0x1800047a2  cmp     edx, 0FFFFFFFFh
0x1800047a5  jnz     short loc_1800047C8
0x1800047a7  or      eax, edx
0x1800047a9  lock xadd [rcx+0Ch], eax
0x1800047ae  cmp     eax, 1
0x1800047b1  jnz     short loc_1800047C8
0x1800047b3  test    rcx, rcx
0x1800047b6  jz      short loc_1800047C8
0x1800047b8  mov     rax, [rcx]
0x1800047bb  mov     edx, 1
0x1800047c0  mov     rax, [rax]
0x1800047c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c8  add     rsp, 28h
0x1800047cc  retn
```
