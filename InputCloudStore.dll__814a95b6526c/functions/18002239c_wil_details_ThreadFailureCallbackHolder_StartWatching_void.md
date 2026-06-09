# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18002239c`
- end: `0x180022409`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a3d0`

## callees

- `0x180003fd4`
- `0x180005a2c`
- `0x1800074d8`
- `0x18002239c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223d1`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v3);
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
0x18002239c  push    rbx
0x18002239e  sub     rsp, 0C0h
0x1800223a5  cmp     dword ptr [rcx+18h], 0
0x1800223a9  mov     rbx, rcx
0x1800223ac  jnz     short loc_1800223EC
0x1800223ae  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800223b6  jz      short loc_1800223DC
0x1800223b8  mov     dl, 1
0x1800223ba  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800223bf  mov     [rbx], rax
0x1800223c2  test    rax, rax
0x1800223c5  jz      short loc_1800223E3
0x1800223c7  mov     rcx, [rax]
0x1800223ca  mov     [rbx+10h], rcx
0x1800223ce  mov     [rax], rbx
0x1800223d1  call    cs:__imp_GetCurrentThreadId
0x1800223d7  mov     [rbx+18h], eax
0x1800223da  jmp     short loc_1800223E3
0x1800223dc  mov     qword ptr [rcx], 0
0x1800223e3  add     rsp, 0C0h
0x1800223ea  pop     rbx
0x1800223eb  retn
0x1800223ec  xor     edx, edx; Val
0x1800223ee  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800223f3  mov     r8d, 98h; Size
0x1800223f9  call    memset_0
0x1800223fe  lea     rcx, [rsp+0C8h+var_A8]; this
0x180022403  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
