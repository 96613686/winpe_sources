# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400048bc`
- end: `0x140004912`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400043e4`

## callees

- `0x1400048bc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400048c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400048c9`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(v0 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
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
0x1400048bc  push    rbx
0x1400048be  sub     rsp, 20h
0x1400048c2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400048c9  call    cs:__imp_GetCurrentThreadId
0x1400048cf  mov     r8d, eax
0x1400048d2  mov     r9d, eax
0x1400048d5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400048df  shr     r8, 2
0x1400048e3  mul     r8
0x1400048e6  shr     rdx, 3
0x1400048ea  lea     rcx, [rdx+rdx*4]
0x1400048ee  add     rcx, rcx
0x1400048f1  sub     r8, rcx
0x1400048f4  mov     rax, [rbx+r8*8]
0x1400048f8  test    rax, rax
0x1400048fb  jz      short loc_14000490C
0x1400048fd  cmp     [rax], r9d
0x140004900  jz      short loc_140004908
0x140004902  mov     rax, [rax+8]
0x140004906  jmp     short loc_1400048F8
0x140004908  add     rax, 10h
0x14000490c  add     rsp, 20h
0x140004910  pop     rbx
0x140004911  retn
```
