# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140004854`
- end: `0x1400048b1`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004354`

## callees

- `0x140004854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004861`

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
0x140004854  push    rbx
0x140004856  sub     rsp, 20h
0x14000485a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004861  call    cs:__imp_GetCurrentThreadId
0x140004868  nop     dword ptr [rax+rax+00h]
0x14000486d  mov     r8d, eax
0x140004870  mov     r9d, eax
0x140004873  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000487d  shr     r8, 2
0x140004881  mul     r8
0x140004884  shr     rdx, 3
0x140004888  lea     rcx, [rdx+rdx*4]
0x14000488c  add     rcx, rcx
0x14000488f  sub     r8, rcx
0x140004892  mov     rax, [rbx+r8*8]
0x140004896  test    rax, rax
0x140004899  jz      short loc_1400048AA
0x14000489b  cmp     [rax], r9d
0x14000489e  jz      short loc_1400048A6
0x1400048a0  mov     rax, [rax+8]
0x1400048a4  jmp     short loc_140004896
0x1400048a6  add     rax, 10h
0x1400048aa  add     rsp, 20h
0x1400048ae  pop     rbx
0x1400048af  retn
```
