# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x14000c618`
- end: `0x14000c61d`
- name: `j_??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000bfc8`

## callees

- `0x14000c568`

## pseudocode

```c
// attributes: thunk
LARGE_INTEGER __fastcall common_lseek_nolock<__int64>(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  return ??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000c618  jmp     ??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z
```
