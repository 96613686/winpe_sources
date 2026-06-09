# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18009f7a8`
- end: `0x18009f7fd`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009fa54`

## callees

- `0x18009f7a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f7b1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(a1 + 8 * (CurrentThreadId % 0xAuLL)); result; result = *(_QWORD *)(result + 8) )
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
0x18009f7a8  push    rbx
0x18009f7aa  sub     rsp, 20h
0x18009f7ae  mov     rbx, rcx
0x18009f7b1  call    cs:__imp_GetCurrentThreadId
0x18009f7b8  nop     dword ptr [rax+rax+00h]
0x18009f7bd  mov     r9d, eax
0x18009f7c0  mov     ecx, eax
0x18009f7c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18009f7cc  mul     rcx
0x18009f7cf  shr     rdx, 3
0x18009f7d3  lea     r8, [rdx+rdx*4]
0x18009f7d7  add     r8, r8
0x18009f7da  sub     r9, r8
0x18009f7dd  mov     rax, [rbx+r9*8]
0x18009f7e1  jmp     short loc_18009F7EB
0x18009f7e3  cmp     [rax], ecx
0x18009f7e5  jz      short loc_18009F7F7
0x18009f7e7  mov     rax, [rax+8]
0x18009f7eb  test    rax, rax
0x18009f7ee  jnz     short loc_18009F7E3
0x18009f7f0  add     rsp, 20h
0x18009f7f4  pop     rbx
0x18009f7f5  retn
0x18009f7f7  add     rax, 10h
0x18009f7fb  jmp     short loc_18009F7F0
```
