# CodeIntegrity::Management::GetPolicyInformation(_GUID const *)

- ea: `0x180012da0`
- end: `0x180012e0e`
- name: `?GetPolicyInformation@Management@CodeIntegrity@@YA?AV?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@PEBU_GUID@@@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fb0`
- `0x1800096e0`

## callees

- `0x180002ab4`
- `0x18000de54`
- `0x180012da0`
- `0x180015518`
- `0x180017468`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::Management::GetPolicyInformation(_QWORD *a1, __int64 a2)
{
  CodeIntegrity::Management::SiPolicyView **v3; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  const struct CodeIntegrity::Management::SiPolicyView *v6; // rbx
  CodeIntegrity::Management::SiPolicyView *v7; // rax
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CodeIntegrity::Management::SiPolicyView *v15; // [rsp+50h] [rbp+18h] BYREF

  v3 = (CodeIntegrity::Management::SiPolicyView **)qword_180039828;
  std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(
    qword_180039828,
    &v15,
    a2);
  try
  {
    if ( v15 == *v3 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x260, v4, v5, v13);
    v6 = (CodeIntegrity::Management::SiPolicyView *)((char *)v15 + 32);
    v7 = (CodeIntegrity::Management::SiPolicyView *)operator new(0xB0u);
    v15 = v7;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x267, v8, v9);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x268, v11, v12);
  }
  if ( v15 == *v3 )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x260, v4, v5, v13);
  v6 = (CodeIntegrity::Management::SiPolicyView *)((char *)v15 + 32);
}

```

## disassembly

```asm
0x180012da0  mov     [rsp+arg_0], rbx
0x180012da5  push    rdi
0x180012da6  sub     rsp, 30h
0x180012daa  mov     rdi, rcx
0x180012dad  mov     r8, rdx
0x180012db0  lea     rdx, [rsp+38h+arg_10]
0x180012db5  mov     rbx, cs:qword_180039828
0x180012dbc  mov     rcx, rbx
0x180012dbf  call    ??$find@U_GUID@@U?$less@X@std@@$0A@@?$_Tree@V?$_Tset_traits@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>,0>>::find<_GUID,std::less<void>,0>(_GUID const &)
0x180012dc4  mov     rax, [rsp+38h+arg_10]
0x180012dc9  cmp     rax, [rbx]
0x180012dcc  jnz     short loc_180012DDD
0x180012dce  mov     rcx, [rsp+38h]; this
0x180012dd3  mov     edx, 260h; void *
0x180012dd8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012ddd  lea     rbx, [rax+20h]
0x180012de1  mov     ecx, 0B0h; Size
0x180012de6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012deb  mov     [rsp+38h+arg_10], rax
0x180012df0  mov     rdx, rbx; struct CodeIntegrity::Management::SiPolicyView *
0x180012df3  mov     rcx, rax; this
0x180012df6  call    ??0SiPolicyView@Management@CodeIntegrity@@QEAA@AEBV012@@Z; CodeIntegrity::Management::SiPolicyView::SiPolicyView(CodeIntegrity::Management::SiPolicyView const &)
0x180012dfb  nop
0x180012dfc  mov     [rdi], rax
0x180012dff  mov     rax, rdi
0x180012e02  mov     rbx, [rsp+38h+arg_0]
0x180012e07  add     rsp, 30h
0x180012e0b  pop     rdi
0x180012e0c  retn
```
