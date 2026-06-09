# common_initialize_environment_nolock<wchar_t>(void)

- ea: `0x140004ac4`
- end: `0x140004b32`
- name: `??$common_initialize_environment_nolock@_W@@YAHXZ`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004d8c`
- `0x140004e0c`
- `0x140004e5c`

## callees

- `0x140004ac4`
- `0x140004b34`
- `0x140006940`
- `0x140007ca4`

## pseudocode

```c
__int64 common_initialize_environment_nolock<wchar_t>()
{
  unsigned int v0; // edi
  __int16 *wide_environment_from_os; // rax
  __int16 *v3; // rbx
  void *v4; // rax

  v0 = 0;
  if ( qword_14001A418 )
    return 0;
  wide_environment_from_os = (__int16 *)_dcrt_get_wide_environment_from_os();
  v3 = wide_environment_from_os;
  if ( wide_environment_from_os )
  {
    v4 = create_environment<wchar_t>(wide_environment_from_os);
    if ( v4 )
    {
      qword_14001A420 = v4;
      qword_14001A418 = v4;
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
0x140004ac4  mov     [rsp+arg_0], rbx
0x140004ac9  push    rdi
0x140004aca  sub     rsp, 20h
0x140004ace  xor     edi, edi
0x140004ad0  cmp     cs:qword_14001A418, rdi
0x140004ad7  jz      short loc_140004ADD
0x140004ad9  xor     eax, eax
0x140004adb  jmp     short loc_140004B27
0x140004add  call    __dcrt_get_wide_environment_from_os
0x140004ae2  mov     rbx, rax
0x140004ae5  test    rax, rax
0x140004ae8  jnz     short loc_140004AF6
0x140004aea  xor     ecx, ecx; Block
0x140004aec  call    _free_base
0x140004af1  or      eax, 0FFFFFFFFh
0x140004af4  jmp     short loc_140004B27
0x140004af6  mov     rcx, rbx
0x140004af9  call    ??$create_environment@_W@@YAQEAPEA_WQEA_W@Z
0x140004afe  test    rax, rax
0x140004b01  jnz     short loc_140004B08
0x140004b03  or      edi, 0FFFFFFFFh
0x140004b06  jmp     short loc_140004B16
0x140004b08  mov     cs:qword_14001A420, rax
0x140004b0f  mov     cs:qword_14001A418, rax
0x140004b16  xor     ecx, ecx; Block
0x140004b18  call    _free_base
0x140004b1d  mov     rcx, rbx; Block
0x140004b20  call    _free_base
0x140004b25  mov     eax, edi
0x140004b27  mov     rbx, [rsp+28h+arg_0]
0x140004b2c  add     rsp, 20h
0x140004b30  pop     rdi
0x140004b31  retn
```
