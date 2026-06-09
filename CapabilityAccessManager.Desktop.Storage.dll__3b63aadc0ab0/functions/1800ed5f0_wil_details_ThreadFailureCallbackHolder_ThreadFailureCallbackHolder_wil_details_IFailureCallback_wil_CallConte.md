# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x1800ed5f0`
- end: `0x1800ed655`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `101`
- prototype: `wil::details::ThreadFailureCallbackHolder *__fastcall(wil::details::ThreadFailureCallbackHolder *this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800f8388`
- `0x180108030`

## callees

- `0x1800e8310`
- `0x1800ed5f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed643`

## pseudocode

```c
wil::details::ThreadFailureCallbackHolder *__fastcall wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this,
        struct wil::details::IFailureCallback *a2,
        struct wil::CallContextInfo *a3,
        char a4)
{
  _QWORD *Local; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_BYTE *)this + 40) = 0;
  if ( a4 )
  {
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
  }
  return this;
}

```

## disassembly

```asm
0x1800ed5f0  push    rbx
0x1800ed5f2  sub     rsp, 20h
0x1800ed5f6  mov     rbx, rcx
0x1800ed5f9  mov     qword ptr [rcx], 0
0x1800ed600  mov     [rcx+8], rdx
0x1800ed604  mov     qword ptr [rcx+10h], 0
0x1800ed60c  mov     dword ptr [rcx+18h], 0
0x1800ed613  mov     [rcx+20h], r8
0x1800ed617  mov     byte ptr [rcx+28h], 0
0x1800ed61b  test    r9b, r9b
0x1800ed61e  jz      short loc_1800ED64C
0x1800ed620  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800ed628  jz      short loc_1800ED64C
0x1800ed62a  mov     dl, 1
0x1800ed62c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800ed631  mov     [rbx], rax
0x1800ed634  test    rax, rax
0x1800ed637  jz      short loc_1800ED64C
0x1800ed639  mov     rcx, [rax]
0x1800ed63c  mov     [rbx+10h], rcx
0x1800ed640  mov     [rax], rbx
0x1800ed643  call    cs:__imp_GetCurrentThreadId
0x1800ed649  mov     [rbx+18h], eax
0x1800ed64c  mov     rax, rbx
0x1800ed64f  add     rsp, 20h
0x1800ed653  pop     rbx
0x1800ed654  retn
```
