# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x14000aca0`
- end: `0x14000ad0d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008ba0`

## callees

- `0x140003f8c`
- `0x140005dcc`
- `0x140007558`
- `0x14000aca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000acf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000acf2`

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
0x14000aca0  push    rbx
0x14000aca2  sub     rsp, 0C0h
0x14000aca9  cmp     dword ptr [rcx+18h], 0
0x14000acad  mov     rbx, rcx
0x14000acb0  jz      short loc_14000ACCF
0x14000acb2  xor     edx, edx; Val
0x14000acb4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000acb9  mov     r8d, 98h; Size
0x14000acbf  call    memset_0
0x14000acc4  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000acc9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000accf  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000acd7  jz      short loc_14000ACFD
0x14000acd9  mov     dl, 1
0x14000acdb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14000ace0  mov     [rbx], rax
0x14000ace3  test    rax, rax
0x14000ace6  jz      short loc_14000AD04
0x14000ace8  mov     rcx, [rax]
0x14000aceb  mov     [rbx+10h], rcx
0x14000acef  mov     [rax], rbx
0x14000acf2  call    cs:__imp_GetCurrentThreadId
0x14000acf8  mov     [rbx+18h], eax
0x14000acfb  jmp     short loc_14000AD04
0x14000acfd  mov     qword ptr [rcx], 0
0x14000ad04  add     rsp, 0C0h
0x14000ad0b  pop     rbx
0x14000ad0c  retn
```
