# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x14002282c`
- end: `0x14002289a`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `110`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140022a78`

## callees

- `0x1400107c4`
- `0x14002282c`
- `0x14002289c`
- `0x140023bc8`

## pseudocode

```c
__int64 common_initialize_environment_nolock<wchar_t>()
{
  unsigned int v0; // edi
  wchar_t *wide_environment_from_os; // rax
  wchar_t *v3; // rbx
  void *v4; // rax

  v0 = 0;
  if ( qword_1400D7BA8 )
    return 0;
  wide_environment_from_os = (wchar_t *)_dcrt_get_wide_environment_from_os();
  v3 = wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = (void *)create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      qword_1400D7BB0 = v4;
      qword_1400D7BA8 = (__int64)v4;
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
0x14002282c  mov     [rsp+arg_0], rbx
0x140022831  push    rdi
0x140022832  sub     rsp, 20h
0x140022836  xor     edi, edi
0x140022838  cmp     cs:qword_1400D7BA8, rdi
0x14002283f  jz      short loc_140022845
0x140022841  xor     eax, eax
0x140022843  jmp     short loc_14002288F
0x140022845  call    __dcrt_get_wide_environment_from_os
0x14002284a  mov     rbx, rax
0x14002284d  test    rax, rax
0x140022850  jnz     short loc_14002285E
0x140022852  xor     ecx, ecx; Block
0x140022854  call    _free_base
0x140022859  or      eax, 0FFFFFFFFh
0x14002285c  jmp     short loc_14002288F
0x14002285e  mov     rcx, rbx; Source
0x140022861  call    ??$create_environment@_W@@YAQEAPEA_WQEA_W@Z
0x140022866  test    rax, rax
0x140022869  jnz     short loc_140022870
0x14002286b  or      edi, 0FFFFFFFFh
0x14002286e  jmp     short loc_14002287E
0x140022870  mov     cs:qword_1400D7BB0, rax
0x140022877  mov     cs:qword_1400D7BA8, rax
0x14002287e  xor     ecx, ecx; Block
0x140022880  call    _free_base
0x140022885  mov     rcx, rbx; Block
0x140022888  call    _free_base
0x14002288d  mov     eax, edi
0x14002288f  mov     rbx, [rsp+28h+arg_0]
0x140022894  add     rsp, 20h
0x140022898  pop     rdi
0x140022899  retn
```
