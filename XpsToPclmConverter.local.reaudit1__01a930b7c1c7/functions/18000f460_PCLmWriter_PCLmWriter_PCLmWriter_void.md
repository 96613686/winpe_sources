# PCLmWriter::PCLmWriter::PCLmWriter(void)

- ea: `0x18000f460`
- end: `0x18000f4eb`
- name: `??0PCLmWriter@0@QEAA@XZ`
- size: `139`
- prototype: `PCLmWriter *__fastcall(PCLmWriter::PCLmWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fd5c`

## callees

- `0x18000d9ac`
- `0x18000f460`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter *__fastcall PCLmWriter::PCLmWriter::PCLmWriter(PCLmWriter::PCLmWriter *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>(this);
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPCLmWriter>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &PCLmWriter::PCLmWriter::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  return this;
}

```

## disassembly

```asm
0x18000f460  push    rbx
0x18000f462  sub     rsp, 20h
0x18000f466  mov     rbx, rcx
0x18000f469  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPCLmWriter@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPCLmWriter>(void)
0x18000f46e  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPCLmWriter@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPCLmWriter>::`vftable'
0x18000f475  mov     [rbx], rcx
0x18000f478  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f47f  test    rcx, rcx
0x18000f482  jz      short loc_18000F491
0x18000f484  mov     rax, [rcx]
0x18000f487  mov     rax, [rax+8]
0x18000f48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f490  nop
0x18000f491  lea     rax, ??_7PCLmWriter@0@6B@; const PCLmWriter::PCLmWriter::`vftable'
0x18000f498  mov     [rbx], rax
0x18000f49b  mov     qword ptr [rbx+10h], 0
0x18000f4a3  mov     qword ptr [rbx+18h], 0
0x18000f4ab  mov     qword ptr [rbx+20h], 0
0x18000f4b3  mov     qword ptr [rbx+28h], 0
0x18000f4bb  mov     qword ptr [rbx+30h], 0
0x18000f4c3  mov     qword ptr [rbx+38h], 0
0x18000f4cb  mov     qword ptr [rbx+40h], 0
0x18000f4d3  mov     qword ptr [rbx+48h], 0
0x18000f4db  mov     dword ptr [rbx+50h], 0
0x18000f4e2  mov     rax, rbx
0x18000f4e5  add     rsp, 20h
0x18000f4e9  pop     rbx
0x18000f4ea  retn
```
