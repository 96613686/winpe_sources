# `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800092c0`
- end: `0x1800092e9`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `41`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  __int64 result; // rax

  byte_18001E7E8 = 1;
  Microsoft::WRL::Details::ModuleBase::module_ = (struct Microsoft::WRL::Details::ModuleBase *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_;
  result = 1;
  Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ = (__int64)&Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800092c0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800092c7  mov     cs:byte_18001E7E8, 1
0x1800092ce  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rcx; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800092d5  mov     eax, 1
0x1800092da  lea     rcx, ??_7?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable'
0x1800092e1  mov     cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A, rcx; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800092e8  retn
```
