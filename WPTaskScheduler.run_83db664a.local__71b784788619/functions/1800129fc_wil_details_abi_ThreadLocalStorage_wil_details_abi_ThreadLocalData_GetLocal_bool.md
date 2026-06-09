# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800129fc`
- end: `0x180012a4e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d0c`

## callees

- `0x1800129fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a05`

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
0x1800129fc  push    rbx
0x1800129fe  sub     rsp, 20h
0x180012a02  mov     rbx, rcx
0x180012a05  call    cs:__imp_GetCurrentThreadId
0x180012a0b  mov     r9d, eax
0x180012a0e  mov     ecx, eax
0x180012a10  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012a1a  shr     r9, 2
0x180012a1e  mul     r9
0x180012a21  shr     rdx, 3
0x180012a25  lea     r8, [rdx+rdx*4]
0x180012a29  add     r8, r8
0x180012a2c  sub     r9, r8
0x180012a2f  mov     rax, [rbx+r9*8]
0x180012a33  jmp     short loc_180012A3D
0x180012a35  cmp     [rax], ecx
0x180012a37  jz      short loc_180012A48
0x180012a39  mov     rax, [rax+8]
0x180012a3d  test    rax, rax
0x180012a40  jnz     short loc_180012A35
0x180012a42  add     rsp, 20h
0x180012a46  pop     rbx
0x180012a47  retn
0x180012a48  add     rax, 10h
0x180012a4c  jmp     short loc_180012A42
```
