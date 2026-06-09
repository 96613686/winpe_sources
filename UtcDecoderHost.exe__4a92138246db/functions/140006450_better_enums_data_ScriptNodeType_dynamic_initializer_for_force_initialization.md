# better_enums::_data_ScriptNodeType::_dynamic_initializer_for___force_initialization__

- ea: `0x140006450`
- end: `0x1400064e3`
- name: `better_enums::_data_ScriptNodeType::_dynamic_initializer_for___force_initialization__`
- size: `147`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140006450`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006495`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x140006495`

## string_xrefs

- `0x14000647c`: `Assign,Add,Sub,Mult,Div,Mod,BitwiseOr,BitwiseAnd,BitwiseNot,BitwiseXor,LeftShift,RightShift,Or,And,Not,Less,Greater,LessEqual,GreaterEqual,Equal,NotEqual,Var,Constant,Transition,FileFunction,ServiceFunction,RegistryFunction,OtherFunction,Return,TriggerField,Unknown,`

## pseudocode

```c
void better_enums::_data_ScriptNodeType::_dynamic_initializer_for___force_initialization__()
{
  __int64 v0; // rdi
  unsigned __int64 i; // rbx
  const char *v2; // rcx
  size_t v3; // rax
  char *v4; // rcx
  __int64 v5; // rax

  if ( !`better_enums::_data_ScriptNodeType::_initialized'::`2'::value )
  {
    v0 = 0;
    for ( i = 0; i < 0x1F; ++i )
    {
      v2 = off_140019420[i];
      `better_enums::_data_ScriptNodeType::_name_array'::`2'::value[i] = (__int64)&`better_enums::_data_ScriptNodeType::_name_storage'::`2'::storage[v0];
      v3 = strcspn(v2, "= \t\n");
      v4 = off_140019420[i];
      `better_enums::_data_ScriptNodeType::_name_storage'::`2'::storage[v0 + v3] = 0;
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v0 += v5 + 1;
    }
    `better_enums::_data_ScriptNodeType::_initialized'::`2'::value = 1;
  }
}

```

## disassembly

```asm
0x140006450  mov     [rsp+arg_0], rbx
0x140006455  mov     [rsp+arg_8], rdi
0x14000645a  push    r14
0x14000645c  sub     rsp, 20h
0x140006460  cmp     cs:?value@?1??_initialized@_data_ScriptNodeType@better_enums@@YAAEA_NXZ@4_NA, 0; bool `better_enums::_data_ScriptNodeType::_initialized(void)'::`2'::value
0x140006467  jnz     short loc_1400064D2
0x140006469  xor     edi, edi
0x14000646b  lea     r14, cs:140000000h
0x140006472  xor     ebx, ebx
0x140006474  mov     rcx, ds:rva off_140019420[r14+rbx*8]; Str
0x14000647c  lea     rax, rva ?storage@?1??_name_storage@_data_ScriptNodeType@better_enums@@YAPEADXZ@4PADA[r14]; "Assign,Add,Sub,Mult,Div,Mod,BitwiseOr,B"... ...
0x140006483  add     rax, rdi
0x140006486  lea     rdx, Control; "= \t\n"
0x14000648d  mov     rva ?value@?1??_name_array@_data_ScriptNodeType@better_enums@@YAPEAPEBDXZ@4PAPEBDA[r14+rbx*8], rax; char const * near * `better_enums::_data_ScriptNodeType::_name_array(void)'::`2'::value ...
0x140006495  call    cs:__imp_strcspn
0x14000649b  mov     rcx, ds:rva off_140019420[r14+rbx*8]; "Assign" ...
0x1400064a3  add     rax, rdi
0x1400064a6  mov     byte ptr [rax+r14+26180h], 0
0x1400064af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400064b3  inc     rax
0x1400064b6  cmp     byte ptr [rcx+rax], 0
0x1400064ba  jnz     short loc_1400064B3
0x1400064bc  inc     rdi
0x1400064bf  inc     rbx
0x1400064c2  add     rdi, rax
0x1400064c5  cmp     rbx, 1Fh
0x1400064c9  jb      short loc_140006474
0x1400064cb  mov     cs:?value@?1??_initialized@_data_ScriptNodeType@better_enums@@YAAEA_NXZ@4_NA, 1; bool `better_enums::_data_ScriptNodeType::_initialized(void)'::`2'::value
0x1400064d2  mov     rbx, [rsp+28h+arg_0]
0x1400064d7  mov     rdi, [rsp+28h+arg_8]
0x1400064dc  add     rsp, 20h
0x1400064e0  pop     r14
0x1400064e2  retn
```
