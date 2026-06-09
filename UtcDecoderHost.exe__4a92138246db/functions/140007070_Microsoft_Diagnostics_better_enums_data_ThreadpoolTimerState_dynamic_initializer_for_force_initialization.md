# Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_dynamic_initializer_for___force_initialization__

- ea: `0x140007070`
- end: `0x140007103`
- name: `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007070`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400070b5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400070b5`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 4; ++i )
    {
      v2 = off_14001A090[i];
      `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001A090[i];
      `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140007070  mov     [rsp+arg_0], rbx
0x140007075  mov     [rsp+arg_8], rdi
0x14000707a  push    r14
0x14000707c  sub     rsp, 20h
0x140007080  cmp     cs:?value@?1??_initialized@_data_ThreadpoolTimerState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_initialized(void)'::`2'::value
0x140007087  jnz     short loc_1400070F2
0x140007089  xor     edi, edi
0x14000708b  lea     r14, cs:140000000h
0x140007092  xor     ebx, ebx
0x140007094  mov     rcx, ds:rva off_14001A090[r14+rbx*8]; Str
0x14000709c  lea     rax, rva ?storage@?1??_name_storage@_data_ThreadpoolTimerState@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "NotRunning = 0,Running,RunningAndRunAga"... ...
0x1400070a3  add     rax, rdi
0x1400070a6  lea     rdx, Control; "= \t\n"
0x1400070ad  mov     rva ?value@?1??_name_array@_data_ThreadpoolTimerState@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_name_array(void)'::`2'::value ...
0x1400070b5  call    cs:__imp_strcspn
0x1400070bb  mov     rcx, ds:rva off_14001A090[r14+rbx*8]; "NotRunning = 0" ...
0x1400070c3  add     rax, rdi
0x1400070c6  mov     byte ptr [rax+r14+28260h], 0
0x1400070cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400070d3  inc     rax
0x1400070d6  cmp     byte ptr [rcx+rax], 0
0x1400070da  jnz     short loc_1400070D3
0x1400070dc  inc     rdi
0x1400070df  inc     rbx
0x1400070e2  add     rdi, rax
0x1400070e5  cmp     rbx, 4
0x1400070e9  jb      short loc_140007094
0x1400070eb  mov     cs:?value@?1??_initialized@_data_ThreadpoolTimerState@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ThreadpoolTimerState::_initialized(void)'::`2'::value
0x1400070f2  mov     rbx, [rsp+28h+arg_0]
0x1400070f7  mov     rdi, [rsp+28h+arg_8]
0x1400070fc  add     rsp, 20h
0x140007100  pop     r14
0x140007102  retn
```
