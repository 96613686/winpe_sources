# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180009fc8`
- end: `0x18000a035`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x1800100cc`
- `0x180013344`
- `0x18001584c`
- `0x180016948`
- `0x180018360`
- `0x18001cdc0`
- `0x180020088`
- `0x18002028c`
- `0x1800229a0`

## callees

- `0x180002c04`
- `0x180007710`
- `0x180009fc8`
- `0x18000a7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ffd`

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
0x180009fc8  push    rbx
0x180009fca  sub     rsp, 0C0h
0x180009fd1  cmp     dword ptr [rcx+18h], 0
0x180009fd5  mov     rbx, rcx
0x180009fd8  jnz     short loc_18000A018
0x180009fda  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009fe2  jz      short loc_18000A008
0x180009fe4  mov     dl, 1
0x180009fe6  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009feb  mov     [rbx], rax
0x180009fee  test    rax, rax
0x180009ff1  jz      short loc_18000A00F
0x180009ff3  mov     rcx, [rax]
0x180009ff6  mov     [rbx+10h], rcx
0x180009ffa  mov     [rax], rbx
0x180009ffd  call    cs:__imp_GetCurrentThreadId
0x18000a003  mov     [rbx+18h], eax
0x18000a006  jmp     short loc_18000A00F
0x18000a008  mov     qword ptr [rcx], 0
0x18000a00f  add     rsp, 0C0h
0x18000a016  pop     rbx
0x18000a017  retn
0x18000a018  xor     edx, edx; Val
0x18000a01a  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000a01f  mov     r8d, 98h; Size
0x18000a025  call    memset_0
0x18000a02a  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000a02f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
