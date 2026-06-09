# std::vector<DISPLAYCONFIG_MODE_INFO,std::allocator<DISPLAYCONFIG_MODE_INFO>>::_Construct_n<>(unsigned __int64)

- ea: `0x14000df24`
- end: `0x14000df84`
- name: `??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e7e4`

## callees

- `0x1400061b8`
- `0x14000df24`
- `0x14000e15c`
- `0x14000efa4`

## pseudocode

```c
__int64 __fastcall std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  char *v4; // rdi
  int v5; // edx
  __int64 result; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    v2 = a2;
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Buy_nonzero();
    v4 = (char *)*a1;
    LOBYTE(v5) = 0;
    memset_0(*a1, v5, v2 << 6);
    do
    {
      v4 += 64;
      --v2;
    }
    while ( v2 );
    a1[1] = v4;
    v7 = 0;
    return std::_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000df24  test    rdx, rdx
0x14000df27  jz      short locret_14000DF83
0x14000df29  mov     [rsp+arg_8], rbx
0x14000df2e  mov     [rsp+arg_10], rsi
0x14000df33  push    rdi
0x14000df34  sub     rsp, 20h
0x14000df38  mov     rbx, rdx
0x14000df3b  mov     rsi, rcx
0x14000df3e  call    ?_Buy_nonzero@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Buy_nonzero(unsigned __int64)
0x14000df43  mov     rdi, [rsi]
0x14000df46  mov     r8, rbx
0x14000df49  shl     r8, 6; Size
0x14000df4d  xor     dl, dl; Val
0x14000df4f  mov     rcx, rdi; void *
0x14000df52  call    memset_0
0x14000df57  add     rdi, 40h ; '@'
0x14000df5b  sub     rbx, 1
0x14000df5f  jnz     short loc_14000DF57
0x14000df61  lea     rcx, [rsp+28h+arg_0]
0x14000df66  mov     [rsi+8], rdi
0x14000df6a  mov     [rsp+28h+arg_0], rbx
0x14000df6f  call    ??1?$_Tidy_guard@V?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>(void)
0x14000df74  mov     rbx, [rsp+28h+arg_8]
0x14000df79  mov     rsi, [rsp+28h+arg_10]
0x14000df7e  add     rsp, 20h
0x14000df82  pop     rdi
0x14000df83  retn
```
