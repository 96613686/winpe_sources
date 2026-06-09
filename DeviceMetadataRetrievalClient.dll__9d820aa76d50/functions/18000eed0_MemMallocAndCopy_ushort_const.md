# MemMallocAndCopy(ushort const *)

- ea: `0x18000eed0`
- end: `0x18000ef6c`
- name: `?MemMallocAndCopy@@YAPEAGPEBG@Z`
- size: `156`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cb0`
- `0x180003514`
- `0x1800038c8`
- `0x1800064a8`
- `0x18000838c`
- `0x180008d8c`
- `0x18000913c`
- `0x18000a200`
- `0x18000c880`
- `0x18000ca5c`
- `0x18000d64c`
- `0x18000ed9c`
- `0x18000f4c8`

## callees

- `0x180002eb8`
- `0x18000eed0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000ef25`
- `KERNEL32!HeapAlloc` at `0x18000ef25`
- `KERNEL32!GetProcessHeap` at `0x18000ef16`
- `KERNEL32!GetProcessHeap` at `0x18000ef45`
- `KERNEL32!GetProcessHeap` at `0x18000ef16`
- `KERNEL32!GetProcessHeap` at `0x18000ef45`
- `KERNEL32!HeapFree` at `0x18000ef53`
- `KERNEL32!HeapFree` at `0x18000ef53`

## pseudocode

```c
unsigned __int16 *__fastcall MemMallocAndCopy(const unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  unsigned __int64 v4; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  HANDLE v8; // rax

  if ( !a1 )
    return 0;
  v2 = a1;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  if ( !v3 )
    return 0;
  v4 = ((0x7FFFFFFF - v3) & -(__int64)(v3 != 0)) + 1;
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, (unsigned int)(2 * v4));
  v7 = v6;
  if ( v6 )
  {
    if ( (int)StringCchCopyW(v6, v4, a1) < 0 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v7);
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000eed0  push    rbx
0x18000eed2  push    rbp
0x18000eed3  push    rsi
0x18000eed4  push    rdi
0x18000eed5  sub     rsp, 28h
0x18000eed9  xor     ebp, ebp
0x18000eedb  mov     rdi, rcx
0x18000eede  test    rcx, rcx
0x18000eee1  jz      short loc_18000EF61
0x18000eee3  mov     r8d, 7FFFFFFFh
0x18000eee9  mov     rax, rcx
0x18000eeec  mov     edx, r8d
0x18000eeef  cmp     [rax], bp
0x18000eef2  jz      short loc_18000EEFE
0x18000eef4  add     rax, 2
0x18000eef8  sub     rdx, 1
0x18000eefc  jnz     short loc_18000EEEF
0x18000eefe  sub     r8, rdx
0x18000ef01  mov     rax, rdx
0x18000ef04  neg     rax
0x18000ef07  sbb     rcx, rcx
0x18000ef0a  and     rcx, r8
0x18000ef0d  test    rdx, rdx
0x18000ef10  jz      short loc_18000EF61
0x18000ef12  lea     rsi, [rcx+1]
0x18000ef16  call    cs:__imp_GetProcessHeap
0x18000ef1c  lea     r8d, [rsi+rsi]; dwBytes
0x18000ef20  xor     edx, edx; dwFlags
0x18000ef22  mov     rcx, rax; hHeap
0x18000ef25  call    cs:__imp_HeapAlloc
0x18000ef2b  mov     rbx, rax
0x18000ef2e  test    rax, rax
0x18000ef31  jz      short loc_18000EF5C
0x18000ef33  mov     r8, rdi; unsigned __int16 *
0x18000ef36  mov     rdx, rsi; unsigned __int64
0x18000ef39  mov     rcx, rax; unsigned __int16 *
0x18000ef3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ef41  test    eax, eax
0x18000ef43  jns     short loc_18000EF5C
0x18000ef45  call    cs:__imp_GetProcessHeap
0x18000ef4b  mov     r8, rbx; lpMem
0x18000ef4e  xor     edx, edx; dwFlags
0x18000ef50  mov     rcx, rax; hHeap
0x18000ef53  call    cs:__imp_HeapFree
0x18000ef59  mov     rbx, rbp
0x18000ef5c  mov     rax, rbx
0x18000ef5f  jmp     short loc_18000EF63
0x18000ef61  xor     eax, eax
0x18000ef63  add     rsp, 28h
0x18000ef67  pop     rdi
0x18000ef68  pop     rsi
0x18000ef69  pop     rbp
0x18000ef6a  pop     rbx
0x18000ef6b  retn
```
