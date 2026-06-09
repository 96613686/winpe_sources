# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000ba30`
- end: `0x18000ba9d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b8c4`

## callees

- `0x180009b54`
- `0x18000ba30`
- `0x18000c388`
- `0x18000f076`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba82`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  const struct wil::FailureInfo *v2; // rdx
  _QWORD *Local; // rax
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v2);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        (__int64)this,
                        1);
    *(_QWORD *)this = Local;
    if ( Local )
    {
      *((_QWORD *)this + 2) = *Local;
      *Local = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000ba30  push    rbx
0x18000ba32  sub     rsp, 0C0h
0x18000ba39  cmp     dword ptr [rcx+18h], 0
0x18000ba3d  mov     rbx, rcx
0x18000ba40  jz      short loc_18000BA5F
0x18000ba42  xor     edx, edx; Val
0x18000ba44  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000ba49  mov     r8d, 98h; Size
0x18000ba4f  call    memset_0
0x18000ba54  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ba59  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ba5f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ba67  jz      short loc_18000BA8D
0x18000ba69  mov     dl, 1
0x18000ba6b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ba70  mov     [rbx], rax
0x18000ba73  test    rax, rax
0x18000ba76  jz      short loc_18000BA94
0x18000ba78  mov     rcx, [rax]
0x18000ba7b  mov     [rbx+10h], rcx
0x18000ba7f  mov     [rax], rbx
0x18000ba82  call    cs:__imp_GetCurrentThreadId
0x18000ba88  mov     [rbx+18h], eax
0x18000ba8b  jmp     short loc_18000BA94
0x18000ba8d  mov     qword ptr [rcx], 0
0x18000ba94  add     rsp, 0C0h
0x18000ba9b  pop     rbx
0x18000ba9c  retn
```
