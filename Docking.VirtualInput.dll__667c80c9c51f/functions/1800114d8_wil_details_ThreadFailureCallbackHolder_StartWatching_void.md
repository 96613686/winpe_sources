# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1800114d8`
- end: `0x1800115a5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `205`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c5e0`
- `0x18000dd10`

## callees

- `0x180005988`
- `0x180007148`
- `0x1800114d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001158b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001158b`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        const struct wil::FailureInfo *a2)
{
  __int64 Local; // [rsp+20h] [rbp-B8h]
  _BYTE v3[168]; // [rsp+30h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset(v3, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v3, a2);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
              wil::details::g_pThreadFailureCallbacks,
              a2);
  }
  else
  {
    Local = 0;
  }
  *(_QWORD *)this = Local;
  if ( *(_QWORD *)this )
  {
    *((_QWORD *)this + 2) = **(_QWORD **)this;
    **(_QWORD **)this = this;
    *((_DWORD *)this + 6) = GetCurrentThreadId();
  }
}

```

## disassembly

```asm
0x1800114d8  mov     [rsp+arg_0], rcx
0x1800114dd  push    rdi
0x1800114de  sub     rsp, 0D0h
0x1800114e5  mov     rax, [rsp+0D8h+arg_0]
0x1800114ed  cmp     dword ptr [rax+18h], 0
0x1800114f1  jz      short loc_18001150F
0x1800114f3  lea     rax, [rsp+0D8h+var_A8]
0x1800114f8  mov     rdi, rax
0x1800114fb  xor     eax, eax
0x1800114fd  mov     ecx, 98h
0x180011502  rep stosb
0x180011504  lea     rcx, [rsp+0D8h+var_A8]; this
0x180011509  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001150f  xor     eax, eax
0x180011511  test    eax, eax
0x180011513  jnz     short loc_1800114E5
0x180011515  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001151d  jz      short loc_180011534
0x18001151f  mov     dl, 1
0x180011521  mov     rcx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011528  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001152d  mov     [rsp+0D8h+var_B8], rax
0x180011532  jmp     short loc_18001153D
0x180011534  mov     [rsp+0D8h+var_B8], 0
0x18001153d  mov     rax, [rsp+0D8h+arg_0]
0x180011545  mov     rcx, [rsp+0D8h+var_B8]
0x18001154a  mov     [rax], rcx
0x18001154d  mov     rax, [rsp+0D8h+arg_0]
0x180011555  cmp     qword ptr [rax], 0
0x180011559  jz      short loc_18001159C
0x18001155b  mov     rax, [rsp+0D8h+arg_0]
0x180011563  mov     rax, [rax]
0x180011566  mov     rcx, [rsp+0D8h+arg_0]
0x18001156e  mov     rax, [rax]
0x180011571  mov     [rcx+10h], rax
0x180011575  mov     rax, [rsp+0D8h+arg_0]
0x18001157d  mov     rax, [rax]
0x180011580  mov     rcx, [rsp+0D8h+arg_0]
0x180011588  mov     [rax], rcx
0x18001158b  call    cs:__imp_GetCurrentThreadId
0x180011591  mov     rcx, [rsp+0D8h+arg_0]
0x180011599  mov     [rcx+18h], eax
0x18001159c  add     rsp, 0D0h
0x1800115a3  pop     rdi
0x1800115a4  retn
```
