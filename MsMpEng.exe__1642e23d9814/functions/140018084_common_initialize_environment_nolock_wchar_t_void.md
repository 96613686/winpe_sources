# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x140018084`
- end: `0x1400180f2`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `110`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001834c`
- `0x1400183cc`
- `0x14001841c`

## callees

- `0x140018084`
- `0x1400180f4`
- `0x140019930`
- `0x14001dd84`

## pseudocode

```c
__int64 common_initialize_environment_nolock<wchar_t>()
{
  unsigned int v0; // edi
  __int64 wide_environment_from_os; // rax
  void *v3; // rbx
  void *v4; // rax

  v0 = 0;
  if ( qword_14003E4F8 )
    return 0;
  wide_environment_from_os = _dcrt_get_wide_environment_from_os();
  v3 = (void *)wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = (void *)create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      qword_14003E500 = v4;
      qword_14003E4F8 = v4;
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
0x140018084  mov     [rsp+arg_0], rbx
0x140018089  push    rdi
0x14001808a  sub     rsp, 20h
0x14001808e  xor     edi, edi
0x140018090  cmp     cs:qword_14003E4F8, rdi
0x140018097  jz      short loc_14001809D
0x140018099  xor     eax, eax
0x14001809b  jmp     short loc_1400180E7
0x14001809d  call    __dcrt_get_wide_environment_from_os
0x1400180a2  mov     rbx, rax
0x1400180a5  test    rax, rax
0x1400180a8  jnz     short loc_1400180B6
0x1400180aa  xor     ecx, ecx; Block
0x1400180ac  call    _free_base
0x1400180b1  or      eax, 0FFFFFFFFh
0x1400180b4  jmp     short loc_1400180E7
0x1400180b6  mov     rcx, rbx
0x1400180b9  call    ??$create_environment@_W@@YAQEAPEA_WQEA_W@Z
0x1400180be  test    rax, rax
0x1400180c1  jnz     short loc_1400180C8
0x1400180c3  or      edi, 0FFFFFFFFh
0x1400180c6  jmp     short loc_1400180D6
0x1400180c8  mov     cs:qword_14003E500, rax
0x1400180cf  mov     cs:qword_14003E4F8, rax
0x1400180d6  xor     ecx, ecx; Block
0x1400180d8  call    _free_base
0x1400180dd  mov     rcx, rbx; Block
0x1400180e0  call    _free_base
0x1400180e5  mov     eax, edi
0x1400180e7  mov     rbx, [rsp+28h+arg_0]
0x1400180ec  add     rsp, 20h
0x1400180f0  pop     rdi
0x1400180f1  retn
```
