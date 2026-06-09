# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18001bcec`
- end: `0x18001bd59`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011cd0`

## callees

- `0x180002c18`
- `0x1800069ec`
- `0x18000aba0`
- `0x18001bcec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd21`

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
0x18001bcec  push    rbx
0x18001bcee  sub     rsp, 0C0h
0x18001bcf5  cmp     dword ptr [rcx+18h], 0
0x18001bcf9  mov     rbx, rcx
0x18001bcfc  jnz     short loc_18001BD3C
0x18001bcfe  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001bd06  jz      short loc_18001BD2C
0x18001bd08  mov     dl, 1
0x18001bd0a  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001bd0f  mov     [rbx], rax
0x18001bd12  test    rax, rax
0x18001bd15  jz      short loc_18001BD33
0x18001bd17  mov     rcx, [rax]
0x18001bd1a  mov     [rbx+10h], rcx
0x18001bd1e  mov     [rax], rbx
0x18001bd21  call    cs:__imp_GetCurrentThreadId
0x18001bd27  mov     [rbx+18h], eax
0x18001bd2a  jmp     short loc_18001BD33
0x18001bd2c  mov     qword ptr [rcx], 0
0x18001bd33  add     rsp, 0C0h
0x18001bd3a  pop     rbx
0x18001bd3b  retn
0x18001bd3c  xor     edx, edx; Val
0x18001bd3e  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001bd43  mov     r8d, 98h; Size
0x18001bd49  call    memset_0
0x18001bd4e  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001bd53  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
