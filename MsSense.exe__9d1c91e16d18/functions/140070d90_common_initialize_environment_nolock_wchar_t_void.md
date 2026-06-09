# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x140070d90`
- end: `0x140070dfe`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `110`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140071058`
- `0x1400710d8`
- `0x140071128`

## callees

- `0x140070d90`
- `0x140070e00`
- `0x140072280`
- `0x14007b434`

## pseudocode

```c
__int64 common_initialize_environment_nolock<wchar_t>()
{
  unsigned int v0; // edi
  __int64 wide_environment_from_os; // rax
  void *v3; // rbx
  void *v4; // rax

  v0 = 0;
  if ( Block )
    return 0;
  wide_environment_from_os = _dcrt_get_wide_environment_from_os();
  v3 = (void *)wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = (void *)create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      qword_1400C4880 = v4;
      Block = v4;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
    free_base(v3);
    return v0;
  }
  else
  {
    free_base(0);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x140070d90  mov     [rsp+arg_0], rbx
0x140070d95  push    rdi
0x140070d96  sub     rsp, 20h
0x140070d9a  xor     edi, edi
0x140070d9c  cmp     cs:Block, rdi
0x140070da3  jz      short loc_140070DA9
0x140070da5  xor     eax, eax
0x140070da7  jmp     short loc_140070DF3
0x140070da9  call    __dcrt_get_wide_environment_from_os
0x140070dae  mov     rbx, rax
0x140070db1  test    rax, rax
0x140070db4  jnz     short loc_140070DC2
0x140070db6  xor     ecx, ecx; Block
0x140070db8  call    _free_base
0x140070dbd  or      eax, 0FFFFFFFFh
0x140070dc0  jmp     short loc_140070DF3
0x140070dc2  mov     rcx, rbx
0x140070dc5  call    ??$create_environment@_W@@YAQEAPEA_WQEA_W@Z
0x140070dca  test    rax, rax
0x140070dcd  jnz     short loc_140070DD4
0x140070dcf  or      edi, 0FFFFFFFFh
0x140070dd2  jmp     short loc_140070DE2
0x140070dd4  mov     cs:qword_1400C4880, rax
0x140070ddb  mov     cs:Block, rax
0x140070de2  xor     ecx, ecx; Block
0x140070de4  call    _free_base
0x140070de9  mov     rcx, rbx; Block
0x140070dec  call    _free_base
0x140070df1  mov     eax, edi
0x140070df3  mov     rbx, [rsp+28h+arg_0]
0x140070df8  add     rsp, 20h
0x140070dfc  pop     rdi
0x140070dfd  retn
```
