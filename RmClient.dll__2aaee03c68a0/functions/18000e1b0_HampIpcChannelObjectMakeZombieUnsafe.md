# HampIpcChannelObjectMakeZombieUnsafe

- ea: `0x18000e1b0`
- end: `0x18000e230`
- name: `HampIpcChannelObjectMakeZombieUnsafe`
- size: `128`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800049fc`

## callees

- `0x18000e1b0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e222`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1f3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e1f3`
- `ntdll!RtlRbRemoveNode` at `0x18000e1c7`
- `ntdll!RtlRbRemoveNode` at `0x18000e1c7`
- `ntdll!TpPostWork` at `0x18000e20e`
- `ntdll!TpPostWork` at `0x18000e20e`

## pseudocode

```c
__int64 __fastcall HampIpcChannelObjectMakeZombieUnsafe(__int64 a1, __int64 *a2)
{
  __int64 **v4; // rdx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rcx

  RtlRbRemoveNode(a2 + 3, a1);
  v4 = (__int64 **)a2[6];
  if ( *v4 != a2 + 5 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 24) = a2 + 5;
  *(_QWORD *)(a1 + 32) = v4;
  *v4 = (__int64 *)(a1 + 24);
  a2[6] = a1 + 24;
  v5 = *a2;
  RtlAcquireSRWLockExclusive(v5 + 32);
  *(_DWORD *)(v5 + 64) |= 2u;
  v6 = *(_DWORD *)(v5 + 64);
  if ( (v6 & 1) == 0 )
  {
    v7 = *(_QWORD *)(v5 + 56);
    *(_DWORD *)(v5 + 64) = v6 | 1;
    TpPostWork(v7);
  }
  return RtlReleaseSRWLockExclusive(v5 + 32);
}

```

## disassembly

```asm
0x18000e1b0  mov     [rsp+arg_0], rbx
0x18000e1b5  push    rdi
0x18000e1b6  sub     rsp, 20h
0x18000e1ba  mov     rdi, rcx
0x18000e1bd  mov     rbx, rdx
0x18000e1c0  lea     rcx, [rdx+18h]
0x18000e1c4  mov     rdx, rdi
0x18000e1c7  call    cs:__imp_RtlRbRemoveNode
0x18000e1cd  mov     rdx, [rbx+30h]
0x18000e1d1  lea     r8, [rbx+28h]
0x18000e1d5  cmp     [rdx], r8
0x18000e1d8  jnz     short loc_18000E229
0x18000e1da  lea     rax, [rdi+18h]
0x18000e1de  mov     [rax], r8
0x18000e1e1  mov     [rax+8], rdx
0x18000e1e5  mov     [rdx], rax
0x18000e1e8  mov     [r8+8], rax
0x18000e1ec  mov     rbx, [rbx]
0x18000e1ef  lea     rcx, [rbx+20h]
0x18000e1f3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e1f9  or      dword ptr [rbx+40h], 2
0x18000e1fd  mov     eax, [rbx+40h]
0x18000e200  test    al, 1
0x18000e202  jnz     short loc_18000E214
0x18000e204  mov     rcx, [rbx+38h]
0x18000e208  or      eax, 1
0x18000e20b  mov     [rbx+40h], eax
0x18000e20e  call    cs:__imp_TpPostWork
0x18000e214  lea     rcx, [rbx+20h]
0x18000e218  mov     rbx, [rsp+28h+arg_0]
0x18000e21d  add     rsp, 20h
0x18000e221  pop     rdi
0x18000e222  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x18000e229  mov     ecx, 3
0x18000e22e  int     29h; Win8: RtlFailFast(ecx)
```
