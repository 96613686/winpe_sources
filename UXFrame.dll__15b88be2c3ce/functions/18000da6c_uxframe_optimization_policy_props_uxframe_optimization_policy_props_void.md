# uxframe_optimization_policy_props::uxframe_optimization_policy_props(void)

- ea: `0x18000da6c`
- end: `0x18000db53`
- name: `??0uxframe_optimization_policy_props@@QEAA@XZ`
- size: `231`
- prototype: `uxframe_optimization_policy_props *__fastcall(uxframe_optimization_policy_props *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d294`
- `0x180018f10`

## callees

- `0x18005a010`

## string_xrefs

- `0x18000da97`: `keep_xaml_thread_alive`
- `0x18000dacb`: `precreate_udk_extension_when_launching_normally`
- `0x18000db0d`: `precreate_udk_extension_when_prelaunching`

## pseudocode

```c
uxframe_optimization_policy_props *__fastcall uxframe_optimization_policy_props::uxframe_optimization_policy_props(
        uxframe_optimization_policy_props *this)
{
  _QWORD *v1; // rbx
  uxframe_optimization_policy_props *result; // rax

  v1 = (_QWORD *)((char *)this + 24);
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &uxframe_optimization_policy_props::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = "keep_xaml_thread_alive";
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 3) = &fc::config_property<bool,fc::details::minmax<bool,0>>::`vftable';
  *((_BYTE *)this + 65) = 1;
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4), (char *)this + 24);
  *v1 = &fc::config_value<bool,fc::details::minmax<bool,0>>::`vftable';
  *((_QWORD *)this + 11) = "precreate_udk_extension_when_launching_normally";
  *((_QWORD *)this + 10) = this;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 9) = &fc::config_property<bool,fc::details::minmax<bool,0>>::`vftable';
  *((_BYTE *)this + 113) = 0;
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10), (char *)this + 72);
  *((_QWORD *)this + 9) = &fc::config_value<bool,fc::details::minmax<bool,0>>::`vftable';
  *((_QWORD *)this + 17) = "precreate_udk_extension_when_prelaunching";
  *((_QWORD *)this + 16) = this;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 15) = &fc::config_property<bool,fc::details::minmax<bool,0>>::`vftable';
  *((_BYTE *)this + 161) = 1;
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 64LL))(*((_QWORD *)this + 16), (char *)this + 120);
  result = this;
  *((_QWORD *)this + 15) = &fc::config_value<bool,fc::details::minmax<bool,0>>::`vftable';
  return result;
}

```

## disassembly

```asm
0x18000da6c  push    rbx
0x18000da6e  push    rbp
0x18000da6f  push    rsi
0x18000da70  push    rdi
0x18000da71  push    r14
0x18000da73  sub     rsp, 20h
0x18000da77  lea     rbx, [rcx+18h]
0x18000da7b  xor     r14d, r14d
0x18000da7e  mov     [rcx+8], r14
0x18000da82  lea     rax, ??_7uxframe_optimization_policy_props@@6B@; const uxframe_optimization_policy_props::`vftable'
0x18000da89  mov     [rcx], rax
0x18000da8c  lea     rbp, ??_7?$config_property@_NU?$minmax@_N$0A@@details@fc@@@fc@@6B@; const fc::config_property<bool,fc::details::minmax<bool,0>>::`vftable'
0x18000da93  mov     [rcx+10h], r14
0x18000da97  lea     rax, aKeepXamlThread; "keep_xaml_thread_alive"
0x18000da9e  mov     [rbx+10h], rax
0x18000daa2  mov     rdi, rcx
0x18000daa5  mov     [rbx+8], rcx
0x18000daa9  mov     rdx, rbx
0x18000daac  mov     [rbx+18h], r14
0x18000dab0  mov     [rbx+20h], r14
0x18000dab4  mov     [rbx], rbp
0x18000dab7  mov     byte ptr [rbx+29h], 1
0x18000dabb  mov     rcx, [rbx+8]
0x18000dabf  mov     rax, [rcx]
0x18000dac2  mov     rax, [rax+40h]
0x18000dac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dacb  lea     rax, aPrecreateUdkEx_0; "precreate_udk_extension_when_launching_"...
0x18000dad2  lea     rsi, ??_7?$config_value@_NU?$minmax@_N$0A@@details@fc@@@fc@@6B@; const fc::config_value<bool,fc::details::minmax<bool,0>>::`vftable'
0x18000dad9  mov     [rbx], rsi
0x18000dadc  lea     rbx, [rdi+48h]
0x18000dae0  mov     [rbx+10h], rax
0x18000dae4  mov     rdx, rbx
0x18000dae7  mov     [rbx+8], rdi
0x18000daeb  mov     [rbx+18h], r14
0x18000daef  mov     [rbx+20h], r14
0x18000daf3  mov     [rbx], rbp
0x18000daf6  mov     [rbx+29h], r14b
0x18000dafa  mov     rcx, [rbx+8]
0x18000dafe  mov     rax, [rcx]
0x18000db01  mov     rax, [rax+40h]
0x18000db05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0a  mov     [rbx], rsi
0x18000db0d  lea     rax, aPrecreateUdkEx; "precreate_udk_extension_when_prelaunchi"...
0x18000db14  lea     rbx, [rdi+78h]
0x18000db18  mov     [rbx+10h], rax
0x18000db1c  mov     rdx, rbx
0x18000db1f  mov     [rbx+8], rdi
0x18000db23  mov     [rbx+18h], r14
0x18000db27  mov     [rbx+20h], r14
0x18000db2b  mov     [rbx], rbp
0x18000db2e  mov     byte ptr [rbx+29h], 1
0x18000db32  mov     rcx, [rbx+8]
0x18000db36  mov     rax, [rcx]
0x18000db39  mov     rax, [rax+40h]
0x18000db3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db42  mov     rax, rdi
0x18000db45  mov     [rbx], rsi
0x18000db48  add     rsp, 20h
0x18000db4c  pop     r14
0x18000db4e  pop     rdi
0x18000db4f  pop     rsi
0x18000db50  pop     rbp
0x18000db51  pop     rbx
0x18000db52  retn
```
