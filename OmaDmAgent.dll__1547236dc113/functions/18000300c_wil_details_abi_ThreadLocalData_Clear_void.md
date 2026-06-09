# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x18000300c`
- end: `0x1800030a1`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c70`

## callees

- `0x18000300c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003031`
- `KERNEL32!GetProcessHeap` at `0x18000306e`
- `KERNEL32!GetProcessHeap` at `0x180003031`
- `KERNEL32!GetProcessHeap` at `0x18000306e`
- `KERNEL32!HeapFree` at `0x180003045`
- `KERNEL32!HeapFree` at `0x180003082`
- `KERNEL32!HeapFree` at `0x180003045`
- `KERNEL32!HeapFree` at `0x180003082`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000300c  push    rbx
0x18000300e  push    rbp
0x18000300f  push    rsi
0x180003010  push    rdi
0x180003011  sub     rsp, 28h
0x180003015  movzx   eax, word ptr [rcx+20h]
0x180003019  mov     rsi, rcx
0x18000301c  mov     rdi, [rcx+18h]
0x180003020  lea     rbp, [rax+rax*4]
0x180003024  shl     rbp, 4
0x180003028  add     rbp, rdi
0x18000302b  jmp     short loc_180003065
0x18000302d  mov     rbx, [rdi+40h]
0x180003031  call    cs:__imp_GetProcessHeap
0x180003038  nop     dword ptr [rax+rax+00h]
0x18000303d  mov     r8, rbx; lpMem
0x180003040  xor     edx, edx; dwFlags
0x180003042  mov     rcx, rax; hHeap
0x180003045  call    cs:__imp_HeapFree
0x18000304c  nop     dword ptr [rax+rax+00h]
0x180003051  mov     qword ptr [rdi+40h], 0
0x180003059  mov     qword ptr [rdi+48h], 0
0x180003061  add     rdi, 50h ; 'P'
0x180003065  cmp     rdi, rbp
0x180003068  jnz     short loc_18000302D
0x18000306a  mov     rbx, [rsi+18h]
0x18000306e  call    cs:__imp_GetProcessHeap
0x180003075  nop     dword ptr [rax+rax+00h]
0x18000307a  mov     r8, rbx; lpMem
0x18000307d  xor     edx, edx; dwFlags
0x18000307f  mov     rcx, rax; hHeap
0x180003082  call    cs:__imp_HeapFree
0x180003089  nop     dword ptr [rax+rax+00h]
0x18000308e  xor     eax, eax
0x180003090  mov     [rsi+20h], eax
0x180003093  mov     [rsi+18h], rax
0x180003097  add     rsp, 28h
0x18000309b  pop     rdi
0x18000309c  pop     rsi
0x18000309d  pop     rbp
0x18000309e  pop     rbx
0x18000309f  retn
```
