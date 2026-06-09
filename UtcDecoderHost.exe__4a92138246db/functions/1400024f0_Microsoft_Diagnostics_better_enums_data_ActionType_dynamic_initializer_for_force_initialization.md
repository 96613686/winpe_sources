# Microsoft::Diagnostics::better_enums::_data_ActionType::_dynamic_initializer_for___force_initialization__

- ea: `0x1400024f0`
- end: `0x140002583`
- name: `Microsoft::Diagnostics::better_enums::_data_ActionType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400024f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002535`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140002535`

## string_xrefs

- `0x14000251c`: `CreateSif,Delay,EnableRadar,GetAgentDiagnostics,GetAppxPackage,GetFile,GetFileInfo,GetKernelDump,GetMemoryInfo,GetProcessDump,GetRegKey,GetShutdownTrace,GetWnfState,Notify,Radar,RunExeWithArgs,SetRegKey,SnapAlwaysOnTrace,SnapRadar,SnapSnapshot,SnapTrace,SoftLanding,StartImpersonation,StartSnapshot,StartTraceAction,StartTimeTravelDebugging,StopImpersonation,StopSnapshot,StopTimeTravelDebugging,StopTraceAction,ToggleTrace,SnapFileBackedTrace,GetContainerMemoryState,AzureOneTraceAction,`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ActionType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ActionType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x22; ++i )
    {
      v2 = off_140019EB0[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ActionType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019EB0[i];
      `Microsoft::Diagnostics::better_enums::_data_ActionType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ActionType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x1400024f0  mov     [rsp+arg_0], rbx
0x1400024f5  mov     [rsp+arg_8], rdi
0x1400024fa  push    r14
0x1400024fc  sub     rsp, 20h
0x140002500  cmp     cs:?value@?1??_initialized@_data_ActionType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ActionType::_initialized(void)'::`2'::value
0x140002507  jnz     short loc_140002572
0x140002509  xor     edi, edi
0x14000250b  lea     r14, cs:140000000h
0x140002512  xor     ebx, ebx
0x140002514  mov     rcx, ds:rva off_140019EB0[r14+rbx*8]; Str
0x14000251c  lea     rax, rva ?storage@?1??_name_storage@_data_ActionType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "CreateSif,Delay,EnableRadar,GetAgentDia"... ...
0x140002523  add     rax, rdi
0x140002526  lea     rdx, Control; "= \t\n"
0x14000252d  mov     rva ?value@?1??_name_array@_data_ActionType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ActionType::_name_array(void)'::`2'::value ...
0x140002535  call    cs:__imp_strcspn
0x14000253b  mov     rcx, ds:rva off_140019EB0[r14+rbx*8]; "CreateSif" ...
0x140002543  add     rax, rdi
0x140002546  mov     byte ptr [rax+r14+28050h], 0
0x14000254f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002553  inc     rax
0x140002556  cmp     byte ptr [rcx+rax], 0
0x14000255a  jnz     short loc_140002553
0x14000255c  inc     rdi
0x14000255f  inc     rbx
0x140002562  add     rdi, rax
0x140002565  cmp     rbx, 22h ; '"'
0x140002569  jb      short loc_140002514
0x14000256b  mov     cs:?value@?1??_initialized@_data_ActionType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ActionType::_initialized(void)'::`2'::value
0x140002572  mov     rbx, [rsp+28h+arg_0]
0x140002577  mov     rdi, [rsp+28h+arg_8]
0x14000257c  add     rsp, 20h
0x140002580  pop     r14
0x140002582  retn
```
