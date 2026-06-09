# update_tree_estimates

- ea: `0x140011304`
- end: `0x14001136d`
- name: `update_tree_estimates`
- size: `105`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140004770`

## callees

- `0x1400057ec`
- `0x1400097c0`
- `0x14000bf78`
- `0x14000c820`
- `0x140011304`

## pseudocode

```c
__int64 __fastcall update_tree_estimates(_DWORD *a1)
{
  __int64 result; // rax
  int v3; // ecx

  if ( a1[14] )
  {
    if ( a1[620] )
    {
      get_block_stats();
      a1[620] = 0;
    }
    else
    {
      tally_frequency(a1, (unsigned int)a1[2398], (unsigned int)a1[2399]);
    }
    create_trees((__int64)a1, 0);
    fix_tree_cost_estimates((__int64)a1);
    result = (unsigned int)a1[15];
    v3 = a1[14];
    a1[2399] = result;
    a1[2398] = v3;
  }
  return result;
}

```

## disassembly

```asm
0x140011304  push    rbx
0x140011306  sub     rsp, 20h
0x14001130a  mov     r9d, [rcx+38h]
0x14001130e  mov     rbx, rcx
0x140011311  test    r9d, r9d
0x140011314  jz      short loc_140011366
0x140011316  cmp     dword ptr [rcx+9B0h], 0
0x14001131d  jz      short loc_140011330
0x14001131f  call    get_block_stats
0x140011324  mov     dword ptr [rbx+9B0h], 0
0x14001132e  jmp     short loc_140011342
0x140011330  mov     r8d, [rcx+257Ch]
0x140011337  mov     edx, [rcx+2578h]
0x14001133d  call    tally_frequency
0x140011342  xor     edx, edx
0x140011344  mov     rcx, rbx
0x140011347  call    create_trees
0x14001134c  mov     rcx, rbx
0x14001134f  call    fix_tree_cost_estimates
0x140011354  mov     eax, [rbx+3Ch]
0x140011357  mov     ecx, [rbx+38h]
0x14001135a  mov     [rbx+257Ch], eax
0x140011360  mov     [rbx+2578h], ecx
0x140011366  add     rsp, 20h
0x14001136a  pop     rbx
0x14001136b  retn
```
