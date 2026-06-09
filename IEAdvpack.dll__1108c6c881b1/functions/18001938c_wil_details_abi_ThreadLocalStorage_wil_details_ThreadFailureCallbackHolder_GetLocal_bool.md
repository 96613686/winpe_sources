# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001938c`
- end: `0x1800193e1`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `85`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018eb4`

## callees

- `0x180001be2`
- `0x18001938c`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId_0; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId_0 = GetCurrentThreadId_0();
  for ( result = *(_QWORD *)(v0 + 8 * (((unsigned __int64)CurrentThreadId_0 >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId_0 )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001938c  push    rbx
0x18001938e  sub     rsp, 20h
0x180019392  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180019399  call    GetCurrentThreadId_0
0x18001939e  mov     r8d, eax
0x1800193a1  mov     r9d, eax
0x1800193a4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800193ae  shr     r8, 2
0x1800193b2  mul     r8
0x1800193b5  shr     rdx, 3
0x1800193b9  lea     rcx, [rdx+rdx*4]
0x1800193bd  add     rcx, rcx
0x1800193c0  sub     r8, rcx
0x1800193c3  mov     rax, [rbx+r8*8]
0x1800193c7  test    rax, rax
0x1800193ca  jz      short loc_1800193DB
0x1800193cc  cmp     [rax], r9d
0x1800193cf  jz      short loc_1800193D7
0x1800193d1  mov     rax, [rax+8]
0x1800193d5  jmp     short loc_1800193C7
0x1800193d7  add     rax, 10h
0x1800193db  add     rsp, 20h
0x1800193df  pop     rbx
0x1800193e0  retn
```
