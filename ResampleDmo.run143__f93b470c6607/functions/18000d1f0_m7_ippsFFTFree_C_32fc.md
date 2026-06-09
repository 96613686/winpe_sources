# m7_ippsFFTFree_C_32fc

- ea: `0x18000d1f0`
- end: `0x18000d209`
- name: `m7_ippsFFTFree_C_32fc`
- size: `25`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180047978`
- `0x180047a70`
- `0x180047f10`
- `0x180048120`
- `0x180048d70`
- `0x180048f80`
- `0x180049b00`
- `0x180049d10`

## callees

- `0x18000d1f0`
- `0x180011020`

## pseudocode

```c
__int64 __fastcall m7_ippsFFTFree_C_32fc(_DWORD *a1)
{
  *a1 = 0;
  if ( a1[7] == 1 )
    m7_ippsFree((__int64)a1);
  return 0;
}

```

## disassembly

```asm
0x18000d1f0  sub     rsp, 28h
0x18000d1f4  and     dword ptr [rcx], 0
0x18000d1f7  cmp     dword ptr [rcx+1Ch], 1
0x18000d1fb  jnz     short loc_18000D202
0x18000d1fd  call    m7_ippsFree
0x18000d202  xor     eax, eax
0x18000d204  add     rsp, 28h
0x18000d208  retn
```
