# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800775bc`
- end: `0x18007760e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180077930`

## callees

- `0x1800775bc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800775c5`
- `KERNEL32!GetCurrentThreadId` at `0x1800775c5`

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
0x1800775bc  push    rbx
0x1800775be  sub     rsp, 20h
0x1800775c2  mov     rbx, rcx
0x1800775c5  call    cs:__imp_GetCurrentThreadId
0x1800775cb  mov     r9d, eax
0x1800775ce  mov     ecx, eax
0x1800775d0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800775da  shr     r9, 2
0x1800775de  mul     r9
0x1800775e1  shr     rdx, 3
0x1800775e5  lea     r8, [rdx+rdx*4]
0x1800775e9  add     r8, r8
0x1800775ec  sub     r9, r8
0x1800775ef  mov     rax, [rbx+r9*8]
0x1800775f3  jmp     short loc_1800775FD
0x1800775f5  cmp     [rax], ecx
0x1800775f7  jz      short loc_180077608
0x1800775f9  mov     rax, [rax+8]
0x1800775fd  test    rax, rax
0x180077600  jnz     short loc_1800775F5
0x180077602  add     rsp, 20h
0x180077606  pop     rbx
0x180077607  retn
0x180077608  add     rax, 10h
0x18007760c  jmp     short loc_180077602
```
