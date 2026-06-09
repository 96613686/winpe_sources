# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18004ac30`
- end: `0x18004ac82`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004aeb0`

## callees

- `0x18004ac30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ac39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ac39`

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
0x18004ac30  push    rbx
0x18004ac32  sub     rsp, 20h
0x18004ac36  mov     rbx, rcx
0x18004ac39  call    cs:__imp_GetCurrentThreadId
0x18004ac3f  mov     r9d, eax
0x18004ac42  mov     ecx, eax
0x18004ac44  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004ac4e  shr     r9, 2
0x18004ac52  mul     r9
0x18004ac55  shr     rdx, 3
0x18004ac59  lea     r8, [rdx+rdx*4]
0x18004ac5d  add     r8, r8
0x18004ac60  sub     r9, r8
0x18004ac63  mov     rax, [rbx+r9*8]
0x18004ac67  jmp     short loc_18004AC71
0x18004ac69  cmp     [rax], ecx
0x18004ac6b  jz      short loc_18004AC7C
0x18004ac6d  mov     rax, [rax+8]
0x18004ac71  test    rax, rax
0x18004ac74  jnz     short loc_18004AC69
0x18004ac76  add     rsp, 20h
0x18004ac7a  pop     rbx
0x18004ac7b  retn
0x18004ac7c  add     rax, 10h
0x18004ac80  jmp     short loc_18004AC76
```
