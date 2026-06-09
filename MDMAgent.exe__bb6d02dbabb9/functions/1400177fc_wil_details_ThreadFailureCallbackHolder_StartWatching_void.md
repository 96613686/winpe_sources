# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1400177fc`
- end: `0x140017870`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400167e0`

## callees

- `0x14000353c`
- `0x1400058a4`
- `0x140007a80`
- `0x1400177fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001784e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001784e`

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
0x1400177fc  push    rbx
0x1400177fe  sub     rsp, 0C0h
0x140017805  cmp     dword ptr [rcx+18h], 0
0x140017809  mov     rbx, rcx
0x14001780c  jz      short loc_14001782B
0x14001780e  xor     edx, edx; Val
0x140017810  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140017815  mov     r8d, 98h; Size
0x14001781b  call    memset_0
0x140017820  lea     rcx, [rsp+0C8h+var_A8]; this
0x140017825  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14001782b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140017833  jz      short loc_14001785F
0x140017835  mov     dl, 1
0x140017837  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14001783c  mov     [rbx], rax
0x14001783f  test    rax, rax
0x140017842  jz      short loc_140017866
0x140017844  mov     rcx, [rax]
0x140017847  mov     [rbx+10h], rcx
0x14001784b  mov     [rax], rbx
0x14001784e  call    cs:__imp_GetCurrentThreadId
0x140017855  nop     dword ptr [rax+rax+00h]
0x14001785a  mov     [rbx+18h], eax
0x14001785d  jmp     short loc_140017866
0x14001785f  mov     qword ptr [rcx], 0
0x140017866  add     rsp, 0C0h
0x14001786d  pop     rbx
0x14001786e  retn
```
