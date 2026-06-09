# Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_dynamic_initializer_for___force_initialization__

- ea: `0x140006040`
- end: `0x1400060d3`
- name: `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140006040`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006085`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006085`

## string_xrefs

- `0x14000606c`: `Invalid,Scenario,EtwTrigger,TimeTrigger,SyntheticTrigger,RegistryKeyFilter,FileInfoFilter,ServiceStatusFilter,TelemetryProtocolFilter,SinglePropertyFilter,DualPropertyFilter,ScriptFilter,CreateSif,Delay,EnableRadar,GetAppxPackage,GetFile,GetFileInfo,GetKernelDump,GetMemoryInfo,GetProcessDump,GetRegKey,GetShutdownTrace,GetWnfState,Radar,RunExeWithArgs,SetRegKey,SnapAlwaysOnTrace,SnapRadar,SnapSnapshot,SnapTrace,SoftLanding,StartImpersonation,StartSnapshot,StartTraceAction,StartTimeTravelDebugging`

## pseudocode

```c
void Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x35; ++i )
    {
      v2 = off_14001AB60[i];
      `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_14001AB60[i];
      `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006040  mov     [rsp+arg_0], rbx
0x140006045  mov     [rsp+arg_8], rdi
0x14000604a  push    r14
0x14000604c  sub     rsp, 20h
0x140006050  cmp     cs:?value@?1??_initialized@_data_ScenarioDbObjectType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_initialized(void)'::`2'::value
0x140006057  jnz     short loc_1400060C2
0x140006059  xor     edi, edi
0x14000605b  lea     r14, cs:140000000h
0x140006062  xor     ebx, ebx
0x140006064  mov     rcx, ds:rva off_14001AB60[r14+rbx*8]; Str
0x14000606c  lea     rax, rva ?storage@?1??_name_storage@_data_ScenarioDbObjectType@better_enums@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "Invalid,Scenario,EtwTrigger,TimeTrigger"... ...
0x140006073  add     rax, rdi
0x140006076  lea     rdx, Control; "= \t\n"
0x14000607d  mov     rva ?value@?1??_name_array@_data_ScenarioDbObjectType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_name_array(void)'::`2'::value ...
0x140006085  call    cs:__imp_strcspn
0x14000608b  mov     rcx, ds:rva off_14001AB60[r14+rbx*8]; "Invalid" ...
0x140006093  add     rax, rdi
0x140006096  mov     byte ptr [rax+r14+25CD0h], 0
0x14000609f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400060a3  inc     rax
0x1400060a6  cmp     byte ptr [rcx+rax], 0
0x1400060aa  jnz     short loc_1400060A3
0x1400060ac  inc     rdi
0x1400060af  inc     rbx
0x1400060b2  add     rdi, rax
0x1400060b5  cmp     rbx, 35h ; '5'
0x1400060b9  jb      short loc_140006064
0x1400060bb  mov     cs:?value@?1??_initialized@_data_ScenarioDbObjectType@better_enums@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::better_enums::_data_ScenarioDbObjectType::_initialized(void)'::`2'::value
0x1400060c2  mov     rbx, [rsp+28h+arg_0]
0x1400060c7  mov     rdi, [rsp+28h+arg_8]
0x1400060cc  add     rsp, 20h
0x1400060d0  pop     r14
0x1400060d2  retn
```
