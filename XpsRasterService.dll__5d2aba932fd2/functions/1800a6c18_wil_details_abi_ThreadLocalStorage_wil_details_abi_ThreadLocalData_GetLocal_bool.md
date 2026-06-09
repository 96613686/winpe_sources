# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800a6c18`
- end: `0x1800a6c6a`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a6db4`

## callees

- `0x1800a6c18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6c21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6c21`

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
0x1800a6c18  push    rbx
0x1800a6c1a  sub     rsp, 20h
0x1800a6c1e  mov     rbx, rcx
0x1800a6c21  call    cs:__imp_GetCurrentThreadId
0x1800a6c27  mov     r9d, eax
0x1800a6c2a  mov     ecx, eax
0x1800a6c2c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800a6c36  shr     r9, 2
0x1800a6c3a  mul     r9
0x1800a6c3d  shr     rdx, 3
0x1800a6c41  lea     r8, [rdx+rdx*4]
0x1800a6c45  add     r8, r8
0x1800a6c48  sub     r9, r8
0x1800a6c4b  mov     rax, [rbx+r9*8]
0x1800a6c4f  jmp     short loc_1800A6C59
0x1800a6c51  cmp     [rax], ecx
0x1800a6c53  jz      short loc_1800A6C64
0x1800a6c55  mov     rax, [rax+8]
0x1800a6c59  test    rax, rax
0x1800a6c5c  jnz     short loc_1800A6C51
0x1800a6c5e  add     rsp, 20h
0x1800a6c62  pop     rbx
0x1800a6c63  retn
0x1800a6c64  add     rax, 10h
0x1800a6c68  jmp     short loc_1800A6C5E
```
