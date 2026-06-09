# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1800295e8`
- end: `0x180029655`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019d34`
- `0x18001d9b0`

## callees

- `0x180009cf0`
- `0x18000c8dc`
- `0x18000fdc8`
- `0x1800295e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002963a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002963a`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  const struct wil::FailureInfo *v3; // rdx
  _QWORD *Local; // rax
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v3);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
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
0x1800295e8  push    rbx
0x1800295ea  sub     rsp, 0C0h
0x1800295f1  cmp     dword ptr [rcx+18h], 0
0x1800295f5  mov     rbx, rcx
0x1800295f8  jz      short loc_180029617
0x1800295fa  xor     edx, edx; Val
0x1800295fc  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180029601  mov     r8d, 98h; Size
0x180029607  call    memset_0
0x18002960c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180029611  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180029617  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002961f  jz      short loc_180029645
0x180029621  mov     dl, 1
0x180029623  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180029628  mov     [rbx], rax
0x18002962b  test    rax, rax
0x18002962e  jz      short loc_18002964C
0x180029630  mov     rcx, [rax]
0x180029633  mov     [rbx+10h], rcx
0x180029637  mov     [rax], rbx
0x18002963a  call    cs:__imp_GetCurrentThreadId
0x180029640  mov     [rbx+18h], eax
0x180029643  jmp     short loc_18002964C
0x180029645  mov     qword ptr [rcx], 0
0x18002964c  add     rsp, 0C0h
0x180029653  pop     rbx
0x180029654  retn
```
