# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x140007304`
- end: `0x140007354`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400072ac`

## callees

- `0x140007304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000730d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000730d`

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
0x140007304  push    rbx
0x140007306  sub     rsp, 20h
0x14000730a  mov     rbx, rcx
0x14000730d  call    cs:__imp_GetCurrentThreadId
0x140007313  mov     r9d, eax
0x140007316  mov     ecx, eax
0x140007318  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140007322  shr     r9, 2
0x140007326  mul     r9
0x140007329  shr     rdx, 3
0x14000732d  lea     r8, [rdx+rdx*4]
0x140007331  add     r8, r8
0x140007334  sub     r9, r8
0x140007337  mov     rax, [rbx+r9*8]
0x14000733b  test    rax, rax
0x14000733e  jz      short loc_14000734E
0x140007340  cmp     [rax], ecx
0x140007342  jz      short loc_14000734A
0x140007344  mov     rax, [rax+8]
0x140007348  jmp     short loc_14000733B
0x14000734a  add     rax, 10h
0x14000734e  add     rsp, 20h
0x140007352  pop     rbx
0x140007353  retn
```
