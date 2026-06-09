# InputStreamComAdapter::InputStreamComAdapter(InputStream &)

- ea: `0x180023dd0`
- end: `0x180023e36`
- name: `??0InputStreamComAdapter@@QEAA@AEAVInputStream@@@Z`
- size: `102`
- prototype: `InputStreamComAdapter *__fastcall(InputStreamComAdapter *__hidden this, struct InputStream *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022e90`

## callees

- `0x180023dd0`
- `0x18002c010`

## pseudocode

```c
InputStreamComAdapter *__fastcall InputStreamComAdapter::InputStreamComAdapter(
        InputStreamComAdapter *this,
        struct InputStream *a2)
{
  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &InputStreamComAdapter::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = a2;
  return this;
}

```

## disassembly

```asm
0x180023dd0  mov     [rsp+arg_0], rbx
0x180023dd5  push    rdi
0x180023dd6  sub     rsp, 20h
0x180023dda  mov     rdi, rdx
0x180023ddd  mov     rbx, rcx
0x180023de0  mov     dword ptr [rcx+0Ch], 1
0x180023de7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x180023dee  mov     [rcx], rax
0x180023df1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180023df8  test    rcx, rcx
0x180023dfb  jz      short loc_180023E0A
0x180023dfd  mov     rax, [rcx]
0x180023e00  mov     rax, [rax+8]
0x180023e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e09  nop
0x180023e0a  lea     rax, ??_7InputStreamComAdapter@@6B@; const InputStreamComAdapter::`vftable'
0x180023e11  mov     [rbx], rax
0x180023e14  mov     qword ptr [rbx+10h], 0
0x180023e1c  mov     qword ptr [rbx+18h], 0
0x180023e24  mov     [rbx+20h], rdi
0x180023e28  mov     rax, rbx
0x180023e2b  mov     rbx, [rsp+28h+arg_0]
0x180023e30  add     rsp, 20h
0x180023e34  pop     rdi
0x180023e35  retn
```
