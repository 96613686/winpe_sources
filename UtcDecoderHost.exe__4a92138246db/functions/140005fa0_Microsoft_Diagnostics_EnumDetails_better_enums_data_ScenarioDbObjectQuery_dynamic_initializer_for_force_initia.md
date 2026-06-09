# Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_dynamic_initializer_for___force_initialization__

- ea: `0x140005fa0`
- end: `0x140006033`
- name: `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005fa0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005fe5`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140005fe5`

## string_xrefs

- `0x140005fcc`: `CheckScenarioInfo,WriteScenarioInfo,ReadScenarioNamespaceHash,ReadScenarioInfo,DeleteScenarioInfo,CheckTrigger,WriteTrigger,ReadTrigger,ReadRefTrigger,AddRefTrigger,RemoveRefTrigger,DeleteTrigger,CheckFilter,WriteFilter,ReadFilter,ReadRefFilter,AddRefFilter,RemoveRefFilter,DeleteFilter,CheckAction,WriteAction,ReadAction,ReadRefAction,AddRefAction,RemoveRefAction,DeleteAction,CheckScenarioStateModel,WriteScenarioStateModel,ReadScenarioStateModel,ReadRefScenarioStateModel,AddRefScenarioStateModel,`

## pseudocode

```c
void Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x3D; ++i )
    {
      v2 = off_140019860[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_name_array'::`2'::value[i] = (__int64)&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019860[i];
      `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140005fa0  mov     [rsp+arg_0], rbx
0x140005fa5  mov     [rsp+arg_8], rdi
0x140005faa  push    r14
0x140005fac  sub     rsp, 20h
0x140005fb0  cmp     cs:?value@?1??_initialized@_data_ScenarioDbObjectQuery@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 0; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_initialized(void)'::`2'::value
0x140005fb7  jnz     short loc_140006022
0x140005fb9  xor     edi, edi
0x140005fbb  lea     r14, cs:140000000h
0x140005fc2  xor     ebx, ebx
0x140005fc4  mov     rcx, ds:rva off_140019860[r14+rbx*8]; Str
0x140005fcc  lea     rax, rva ?storage@?1??_name_storage@_data_ScenarioDbObjectQuery@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEADXZ@4PADA[r14]; "CheckScenarioInfo,WriteScenarioInfo,Rea"... ...
0x140005fd3  add     rax, rdi
0x140005fd6  lea     rdx, Control; "= \t\n"
0x140005fdd  mov     rva ?value@?1??_name_array@_data_ScenarioDbObjectQuery@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_name_array(void)'::`2'::value ...
0x140005fe5  call    cs:__imp_strcspn
0x140005feb  mov     rcx, ds:rva off_140019860[r14+rbx*8]; "CheckScenarioInfo" ...
0x140005ff3  add     rax, rdi
0x140005ff6  mov     byte ptr [rax+r14+27670h], 0
0x140005fff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006003  inc     rax
0x140006006  cmp     byte ptr [rcx+rax], 0
0x14000600a  jnz     short loc_140006003
0x14000600c  inc     rdi
0x14000600f  inc     rbx
0x140006012  add     rdi, rax
0x140006015  cmp     rbx, 3Dh ; '='
0x140006019  jb      short loc_140005FC4
0x14000601b  mov     cs:?value@?1??_initialized@_data_ScenarioDbObjectQuery@better_enums@EnumDetails@Diagnostics@Microsoft@@YAAEA_NXZ@4_NA, 1; bool `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ScenarioDbObjectQuery::_initialized(void)'::`2'::value
0x140006022  mov     rbx, [rsp+28h+arg_0]
0x140006027  mov     rdi, [rsp+28h+arg_8]
0x14000602c  add     rsp, 20h
0x140006030  pop     r14
0x140006032  retn
```
