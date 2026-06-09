# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18004bcf4`
- end: `0x18004bd4b`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004bc34`

## callees

- `0x18004bcf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bcfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bcfd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(a1 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
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
0x18004bcf4  push    rbx
0x18004bcf6  sub     rsp, 20h
0x18004bcfa  mov     rbx, rcx
0x18004bcfd  call    cs:__imp_GetCurrentThreadId
0x18004bd04  nop     dword ptr [rax+rax+00h]
0x18004bd09  mov     r9d, eax
0x18004bd0c  mov     ecx, eax
0x18004bd0e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004bd18  shr     r9, 2
0x18004bd1c  mul     r9
0x18004bd1f  shr     rdx, 3
0x18004bd23  lea     r8, [rdx+rdx*4]
0x18004bd27  add     r8, r8
0x18004bd2a  sub     r9, r8
0x18004bd2d  mov     rax, [rbx+r9*8]
0x18004bd31  test    rax, rax
0x18004bd34  jz      short loc_18004BD44
0x18004bd36  cmp     [rax], ecx
0x18004bd38  jz      short loc_18004BD40
0x18004bd3a  mov     rax, [rax+8]
0x18004bd3e  jmp     short loc_18004BD31
0x18004bd40  add     rax, 10h
0x18004bd44  add     rsp, 20h
0x18004bd48  pop     rbx
0x18004bd49  retn
```
