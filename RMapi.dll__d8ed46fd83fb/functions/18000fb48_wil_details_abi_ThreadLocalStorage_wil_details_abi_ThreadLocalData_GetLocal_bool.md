# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000fb48`
- end: `0x18000fb98`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dfc`

## callees

- `0x18000fb48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb51`

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
0x18000fb48  push    rbx
0x18000fb4a  sub     rsp, 20h
0x18000fb4e  mov     rbx, rcx
0x18000fb51  call    cs:__imp_GetCurrentThreadId
0x18000fb57  mov     r9d, eax
0x18000fb5a  mov     ecx, eax
0x18000fb5c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000fb66  shr     r9, 2
0x18000fb6a  mul     r9
0x18000fb6d  shr     rdx, 3
0x18000fb71  lea     r8, [rdx+rdx*4]
0x18000fb75  add     r8, r8
0x18000fb78  sub     r9, r8
0x18000fb7b  mov     rax, [rbx+r9*8]
0x18000fb7f  test    rax, rax
0x18000fb82  jz      short loc_18000FB92
0x18000fb84  cmp     [rax], ecx
0x18000fb86  jz      short loc_18000FB8E
0x18000fb88  mov     rax, [rax+8]
0x18000fb8c  jmp     short loc_18000FB7F
0x18000fb8e  add     rax, 10h
0x18000fb92  add     rsp, 20h
0x18000fb96  pop     rbx
0x18000fb97  retn
```
